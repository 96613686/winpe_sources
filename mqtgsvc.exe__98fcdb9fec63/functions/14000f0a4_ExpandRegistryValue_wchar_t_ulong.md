# ExpandRegistryValue(wchar_t *,ulong)

- ea: `0x14000f0a4`
- end: `0x14000f301`
- name: `?ExpandRegistryValue@@YAXPEA_WK@Z`
- size: `605`
- prototype: `void __fastcall(wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x14000f444`

## callees

- `0x140001cc6`
- `0x1400038dc`
- `0x140004648`
- `0x140007554`
- `0x14000ee20`
- `0x14000ee64`
- `0x14000f0a4`
- `0x14001ccec`
- `0x14001cf00`
- `0x14001cfc0`
- `0x140020010`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000f1e8`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000f1e8`
- `KERNEL32!GetLastError` at `0x14000f20b`
- `KERNEL32!GetLastError` at `0x14000f230`
- `KERNEL32!GetLastError` at `0x14000f297`
- `KERNEL32!GetLastError` at `0x14000f20b`
- `KERNEL32!GetLastError` at `0x14000f230`
- `KERNEL32!GetLastError` at `0x14000f297`

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
  signed int LastError; // eax
  signed int v14; // eax
  __int64 v15; // [rsp+0h] [rbp-30h] BYREF
  int v16; // [rsp+30h] [rbp+0h] BYREF
  wchar_t *v17; // [rsp+38h] [rbp+8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+40h] [rbp+10h] BYREF

  v2 = a2;
  v17 = 0;
  v4 = 2LL * a2;
  if ( v4 > 0xFFFFFFFF )
  {
    v16 = -2147024362;
    throw (long *)&v16;
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
  v5 = (wchar_t *)&v16;
  if ( &v15 == (__int64 *)-48LL || (v16 = 1801679955, (v5 = (wchar_t *)&v17) == 0) )
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
  v17 = v5;
  v11 = StringCchCopyW(v5, v2, a1);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids);
    registry_access_error::registry_access_error((registry_access_error *)pExceptionObject, v11);
    throw (registry_access_error *)pExceptionObject;
  }
  v12 = ExpandEnvironmentStringsW(v5, a1, v2);
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids);
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    registry_access_error::registry_access_error((registry_access_error *)pExceptionObject, LastError);
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
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    registry_access_error::registry_access_error((registry_access_error *)pExceptionObject, v14);
    throw (registry_access_error *)pExceptionObject;
  }
  SP<wchar_t>::~SP<wchar_t>(&v17);
}

```

## disassembly

```asm
0x14000f0a4  push    rbp
0x14000f0a6  push    rbx
0x14000f0a7  push    rsi
0x14000f0a8  push    rdi
0x14000f0a9  push    r12
0x14000f0ab  push    r14
0x14000f0ad  push    r15
0x14000f0af  sub     rsp, 70h
0x14000f0b3  lea     rbp, [rsp+30h]
0x14000f0b8  mov     rax, cs:__security_cookie
0x14000f0bf  xor     rax, rbp
0x14000f0c2  mov     [rbp+70h+var_40], rax
0x14000f0c6  mov     edi, edx
0x14000f0c8  mov     r12, rcx
0x14000f0cb  mov     [rbp+70h+var_68], 0
0x14000f0d3  lea     r14, [rdi+rdi]
0x14000f0d7  mov     eax, 0FFFFFFFFh
0x14000f0dc  cmp     r14, rax
0x14000f0df  ja      loc_14000F2E9
0x14000f0e5  xor     ebx, ebx
0x14000f0e7  test    r14d, r14d
0x14000f0ea  jz      short loc_14000F150
0x14000f0ec  mov     esi, r14d
0x14000f0ef  cmp     rsi, cs:g_ulMaxStackAllocSize
0x14000f0f6  ja      short loc_14000F150
0x14000f0f8  mov     rcx, cs:g_ulAdditionalProbeSize
0x14000f0ff  add     rcx, 8
0x14000f103  add     rcx, rsi
0x14000f106  cmp     rcx, rsi
0x14000f109  jb      short loc_14000F150
0x14000f10b  call    VerifyStackAvailable
0x14000f110  test    eax, eax
0x14000f112  jz      short loc_14000F150
0x14000f114  lea     rax, [rsi+8]
0x14000f118  lea     rcx, [rax+0Fh]
0x14000f11c  cmp     rcx, rax
0x14000f11f  ja      short loc_14000F12B
0x14000f121  mov     rcx, 0FFFFFFFFFFFFFF0h
0x14000f12b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000f12f  mov     rax, rcx
0x14000f132  call    _alloca_probe
0x14000f137  sub     rsp, rcx
0x14000f13a  lea     rbx, [rsp+0A0h+var_70]
0x14000f13f  test    rbx, rbx
0x14000f142  jz      short loc_14000F150
0x14000f144  mov     dword ptr [rbx], 6B637453h
0x14000f14a  add     rbx, 8
0x14000f14e  jnz     short loc_14000F17A
0x14000f150  mov     eax, r14d
0x14000f153  lea     rcx, [rax+8]
0x14000f157  cmp     rcx, rax
0x14000f15a  jb      short loc_14000F17A
0x14000f15c  mov     rax, cs:g_pfnAllocate
0x14000f163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f168  mov     rbx, rax
0x14000f16b  test    rax, rax
0x14000f16e  jz      short loc_14000F17A
0x14000f170  mov     dword ptr [rax], 70616548h
0x14000f176  add     rbx, 8
0x14000f17a  mov     [rbp+70h+var_68], rbx
0x14000f17e  mov     r8, r12; wchar_t *
0x14000f181  mov     rdx, rdi; unsigned __int64
0x14000f184  mov     rcx, rbx; wchar_t *
0x14000f187  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000f18c  mov     esi, eax
0x14000f18e  test    eax, eax
0x14000f190  jns     short loc_14000F1DF
0x14000f192  lea     rdx, WPP_GLOBAL_Control
0x14000f199  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f1a0  cmp     rcx, rdx
0x14000f1a3  jz      short loc_14000F1C3
0x14000f1a5  test    byte ptr [rcx+1Ch], 1
0x14000f1a9  jz      short loc_14000F1C3
0x14000f1ab  mov     edx, 0Ah
0x14000f1b0  mov     r9d, edi
0x14000f1b3  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x14000f1ba  mov     rcx, [rcx+10h]
0x14000f1be  call    WPP_SF_d
0x14000f1c3  mov     edx, esi; int
0x14000f1c5  lea     rcx, [rbp+70h+pExceptionObject]; this
0x14000f1c9  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x14000f1ce  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x14000f1d5  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x14000f1d9  call    _CxxThrowException_0
0x14000f1df  mov     r8d, edi; nSize
0x14000f1e2  mov     rdx, r12; lpDst
0x14000f1e5  mov     rcx, rbx; lpSrc
0x14000f1e8  call    cs:__imp_ExpandEnvironmentStringsW
0x14000f1ee  test    eax, eax
0x14000f1f0  jnz     short loc_14000F25E
0x14000f1f2  lea     rdx, WPP_GLOBAL_Control
0x14000f1f9  mov     rax, cs:WPP_GLOBAL_Control
0x14000f200  cmp     rax, rdx
0x14000f203  jz      short loc_14000F230
0x14000f205  test    byte ptr [rax+1Ch], 1
0x14000f209  jz      short loc_14000F230
0x14000f20b  call    cs:__imp_GetLastError
0x14000f211  mov     edx, 0Bh
0x14000f216  mov     r9d, eax
0x14000f219  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x14000f220  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f227  mov     rcx, [rcx+10h]
0x14000f22b  call    WPP_SF_d
0x14000f230  call    cs:__imp_GetLastError
0x14000f236  test    eax, eax
0x14000f238  jle     short loc_14000F242
0x14000f23a  movzx   eax, ax
0x14000f23d  or      eax, 80070000h
0x14000f242  mov     edx, eax; int
0x14000f244  lea     rcx, [rbp+70h+pExceptionObject]; this
0x14000f248  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x14000f24d  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x14000f254  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x14000f258  call    _CxxThrowException_0
0x14000f25e  cmp     edi, eax
0x14000f260  jnb     short loc_14000F2C5
0x14000f262  lea     rdx, WPP_GLOBAL_Control
0x14000f269  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f270  cmp     rcx, rdx
0x14000f273  jz      short loc_14000F297
0x14000f275  test    byte ptr [rcx+1Ch], 1
0x14000f279  jz      short loc_14000F297
0x14000f27b  mov     edx, 0Ch
0x14000f280  mov     [rsp+0A0h+var_80], eax
0x14000f284  mov     r9d, edi
0x14000f287  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x14000f28e  mov     rcx, [rcx+10h]
0x14000f292  call    WPP_SF_dd
0x14000f297  call    cs:__imp_GetLastError
0x14000f29d  test    eax, eax
0x14000f29f  jle     short loc_14000F2A9
0x14000f2a1  movzx   eax, ax
0x14000f2a4  or      eax, 80070000h
0x14000f2a9  mov     edx, eax; int
0x14000f2ab  lea     rcx, [rbp+70h+pExceptionObject]; this
0x14000f2af  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x14000f2b4  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x14000f2bb  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x14000f2bf  call    _CxxThrowException_0
0x14000f2c5  lea     rcx, [rbp+70h+var_68]
0x14000f2c9  call    ??1?$SP@_W@@QEAA@XZ; SP<wchar_t>::~SP<wchar_t>(void)
0x14000f2ce  mov     rcx, [rbp+70h+var_40]
0x14000f2d2  xor     rcx, rbp; StackCookie
0x14000f2d5  call    __security_check_cookie
0x14000f2da  lea     rsp, [rbp+40h]
0x14000f2de  pop     r15
0x14000f2e0  pop     r14
0x14000f2e2  pop     r12
0x14000f2e4  pop     rdi
0x14000f2e5  pop     rsi
0x14000f2e6  pop     rbx
0x14000f2e7  pop     rbp
0x14000f2e8  retn
0x14000f2e9  mov     [rbp+70h+var_70], 80070216h
0x14000f2f0  lea     rdx, _TI1J; pThrowInfo
0x14000f2f7  lea     rcx, [rbp+70h+var_70]; pExceptionObject
0x14000f2fb  call    _CxxThrowException_0
```
