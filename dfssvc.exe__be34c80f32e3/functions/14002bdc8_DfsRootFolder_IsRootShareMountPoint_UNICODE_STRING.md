# DfsRootFolder::IsRootShareMountPoint(_UNICODE_STRING *)

- ea: `0x14002bdc8`
- end: `0x14002bec1`
- name: `?IsRootShareMountPoint@DfsRootFolder@@QEAAJPEAU_UNICODE_STRING@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(DfsRootFolder *__hidden this, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140028098`

## callees

- `0x1400291d0`
- `0x14002bdc8`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14002be63`
- `ntdll!NtOpenFile` at `0x14002be63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002be99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002be99`

## pseudocode

```c
__int64 __fastcall DfsRootFolder::IsRootShareMountPoint(DfsRootFolder *this, __m128i *a2)
{
  __m128i v2; // xmm1
  unsigned int v4; // ebx
  struct _UNICODE_STRING v6; // [rsp+38h] [rbp-9h] BYREF
  __m128i v7; // [rsp+48h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp+6Fh] BYREF

  v2 = *a2;
  FileHandle = 0;
  *(_DWORD *)(&v6.MaximumLength + 1) = v2.m128i_i32[1];
  v6.MaximumLength = v2.m128i_i16[1] - 14;
  v6.Buffer = (PWSTR)(v2.m128i_i64[1] + 14);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v6.Length = _mm_cvtsi128_si32(v2) - 14;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v7 = v2;
  v7.m128i_i16[0] = 14;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v7;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4021u);
  if ( !v4 )
  {
    if ( v6.Length )
      v4 = DfsRootFolder::CreateLinkDirectories(this, &v6, FileHandle, 0, 0);
    CloseHandle(FileHandle);
  }
  return v4;
}

```

## disassembly

```asm
0x14002bdc8  mov     rax, rsp
0x14002bdcb  mov     [rax+8], rbx
0x14002bdcf  mov     [rax+18h], rsi
0x14002bdd3  mov     [rax+20h], rdi
0x14002bdd7  push    rbp
0x14002bdd8  lea     rbp, [rax-5Fh]
0x14002bddc  sub     rsp, 90h
0x14002bde3  movups  xmm1, xmmword ptr [rdx]
0x14002bde6  xor     esi, esi
0x14002bde8  mov     [rsp+90h+OpenOptions], 4021h; OpenOptions
0x14002bdf0  mov     rdi, rcx
0x14002bdf3  mov     [rbp+57h+FileHandle], rsi
0x14002bdf7  movups  xmmword ptr [rbp+57h+var_60.Length], xmm1
0x14002bdfb  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14002bdff  mov     ecx, 0FFF2h
0x14002be04  lea     edx, [rsi+0Eh]
0x14002be07  movd    eax, xmm1
0x14002be0b  add     [rbp+57h+var_60.MaximumLength], cx
0x14002be0f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002be13  add     [rbp+57h+var_60.Buffer], rdx
0x14002be17  xorps   xmm0, xmm0
0x14002be1a  add     ax, cx
0x14002be1d  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002be25  mov     [rbp+57h+var_60.Length], ax
0x14002be29  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14002be2d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14002be31  lea     rax, [rbp+57h+var_50]
0x14002be35  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14002be3d  movdqu  [rbp+57h+var_50], xmm1
0x14002be42  mov     word ptr [rbp+57h+var_50], dx
0x14002be46  mov     edx, 100001h; DesiredAccess
0x14002be4b  xorps   xmm0, xmm0
0x14002be4e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002be52  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14002be56  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002be5b  mov     [rsp+90h+ShareAccess], 3; ShareAccess
0x14002be63  call    cs:__imp_NtOpenFile
0x14002be6a  nop     dword ptr [rax+rax+00h]
0x14002be6f  mov     ebx, eax
0x14002be71  test    eax, eax
0x14002be73  jnz     short loc_14002BEA5
0x14002be75  cmp     [rbp+57h+var_60.Length], si
0x14002be79  jz      short loc_14002BE95
0x14002be7b  mov     r8, [rbp+57h+FileHandle]; void *
0x14002be7f  lea     rdx, [rbp+57h+var_60]; struct _UNICODE_STRING *
0x14002be83  xor     r9d, r9d; void **
0x14002be86  mov     qword ptr [rsp+90h+ShareAccess], rsi; unsigned __int8 *
0x14002be8b  mov     rcx, rdi; this
0x14002be8e  call    ?CreateLinkDirectories@DfsRootFolder@@AEAAJPEAU_UNICODE_STRING@@PEAXPEAPEAXPEAE@Z; DfsRootFolder::CreateLinkDirectories(_UNICODE_STRING *,void *,void * *,uchar *)
0x14002be93  mov     ebx, eax
0x14002be95  mov     rcx, [rbp+57h+FileHandle]; hObject
0x14002be99  call    cs:__imp_CloseHandle
0x14002bea0  nop     dword ptr [rax+rax+00h]
0x14002bea5  lea     r11, [rsp+90h+var_s0]
0x14002bead  mov     eax, ebx
0x14002beaf  mov     rbx, [r11+10h]
0x14002beb3  mov     rsi, [r11+20h]
0x14002beb7  mov     rdi, [r11+28h]
0x14002bebb  mov     rsp, r11
0x14002bebe  pop     rbp
0x14002bebf  retn
```
