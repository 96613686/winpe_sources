# FveWrqCompleteRequestByFileObject

- ea: `0x14002e440`
- end: `0x14002e628`
- name: `FveWrqCompleteRequestByFileObject`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400878e0`

## callees

- `0x140008f04`
- `0x14000a210`
- `0x14000bc14`
- `0x140022cd0`
- `0x14002e440`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002e53a`
- `ntoskrnl!IofCompleteRequest` at `0x14002e53a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e485`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e485`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e466`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e466`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e5ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e5ce`

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
0x14002e440  push    rbx
0x14002e442  push    rbp
0x14002e443  push    rsi
0x14002e444  push    rdi
0x14002e445  push    r14
0x14002e447  push    r15
0x14002e449  sub     rsp, 38h
0x14002e44d  mov     rsi, rdx
0x14002e450  lea     r15, [rcx+320h]
0x14002e457  mov     rbp, rcx
0x14002e45a  lea     r14, [rcx+308h]
0x14002e461  xor     edi, edi
0x14002e463  mov     rcx, r15; SpinLock
0x14002e466  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002e46d  nop     dword ptr [rax+rax+00h]
0x14002e472  mov     rcx, [r14]
0x14002e475  mov     r8b, al
0x14002e478  xor     ebx, ebx
0x14002e47a  cmp     rcx, r14
0x14002e47d  jnz     short loc_14002E4CE
0x14002e47f  mov     dl, r8b; NewIrql
0x14002e482  mov     rcx, r15; SpinLock
0x14002e485  call    cs:__imp_KeReleaseSpinLock
0x14002e48c  nop     dword ptr [rax+rax+00h]
0x14002e491  test    rbx, rbx
0x14002e494  jnz     short loc_14002E4FD
0x14002e496  test    edi, edi
0x14002e498  jnz     loc_14002E5DF
0x14002e49e  add     rsp, 38h
0x14002e4a2  pop     r15
0x14002e4a4  pop     r14
0x14002e4a6  pop     rdi
0x14002e4a7  pop     rsi
0x14002e4a8  pop     rbp
0x14002e4a9  pop     rbx
0x14002e4aa  retn
0x14002e4ac  mov     rdx, [rcx]
0x14002e4af  cmp     [rdx+8], rcx
0x14002e4b3  jnz     short loc_14002E4BE
0x14002e4b5  mov     rax, [rcx+8]
0x14002e4b9  cmp     [rax], rcx
0x14002e4bc  jz      short loc_14002E4C5
0x14002e4be  mov     ecx, 3
0x14002e4c3  int     29h; Win8: RtlFailFast(ecx)
0x14002e4c5  mov     [rax], rdx
0x14002e4c8  mov     [rdx+8], rax
0x14002e4cc  jmp     short loc_14002E47F
0x14002e4ce  mov     rdx, [rcx+18h]
0x14002e4d2  mov     rbx, rcx
0x14002e4d5  test    rdx, rdx
0x14002e4d8  jz      short loc_14002E4DF
0x14002e4da  cmp     rdx, rsi
0x14002e4dd  jmp     short loc_14002E4F3
0x14002e4df  mov     rax, [rcx+20h]
0x14002e4e3  test    rax, rax
0x14002e4e6  jz      short loc_14002E4F5
0x14002e4e8  mov     rax, [rax+0B8h]
0x14002e4ef  cmp     [rax+30h], rsi
0x14002e4f3  jz      short loc_14002E4AC
0x14002e4f5  mov     rcx, [rcx]
0x14002e4f8  jmp     loc_14002E478
0x14002e4fd  mov     rax, [rbx+20h]
0x14002e501  test    rax, rax
0x14002e504  jz      short loc_14002E546
0x14002e506  cmp     qword ptr [rbx+18h], 0
0x14002e50b  jz      short loc_14002E521
0x14002e50d  mov     rdx, [rbx+28h]
0x14002e511  mov     r8d, 0C0000120h
0x14002e517  mov     rcx, rbp
0x14002e51a  call    _guard_dispatch_icall
0x14002e51f  jmp     short loc_14002E546
0x14002e521  mov     qword ptr [rax+38h], 0
0x14002e529  xor     edx, edx; PriorityBoost
0x14002e52b  mov     rax, [rbx+20h]
0x14002e52f  mov     dword ptr [rax+30h], 0C0000120h
0x14002e536  mov     rcx, [rbx+20h]; Irp
0x14002e53a  call    cs:__imp_IofCompleteRequest
0x14002e541  nop     dword ptr [rax+rax+00h]
0x14002e546  inc     edi
0x14002e548  cmp     edi, 1
0x14002e54b  jnz     short loc_14002E58D
0x14002e54d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e554  lea     rax, WPP_GLOBAL_Control
0x14002e55b  cmp     rcx, rax
0x14002e55e  jz      short loc_14002E5C6
0x14002e560  mov     eax, [rcx+2Ch]
0x14002e563  test    al, 8
0x14002e565  jz      short loc_14002E58D
0x14002e567  cmp     byte ptr [rcx+29h], 5
0x14002e56b  jb      short loc_14002E58D
0x14002e56d  mov     rcx, [rcx+18h]
0x14002e571  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002e578  mov     edx, 89h
0x14002e57d  mov     [rsp+68h+var_48], 0C0000120h
0x14002e585  mov     r9, rsi
0x14002e588  call    WPP_SF_qd
0x14002e58d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e594  lea     rax, WPP_GLOBAL_Control
0x14002e59b  cmp     rcx, rax
0x14002e59e  jz      short loc_14002E5C6
0x14002e5a0  mov     eax, [rcx+2Ch]
0x14002e5a3  test    al, 8
0x14002e5a5  jz      short loc_14002E5C6
0x14002e5a7  cmp     byte ptr [rcx+29h], 5
0x14002e5ab  jb      short loc_14002E5C6
0x14002e5ad  mov     r9, [rbx+10h]
0x14002e5b1  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002e5b8  mov     rcx, [rcx+18h]
0x14002e5bc  mov     edx, 8Ah
0x14002e5c1  call    WPP_SF_q
0x14002e5c6  mov     edx, 30455646h; Tag
0x14002e5cb  mov     rcx, rbx; P
0x14002e5ce  call    cs:__imp_ExFreePoolWithTag
0x14002e5d5  nop     dword ptr [rax+rax+00h]
0x14002e5da  jmp     loc_14002E463
0x14002e5df  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e5e6  lea     rax, WPP_GLOBAL_Control
0x14002e5ed  cmp     rcx, rax
0x14002e5f0  jz      loc_14002E49E
0x14002e5f6  mov     eax, [rcx+2Ch]
0x14002e5f9  test    al, 8
0x14002e5fb  jz      loc_14002E49E
0x14002e601  cmp     byte ptr [rcx+29h], 5
0x14002e605  jb      loc_14002E49E
0x14002e60b  mov     rcx, [rcx+18h]
0x14002e60f  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002e616  mov     edx, 8Bh
0x14002e61b  mov     r9d, edi
0x14002e61e  call    WPP_SF_d
0x14002e623  jmp     loc_14002E49E
```
