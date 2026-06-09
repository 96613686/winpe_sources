# BasepCreateBnoIsolationSymbolicLinks

- ea: `0x18017d848`
- end: `0x18017dc37`
- name: `BasepCreateBnoIsolationSymbolicLinks`
- size: `1007`
- prototype: `__int64 __usercall@<rax>(HANDLE Handle@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18017d680`

## callees

- `0x18006fd7c`
- `0x18017d848`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18017d9fb`
- `ntdll!RtlInitUnicodeString` at `0x18017da8e`
- `ntdll!RtlInitUnicodeString` at `0x18017db1b`
- `ntdll!RtlInitUnicodeString` at `0x18017d9fb`
- `ntdll!RtlInitUnicodeString` at `0x18017da8e`
- `ntdll!RtlInitUnicodeString` at `0x18017db1b`
- `ntdll!NtClose` at `0x18017dbdc`
- `ntdll!NtClose` at `0x18017dbec`
- `ntdll!NtClose` at `0x18017dbfc`
- `ntdll!NtClose` at `0x18017dc0c`
- `ntdll!NtClose` at `0x18017dbdc`
- `ntdll!NtClose` at `0x18017dbec`
- `ntdll!NtClose` at `0x18017dbfc`
- `ntdll!NtClose` at `0x18017dc0c`
- `ntdll!RtlFreeHeap` at `0x18017dbcc`
- `ntdll!RtlFreeHeap` at `0x18017dbcc`
- `ntdll!NtQueryObject` at `0x18017d8f8`
- `ntdll!NtQueryObject` at `0x18017d955`
- `ntdll!NtQueryObject` at `0x18017d8f8`
- `ntdll!NtQueryObject` at `0x18017d955`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18017d9b1`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18017da41`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18017dace`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18017db5b`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18017d9b1`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18017da41`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18017dace`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18017db5b`
- `ntdll!RtlAllocateHeap` at `0x18017d923`
- `ntdll!RtlAllocateHeap` at `0x18017d923`

## pseudocode

```c
__int64 __fastcall BasepCreateBnoIsolationSymbolicLinks(
        HANDLE Handle,
        void *a2,
        __int64 a3,
        HANDLE *a4,
        HANDLE *a5,
        HANDLE *a6,
        HANDLE *a7)
{
  PVOID Heap; // rdi
  NTSTATUS v12; // eax
  NTSTATUS v13; // ebx
  _BYTE *v14; // rsi
  HANDLE *v15; // rcx
  ULONG ObjectInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handlea; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE SymbolicLinkHandle; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v20; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v21; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  HANDLE *v24; // [rsp+98h] [rbp-68h]
  HANDLE *v25; // [rsp+A0h] [rbp-60h]
  WCHAR SourceString[392]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE ObjectInformation[528]; // [rsp+3C0h] [rbp+2C0h] BYREF

  Heap = 0;
  *a4 = 0;
  v24 = a6;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  v25 = a7;
  ObjectInformationLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Handlea = 0;
  SymbolicLinkHandle = 0;
  v20 = 0;
  DestinationString = 0;
  v21 = 0;
  v12 = NtQueryObject(Handle, ObjectNameInformation, ObjectInformation, 0x210u, &ObjectInformationLength);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = ObjectInformation;
  }
  else
  {
    if ( v12 != -1073741820 )
      goto LABEL_18;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ObjectInformationLength);
    if ( !Heap )
    {
      v13 = -1073741801;
      goto LABEL_18;
    }
    v13 = NtQueryObject(Handle, ObjectNameInformation, Heap, ObjectInformationLength, &ObjectInformationLength);
    if ( v13 < 0 )
      goto LABEL_17;
    v14 = Heap;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_180276DA0;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.Attributes = 130;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = NtCreateSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes, (PUNICODE_STRING)&stru_180276DB0);
  if ( v13 >= 0 )
  {
    SourceString[0] = 0;
    v13 = RtlStringCchPrintfW(SourceString, 392, L"%ws\\%ws", *((_QWORD *)v14 + 1), *(_QWORD *)(a3 + 8));
    if ( v13 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      ObjectAttributes.RootDirectory = a2;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_180276DC0;
      ObjectAttributes.Attributes = 130;
      ObjectAttributes.Length = 48;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v13 = NtCreateSymbolicLinkObject(&Handlea, 0xF0001u, &ObjectAttributes, &DestinationString);
      if ( v13 >= 0 )
      {
        SourceString[0] = 0;
        v13 = RtlStringCchPrintfW(SourceString, 392, L"%ws\\%ws", *((_QWORD *)v14 + 1), L"Session");
        if ( v13 >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, SourceString);
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_180276DD0;
          ObjectAttributes.RootDirectory = a2;
          ObjectAttributes.Attributes = 130;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v13 = NtCreateSymbolicLinkObject(&v20, 0xF0001u, &ObjectAttributes, &DestinationString);
          if ( v13 >= 0 )
          {
            SourceString[0] = 0;
            v13 = RtlStringCchPrintfW(SourceString, 392, L"%ws\\%ws", *((_QWORD *)v14 + 1), L"AppContainerNamedObjects");
            if ( v13 >= 0 )
            {
              RtlInitUnicodeString(&DestinationString, SourceString);
              ObjectAttributes.Length = 48;
              ObjectAttributes.ObjectName = (PUNICODE_STRING)L"02";
              ObjectAttributes.RootDirectory = a2;
              ObjectAttributes.Attributes = 130;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              v13 = NtCreateSymbolicLinkObject(&v21, 0xF0001u, &ObjectAttributes, &DestinationString);
              if ( v13 >= 0 )
              {
                v15 = v24;
                *a4 = Handlea;
                *a5 = SymbolicLinkHandle;
                *v15 = v20;
                Handlea = 0;
                SymbolicLinkHandle = 0;
                v20 = 0;
                *v25 = v21;
                v21 = 0;
              }
            }
          }
        }
      }
    }
  }
  if ( Heap )
LABEL_17:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
LABEL_18:
  if ( Handlea )
    NtClose(Handlea);
  if ( SymbolicLinkHandle )
    NtClose(SymbolicLinkHandle);
  if ( v20 )
    NtClose(v20);
  if ( v21 )
    NtClose(v21);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18017d848  push    rbp
0x18017d84a  push    rbx
0x18017d84b  push    rsi
0x18017d84c  push    rdi
0x18017d84d  push    r12
0x18017d84f  push    r13
0x18017d851  push    r14
0x18017d853  push    r15
0x18017d855  lea     rbp, [rsp-4E8h]
0x18017d85d  sub     rsp, 5E8h
0x18017d864  mov     rax, cs:__security_cookie
0x18017d86b  xor     rax, rsp
0x18017d86e  mov     [rbp+520h+var_50], rax
0x18017d875  mov     rax, [rbp+520h+arg_28]
0x18017d87c  xor     edi, edi
0x18017d87e  mov     r13, [rbp+520h+arg_20]
0x18017d885  xorps   xmm0, xmm0
0x18017d888  mov     [r9], rdi
0x18017d88b  mov     rsi, rcx
0x18017d88e  mov     rcx, [rbp+520h+arg_30]
0x18017d895  mov     r12, r9
0x18017d898  mov     [rbp+520h+var_588], rax
0x18017d89c  mov     r15, r8
0x18017d89f  mov     [r13+0], rdi
0x18017d8a3  lea     r8, [rbp+520h+ObjectInformation]; ObjectInformation
0x18017d8aa  mov     [rax], rdi
0x18017d8ad  mov     r14, rdx
0x18017d8b0  mov     [rcx], rdi
0x18017d8b3  lea     rax, [rsp+620h+ObjectInformationLength]
0x18017d8b8  mov     [rbp+520h+var_580], rcx
0x18017d8bc  lea     edx, [rdi+1]; ObjectInformationClass
0x18017d8bf  mov     rcx, rsi; Handle
0x18017d8c2  mov     [rsp+620h+ReturnLength], rax; ReturnLength
0x18017d8c7  mov     r9d, 210h; ObjectInformationLength
0x18017d8cd  mov     [rsp+620h+ObjectInformationLength], edi
0x18017d8d1  movups  xmmword ptr [rsp+620h+ObjectAttributes.Length], xmm0
0x18017d8d6  mov     [rsp+620h+Handle], rdi
0x18017d8db  movups  xmmword ptr [rsp+620h+ObjectAttributes.ObjectName], xmm0
0x18017d8e0  mov     [rsp+620h+SymbolicLinkHandle], rdi
0x18017d8e5  movups  xmmword ptr [rsp+620h+ObjectAttributes.SecurityDescriptor], xmm0
0x18017d8ea  mov     [rsp+620h+var_5D8], rdi
0x18017d8ef  movups  xmmword ptr [rbp+520h+DestinationString.Length], xmm0
0x18017d8f3  mov     [rsp+620h+var_5D0], rdi
0x18017d8f8  call    cs:__imp_NtQueryObject
0x18017d8fe  mov     ebx, eax
0x18017d900  test    eax, eax
0x18017d902  jns     short loc_18017D96A
0x18017d904  cmp     eax, 0C0000004h
0x18017d909  jnz     loc_18017DBD2
0x18017d90f  mov     rcx, gs:60h
0x18017d918  xor     edx, edx; Flags
0x18017d91a  mov     r8d, [rsp+620h+ObjectInformationLength]; Size
0x18017d91f  mov     rcx, [rcx+30h]; HeapHandle
0x18017d923  call    cs:__imp_RtlAllocateHeap
0x18017d929  mov     rdi, rax
0x18017d92c  test    rax, rax
0x18017d92f  jnz     short loc_18017D93B
0x18017d931  mov     ebx, 0C0000017h
0x18017d936  jmp     loc_18017DBD2
0x18017d93b  mov     r9d, [rsp+620h+ObjectInformationLength]; ObjectInformationLength
0x18017d940  lea     rax, [rsp+620h+ObjectInformationLength]
0x18017d945  mov     r8, rdi; ObjectInformation
0x18017d948  mov     [rsp+620h+ReturnLength], rax; ReturnLength
0x18017d94d  mov     edx, 1; ObjectInformationClass
0x18017d952  mov     rcx, rsi; Handle
0x18017d955  call    cs:__imp_NtQueryObject
0x18017d95b  mov     ebx, eax
0x18017d95d  test    eax, eax
0x18017d95f  js      loc_18017DBBA
0x18017d965  mov     rsi, rdi
0x18017d968  jmp     short loc_18017D971
0x18017d96a  lea     rsi, [rbp+520h+ObjectInformation]
0x18017d971  lea     rax, qword_180276DA0
0x18017d978  mov     [rsp+620h+ObjectAttributes.Length], 30h ; '0'
0x18017d980  xorps   xmm0, xmm0
0x18017d983  mov     [rsp+620h+ObjectAttributes.ObjectName], rax
0x18017d988  lea     r9, stru_180276DB0; Name
0x18017d98f  mov     [rsp+620h+ObjectAttributes.RootDirectory], r14
0x18017d994  lea     r8, [rsp+620h+ObjectAttributes]; ObjectAttributes
0x18017d999  mov     [rsp+620h+ObjectAttributes.Attributes], 82h
0x18017d9a1  mov     edx, 0F0001h; DesiredAccess
0x18017d9a6  lea     rcx, [rsp+620h+SymbolicLinkHandle]; SymbolicLinkHandle
0x18017d9ab  movdqu  xmmword ptr [rsp+620h+ObjectAttributes.SecurityDescriptor], xmm0
0x18017d9b1  call    cs:__imp_NtCreateSymbolicLinkObject
0x18017d9b7  mov     ebx, eax
0x18017d9b9  test    eax, eax
0x18017d9bb  js      loc_18017DBB5
0x18017d9c1  xor     eax, eax
0x18017d9c3  lea     r8, aWsWs; "%ws\\%ws"
0x18017d9ca  mov     [rbp+520h+SourceString], ax
0x18017d9ce  lea     rcx, [rbp+520h+SourceString]
0x18017d9d2  mov     rax, [r15+8]
0x18017d9d6  mov     edx, 188h
0x18017d9db  mov     r9, [rsi+8]
0x18017d9df  mov     [rsp+620h+ReturnLength], rax
0x18017d9e4  call    RtlStringCchPrintfW
0x18017d9e9  mov     ebx, eax
0x18017d9eb  test    eax, eax
0x18017d9ed  js      loc_18017DBB5
0x18017d9f3  lea     rdx, [rbp+520h+SourceString]; SourceString
0x18017d9f7  lea     rcx, [rbp+520h+DestinationString]; DestinationString
0x18017d9fb  call    cs:__imp_RtlInitUnicodeString
0x18017da01  lea     rax, qword_180276DC0
0x18017da08  mov     [rsp+620h+ObjectAttributes.RootDirectory], r14
0x18017da0d  xorps   xmm0, xmm0
0x18017da10  mov     [rsp+620h+ObjectAttributes.ObjectName], rax
0x18017da15  mov     r15d, 30h ; '0'
0x18017da1b  mov     [rsp+620h+ObjectAttributes.Attributes], 82h
0x18017da23  lea     r9, [rbp+520h+DestinationString]; Name
0x18017da27  mov     [rsp+620h+ObjectAttributes.Length], r15d
0x18017da2c  lea     r8, [rsp+620h+ObjectAttributes]; ObjectAttributes
0x18017da31  mov     edx, 0F0001h; DesiredAccess
0x18017da36  lea     rcx, [rsp+620h+Handle]; SymbolicLinkHandle
0x18017da3b  movdqu  xmmword ptr [rsp+620h+ObjectAttributes.SecurityDescriptor], xmm0
0x18017da41  call    cs:__imp_NtCreateSymbolicLinkObject
0x18017da47  mov     ebx, eax
0x18017da49  test    eax, eax
0x18017da4b  js      loc_18017DBB5
0x18017da51  xor     eax, eax
0x18017da53  lea     r8, aWsWs; "%ws\\%ws"
0x18017da5a  mov     [rbp+520h+SourceString], ax
0x18017da5e  lea     rcx, [rbp+520h+SourceString]
0x18017da62  mov     r9, [rsi+8]
0x18017da66  lea     rax, aSession; "Session"
0x18017da6d  mov     edx, 188h
0x18017da72  mov     [rsp+620h+ReturnLength], rax
0x18017da77  call    RtlStringCchPrintfW
0x18017da7c  mov     ebx, eax
0x18017da7e  test    eax, eax
0x18017da80  js      loc_18017DBB5
0x18017da86  lea     rdx, [rbp+520h+SourceString]; SourceString
0x18017da8a  lea     rcx, [rbp+520h+DestinationString]; DestinationString
0x18017da8e  call    cs:__imp_RtlInitUnicodeString
0x18017da94  lea     rax, qword_180276DD0
0x18017da9b  mov     [rsp+620h+ObjectAttributes.Length], r15d
0x18017daa0  xorps   xmm0, xmm0
0x18017daa3  mov     [rsp+620h+ObjectAttributes.ObjectName], rax
0x18017daa8  lea     r9, [rbp+520h+DestinationString]; Name
0x18017daac  mov     [rsp+620h+ObjectAttributes.RootDirectory], r14
0x18017dab1  lea     r8, [rsp+620h+ObjectAttributes]; ObjectAttributes
0x18017dab6  mov     [rsp+620h+ObjectAttributes.Attributes], 82h
0x18017dabe  mov     edx, 0F0001h; DesiredAccess
0x18017dac3  lea     rcx, [rsp+620h+var_5D8]; SymbolicLinkHandle
0x18017dac8  movdqu  xmmword ptr [rsp+620h+ObjectAttributes.SecurityDescriptor], xmm0
0x18017dace  call    cs:__imp_NtCreateSymbolicLinkObject
0x18017dad4  mov     ebx, eax
0x18017dad6  test    eax, eax
0x18017dad8  js      loc_18017DBB5
0x18017dade  xor     eax, eax
0x18017dae0  lea     r8, aWsWs; "%ws\\%ws"
0x18017dae7  mov     [rbp+520h+SourceString], ax
0x18017daeb  lea     rcx, [rbp+520h+SourceString]
0x18017daef  mov     r9, [rsi+8]
0x18017daf3  lea     rax, aAppcontainerna; "AppContainerNamedObjects"
0x18017dafa  mov     edx, 188h
0x18017daff  mov     [rsp+620h+ReturnLength], rax
0x18017db04  call    RtlStringCchPrintfW
0x18017db09  mov     ebx, eax
0x18017db0b  test    eax, eax
0x18017db0d  js      loc_18017DBB5
0x18017db13  lea     rdx, [rbp+520h+SourceString]; SourceString
0x18017db17  lea     rcx, [rbp+520h+DestinationString]; DestinationString
0x18017db1b  call    cs:__imp_RtlInitUnicodeString
0x18017db21  lea     rax, a02; "02"
0x18017db28  mov     [rsp+620h+ObjectAttributes.Length], r15d
0x18017db2d  xorps   xmm0, xmm0
0x18017db30  mov     [rsp+620h+ObjectAttributes.ObjectName], rax
0x18017db35  lea     r9, [rbp+520h+DestinationString]; Name
0x18017db39  mov     [rsp+620h+ObjectAttributes.RootDirectory], r14
0x18017db3e  lea     r8, [rsp+620h+ObjectAttributes]; ObjectAttributes
0x18017db43  mov     [rsp+620h+ObjectAttributes.Attributes], 82h
0x18017db4b  mov     edx, 0F0001h; DesiredAccess
0x18017db50  lea     rcx, [rsp+620h+var_5D0]; SymbolicLinkHandle
0x18017db55  movdqu  xmmword ptr [rsp+620h+ObjectAttributes.SecurityDescriptor], xmm0
0x18017db5b  call    cs:__imp_NtCreateSymbolicLinkObject
0x18017db61  mov     ebx, eax
0x18017db63  test    eax, eax
0x18017db65  js      short loc_18017DBB5
0x18017db67  mov     rax, [rsp+620h+Handle]
0x18017db6c  mov     rcx, [rbp+520h+var_588]
0x18017db70  mov     [r12], rax
0x18017db74  mov     rax, [rsp+620h+SymbolicLinkHandle]
0x18017db79  mov     [r13+0], rax
0x18017db7d  mov     rax, [rsp+620h+var_5D8]
0x18017db82  mov     [rcx], rax
0x18017db85  mov     rax, [rsp+620h+var_5D0]
0x18017db8a  mov     rcx, [rbp+520h+var_580]
0x18017db8e  mov     [rsp+620h+Handle], 0
0x18017db97  mov     [rsp+620h+SymbolicLinkHandle], 0
0x18017dba0  mov     [rsp+620h+var_5D8], 0
0x18017dba9  mov     [rcx], rax
0x18017dbac  mov     [rsp+620h+var_5D0], 0
0x18017dbb5  test    rdi, rdi
0x18017dbb8  jz      short loc_18017DBD2
0x18017dbba  mov     rcx, gs:60h
0x18017dbc3  mov     r8, rdi; P
0x18017dbc6  xor     edx, edx; Flags
0x18017dbc8  mov     rcx, [rcx+30h]; HeapHandle
0x18017dbcc  call    cs:__imp_RtlFreeHeap
0x18017dbd2  mov     rcx, [rsp+620h+Handle]; Handle
0x18017dbd7  test    rcx, rcx
0x18017dbda  jz      short loc_18017DBE2
0x18017dbdc  call    cs:__imp_NtClose
0x18017dbe2  mov     rcx, [rsp+620h+SymbolicLinkHandle]; Handle
0x18017dbe7  test    rcx, rcx
0x18017dbea  jz      short loc_18017DBF2
0x18017dbec  call    cs:__imp_NtClose
0x18017dbf2  mov     rcx, [rsp+620h+var_5D8]; Handle
0x18017dbf7  test    rcx, rcx
0x18017dbfa  jz      short loc_18017DC02
0x18017dbfc  call    cs:__imp_NtClose
0x18017dc02  mov     rcx, [rsp+620h+var_5D0]; Handle
0x18017dc07  test    rcx, rcx
0x18017dc0a  jz      short loc_18017DC12
0x18017dc0c  call    cs:__imp_NtClose
0x18017dc12  mov     eax, ebx
0x18017dc14  mov     rcx, [rbp+520h+var_50]
0x18017dc1b  xor     rcx, rsp; StackCookie
0x18017dc1e  call    __security_check_cookie
0x18017dc23  add     rsp, 5E8h
0x18017dc2a  pop     r15
0x18017dc2c  pop     r14
0x18017dc2e  pop     r13
0x18017dc30  pop     r12
0x18017dc32  pop     rdi
0x18017dc33  pop     rsi
0x18017dc34  pop     rbx
0x18017dc35  pop     rbp
0x18017dc36  retn
```
