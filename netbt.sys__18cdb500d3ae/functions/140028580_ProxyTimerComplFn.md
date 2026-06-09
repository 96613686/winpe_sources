# ProxyTimerComplFn

- ea: `0x140028580`
- end: `0x140028808`
- name: `ProxyTimerComplFn`
- size: `648`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007ed8`
- `0x140008160`
- `0x140009e1c`
- `0x14000a7b0`
- `0x140028580`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400285fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400285fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002870c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002878d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002870c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002878d`

## pseudocode

```c
void __fastcall ProxyTimerComplFn(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  KIRQL v6; // r14
  int v8; // ecx
  char *v9; // rbx
  _QWORD *v10; // rax
  void **v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  int v14; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+20h] BYREF

  v15 = 0;
  v14 = 0;
  if ( !a3 )
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 48) + 112LL) = 0;
    _InterlockedDecrement(&dword_1400394B0);
    NbtDereferenceName(*(PVOID *)(a1 + 48), (__int64)"minio\\netbt\\sys\\proxy.c");
    LOBYTE(v5) = 1;
    NbtDereferenceTracker(a1, v5, 232, "minio\\netbt\\sys\\proxy.c");
    return;
  }
  v6 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( (*(_WORD *)(a3 + 20))-- == 1 )
  {
    v8 = *(_DWORD *)(a1 + 240);
    if ( (v8 & 2) == 0 )
    {
      *(_QWORD *)(a3 + 72) = 0;
      v9 = *(char **)(a1 + 48);
      *((_QWORD *)v9 + 14) = 0;
      v10 = *(_QWORD **)v9;
      if ( *(char **)(*(_QWORD *)v9 + 8LL) != v9 || (v11 = (void **)*((_QWORD *)v9 + 1), *v11 != v9) )
        __fastfail(3u);
      *v11 = v10;
      v10[1] = v11;
      *((_QWORD *)v9 + 1) = v9;
      *(_QWORD *)v9 = v9;
      if ( (int)AddToHashTable(
                  qword_140039468,
                  v9 + 164,
                  Str2,
                  *((unsigned int *)v9 + 8),
                  0,
                  0,
                  &v15,
                  *(_QWORD *)(a1 + 32),
                  48) >= 0 )
      {
        v12 = v15;
        *(_DWORD *)(v15 + 72) = *(_DWORD *)(v15 + 72) & 0xFFFFFF0F | 0x20;
        *(_DWORD *)(v12 + 56) = 60000;
      }
      _InterlockedDecrement(&dword_1400394B0);
      NbtDereferenceName(v9, (__int64)"minio\\netbt\\sys\\proxy.c");
      LOBYTE(v13) = 1;
      NbtDereferenceTracker(a1, v13, 295, "minio\\netbt\\sys\\proxy.c");
      KeReleaseSpinLock(&SpinLock, v6);
      return;
    }
    *(_DWORD *)(a1 + 240) = v8 & 0xFFFFFFF9 | 4;
    *(_WORD *)(a3 + 20) = word_1400395D8;
  }
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      *(_DWORD *)(a1 + 20),
      15,
      (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
      a1,
      *(_DWORD *)(a1 + 20),
      *(_DWORD *)(a1 + 20) + 1,
      56,
      (__int64)"minio\\netbt\\sys\\proxy.c");
  _InterlockedAdd((volatile signed __int32 *)(a1 + 20), 1u);
  KeReleaseSpinLock(&SpinLock, v6);
  SendNameServiceRequest(*(_QWORD *)(a1 + 48), Str2, a1, 0, 0, 0, 0, 0, 0, 1, &v14);
  NbtDereferenceTracker(a1, 0, 325, "minio\\netbt\\sys\\proxy.c");
  *(_WORD *)(a3 + 256) |= 1u;
}

```

## disassembly

```asm
0x140028580  mov     r11, rsp
0x140028583  mov     [r11+10h], rbx
0x140028587  push    rbp
0x140028588  push    rsi
0x140028589  push    rdi
0x14002858a  push    r14
0x14002858c  push    r15
0x14002858e  sub     rsp, 60h
0x140028592  xor     r15d, r15d
0x140028595  mov     rbx, r8
0x140028598  mov     [r11+20h], r15
0x14002859c  mov     rdi, rcx
0x14002859f  mov     [r11+18h], r15d
0x1400285a3  test    r8, r8
0x1400285a6  jnz     short loc_1400285F4
0x1400285a8  mov     rax, [rcx+30h]
0x1400285ac  lea     ebp, [r8+1]
0x1400285b0  lea     rsi, aMinioNetbtSysP_0; "minio\\netbt\\sys\\proxy.c"
0x1400285b7  mov     r9d, 0E7h
0x1400285bd  mov     r8b, bpl
0x1400285c0  mov     [r11-68h], rsi
0x1400285c4  lea     edx, [rbx+0Ch]
0x1400285c7  mov     [rax+70h], r15
0x1400285cb  lock dec cs:dword_1400394B0
0x1400285d2  mov     rcx, [rcx+30h]; P
0x1400285d6  call    NbtDereferenceName
0x1400285db  mov     r9, rsi
0x1400285de  mov     r8d, 0E8h
0x1400285e4  mov     dl, bpl
0x1400285e7  mov     rcx, rdi
0x1400285ea  call    NbtDereferenceTracker
0x1400285ef  jmp     loc_1400287F3
0x1400285f4  lea     rcx, SpinLock; SpinLock
0x1400285fb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140028602  nop     dword ptr [rax+rax+00h]
0x140028607  mov     r14b, al
0x14002860a  mov     eax, 0FFFFh
0x14002860f  add     [rbx+14h], ax
0x140028613  jnz     loc_14002873B
0x140028619  mov     ecx, [rdi+0F0h]
0x14002861f  test    cl, 2
0x140028622  jnz     loc_140028724
0x140028628  mov     [rbx+48h], r15
0x14002862c  mov     rbx, [rdi+30h]
0x140028630  mov     [rbx+70h], r15
0x140028634  mov     rax, [rbx]
0x140028637  cmp     [rax+8], rbx
0x14002863b  jnz     loc_14002871D
0x140028641  mov     rcx, [rbx+8]
0x140028645  cmp     [rcx], rbx
0x140028648  jnz     loc_14002871D
0x14002864e  mov     [rcx], rax
0x140028651  lea     rdx, [rbx+0A4h]
0x140028658  mov     [rax+8], rcx
0x14002865c  mov     [rbx+8], rbx
0x140028660  mov     [rbx], rbx
0x140028663  mov     rax, [rdi+20h]
0x140028667  mov     r9d, [rbx+20h]
0x14002866b  mov     r8, cs:Str2
0x140028672  mov     rcx, cs:qword_140039468
0x140028679  mov     word ptr [rsp+88h+var_48], 30h ; '0'
0x140028680  mov     [rsp+88h+var_50], rax
0x140028685  lea     rax, [rsp+88h+arg_18]
0x14002868d  mov     [rsp+88h+var_58], rax
0x140028692  mov     [rsp+88h+var_60], r15
0x140028697  mov     dword ptr [rsp+88h+var_68], r15d
0x14002869c  call    AddToHashTable
0x1400286a1  test    eax, eax
0x1400286a3  js      short loc_1400286C2
0x1400286a5  mov     rdx, [rsp+88h+arg_18]
0x1400286ad  mov     eax, [rdx+48h]
0x1400286b0  and     eax, 0FFFFFF2Fh
0x1400286b5  or      eax, 20h
0x1400286b8  mov     [rdx+48h], eax
0x1400286bb  mov     dword ptr [rdx+38h], 0EA60h
0x1400286c2  lock dec cs:dword_1400394B0
0x1400286c9  lea     rsi, aMinioNetbtSysP_0; "minio\\netbt\\sys\\proxy.c"
0x1400286d0  mov     ebp, 1
0x1400286d5  mov     [rsp+88h+var_68], rsi; __int64
0x1400286da  mov     r9d, 126h
0x1400286e0  mov     r8b, bpl
0x1400286e3  mov     rcx, rbx; P
0x1400286e6  lea     edx, [rbp+0Bh]
0x1400286e9  call    NbtDereferenceName
0x1400286ee  mov     r9, rsi
0x1400286f1  mov     r8d, 127h
0x1400286f7  mov     dl, bpl
0x1400286fa  mov     rcx, rdi
0x1400286fd  call    NbtDereferenceTracker
0x140028702  mov     dl, r14b; NewIrql
0x140028705  lea     rcx, SpinLock; SpinLock
0x14002870c  call    cs:__imp_KeReleaseSpinLock
0x140028713  nop     dword ptr [rax+rax+00h]
0x140028718  jmp     loc_1400287F3
0x14002871d  mov     ecx, 3
0x140028722  int     29h; Win8: RtlFailFast(ecx)
0x140028724  and     ecx, 0FFFFFFFDh
0x140028727  or      ecx, 4
0x14002872a  mov     [rdi+0F0h], ecx
0x140028730  movzx   eax, cs:word_1400395D8
0x140028737  mov     [rbx+14h], ax
0x14002873b  test    byte ptr cs:xmmword_140038420+9, 40h
0x140028742  lea     rsi, aMinioNetbtSysP_0; "minio\\netbt\\sys\\proxy.c"
0x140028749  jz      short loc_14002877A
0x14002874b  mov     ecx, [rdi+14h]
0x14002874e  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x140028755  mov     [rsp+88h+var_50], rsi
0x14002875a  mov     edx, 0Fh
0x14002875f  mov     dword ptr [rsp+88h+var_58], 138h
0x140028767  mov     r9, rdi
0x14002876a  lea     eax, [rcx+1]
0x14002876d  mov     dword ptr [rsp+88h+var_60], eax
0x140028771  mov     dword ptr [rsp+88h+var_68], ecx
0x140028775  call    WPP_SF_qddds
0x14002877a  mov     ebp, 1
0x14002877f  lock add [rdi+14h], ebp
0x140028783  mov     dl, r14b; NewIrql
0x140028786  lea     rcx, SpinLock; SpinLock
0x14002878d  call    cs:__imp_KeReleaseSpinLock
0x140028794  nop     dword ptr [rax+rax+00h]
0x140028799  mov     rdx, cs:Str2
0x1400287a0  lea     rax, [rsp+88h+arg_10]
0x1400287a8  mov     rcx, [rdi+30h]
0x1400287ac  xor     r9d, r9d
0x1400287af  mov     [rsp+88h+var_38], rax
0x1400287b4  mov     r8, rdi
0x1400287b7  mov     [rsp+88h+var_40], ebp
0x1400287bb  mov     [rsp+88h+var_48], r15d
0x1400287c0  mov     dword ptr [rsp+88h+var_50], r15d
0x1400287c5  mov     dword ptr [rsp+88h+var_58], r15d
0x1400287ca  mov     [rsp+88h+var_60], r15
0x1400287cf  mov     [rsp+88h+var_68], r15
0x1400287d4  call    SendNameServiceRequest
0x1400287d9  mov     r9, rsi
0x1400287dc  xor     edx, edx
0x1400287de  mov     r8d, 145h
0x1400287e4  mov     rcx, rdi
0x1400287e7  call    NbtDereferenceTracker
0x1400287ec  or      [rbx+100h], bp
0x1400287f3  mov     rbx, [rsp+88h+arg_8]
0x1400287fb  add     rsp, 60h
0x1400287ff  pop     r15
0x140028801  pop     r14
0x140028803  pop     rdi
0x140028804  pop     rsi
0x140028805  pop     rbp
0x140028806  retn
```
