# DfsOpenDirectory(_UNICODE_STRING *,ulong,ulong,void *,void * *,uchar *)

- ea: `0x140025d40`
- end: `0x140025e56`
- name: `?DfsOpenDirectory@@YAJPEAU_UNICODE_STRING@@KKPEAXPEAPEAXPEAE@Z`
- size: `278`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, unsigned int, unsigned int, void *, PHANDLE FileHandle, unsigned __int8 *)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x140024f4c`
- `0x140025060`
- `0x1400291d0`
- `0x14002a25c`
- `0x14002a3f4`
- `0x14002ffe0`
- `0x140030784`
- `0x140031604`

## callees

- `0x14000fd24`
- `0x140025d40`

## import_xrefs

- `ntdll!NtCreateFile` at `0x140025dd4`
- `ntdll!NtCreateFile` at `0x140025dd4`

## pseudocode

```c
__int64 __fastcall DfsOpenDirectory(
        struct _UNICODE_STRING *a1,
        __int64 a2,
        int a3,
        void *a4,
        PHANDLE FileHandle,
        bool *a6)
{
  int v6; // edi
  unsigned int v7; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-38h] BYREF

  *(&ObjectAttributes.Length + 1) = 0;
  v6 = (int)a1;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.RootDirectory = a4;
  ObjectAttributes.ObjectName = a1;
  IoStatusBlock = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  v7 = NtCreateFile(
         FileHandle,
         a3 | 0x100180,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0x80u,
         7u,
         3u,
         (a3 & 0x10000 | 0x2040210u) >> 4,
         0,
         0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_ZD(*((_QWORD *)pWppControl + 2), 10, (unsigned int)WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids, v6, v7);
  }
  if ( !v7 && a6 )
    *a6 = IoStatusBlock.Information == 2;
  return v7;
}

```

## disassembly

```asm
0x140025d40  mov     rax, rsp
0x140025d43  mov     [rax+8], rbx
0x140025d47  push    rdi
0x140025d48  sub     rsp, 0A0h
0x140025d4f  and     [rsp+0A8h+var_58], 0
0x140025d54  xorps   xmm0, xmm0
0x140025d57  and     [rsp+0A8h+var_60], 0
0x140025d5d  mov     edx, r8d
0x140025d60  and     dword ptr [rax-34h], 0
0x140025d64  mov     rdi, rcx
0x140025d67  and     dword ptr [rax-1Ch], 0
0x140025d6b  or      edx, 100180h; DesiredAccess
0x140025d71  mov     [rax-30h], r9
0x140025d75  lea     r9, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x140025d7a  mov     [rax-28h], rcx
0x140025d7e  mov     rcx, [rsp+0A8h+FileHandle]; FileHandle
0x140025d86  movups  xmmword ptr [rax-48h], xmm0
0x140025d8a  mov     dword ptr [rax-38h], 30h ; '0'
0x140025d91  movdqu  xmmword ptr [rax-18h], xmm0
0x140025d96  mov     dword ptr [rax-20h], 40h ; '@'
0x140025d9d  mov     eax, r8d
0x140025da0  and     eax, 10000h
0x140025da5  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x140025daa  or      eax, 2040210h
0x140025daf  shr     eax, 4
0x140025db2  mov     [rsp+0A8h+CreateOptions], eax; CreateOptions
0x140025db6  mov     [rsp+0A8h+CreateDisposition], 3; CreateDisposition
0x140025dbe  mov     [rsp+0A8h+ShareAccess], 7; ShareAccess
0x140025dc6  mov     [rsp+0A8h+FileAttributes], 80h; FileAttributes
0x140025dce  and     [rsp+0A8h+var_88], 0
0x140025dd4  call    cs:__imp_NtCreateFile
0x140025ddb  nop     dword ptr [rax+rax+00h]
0x140025de0  mov     ebx, eax
0x140025de2  lea     rax, WPP_GLOBAL_Control
0x140025de9  cmp     cs:WPP_GLOBAL_Control, rax
0x140025df0  jz      short loc_140025E26
0x140025df2  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140025df9  test    rcx, rcx
0x140025dfc  jz      short loc_140025E26
0x140025dfe  test    byte ptr [rcx+1Ch], 20h
0x140025e02  jz      short loc_140025E26
0x140025e04  cmp     byte ptr [rcx+19h], 3
0x140025e08  jb      short loc_140025E26
0x140025e0a  mov     rcx, [rcx+10h]
0x140025e0e  lea     r8, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids
0x140025e15  mov     edx, 0Ah
0x140025e1a  mov     dword ptr [rsp+0A8h+var_88], ebx
0x140025e1e  mov     r9, rdi
0x140025e21  call    WPP_SF_ZD
0x140025e26  test    ebx, ebx
0x140025e28  jnz     short loc_140025E42
0x140025e2a  mov     rcx, [rsp+0A8h+arg_28]
0x140025e32  test    rcx, rcx
0x140025e35  jz      short loc_140025E42
0x140025e37  cmp     [rsp+0A8h+IoStatusBlock.Information], 2
0x140025e3d  setz    al
0x140025e40  mov     [rcx], al
0x140025e42  mov     eax, ebx
0x140025e44  mov     rbx, [rsp+0A8h+arg_0]
0x140025e4c  add     rsp, 0A0h
0x140025e53  pop     rdi
0x140025e54  retn
```
