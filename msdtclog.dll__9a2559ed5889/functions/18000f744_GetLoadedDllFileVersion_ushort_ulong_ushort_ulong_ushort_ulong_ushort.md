# GetLoadedDllFileVersion(ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *)

- ea: `0x18000f744`
- end: `0x18000f92e`
- name: `?GetLoadedDllFileVersion@@YAXPEAGK0K0K0@Z`
- size: `490`
- prototype: `void __fastcall(unsigned __int16 *, __int64, unsigned __int16 *, __int64, unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ea1c`

## callees

- `0x18000ad1c`
- `0x18000e000`
- `0x18000f744`
- `0x1800127f2`
- `0x180012830`
- `0x1800128f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000f7dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000f7dd`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000f7c8`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000f7c8`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000f7ef`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000f7ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f7a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f7a8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000f850`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000f8a4`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000f850`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000f8a4`

## string_xrefs

- `0x18000f79a`: `comsvcs.dll`

## pseudocode

```c
void __fastcall GetLoadedDllFileVersion(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned __int16 *a7)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v9; // rbx
  HRSRC Resource; // rax
  HGLOBAL v11; // rax
  unsigned __int16 *v12; // rax
  const void *v13; // r9
  size_t v14; // r8
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  void *v17; // rsp
  unsigned int v18; // ecx
  _BYTE *v19; // r10
  unsigned int v20; // r9d
  const unsigned __int16 *v21; // r8
  unsigned int pBlock; // [rsp+40h] [rbp+0h] BYREF
  LPVOID v23; // [rsp+48h] [rbp+8h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp+10h] BYREF

  *a3 = 0;
  lpBuffer = 0;
  v23 = 0;
  pBlock = 0;
  StringCchCopyW(a5, 0x32u, L"not loaded");
  *a7 = 0;
  ModuleHandleW = GetModuleHandleW(L"comsvcs.dll");
  v9 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    Resource = FindResourceExW(ModuleHandleW, (LPCWSTR)0x10, (LPCWSTR)1, 0);
    if ( Resource )
    {
      v11 = LoadResource(v9, Resource);
      if ( v11 )
      {
        v12 = (unsigned __int16 *)LockResource(v11);
        v13 = v12;
        if ( v12 )
        {
          v14 = *v12;
          v15 = (unsigned int)v14 + (*v12 >> 1);
          v16 = v15 + 15;
          if ( v15 + 15 <= v15 )
            v16 = 0xFFFFFFFFFFFFFF0LL;
          v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
          memcpy_0(&pBlock, v13, v14);
          if ( VerQueryValueW(&pBlock, L"\\VarFileInfo\\Translation", &lpBuffer, &pBlock) )
          {
            v18 = 0;
            while ( *(_WORD *)lpBuffer != LOWORD(qword_180016300[2 * v18]) )
            {
              if ( ++v18 >= 0x27 )
                goto LABEL_13;
            }
            StringCchCopyW(a3, 5u, (const unsigned __int16 *)qword_180016300[2 * v18 + 1]);
          }
LABEL_13:
          if ( VerQueryValueW(&pBlock, L"\\", &v23, &pBlock) )
          {
            v19 = v23;
            v20 = *((_DWORD *)v23 + 2);
            if ( v20 != -1 )
            {
              StringCchPrintfW(
                a5,
                0x32u,
                L"%u.%u.%u.%u",
                HIWORD(v20),
                (unsigned __int16)v20,
                *((unsigned __int16 *)v23 + 7),
                *((unsigned __int16 *)v23 + 6));
              v19 = v23;
            }
            v21 = L"dbg";
            if ( (v19[28] & 1) == 0 )
              v21 = L"shp";
            StringCchCopyW(a7, 5u, v21);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000f744  push    rbp
0x18000f746  push    rbx
0x18000f747  push    rsi
0x18000f748  push    rdi
0x18000f749  sub     rsp, 68h
0x18000f74d  lea     rbp, [rsp+40h]
0x18000f752  mov     rax, cs:__security_cookie
0x18000f759  xor     rax, rbp
0x18000f75c  mov     [rbp+40h+var_28], rax
0x18000f760  mov     rcx, [rbp+40h+arg_20]; unsigned __int16 *
0x18000f764  xor     eax, eax
0x18000f766  mov     rdi, r8
0x18000f769  mov     [r8], ax
0x18000f76d  lea     r8, aNotLoaded; "not loaded"
0x18000f774  mov     [rbp+40h+lpBuffer], 0
0x18000f77c  mov     [rbp+40h+var_38], 0
0x18000f784  lea     edx, [rax+32h]; unsigned __int64
0x18000f787  mov     [rbp+40h+pBlock], 0
0x18000f78e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f793  mov     rsi, [rbp+40h+arg_30]
0x18000f79a  lea     rcx, aComsvcsDll; "comsvcs.dll"
0x18000f7a1  xor     r11d, r11d
0x18000f7a4  mov     [rsi], r11w
0x18000f7a8  call    cs:__imp_GetModuleHandleW
0x18000f7ae  mov     rbx, rax
0x18000f7b1  test    rax, rax
0x18000f7b4  jz      loc_18000F919
0x18000f7ba  xor     r9d, r9d; wLanguage
0x18000f7bd  mov     rcx, rax; hModule
0x18000f7c0  lea     edx, [r9+10h]; lpType
0x18000f7c4  lea     r8d, [r9+1]; lpName
0x18000f7c8  call    cs:__imp_FindResourceExW
0x18000f7ce  test    rax, rax
0x18000f7d1  jz      loc_18000F919
0x18000f7d7  mov     rdx, rax; hResInfo
0x18000f7da  mov     rcx, rbx; hModule
0x18000f7dd  call    cs:__imp_LoadResource
0x18000f7e3  test    rax, rax
0x18000f7e6  jz      loc_18000F919
0x18000f7ec  mov     rcx, rax; hResData
0x18000f7ef  call    cs:__imp_LockResource
0x18000f7f5  mov     r9, rax
0x18000f7f8  test    rax, rax
0x18000f7fb  jz      loc_18000F919
0x18000f801  movzx   r8d, word ptr [rax]
0x18000f805  mov     ecx, r8d
0x18000f808  shr     ecx, 1
0x18000f80a  add     ecx, r8d
0x18000f80d  mov     edx, ecx
0x18000f80f  lea     rax, [rcx+0Fh]
0x18000f813  cmp     rax, rdx
0x18000f816  ja      short loc_18000F822
0x18000f818  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000f822  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000f826  call    _alloca_probe
0x18000f82b  sub     rsp, rax
0x18000f82e  mov     rdx, r9; Src
0x18000f831  lea     rbx, [rsp+80h+pBlock]
0x18000f836  mov     rcx, rbx; void *
0x18000f839  call    memcpy_0
0x18000f83e  lea     r9, [rbp+40h+pBlock]; puLen
0x18000f842  mov     rcx, rbx; pBlock
0x18000f845  lea     r8, [rbp+40h+lpBuffer]; lplpBuffer
0x18000f849  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18000f850  call    cs:__imp_VerQueryValueW
0x18000f856  test    eax, eax
0x18000f858  jz      short loc_18000F892
0x18000f85a  mov     rax, [rbp+40h+lpBuffer]
0x18000f85e  xor     ecx, ecx
0x18000f860  movzx   edx, word ptr [rax]
0x18000f863  lea     rax, qword_180016300
0x18000f86a  mov     r8d, ecx
0x18000f86d  add     r8, r8
0x18000f870  cmp     dx, [rax+r8*8]
0x18000f875  jz      short loc_18000F880
0x18000f877  inc     ecx
0x18000f879  cmp     ecx, 27h ; '''
0x18000f87c  jb      short loc_18000F86A
0x18000f87e  jmp     short loc_18000F892
0x18000f880  mov     r8, [rax+r8*8+8]; unsigned __int16 *
0x18000f885  mov     edx, 5; unsigned __int64
0x18000f88a  mov     rcx, rdi; unsigned __int16 *
0x18000f88d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f892  lea     r9, [rbp+40h+pBlock]; puLen
0x18000f896  mov     rcx, rbx; pBlock
0x18000f899  lea     r8, [rbp+40h+var_38]; lplpBuffer
0x18000f89d  lea     rdx, asc_180018224; "\\"
0x18000f8a4  call    cs:__imp_VerQueryValueW
0x18000f8aa  test    eax, eax
0x18000f8ac  jz      short loc_18000F919
0x18000f8ae  mov     r10, [rbp+40h+var_38]
0x18000f8b2  mov     r9d, [r10+8]
0x18000f8b6  cmp     r9d, 0FFFFFFFFh
0x18000f8ba  jz      short loc_18000F8F5
0x18000f8bc  movzx   r8d, word ptr [r10+0Eh]
0x18000f8c1  mov     edx, 32h ; '2'; unsigned __int64
0x18000f8c6  movzx   eax, word ptr [r10+0Ch]
0x18000f8cb  mov     rcx, [rbp+40h+arg_20]; unsigned __int16 *
0x18000f8cf  mov     [rsp+80h+var_50], eax
0x18000f8d3  mov     [rsp+80h+var_58], r8d
0x18000f8d8  lea     r8, aUUUU; "%u.%u.%u.%u"
0x18000f8df  movzx   r10d, r9w
0x18000f8e3  shr     r9d, 10h
0x18000f8e7  mov     [rsp+80h+var_60], r10d
0x18000f8ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f8f1  mov     r10, [rbp+40h+var_38]
0x18000f8f5  test    byte ptr [r10+1Ch], 1
0x18000f8fa  lea     rax, aShp; "shp"
0x18000f901  lea     r8, aDbg; "dbg"
0x18000f908  mov     edx, 5; unsigned __int64
0x18000f90d  cmovz   r8, rax; unsigned __int16 *
0x18000f911  mov     rcx, rsi; unsigned __int16 *
0x18000f914  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f919  mov     rcx, [rbp+40h+var_28]
0x18000f91d  xor     rcx, rbp; StackCookie
0x18000f920  call    __security_check_cookie
0x18000f925  lea     rsp, [rbp+28h]
0x18000f929  pop     rdi
0x18000f92a  pop     rsi
0x18000f92b  pop     rbx
0x18000f92c  pop     rbp
0x18000f92d  retn
```
