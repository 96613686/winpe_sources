# CipIsCimBackedFile

- ea: `0x180057134`
- end: `0x18005739e`
- name: `CipIsCimBackedFile`
- size: `618`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180057008`
- `0x18008fa34`

## callees

- `0x180057134`
- `0x1800573a4`
- `0x18008a088`
- `0x18008a2f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18005720b`
- `ntoskrnl!ExAllocatePool2` at `0x18005720b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800571e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180057374`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800571e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180057374`
- `ntoskrnl!ZwOpenFile` at `0x1800572cb`
- `ntoskrnl!ZwOpenFile` at `0x1800572cb`
- `ntoskrnl!ZwClose` at `0x18005735b`
- `ntoskrnl!ZwClose` at `0x18005735b`
- `ntoskrnl!ObfDereferenceObject` at `0x180057346`
- `ntoskrnl!ObfDereferenceObject` at `0x180057346`
- `ntoskrnl!IoFileObjectType` at `0x1800572dd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180057302`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180057302`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1800571b7`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1800571b7`

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
0x180057134  mov     [rsp-8+arg_0], rbx
0x180057139  push    rbp
0x18005713a  push    rsi
0x18005713b  push    rdi
0x18005713c  push    r12
0x18005713e  push    r13
0x180057140  push    r14
0x180057142  push    r15
0x180057144  lea     rbp, [rsp-27h]
0x180057149  sub     rsp, 0D0h
0x180057150  xorps   xmm0, xmm0
0x180057153  mov     r13, rcx
0x180057156  xor     ecx, ecx
0x180057158  xorps   xmm1, xmm1
0x18005715b  xor     eax, eax
0x18005715d  mov     [rbp+57h+arg_8], ecx
0x180057160  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180057164  mov     [rbp+57h+var_A8], rax
0x180057168  mov     r12, r8
0x18005716b  mov     [rbp+57h+var_90], rax
0x18005716f  mov     r15, rdx
0x180057172  mov     edi, ecx
0x180057174  mov     [rbp+57h+FileHandle], rcx
0x180057178  mov     esi, ecx
0x18005717a  mov     [rdx], cl
0x18005717c  movups  [rbp+57h+var_58], xmm0
0x180057180  mov     r14d, ecx
0x180057183  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180057187  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18005718b  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18005718f  movups  [rbp+57h+var_B8], xmm1
0x180057193  movups  [rbp+57h+var_A0], xmm0
0x180057197  lea     rax, [rbp+57h+arg_8]
0x18005719b  xor     r9d, r9d
0x18005719e  mov     [rsp+100h+var_D0], rax
0x1800571a3  xor     r8d, r8d
0x1800571a6  mov     [rsp+100h+OpenOptions], esi
0x1800571aa  mov     edx, 904A0h
0x1800571af  mov     rcx, r13
0x1800571b2  mov     qword ptr [rsp+100h+ShareAccess], rdi
0x1800571b7  call    cs:__imp_FsRtlKernelFsControlFile
0x1800571be  nop     dword ptr [rax+rax+00h]
0x1800571c3  mov     ebx, eax
0x1800571c5  cmp     eax, 80000005h
0x1800571ca  jz      short loc_1800571D3
0x1800571cc  cmp     eax, 0C0000023h
0x1800571d1  jnz     short loc_18005722D
0x1800571d3  test    rdi, rdi
0x1800571d6  jz      short loc_1800571EE
0x1800571d8  mov     edx, 63734943h; Tag
0x1800571dd  mov     rcx, rdi; P
0x1800571e0  call    cs:__imp_ExFreePoolWithTag
0x1800571e7  nop     dword ptr [rax+rax+00h]
0x1800571ec  xor     edi, edi
0x1800571ee  lea     eax, [rsi+228h]
0x1800571f4  cmp     eax, esi
0x1800571f6  jb      loc_180057329
0x1800571fc  mov     edx, eax
0x1800571fe  mov     ecx, 100h
0x180057203  mov     r8d, 63734943h
0x180057209  mov     esi, eax
0x18005720b  call    cs:__imp_ExAllocatePool2
0x180057212  nop     dword ptr [rax+rax+00h]
0x180057217  mov     rdi, rax
0x18005721a  test    rax, rax
0x18005721d  jnz     loc_180057197
0x180057223  mov     ebx, 0C0000017h
0x180057228  jmp     loc_18005732E
0x18005722d  test    eax, eax
0x18005722f  jns     short loc_180057246
0x180057231  cmp     eax, 0C0000010h
0x180057236  jnz     loc_18005732E
0x18005723c  mov     [r15], r14b
0x18005723f  xor     ebx, ebx
0x180057241  jmp     loc_18005732E
0x180057246  mov     eax, [rdi+14h]
0x180057249  lea     rdx, [rbp+57h+var_A0]
0x18005724d  mov     qword ptr [rbp+57h+var_B8], rax
0x180057251  lea     rcx, [rbp+57h+var_B8]
0x180057255  mov     qword ptr [rbp+57h+var_B8+8], rax
0x180057259  lea     rax, [rdi+18h]
0x18005725d  mov     [rbp+57h+var_A8], rax
0x180057261  call    RtlConvertWin32FilePathToNtFilePath
0x180057266  mov     ebx, eax
0x180057268  test    eax, eax
0x18005726a  js      loc_18005732E
0x180057270  lea     rdx, [rbp+57h+var_58]
0x180057274  lea     rcx, [rbp+57h+var_A0]
0x180057278  call    RtlInitUnicodeStringFromLUnicodeString
0x18005727d  mov     ebx, eax
0x18005727f  test    eax, eax
0x180057281  js      loc_18005732E
0x180057287  lea     rax, [rbp+57h+var_58]
0x18005728b  mov     [rsp+100h+OpenOptions], 40h ; '@'; OpenOptions
0x180057293  xorps   xmm0, xmm0
0x180057296  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005729a  mov     esi, 1
0x18005729f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800572a6  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800572aa  mov     [rsp+100h+ShareAccess], esi; ShareAccess
0x1800572ae  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800572b2  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x1800572b6  mov     edx, 120089h; DesiredAccess
0x1800572bb  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800572c2  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800572c6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800572cb  call    cs:__imp_ZwOpenFile
0x1800572d2  nop     dword ptr [rax+rax+00h]
0x1800572d7  mov     ebx, eax
0x1800572d9  test    eax, eax
0x1800572db  js      short loc_18005732E
0x1800572dd  mov     r8, cs:__imp_IoFileObjectType
0x1800572e4  lea     rax, [rbp+57h+Object]
0x1800572e8  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800572ec  xor     r9d, r9d; AccessMode
0x1800572ef  mov     qword ptr [rsp+100h+OpenOptions], r14; HandleInformation
0x1800572f4  mov     edx, esi; DesiredAccess
0x1800572f6  mov     [rbp+57h+Object], r14
0x1800572fa  mov     r8, [r8]; ObjectType
0x1800572fd  mov     qword ptr [rsp+100h+ShareAccess], rax; Object
0x180057302  call    cs:__imp_ObReferenceObjectByHandle
0x180057309  nop     dword ptr [rax+rax+00h]
0x18005730e  mov     r14, [rbp+57h+Object]
0x180057312  mov     ebx, eax
0x180057314  test    eax, eax
0x180057316  js      short loc_18005732E
0x180057318  test    r12, r12
0x18005731b  jz      short loc_180057324
0x18005731d  mov     [r12], r14
0x180057321  xor     r14d, r14d
0x180057324  mov     [r15], sil
0x180057327  jmp     short loc_18005732E
0x180057329  mov     ebx, 0C0000095h
0x18005732e  cmp     [rbp+57h+var_90], 0
0x180057333  jz      short loc_18005733E
0x180057335  lea     rcx, [rbp+57h+var_A0]
0x180057339  call    RtlFreeLBlob
0x18005733e  test    r14, r14
0x180057341  jz      short loc_180057352
0x180057343  mov     rcx, r14; Object
0x180057346  call    cs:__imp_ObfDereferenceObject
0x18005734d  nop     dword ptr [rax+rax+00h]
0x180057352  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180057356  test    rcx, rcx
0x180057359  jz      short loc_180057367
0x18005735b  call    cs:__imp_ZwClose
0x180057362  nop     dword ptr [rax+rax+00h]
0x180057367  test    rdi, rdi
0x18005736a  jz      short loc_180057380
0x18005736c  mov     edx, 63734943h; Tag
0x180057371  mov     rcx, rdi; P
0x180057374  call    cs:__imp_ExFreePoolWithTag
0x18005737b  nop     dword ptr [rax+rax+00h]
0x180057380  mov     eax, ebx
0x180057382  mov     rbx, [rsp+100h+arg_0]
0x18005738a  add     rsp, 0D0h
0x180057391  pop     r15
0x180057393  pop     r14
0x180057395  pop     r13
0x180057397  pop     r12
0x180057399  pop     rdi
0x18005739a  pop     rsi
0x18005739b  pop     rbp
0x18005739c  retn
```
