# BasepCreateBnoIsolationSymbolicLinks

- ea: `0x180188e34`
- end: `0x18018927e`
- name: `BasepCreateBnoIsolationSymbolicLinks`
- size: `1098`
- prototype: `__int64 __usercall@<rax>(HANDLE Handle@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180188c40`

## callees

- `0x180074ac8`
- `0x180188e34`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180188fff`
- `ntdll!RtlInitUnicodeString` at `0x18018909e`
- `ntdll!RtlInitUnicodeString` at `0x180189137`
- `ntdll!RtlInitUnicodeString` at `0x180188fff`
- `ntdll!RtlInitUnicodeString` at `0x18018909e`
- `ntdll!RtlInitUnicodeString` at `0x180189137`
- `ntdll!NtClose` at `0x18018920a`
- `ntdll!NtClose` at `0x180189220`
- `ntdll!NtClose` at `0x180189236`
- `ntdll!NtClose` at `0x18018924c`
- `ntdll!NtClose` at `0x18018920a`
- `ntdll!NtClose` at `0x180189220`
- `ntdll!NtClose` at `0x180189236`
- `ntdll!NtClose` at `0x18018924c`
- `ntdll!RtlFreeHeap` at `0x1801891f4`
- `ntdll!RtlFreeHeap` at `0x1801891f4`
- `ntdll!NtQueryObject` at `0x180188ee4`
- `ntdll!NtQueryObject` at `0x180188f4d`
- `ntdll!NtQueryObject` at `0x180188ee4`
- `ntdll!NtQueryObject` at `0x180188f4d`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180188faf`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18018904b`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1801890e4`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18018917d`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180188faf`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18018904b`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1801890e4`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18018917d`
- `ntdll!RtlAllocateHeap` at `0x180188f15`
- `ntdll!RtlAllocateHeap` at `0x180188f15`

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
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_1802821C8;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.Attributes = 130;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = NtCreateSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes, (PUNICODE_STRING)&stru_1802821D8);
  if ( v13 >= 0 )
  {
    SourceString[0] = 0;
    v13 = RtlStringCchPrintfW(SourceString, 392, L"%ws\\%ws", *((_QWORD *)v14 + 1), *(_QWORD *)(a3 + 8));
    if ( v13 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      ObjectAttributes.RootDirectory = a2;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_1802821E8;
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
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_1802821F8;
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
0x180188e34  push    rbp
0x180188e36  push    rbx
0x180188e37  push    rsi
0x180188e38  push    rdi
0x180188e39  push    r12
0x180188e3b  push    r13
0x180188e3d  push    r14
0x180188e3f  push    r15
0x180188e41  lea     rbp, [rsp-4E8h]
0x180188e49  sub     rsp, 5E8h
0x180188e50  mov     rax, cs:__security_cookie
0x180188e57  xor     rax, rsp
0x180188e5a  mov     [rbp+520h+var_50], rax
0x180188e61  mov     rax, [rbp+520h+arg_28]
0x180188e68  xor     edi, edi
0x180188e6a  mov     r13, [rbp+520h+arg_20]
0x180188e71  xorps   xmm0, xmm0
0x180188e74  mov     [r9], rdi
0x180188e77  mov     rsi, rcx
0x180188e7a  mov     rcx, [rbp+520h+arg_30]
0x180188e81  mov     r12, r9
0x180188e84  mov     [rbp+520h+var_588], rax
0x180188e88  mov     r15, r8
0x180188e8b  mov     [r13+0], rdi
0x180188e8f  lea     r8, [rbp+520h+ObjectInformation]; ObjectInformation
0x180188e96  mov     [rax], rdi
0x180188e99  mov     r14, rdx
0x180188e9c  mov     [rcx], rdi
0x180188e9f  lea     rax, [rsp+620h+ObjectInformationLength]
0x180188ea4  mov     [rbp+520h+var_580], rcx
0x180188ea8  lea     edx, [rdi+1]; ObjectInformationClass
0x180188eab  mov     rcx, rsi; Handle
0x180188eae  mov     [rsp+620h+ReturnLength], rax; ReturnLength
0x180188eb3  mov     r9d, 210h; ObjectInformationLength
0x180188eb9  mov     [rsp+620h+ObjectInformationLength], edi
0x180188ebd  movups  xmmword ptr [rsp+620h+ObjectAttributes.Length], xmm0
0x180188ec2  mov     [rsp+620h+Handle], rdi
0x180188ec7  movups  xmmword ptr [rsp+620h+ObjectAttributes.ObjectName], xmm0
0x180188ecc  mov     [rsp+620h+SymbolicLinkHandle], rdi
0x180188ed1  movups  xmmword ptr [rsp+620h+ObjectAttributes.SecurityDescriptor], xmm0
0x180188ed6  mov     [rsp+620h+var_5D8], rdi
0x180188edb  movups  xmmword ptr [rbp+520h+DestinationString.Length], xmm0
0x180188edf  mov     [rsp+620h+var_5D0], rdi
0x180188ee4  call    cs:__imp_NtQueryObject
0x180188eeb  nop     dword ptr [rax+rax+00h]
0x180188ef0  mov     ebx, eax
0x180188ef2  test    eax, eax
0x180188ef4  jns     short loc_180188F68
0x180188ef6  cmp     eax, 0C0000004h
0x180188efb  jnz     loc_180189200
0x180188f01  mov     rcx, gs:60h
0x180188f0a  xor     edx, edx; Flags
0x180188f0c  mov     r8d, [rsp+620h+ObjectInformationLength]; Size
0x180188f11  mov     rcx, [rcx+30h]; HeapHandle
0x180188f15  call    cs:__imp_RtlAllocateHeap
0x180188f1c  nop     dword ptr [rax+rax+00h]
0x180188f21  mov     rdi, rax
0x180188f24  test    rax, rax
0x180188f27  jnz     short loc_180188F33
0x180188f29  mov     ebx, 0C0000017h
0x180188f2e  jmp     loc_180189200
0x180188f33  mov     r9d, [rsp+620h+ObjectInformationLength]; ObjectInformationLength
0x180188f38  lea     rax, [rsp+620h+ObjectInformationLength]
0x180188f3d  mov     r8, rdi; ObjectInformation
0x180188f40  mov     [rsp+620h+ReturnLength], rax; ReturnLength
0x180188f45  mov     edx, 1; ObjectInformationClass
0x180188f4a  mov     rcx, rsi; Handle
0x180188f4d  call    cs:__imp_NtQueryObject
0x180188f54  nop     dword ptr [rax+rax+00h]
0x180188f59  mov     ebx, eax
0x180188f5b  test    eax, eax
0x180188f5d  js      loc_1801891E2
0x180188f63  mov     rsi, rdi
0x180188f66  jmp     short loc_180188F6F
0x180188f68  lea     rsi, [rbp+520h+ObjectInformation]
0x180188f6f  lea     rax, qword_1802821C8
0x180188f76  mov     [rsp+620h+ObjectAttributes.Length], 30h ; '0'
0x180188f7e  xorps   xmm0, xmm0
0x180188f81  mov     [rsp+620h+ObjectAttributes.ObjectName], rax
0x180188f86  lea     r9, stru_1802821D8; Name
0x180188f8d  mov     [rsp+620h+ObjectAttributes.RootDirectory], r14
0x180188f92  lea     r8, [rsp+620h+ObjectAttributes]; ObjectAttributes
0x180188f97  mov     [rsp+620h+ObjectAttributes.Attributes], 82h
0x180188f9f  mov     edx, 0F0001h; DesiredAccess
0x180188fa4  lea     rcx, [rsp+620h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180188fa9  movdqu  xmmword ptr [rsp+620h+ObjectAttributes.SecurityDescriptor], xmm0
0x180188faf  call    cs:__imp_NtCreateSymbolicLinkObject
0x180188fb6  nop     dword ptr [rax+rax+00h]
0x180188fbb  mov     ebx, eax
0x180188fbd  test    eax, eax
0x180188fbf  js      loc_1801891DD
0x180188fc5  xor     eax, eax
0x180188fc7  lea     r8, aWsWs; "%ws\\%ws"
0x180188fce  mov     [rbp+520h+SourceString], ax
0x180188fd2  lea     rcx, [rbp+520h+SourceString]
0x180188fd6  mov     rax, [r15+8]
0x180188fda  mov     edx, 188h
0x180188fdf  mov     r9, [rsi+8]
0x180188fe3  mov     [rsp+620h+ReturnLength], rax
0x180188fe8  call    RtlStringCchPrintfW
0x180188fed  mov     ebx, eax
0x180188fef  test    eax, eax
0x180188ff1  js      loc_1801891DD
0x180188ff7  lea     rdx, [rbp+520h+SourceString]; SourceString
0x180188ffb  lea     rcx, [rbp+520h+DestinationString]; DestinationString
0x180188fff  call    cs:__imp_RtlInitUnicodeString
0x180189006  nop     dword ptr [rax+rax+00h]
0x18018900b  lea     rax, qword_1802821E8
0x180189012  mov     [rsp+620h+ObjectAttributes.RootDirectory], r14
0x180189017  xorps   xmm0, xmm0
0x18018901a  mov     [rsp+620h+ObjectAttributes.ObjectName], rax
0x18018901f  mov     r15d, 30h ; '0'
0x180189025  mov     [rsp+620h+ObjectAttributes.Attributes], 82h
0x18018902d  lea     r9, [rbp+520h+DestinationString]; Name
0x180189031  mov     [rsp+620h+ObjectAttributes.Length], r15d
0x180189036  lea     r8, [rsp+620h+ObjectAttributes]; ObjectAttributes
0x18018903b  mov     edx, 0F0001h; DesiredAccess
0x180189040  lea     rcx, [rsp+620h+Handle]; SymbolicLinkHandle
0x180189045  movdqu  xmmword ptr [rsp+620h+ObjectAttributes.SecurityDescriptor], xmm0
0x18018904b  call    cs:__imp_NtCreateSymbolicLinkObject
0x180189052  nop     dword ptr [rax+rax+00h]
0x180189057  mov     ebx, eax
0x180189059  test    eax, eax
0x18018905b  js      loc_1801891DD
0x180189061  xor     eax, eax
0x180189063  lea     r8, aWsWs; "%ws\\%ws"
0x18018906a  mov     [rbp+520h+SourceString], ax
0x18018906e  lea     rcx, [rbp+520h+SourceString]
0x180189072  mov     r9, [rsi+8]
0x180189076  lea     rax, aSession; "Session"
0x18018907d  mov     edx, 188h
0x180189082  mov     [rsp+620h+ReturnLength], rax
0x180189087  call    RtlStringCchPrintfW
0x18018908c  mov     ebx, eax
0x18018908e  test    eax, eax
0x180189090  js      loc_1801891DD
0x180189096  lea     rdx, [rbp+520h+SourceString]; SourceString
0x18018909a  lea     rcx, [rbp+520h+DestinationString]; DestinationString
0x18018909e  call    cs:__imp_RtlInitUnicodeString
0x1801890a5  nop     dword ptr [rax+rax+00h]
0x1801890aa  lea     rax, qword_1802821F8
0x1801890b1  mov     [rsp+620h+ObjectAttributes.Length], r15d
0x1801890b6  xorps   xmm0, xmm0
0x1801890b9  mov     [rsp+620h+ObjectAttributes.ObjectName], rax
0x1801890be  lea     r9, [rbp+520h+DestinationString]; Name
0x1801890c2  mov     [rsp+620h+ObjectAttributes.RootDirectory], r14
0x1801890c7  lea     r8, [rsp+620h+ObjectAttributes]; ObjectAttributes
0x1801890cc  mov     [rsp+620h+ObjectAttributes.Attributes], 82h
0x1801890d4  mov     edx, 0F0001h; DesiredAccess
0x1801890d9  lea     rcx, [rsp+620h+var_5D8]; SymbolicLinkHandle
0x1801890de  movdqu  xmmword ptr [rsp+620h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801890e4  call    cs:__imp_NtCreateSymbolicLinkObject
0x1801890eb  nop     dword ptr [rax+rax+00h]
0x1801890f0  mov     ebx, eax
0x1801890f2  test    eax, eax
0x1801890f4  js      loc_1801891DD
0x1801890fa  xor     eax, eax
0x1801890fc  lea     r8, aWsWs; "%ws\\%ws"
0x180189103  mov     [rbp+520h+SourceString], ax
0x180189107  lea     rcx, [rbp+520h+SourceString]
0x18018910b  mov     r9, [rsi+8]
0x18018910f  lea     rax, aAppcontainerna; "AppContainerNamedObjects"
0x180189116  mov     edx, 188h
0x18018911b  mov     [rsp+620h+ReturnLength], rax
0x180189120  call    RtlStringCchPrintfW
0x180189125  mov     ebx, eax
0x180189127  test    eax, eax
0x180189129  js      loc_1801891DD
0x18018912f  lea     rdx, [rbp+520h+SourceString]; SourceString
0x180189133  lea     rcx, [rbp+520h+DestinationString]; DestinationString
0x180189137  call    cs:__imp_RtlInitUnicodeString
0x18018913e  nop     dword ptr [rax+rax+00h]
0x180189143  lea     rax, a02; "02"
0x18018914a  mov     [rsp+620h+ObjectAttributes.Length], r15d
0x18018914f  xorps   xmm0, xmm0
0x180189152  mov     [rsp+620h+ObjectAttributes.ObjectName], rax
0x180189157  lea     r9, [rbp+520h+DestinationString]; Name
0x18018915b  mov     [rsp+620h+ObjectAttributes.RootDirectory], r14
0x180189160  lea     r8, [rsp+620h+ObjectAttributes]; ObjectAttributes
0x180189165  mov     [rsp+620h+ObjectAttributes.Attributes], 82h
0x18018916d  mov     edx, 0F0001h; DesiredAccess
0x180189172  lea     rcx, [rsp+620h+var_5D0]; SymbolicLinkHandle
0x180189177  movdqu  xmmword ptr [rsp+620h+ObjectAttributes.SecurityDescriptor], xmm0
0x18018917d  call    cs:__imp_NtCreateSymbolicLinkObject
0x180189184  nop     dword ptr [rax+rax+00h]
0x180189189  mov     ebx, eax
0x18018918b  test    eax, eax
0x18018918d  js      short loc_1801891DD
0x18018918f  mov     rax, [rsp+620h+Handle]
0x180189194  mov     rcx, [rbp+520h+var_588]
0x180189198  mov     [r12], rax
0x18018919c  mov     rax, [rsp+620h+SymbolicLinkHandle]
0x1801891a1  mov     [r13+0], rax
0x1801891a5  mov     rax, [rsp+620h+var_5D8]
0x1801891aa  mov     [rcx], rax
0x1801891ad  mov     rax, [rsp+620h+var_5D0]
0x1801891b2  mov     rcx, [rbp+520h+var_580]
0x1801891b6  mov     [rsp+620h+Handle], 0
0x1801891bf  mov     [rsp+620h+SymbolicLinkHandle], 0
0x1801891c8  mov     [rsp+620h+var_5D8], 0
0x1801891d1  mov     [rcx], rax
0x1801891d4  mov     [rsp+620h+var_5D0], 0
0x1801891dd  test    rdi, rdi
0x1801891e0  jz      short loc_180189200
0x1801891e2  mov     rcx, gs:60h
0x1801891eb  mov     r8, rdi; P
0x1801891ee  xor     edx, edx; Flags
0x1801891f0  mov     rcx, [rcx+30h]; HeapHandle
0x1801891f4  call    cs:__imp_RtlFreeHeap
0x1801891fb  nop     dword ptr [rax+rax+00h]
0x180189200  mov     rcx, [rsp+620h+Handle]; Handle
0x180189205  test    rcx, rcx
0x180189208  jz      short loc_180189216
0x18018920a  call    cs:__imp_NtClose
0x180189211  nop     dword ptr [rax+rax+00h]
0x180189216  mov     rcx, [rsp+620h+SymbolicLinkHandle]; Handle
0x18018921b  test    rcx, rcx
0x18018921e  jz      short loc_18018922C
0x180189220  call    cs:__imp_NtClose
0x180189227  nop     dword ptr [rax+rax+00h]
0x18018922c  mov     rcx, [rsp+620h+var_5D8]; Handle
0x180189231  test    rcx, rcx
0x180189234  jz      short loc_180189242
0x180189236  call    cs:__imp_NtClose
0x18018923d  nop     dword ptr [rax+rax+00h]
0x180189242  mov     rcx, [rsp+620h+var_5D0]; Handle
0x180189247  test    rcx, rcx
0x18018924a  jz      short loc_180189258
0x18018924c  call    cs:__imp_NtClose
0x180189253  nop     dword ptr [rax+rax+00h]
0x180189258  mov     eax, ebx
0x18018925a  mov     rcx, [rbp+520h+var_50]
0x180189261  xor     rcx, rsp; StackCookie
0x180189264  call    __security_check_cookie
0x180189269  add     rsp, 5E8h
0x180189270  pop     r15
0x180189272  pop     r14
0x180189274  pop     r13
0x180189276  pop     r12
0x180189278  pop     rdi
0x180189279  pop     rsi
0x18018927a  pop     rbx
0x18018927b  pop     rbp
0x18018927c  retn
```
