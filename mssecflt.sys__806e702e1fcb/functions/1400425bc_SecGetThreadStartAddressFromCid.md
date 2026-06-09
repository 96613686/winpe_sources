# SecGetThreadStartAddressFromCid

- ea: `0x1400425bc`
- end: `0x14004266b`
- name: `SecGetThreadStartAddressFromCid`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002ec70`
- `0x140040f3c`

## callees

- `0x140011650`
- `0x140042558`
- `0x1400425bc`

## import_xrefs

- `ntoskrnl!ZwOpenThread` at `0x14004261b`
- `ntoskrnl!ZwOpenThread` at `0x14004261b`
- `ntoskrnl!ZwClose` at `0x140042642`
- `ntoskrnl!ZwClose` at `0x140042642`

## pseudocode

```c
NTSTATUS __fastcall SecGetThreadStartAddressFromCid(void *a1, void *a2, __int64 a3)
{
  NTSTATUS result; // eax
  int ThreadStartAddress; // ebx
  void *ThreadHandle; // [rsp+20h] [rbp-50h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+28h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF

  ClientId.UniqueProcess = a2;
  ClientId.UniqueThread = a1;
  ThreadHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenThread(&ThreadHandle, 0x40u, &ObjectAttributes, &ClientId);
  if ( result >= 0 )
  {
    ThreadStartAddress = SecGetThreadStartAddress(ThreadHandle, a3);
    ZwClose(ThreadHandle);
    return ThreadStartAddress;
  }
  else
  {
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x1400425bc  mov     [rsp-8+arg_18], rbx
0x1400425c1  push    rbp
0x1400425c2  mov     rbp, rsp
0x1400425c5  sub     rsp, 70h
0x1400425c9  mov     rax, cs:__security_cookie
0x1400425d0  xor     rax, rsp
0x1400425d3  mov     [rbp+var_8], rax
0x1400425d7  xor     eax, eax
0x1400425d9  mov     [rbp+ClientId.UniqueProcess], rdx
0x1400425dd  mov     rbx, r8
0x1400425e0  mov     [rbp+ClientId.UniqueThread], rcx
0x1400425e4  xorps   xmm0, xmm0
0x1400425e7  mov     [rbp+ThreadHandle], 0
0x1400425ef  lea     r9, [rbp+ClientId]; ClientId
0x1400425f3  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400425fb  lea     edx, [rax+40h]; DesiredAccess
0x1400425fe  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x140042606  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14004260a  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14004260e  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x140042612  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140042616  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14004261b  call    cs:__imp_ZwOpenThread
0x140042622  nop     dword ptr [rax+rax+00h]
0x140042627  test    eax, eax
0x140042629  jns     short loc_140042630
0x14004262b  lfence
0x14004262e  jmp     short loc_140042650
0x140042630  mov     rcx, [rbp+ThreadHandle]
0x140042634  mov     rdx, rbx
0x140042637  call    SecGetThreadStartAddress
0x14004263c  mov     rcx, [rbp+ThreadHandle]; Handle
0x140042640  mov     ebx, eax
0x140042642  call    cs:__imp_ZwClose
0x140042649  nop     dword ptr [rax+rax+00h]
0x14004264e  mov     eax, ebx
0x140042650  mov     rcx, [rbp+var_8]
0x140042654  xor     rcx, rsp; StackCookie
0x140042657  call    __security_check_cookie
0x14004265c  mov     rbx, [rsp+70h+arg_18]
0x140042664  add     rsp, 70h
0x140042668  pop     rbp
0x140042669  retn
```
