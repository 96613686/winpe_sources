# NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)

- ea: `0x180016528`
- end: `0x1800166dc`
- name: `??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z`
- size: `436`
- prototype: `__int64 __fastcall(NgcUtils::RegKeyIterator *__hidden this, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016be4`
- `0x180017718`
- `0x180018898`

## callees

- `0x180003bc8`
- `0x180016238`
- `0x180016528`
- `0x18001ae30`
- `0x18001ae7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016589`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016576`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800165a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800165a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016581`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016581`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016624`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016624`

## string_xrefs

- `0x1800166b8`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x1800166ca`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
NgcUtils::RegKeyIterator *__fastcall NgcUtils::RegKeyIterator::RegKeyIterator(
        NgcUtils::RegKeyIterator *this,
        HKEY hKey,
        LPCWSTR lpSubKey)
{
  DWORD *v6; // r14
  struct _FILETIME *lpftLastWriteTime; // r15
  char *v8; // rdi
  HKEY v9; // rbp
  DWORD LastError; // ebx
  LSTATUS v11; // eax
  unsigned __int64 v12; // r9
  unsigned int v13; // eax
  unsigned __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rbp
  unsigned __int64 v17; // rcx
  __int64 v18; // rax
  size_t v19; // rbx
  int phkResult; // [rsp+20h] [rbp-78h]
  unsigned int phkResulta; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  DWORD cbMaxSubKeyLen; // [rsp+B8h] [rbp+20h] BYREF

  *(_QWORD *)this = 0;
  v6 = (DWORD *)((char *)this + 8);
  *((_DWORD *)this + 2) = 0;
  lpftLastWriteTime = (struct _FILETIME *)((char *)this + 12);
  *(_QWORD *)((char *)this + 12) = 0;
  v8 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v9 = *(HKEY *)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    RegCloseKey(v9);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  v11 = RegOpenKeyExW(hKey, lpSubKey, 0, 9u, (PHKEY)this);
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  else
    v12 = (unsigned int)v11;
  if ( (v11 & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)v12,
      phkResult);
  if ( !v11 )
  {
    cbMaxSubKeyLen = 0;
    v13 = RegQueryInfoKeyW(*(HKEY *)this, 0, 0, 0, v6, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, lpftLastWriteTime);
    if ( v13 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
        (const char *)v13,
        phkResulta);
    if ( *v6 )
    {
      v14 = cbMaxSubKeyLen + 1;
      v15 = *(_QWORD *)v8;
      v16 = *((_QWORD *)v8 + 1);
      v17 = (v16 - *(_QWORD *)v8) >> 1;
      if ( v14 < v17 )
      {
        v18 = v15 + 2LL * (cbMaxSubKeyLen + 1);
LABEL_16:
        *((_QWORD *)v8 + 1) = v18;
        return this;
      }
      if ( v14 > v17 )
      {
        if ( v14 <= (*((_QWORD *)v8 + 2) - v15) >> 1 )
        {
          v19 = 2 * (v14 - v17);
          memset_0(*((void **)v8 + 1), 0, v19);
          v18 = v19 + v16;
          goto LABEL_16;
        }
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(v8, cbMaxSubKeyLen + 1);
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180016528  mov     [rsp+arg_8], rbx
0x18001652d  mov     [rsp+arg_0], rcx
0x180016532  push    rbp
0x180016533  push    rsi
0x180016534  push    rdi
0x180016535  push    r12
0x180016537  push    r13
0x180016539  push    r14
0x18001653b  push    r15
0x18001653d  sub     rsp, 60h
0x180016541  mov     r12, r8
0x180016544  mov     r13, rdx
0x180016547  mov     rsi, rcx
0x18001654a  xor     ebx, ebx
0x18001654c  mov     [rcx], rbx
0x18001654f  lea     r14, [rcx+8]
0x180016553  mov     [r14], ebx
0x180016556  lea     r15, [rcx+0Ch]
0x18001655a  xor     eax, eax
0x18001655c  mov     [r15], rax
0x18001655f  lea     rdi, [rcx+18h]
0x180016563  mov     [rdi], rbx
0x180016566  mov     [rdi+8], rbx
0x18001656a  mov     [rdi+10h], rbx
0x18001656e  mov     rbp, [rcx]
0x180016571  test    rbp, rbp
0x180016574  jz      short loc_180016591
0x180016576  call    cs:__imp_GetLastError
0x18001657c  mov     ebx, eax
0x18001657e  mov     rcx, rbp; hKey
0x180016581  call    cs:__imp_RegCloseKey
0x180016587  mov     ecx, ebx; dwErrCode
0x180016589  call    cs:__imp_SetLastError
0x18001658f  xor     ebx, ebx
0x180016591  mov     [rsi], rbx
0x180016594  mov     [rsp+98h+phkResult], rsi; int
0x180016599  mov     r9d, 9; samDesired
0x18001659f  xor     r8d, r8d; ulOptions
0x1800165a2  mov     rdx, r12; lpSubKey
0x1800165a5  mov     rcx, r13; hKey
0x1800165a8  call    cs:__imp_RegOpenKeyExW
0x1800165ae  test    eax, 0FFFFFFFDh
0x1800165b3  setnz   dl
0x1800165b6  test    eax, eax
0x1800165b8  jg      short loc_1800165BF
0x1800165ba  mov     r9d, eax
0x1800165bd  jmp     short loc_1800165CA
0x1800165bf  movzx   r9d, ax
0x1800165c3  or      r9d, 80070000h; char *
0x1800165ca  mov     rcx, [rsp+98h]; this
0x1800165d2  test    dl, dl
0x1800165d4  jnz     loc_1800166CA
0x1800165da  test    eax, eax
0x1800165dc  jnz     loc_18001669A
0x1800165e2  mov     [rsp+98h+cbMaxSubKeyLen], ebx
0x1800165e9  mov     [rsp+98h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800165ee  mov     [rsp+98h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x1800165f3  mov     [rsp+98h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x1800165f8  mov     [rsp+98h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x1800165fd  mov     [rsp+98h+lpcValues], rbx; lpcValues
0x180016602  mov     [rsp+98h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x180016607  lea     rax, [rsp+98h+cbMaxSubKeyLen]
0x18001660f  mov     [rsp+98h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180016614  mov     [rsp+98h+phkResult], r14; unsigned int
0x180016619  xor     r9d, r9d; lpReserved
0x18001661c  xor     r8d, r8d; lpcchClass
0x18001661f  xor     edx, edx; lpClass
0x180016621  mov     rcx, [rsi]; hKey
0x180016624  call    cs:__imp_RegQueryInfoKeyW
0x18001662a  mov     rcx, [rsp+98h]; this
0x180016632  test    eax, eax
0x180016634  jnz     short loc_1800166B5
0x180016636  cmp     [r14], ebx
0x180016639  jbe     short loc_18001669A
0x18001663b  mov     eax, [rsp+98h+cbMaxSubKeyLen]
0x180016642  inc     eax
0x180016644  mov     ebx, eax
0x180016646  mov     rdx, [rdi]
0x180016649  mov     rbp, [rdi+8]
0x18001664d  mov     rcx, rbp
0x180016650  sub     rcx, rdx
0x180016653  sar     rcx, 1
0x180016656  cmp     rbx, rcx
0x180016659  jnb     short loc_180016661
0x18001665b  lea     rax, [rdx+rax*2]
0x18001665f  jmp     short loc_180016696
0x180016661  jbe     short loc_18001669A
0x180016663  mov     rax, [rdi+10h]
0x180016667  sub     rax, rdx
0x18001666a  sar     rax, 1
0x18001666d  cmp     rbx, rax
0x180016670  jbe     short loc_18001667F
0x180016672  mov     rdx, rbx
0x180016675  mov     rcx, rdi
0x180016678  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001667d  jmp     short loc_18001669A
0x18001667f  sub     rbx, rcx
0x180016682  add     rbx, rbx
0x180016685  mov     r8, rbx; Size
0x180016688  xor     edx, edx; Val
0x18001668a  mov     rcx, rbp; void *
0x18001668d  call    memset_0
0x180016692  lea     rax, [rbx+rbp]
0x180016696  mov     [rdi+8], rax
0x18001669a  mov     rax, rsi
0x18001669d  mov     rbx, [rsp+98h+arg_8]
0x1800166a5  add     rsp, 60h
0x1800166a9  pop     r15
0x1800166ab  pop     r14
0x1800166ad  pop     r13
0x1800166af  pop     r12
0x1800166b1  pop     rdi
0x1800166b2  pop     rsi
0x1800166b3  pop     rbp
0x1800166b4  retn
0x1800166b5  mov     r9d, eax; char *
0x1800166b8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800166bf  mov     edx, 32h ; '2'; void *
0x1800166c4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800166ca  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800166d1  mov     edx, 20h ; ' '; void *
0x1800166d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
