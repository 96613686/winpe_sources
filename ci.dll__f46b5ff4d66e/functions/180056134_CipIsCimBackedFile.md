# CipIsCimBackedFile

- ea: `0x180056134`
- end: `0x18005639e`
- name: `CipIsCimBackedFile`
- size: `618`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180056008`
- `0x18009d178`

## callees

- `0x180056134`
- `0x1800563a4`
- `0x18008803c`
- `0x1800882a4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18005620b`
- `ntoskrnl!ExAllocatePool2` at `0x18005620b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800561e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180056374`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800561e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180056374`
- `ntoskrnl!ZwOpenFile` at `0x1800562cb`
- `ntoskrnl!ZwOpenFile` at `0x1800562cb`
- `ntoskrnl!ZwClose` at `0x18005635b`
- `ntoskrnl!ZwClose` at `0x18005635b`
- `ntoskrnl!ObfDereferenceObject` at `0x180056346`
- `ntoskrnl!ObfDereferenceObject` at `0x180056346`
- `ntoskrnl!IoFileObjectType` at `0x1800562dd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180056302`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180056302`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1800561b7`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1800561b7`

## pseudocode

```c
__int64 __fastcall CipIsCimBackedFile(__int64 a1, _BYTE *a2, PVOID *a3)
{
  unsigned int *Pool2; // rdi
  unsigned int v7; // esi
  PVOID v8; // r14
  int v9; // eax
  int inited; // ebx
  unsigned int v11; // eax
  NTSTATUS v12; // eax
  PVOID Object; // [rsp+40h] [rbp-69h] BYREF
  __int128 v15; // [rsp+48h] [rbp-61h] BYREF
  unsigned int *v16; // [rsp+58h] [rbp-51h]
  __int128 v17; // [rsp+60h] [rbp-49h] BYREF
  __int64 v18; // [rsp+70h] [rbp-39h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-31h] BYREF
  __int128 v20; // [rsp+A8h] [rbp-1h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp+Fh] BYREF
  int v22; // [rsp+118h] [rbp+6Fh] BYREF
  void *FileHandle; // [rsp+128h] [rbp+7Fh] BYREF

  v22 = 0;
  *(_OWORD *)&ObjectAttributes.ObjectName = 0;
  v16 = 0;
  v18 = 0;
  Pool2 = 0;
  FileHandle = 0;
  v7 = 0;
  *a2 = 0;
  v20 = 0;
  v8 = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  v15 = 0;
  v17 = 0;
  while ( 1 )
  {
    v9 = FsRtlKernelFsControlFile(a1, 591008, 0, 0, Pool2, v7, &v22);
    inited = v9;
    if ( v9 != -2147483643 && v9 != -1073741789 )
      break;
    if ( Pool2 )
    {
      ExFreePoolWithTag(Pool2, 0x63734943u);
      Pool2 = 0;
    }
    v11 = v7 + 552;
    if ( v7 + 552 < v7 )
    {
      inited = -1073741675;
      goto LABEL_20;
    }
    v7 += 552;
    Pool2 = (unsigned int *)ExAllocatePool2(256, v11, 1668499779);
    if ( !Pool2 )
    {
      inited = -1073741801;
      goto LABEL_20;
    }
  }
  if ( v9 >= 0 )
  {
    *(_QWORD *)&v15 = Pool2[5];
    *((_QWORD *)&v15 + 1) = v15;
    v16 = Pool2 + 6;
    inited = RtlConvertWin32FilePathToNtFilePath((unsigned __int64 *)&v15, &v17);
    if ( inited >= 0 )
    {
      inited = RtlInitUnicodeStringFromLUnicodeString(&v17, &v20);
      if ( inited >= 0 )
      {
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v20;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        inited = ZwOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 1u, 0x40u);
        if ( inited >= 0 )
        {
          Object = 0;
          v12 = ObReferenceObjectByHandle(FileHandle, 1u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
          v8 = Object;
          inited = v12;
          if ( v12 >= 0 )
          {
            if ( a3 )
            {
              *a3 = Object;
              v8 = 0;
            }
            *a2 = 1;
          }
        }
      }
    }
  }
  else if ( v9 == -1073741808 )
  {
    *a2 = 0;
    inited = 0;
  }
LABEL_20:
  if ( v18 )
    RtlFreeLBlob(&v17);
  if ( v8 )
    ObfDereferenceObject(v8);
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x63734943u);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180056134  mov     [rsp-8+arg_0], rbx
0x180056139  push    rbp
0x18005613a  push    rsi
0x18005613b  push    rdi
0x18005613c  push    r12
0x18005613e  push    r13
0x180056140  push    r14
0x180056142  push    r15
0x180056144  lea     rbp, [rsp-27h]
0x180056149  sub     rsp, 0D0h
0x180056150  xorps   xmm0, xmm0
0x180056153  mov     r13, rcx
0x180056156  xor     ecx, ecx
0x180056158  xorps   xmm1, xmm1
0x18005615b  xor     eax, eax
0x18005615d  mov     [rbp+57h+arg_8], ecx
0x180056160  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180056164  mov     [rbp+57h+var_A8], rax
0x180056168  mov     r12, r8
0x18005616b  mov     [rbp+57h+var_90], rax
0x18005616f  mov     r15, rdx
0x180056172  mov     edi, ecx
0x180056174  mov     [rbp+57h+FileHandle], rcx
0x180056178  mov     esi, ecx
0x18005617a  mov     [rdx], cl
0x18005617c  movups  [rbp+57h+var_58], xmm0
0x180056180  mov     r14d, ecx
0x180056183  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180056187  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18005618b  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18005618f  movups  [rbp+57h+var_B8], xmm1
0x180056193  movups  [rbp+57h+var_A0], xmm0
0x180056197  lea     rax, [rbp+57h+arg_8]
0x18005619b  xor     r9d, r9d
0x18005619e  mov     [rsp+100h+var_D0], rax
0x1800561a3  xor     r8d, r8d
0x1800561a6  mov     [rsp+100h+OpenOptions], esi
0x1800561aa  mov     edx, 904A0h
0x1800561af  mov     rcx, r13
0x1800561b2  mov     qword ptr [rsp+100h+ShareAccess], rdi
0x1800561b7  call    cs:__imp_FsRtlKernelFsControlFile
0x1800561be  nop     dword ptr [rax+rax+00h]
0x1800561c3  mov     ebx, eax
0x1800561c5  cmp     eax, 80000005h
0x1800561ca  jz      short loc_1800561D3
0x1800561cc  cmp     eax, 0C0000023h
0x1800561d1  jnz     short loc_18005622D
0x1800561d3  test    rdi, rdi
0x1800561d6  jz      short loc_1800561EE
0x1800561d8  mov     edx, 63734943h; Tag
0x1800561dd  mov     rcx, rdi; P
0x1800561e0  call    cs:__imp_ExFreePoolWithTag
0x1800561e7  nop     dword ptr [rax+rax+00h]
0x1800561ec  xor     edi, edi
0x1800561ee  lea     eax, [rsi+228h]
0x1800561f4  cmp     eax, esi
0x1800561f6  jb      loc_180056329
0x1800561fc  mov     edx, eax
0x1800561fe  mov     ecx, 100h
0x180056203  mov     r8d, 63734943h
0x180056209  mov     esi, eax
0x18005620b  call    cs:__imp_ExAllocatePool2
0x180056212  nop     dword ptr [rax+rax+00h]
0x180056217  mov     rdi, rax
0x18005621a  test    rax, rax
0x18005621d  jnz     loc_180056197
0x180056223  mov     ebx, 0C0000017h
0x180056228  jmp     loc_18005632E
0x18005622d  test    eax, eax
0x18005622f  jns     short loc_180056246
0x180056231  cmp     eax, 0C0000010h
0x180056236  jnz     loc_18005632E
0x18005623c  mov     [r15], r14b
0x18005623f  xor     ebx, ebx
0x180056241  jmp     loc_18005632E
0x180056246  mov     eax, [rdi+14h]
0x180056249  lea     rdx, [rbp+57h+var_A0]
0x18005624d  mov     qword ptr [rbp+57h+var_B8], rax
0x180056251  lea     rcx, [rbp+57h+var_B8]
0x180056255  mov     qword ptr [rbp+57h+var_B8+8], rax
0x180056259  lea     rax, [rdi+18h]
0x18005625d  mov     [rbp+57h+var_A8], rax
0x180056261  call    RtlConvertWin32FilePathToNtFilePath
0x180056266  mov     ebx, eax
0x180056268  test    eax, eax
0x18005626a  js      loc_18005632E
0x180056270  lea     rdx, [rbp+57h+var_58]
0x180056274  lea     rcx, [rbp+57h+var_A0]
0x180056278  call    RtlInitUnicodeStringFromLUnicodeString
0x18005627d  mov     ebx, eax
0x18005627f  test    eax, eax
0x180056281  js      loc_18005632E
0x180056287  lea     rax, [rbp+57h+var_58]
0x18005628b  mov     [rsp+100h+OpenOptions], 40h ; '@'; OpenOptions
0x180056293  xorps   xmm0, xmm0
0x180056296  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005629a  mov     esi, 1
0x18005629f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800562a6  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800562aa  mov     [rsp+100h+ShareAccess], esi; ShareAccess
0x1800562ae  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800562b2  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x1800562b6  mov     edx, 120089h; DesiredAccess
0x1800562bb  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800562c2  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800562c6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800562cb  call    cs:__imp_ZwOpenFile
0x1800562d2  nop     dword ptr [rax+rax+00h]
0x1800562d7  mov     ebx, eax
0x1800562d9  test    eax, eax
0x1800562db  js      short loc_18005632E
0x1800562dd  mov     r8, cs:__imp_IoFileObjectType
0x1800562e4  lea     rax, [rbp+57h+Object]
0x1800562e8  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800562ec  xor     r9d, r9d; AccessMode
0x1800562ef  mov     qword ptr [rsp+100h+OpenOptions], r14; HandleInformation
0x1800562f4  mov     edx, esi; DesiredAccess
0x1800562f6  mov     [rbp+57h+Object], r14
0x1800562fa  mov     r8, [r8]; ObjectType
0x1800562fd  mov     qword ptr [rsp+100h+ShareAccess], rax; Object
0x180056302  call    cs:__imp_ObReferenceObjectByHandle
0x180056309  nop     dword ptr [rax+rax+00h]
0x18005630e  mov     r14, [rbp+57h+Object]
0x180056312  mov     ebx, eax
0x180056314  test    eax, eax
0x180056316  js      short loc_18005632E
0x180056318  test    r12, r12
0x18005631b  jz      short loc_180056324
0x18005631d  mov     [r12], r14
0x180056321  xor     r14d, r14d
0x180056324  mov     [r15], sil
0x180056327  jmp     short loc_18005632E
0x180056329  mov     ebx, 0C0000095h
0x18005632e  cmp     [rbp+57h+var_90], 0
0x180056333  jz      short loc_18005633E
0x180056335  lea     rcx, [rbp+57h+var_A0]
0x180056339  call    RtlFreeLBlob
0x18005633e  test    r14, r14
0x180056341  jz      short loc_180056352
0x180056343  mov     rcx, r14; Object
0x180056346  call    cs:__imp_ObfDereferenceObject
0x18005634d  nop     dword ptr [rax+rax+00h]
0x180056352  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180056356  test    rcx, rcx
0x180056359  jz      short loc_180056367
0x18005635b  call    cs:__imp_ZwClose
0x180056362  nop     dword ptr [rax+rax+00h]
0x180056367  test    rdi, rdi
0x18005636a  jz      short loc_180056380
0x18005636c  mov     edx, 63734943h; Tag
0x180056371  mov     rcx, rdi; P
0x180056374  call    cs:__imp_ExFreePoolWithTag
0x18005637b  nop     dword ptr [rax+rax+00h]
0x180056380  mov     eax, ebx
0x180056382  mov     rbx, [rsp+100h+arg_0]
0x18005638a  add     rsp, 0D0h
0x180056391  pop     r15
0x180056393  pop     r14
0x180056395  pop     r13
0x180056397  pop     r12
0x180056399  pop     rdi
0x18005639a  pop     rsi
0x18005639b  pop     rbp
0x18005639c  retn
```
