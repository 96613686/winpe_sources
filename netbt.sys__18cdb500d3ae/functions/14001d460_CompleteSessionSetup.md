# CompleteSessionSetup

- ea: `0x14001d460`
- end: `0x14001d57a`
- name: `CompleteSessionSetup`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001c600`

## callees

- `0x140004880`
- `0x140018d7c`
- `0x14001d460`
- `0x14001f310`
- `0x140025078`
- `0x140028c18`
- `0x1400400a4`
- `0x140040590`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d507`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d507`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d526`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d526`

## pseudocode

```c
__int64 CompleteSessionSetup(__int64 a1, __int64 a2, __int64 a3, ...)
{
  IRP *v3; // rdi
  NTSTATUS v6; // edx
  IRP *v7; // rcx
  int v9; // eax
  __int64 v10; // r9
  KIRQL v11; // bl
  IRP *v12; // [rsp+58h] [rbp+20h] BYREF
  va_list va; // [rsp+58h] [rbp+20h]
  va_list va1; // [rsp+60h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v12 = va_arg(va1, IRP *);
  v3 = v12;
  if ( *(_DWORD *)(*(_QWORD *)(a2 + 40) + 340LL) == 1 || (v9 = TcpSendSessionResponse(a2, 130, 0), v9 >= 0) )
  {
    if ( (BYTE2(xmmword_140038420) & 0x20) != 0 )
      WPP_SF_qq(1045, 26, WPP_ffc711f4ba0833be1e89b8c0ea368d15_Traceguids, a3, a2);
    v6 = 0;
    v7 = v3;
    goto LABEL_5;
  }
  if ( (BYTE2(xmmword_140038420) & 0x20) != 0 )
    WPP_SF_d(1045, 27, WPP_ffc711f4ba0833be1e89b8c0ea368d15_Traceguids, (unsigned int)v9);
  LOBYTE(v10) = 1;
  RejectSession(a2, 131, 131, v10);
  v11 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  RelistConnection(a3);
  KeReleaseSpinLock(&SpinLock, v11);
  GetIrpIfNotCancelled(a3, (IRP **)va);
  v7 = v12;
  if ( v12 )
  {
    v6 = -1073741823;
LABEL_5:
    NTIoComplete(v7, v6, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14001d460  mov     [rsp+arg_0], rbx
0x14001d465  mov     [rsp+arg_8], rsi
0x14001d46a  mov     [rsp+arg_18], r9
0x14001d46f  push    rdi
0x14001d470  sub     rsp, 30h
0x14001d474  mov     rax, [rdx+28h]
0x14001d478  mov     rdi, r9
0x14001d47b  mov     rsi, r8
0x14001d47e  mov     rbx, rdx
0x14001d481  cmp     dword ptr [rax+154h], 1
0x14001d488  jnz     short loc_14001D4B7
0x14001d48a  test    byte ptr cs:xmmword_140038420+2, 20h
0x14001d491  jnz     loc_14001D557
0x14001d497  xor     edx, edx
0x14001d499  mov     rcx, rdi; Irp
0x14001d49c  xor     r8d, r8d
0x14001d49f  call    NTIoComplete
0x14001d4a4  mov     rbx, [rsp+38h+arg_0]
0x14001d4a9  xor     eax, eax
0x14001d4ab  mov     rsi, [rsp+38h+arg_8]
0x14001d4b0  add     rsp, 30h
0x14001d4b4  pop     rdi
0x14001d4b5  retn
0x14001d4b7  xor     r8d, r8d
0x14001d4ba  mov     edx, 82h
0x14001d4bf  mov     rcx, rbx
0x14001d4c2  call    TcpSendSessionResponse
0x14001d4c7  test    eax, eax
0x14001d4c9  jns     short loc_14001D48A
0x14001d4cb  test    byte ptr cs:xmmword_140038420+2, 20h
0x14001d4d2  jz      short loc_14001D4ED
0x14001d4d4  mov     edx, 1Bh
0x14001d4d9  lea     r8, WPP_ffc711f4ba0833be1e89b8c0ea368d15_Traceguids
0x14001d4e0  mov     ecx, 415h
0x14001d4e5  mov     r9d, eax
0x14001d4e8  call    WPP_SF_d
0x14001d4ed  mov     edx, 83h
0x14001d4f2  mov     r9b, 1
0x14001d4f5  mov     r8d, edx
0x14001d4f8  mov     rcx, rbx
0x14001d4fb  call    RejectSession
0x14001d500  lea     rcx, SpinLock; SpinLock
0x14001d507  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001d50e  nop     dword ptr [rax+rax+00h]
0x14001d513  mov     rcx, rsi
0x14001d516  mov     bl, al
0x14001d518  call    RelistConnection
0x14001d51d  mov     dl, bl; NewIrql
0x14001d51f  lea     rcx, SpinLock; SpinLock
0x14001d526  call    cs:__imp_KeReleaseSpinLock
0x14001d52d  nop     dword ptr [rax+rax+00h]
0x14001d532  lea     rdx, [rsp+38h+arg_18]
0x14001d537  mov     rcx, rsi
0x14001d53a  call    GetIrpIfNotCancelled
0x14001d53f  mov     rcx, [rsp+38h+arg_18]
0x14001d544  test    rcx, rcx
0x14001d547  jz      loc_14001D4A4
0x14001d54d  mov     edx, 0C0000001h
0x14001d552  jmp     loc_14001D49C
0x14001d557  mov     edx, 1Ah
0x14001d55c  mov     [rsp+38h+var_18], rbx
0x14001d561  mov     ecx, 415h
0x14001d566  lea     r8, WPP_ffc711f4ba0833be1e89b8c0ea368d15_Traceguids
0x14001d56d  mov     r9, rsi
0x14001d570  call    WPP_SF_qq
0x14001d575  jmp     loc_14001D497
```
