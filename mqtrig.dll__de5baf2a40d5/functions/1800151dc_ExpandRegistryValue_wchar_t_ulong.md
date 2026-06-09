# ExpandRegistryValue(wchar_t *,ulong)

- ea: `0x1800151dc`
- end: `0x180015439`
- name: `?ExpandRegistryValue@@YAXPEA_WK@Z`
- size: `605`
- prototype: `void __fastcall(wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001557c`

## callees

- `0x180001ce6`
- `0x18000c654`
- `0x18000cd90`
- `0x18000d87c`
- `0x180014f54`
- `0x180014f98`
- `0x1800151dc`
- `0x18001e128`
- `0x18001e380`
- `0x18001e440`
- `0x180022010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180015343`
- `KERNEL32!GetLastError` at `0x180015368`
- `KERNEL32!GetLastError` at `0x1800153cf`
- `KERNEL32!GetLastError` at `0x180015343`
- `KERNEL32!GetLastError` at `0x180015368`
- `KERNEL32!GetLastError` at `0x1800153cf`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180015320`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180015320`

## pseudocode

```c
void __fastcall ExpandRegistryValue(wchar_t *a1, unsigned int a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v4; // r14
  wchar_t *v5; // rbx
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  void *v8; // rsp
  void *v9; // rsp
  wchar_t *v10; // rax
  int v11; // esi
  DWORD v12; // eax
  DWORD LastError; // eax
  signed int v14; // eax
  signed int v15; // eax
  __int64 v16; // [rsp+0h] [rbp-30h] BYREF
  int v17; // [rsp+30h] [rbp+0h] BYREF
  wchar_t *v18; // [rsp+38h] [rbp+8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+40h] [rbp+10h] BYREF

  v2 = a2;
  v18 = 0;
  v4 = 2LL * a2;
  if ( v4 > 0xFFFFFFFF )
  {
    v17 = -2147024362;
    throw (long *)&v17;
  }
  v5 = 0;
  if ( !(_DWORD)v4
    || (unsigned int)v4 > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)(unsigned int)v4 + g_ulAdditionalProbeSize + 8 < (unsigned int)v4
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_36;
  }
  v6 = (unsigned int)v4 + 23LL;
  if ( v6 <= (unsigned __int64)(unsigned int)v4 + 8 )
    v6 = 0xFFFFFFFFFFFFFF0LL;
  v7 = v6 & 0xFFFFFFFFFFFFFFF0uLL;
  v8 = alloca(v7);
  v9 = alloca(v7);
  v5 = (wchar_t *)&v17;
  if ( &v16 == (__int64 *)-48LL || (v17 = 1801679955, (v5 = (wchar_t *)&v18) == 0) )
  {
LABEL_36:
    if ( (unsigned __int64)(unsigned int)v4 + 8 >= (unsigned int)v4 )
    {
      v10 = (wchar_t *)((__int64 (*)(void))g_pfnAllocate)();
      v5 = v10;
      if ( v10 )
      {
        *(_DWORD *)v10 = 1885431112;
        v5 = v10 + 4;
      }
    }
  }
  v18 = v5;
  v11 = StringCchCopyW(v5, v2, a1);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_45b597e3d7703f55d09231576c0512fb_Traceguids,
        (unsigned int)v2);
    registry_access_error::registry_access_error((registry_access_error *)pExceptionObject, v11);
    throw (registry_access_error *)pExceptionObject;
  }
  v12 = ExpandEnvironmentStringsW(v5, a1, v2);
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids, LastError);
    }
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    registry_access_error::registry_access_error((registry_access_error *)pExceptionObject, v14);
    throw (registry_access_error *)pExceptionObject;
  }
  if ( (unsigned int)v2 < v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_45b597e3d7703f55d09231576c0512fb_Traceguids,
        (unsigned int)v2,
        v12);
    v15 = GetLastError();
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    registry_access_error::registry_access_error((registry_access_error *)pExceptionObject, v15);
    throw (registry_access_error *)pExceptionObject;
  }
  SP<wchar_t>::~SP<wchar_t>(&v18);
}

```

## disassembly

```asm
0x1800151dc  push    rbp
0x1800151de  push    rbx
0x1800151df  push    rsi
0x1800151e0  push    rdi
0x1800151e1  push    r12
0x1800151e3  push    r14
0x1800151e5  push    r15
0x1800151e7  sub     rsp, 70h
0x1800151eb  lea     rbp, [rsp+30h]
0x1800151f0  mov     rax, cs:__security_cookie
0x1800151f7  xor     rax, rbp
0x1800151fa  mov     [rbp+70h+var_40], rax
0x1800151fe  mov     edi, edx
0x180015200  mov     r12, rcx
0x180015203  mov     [rbp+70h+var_68], 0
0x18001520b  lea     r14, [rdi+rdi]
0x18001520f  mov     eax, 0FFFFFFFFh
0x180015214  cmp     r14, rax
0x180015217  ja      loc_180015421
0x18001521d  xor     ebx, ebx
0x18001521f  test    r14d, r14d
0x180015222  jz      short loc_180015288
0x180015224  mov     esi, r14d
0x180015227  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18001522e  ja      short loc_180015288
0x180015230  mov     rcx, cs:g_ulAdditionalProbeSize
0x180015237  add     rcx, 8
0x18001523b  add     rcx, rsi
0x18001523e  cmp     rcx, rsi
0x180015241  jb      short loc_180015288
0x180015243  call    VerifyStackAvailable
0x180015248  test    eax, eax
0x18001524a  jz      short loc_180015288
0x18001524c  lea     rax, [rsi+8]
0x180015250  lea     rcx, [rax+0Fh]
0x180015254  cmp     rcx, rax
0x180015257  ja      short loc_180015263
0x180015259  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180015263  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180015267  mov     rax, rcx
0x18001526a  call    _alloca_probe
0x18001526f  sub     rsp, rcx
0x180015272  lea     rbx, [rsp+0A0h+var_70]
0x180015277  test    rbx, rbx
0x18001527a  jz      short loc_180015288
0x18001527c  mov     dword ptr [rbx], 6B637453h
0x180015282  add     rbx, 8
0x180015286  jnz     short loc_1800152B2
0x180015288  mov     eax, r14d
0x18001528b  lea     rcx, [rax+8]
0x18001528f  cmp     rcx, rax
0x180015292  jb      short loc_1800152B2
0x180015294  mov     rax, cs:g_pfnAllocate
0x18001529b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152a0  mov     rbx, rax
0x1800152a3  test    rax, rax
0x1800152a6  jz      short loc_1800152B2
0x1800152a8  mov     dword ptr [rax], 70616548h
0x1800152ae  add     rbx, 8
0x1800152b2  mov     [rbp+70h+var_68], rbx
0x1800152b6  mov     r8, r12; wchar_t *
0x1800152b9  mov     rdx, rdi; unsigned __int64
0x1800152bc  mov     rcx, rbx; wchar_t *
0x1800152bf  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800152c4  mov     esi, eax
0x1800152c6  test    eax, eax
0x1800152c8  jns     short loc_180015317
0x1800152ca  lea     rdx, WPP_GLOBAL_Control
0x1800152d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152d8  cmp     rcx, rdx
0x1800152db  jz      short loc_1800152FB
0x1800152dd  test    byte ptr [rcx+1Ch], 1
0x1800152e1  jz      short loc_1800152FB
0x1800152e3  mov     edx, 0Ah
0x1800152e8  mov     r9d, edi
0x1800152eb  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x1800152f2  mov     rcx, [rcx+10h]
0x1800152f6  call    WPP_SF_d
0x1800152fb  mov     edx, esi; int
0x1800152fd  lea     rcx, [rbp+70h+pExceptionObject]; this
0x180015301  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x180015306  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x18001530d  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180015311  call    _CxxThrowException_0
0x180015317  mov     r8d, edi; nSize
0x18001531a  mov     rdx, r12; lpDst
0x18001531d  mov     rcx, rbx; lpSrc
0x180015320  call    cs:__imp_ExpandEnvironmentStringsW
0x180015326  test    eax, eax
0x180015328  jnz     short loc_180015396
0x18001532a  lea     rdx, WPP_GLOBAL_Control
0x180015331  mov     rax, cs:WPP_GLOBAL_Control
0x180015338  cmp     rax, rdx
0x18001533b  jz      short loc_180015368
0x18001533d  test    byte ptr [rax+1Ch], 1
0x180015341  jz      short loc_180015368
0x180015343  call    cs:__imp_GetLastError
0x180015349  mov     edx, 0Bh
0x18001534e  mov     r9d, eax
0x180015351  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x180015358  mov     rcx, cs:WPP_GLOBAL_Control
0x18001535f  mov     rcx, [rcx+10h]
0x180015363  call    WPP_SF_d
0x180015368  call    cs:__imp_GetLastError
0x18001536e  test    eax, eax
0x180015370  jle     short loc_18001537A
0x180015372  movzx   eax, ax
0x180015375  or      eax, 80070000h
0x18001537a  mov     edx, eax; int
0x18001537c  lea     rcx, [rbp+70h+pExceptionObject]; this
0x180015380  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x180015385  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x18001538c  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180015390  call    _CxxThrowException_0
0x180015396  cmp     edi, eax
0x180015398  jnb     short loc_1800153FD
0x18001539a  lea     rdx, WPP_GLOBAL_Control
0x1800153a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153a8  cmp     rcx, rdx
0x1800153ab  jz      short loc_1800153CF
0x1800153ad  test    byte ptr [rcx+1Ch], 1
0x1800153b1  jz      short loc_1800153CF
0x1800153b3  mov     edx, 0Ch
0x1800153b8  mov     [rsp+0A0h+var_80], eax
0x1800153bc  mov     r9d, edi
0x1800153bf  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x1800153c6  mov     rcx, [rcx+10h]
0x1800153ca  call    WPP_SF_dd
0x1800153cf  call    cs:__imp_GetLastError
0x1800153d5  test    eax, eax
0x1800153d7  jle     short loc_1800153E1
0x1800153d9  movzx   eax, ax
0x1800153dc  or      eax, 80070000h
0x1800153e1  mov     edx, eax; int
0x1800153e3  lea     rcx, [rbp+70h+pExceptionObject]; this
0x1800153e7  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x1800153ec  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x1800153f3  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x1800153f7  call    _CxxThrowException_0
0x1800153fd  lea     rcx, [rbp+70h+var_68]
0x180015401  call    ??1?$SP@_W@@QEAA@XZ; SP<wchar_t>::~SP<wchar_t>(void)
0x180015406  mov     rcx, [rbp+70h+var_40]
0x18001540a  xor     rcx, rbp; StackCookie
0x18001540d  call    __security_check_cookie
0x180015412  lea     rsp, [rbp+40h]
0x180015416  pop     r15
0x180015418  pop     r14
0x18001541a  pop     r12
0x18001541c  pop     rdi
0x18001541d  pop     rsi
0x18001541e  pop     rbx
0x18001541f  pop     rbp
0x180015420  retn
0x180015421  mov     [rbp+70h+var_70], 80070216h
0x180015428  lea     rdx, _TI1J; pThrowInfo
0x18001542f  lea     rcx, [rbp+70h+var_70]; pExceptionObject
0x180015433  call    _CxxThrowException_0
```
