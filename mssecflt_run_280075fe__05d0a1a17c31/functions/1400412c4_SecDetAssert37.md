# SecDetAssert37

- ea: `0x1400412c4`
- end: `0x14004152e`
- name: `SecDetAssert37`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140043ff0`

## callees

- `0x1400062f4`
- `0x140009b80`
- `0x14000b824`
- `0x14000b940`
- `0x140011610`
- `0x140011650`
- `0x14002aa18`
- `0x1400412c4`
- `0x14004195c`

## import_xrefs

- `ntoskrnl!ZwOpenDirectoryObject` at `0x14004136a`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x14004136a`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x1400413e3`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x1400413e3`
- `ntoskrnl!IoDriverObjectType` at `0x140041439`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400413a4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400413a4`
- `ntoskrnl!ZwClose` at `0x1400414e6`
- `ntoskrnl!ZwClose` at `0x1400414e6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400414a0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400414a0`

## pseudocode

```c
void SecDetAssert37()
{
  void *v0; // rbx
  PVOID v1; // rax
  NTSTATUS v2; // esi
  _QWORD *v3; // rdi
  int appended; // eax
  int Context; // [rsp+30h] [rbp-21h]
  PVOID Object; // [rsp+48h] [rbp-9h] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+50h] [rbp-1h] BYREF
  PVOID P; // [rsp+58h] [rbp+7h] BYREF
  void *DirectoryHandle; // [rsp+60h] [rbp+Fh] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp+17h] BYREF
  ULONG ReturnLength; // [rsp+98h] [rbp+47h] BYREF
  ULONG v12; // [rsp+9Ch] [rbp+4Bh] BYREF

  DirectoryHandle = 0;
  v0 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v12 = 0;
  ReturnLength = 0;
  Object = 0;
  P = 0;
  ListEntry = 0;
  if ( *(_BYTE *)DetectionContext && _bittest64((const signed __int64 *)&xmmword_14001B740, 0x27u) )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_14001B0F8;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenDirectoryObject(&DirectoryHandle, 1u, &ObjectAttributes) >= 0 )
    {
      v1 = qword_140020008
         ? (PVOID)qword_140020008(256, 4096, 2020434771)
         : ExAllocatePoolWithTag(PagedPool, 0x1000u, 0x786D6353u);
      v0 = v1;
      if ( v1 )
      {
        do
        {
          v2 = ZwQueryDirectoryObject(DirectoryHandle, v0, 0x1000u, 0, 0, &v12, &ReturnLength);
          if ( v2 < 0 )
            break;
          v3 = v0;
          if ( *((_QWORD *)v0 + 3) )
          {
            do
            {
              appended = SecAppendUnicodeStringToUnicodeString(&qword_14001B108, v3, &P, 1953719123);
              v3 += 4;
              if ( appended >= 0 )
              {
                LOBYTE(Context) = 0;
                if ( (int)SecReferenceObjectByName(P, 64, 0, 0x80000000LL, IoDriverObjectType, Context, 0, &Object) >= 0
                  && (int)SecGetSystemModuleContextByAddress(*((_QWORD *)Object + 11), &ListEntry) >= 0 )
                {
                  SecDetAssertDriverDispatchVectorsForDriver(Object, ListEntry);
                }
              }
              if ( ListEntry )
              {
                SecReleaseSystemModuleContext(ListEntry);
                ListEntry = 0;
              }
              if ( Object )
              {
                ObfDereferenceObject(Object);
                Object = 0;
              }
              if ( P )
              {
                SecFreePool(P, 0x74736353u);
                P = 0;
              }
            }
            while ( v3[3] );
          }
        }
        while ( v2 == 261 );
      }
    }
    if ( DirectoryHandle )
      ZwClose(DirectoryHandle);
    if ( v0 )
      SecFreePool(v0, 0x786D6353u);
  }
}

```

## disassembly

```asm
0x1400412c4  mov     rax, rsp
0x1400412c7  mov     [rax+8], rbx
0x1400412cb  mov     [rax+10h], rsi
0x1400412cf  mov     [rax+18h], rdi
0x1400412d3  mov     [rax+20h], r14
0x1400412d7  push    rbp
0x1400412d8  lea     rbp, [rax-5Fh]
0x1400412dc  sub     rsp, 0A0h
0x1400412e3  mov     rax, cs:__security_cookie
0x1400412ea  xor     rax, rsp
0x1400412ed  mov     [rbp+57h+var_8], rax
0x1400412f1  mov     rax, cs:DetectionContext
0x1400412f8  xor     r14d, r14d
0x1400412fb  mov     [rbp+57h+DirectoryHandle], r14
0x1400412ff  mov     ebx, r14d
0x140041302  mov     dword ptr [rbp+57h+ObjectAttributes+4], r14d
0x140041306  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], r14d
0x14004130a  mov     [rbp+57h+var_C], r14d
0x14004130e  mov     [rbp+57h+var_10], r14d
0x140041312  mov     [rbp+57h+Object], r14
0x140041316  mov     [rbp+57h+P], r14
0x14004131a  mov     [rbp+57h+ListEntry], r14
0x14004131e  mov     cl, [rax]
0x140041320  test    cl, cl
0x140041322  jz      loc_140041504
0x140041328  bt      qword ptr cs:xmmword_14001B740, 27h ; '''
0x140041331  jnb     loc_140041504
0x140041337  lea     rax, qword_14001B0F8
0x14004133e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140041345  xorps   xmm0, xmm0
0x140041348  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14004134c  lea     edi, [r14+1]
0x140041350  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140041357  mov     edx, edi; DesiredAccess
0x140041359  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14004135d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140041361  lea     rcx, [rbp+57h+DirectoryHandle]; DirectoryHandle
0x140041365  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004136a  call    cs:__imp_ZwOpenDirectoryObject
0x140041371  nop     dword ptr [rax+rax+00h]
0x140041376  test    eax, eax
0x140041378  js      loc_1400414DD
0x14004137e  mov     rax, cs:qword_140020008
0x140041385  mov     edx, 1000h; NumberOfBytes
0x14004138a  mov     r8d, 786D6353h; Tag
0x140041390  test    rax, rax
0x140041393  jz      short loc_1400413A2
0x140041395  mov     ecx, 100h
0x14004139a  call    cs:__guard_dispatch_icall_fptr
0x1400413a0  jmp     short loc_1400413B0
0x1400413a2  mov     ecx, edi; PoolType
0x1400413a4  call    cs:__imp_ExAllocatePoolWithTag
0x1400413ab  nop     dword ptr [rax+rax+00h]
0x1400413b0  mov     rbx, rax
0x1400413b3  test    rax, rax
0x1400413b6  jz      loc_1400414DD
0x1400413bc  mov     rcx, [rbp+57h+DirectoryHandle]; DirectoryHandle
0x1400413c0  lea     rax, [rbp+57h+var_10]
0x1400413c4  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x1400413c9  xor     r9d, r9d; ReturnSingleEntry
0x1400413cc  lea     rax, [rbp+57h+var_C]
0x1400413d0  mov     r8d, 1000h; BufferLength
0x1400413d6  mov     [rsp+0A0h+Context], rax; Context
0x1400413db  mov     rdx, rbx; Buffer
0x1400413de  mov     [rsp+0A0h+RestartScan], r14b; RestartScan
0x1400413e3  call    cs:__imp_ZwQueryDirectoryObject
0x1400413ea  nop     dword ptr [rax+rax+00h]
0x1400413ef  mov     esi, eax
0x1400413f1  test    eax, eax
0x1400413f3  js      loc_1400414DD
0x1400413f9  mov     rdi, rbx
0x1400413fc  cmp     [rbx+18h], r14
0x140041400  jz      loc_1400414D1
0x140041406  mov     r9d, 74736353h
0x14004140c  lea     r8, [rbp+57h+P]
0x140041410  mov     rdx, rdi
0x140041413  lea     rcx, qword_14001B108
0x14004141a  call    SecAppendUnicodeStringToUnicodeString
0x14004141f  add     rdi, 20h ; ' '
0x140041423  test    eax, eax
0x140041425  js      short loc_140041485
0x140041427  lea     rax, [rbp+57h+Object]
0x14004142b  xor     r8d, r8d
0x14004142e  mov     [rsp+0A0h+var_68], rax
0x140041433  mov     r9d, 80000000h
0x140041439  mov     rax, cs:__imp_IoDriverObjectType
0x140041440  mov     [rsp+0A0h+ReturnLength], r14
0x140041445  mov     byte ptr [rsp+0A0h+Context], r14b
0x14004144a  lea     edx, [r8+40h]
0x14004144e  mov     rcx, [rax]
0x140041451  mov     qword ptr [rsp+0A0h+RestartScan], rcx
0x140041456  mov     rcx, [rbp+57h+P]
0x14004145a  call    SecReferenceObjectByName
0x14004145f  test    eax, eax
0x140041461  js      short loc_140041485
0x140041463  mov     rcx, [rbp+57h+Object]
0x140041467  lea     rdx, [rbp+57h+ListEntry]
0x14004146b  mov     rcx, [rcx+58h]
0x14004146f  call    SecGetSystemModuleContextByAddress
0x140041474  test    eax, eax
0x140041476  js      short loc_140041485
0x140041478  mov     rdx, [rbp+57h+ListEntry]
0x14004147c  mov     rcx, [rbp+57h+Object]
0x140041480  call    SecDetAssertDriverDispatchVectorsForDriver
0x140041485  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x140041489  test    rcx, rcx
0x14004148c  jz      short loc_140041497
0x14004148e  call    SecReleaseSystemModuleContext
0x140041493  mov     [rbp+57h+ListEntry], r14
0x140041497  mov     rcx, [rbp+57h+Object]; Object
0x14004149b  test    rcx, rcx
0x14004149e  jz      short loc_1400414B0
0x1400414a0  call    cs:__imp_ObfDereferenceObject
0x1400414a7  nop     dword ptr [rax+rax+00h]
0x1400414ac  mov     [rbp+57h+Object], r14
0x1400414b0  mov     rcx, [rbp+57h+P]; P
0x1400414b4  test    rcx, rcx
0x1400414b7  jz      short loc_1400414C7
0x1400414b9  mov     edx, 74736353h; Tag
0x1400414be  call    SecFreePool
0x1400414c3  mov     [rbp+57h+P], r14
0x1400414c7  cmp     [rdi+18h], r14
0x1400414cb  jnz     loc_140041406
0x1400414d1  cmp     esi, 105h
0x1400414d7  jz      loc_1400413BC
0x1400414dd  mov     rcx, [rbp+57h+DirectoryHandle]; Handle
0x1400414e1  test    rcx, rcx
0x1400414e4  jz      short loc_1400414F2
0x1400414e6  call    cs:__imp_ZwClose
0x1400414ed  nop     dword ptr [rax+rax+00h]
0x1400414f2  test    rbx, rbx
0x1400414f5  jz      short loc_140041504
0x1400414f7  mov     edx, 786D6353h; Tag
0x1400414fc  mov     rcx, rbx; P
0x1400414ff  call    SecFreePool
0x140041504  mov     rcx, [rbp+57h+var_8]
0x140041508  xor     rcx, rsp; StackCookie
0x14004150b  call    __security_check_cookie
0x140041510  lea     r11, [rsp+0A0h+var_s0]
0x140041518  mov     rbx, [r11+10h]
0x14004151c  mov     rsi, [r11+18h]
0x140041520  mov     rdi, [r11+20h]
0x140041524  mov     r14, [r11+28h]
0x140041528  mov     rsp, r11
0x14004152b  pop     rbp
0x14004152c  retn
```
