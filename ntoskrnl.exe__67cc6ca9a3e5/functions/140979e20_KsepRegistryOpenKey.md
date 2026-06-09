# KsepRegistryOpenKey

- ea: `0x140979e20`
- end: `0x140979f06`
- name: `KsepRegistryOpenKey`
- size: `230`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14077c054`
- `0x140c6f164`
- `0x140ca6c24`

## callees

- `0x1404adb80`
- `0x140613770`
- `0x1406daad0`
- `0x140979e20`
- `0x140979f0c`
- `0x14097a928`

## string_xrefs

- `0x140b60cae`: `EnginePath != NULL`
- `0x140b60ca7`: `minkernel\ntos\kshim\kseregistry.c`
- `0x140b60cfb`: `minkernel\ntos\kshim\kseregistry.c`

## pseudocode

```c
__int64 __fastcall KsepRegistryOpenKey(__int64 a1, __int64 a2, HANDLE *a3)
{
  int v6; // eax
  NTSTATUS v7; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+28h] [rbp-40h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+A0h] [rbp+38h] BYREF

  v11 = 0;
  v12 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !a1 )
  {
    v9 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u) + 1)
       & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v9) = -1073740768;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v9) = 262564;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("EnginePath != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x1A4u, 0);
  }
  if ( !a3 )
  {
    v10 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u)
         + 1)
        & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v10) = -1073740768;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v10) = 262565;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("Handle != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x1A5u, 0);
  }
  if ( a2 )
    v6 = KsepStringConcatenate(&v11, a1, a2, 1);
  else
    v6 = KsepStringDuplicate(&v11, a1);
  v7 = v6;
  if ( v6 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v11;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v7 >= 0 )
    {
      *a3 = KeyHandle;
      _InterlockedIncrement((volatile signed __int32 *)&AlpcpMessageLogLock.WaitBlockList);
    }
  }
  if ( v12 )
    KsepPoolFreePaged(v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140979e20  push    rbp
0x140979e22  push    rbx
0x140979e23  push    rsi
0x140979e24  push    rdi
0x140979e25  push    r12
0x140979e27  push    r13
0x140979e29  mov     rbp, rsp
0x140979e2c  sub     rsp, 68h
0x140979e30  xor     eax, eax
0x140979e32  lea     r12, AlpcpMessageLogLock.Timer.Processor
0x140979e39  mov     [rbp+var_48], rax
0x140979e3d  xorps   xmm0, xmm0
0x140979e40  mov     [rbp+var_40], rax
0x140979e44  mov     rsi, r8
0x140979e47  mov     [rbp+KeyHandle], rax
0x140979e4b  mov     rdi, rdx
0x140979e4e  lea     r13d, [rax+4]
0x140979e52  mov     rbx, rcx
0x140979e55  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140979e59  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140979e5d  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140979e61  test    rcx, rcx
0x140979e64  jz      loc_140B60C6C
0x140979e6a  test    rsi, rsi
0x140979e6d  jz      loc_140B60CC0
0x140979e73  lea     rcx, [rbp+var_48]
0x140979e77  mov     rdx, rbx
0x140979e7a  test    rdi, rdi
0x140979e7d  jz      short loc_140979EEF
0x140979e7f  mov     r9d, 1
0x140979e85  mov     r8, rdi
0x140979e88  call    KsepStringConcatenate
0x140979e8d  mov     ebx, eax
0x140979e8f  test    eax, eax
0x140979e91  js      short loc_140979ED1
0x140979e93  lea     rax, [rbp+var_48]
0x140979e97  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140979e9e  xorps   xmm0, xmm0
0x140979ea1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140979ea5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140979ea9  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140979eb1  mov     edx, 20019h; DesiredAccess
0x140979eb6  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140979ebd  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140979ec1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140979ec6  call    ZwOpenKey
0x140979ecb  mov     ebx, eax
0x140979ecd  test    eax, eax
0x140979ecf  jns     short loc_140979EF6
0x140979ed1  mov     rcx, [rbp+var_40]
0x140979ed5  test    rcx, rcx
0x140979ed8  jz      short loc_140979EDF
0x140979eda  call    KsepPoolFreePaged
0x140979edf  mov     eax, ebx
0x140979ee1  add     rsp, 68h
0x140979ee5  pop     r13
0x140979ee7  pop     r12
0x140979ee9  pop     rdi
0x140979eea  pop     rsi
0x140979eeb  pop     rbx
0x140979eec  pop     rbp
0x140979eed  retn
0x140979eef  call    KsepStringDuplicate
0x140979ef4  jmp     short loc_140979E8D
0x140979ef6  mov     rax, [rbp+KeyHandle]
0x140979efa  mov     [rsi], rax
0x140979efd  lock inc dword ptr cs:AlpcpMessageLogLock.WaitBlockList
0x140979f04  jmp     short loc_140979ED1
0x140b60c6c  mov     eax, 1
0x140b60c71  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x140b60c79  inc     eax
0x140b60c7b  mov     r8d, 1A4h; LineNumber
0x140b60c81  and     eax, 3Fh
0x140b60c84  mov     dword ptr [r12+rax*8+4], 0C0000420h
0x140b60c8d  mov     dword ptr [r12+rax*8], 401A4h
0x140b60c95  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x140b60c9b  test    r13b, al
0x140b60c9e  jz      loc_140979E6A
0x140b60ca4  xor     r9d, r9d; MutableMessage
0x140b60ca7  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140b60cae  lea     rcx, aEnginepathNull; "EnginePath != NULL"
0x140b60cb5  call    RtlAssert
0x140b60cba  nop
0x140b60cbb  jmp     loc_140979E6A
0x140b60cc0  mov     eax, 1
0x140b60cc5  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x140b60ccd  inc     eax
0x140b60ccf  mov     r8d, 1A5h; LineNumber
0x140b60cd5  and     eax, 3Fh
0x140b60cd8  mov     dword ptr [r12+rax*8+4], 0C0000420h
0x140b60ce1  mov     dword ptr [r12+rax*8], 401A5h
0x140b60ce9  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x140b60cef  test    r13b, al
0x140b60cf2  jz      loc_140979E73
0x140b60cf8  xor     r9d, r9d; MutableMessage
0x140b60cfb  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140b60d02  lea     rcx, aHandleNull; "Handle != NULL"
0x140b60d09  call    RtlAssert
0x140b60d0e  nop
0x140b60d0f  jmp     loc_140979E73
```
