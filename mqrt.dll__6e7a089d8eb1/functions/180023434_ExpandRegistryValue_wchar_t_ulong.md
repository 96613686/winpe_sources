# ExpandRegistryValue(wchar_t *,ulong)

- ea: `0x180023434`
- end: `0x180023691`
- name: `?ExpandRegistryValue@@YAXPEA_WK@Z`
- size: `605`
- prototype: `void __fastcall(wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800237d4`

## callees

- `0x1800022d6`
- `0x180006fdc`
- `0x1800087f8`
- `0x180012e88`
- `0x1800232dc`
- `0x180023320`
- `0x180023434`
- `0x1800239f8`
- `0x180023ca0`
- `0x180023d60`
- `0x180026010`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x180023578`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180023578`
- `KERNEL32!GetLastError` at `0x18002359b`
- `KERNEL32!GetLastError` at `0x1800235c0`
- `KERNEL32!GetLastError` at `0x180023627`
- `KERNEL32!GetLastError` at `0x18002359b`
- `KERNEL32!GetLastError` at `0x1800235c0`
- `KERNEL32!GetLastError` at `0x180023627`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180023434  push    rbp
0x180023436  push    rbx
0x180023437  push    rsi
0x180023438  push    rdi
0x180023439  push    r12
0x18002343b  push    r14
0x18002343d  push    r15
0x18002343f  sub     rsp, 70h
0x180023443  lea     rbp, [rsp+30h]
0x180023448  mov     rax, cs:__security_cookie
0x18002344f  xor     rax, rbp
0x180023452  mov     [rbp+70h+var_40], rax
0x180023456  mov     edi, edx
0x180023458  mov     r12, rcx
0x18002345b  mov     [rbp+70h+var_68], 0
0x180023463  lea     r14, [rdi+rdi]
0x180023467  mov     eax, 0FFFFFFFFh
0x18002346c  cmp     r14, rax
0x18002346f  ja      loc_180023679
0x180023475  xor     ebx, ebx
0x180023477  test    r14d, r14d
0x18002347a  jz      short loc_1800234E0
0x18002347c  mov     esi, r14d
0x18002347f  cmp     rsi, cs:g_ulMaxStackAllocSize
0x180023486  ja      short loc_1800234E0
0x180023488  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002348f  add     rcx, 8
0x180023493  add     rcx, rsi
0x180023496  cmp     rcx, rsi
0x180023499  jb      short loc_1800234E0
0x18002349b  call    VerifyStackAvailable
0x1800234a0  test    eax, eax
0x1800234a2  jz      short loc_1800234E0
0x1800234a4  lea     rax, [rsi+8]
0x1800234a8  lea     rcx, [rax+0Fh]
0x1800234ac  cmp     rcx, rax
0x1800234af  ja      short loc_1800234BB
0x1800234b1  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800234bb  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800234bf  mov     rax, rcx
0x1800234c2  call    _alloca_probe
0x1800234c7  sub     rsp, rcx
0x1800234ca  lea     rbx, [rsp+0A0h+var_70]
0x1800234cf  test    rbx, rbx
0x1800234d2  jz      short loc_1800234E0
0x1800234d4  mov     dword ptr [rbx], 6B637453h
0x1800234da  add     rbx, 8
0x1800234de  jnz     short loc_18002350A
0x1800234e0  mov     eax, r14d
0x1800234e3  lea     rcx, [rax+8]
0x1800234e7  cmp     rcx, rax
0x1800234ea  jb      short loc_18002350A
0x1800234ec  mov     rax, cs:g_pfnAllocate
0x1800234f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234f8  mov     rbx, rax
0x1800234fb  test    rax, rax
0x1800234fe  jz      short loc_18002350A
0x180023500  mov     dword ptr [rax], 70616548h
0x180023506  add     rbx, 8
0x18002350a  mov     [rbp+70h+var_68], rbx
0x18002350e  mov     r8, r12; wchar_t *
0x180023511  mov     rdx, rdi; unsigned __int64
0x180023514  mov     rcx, rbx; wchar_t *
0x180023517  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002351c  mov     esi, eax
0x18002351e  test    eax, eax
0x180023520  jns     short loc_18002356F
0x180023522  lea     rdx, WPP_GLOBAL_Control
0x180023529  mov     rcx, cs:WPP_GLOBAL_Control
0x180023530  cmp     rcx, rdx
0x180023533  jz      short loc_180023553
0x180023535  test    byte ptr [rcx+1Ch], 1
0x180023539  jz      short loc_180023553
0x18002353b  mov     edx, 0Ah
0x180023540  mov     r9d, edi
0x180023543  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x18002354a  mov     rcx, [rcx+10h]
0x18002354e  call    WPP_SF_d
0x180023553  mov     edx, esi; int
0x180023555  lea     rcx, [rbp+70h+pExceptionObject]; this
0x180023559  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x18002355e  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x180023565  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180023569  call    _CxxThrowException_0
0x18002356f  mov     r8d, edi; nSize
0x180023572  mov     rdx, r12; lpDst
0x180023575  mov     rcx, rbx; lpSrc
0x180023578  call    cs:__imp_ExpandEnvironmentStringsW
0x18002357e  test    eax, eax
0x180023580  jnz     short loc_1800235EE
0x180023582  lea     rdx, WPP_GLOBAL_Control
0x180023589  mov     rax, cs:WPP_GLOBAL_Control
0x180023590  cmp     rax, rdx
0x180023593  jz      short loc_1800235C0
0x180023595  test    byte ptr [rax+1Ch], 1
0x180023599  jz      short loc_1800235C0
0x18002359b  call    cs:__imp_GetLastError
0x1800235a1  mov     edx, 0Bh
0x1800235a6  mov     r9d, eax
0x1800235a9  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x1800235b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235b7  mov     rcx, [rcx+10h]
0x1800235bb  call    WPP_SF_d
0x1800235c0  call    cs:__imp_GetLastError
0x1800235c6  test    eax, eax
0x1800235c8  jle     short loc_1800235D2
0x1800235ca  movzx   eax, ax
0x1800235cd  or      eax, 80070000h
0x1800235d2  mov     edx, eax; int
0x1800235d4  lea     rcx, [rbp+70h+pExceptionObject]; this
0x1800235d8  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x1800235dd  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x1800235e4  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x1800235e8  call    _CxxThrowException_0
0x1800235ee  cmp     edi, eax
0x1800235f0  jnb     short loc_180023655
0x1800235f2  lea     rdx, WPP_GLOBAL_Control
0x1800235f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180023600  cmp     rcx, rdx
0x180023603  jz      short loc_180023627
0x180023605  test    byte ptr [rcx+1Ch], 1
0x180023609  jz      short loc_180023627
0x18002360b  mov     edx, 0Ch
0x180023610  mov     [rsp+0A0h+var_80], eax
0x180023614  mov     r9d, edi
0x180023617  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x18002361e  mov     rcx, [rcx+10h]
0x180023622  call    WPP_SF_dd
0x180023627  call    cs:__imp_GetLastError
0x18002362d  test    eax, eax
0x18002362f  jle     short loc_180023639
0x180023631  movzx   eax, ax
0x180023634  or      eax, 80070000h
0x180023639  mov     edx, eax; int
0x18002363b  lea     rcx, [rbp+70h+pExceptionObject]; this
0x18002363f  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x180023644  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x18002364b  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x18002364f  call    _CxxThrowException_0
0x180023655  lea     rcx, [rbp+70h+var_68]
0x180023659  call    ??1?$SP@_W@@QEAA@XZ; SP<wchar_t>::~SP<wchar_t>(void)
0x18002365e  mov     rcx, [rbp+70h+var_40]
0x180023662  xor     rcx, rbp; StackCookie
0x180023665  call    __security_check_cookie
0x18002366a  lea     rsp, [rbp+40h]
0x18002366e  pop     r15
0x180023670  pop     r14
0x180023672  pop     r12
0x180023674  pop     rdi
0x180023675  pop     rsi
0x180023676  pop     rbx
0x180023677  pop     rbp
0x180023678  retn
0x180023679  mov     [rbp+70h+var_70], 80070216h
0x180023680  lea     rdx, _TI1J; pThrowInfo
0x180023687  lea     rcx, [rbp+70h+var_70]; pExceptionObject
0x18002368b  call    _CxxThrowException_0
```
