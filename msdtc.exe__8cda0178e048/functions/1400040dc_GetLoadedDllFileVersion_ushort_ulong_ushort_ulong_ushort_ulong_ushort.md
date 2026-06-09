# GetLoadedDllFileVersion(ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *)

- ea: `0x1400040dc`
- end: `0x1400042c6`
- name: `?GetLoadedDllFileVersion@@YAXPEAGK0K0K0@Z`
- size: `490`
- prototype: `void __fastcall(unsigned __int16 *, __int64, unsigned __int16 *, __int64, unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400033b4`

## callees

- `0x140001f9c`
- `0x1400028f4`
- `0x1400040dc`
- `0x140006ee2`
- `0x140006f10`
- `0x140006fa0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140004175`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140004175`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140004160`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140004160`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x140004187`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x140004187`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004140`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004140`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1400041e8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14000423c`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1400041e8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14000423c`

## string_xrefs

- `0x140004132`: `comsvcs.dll`

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
            while ( *(_WORD *)lpBuffer != LOWORD(qword_140009080[2 * v18]) )
            {
              if ( ++v18 >= 0x27 )
                goto LABEL_13;
            }
            StringCchCopyW(a3, 5u, (const unsigned __int16 *)qword_140009080[2 * v18 + 1]);
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
0x1400040dc  push    rbp
0x1400040de  push    rbx
0x1400040df  push    rsi
0x1400040e0  push    rdi
0x1400040e1  sub     rsp, 68h
0x1400040e5  lea     rbp, [rsp+40h]
0x1400040ea  mov     rax, cs:__security_cookie
0x1400040f1  xor     rax, rbp
0x1400040f4  mov     [rbp+40h+var_28], rax
0x1400040f8  mov     rcx, [rbp+40h+arg_20]; unsigned __int16 *
0x1400040fc  xor     eax, eax
0x1400040fe  mov     rdi, r8
0x140004101  mov     [r8], ax
0x140004105  lea     r8, aNotLoaded; "not loaded"
0x14000410c  mov     [rbp+40h+lpBuffer], 0
0x140004114  mov     [rbp+40h+var_38], 0
0x14000411c  lea     edx, [rax+32h]; unsigned __int64
0x14000411f  mov     [rbp+40h+pBlock], 0
0x140004126  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000412b  mov     rsi, [rbp+40h+arg_30]
0x140004132  lea     rcx, ModuleName; "comsvcs.dll"
0x140004139  xor     r11d, r11d
0x14000413c  mov     [rsi], r11w
0x140004140  call    cs:__imp_GetModuleHandleW
0x140004146  mov     rbx, rax
0x140004149  test    rax, rax
0x14000414c  jz      loc_1400042B1
0x140004152  xor     r9d, r9d; wLanguage
0x140004155  mov     rcx, rax; hModule
0x140004158  lea     edx, [r9+10h]; lpType
0x14000415c  lea     r8d, [r9+1]; lpName
0x140004160  call    cs:__imp_FindResourceExW
0x140004166  test    rax, rax
0x140004169  jz      loc_1400042B1
0x14000416f  mov     rdx, rax; hResInfo
0x140004172  mov     rcx, rbx; hModule
0x140004175  call    cs:__imp_LoadResource
0x14000417b  test    rax, rax
0x14000417e  jz      loc_1400042B1
0x140004184  mov     rcx, rax; hResData
0x140004187  call    cs:__imp_LockResource
0x14000418d  mov     r9, rax
0x140004190  test    rax, rax
0x140004193  jz      loc_1400042B1
0x140004199  movzx   r8d, word ptr [rax]
0x14000419d  mov     ecx, r8d
0x1400041a0  shr     ecx, 1
0x1400041a2  add     ecx, r8d
0x1400041a5  mov     edx, ecx
0x1400041a7  lea     rax, [rcx+0Fh]
0x1400041ab  cmp     rax, rdx
0x1400041ae  ja      short loc_1400041BA
0x1400041b0  mov     rax, 0FFFFFFFFFFFFFF0h
0x1400041ba  and     rax, 0FFFFFFFFFFFFFFF0h
0x1400041be  call    _alloca_probe
0x1400041c3  sub     rsp, rax
0x1400041c6  mov     rdx, r9; Src
0x1400041c9  lea     rbx, [rsp+80h+pBlock]
0x1400041ce  mov     rcx, rbx; void *
0x1400041d1  call    memcpy_0
0x1400041d6  lea     r9, [rbp+40h+pBlock]; puLen
0x1400041da  mov     rcx, rbx; pBlock
0x1400041dd  lea     r8, [rbp+40h+lpBuffer]; lplpBuffer
0x1400041e1  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x1400041e8  call    cs:__imp_VerQueryValueW
0x1400041ee  test    eax, eax
0x1400041f0  jz      short loc_14000422A
0x1400041f2  mov     rax, [rbp+40h+lpBuffer]
0x1400041f6  xor     ecx, ecx
0x1400041f8  movzx   edx, word ptr [rax]
0x1400041fb  lea     rax, qword_140009080
0x140004202  mov     r8d, ecx
0x140004205  add     r8, r8
0x140004208  cmp     dx, [rax+r8*8]
0x14000420d  jz      short loc_140004218
0x14000420f  inc     ecx
0x140004211  cmp     ecx, 27h ; '''
0x140004214  jb      short loc_140004202
0x140004216  jmp     short loc_14000422A
0x140004218  mov     r8, [rax+r8*8+8]; unsigned __int16 *
0x14000421d  mov     edx, 5; unsigned __int64
0x140004222  mov     rcx, rdi; unsigned __int16 *
0x140004225  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000422a  lea     r9, [rbp+40h+pBlock]; puLen
0x14000422e  mov     rcx, rbx; pBlock
0x140004231  lea     r8, [rbp+40h+var_38]; lplpBuffer
0x140004235  lea     rdx, asc_140009CCC; "\\"
0x14000423c  call    cs:__imp_VerQueryValueW
0x140004242  test    eax, eax
0x140004244  jz      short loc_1400042B1
0x140004246  mov     r10, [rbp+40h+var_38]
0x14000424a  mov     r9d, [r10+8]
0x14000424e  cmp     r9d, 0FFFFFFFFh
0x140004252  jz      short loc_14000428D
0x140004254  movzx   r8d, word ptr [r10+0Eh]
0x140004259  mov     edx, 32h ; '2'; unsigned __int64
0x14000425e  movzx   eax, word ptr [r10+0Ch]
0x140004263  mov     rcx, [rbp+40h+arg_20]; unsigned __int16 *
0x140004267  mov     [rsp+80h+var_50], eax
0x14000426b  mov     [rsp+80h+var_58], r8d
0x140004270  lea     r8, aUUUU; "%u.%u.%u.%u"
0x140004277  movzx   r10d, r9w
0x14000427b  shr     r9d, 10h
0x14000427f  mov     [rsp+80h+var_60], r10d
0x140004284  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004289  mov     r10, [rbp+40h+var_38]
0x14000428d  test    byte ptr [r10+1Ch], 1
0x140004292  lea     rax, aShp; "shp"
0x140004299  lea     r8, aDbg; "dbg"
0x1400042a0  mov     edx, 5; unsigned __int64
0x1400042a5  cmovz   r8, rax; unsigned __int16 *
0x1400042a9  mov     rcx, rsi; unsigned __int16 *
0x1400042ac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400042b1  mov     rcx, [rbp+40h+var_28]
0x1400042b5  xor     rcx, rbp; StackCookie
0x1400042b8  call    __security_check_cookie
0x1400042bd  lea     rsp, [rbp+28h]
0x1400042c1  pop     rdi
0x1400042c2  pop     rsi
0x1400042c3  pop     rbx
0x1400042c4  pop     rbp
0x1400042c5  retn
```
