# CFontManager::_ReportInvalidFontFile(HWND__ *,CFontAgent &,int)

- ea: `0x18001f0a0`
- end: `0x18001f2af`
- name: `?_ReportInvalidFontFile@CFontManager@@AEAAXPEAUHWND__@@AEAVCFontAgent@@H@Z`
- size: `527`
- prototype: `void __fastcall(CFontManager *__hidden this, HWND, struct CFontAgent *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d074`

## callees

- `0x18001e964`
- `0x18001f0a0`
- `0x18001f560`
- `0x18003104a`
- `0x180031070`
- `0x180031100`
- `0x180032010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18001f137`
- `SHLWAPI!PathFindExtensionW` at `0x18001f137`
- `SHLWAPI!PathStripPathW` at `0x18001f187`
- `SHLWAPI!PathStripPathW` at `0x18001f187`
- `SHLWAPI!PathCompactPathExW` at `0x18001f12d`
- `SHLWAPI!PathCompactPathExW` at `0x18001f12d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f159`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f159`

## pseudocode

```c
void __fastcall CFontManager::_ReportInvalidFontFile(CFontManager *this, HWND a2, struct CFontAgent *a3, int a4)
{
  const WCHAR *ExtensionW; // rax
  unsigned int v9; // esi
  CFontManager *v10; // rcx
  CFontManager *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rax
  unsigned int lpString2; // [rsp+20h] [rbp-E0h]
  unsigned int lpString2a; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v17[3]; // [rsp+34h] [rbp-CCh] BYREF
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  HWND v19; // [rsp+44h] [rbp-BCh]
  HINSTANCE v20; // [rsp+4Ch] [rbp-B4h]
  int v21; // [rsp+54h] [rbp-ACh]
  int v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+5Ch] [rbp-A4h]
  __int64 v24; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 *v25; // [rsp+6Ch] [rbp-94h]
  unsigned __int16 *v26; // [rsp+74h] [rbp-8Ch]
  int v27; // [rsp+88h] [rbp-78h]
  __int64 v28; // [rsp+9Ch] [rbp-64h]
  WCHAR pszSrc[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR pszOut[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v31[1024]; // [rsp+500h] [rbp+400h] BYREF
  unsigned __int16 v32[1024]; // [rsp+D00h] [rbp+C00h] BYREF

  memset_0(pszSrc, 0, 0x208u);
  memset_0(pszOut, 0, 0x208u);
  (*(void (__fastcall **)(struct CFontAgent *, WCHAR *, __int64))(*(_QWORD *)a3 + 104LL))(a3, pszSrc, 260);
  PathCompactPathExW(pszOut, pszSrc, 0x28u, 0);
  ExtensionW = PathFindExtensionW(pszSrc);
  if ( CompareStringW(0x7Fu, 1u, L".PFB", -1, ExtensionW, -1) == 2 )
  {
    v9 = 208;
    if ( *((_DWORD *)this + 8) )
      return;
  }
  else
  {
    v9 = 211;
    if ( *((_DWORD *)this + 7) )
      return;
  }
  PathStripPathW(pszSrc);
  if ( CFontManager::_GetFormattedString(v10, 0xCFu, pszSrc, v31, lpString2)
    && CFontManager::_GetFormattedString(v11, v9, pszOut, v32, lpString2a) )
  {
    memset_0(&v18, 0, 0xA0u);
    v20 = g_hInstance;
    v18 = 160;
    v27 = 8;
    v25 = v31;
    v21 = 8;
    v26 = v32;
    v13 = v28;
    if ( a4 )
      v13 = 8118;
    v19 = a2;
    v28 = v13;
    v22 = 32;
    v24 = 0xFFFF;
    v23 = 212;
    v16 = 0;
    v17[0] = 0;
    if ( (int)IsolationAwareTaskDialogIndirect(&v18, v17, v12, &v16) >= 0 && v16 && v17[0] != 2 )
    {
      if ( v9 == 208 )
        *((_DWORD *)this + 8) = 1;
      else
        *((_DWORD *)this + 7) = 1;
    }
  }
}

```

## disassembly

```asm
0x18001f0a0  mov     [rsp-8+arg_18], rbx
0x18001f0a5  push    rbp
0x18001f0a6  push    rsi
0x18001f0a7  push    rdi
0x18001f0a8  push    r14
0x18001f0aa  push    r15
0x18001f0ac  lea     rbp, [rsp-1410h]
0x18001f0b4  mov     eax, 1510h
0x18001f0b9  call    _alloca_probe
0x18001f0be  sub     rsp, rax
0x18001f0c1  mov     rax, cs:__security_cookie
0x18001f0c8  xor     rax, rsp
0x18001f0cb  mov     [rbp+1430h+var_30], rax
0x18001f0d2  mov     rbx, r8
0x18001f0d5  mov     r15, rdx
0x18001f0d8  mov     rdi, rcx
0x18001f0db  mov     esi, 208h
0x18001f0e0  mov     r8d, esi; Size
0x18001f0e3  lea     rcx, [rbp+1430h+pszSrc]; void *
0x18001f0e7  xor     edx, edx; Val
0x18001f0e9  mov     r14d, r9d
0x18001f0ec  call    memset_0
0x18001f0f1  mov     r8d, esi; Size
0x18001f0f4  lea     rcx, [rbp+1430h+pszOut]; void *
0x18001f0fb  xor     edx, edx; Val
0x18001f0fd  call    memset_0
0x18001f102  mov     rax, [rbx]
0x18001f105  lea     rdx, [rbp+1430h+pszSrc]
0x18001f109  mov     r8d, 104h
0x18001f10f  mov     rcx, rbx
0x18001f112  mov     rax, [rax+68h]
0x18001f116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f11b  xor     r9d, r9d; dwFlags
0x18001f11e  lea     rdx, [rbp+1430h+pszSrc]; pszSrc
0x18001f122  lea     rcx, [rbp+1430h+pszOut]; pszOut
0x18001f129  lea     r8d, [r9+28h]; cchMax
0x18001f12d  call    cs:__imp_PathCompactPathExW
0x18001f133  lea     rcx, [rbp+1430h+pszSrc]; pszPath
0x18001f137  call    cs:__imp_PathFindExtensionW
0x18001f13d  or      r9d, 0FFFFFFFFh; cchCount1
0x18001f141  lea     r8, pszExt; ".PFB"
0x18001f148  mov     [rsp+1530h+cchCount2], r9d; cchCount2
0x18001f14d  mov     [rsp+1530h+lpString2], rax; unsigned int
0x18001f152  lea     edx, [r9+2]; dwCmpFlags
0x18001f156  lea     ecx, [rdx+7Eh]; Locale
0x18001f159  call    cs:__imp_CompareStringW
0x18001f15f  xor     ebx, ebx
0x18001f161  cmp     eax, 2
0x18001f164  jnz     short loc_18001F175
0x18001f166  mov     esi, 0D0h
0x18001f16b  cmp     [rdi+20h], ebx
0x18001f16e  jz      short loc_18001F183
0x18001f170  jmp     loc_18001F289
0x18001f175  mov     esi, 0D3h
0x18001f17a  cmp     [rdi+1Ch], ebx
0x18001f17d  jnz     loc_18001F289
0x18001f183  lea     rcx, [rbp+1430h+pszSrc]; pszPath
0x18001f187  call    cs:__imp_PathStripPathW
0x18001f18d  lea     r9, [rbp+1430h+var_1030]; unsigned __int16 *
0x18001f194  mov     edx, 0CFh; unsigned int
0x18001f199  lea     r8, [rbp+1430h+pszSrc]; unsigned __int16 *
0x18001f19d  call    ?_GetFormattedString@CFontManager@@AEAAHKPEBGPEAGK@Z; CFontManager::_GetFormattedString(ulong,ushort const *,ushort *,ulong)
0x18001f1a2  test    eax, eax
0x18001f1a4  jz      loc_18001F289
0x18001f1aa  lea     r9, [rbp+1430h+var_830]; unsigned __int16 *
0x18001f1b1  mov     edx, esi; unsigned int
0x18001f1b3  lea     r8, [rbp+1430h+pszOut]; unsigned __int16 *
0x18001f1ba  call    ?_GetFormattedString@CFontManager@@AEAAHKPEBGPEAGK@Z; CFontManager::_GetFormattedString(ulong,ushort const *,ushort *,ulong)
0x18001f1bf  test    eax, eax
0x18001f1c1  jz      loc_18001F289
0x18001f1c7  xor     edx, edx; Val
0x18001f1c9  lea     rcx, [rsp+1530h+var_14F0]; void *
0x18001f1ce  mov     r8d, 0A0h; Size
0x18001f1d4  call    memset_0
0x18001f1d9  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18001f1e0  lea     r9, [rsp+1530h+var_1500]
0x18001f1e5  mov     [rsp+1530h+var_14E4], rax
0x18001f1ea  lea     rdx, [rsp+1530h+var_14FC]
0x18001f1ef  mov     ecx, 8
0x18001f1f4  mov     [rsp+1530h+var_14F0], 0A0h
0x18001f1fc  mov     [rbp+1430h+var_14A8], ecx
0x18001f1ff  lea     rax, [rbp+1430h+var_1030]
0x18001f206  mov     [rsp+1530h+var_14C4], rax
0x18001f20b  test    r14d, r14d
0x18001f20e  mov     [rsp+1530h+var_14DC], ecx
0x18001f212  lea     rax, [rbp+1430h+var_830]
0x18001f219  mov     [rsp+1530h+var_14BC], rax
0x18001f21e  mov     ecx, 1FB6h
0x18001f223  mov     rax, [rbp+1430h+var_1494]
0x18001f227  cmovnz  rax, rcx
0x18001f22b  mov     [rsp+1530h+var_14EC], r15
0x18001f230  lea     rcx, [rsp+1530h+var_14F0]
0x18001f235  mov     [rbp+1430h+var_1494], rax
0x18001f239  mov     [rsp+1530h+var_14D8], 20h ; ' '
0x18001f241  mov     [rsp+1530h+var_14CC], 0FFFFh
0x18001f24a  mov     [rsp+1530h+var_14D4], 0D4h
0x18001f253  mov     [rsp+1530h+var_1500], ebx
0x18001f257  mov     [rsp+1530h+var_14FC], ebx
0x18001f25b  call    IsolationAwareTaskDialogIndirect
0x18001f260  test    eax, eax
0x18001f262  js      short loc_18001F289
0x18001f264  cmp     [rsp+1530h+var_1500], ebx
0x18001f268  jz      short loc_18001F289
0x18001f26a  cmp     [rsp+1530h+var_14FC], 2
0x18001f26f  jz      short loc_18001F289
0x18001f271  cmp     esi, 0D0h
0x18001f277  jnz     short loc_18001F282
0x18001f279  mov     dword ptr [rdi+20h], 1
0x18001f280  jmp     short loc_18001F289
0x18001f282  mov     dword ptr [rdi+1Ch], 1
0x18001f289  mov     rcx, [rbp+1430h+var_30]
0x18001f290  xor     rcx, rsp; StackCookie
0x18001f293  call    __security_check_cookie
0x18001f298  mov     rbx, [rsp+1530h+arg_18]
0x18001f2a0  add     rsp, 1510h
0x18001f2a7  pop     r15
0x18001f2a9  pop     r14
0x18001f2ab  pop     rdi
0x18001f2ac  pop     rsi
0x18001f2ad  pop     rbp
0x18001f2ae  retn
```
