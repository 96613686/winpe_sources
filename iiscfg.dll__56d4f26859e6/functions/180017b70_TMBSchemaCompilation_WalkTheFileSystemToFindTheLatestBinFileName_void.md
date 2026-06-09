# TMBSchemaCompilation::WalkTheFileSystemToFindTheLatestBinFileName(void)

- ea: `0x180017b70`
- end: `0x180017d3c`
- name: `?WalkTheFileSystemToFindTheLatestBinFileName@TMBSchemaCompilation@@AEAAJXZ`
- size: `460`
- prototype: `__int64 __fastcall(TMBSchemaCompilation *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180017114`
- `0x180017964`

## callees

- `0x180005870`
- `0x180015e04`
- `0x180016a18`
- `0x1800176b8`
- `0x180017814`
- `0x180017b70`
- `0x18002e0ca`
- `0x18002e110`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180017c00`
- `msvcrt!wcscat_s` at `0x180017c00`
- `msvcrt!wcscpy_s` at `0x180017be9`
- `msvcrt!wcscpy_s` at `0x180017be9`
- `KERNEL32!FindClose` at `0x180017c31`
- `KERNEL32!FindClose` at `0x180017cde`
- `KERNEL32!FindClose` at `0x180017c31`
- `KERNEL32!FindClose` at `0x180017cde`
- `KERNEL32!FindNextFileW` at `0x180017c64`
- `KERNEL32!FindNextFileW` at `0x180017cd1`
- `KERNEL32!FindNextFileW` at `0x180017c64`
- `KERNEL32!FindNextFileW` at `0x180017cd1`
- `KERNEL32!FindFirstFileW` at `0x180017c20`
- `KERNEL32!FindFirstFileW` at `0x180017c20`
- `KERNEL32!DeleteFileW` at `0x180017cbc`
- `KERNEL32!DeleteFileW` at `0x180017cbc`
- `ole32!CoTaskMemAlloc` at `0x180017bbb`
- `ole32!CoTaskMemAlloc` at `0x180017bbb`

## pseudocode

```c
__int64 __fastcall TMBSchemaCompilation::WalkTheFileSystemToFindTheLatestBinFileName(TMBSchemaCompilation *this)
{
  wchar_t *v2; // rax
  wchar_t *v3; // rbx
  unsigned int v4; // ebx
  HANDLE FirstFileW; // r14
  __int64 v6; // rcx
  __int32 v7; // ebx
  void *v8; // rcx
  int v9; // esi
  int v10; // eax
  int v11; // ecx
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t *v14; // [rsp+28h] [rbp-D8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF

  v2 = (wchar_t *)CoTaskMemAlloc(saturated_mul(*((_QWORD *)this + 320), 2u));
  v3 = v2;
  v14 = v2;
  if ( v2 )
  {
    wcscpy_s(v2, *((_QWORD *)this + 320), *((const wchar_t **)this + 321));
    wcscat_s(v3, *((_QWORD *)this + 320), L"MBSchema.bin.????????h");
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(v3, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      v6 = -1;
LABEL_5:
      FindClose((HANDLE)v6);
      v4 = 0;
    }
    else
    {
      v13 = -1;
      while ( 1 )
      {
        TMBSchemaCompilation::BinFileToBinVersion(this, &v13, FindFileData.cFileName);
        v7 = v13;
        v8 = FirstFileW;
        if ( v13 != -1 )
          break;
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
        {
          v6 = (__int64)FirstFileW;
          goto LABEL_5;
        }
      }
      v9 = 1;
      while ( FindNextFileW(v8, &FindFileData) )
      {
        v13 = 0;
        if ( (int)TMBSchemaCompilation::BinFileToBinVersion(this, &v13, FindFileData.cFileName) >= 0 )
        {
          if ( v13 <= v7 )
          {
            if ( !DeleteFileW(FindFileData.cFileName) )
              v9 = 0;
          }
          else
          {
            v10 = TMBSchemaCompilation::DeleteBinFileVersion(this, v7);
            v11 = 0;
            if ( v10 )
              v11 = v9;
            v9 = v11;
            v7 = v13;
          }
        }
        v8 = FirstFileW;
      }
      FindClose(FirstFileW);
      if ( v9 && v7 && (int)TMBSchemaCompilation::RenameBinFileVersion(this, v7) >= 0 )
        v7 = 0;
      v4 = TMBSchemaCompilation::SetBinFileVersion(this, v7);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v14);
  return v4;
}

```

## disassembly

```asm
0x180017b70  mov     [rsp-8+arg_8], rbx
0x180017b75  mov     [rsp-8+arg_10], rsi
0x180017b7a  push    rbp
0x180017b7b  push    rdi
0x180017b7c  push    r14
0x180017b7e  lea     rbp, [rsp-190h]
0x180017b86  sub     rsp, 290h
0x180017b8d  mov     rax, cs:__security_cookie
0x180017b94  xor     rax, rsp
0x180017b97  mov     [rbp+1A0h+var_20], rax
0x180017b9e  mov     rdi, rcx
0x180017ba1  mov     eax, 2
0x180017ba6  mul     qword ptr [rcx+0A00h]
0x180017bad  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180017bb4  cmovb   rax, rsi
0x180017bb8  mov     rcx, rax; cb
0x180017bbb  call    cs:__imp_CoTaskMemAlloc
0x180017bc1  mov     rbx, rax
0x180017bc4  mov     [rsp+2A0h+var_278], rax
0x180017bc9  test    rax, rax
0x180017bcc  jnz     short loc_180017BD8
0x180017bce  mov     ebx, 8007000Eh
0x180017bd3  jmp     loc_180017D09
0x180017bd8  mov     r8, [rdi+0A08h]; Source
0x180017bdf  mov     rdx, [rdi+0A00h]; SizeInWords
0x180017be6  mov     rcx, rbx; Destination
0x180017be9  call    cs:__imp_wcscpy_s
0x180017bef  lea     r8, aMbschemaBinH; "MBSchema.bin.????????h"
0x180017bf6  mov     rdx, [rdi+0A00h]; SizeInWords
0x180017bfd  mov     rcx, rbx; Destination
0x180017c00  call    cs:__imp_wcscat_s
0x180017c06  xor     edx, edx; Val
0x180017c08  mov     r8d, 250h; Size
0x180017c0e  lea     rcx, [rsp+2A0h+FindFileData]; void *
0x180017c13  call    memset_0
0x180017c18  lea     rdx, [rsp+2A0h+FindFileData]; lpFindFileData
0x180017c1d  mov     rcx, rbx; lpFileName
0x180017c20  call    cs:__imp_FindFirstFileW
0x180017c26  mov     r14, rax
0x180017c29  cmp     rax, rsi
0x180017c2c  jnz     short loc_180017C3E
0x180017c2e  mov     rcx, rsi; hFindFile
0x180017c31  call    cs:__imp_FindClose
0x180017c37  xor     ebx, ebx
0x180017c39  jmp     loc_180017D09
0x180017c3e  mov     [rsp+2A0h+var_280], esi
0x180017c42  lea     r8, [rsp+2A0h+FindFileData.cFileName]; unsigned __int16 *
0x180017c47  lea     rdx, [rsp+2A0h+var_280]; int *
0x180017c4c  mov     rcx, rdi; this
0x180017c4f  call    ?BinFileToBinVersion@TMBSchemaCompilation@@AEBAJAEAJPEBG@Z; TMBSchemaCompilation::BinFileToBinVersion(long &,ushort const *)
0x180017c54  mov     ebx, [rsp+2A0h+var_280]
0x180017c58  lea     rdx, [rsp+2A0h+FindFileData]; lpFindFileData
0x180017c5d  mov     rcx, r14; hFindFile
0x180017c60  cmp     ebx, esi
0x180017c62  jnz     short loc_180017C73
0x180017c64  call    cs:__imp_FindNextFileW
0x180017c6a  test    eax, eax
0x180017c6c  jnz     short loc_180017C42
0x180017c6e  mov     rcx, r14
0x180017c71  jmp     short loc_180017C31
0x180017c73  mov     esi, 1
0x180017c78  jmp     short loc_180017CD1
0x180017c7a  mov     [rsp+2A0h+var_280], 0
0x180017c82  lea     r8, [rsp+2A0h+FindFileData.cFileName]; unsigned __int16 *
0x180017c87  lea     rdx, [rsp+2A0h+var_280]; int *
0x180017c8c  mov     rcx, rdi; this
0x180017c8f  call    ?BinFileToBinVersion@TMBSchemaCompilation@@AEBAJAEAJPEBG@Z; TMBSchemaCompilation::BinFileToBinVersion(long &,ushort const *)
0x180017c94  test    eax, eax
0x180017c96  js      short loc_180017CC9
0x180017c98  cmp     [rsp+2A0h+var_280], ebx
0x180017c9c  jle     short loc_180017CB7
0x180017c9e  mov     edx, ebx; int
0x180017ca0  mov     rcx, rdi; this
0x180017ca3  call    ?DeleteBinFileVersion@TMBSchemaCompilation@@AEAAJJ@Z; TMBSchemaCompilation::DeleteBinFileVersion(long)
0x180017ca8  xor     ecx, ecx
0x180017caa  test    eax, eax
0x180017cac  cmovnz  ecx, esi
0x180017caf  mov     esi, ecx
0x180017cb1  mov     ebx, [rsp+2A0h+var_280]
0x180017cb5  jmp     short loc_180017CC9
0x180017cb7  lea     rcx, [rsp+2A0h+FindFileData.cFileName]; lpFileName
0x180017cbc  call    cs:__imp_DeleteFileW
0x180017cc2  xor     ecx, ecx
0x180017cc4  test    eax, eax
0x180017cc6  cmovz   esi, ecx
0x180017cc9  lea     rdx, [rsp+2A0h+FindFileData]; lpFindFileData
0x180017cce  mov     rcx, r14; hFindFile
0x180017cd1  call    cs:__imp_FindNextFileW
0x180017cd7  test    eax, eax
0x180017cd9  jnz     short loc_180017C7A
0x180017cdb  mov     rcx, r14; hFindFile
0x180017cde  call    cs:__imp_FindClose
0x180017ce4  test    esi, esi
0x180017ce6  jz      short loc_180017CFD
0x180017ce8  test    ebx, ebx
0x180017cea  jz      short loc_180017CFD
0x180017cec  mov     edx, ebx; int
0x180017cee  mov     rcx, rdi; this
0x180017cf1  call    ?RenameBinFileVersion@TMBSchemaCompilation@@AEAAJJJ@Z; TMBSchemaCompilation::RenameBinFileVersion(long,long)
0x180017cf6  xor     edx, edx
0x180017cf8  test    eax, eax
0x180017cfa  cmovns  ebx, edx
0x180017cfd  mov     edx, ebx; int
0x180017cff  mov     rcx, rdi; this
0x180017d02  call    ?SetBinFileVersion@TMBSchemaCompilation@@AEAAJJ@Z; TMBSchemaCompilation::SetBinFileVersion(long)
0x180017d07  mov     ebx, eax
0x180017d09  lea     rcx, [rsp+2A0h+var_278]; void *
0x180017d0e  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x180017d13  mov     eax, ebx
0x180017d15  mov     rcx, [rbp+1A0h+var_20]
0x180017d1c  xor     rcx, rsp; StackCookie
0x180017d1f  call    __security_check_cookie
0x180017d24  lea     r11, [rsp+2A0h+var_10]
0x180017d2c  mov     rbx, [r11+28h]
0x180017d30  mov     rsi, [r11+30h]
0x180017d34  mov     rsp, r11
0x180017d37  pop     r14
0x180017d39  pop     rdi
0x180017d3a  pop     rbp
0x180017d3b  retn
```
