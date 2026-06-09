# FindShimInfoFromWin32(_GUID const &,int,ushort * *,ushort * *,ushort * *,ushort * *)

- ea: `0x18003fda8`
- end: `0x18003ffeb`
- name: `?FindShimInfoFromWin32@@YAJAEBU_GUID@@HPEAPEAG111@Z`
- size: `579`
- prototype: `__int64 __fastcall(const struct _GUID *, int, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180029774`

## callees

- `0x180003740`
- `0x180003840`
- `0x180007300`
- `0x18000b348`
- `0x18000c1a8`
- `0x18003fda8`
- `0x180041ac0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003fe4d`
- `KERNEL32!GetProcAddress` at `0x18003fe4d`
- `KERNEL32!GetLastError` at `0x18003fece`
- `KERNEL32!GetLastError` at `0x18003fece`
- `KERNEL32!LoadLibraryW` at `0x18003fe31`
- `KERNEL32!LoadLibraryW` at `0x18003fe31`

## string_xrefs

- `0x18003fe2a`: `sxs.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FindShimInfoFromWin32(
        const struct _GUID *a1,
        __int64 a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  int v5; // ebx
  HMODULE LibraryW; // rax
  _BYTE *v7; // r9
  __int64 v8; // r8
  __int64 v9; // r9
  _BYTE *v10; // r9
  _BYTE *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rax
  rsize_t v14; // r14
  unsigned __int128 v15; // rax
  unsigned __int64 v16; // kr00_8
  unsigned __int16 *v17; // rax
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v20; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE *v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h]
  __int64 v23; // [rsp+70h] [rbp-90h]
  _BYTE v24[520]; // [rsp+78h] [rbp-88h] BYREF

  v21 = 0;
  v22 = 0;
  v23 = 512;
  v19 = 0;
  v20 = (__int128)*a1;
  if ( !a3 )
  {
    v5 = -2147024809;
    goto LABEL_33;
  }
  *a3 = 0;
  if ( !g_fSxSInfoInitialized )
  {
    LibraryW = g_hmSxsDll;
    if ( g_hmSxsDll || (LibraryW = LoadLibraryW(L"sxs.dll"), (g_hmSxsDll = LibraryW) != 0) )
      g_pfnLookupGuid = (int (*)(unsigned int, struct _GUID *, void *, void *, unsigned __int64, unsigned __int64 *))GetProcAddress(LibraryW, "SxsLookupClrGuid");
    g_fSxSInfoInitialized = 1;
  }
  if ( g_pfnLookupGuid )
  {
    v5 = CQuickMemoryBase<512,128>::ReSizeNoThrow(&v21, 512, a3, a4);
    if ( v5 < 0 )
      goto LABEL_31;
    v7 = v24;
    if ( v21 )
      v7 = v21;
    if ( (unsigned int)((__int64 (__fastcall *)(__int64, __int128 *, __int64, _BYTE *, __int64, __int64 *))g_pfnLookupGuid)(
                         196608,
                         &v20,
                         -1,
                         v7,
                         v22,
                         &v19) )
      goto LABEL_18;
    if ( GetLastError() == 122 )
    {
      v5 = CQuickMemoryBase<512,128>::ReSizeNoThrow(&v21, v19, v8, v9);
      if ( v5 < 0 )
        goto LABEL_31;
      v10 = v24;
      if ( v21 )
        v10 = v21;
      if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, __int128 *, __int64, _BYTE *, __int64, __int64 *))g_pfnLookupGuid)(
                           0,
                           &v20,
                           -1,
                           v10,
                           v22,
                           &v19) )
      {
LABEL_18:
        v11 = v24;
        if ( v21 )
          v11 = v21;
        if ( *((_DWORD *)v11 + 1) != 1 )
        {
          v12 = *((_QWORD *)v11 + 1);
          if ( !v12 )
            goto LABEL_33;
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)(v12 + 2 * v13) );
          if ( v13 )
          {
            v14 = v13 + 1;
            v16 = v13 + 1;
            v15 = (unsigned __int64)(v13 + 1) * (unsigned __int128)2uLL;
            if ( !is_mul_ok(v16, 2u) )
              *(_QWORD *)&v15 = -1;
            v17 = (unsigned __int16 *)operator new(v15, *((const struct NoThrow **)&v15 + 1));
            *a3 = v17;
            if ( v17 )
            {
              wcscpy_s(v17, v14, *((const wchar_t **)v11 + 1));
              goto LABEL_33;
            }
            v5 = -2147024882;
            goto LABEL_31;
          }
        }
      }
    }
  }
  v5 = -2147467259;
LABEL_31:
  if ( *a3 )
  {
    operator delete(*a3);
    *a3 = 0;
  }
LABEL_33:
  CQuickArray<unsigned short>::~CQuickArray<unsigned short>(&v21);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003fda8  mov     [rsp-8+arg_8], rbx
0x18003fdad  mov     [rsp-8+arg_18], rsi
0x18003fdb2  push    rbp
0x18003fdb3  push    rdi
0x18003fdb4  push    r12
0x18003fdb6  push    r14
0x18003fdb8  push    r15
0x18003fdba  lea     rbp, [rsp-190h]
0x18003fdc2  sub     rsp, 290h
0x18003fdc9  mov     rax, cs:__security_cookie
0x18003fdd0  xor     rax, rsp
0x18003fdd3  mov     [rbp+1B0h+var_30], rax
0x18003fdda  mov     rsi, r8
0x18003fddd  xor     r15d, r15d
0x18003fde0  mov     [rsp+2B0h+var_250], r15
0x18003fde5  mov     [rsp+2B0h+var_248], r15
0x18003fdea  mov     ebx, 200h
0x18003fdef  mov     [rsp+2B0h+var_240], rbx
0x18003fdf4  mov     [rsp+2B0h+var_270], r15
0x18003fdf9  movups  xmm0, xmmword ptr [rcx]
0x18003fdfc  movdqu  [rsp+2B0h+var_268], xmm0
0x18003fe02  test    r8, r8
0x18003fe05  jnz     short loc_18003FE11
0x18003fe07  mov     ebx, 80070057h
0x18003fe0c  jmp     loc_18003FFB4
0x18003fe11  mov     [r8], r15
0x18003fe14  mov     eax, cs:?g_fSxSInfoInitialized@@3V?$Volatile@H@@A; Volatile<int> g_fSxSInfoInitialized
0x18003fe1a  test    eax, eax
0x18003fe1c  jnz     short loc_18003FE64
0x18003fe1e  mov     rax, cs:?g_hmSxsDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hmSxsDll
0x18003fe25  test    rax, rax
0x18003fe28  jnz     short loc_18003FE43
0x18003fe2a  lea     rcx, aSxsDll; "sxs.dll"
0x18003fe31  call    cs:__imp_LoadLibraryW
0x18003fe37  mov     cs:?g_hmSxsDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hmSxsDll
0x18003fe3e  test    rax, rax
0x18003fe41  jz      short loc_18003FE5A
0x18003fe43  lea     rdx, aSxslookupclrgu; "SxsLookupClrGuid"
0x18003fe4a  mov     rcx, rax; hModule
0x18003fe4d  call    cs:__imp_GetProcAddress
0x18003fe53  mov     cs:?g_pfnLookupGuid@@3P6AHKPEAU_GUID@@PEAX1_KPEA_K@ZEA, rax; int (*g_pfnLookupGuid)(ulong,_GUID *,void *,void *,unsigned __int64,unsigned __int64 *)
0x18003fe5a  mov     cs:?g_fSxSInfoInitialized@@3V?$Volatile@H@@A, 1; Volatile<int> g_fSxSInfoInitialized
0x18003fe64  cmp     cs:?g_pfnLookupGuid@@3P6AHKPEAU_GUID@@PEAX1_KPEA_K@ZEA, r15; int (*g_pfnLookupGuid)(ulong,_GUID *,void *,void *,unsigned __int64,unsigned __int64 *)
0x18003fe6b  jz      loc_18003FF9F
0x18003fe71  mov     rdx, rbx
0x18003fe74  lea     rcx, [rsp+2B0h+var_250]
0x18003fe79  call    ?ReSizeNoThrow@?$CQuickMemoryBase@$0CAA@$0IA@@@QEAAJ_K@Z; CQuickMemoryBase<512,128>::ReSizeNoThrow(unsigned __int64)
0x18003fe7e  mov     ebx, eax
0x18003fe80  test    eax, eax
0x18003fe82  js      loc_18003FFA4
0x18003fe88  mov     rdx, [rsp+2B0h+var_248]
0x18003fe8d  lea     r9, [rsp+2B0h+var_238]
0x18003fe92  mov     rcx, [rsp+2B0h+var_250]
0x18003fe97  test    rcx, rcx
0x18003fe9a  cmovnz  r9, rcx
0x18003fe9e  lea     rax, [rsp+2B0h+var_270]
0x18003fea3  mov     [rsp+2B0h+var_288], rax
0x18003fea8  mov     [rsp+2B0h+var_290], rdx
0x18003fead  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003feb1  mov     r8, r12
0x18003feb4  lea     rdx, [rsp+2B0h+var_268]
0x18003feb9  mov     ecx, 30000h
0x18003febe  mov     rax, cs:?g_pfnLookupGuid@@3P6AHKPEAU_GUID@@PEAX1_KPEA_K@ZEA; int (*g_pfnLookupGuid)(ulong,_GUID *,void *,void *,unsigned __int64,unsigned __int64 *)
0x18003fec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003feca  test    eax, eax
0x18003fecc  jnz     short loc_18003FF35
0x18003fece  call    cs:__imp_GetLastError
0x18003fed4  cmp     eax, 7Ah ; 'z'
0x18003fed7  jnz     loc_18003FF9F
0x18003fedd  mov     rdx, [rsp+2B0h+var_270]
0x18003fee2  lea     rcx, [rsp+2B0h+var_250]
0x18003fee7  call    ?ReSizeNoThrow@?$CQuickMemoryBase@$0CAA@$0IA@@@QEAAJ_K@Z; CQuickMemoryBase<512,128>::ReSizeNoThrow(unsigned __int64)
0x18003feec  mov     ebx, eax
0x18003feee  test    eax, eax
0x18003fef0  js      loc_18003FFA4
0x18003fef6  mov     rdx, [rsp+2B0h+var_248]
0x18003fefb  lea     r9, [rsp+2B0h+var_238]
0x18003ff00  mov     rcx, [rsp+2B0h+var_250]
0x18003ff05  test    rcx, rcx
0x18003ff08  cmovnz  r9, rcx
0x18003ff0c  lea     rax, [rsp+2B0h+var_270]
0x18003ff11  mov     [rsp+2B0h+var_288], rax
0x18003ff16  mov     [rsp+2B0h+var_290], rdx
0x18003ff1b  mov     r8, r12
0x18003ff1e  lea     rdx, [rsp+2B0h+var_268]
0x18003ff23  xor     ecx, ecx
0x18003ff25  mov     rax, cs:?g_pfnLookupGuid@@3P6AHKPEAU_GUID@@PEAX1_KPEA_K@ZEA; int (*g_pfnLookupGuid)(ulong,_GUID *,void *,void *,unsigned __int64,unsigned __int64 *)
0x18003ff2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff31  test    eax, eax
0x18003ff33  jz      short loc_18003FF9F
0x18003ff35  lea     rdi, [rsp+2B0h+var_238]
0x18003ff3a  mov     rax, [rsp+2B0h+var_250]
0x18003ff3f  test    rax, rax
0x18003ff42  cmovnz  rdi, rax
0x18003ff46  cmp     dword ptr [rdi+4], 1
0x18003ff4a  jz      short loc_18003FF9F
0x18003ff4c  mov     rcx, [rdi+8]
0x18003ff50  test    rcx, rcx
0x18003ff53  jz      short loc_18003FFB4
0x18003ff55  mov     rax, r12
0x18003ff58  inc     rax
0x18003ff5b  cmp     [rcx+rax*2], r15w
0x18003ff60  jnz     short loc_18003FF58
0x18003ff62  test    rax, rax
0x18003ff65  jz      short loc_18003FF9F
0x18003ff67  lea     r14, [rax+1]
0x18003ff6b  mov     eax, 2
0x18003ff70  mul     r14
0x18003ff73  cmovb   rax, r12
0x18003ff77  mov     rcx, rax; unsigned __int64
0x18003ff7a  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18003ff7f  mov     [rsi], rax
0x18003ff82  test    rax, rax
0x18003ff85  jnz     short loc_18003FF8E
0x18003ff87  mov     ebx, 8007000Eh
0x18003ff8c  jmp     short loc_18003FFA4
0x18003ff8e  mov     r8, [rdi+8]; Source
0x18003ff92  mov     rdx, r14; SizeInWords
0x18003ff95  mov     rcx, rax; Destination
0x18003ff98  call    wcscpy_s
0x18003ff9d  jmp     short loc_18003FFB4
0x18003ff9f  mov     ebx, 80004005h
0x18003ffa4  mov     rcx, [rsi]; void *
0x18003ffa7  test    rcx, rcx
0x18003ffaa  jz      short loc_18003FFB4
0x18003ffac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ffb1  mov     [rsi], r15
0x18003ffb4  lea     rcx, [rsp+2B0h+var_250]
0x18003ffb9  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x18003ffbe  mov     eax, ebx
0x18003ffc0  mov     rcx, [rbp+1B0h+var_30]
0x18003ffc7  xor     rcx, rsp; StackCookie
0x18003ffca  call    __security_check_cookie
0x18003ffcf  lea     r11, [rsp+2B0h+var_20]
0x18003ffd7  mov     rbx, [r11+38h]
0x18003ffdb  mov     rsi, [r11+48h]
0x18003ffdf  mov     rsp, r11
0x18003ffe2  pop     r15
0x18003ffe4  pop     r14
0x18003ffe6  pop     r12
0x18003ffe8  pop     rdi
0x18003ffe9  pop     rbp
0x18003ffea  retn
```
