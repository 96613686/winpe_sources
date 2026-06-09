# CipInitializeDriverStoreCatalogStores

- ea: `0x18005da00`
- end: `0x18005dcb2`
- name: `CipInitializeDriverStoreCatalogStores`
- size: `690`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180061050`
- `0x1800e1e58`

## callees

- `0x18005da00`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005da47`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005da47`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005dbb7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005dbb7`
- `ntoskrnl!ExAllocatePool2` at `0x18005dab5`
- `ntoskrnl!ExAllocatePool2` at `0x18005db57`
- `ntoskrnl!ExAllocatePool2` at `0x18005db97`
- `ntoskrnl!ExAllocatePool2` at `0x18005dab5`
- `ntoskrnl!ExAllocatePool2` at `0x18005db57`
- `ntoskrnl!ExAllocatePool2` at `0x18005db97`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005dc5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005dc91`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005dc5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005dc91`
- `ntoskrnl!ZwClose` at `0x18005dc7a`
- `ntoskrnl!ZwClose` at `0x18005dc7a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005dbcd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005dbdf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005dbf5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005dbcd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005dbdf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005dbf5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18005dc0b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18005dc0b`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x18005dafb`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x18005dafb`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x18005da81`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x18005da81`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005db36`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005db36`

## string_xrefs

- `0x18005dc01`: `System32\CatRoot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\`

## pseudocode

```c
__int64 CipInitializeDriverStoreCatalogStores()
{
  UNICODE_STRING *Pool2; // rdi
  NTSTATUS v1; // eax
  unsigned int v2; // ebx
  BOOLEAN RestartScan; // al
  NTSTATUS v4; // eax
  const UNICODE_STRING *i; // rbx
  __int64 v6; // rax
  _QWORD *v7; // rsi
  struct _UNICODE_STRING *v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rax
  _QWORD *v11; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG ReturnLength; // [rsp+C0h] [rbp+40h] BYREF
  ULONG Context; // [rsp+C8h] [rbp+48h] BYREF
  void *DirectoryHandle; // [rsp+D0h] [rbp+50h] BYREF

  DirectoryHandle = 0;
  Pool2 = 0;
  Context = 0;
  DestinationString = 0;
  ReturnLength = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\DriverStore\\Nodes");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwOpenDirectoryObject(&DirectoryHandle, 1u, &ObjectAttributes);
  v2 = v1;
  if ( v1 == -1073741766 )
    goto LABEL_19;
  if ( v1 < 0 )
    goto LABEL_20;
  Pool2 = (UNICODE_STRING *)ExAllocatePool2(256, 1024, 1919109443);
  if ( !Pool2 )
    goto LABEL_4;
  RestartScan = 1;
LABEL_6:
  v4 = ZwQueryDirectoryObject(DirectoryHandle, Pool2, 0x400u, 1u, RestartScan, &Context, &ReturnLength);
  v2 = v4;
  if ( v4 == -2147483622 )
  {
LABEL_19:
    v2 = 0;
    goto LABEL_20;
  }
  if ( v4 < 0 )
    goto LABEL_20;
  for ( i = Pool2; ; i += 2 )
  {
    if ( !i->Length )
    {
      RestartScan = 0;
      goto LABEL_6;
    }
    if ( !RtlEqualUnicodeString(i, &stru_180030480, 1u) )
      break;
LABEL_15:
    ;
  }
  v6 = ExAllocatePool2(256, 40, 1919109443);
  v7 = (_QWORD *)v6;
  if ( !v6 )
    goto LABEL_4;
  *(_DWORD *)v6 = 42;
  v8 = (struct _UNICODE_STRING *)(v6 + 8);
  *(_WORD *)(v6 + 8) = 0;
  v9 = (unsigned __int16)(i->Length + DestinationString.Length + 118);
  *(_WORD *)(v6 + 10) = v9;
  v10 = ExAllocatePool2(258, v9, 1919109443);
  v7[2] = v10;
  if ( v10 )
  {
    RtlCopyUnicodeString(v8, &DestinationString);
    RtlAppendUnicodeStringToString(v8, &Source);
    RtlAppendUnicodeStringToString(v8, i);
    RtlAppendUnicodeStringToString(v8, &Source);
    RtlAppendUnicodeToString(v8, L"System32\\CatRoot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\\");
    v11 = (_QWORD *)qword_180048788;
    if ( *(__int64 **)qword_180048788 != &qword_180048780 )
      __fastfail(3u);
    v7[3] = &qword_180048780;
    v7[4] = v11;
    *v11 = v7 + 3;
    qword_180048788 = (__int64)(v7 + 3);
    goto LABEL_15;
  }
  ExFreePoolWithTag(v7, 0x72634943u);
LABEL_4:
  v2 = -1073741801;
LABEL_20:
  if ( DirectoryHandle )
    ZwClose(DirectoryHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x72634943u);
  return v2;
}

```

## disassembly

```asm
0x18005da00  push    rbp
0x18005da02  push    rbx
0x18005da03  push    rsi
0x18005da04  push    rdi
0x18005da05  push    r12
0x18005da07  push    r14
0x18005da09  push    r15
0x18005da0b  mov     rbp, rsp
0x18005da0e  sub     rsp, 80h
0x18005da15  xorps   xmm0, xmm0
0x18005da18  lea     rdx, SourceString; "\\DriverStore\\Nodes"
0x18005da1f  xor     r15d, r15d
0x18005da22  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005da26  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18005da2a  xor     eax, eax
0x18005da2c  mov     [rbp+DirectoryHandle], r15
0x18005da30  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18005da34  mov     edi, r15d
0x18005da37  mov     [rbp+arg_8], r15d
0x18005da3b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005da3f  mov     [rbp+arg_0], r15d
0x18005da43  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18005da47  call    cs:__imp_RtlInitUnicodeString
0x18005da4e  nop     dword ptr [rax+rax+00h]
0x18005da53  lea     rax, [rbp+DestinationString]
0x18005da57  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005da5e  xorps   xmm0, xmm0
0x18005da61  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18005da65  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18005da69  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x18005da6d  lea     edx, [r15+1]; DesiredAccess
0x18005da71  mov     [rbp+ObjectAttributes.Attributes], 240h
0x18005da78  lea     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x18005da7c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005da81  call    cs:__imp_ZwOpenDirectoryObject
0x18005da88  nop     dword ptr [rax+rax+00h]
0x18005da8d  mov     ebx, eax
0x18005da8f  mov     r12d, 72634943h
0x18005da95  cmp     eax, 0C000003Ah
0x18005da9a  jz      loc_18005DC6E
0x18005daa0  test    eax, eax
0x18005daa2  js      loc_18005DC71
0x18005daa8  mov     r8d, r12d
0x18005daab  mov     edx, 400h
0x18005dab0  mov     ecx, 100h
0x18005dab5  call    cs:__imp_ExAllocatePool2
0x18005dabc  nop     dword ptr [rax+rax+00h]
0x18005dac1  mov     rdi, rax
0x18005dac4  test    rax, rax
0x18005dac7  jnz     short loc_18005DAD3
0x18005dac9  mov     ebx, 0C0000017h
0x18005dace  jmp     loc_18005DC71
0x18005dad3  mov     al, 1
0x18005dad5  lea     rcx, [rbp+arg_0]
0x18005dad9  mov     r9b, 1; ReturnSingleEntry
0x18005dadc  mov     [rsp+80h+ReturnLength], rcx; ReturnLength
0x18005dae1  mov     r8d, 400h; BufferLength
0x18005dae7  lea     rcx, [rbp+arg_8]
0x18005daeb  mov     rdx, rdi; Buffer
0x18005daee  mov     [rsp+80h+Context], rcx; Context
0x18005daf3  mov     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x18005daf7  mov     [rsp+80h+RestartScan], al; RestartScan
0x18005dafb  call    cs:__imp_ZwQueryDirectoryObject
0x18005db02  nop     dword ptr [rax+rax+00h]
0x18005db07  mov     ebx, eax
0x18005db09  cmp     eax, 8000001Ah
0x18005db0e  jz      loc_18005DC6E
0x18005db14  test    eax, eax
0x18005db16  js      loc_18005DC71
0x18005db1c  mov     rbx, rdi
0x18005db1f  cmp     [rbx], r15w
0x18005db23  jz      loc_18005DC48
0x18005db29  mov     r8b, 1; CaseInSensitive
0x18005db2c  lea     rdx, stru_180030480; String2
0x18005db33  mov     rcx, rbx; String1
0x18005db36  call    cs:__imp_RtlEqualUnicodeString
0x18005db3d  nop     dword ptr [rax+rax+00h]
0x18005db42  test    al, al
0x18005db44  jnz     loc_18005DC3F
0x18005db4a  mov     r8d, r12d
0x18005db4d  mov     edx, 28h ; '('
0x18005db52  mov     ecx, 100h
0x18005db57  call    cs:__imp_ExAllocatePool2
0x18005db5e  nop     dword ptr [rax+rax+00h]
0x18005db63  mov     rsi, rax
0x18005db66  test    rax, rax
0x18005db69  jz      loc_18005DAC9
0x18005db6f  mov     dword ptr [rax], 2Ah ; '*'
0x18005db75  lea     r14, [rax+8]
0x18005db79  mov     [r14], r15w
0x18005db7d  mov     r8d, r12d
0x18005db80  movzx   ecx, [rbp+DestinationString.Length]
0x18005db84  add     cx, 76h ; 'v'
0x18005db88  add     cx, [rbx]
0x18005db8b  movzx   edx, cx
0x18005db8e  mov     ecx, 102h
0x18005db93  mov     [rax+0Ah], dx
0x18005db97  call    cs:__imp_ExAllocatePool2
0x18005db9e  nop     dword ptr [rax+rax+00h]
0x18005dba3  mov     [rsi+10h], rax
0x18005dba7  test    rax, rax
0x18005dbaa  jz      loc_18005DC57
0x18005dbb0  lea     rdx, [rbp+DestinationString]; SourceString
0x18005dbb4  mov     rcx, r14; DestinationString
0x18005dbb7  call    cs:__imp_RtlCopyUnicodeString
0x18005dbbe  nop     dword ptr [rax+rax+00h]
0x18005dbc3  lea     rdx, Source; Source
0x18005dbca  mov     rcx, r14; Destination
0x18005dbcd  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005dbd4  nop     dword ptr [rax+rax+00h]
0x18005dbd9  mov     rdx, rbx; Source
0x18005dbdc  mov     rcx, r14; Destination
0x18005dbdf  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005dbe6  nop     dword ptr [rax+rax+00h]
0x18005dbeb  lea     rdx, Source; Source
0x18005dbf2  mov     rcx, r14; Destination
0x18005dbf5  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005dbfc  nop     dword ptr [rax+rax+00h]
0x18005dc01  lea     rdx, aSystem32Catroo; "System32\\CatRoot\\{F750E6C3-38EE-11D1-"...
0x18005dc08  mov     rcx, r14; Destination
0x18005dc0b  call    cs:__imp_RtlAppendUnicodeToString
0x18005dc12  nop     dword ptr [rax+rax+00h]
0x18005dc17  mov     rcx, cs:qword_180048788
0x18005dc1e  lea     r14, qword_180048780
0x18005dc25  cmp     [rcx], r14
0x18005dc28  jnz     short loc_18005DC50
0x18005dc2a  lea     rax, [rsi+18h]
0x18005dc2e  mov     [rax], r14
0x18005dc31  mov     [rax+8], rcx
0x18005dc35  mov     [rcx], rax
0x18005dc38  mov     cs:qword_180048788, rax
0x18005dc3f  add     rbx, 20h ; ' '
0x18005dc43  jmp     loc_18005DB1F
0x18005dc48  mov     al, r15b
0x18005dc4b  jmp     loc_18005DAD5
0x18005dc50  mov     ecx, 3
0x18005dc55  int     29h; Win8: RtlFailFast(ecx)
0x18005dc57  mov     edx, r12d; Tag
0x18005dc5a  mov     rcx, rsi; P
0x18005dc5d  call    cs:__imp_ExFreePoolWithTag
0x18005dc64  nop     dword ptr [rax+rax+00h]
0x18005dc69  jmp     loc_18005DAC9
0x18005dc6e  mov     ebx, r15d
0x18005dc71  mov     rcx, [rbp+DirectoryHandle]; Handle
0x18005dc75  test    rcx, rcx
0x18005dc78  jz      short loc_18005DC86
0x18005dc7a  call    cs:__imp_ZwClose
0x18005dc81  nop     dword ptr [rax+rax+00h]
0x18005dc86  test    rdi, rdi
0x18005dc89  jz      short loc_18005DC9D
0x18005dc8b  mov     edx, r12d; Tag
0x18005dc8e  mov     rcx, rdi; P
0x18005dc91  call    cs:__imp_ExFreePoolWithTag
0x18005dc98  nop     dword ptr [rax+rax+00h]
0x18005dc9d  mov     eax, ebx
0x18005dc9f  add     rsp, 80h
0x18005dca6  pop     r15
0x18005dca8  pop     r14
0x18005dcaa  pop     r12
0x18005dcac  pop     rdi
0x18005dcad  pop     rsi
0x18005dcae  pop     rbx
0x18005dcaf  pop     rbp
0x18005dcb0  retn
```
