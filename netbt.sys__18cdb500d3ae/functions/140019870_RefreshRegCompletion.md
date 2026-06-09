# RefreshRegCompletion

- ea: `0x140019870`
- end: `0x140019a0a`
- name: `RefreshRegCompletion`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140009e1c`
- `0x14000a7b0`
- `0x140019870`
- `0x140019db4`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001989c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001989c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400198cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001993d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400199f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400198cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001993d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400199f9`

## pseudocode

```c
void __fastcall RefreshRegCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  KIRQL v5; // al
  KIRQL v6; // si
  int v8; // [rsp+90h] [rbp+18h] BYREF

  v8 = 0;
  if ( a3 )
  {
    v5 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v6 = v5;
    if ( *(_QWORD *)(a3 + 72) )
    {
      if ( (*(_WORD *)(a3 + 20))-- == 1 )
      {
        KeReleaseSpinLock(&SpinLock, v5);
        InterlockedCallCompletion(a3, 258);
      }
      else
      {
        if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
          WPP_SF_qddds(
            *(_DWORD *)(a1 + 20),
            15,
            (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
            a1,
            *(_DWORD *)(a1 + 20),
            *(_DWORD *)(a1 + 20) + 1,
            86,
            (__int64)"minio\\netbt\\sys\\namesrv.c");
        _InterlockedAdd((volatile signed __int32 *)(a1 + 20), 1u);
        *(_WORD *)(a3 + 256) |= 1u;
        KeReleaseSpinLock(&SpinLock, v6);
        SendNameServiceRequest(*(_QWORD *)(a1 + 48), Str2, a1, 0, 0, 0, 0, 0, *(_DWORD *)(a1 + 224), 1, &v8);
        NbtDereferenceTracker(a1, 0, 1894, "minio\\netbt\\sys\\namesrv.c");
      }
    }
    else
    {
      byte_140039680 &= ~1u;
      KeReleaseSpinLock(&SpinLock, v5);
    }
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 48) + 112LL) = 0;
    byte_140039680 &= ~1u;
  }
}

```

## disassembly

```asm
0x140019870  mov     rax, rsp
0x140019873  mov     [rax+10h], rbx
0x140019877  mov     [rax+20h], rbp
0x14001987b  push    rsi
0x14001987c  push    rdi
0x14001987d  push    r12
0x14001987f  sub     rsp, 60h
0x140019883  mov     dword ptr [rax+18h], 0
0x14001988a  mov     rbx, r8
0x14001988d  mov     rdi, rcx
0x140019890  test    r8, r8
0x140019893  jz      short loc_1400198E6
0x140019895  lea     rcx, SpinLock; SpinLock
0x14001989c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400198a3  nop     dword ptr [rax+rax+00h]
0x1400198a8  cmp     qword ptr [rbx+48h], 0
0x1400198ad  mov     sil, al
0x1400198b0  jz      loc_1400199E8
0x1400198b6  mov     eax, 0FFFFh
0x1400198bb  add     [rbx+14h], ax
0x1400198bf  jnz     short loc_14001990F
0x1400198c1  mov     dl, sil; NewIrql
0x1400198c4  lea     rcx, SpinLock; SpinLock
0x1400198cb  call    cs:__imp_KeReleaseSpinLock
0x1400198d2  nop     dword ptr [rax+rax+00h]
0x1400198d7  mov     edx, 102h
0x1400198dc  mov     rcx, rbx
0x1400198df  call    InterlockedCallCompletion
0x1400198e4  jmp     short loc_1400198F9
0x1400198e6  mov     rax, [rcx+30h]
0x1400198ea  mov     qword ptr [rax+70h], 0
0x1400198f2  and     cs:byte_140039680, 0FEh
0x1400198f9  lea     r11, [rsp+78h+var_18]
0x1400198fe  mov     rbx, [r11+28h]
0x140019902  mov     rbp, [r11+38h]
0x140019906  mov     rsp, r11
0x140019909  pop     r12
0x14001990b  pop     rdi
0x14001990c  pop     rsi
0x14001990d  retn
0x14001990f  test    byte ptr cs:xmmword_140038420+9, 40h
0x140019916  lea     r12, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x14001991d  jnz     loc_1400199B4
0x140019923  mov     ebp, 1
0x140019928  lock add [rdi+14h], ebp
0x14001992c  or      [rbx+100h], bp
0x140019933  lea     rcx, SpinLock; SpinLock
0x14001993a  mov     dl, sil; NewIrql
0x14001993d  call    cs:__imp_KeReleaseSpinLock
0x140019944  nop     dword ptr [rax+rax+00h]
0x140019949  mov     rdx, cs:Str2
0x140019950  lea     rax, [rsp+78h+arg_10]
0x140019958  mov     rcx, [rdi+30h]
0x14001995c  xor     r9d, r9d
0x14001995f  mov     [rsp+78h+var_28], rax
0x140019964  mov     r8, rdi
0x140019967  mov     eax, [rdi+0E0h]
0x14001996d  mov     [rsp+78h+var_30], ebp
0x140019971  mov     [rsp+78h+var_38], eax
0x140019975  mov     dword ptr [rsp+78h+var_40], 0
0x14001997d  mov     [rsp+78h+var_48], 0
0x140019985  mov     [rsp+78h+var_50], 0
0x14001998e  mov     [rsp+78h+var_58], 0
0x140019997  call    SendNameServiceRequest
0x14001999c  mov     r9, r12
0x14001999f  xor     edx, edx
0x1400199a1  mov     r8d, 766h
0x1400199a7  mov     rcx, rdi
0x1400199aa  call    NbtDereferenceTracker
0x1400199af  jmp     loc_1400198F9
0x1400199b4  mov     ecx, [rdi+14h]
0x1400199b7  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x1400199be  mov     [rsp+78h+var_40], r12
0x1400199c3  mov     edx, 0Fh
0x1400199c8  mov     [rsp+78h+var_48], 756h
0x1400199d0  mov     r9, rdi
0x1400199d3  lea     eax, [rcx+1]
0x1400199d6  mov     dword ptr [rsp+78h+var_50], eax
0x1400199da  mov     dword ptr [rsp+78h+var_58], ecx
0x1400199de  call    WPP_SF_qddds
0x1400199e3  jmp     loc_140019923
0x1400199e8  and     cs:byte_140039680, 0FEh
0x1400199ef  lea     rcx, SpinLock; SpinLock
0x1400199f6  mov     dl, sil; NewIrql
0x1400199f9  call    cs:__imp_KeReleaseSpinLock
0x140019a00  nop     dword ptr [rax+rax+00h]
0x140019a05  jmp     loc_1400198F9
```
