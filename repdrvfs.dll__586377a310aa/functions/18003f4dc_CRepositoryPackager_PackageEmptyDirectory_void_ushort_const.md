# CRepositoryPackager::PackageEmptyDirectory(void *,ushort const *)

- ea: `0x18003f4dc`
- end: `0x18003f61b`
- name: `?PackageEmptyDirectory@CRepositoryPackager@@AEAAJPEAXPEBG@Z`
- size: `319`
- prototype: `int(CRepositoryPackager *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003edc4`

## callees

- `0x1800012b8`
- `0x180013880`
- `0x18003f4dc`
- `0x1800443df`
- `0x180044420`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003f5b1`
- `wbemcomn!GetMemLogObject` at `0x18003f5b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f5bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f5bc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f559`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f599`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f559`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f599`

## pseudocode

```c
__int64 __fastcall CRepositoryPackager::PackageEmptyDirectory(
        CRepositoryPackager *this,
        void *a2,
        const unsigned __int16 *a3)
{
  unsigned int v4; // ebx
  CMemoryLog *MemLogObject; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v8; // [rsp+34h] [rbp-CCh] BYREF
  int v9; // [rsp+38h] [rbp-C8h] BYREF
  int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v11[262]; // [rsp+44h] [rbp-BCh] BYREF

  memset_0(v11, 0, sizeof(v11));
  Buffer = 1;
  StringCchCopyW(v11, 0x105u, L".");
  NumberOfBytesWritten = 0;
  if ( !WriteFile(a2, &Buffer, 0x210u, &NumberOfBytesWritten, 0)
    || NumberOfBytesWritten != 528
    || (v9 = 2, v8 = 0, !WriteFile(a2, &v9, 4u, &v8, 0))
    || (v4 = 0, v8 != 4) )
  {
    v4 = -2147217407;
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217407);
  }
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18003f4dc  mov     [rsp-8+arg_0], rbx
0x18003f4e1  push    rbp
0x18003f4e2  lea     rbp, [rsp-160h]
0x18003f4ea  sub     rsp, 260h
0x18003f4f1  mov     rax, cs:__security_cookie
0x18003f4f8  xor     rax, rsp
0x18003f4fb  mov     [rbp+160h+var_10], rax
0x18003f502  mov     rbx, rdx
0x18003f505  lea     rcx, [rsp+260h+var_21C]; void *
0x18003f50a  xor     edx, edx; Val
0x18003f50c  mov     r8d, 20Ch; Size
0x18003f512  call    memset_0
0x18003f517  lea     r8, asc_18004D06C; "."
0x18003f51e  mov     [rsp+260h+Buffer], 1
0x18003f526  mov     edx, 105h; unsigned __int64
0x18003f52b  lea     rcx, [rsp+260h+var_21C]; unsigned __int16 *
0x18003f530  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f535  lea     r9, [rsp+260h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003f53a  mov     [rsp+260h+NumberOfBytesWritten], 0
0x18003f542  mov     r8d, 210h; nNumberOfBytesToWrite
0x18003f548  mov     [rsp+260h+lpOverlapped], 0; lpOverlapped
0x18003f551  lea     rdx, [rsp+260h+Buffer]; lpBuffer
0x18003f556  mov     rcx, rbx; hFile
0x18003f559  call    cs:__imp_WriteFile
0x18003f55f  test    eax, eax
0x18003f561  jz      short loc_18003F5AC
0x18003f563  cmp     [rsp+260h+NumberOfBytesWritten], 210h
0x18003f56b  jnz     short loc_18003F5AC
0x18003f56d  lea     r9, [rsp+260h+var_22C]; lpNumberOfBytesWritten
0x18003f572  mov     [rsp+260h+var_228], 2
0x18003f57a  mov     r8d, 4; nNumberOfBytesToWrite
0x18003f580  mov     [rsp+260h+var_22C], 0
0x18003f588  lea     rdx, [rsp+260h+var_228]; lpBuffer
0x18003f58d  mov     [rsp+260h+lpOverlapped], 0; lpOverlapped
0x18003f596  mov     rcx, rbx; hFile
0x18003f599  call    cs:__imp_WriteFile
0x18003f59f  test    eax, eax
0x18003f5a1  jz      short loc_18003F5AC
0x18003f5a3  xor     ebx, ebx
0x18003f5a5  cmp     [rsp+260h+var_22C], 4
0x18003f5aa  jz      short loc_18003F5C2
0x18003f5ac  mov     ebx, 80041001h
0x18003f5b1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003f5b7  mov     rcx, rax
0x18003f5ba  mov     edx, ebx
0x18003f5bc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f5c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f5c9  lea     rax, WPP_GLOBAL_Control
0x18003f5d0  cmp     rcx, rax
0x18003f5d3  jz      short loc_18003F5F9
0x18003f5d5  test    byte ptr [rcx+1Ch], 1
0x18003f5d9  jz      short loc_18003F5F9
0x18003f5db  cmp     byte ptr [rcx+19h], 2
0x18003f5df  jb      short loc_18003F5F9
0x18003f5e1  mov     rcx, [rcx+10h]
0x18003f5e5  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003f5ec  mov     edx, 0Bh
0x18003f5f1  mov     r9d, ebx
0x18003f5f4  call    WPP_SF_d
0x18003f5f9  mov     eax, ebx
0x18003f5fb  mov     rcx, [rbp+160h+var_10]
0x18003f602  xor     rcx, rsp; StackCookie
0x18003f605  call    __security_check_cookie
0x18003f60a  mov     rbx, [rsp+260h+arg_0]
0x18003f612  add     rsp, 260h
0x18003f619  pop     rbp
0x18003f61a  retn
```
