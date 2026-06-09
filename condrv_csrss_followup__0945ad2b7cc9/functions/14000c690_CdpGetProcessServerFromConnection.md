# CdpGetProcessServerFromConnection

- ea: `0x14000c690`
- end: `0x14000c86a`
- name: `CdpGetProcessServerFromConnection`
- size: `474`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400083b0`
- `0x14000e440`

## callees

- `0x14000ac50`
- `0x14000bb50`
- `0x14000c690`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000c7cc`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c80e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c844`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c7cc`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c80e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c844`
- `ntoskrnl!PsIsSystemProcess` at `0x14000c7fb`
- `ntoskrnl!PsIsSystemProcess` at `0x14000c7fb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000c76a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000c76a`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14000c6f6`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14000c6f6`
- `ntoskrnl!ZwOpenProcess` at `0x14000c735`
- `ntoskrnl!ZwOpenProcess` at `0x14000c735`
- `ntoskrnl!ZwClose` at `0x14000c77c`
- `ntoskrnl!ZwClose` at `0x14000c77c`
- `ntoskrnl!PsGetProcessSessionId` at `0x14000c793`
- `ntoskrnl!PsGetProcessSessionId` at `0x14000c7a4`
- `ntoskrnl!PsGetProcessSessionId` at `0x14000c793`
- `ntoskrnl!PsGetProcessSessionId` at `0x14000c7a4`

## pseudocode

```c
NTSTATUS __fastcall CdpGetProcessServerFromConnection(_QWORD *a1, __int64 a2, void *a3)
{
  __int64 RequestorProcess; // rax
  __int64 v7; // rdi
  NTSTATUS result; // eax
  NTSTATUS ProcessConnection; // ebx
  PVOID v10; // rsi
  int ProcessSessionId; // ebx
  __int64 v12; // rcx
  PVOID Object; // [rsp+30h] [rbp-39h] BYREF
  __int64 v14; // [rsp+38h] [rbp-31h] BYREF
  PVOID v15; // [rsp+40h] [rbp-29h] BYREF
  _CLIENT_ID ClientId; // [rsp+48h] [rbp-21h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-11h] BYREF
  void *ProcessHandle; // [rsp+E8h] [rbp+7Fh] BYREF

  v14 = 0;
  v15 = 0;
  ProcessHandle = 0;
  ClientId = 0;
  memset(&ObjectAttributes, 0, 44);
  RequestorProcess = CdpGetRequestorProcess(a2);
  v7 = RequestorProcess;
  if ( !RequestorProcess )
    return -1073741813;
  ClientId.UniqueThread = 0;
  if ( a3 == (void *)-1LL )
    ClientId.UniqueProcess = (HANDLE)PsGetProcessInheritedFromUniqueProcessId(RequestorProcess);
  else
    ClientId.UniqueProcess = a3;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 1536;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenProcess(&ProcessHandle, 0x1000u, &ObjectAttributes, &ClientId);
  if ( result >= 0 )
  {
    Object = 0;
    ProcessConnection = ObReferenceObjectByHandle(ProcessHandle, 0x1000u, 0, 0, &Object, 0);
    ZwClose(ProcessHandle);
    if ( ProcessConnection < 0 )
      return ProcessConnection;
    v10 = Object;
    ProcessSessionId = PsGetProcessSessionId(v7);
    if ( (unsigned int)PsGetProcessSessionId(v10) != ProcessSessionId && !(unsigned __int8)PsIsSystemProcess(v7) )
    {
      ObfDereferenceObject(v10);
      return -1073741790;
    }
    ProcessConnection = CdGetProcessConnection(&v15, &v14, a2, v10);
    ObfDereferenceObject(v10);
    if ( ProcessConnection >= 0 )
    {
      v12 = *(_QWORD *)(v14 + 24);
      *a1 = v12;
      _InterlockedIncrement64((volatile signed __int64 *)(v12 + 24));
      ObfDereferenceObject(v15);
      return 0;
    }
    else
    {
      return ProcessConnection;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c690  push    rbp
0x14000c692  push    rbx
0x14000c693  push    rsi
0x14000c694  push    rdi
0x14000c695  push    r14
0x14000c697  push    r15
0x14000c699  lea     rbp, [rsp-2Fh]
0x14000c69e  sub     rsp, 98h
0x14000c6a5  xorps   xmm0, xmm0
0x14000c6a8  xor     esi, esi
0x14000c6aa  mov     r15, rcx
0x14000c6ad  mov     [rbp+57h+var_88], rsi
0x14000c6b1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000c6b5  xor     eax, eax
0x14000c6b7  mov     [rbp+57h+var_80], rsi
0x14000c6bb  mov     rcx, rdx
0x14000c6be  mov     [rbp+57h+ProcessHandle], rsi
0x14000c6c2  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000c6c6  mov     rbx, r8
0x14000c6c9  mov     r14, rdx
0x14000c6cc  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x14000c6d0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000c6d4  call    CdpGetRequestorProcess
0x14000c6d9  mov     rdi, rax
0x14000c6dc  test    rax, rax
0x14000c6df  jz      loc_14000C854
0x14000c6e5  mov     [rbp+57h+ClientId.UniqueThread], rsi
0x14000c6e9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000c6ed  jnz     loc_14000C7EF
0x14000c6f3  mov     rcx, rax
0x14000c6f6  call    cs:__imp_PsGetProcessInheritedFromUniqueProcessId
0x14000c6fd  nop     dword ptr [rax+rax+00h]
0x14000c702  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x14000c706  xorps   xmm0, xmm0
0x14000c709  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000c710  lea     r9, [rbp+57h+ClientId]; ClientId
0x14000c714  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14000c718  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000c71c  mov     [rbp+57h+ObjectAttributes.Attributes], 600h
0x14000c723  mov     edx, 1000h; DesiredAccess
0x14000c728  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x14000c72c  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x14000c730  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000c735  call    cs:__imp_ZwOpenProcess
0x14000c73c  nop     dword ptr [rax+rax+00h]
0x14000c741  test    eax, eax
0x14000c743  js      loc_14000C7DE
0x14000c749  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x14000c74d  lea     rax, [rbp+57h+var_90]
0x14000c751  mov     [rsp+0C0h+HandleInformation], rsi; HandleInformation
0x14000c756  xor     r9d, r9d; AccessMode
0x14000c759  xor     r8d, r8d; ObjectType
0x14000c75c  mov     [rsp+0C0h+Object], rax; Object
0x14000c761  mov     edx, 1000h; DesiredAccess
0x14000c766  mov     [rbp+57h+var_90], rsi
0x14000c76a  call    cs:__imp_ObReferenceObjectByHandle
0x14000c771  nop     dword ptr [rax+rax+00h]
0x14000c776  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x14000c77a  mov     ebx, eax
0x14000c77c  call    cs:__imp_ZwClose
0x14000c783  nop     dword ptr [rax+rax+00h]
0x14000c788  test    ebx, ebx
0x14000c78a  js      short loc_14000C7DC
0x14000c78c  mov     rsi, [rbp+57h+var_90]
0x14000c790  mov     rcx, rdi
0x14000c793  call    cs:__imp_PsGetProcessSessionId
0x14000c79a  nop     dword ptr [rax+rax+00h]
0x14000c79f  mov     rcx, rsi
0x14000c7a2  mov     ebx, eax
0x14000c7a4  call    cs:__imp_PsGetProcessSessionId
0x14000c7ab  nop     dword ptr [rax+rax+00h]
0x14000c7b0  cmp     eax, ebx
0x14000c7b2  jnz     short loc_14000C7F8
0x14000c7b4  mov     r9, rsi
0x14000c7b7  lea     rdx, [rbp+57h+var_88]
0x14000c7bb  mov     r8, r14
0x14000c7be  lea     rcx, [rbp+57h+var_80]
0x14000c7c2  call    CdGetProcessConnection
0x14000c7c7  mov     rcx, rsi; Object
0x14000c7ca  mov     ebx, eax
0x14000c7cc  call    cs:__imp_ObfDereferenceObject
0x14000c7d3  nop     dword ptr [rax+rax+00h]
0x14000c7d8  test    ebx, ebx
0x14000c7da  jns     short loc_14000C830
0x14000c7dc  mov     eax, ebx
0x14000c7de  add     rsp, 98h
0x14000c7e5  pop     r15
0x14000c7e7  pop     r14
0x14000c7e9  pop     rdi
0x14000c7ea  pop     rsi
0x14000c7eb  pop     rbx
0x14000c7ec  pop     rbp
0x14000c7ed  retn
0x14000c7ef  mov     [rbp+57h+ClientId.UniqueProcess], rbx
0x14000c7f3  jmp     loc_14000C706
0x14000c7f8  mov     rcx, rdi
0x14000c7fb  call    cs:__imp_PsIsSystemProcess
0x14000c802  nop     dword ptr [rax+rax+00h]
0x14000c807  test    al, al
0x14000c809  jnz     short loc_14000C7B4
0x14000c80b  mov     rcx, rsi; Object
0x14000c80e  call    cs:__imp_ObfDereferenceObject
0x14000c815  nop     dword ptr [rax+rax+00h]
0x14000c81a  mov     eax, 0C0000022h
0x14000c81f  add     rsp, 98h
0x14000c826  pop     r15
0x14000c828  pop     r14
0x14000c82a  pop     rdi
0x14000c82b  pop     rsi
0x14000c82c  pop     rbx
0x14000c82d  pop     rbp
0x14000c82e  retn
0x14000c830  mov     rax, [rbp+57h+var_88]
0x14000c834  mov     rcx, [rax+18h]
0x14000c838  mov     [r15], rcx
0x14000c83b  lock inc qword ptr [rcx+18h]
0x14000c840  mov     rcx, [rbp+57h+var_80]; Object
0x14000c844  call    cs:__imp_ObfDereferenceObject
0x14000c84b  nop     dword ptr [rax+rax+00h]
0x14000c850  xor     eax, eax
0x14000c852  jmp     short loc_14000C7DE
0x14000c854  mov     eax, 0C000000Bh
0x14000c859  add     rsp, 98h
0x14000c860  pop     r15
0x14000c862  pop     r14
0x14000c864  pop     rdi
0x14000c865  pop     rsi
0x14000c866  pop     rbx
0x14000c867  pop     rbp
0x14000c868  retn
```
