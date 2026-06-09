# CRepositoryPackager::UnpackageRepository(ushort const *,ushort const *)

- ea: `0x18004025c`
- end: `0x180040374`
- name: `?UnpackageRepository@CRepositoryPackager@@QEAAJPEBG0@Z`
- size: `280`
- prototype: `__int64 __fastcall(CRepositoryPackager *__hidden this, LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800393e4`

## callees

- `0x1800012b8`
- `0x18003ee5c`
- `0x18003efb4`
- `0x18003fcac`
- `0x18004018c`
- `0x18004025c`
- `0x180044420`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180040305`
- `wbemcomn!GetMemLogObject` at `0x180040305`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040310`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040310`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800402bd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800402bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800402f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800402f6`

## pseudocode

```c
__int64 __fastcall CRepositoryPackager::UnpackageRepository(
        CRepositoryPackager *this,
        LPCWSTR lpFileName,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v5; // rdx
  CRepositoryPackager *v6; // rcx
  int RepositoryDirectory; // ebx
  HANDLE FileW; // rax
  void *v9; // rdi
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 v12[264]; // [rsp+40h] [rbp-228h] BYREF

  RepositoryDirectory = CRepositoryPackager::GetRepositoryDirectory(this, v12);
  if ( RepositoryDirectory < 0 )
    goto LABEL_7;
  FileW = CreateFileW(lpFileName, 0x80000000, 0, 0, 3u, 0x80u, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    RepositoryDirectory = -2147217400;
LABEL_7:
    CRepositoryPackager::DeleteRepository(v6, v5);
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, RepositoryDirectory);
    goto LABEL_8;
  }
  RepositoryDirectory = CRepositoryPackager::UnPackageHeader(v6, FileW);
  if ( RepositoryDirectory >= 0 )
    RepositoryDirectory = CRepositoryPackager::UnPackageContentsOfDirectory(this, v9, v12);
  CloseHandle(v9);
  if ( RepositoryDirectory < 0 )
    goto LABEL_7;
LABEL_8:
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids,
      (unsigned int)RepositoryDirectory);
  }
  return (unsigned int)RepositoryDirectory;
}

```

## disassembly

```asm
0x18004025c  mov     [rsp+arg_10], rbx
0x180040261  mov     [rsp+arg_18], rsi
0x180040266  push    rdi
0x180040267  sub     rsp, 260h
0x18004026e  mov     rax, cs:__security_cookie
0x180040275  xor     rax, rsp
0x180040278  mov     [rsp+268h+var_18], rax
0x180040280  mov     rdi, rdx
0x180040283  mov     rsi, rcx
0x180040286  lea     rdx, [rsp+268h+var_228]; unsigned __int16 *
0x18004028b  call    ?GetRepositoryDirectory@CRepositoryPackager@@AEAAJQEAG@Z; CRepositoryPackager::GetRepositoryDirectory(ushort * const)
0x180040290  mov     ebx, eax
0x180040292  test    eax, eax
0x180040294  js      short loc_180040300
0x180040296  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x18004029f  xor     r9d, r9d; lpSecurityAttributes
0x1800402a2  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800402aa  xor     r8d, r8d; dwShareMode
0x1800402ad  mov     edx, 80000000h; dwDesiredAccess
0x1800402b2  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x1800402ba  mov     rcx, rdi; lpFileName
0x1800402bd  call    cs:__imp_CreateFileW
0x1800402c3  mov     rdi, rax
0x1800402c6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800402ca  jnz     short loc_1800402D3
0x1800402cc  mov     ebx, 80041008h
0x1800402d1  jmp     short loc_180040300
0x1800402d3  mov     rdx, rdi; void *
0x1800402d6  call    ?UnPackageHeader@CRepositoryPackager@@AEAAJPEAX@Z; CRepositoryPackager::UnPackageHeader(void *)
0x1800402db  mov     ebx, eax
0x1800402dd  test    eax, eax
0x1800402df  js      short loc_1800402F3
0x1800402e1  lea     r8, [rsp+268h+var_228]; unsigned __int16 *
0x1800402e6  mov     rdx, rdi; void *
0x1800402e9  mov     rcx, rsi; this
0x1800402ec  call    ?UnPackageContentsOfDirectory@CRepositoryPackager@@AEAAJPEAXPEBG@Z; CRepositoryPackager::UnPackageContentsOfDirectory(void *,ushort const *)
0x1800402f1  mov     ebx, eax
0x1800402f3  mov     rcx, rdi; hObject
0x1800402f6  call    cs:__imp_CloseHandle
0x1800402fc  test    ebx, ebx
0x1800402fe  jns     short loc_180040316
0x180040300  call    ?DeleteRepository@CRepositoryPackager@@QEAAJPEBG@Z; CRepositoryPackager::DeleteRepository(ushort const *)
0x180040305  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004030b  mov     rcx, rax
0x18004030e  mov     edx, ebx
0x180040310  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180040316  mov     rcx, cs:WPP_GLOBAL_Control
0x18004031d  lea     rax, WPP_GLOBAL_Control
0x180040324  cmp     rcx, rax
0x180040327  jz      short loc_18004034D
0x180040329  test    byte ptr [rcx+1Ch], 1
0x18004032d  jz      short loc_18004034D
0x18004032f  cmp     byte ptr [rcx+19h], 2
0x180040333  jb      short loc_18004034D
0x180040335  mov     rcx, [rcx+10h]
0x180040339  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x180040340  mov     edx, 0Dh
0x180040345  mov     r9d, ebx
0x180040348  call    WPP_SF_d
0x18004034d  mov     eax, ebx
0x18004034f  mov     rcx, [rsp+268h+var_18]
0x180040357  xor     rcx, rsp; StackCookie
0x18004035a  call    __security_check_cookie
0x18004035f  lea     r11, [rsp+268h+var_8]
0x180040367  mov     rbx, [r11+20h]
0x18004036b  mov     rsi, [r11+28h]
0x18004036f  mov     rsp, r11
0x180040372  pop     rdi
0x180040373  retn
```
