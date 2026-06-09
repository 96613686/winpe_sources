# FveWrqCompleteRequestByFileObject

- ea: `0x14002d440`
- end: `0x14002d628`
- name: `FveWrqCompleteRequestByFileObject`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140085840`

## callees

- `0x140008e44`
- `0x14000a150`
- `0x14000ba88`
- `0x1400219a0`
- `0x14002d440`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002d53a`
- `ntoskrnl!IofCompleteRequest` at `0x14002d53a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002d485`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002d485`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d466`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d466`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d5ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d5ce`

## pseudocode

```c
void __fastcall FveWrqCompleteRequestByFileObject(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v3; // r15
  _QWORD **v5; // r14
  unsigned int v6; // edi
  KIRQL v7; // al
  _QWORD *v8; // rcx
  KIRQL v9; // r8
  _QWORD *v10; // rbx
  __int64 v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  bool v14; // zf
  __int64 v15; // rax
  __int64 v16; // rax

  v3 = (KSPIN_LOCK *)(a1 + 800);
  v5 = (_QWORD **)(a1 + 776);
  v6 = 0;
  while ( 2 )
  {
    v7 = KeAcquireSpinLockRaiseToDpc(v3);
    v8 = *v5;
    v9 = v7;
    while ( 1 )
    {
      v10 = 0;
      if ( v8 == v5 )
        break;
      v13 = v8[3];
      v10 = v8;
      if ( v13 )
      {
        v14 = v13 == a2;
      }
      else
      {
        v15 = v8[4];
        if ( !v15 )
          goto LABEL_16;
        v14 = *(_QWORD *)(*(_QWORD *)(v15 + 184) + 48LL) == a2;
      }
      if ( v14 )
      {
        v11 = *v8;
        if ( *(_QWORD **)(*v8 + 8LL) != v8 || (v12 = (_QWORD *)v8[1], (_QWORD *)*v12 != v8) )
          __fastfail(3u);
        *v12 = v11;
        *(_QWORD *)(v11 + 8) = v12;
        break;
      }
LABEL_16:
      v8 = (_QWORD *)*v8;
    }
    KeReleaseSpinLock(v3, v9);
    if ( v10 )
    {
      v16 = v10[4];
      if ( v16 )
      {
        if ( v10[3] )
        {
          ((void (__fastcall *)(__int64, _QWORD, __int64))v16)(a1, v10[5], 3221225760LL);
        }
        else
        {
          *(_QWORD *)(v16 + 56) = 0;
          *(_DWORD *)(v10[4] + 48LL) = -1073741536;
          IofCompleteRequest((PIRP)v10[4], 0);
        }
      }
      if ( ++v6 == 1 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
LABEL_30:
          ExFreePoolWithTag(v10, 0x30455646u);
          continue;
        }
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_qd(
            WPP_GLOBAL_Control->AttachedDevice,
            137,
            WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
            a2,
            -1073741536);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids, v10[2]);
      }
      goto LABEL_30;
    }
    break;
  }
  if ( v6
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids, v6);
  }
}

```

## disassembly

```asm
0x14002d440  push    rbx
0x14002d442  push    rbp
0x14002d443  push    rsi
0x14002d444  push    rdi
0x14002d445  push    r14
0x14002d447  push    r15
0x14002d449  sub     rsp, 38h
0x14002d44d  mov     rsi, rdx
0x14002d450  lea     r15, [rcx+320h]
0x14002d457  mov     rbp, rcx
0x14002d45a  lea     r14, [rcx+308h]
0x14002d461  xor     edi, edi
0x14002d463  mov     rcx, r15; SpinLock
0x14002d466  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002d46d  nop     dword ptr [rax+rax+00h]
0x14002d472  mov     rcx, [r14]
0x14002d475  mov     r8b, al
0x14002d478  xor     ebx, ebx
0x14002d47a  cmp     rcx, r14
0x14002d47d  jnz     short loc_14002D4CE
0x14002d47f  mov     dl, r8b; NewIrql
0x14002d482  mov     rcx, r15; SpinLock
0x14002d485  call    cs:__imp_KeReleaseSpinLock
0x14002d48c  nop     dword ptr [rax+rax+00h]
0x14002d491  test    rbx, rbx
0x14002d494  jnz     short loc_14002D4FD
0x14002d496  test    edi, edi
0x14002d498  jnz     loc_14002D5DF
0x14002d49e  add     rsp, 38h
0x14002d4a2  pop     r15
0x14002d4a4  pop     r14
0x14002d4a6  pop     rdi
0x14002d4a7  pop     rsi
0x14002d4a8  pop     rbp
0x14002d4a9  pop     rbx
0x14002d4aa  retn
0x14002d4ac  mov     rdx, [rcx]
0x14002d4af  cmp     [rdx+8], rcx
0x14002d4b3  jnz     short loc_14002D4BE
0x14002d4b5  mov     rax, [rcx+8]
0x14002d4b9  cmp     [rax], rcx
0x14002d4bc  jz      short loc_14002D4C5
0x14002d4be  mov     ecx, 3
0x14002d4c3  int     29h; Win8: RtlFailFast(ecx)
0x14002d4c5  mov     [rax], rdx
0x14002d4c8  mov     [rdx+8], rax
0x14002d4cc  jmp     short loc_14002D47F
0x14002d4ce  mov     rdx, [rcx+18h]
0x14002d4d2  mov     rbx, rcx
0x14002d4d5  test    rdx, rdx
0x14002d4d8  jz      short loc_14002D4DF
0x14002d4da  cmp     rdx, rsi
0x14002d4dd  jmp     short loc_14002D4F3
0x14002d4df  mov     rax, [rcx+20h]
0x14002d4e3  test    rax, rax
0x14002d4e6  jz      short loc_14002D4F5
0x14002d4e8  mov     rax, [rax+0B8h]
0x14002d4ef  cmp     [rax+30h], rsi
0x14002d4f3  jz      short loc_14002D4AC
0x14002d4f5  mov     rcx, [rcx]
0x14002d4f8  jmp     loc_14002D478
0x14002d4fd  mov     rax, [rbx+20h]
0x14002d501  test    rax, rax
0x14002d504  jz      short loc_14002D546
0x14002d506  cmp     qword ptr [rbx+18h], 0
0x14002d50b  jz      short loc_14002D521
0x14002d50d  mov     rdx, [rbx+28h]
0x14002d511  mov     r8d, 0C0000120h
0x14002d517  mov     rcx, rbp
0x14002d51a  call    _guard_dispatch_icall
0x14002d51f  jmp     short loc_14002D546
0x14002d521  mov     qword ptr [rax+38h], 0
0x14002d529  xor     edx, edx; PriorityBoost
0x14002d52b  mov     rax, [rbx+20h]
0x14002d52f  mov     dword ptr [rax+30h], 0C0000120h
0x14002d536  mov     rcx, [rbx+20h]; Irp
0x14002d53a  call    cs:__imp_IofCompleteRequest
0x14002d541  nop     dword ptr [rax+rax+00h]
0x14002d546  inc     edi
0x14002d548  cmp     edi, 1
0x14002d54b  jnz     short loc_14002D58D
0x14002d54d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d554  lea     rax, WPP_GLOBAL_Control
0x14002d55b  cmp     rcx, rax
0x14002d55e  jz      short loc_14002D5C6
0x14002d560  mov     eax, [rcx+2Ch]
0x14002d563  test    al, 8
0x14002d565  jz      short loc_14002D58D
0x14002d567  cmp     byte ptr [rcx+29h], 5
0x14002d56b  jb      short loc_14002D58D
0x14002d56d  mov     rcx, [rcx+18h]
0x14002d571  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002d578  mov     edx, 89h
0x14002d57d  mov     [rsp+68h+var_48], 0C0000120h
0x14002d585  mov     r9, rsi
0x14002d588  call    WPP_SF_qd
0x14002d58d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d594  lea     rax, WPP_GLOBAL_Control
0x14002d59b  cmp     rcx, rax
0x14002d59e  jz      short loc_14002D5C6
0x14002d5a0  mov     eax, [rcx+2Ch]
0x14002d5a3  test    al, 8
0x14002d5a5  jz      short loc_14002D5C6
0x14002d5a7  cmp     byte ptr [rcx+29h], 5
0x14002d5ab  jb      short loc_14002D5C6
0x14002d5ad  mov     r9, [rbx+10h]
0x14002d5b1  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002d5b8  mov     rcx, [rcx+18h]
0x14002d5bc  mov     edx, 8Ah
0x14002d5c1  call    WPP_SF_q
0x14002d5c6  mov     edx, 30455646h; Tag
0x14002d5cb  mov     rcx, rbx; P
0x14002d5ce  call    cs:__imp_ExFreePoolWithTag
0x14002d5d5  nop     dword ptr [rax+rax+00h]
0x14002d5da  jmp     loc_14002D463
0x14002d5df  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d5e6  lea     rax, WPP_GLOBAL_Control
0x14002d5ed  cmp     rcx, rax
0x14002d5f0  jz      loc_14002D49E
0x14002d5f6  mov     eax, [rcx+2Ch]
0x14002d5f9  test    al, 8
0x14002d5fb  jz      loc_14002D49E
0x14002d601  cmp     byte ptr [rcx+29h], 5
0x14002d605  jb      loc_14002D49E
0x14002d60b  mov     rcx, [rcx+18h]
0x14002d60f  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002d616  mov     edx, 8Bh
0x14002d61b  mov     r9d, edi
0x14002d61e  call    WPP_SF_d
0x14002d623  jmp     loc_14002D49E
```
