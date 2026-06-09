# PerflibRename004File

- ea: `0x180011568`
- end: `0x180011732`
- name: `PerflibRename004File`
- size: `458`
- prototype: `void __fastcall(__int64, int, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180010f28`

## callees

- `0x180005da0`
- `0x180008050`
- `0x180011568`
- `0x180011738`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001170c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001170c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800116b0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800116b0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180011703`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180011703`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800116d8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800116d8`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18001168e`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18001168e`

## pseudocode

```c
void __fastcall PerflibRename004File(__int64 a1, int a2, __int64 a3, char a4)
{
  __int64 v7; // rax
  unsigned __int64 v8; // r12
  _QWORD *v9; // rbx
  unsigned __int16 *v10; // rsi
  __int64 v11; // rax
  unsigned __int16 *v12; // r13
  const wchar_t *v13; // rax
  const wchar_t *v14; // rdi
  const wchar_t *v15; // rax
  HANDLE FileW; // rax
  void *v17; // rdi

  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a1 + 2 * v7) );
  v8 = (unsigned int)(v7 + 19);
  v9 = 0;
  v10 = (unsigned __int16 *)operator new(saturated_mul(v8, 2u));
  if ( v10 )
  {
    v11 = operator new(2 * v8 + 24);
    v9 = (_QWORD *)v11;
    if ( v11 )
    {
      v12 = (unsigned __int16 *)(v11 + 20);
      if ( a2 == 4 )
      {
        v13 = L"perfh004.dat";
        v14 = L"perfc004.dat";
      }
      else
      {
        v14 = L"perfc016.dat";
        v13 = L"perfh016.dat";
      }
      if ( !a4 )
        v14 = v13;
      StringCchPrintfW(v10, v8, L"%ws\\%ws", a1, v14);
      if ( a3 )
      {
        v15 = L"prfc";
        if ( !a4 )
          v15 = L"prfh";
        StringCchPrintfW(v12, v8, L"%ws\\%ws%ws%ws", a1, v15, a3, L".dat");
        CopyFileExW(v10, v12, 0, 0, 0, 0);
      }
      else
      {
        StringCchPrintfW(v12, v8, L"%ws\\%ws.tmp", a1, v14);
        DeleteFileW(v12);
        FileW = CreateFileW(v10, 0x40010000u, 0, 0, 3u, 0, 0);
        v17 = FileW;
        if ( FileW != (HANDLE)-1LL )
        {
          *(_BYTE *)v9 = 0;
          v9[1] = 0;
          *((_DWORD *)v9 + 4) = v8;
          SetFileInformationByHandle(FileW, FileRenameInfo, v9, 2 * v8 + 24);
          CloseHandle(v17);
        }
      }
    }
  }
  operator delete(v9);
  operator delete(v10);
}

```

## disassembly

```asm
0x180011568  mov     [rsp+arg_10], r8
0x18001156d  push    rbx
0x18001156e  push    rbp
0x18001156f  push    rsi
0x180011570  push    rdi
0x180011571  push    r12
0x180011573  push    r13
0x180011575  push    r14
0x180011577  push    r15
0x180011579  sub     rsp, 48h
0x18001157d  mov     r14, rcx
0x180011580  mov     r15b, r9b
0x180011583  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180011587  mov     edi, edx
0x180011589  mov     rax, rcx
0x18001158c  xor     r13d, r13d
0x18001158f  inc     rax
0x180011592  cmp     [r14+rax*2], r13w
0x180011597  jnz     short loc_18001158F
0x180011599  lea     r12d, [rax+13h]
0x18001159d  mov     rbx, r13
0x1800115a0  mov     ebp, r12d
0x1800115a3  mov     eax, 2
0x1800115a8  mul     rbp
0x1800115ab  cmovb   rax, rcx
0x1800115af  mov     rcx, rax
0x1800115b2  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800115b7  mov     rsi, rax
0x1800115ba  test    rax, rax
0x1800115bd  jz      loc_180011712
0x1800115c3  lea     rcx, ds:18h[r12*2]
0x1800115cb  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800115d0  mov     rbx, rax
0x1800115d3  test    rax, rax
0x1800115d6  jz      loc_180011712
0x1800115dc  lea     r13, [rax+14h]
0x1800115e0  cmp     edi, 4
0x1800115e3  jnz     short loc_1800115F5
0x1800115e5  lea     rax, aPerfh004Dat; "perfh004.dat"
0x1800115ec  lea     rdi, aPerfc004Dat; "perfc004.dat"
0x1800115f3  jmp     short loc_180011603
0x1800115f5  lea     rdi, FileName; "perfc016.dat"
0x1800115fc  lea     rax, aPerfh016Dat; "perfh016.dat"
0x180011603  test    r15b, r15b
0x180011606  lea     r8, aWsWs; "%ws\\%ws"
0x18001160d  mov     r9, r14
0x180011610  mov     rdx, rbp; unsigned __int64
0x180011613  cmovz   rdi, rax
0x180011617  mov     rcx, rsi; unsigned __int16 *
0x18001161a  mov     [rsp+88h+pbCancel], rdi
0x18001161f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011624  mov     rcx, [rsp+88h+arg_10]
0x18001162c  mov     r9, r14
0x18001162f  test    rcx, rcx
0x180011632  jz      short loc_180011696
0x180011634  lea     rdx, aPrfh; "prfh"
0x18001163b  test    r15b, r15b
0x18001163e  lea     rax, aPrfc; "prfc"
0x180011645  cmovz   rax, rdx
0x180011649  lea     r8, aWsWsWsWs; "%ws\\%ws%ws%ws"
0x180011650  lea     rdx, aDat; ".dat"
0x180011657  mov     [rsp+88h+hTemplateFile], rdx
0x18001165c  mov     rdx, rbp; unsigned __int64
0x18001165f  mov     qword ptr [rsp+88h+dwCopyFlags], rcx
0x180011664  mov     rcx, r13; unsigned __int16 *
0x180011667  mov     [rsp+88h+pbCancel], rax
0x18001166c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011671  xor     r9d, r9d; lpData
0x180011674  mov     [rsp+88h+dwCopyFlags], 0; dwCopyFlags
0x18001167c  xor     r8d, r8d; lpProgressRoutine
0x18001167f  mov     [rsp+88h+pbCancel], 0; pbCancel
0x180011688  mov     rdx, r13; lpNewFileName
0x18001168b  mov     rcx, rsi; lpExistingFileName
0x18001168e  call    cs:__imp_CopyFileExW
0x180011694  jmp     short loc_180011712
0x180011696  lea     r8, aWsWsTmp; "%ws\\%ws.tmp"
0x18001169d  mov     [rsp+88h+pbCancel], rdi
0x1800116a2  mov     rdx, rbp; unsigned __int64
0x1800116a5  mov     rcx, r13; unsigned __int16 *
0x1800116a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800116ad  mov     rcx, r13; lpFileName
0x1800116b0  call    cs:__imp_DeleteFileW
0x1800116b6  xor     ebp, ebp
0x1800116b8  xor     r9d, r9d; lpSecurityAttributes
0x1800116bb  mov     [rsp+88h+hTemplateFile], rbp; hTemplateFile
0x1800116c0  xor     r8d, r8d; dwShareMode
0x1800116c3  mov     [rsp+88h+dwCopyFlags], ebp; dwFlagsAndAttributes
0x1800116c7  mov     edx, 40010000h; dwDesiredAccess
0x1800116cc  mov     rcx, rsi; lpFileName
0x1800116cf  lea     r14d, [rbp+3]
0x1800116d3  mov     dword ptr [rsp+88h+pbCancel], r14d; dwCreationDisposition
0x1800116d8  call    cs:__imp_CreateFileW
0x1800116de  mov     rdi, rax
0x1800116e1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800116e5  jz      short loc_180011712
0x1800116e7  lea     r9d, ds:18h[r12*2]; dwBufferSize
0x1800116ef  mov     [rbx], bpl
0x1800116f2  mov     r8, rbx; lpFileInformation
0x1800116f5  mov     [rbx+8], rbp
0x1800116f9  mov     edx, r14d; FileInformationClass
0x1800116fc  mov     [rbx+10h], r12d
0x180011700  mov     rcx, rax; hFile
0x180011703  call    cs:__imp_SetFileInformationByHandle
0x180011709  mov     rcx, rdi; hObject
0x18001170c  call    cs:__imp_CloseHandle
0x180011712  mov     rcx, rbx; Block
0x180011715  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001171a  mov     rcx, rsi; Block
0x18001171d  add     rsp, 48h
0x180011721  pop     r15
0x180011723  pop     r14
0x180011725  pop     r13
0x180011727  pop     r12
0x180011729  pop     rdi
0x18001172a  pop     rsi
0x18001172b  pop     rbp
0x18001172c  pop     rbx
0x18001172d  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
