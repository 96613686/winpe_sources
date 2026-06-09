# CShareManager::GetScopingShare(ushort const *,ulong *,ushort * *,ushort * *)

- ea: `0x180010000`
- end: `0x180010351`
- name: `?GetScopingShare@CShareManager@@UEAAJPEBGPEAKPEAPEAG2@Z`
- size: `849`
- prototype: `int(CShareManager *__hidden this, const unsigned __int16 *, unsigned int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180010000`
- `0x1800104c0`
- `0x180010568`
- `0x180013220`
- `0x18001d18c`
- `0x1800254e0`
- `0x1800259bc`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010322`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010346`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010322`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010346`
- `SHCORE!SHStrDupW` at `0x1800102f8`
- `SHCORE!SHStrDupW` at `0x1800102f8`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800100e6`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18001021c`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800100e6`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18001021c`
- `SHLWAPI!PathAppendW` at `0x1800102e4`
- `SHLWAPI!PathAppendW` at `0x1800102e4`
- `SHLWAPI!PathFileExistsW` at `0x180010051`
- `SHLWAPI!PathFileExistsW` at `0x180010051`
- `SHLWAPI!PathIsDirectoryW` at `0x1800100d7`
- `SHLWAPI!PathIsDirectoryW` at `0x1800100d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShareManager::GetScopingShare(
        CShareManager *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 **a4,
        unsigned __int16 **ppwsz)
{
  unsigned int v9; // r12d
  __int64 v10; // rax
  const unsigned __int16 *v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // r8
  unsigned __int16 v14; // r9
  HRESULT v15; // ebx
  WCHAR *v16; // rcx
  __int64 v17; // rdi
  void *v18; // rbx
  int DPA; // esi
  _DWORD *v20; // rax
  int v21; // esi
  __int64 (__fastcall *v22)(__int64, __int64); // rbx
  __int64 v23; // rax
  __int64 v24; // r10
  __int64 v25; // r10
  unsigned __int16 *v26; // rax
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v28; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+48h] [rbp-B8h] BYREF
  int v31; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR psz[264]; // [rsp+260h] [rbp+160h] BYREF

  if ( a4 )
    *a4 = 0;
  *ppwsz = 0;
  if ( !PathFileExistsW(a2) )
    return 2147942487LL;
  if ( a3 )
    v9 = *a3;
  else
    v9 = 0x80000000;
  v10 = 2147483646;
  v11 = a2;
  v12 = 260;
  v13 = pszPath;
  do
  {
    if ( !v10 )
      break;
    v14 = *v11;
    if ( !*v11 )
      break;
    ++v11;
    *v13++ = v14;
    --v10;
    --v12;
  }
  while ( v12 );
  v15 = v12 == 0 ? 0x8007007A : 0;
  v16 = v13 - 1;
  if ( v12 )
    v16 = v13;
  *v16 = 0;
  if ( v12 )
  {
    v17 = 0;
    if ( !PathIsDirectoryW(pszPath) )
      PathRemoveFileSpecW(pszPath);
    while ( 1 )
    {
      v18 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
      pv = v18;
      if ( v18 )
      {
        *(_QWORD *)v18 = &CEnumShareInfo::`vftable';
        *((_QWORD *)v18 + 1) = 0;
        *((_DWORD *)v18 + 4) = 0;
        *((_DWORD *)v18 + 5) = 1;
        _InterlockedIncrement(&g_cRefThisDll);
        DPA = CEnumShareInfo::_CreateDPA((CEnumShareInfo *)v18);
        if ( DPA < 0
          || (DPA = CEnumShareInfo::_AddSMBShares((CEnumShareInfo *)v18, pszPath), DPA < 0)
          || (v20 = (_DWORD *)*((_QWORD *)v18 + 1)) != 0 && *v20 )
        {
          if ( DPA >= 0 )
          {
            v27 = 0;
            v30 = 0;
            v21 = 0;
            while ( !(*(unsigned int (__fastcall **)(void *, __int64, __int64 *, int *))(*(_QWORD *)v18 + 24LL))(
                       v18,
                       1,
                       &v27,
                       &v30) )
            {
              v31 = 0;
              if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v27 + 88LL))(v27, v9, &v31) )
              {
                v21 = 1;
                v17 = v27;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
              if ( v21 )
              {
                DPA = 0;
                goto LABEL_31;
              }
            }
            DPA = 1;
          }
        }
        else
        {
          DPA = -2147467259;
        }
LABEL_31:
        (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
        if ( !DPA )
          break;
      }
      if ( !PathRemoveFileSpecW(pszPath) )
        return (unsigned int)-2147467259;
    }
    v28 = 0;
    v22 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 80LL);
    v23 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v28);
    v15 = v22(v17, v23);
    if ( v15 >= 0 )
    {
      pv = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v17 + 32LL))(v17, &pv);
      if ( v15 >= 0 )
      {
        v24 = -1;
        do
          ++v24;
        while ( pszPath[v24] );
        v15 = StringCchCopyW(psz, 0x104u, (const unsigned __int16 *)pv);
        if ( v15 >= 0 )
        {
          if ( PathAppendW(psz, &a2[v25]) )
          {
            v15 = SHStrDupW(psz, ppwsz);
            if ( v15 >= 0 && a4 )
            {
              v26 = (unsigned __int16 *)v28;
              v28 = 0;
              *a4 = v26;
            }
          }
          else
          {
            v15 = -2147467259;
          }
        }
        CoTaskMemFree(pv);
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v28 )
      CoTaskMemFree(v28);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180010000  mov     [rsp-8+arg_0], rbx
0x180010005  push    rbp
0x180010006  push    rsi
0x180010007  push    rdi
0x180010008  push    r12
0x18001000a  push    r13
0x18001000c  push    r14
0x18001000e  push    r15
0x180010010  lea     rbp, [rsp-380h]
0x180010018  sub     rsp, 480h
0x18001001f  mov     rax, cs:__security_cookie
0x180010026  xor     rax, rsp
0x180010029  mov     [rbp+3B0h+var_40], rax
0x180010030  mov     r14, r9
0x180010033  mov     rbx, r8
0x180010036  mov     r15, rdx
0x180010039  mov     r13, [rbp+3B0h+ppwsz]
0x180010040  xor     esi, esi
0x180010042  test    r9, r9
0x180010045  jz      short loc_18001004A
0x180010047  mov     [r9], rsi
0x18001004a  mov     [r13+0], rsi
0x18001004e  mov     rcx, r15; pszPath
0x180010051  call    cs:__imp_PathFileExistsW
0x180010057  test    eax, eax
0x180010059  jnz     short loc_180010065
0x18001005b  mov     eax, 80070057h
0x180010060  jmp     loc_180010231
0x180010065  test    rbx, rbx
0x180010068  jz      short loc_18001006F
0x18001006a  mov     r12d, [rbx]
0x18001006d  jmp     short loc_180010075
0x18001006f  mov     r12d, 80000000h
0x180010075  mov     eax, 7FFFFFFEh
0x18001007a  mov     rcx, r15
0x18001007d  mov     edx, 104h
0x180010082  lea     r8, [rsp+4B0h+pszPath]
0x180010087  test    rax, rax
0x18001008a  jz      short loc_1800100AB
0x18001008c  movzx   r9d, word ptr [rcx]
0x180010090  test    r9w, r9w
0x180010094  jz      short loc_1800100AB
0x180010096  add     rcx, 2
0x18001009a  mov     [r8], r9w
0x18001009e  add     r8, 2
0x1800100a2  dec     rax
0x1800100a5  sub     rdx, 1
0x1800100a9  jnz     short loc_180010087
0x1800100ab  mov     rax, rdx
0x1800100ae  neg     rax
0x1800100b1  sbb     ebx, ebx
0x1800100b3  not     ebx
0x1800100b5  and     ebx, 8007007Ah
0x1800100bb  lea     rcx, [r8-2]
0x1800100bf  test    rdx, rdx
0x1800100c2  cmovnz  rcx, r8
0x1800100c6  mov     [rcx], si
0x1800100c9  jz      loc_18001022F
0x1800100cf  mov     rdi, rsi
0x1800100d2  lea     rcx, [rsp+4B0h+pszPath]; pszPath
0x1800100d7  call    cs:__imp_PathIsDirectoryW
0x1800100dd  test    eax, eax
0x1800100df  jnz     short loc_1800100EC
0x1800100e1  lea     rcx, [rsp+4B0h+pszPath]; pszPath
0x1800100e6  call    cs:__imp_PathRemoveFileSpecW
0x1800100ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800100f3  mov     ecx, 18h; unsigned __int64
0x1800100f8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800100fd  mov     rbx, rax
0x180010100  mov     [rsp+4B0h+pv], rax
0x180010105  test    rax, rax
0x180010108  jz      loc_180010217
0x18001010e  lea     rax, ??_7CEnumShareInfo@@6B@; const CEnumShareInfo::`vftable'
0x180010115  mov     [rbx], rax
0x180010118  mov     [rbx+8], rsi
0x18001011c  mov     [rbx+10h], esi
0x18001011f  mov     dword ptr [rbx+14h], 1
0x180010126  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18001012d  test    rbx, rbx
0x180010130  jz      loc_180010217
0x180010136  mov     rcx, rbx; this
0x180010139  call    ?_CreateDPA@CEnumShareInfo@@AEAAJXZ; CEnumShareInfo::_CreateDPA(void)
0x18001013e  mov     esi, eax
0x180010140  test    eax, eax
0x180010142  js      short loc_18001016F
0x180010144  lea     rdx, [rsp+4B0h+pszPath]; unsigned __int16 *
0x180010149  mov     rcx, rbx; this
0x18001014c  call    ?_AddSMBShares@CEnumShareInfo@@AEAAJPEBG@Z; CEnumShareInfo::_AddSMBShares(ushort const *)
0x180010151  mov     esi, eax
0x180010153  test    eax, eax
0x180010155  js      short loc_18001016F
0x180010157  mov     rax, [rbx+8]
0x18001015b  test    rax, rax
0x18001015e  jz      short loc_180010165
0x180010160  cmp     dword ptr [rax], 0
0x180010163  jnz     short loc_18001016F
0x180010165  mov     esi, 80004005h
0x18001016a  jmp     loc_180010202
0x18001016f  test    esi, esi
0x180010171  js      loc_180010202
0x180010177  mov     [rsp+4B0h+var_480], 0
0x180010180  mov     [rsp+4B0h+var_468], 0
0x180010188  xor     esi, esi
0x18001018a  mov     rax, [rbx]
0x18001018d  lea     r9, [rsp+4B0h+var_468]
0x180010192  lea     r8, [rsp+4B0h+var_480]
0x180010197  mov     edx, 1
0x18001019c  mov     rcx, rbx
0x18001019f  mov     rax, [rax+18h]
0x1800101a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101a8  test    eax, eax
0x1800101aa  jnz     short loc_1800101FD
0x1800101ac  mov     [rsp+4B0h+var_464], eax
0x1800101b0  mov     rcx, [rsp+4B0h+var_480]
0x1800101b5  mov     rax, [rcx]
0x1800101b8  lea     r8, [rsp+4B0h+var_464]
0x1800101bd  mov     edx, r12d
0x1800101c0  mov     rax, [rax+58h]
0x1800101c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101c9  test    eax, eax
0x1800101cb  jnz     short loc_1800101E4
0x1800101cd  lea     esi, [rax+1]
0x1800101d0  mov     rdi, [rsp+4B0h+var_480]
0x1800101d5  mov     rax, [rdi]
0x1800101d8  mov     rcx, rdi
0x1800101db  mov     rax, [rax+8]
0x1800101df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101e4  mov     rcx, [rsp+4B0h+var_480]
0x1800101e9  mov     rax, [rcx]
0x1800101ec  mov     rax, [rax+10h]
0x1800101f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101f5  test    esi, esi
0x1800101f7  jz      short loc_18001018A
0x1800101f9  xor     esi, esi
0x1800101fb  jmp     short loc_180010202
0x1800101fd  mov     esi, 1
0x180010202  mov     rax, [rbx]
0x180010205  mov     rcx, rbx
0x180010208  mov     rax, [rax+10h]
0x18001020c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010211  test    esi, esi
0x180010213  jz      short loc_18001025B
0x180010215  xor     esi, esi
0x180010217  lea     rcx, [rsp+4B0h+pszPath]; pszPath
0x18001021c  call    cs:__imp_PathRemoveFileSpecW
0x180010222  test    eax, eax
0x180010224  jnz     loc_1800100EC
0x18001022a  mov     ebx, 80004005h
0x18001022f  mov     eax, ebx
0x180010231  mov     rcx, [rbp+3B0h+var_40]
0x180010238  xor     rcx, rsp; StackCookie
0x18001023b  call    __security_check_cookie
0x180010240  mov     rbx, [rsp+4B0h+arg_0]
0x180010248  add     rsp, 480h
0x18001024f  pop     r15
0x180010251  pop     r14
0x180010253  pop     r13
0x180010255  pop     r12
0x180010257  pop     rdi
0x180010258  pop     rsi
0x180010259  pop     rbp
0x18001025a  retn
0x18001025b  xor     esi, esi
0x18001025d  mov     [rsp+4B0h+var_478], rsi
0x180010262  mov     rax, [rdi]
0x180010265  mov     rbx, [rax+50h]
0x180010269  lea     rcx, [rsp+4B0h+var_478]
0x18001026e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180010273  mov     rdx, rax
0x180010276  mov     rcx, rdi
0x180010279  mov     rax, rbx
0x18001027c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010281  mov     ebx, eax
0x180010283  test    eax, eax
0x180010285  js      loc_180010328
0x18001028b  mov     [rsp+4B0h+pv], rsi
0x180010290  mov     rax, [rdi]
0x180010293  lea     rdx, [rsp+4B0h+pv]
0x180010298  mov     rcx, rdi
0x18001029b  mov     rax, [rax+20h]
0x18001029f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102a4  mov     ebx, eax
0x1800102a6  test    eax, eax
0x1800102a8  js      short loc_180010328
0x1800102aa  lea     rax, [rsp+4B0h+pszPath]
0x1800102af  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800102b3  inc     r10
0x1800102b6  cmp     [rax+r10*2], si
0x1800102bb  jnz     short loc_1800102B3
0x1800102bd  mov     r8, [rsp+4B0h+pv]; unsigned __int16 *
0x1800102c2  mov     edx, 104h; unsigned __int64
0x1800102c7  lea     rcx, [rbp+3B0h+psz]; unsigned __int16 *
0x1800102ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800102d3  mov     ebx, eax
0x1800102d5  test    eax, eax
0x1800102d7  js      short loc_18001031D
0x1800102d9  lea     rdx, [r15+r10*2]; pszMore
0x1800102dd  lea     rcx, [rbp+3B0h+psz]; pszPath
0x1800102e4  call    cs:__imp_PathAppendW
0x1800102ea  test    eax, eax
0x1800102ec  jz      short loc_180010318
0x1800102ee  mov     rdx, r13; ppwsz
0x1800102f1  lea     rcx, [rbp+3B0h+psz]; psz
0x1800102f8  call    cs:__imp_SHStrDupW
0x1800102fe  mov     ebx, eax
0x180010300  test    eax, eax
0x180010302  js      short loc_18001031D
0x180010304  test    r14, r14
0x180010307  jz      short loc_18001031D
0x180010309  mov     rax, [rsp+4B0h+var_478]
0x18001030e  mov     [rsp+4B0h+var_478], rsi
0x180010313  mov     [r14], rax
0x180010316  jmp     short loc_18001031D
0x180010318  mov     ebx, 80004005h
0x18001031d  mov     rcx, [rsp+4B0h+pv]; pv
0x180010322  call    cs:__imp_CoTaskMemFree
0x180010328  mov     rax, [rdi]
0x18001032b  mov     rcx, rdi
0x18001032e  mov     rax, [rax+10h]
0x180010332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010337  nop
0x180010338  mov     rcx, [rsp+4B0h+var_478]; pv
0x18001033d  test    rcx, rcx
0x180010340  jz      loc_18001022F
0x180010346  call    cs:__imp_CoTaskMemFree
0x18001034c  jmp     loc_18001022F
```
