# KnownUicc::FromRegKey(HKEY__ *,ushort const *)

- ea: `0x180035074`
- end: `0x18003557d`
- name: `?FromRegKey@KnownUicc@@SA?AU1@PEAUHKEY__@@PEBG@Z`
- size: `1289`
- prototype: `_QWORD *__fastcall(_QWORD *, HKEY, char *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180034b9c`
- `0x180034fe0`

## callees

- `0x18000108c`
- `0x1800017c4`
- `0x18000e308`
- `0x180012390`
- `0x1800320e0`
- `0x180032f9c`
- `0x180033418`
- `0x180034914`
- `0x180034aec`
- `0x180035074`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800353ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800353f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800353ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800353f6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003514b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180035160`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180035408`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800354b7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003514b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180035160`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180035408`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800354b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003548d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003549e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003548d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003549e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180035258`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800352e8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180035324`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003537d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180035258`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800352e8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180035324`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003537d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035216`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003528c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035216`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003528c`

## pseudocode

```c
_QWORD *__fastcall KnownUicc::FromRegKey(_QWORD *a1, HKEY a2, char *a3)
{
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r8
  GUID *v8; // r9
  unsigned int v9; // eax
  unsigned int ValueW; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  char *v14; // rbx
  unsigned int v15; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-A9h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A9h]
  unsigned int phkResultb; // [rsp+20h] [rbp-A9h]
  unsigned int phkResultc; // [rsp+20h] [rbp-A9h]
  unsigned int phkResultd; // [rsp+20h] [rbp-A9h]
  unsigned int phkResulte; // [rsp+20h] [rbp-A9h]
  DWORD pcbData; // [rsp+40h] [rbp-89h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-81h] BYREF
  const WCHAR *v25; // [rsp+50h] [rbp-79h] BYREF
  int v26; // [rsp+58h] [rbp-71h]
  HKEY hKey; // [rsp+60h] [rbp-69h] BYREF
  PVOID Src[2]; // [rsp+68h] [rbp-61h] BYREF
  __int64 v29; // [rsp+78h] [rbp-51h]
  _QWORD *v30; // [rsp+80h] [rbp-49h]
  int v31; // [rsp+90h] [rbp-39h]
  char v32; // [rsp+94h] [rbp-35h]
  GUID ActivityId; // [rsp+98h] [rbp-31h] BYREF
  GUID v34; // [rsp+A8h] [rbp-21h] BYREF
  void *v35[3]; // [rsp+B8h] [rbp-11h] BYREF
  unsigned __int64 v36; // [rsp+D0h] [rbp+7h]
  const WCHAR **v37; // [rsp+D8h] [rbp+Fh]
  __int64 v38; // [rsp+E0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v30 = a1;
  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  a1[4] = 0;
  a1[6] = 0;
  a1[7] = 0;
  a1[6] = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>>::_Buyheadnode();
  v26 = 1;
  v6 = -1;
  if ( *(_WORD *)a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&a3[2 * v7] );
  }
  else
  {
    v7 = 0;
  }
  std::wstring::assign(a1, a3, v7);
  v31 = 0;
  v32 = 0;
  if ( (unsigned int)dword_180052170 > 4
    && (qword_180052180 & 0x400000000000LL) != 0
    && (qword_180052188 & 0x400000000000LL) == qword_180052188 )
  {
    EventActivityIdControl(3u, &ActivityId);
    v34 = ActivityId;
    EventActivityIdControl(4u, &v34);
    v32 = 1;
  }
  else
  {
    ActivityId = 0;
  }
  v31 = 1;
  if ( (unsigned int)dword_180052170 > 4
    && (qword_180052180 & 0x400000000000LL) != 0
    && (qword_180052188 & 0x400000000000LL) == qword_180052188 )
  {
    v25 = (const WCHAR *)a3;
    if ( v32 && (v34.Data1 || *(_DWORD *)&v34.Data2 || *(_DWORD *)v34.Data4 || *(_DWORD *)&v34.Data4[4]) )
      v8 = &v34;
    else
      v8 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_180052170,
      (__int64)&dword_180049C5C,
      (__int64)&ActivityId,
      (__int64)v8,
      &v25);
  }
  hkey = 0;
  v9 = RegOpenKeyExW(a2, (LPCWSTR)a3, 0, 1u, &hkey);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      (const char *)v9,
      phkResult);
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"Status", 0x10u, 0, a1 + 5, &pcbData);
  if ( ValueW )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      (const char *)ValueW,
      phkResulta);
  hKey = 0;
  v11 = RegOpenKeyExW(hkey, L"Results", 0, 1u, &hKey);
  if ( v11 )
  {
    if ( v11 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v11,
        phkResultb);
  }
  else
  {
    ForEachRegValue__lambda_04eec936f710298a39cbd82ae29f8689_(hKey);
  }
  if ( *((_DWORD *)a1 + 10) == 1 )
  {
    pcbData = 4;
    v12 = RegGetValueW(hkey, 0, L"UIRequired", 0x10u, 0, (char *)a1 + 44, &pcbData);
    if ( v12 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v12,
        phkResultc);
    pcbData = 0;
    v13 = RegGetValueW(hkey, 0, L"IMSI", 2u, 0, 0, &pcbData);
    if ( v13 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v13,
        phkResultd);
    *(_OWORD *)Src = 0;
    v29 = 0;
    if ( (unsigned __int64)pcbData >> 1 )
      std::vector<unsigned short>::_Reallocate((__int64)Src, (unsigned __int64)pcbData >> 1);
    v14 = (char *)Src[0];
    v15 = RegGetValueW(hkey, 0, L"IMSI", 2u, 0, Src[0], &pcbData);
    if ( v15 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v15,
        phkResulte);
    v36 = 7;
    v35[2] = 0;
    LOWORD(v35[0]) = 0;
    if ( *(_WORD *)v14 )
    {
      do
        ++v6;
      while ( *(_WORD *)&v14[2 * v6] );
    }
    else
    {
      v6 = 0;
    }
    std::wstring::assign(v35, v14, v6);
    nullable_any<std::wstring>::operator=(a1 + 4, v35);
    if ( v36 >= 8 )
      operator delete(v35[0]);
    operator delete(v14);
  }
  if ( v32 )
    EventActivityIdControl(4u, &v34);
  v31 = 2;
  if ( (unsigned int)dword_180052170 > 4
    && (qword_180052180 & 0x400000000000LL) != 0
    && (qword_180052188 & 0x400000000000LL) == qword_180052188 )
  {
    LODWORD(v25) = 0;
    v37 = &v25;
    v38 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180052170, &dword_180049C34, &ActivityId, 0, 3, v35);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( hkey )
    RegCloseKey(hkey);
  if ( v31 == 1 )
  {
    if ( v32 )
      EventActivityIdControl(4u, &v34);
    v31 = 2;
    _tlgWriteActivityAutoStop<70368744177664,4>((unsigned int *)&dword_180052170, (__int64)&ActivityId);
  }
  return a1;
}

```

## disassembly

```asm
0x180035074  mov     [rsp-8+arg_18], rbx
0x180035079  push    rbp
0x18003507a  push    rsi
0x18003507b  push    rdi
0x18003507c  push    r12
0x18003507e  push    r13
0x180035080  push    r14
0x180035082  push    r15
0x180035084  lea     rbp, [rsp-27h]
0x180035089  sub     rsp, 0F0h
0x180035090  mov     rax, cs:__security_cookie
0x180035097  xor     rax, rsp
0x18003509a  mov     [rbp+57h+var_38], rax
0x18003509e  mov     rsi, r8
0x1800350a1  mov     r15, rdx
0x1800350a4  mov     rdi, rcx
0x1800350a7  mov     [rbp+57h+var_A0], rcx
0x1800350ab  xor     r13d, r13d
0x1800350ae  mov     [rbp+57h+var_C8], r13d
0x1800350b2  mov     qword ptr [rcx+18h], 7
0x1800350ba  mov     [rcx+10h], r13
0x1800350be  mov     [rcx], r13w
0x1800350c2  mov     [rcx+20h], r13
0x1800350c6  mov     [rcx+30h], r13
0x1800350ca  mov     [rcx+38h], r13
0x1800350ce  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>>::_Buyheadnode(void)
0x1800350d3  mov     [rdi+30h], rax
0x1800350d7  mov     [rbp+57h+var_C8], 1
0x1800350de  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800350e2  cmp     [rsi], r13w
0x1800350e6  jnz     short loc_1800350ED
0x1800350e8  mov     r8d, r13d
0x1800350eb  jmp     short loc_1800350FA
0x1800350ed  mov     r8, r14
0x1800350f0  inc     r8
0x1800350f3  cmp     [rsi+r8*2], r13w
0x1800350f8  jnz     short loc_1800350F0
0x1800350fa  mov     rdx, rsi; Src
0x1800350fd  mov     rcx, rdi; void *
0x180035100  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180035105  mov     [rbp+57h+var_90], r13d
0x180035109  mov     [rbp+57h+var_8C], r13b
0x18003510d  mov     eax, cs:dword_180052170
0x180035113  mov     rdx, 400000000000h
0x18003511d  mov     ebx, 4
0x180035122  cmp     eax, ebx
0x180035124  jbe     short loc_180035176
0x180035126  mov     rcx, cs:qword_180052188
0x18003512d  mov     rax, cs:qword_180052180
0x180035134  test    rdx, rax
0x180035137  jz      short loc_180035176
0x180035139  mov     rax, rcx
0x18003513c  and     rax, rdx
0x18003513f  cmp     rax, rcx
0x180035142  jnz     short loc_180035176
0x180035144  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180035148  lea     ecx, [rbx-1]; ControlCode
0x18003514b  call    cs:__imp_EventActivityIdControl
0x180035151  movups  xmm0, xmmword ptr [rbp+57h+ActivityId.Data1]
0x180035155  movdqu  xmmword ptr [rbp+57h+var_78.Data1], xmm0
0x18003515a  lea     rdx, [rbp+57h+var_78]; ActivityId
0x18003515e  mov     ecx, ebx; ControlCode
0x180035160  call    cs:__imp_EventActivityIdControl
0x180035166  mov     [rbp+57h+var_8C], 1
0x18003516a  mov     rdx, 400000000000h
0x180035174  jmp     short loc_18003517D
0x180035176  xorps   xmm0, xmm0
0x180035179  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x18003517d  mov     [rbp+57h+var_90], 1
0x180035184  mov     eax, cs:dword_180052170
0x18003518a  cmp     eax, ebx
0x18003518c  jbe     short loc_1800351F8
0x18003518e  mov     rcx, cs:qword_180052188
0x180035195  mov     rax, cs:qword_180052180
0x18003519c  test    rdx, rax
0x18003519f  jz      short loc_1800351F8
0x1800351a1  mov     rax, rcx
0x1800351a4  and     rax, rdx
0x1800351a7  cmp     rax, rcx
0x1800351aa  jnz     short loc_1800351F8
0x1800351ac  mov     [rbp+57h+var_D0], rsi
0x1800351b0  cmp     [rbp+57h+var_8C], r13b
0x1800351b4  jz      short loc_1800351D4
0x1800351b6  cmp     [rbp+57h+var_78.Data1], r13d
0x1800351ba  jnz     short loc_1800351CE
0x1800351bc  cmp     dword ptr [rbp+57h+var_78.Data2], r13d
0x1800351c0  jnz     short loc_1800351CE
0x1800351c2  cmp     dword ptr [rbp+57h+var_78.Data4], r13d
0x1800351c6  jnz     short loc_1800351CE
0x1800351c8  cmp     dword ptr [rbp+57h+var_78.Data4+4], r13d
0x1800351cc  jz      short loc_1800351D4
0x1800351ce  lea     r9, [rbp+57h+var_78]
0x1800351d2  jmp     short loc_1800351D7
0x1800351d4  mov     r9, r13
0x1800351d7  lea     rax, [rbp+57h+var_D0]
0x1800351db  mov     [rsp+120h+phkResult], rax
0x1800351e0  lea     r8, [rbp+57h+ActivityId]
0x1800351e4  lea     rdx, dword_180049C5C
0x1800351eb  lea     rcx, dword_180052170
0x1800351f2  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800351f7  nop
0x1800351f8  mov     [rsp+120h+hkey], r13
0x1800351fd  lea     rax, [rsp+120h+hkey]
0x180035202  mov     [rsp+120h+phkResult], rax; unsigned int
0x180035207  mov     r9d, 1; samDesired
0x18003520d  xor     r8d, r8d; ulOptions
0x180035210  mov     rdx, rsi; lpSubKey
0x180035213  mov     rcx, r15; hKey
0x180035216  call    cs:__imp_RegOpenKeyExW
0x18003521c  mov     rcx, [rbp+5Fh]; this
0x180035220  test    eax, eax
0x180035222  jnz     loc_180035529
0x180035228  mov     [rsp+120h+var_E0], ebx
0x18003522c  lea     rbx, [rdi+28h]
0x180035230  lea     rax, [rsp+120h+var_E0]
0x180035235  mov     [rsp+120h+pcbData], rax; pcbData
0x18003523a  mov     [rsp+120h+pvData], rbx; pvData
0x18003523f  mov     [rsp+120h+phkResult], r13; unsigned int
0x180035244  mov     r9d, 10h; dwFlags
0x18003524a  lea     r8, ?c_status@@3QBGB; "Status"
0x180035251  xor     edx, edx; lpSubKey
0x180035253  mov     rcx, [rsp+120h+hkey]; hkey
0x180035258  call    cs:__imp_RegGetValueW
0x18003525e  mov     rcx, [rbp+5Fh]; this
0x180035262  test    eax, eax
0x180035264  jnz     loc_18003553E
0x18003526a  mov     [rbp+57h+hKey], r13
0x18003526e  lea     rax, [rbp+57h+hKey]
0x180035272  mov     [rsp+120h+phkResult], rax; unsigned int
0x180035277  mov     r9d, 1; samDesired
0x18003527d  xor     r8d, r8d; ulOptions
0x180035280  lea     rdx, ?c_results@@3QBGB; "Results"
0x180035287  mov     rcx, [rsp+120h+hkey]; hKey
0x18003528c  call    cs:__imp_RegOpenKeyExW
0x180035292  mov     r15d, 2
0x180035298  test    eax, eax
0x18003529a  jnz     loc_1800353AB
0x1800352a0  mov     rdx, rdi
0x1800352a3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800352a7  call    ForEachRegValue__lambda_04eec936f710298a39cbd82ae29f8689___; ForEachRegValue__lambda_04eec936f710298a39cbd82ae29f8689_
0x1800352ac  mov     esi, 4
0x1800352b1  cmp     dword ptr [rbx], 1
0x1800352b4  jnz     loc_1800353FC
0x1800352ba  mov     [rsp+120h+var_E0], esi
0x1800352be  lea     rax, [rdi+2Ch]
0x1800352c2  lea     rcx, [rsp+120h+var_E0]
0x1800352c7  mov     [rsp+120h+pcbData], rcx; pcbData
0x1800352cc  mov     [rsp+120h+pvData], rax; pvData
0x1800352d1  mov     [rsp+120h+phkResult], r13; unsigned int
0x1800352d6  lea     r9d, [rsi+0Ch]; dwFlags
0x1800352da  lea     r8, ?gc_wszUIRequired@@3QBGB; "UIRequired"
0x1800352e1  xor     edx, edx; lpSubKey
0x1800352e3  mov     rcx, [rsp+120h+hkey]; hkey
0x1800352e8  call    cs:__imp_RegGetValueW
0x1800352ee  mov     rcx, [rbp+5Fh]; this
0x1800352f2  test    eax, eax
0x1800352f4  jnz     loc_180035553
0x1800352fa  mov     [rsp+120h+var_E0], r13d
0x1800352ff  lea     rax, [rsp+120h+var_E0]
0x180035304  mov     [rsp+120h+pcbData], rax; pcbData
0x180035309  mov     [rsp+120h+pvData], r13; pvData
0x18003530e  mov     [rsp+120h+phkResult], r13; unsigned int
0x180035313  mov     r9d, r15d; dwFlags
0x180035316  lea     r8, c_wszIMSIAttribute; "IMSI"
0x18003531d  xor     edx, edx; lpSubKey
0x18003531f  mov     rcx, [rsp+120h+hkey]; hkey
0x180035324  call    cs:__imp_RegGetValueW
0x18003532a  mov     rcx, [rbp+5Fh]; this
0x18003532e  test    eax, eax
0x180035330  jnz     loc_180035568
0x180035336  xorps   xmm0, xmm0
0x180035339  movdqu  xmmword ptr [rbp+57h+Src], xmm0
0x18003533e  mov     [rbp+57h+var_A8], r13
0x180035342  mov     edx, [rsp+120h+var_E0]
0x180035346  shr     rdx, 1
0x180035349  jz      short loc_180035354
0x18003534b  lea     rcx, [rbp+57h+Src]
0x18003534f  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x180035354  lea     rax, [rsp+120h+var_E0]
0x180035359  mov     [rsp+120h+pcbData], rax; pcbData
0x18003535e  mov     rbx, [rbp+57h+Src]
0x180035362  mov     [rsp+120h+pvData], rbx; pvData
0x180035367  mov     [rsp+120h+phkResult], r13; unsigned int
0x18003536c  mov     r9d, r15d; dwFlags
0x18003536f  lea     r8, c_wszIMSIAttribute; "IMSI"
0x180035376  xor     edx, edx; lpSubKey
0x180035378  mov     rcx, [rsp+120h+hkey]; hkey
0x18003537d  call    cs:__imp_RegGetValueW
0x180035383  mov     rcx, [rbp+5Fh]; this
0x180035387  test    eax, eax
0x180035389  jnz     loc_1800354FB
0x18003538f  mov     [rbp+57h+var_50], 7
0x180035397  mov     [rbp+57h+var_58], r13
0x18003539b  mov     word ptr [rbp+57h+var_68], r13w
0x1800353a0  cmp     [rbx], r13w
0x1800353a4  jnz     short loc_1800353B9
0x1800353a6  mov     r14, r13
0x1800353a9  jmp     short loc_1800353C3
0x1800353ab  cmp     eax, r15d
0x1800353ae  jnz     loc_180035510
0x1800353b4  jmp     loc_1800352AC
0x1800353b9  inc     r14
0x1800353bc  cmp     [rbx+r14*2], r13w
0x1800353c1  jnz     short loc_1800353B9
0x1800353c3  mov     r8, r14
0x1800353c6  mov     rdx, rbx; Src
0x1800353c9  lea     rcx, [rbp+57h+var_68]; void *
0x1800353cd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800353d2  nop
0x1800353d3  lea     rdx, [rbp+57h+var_68]
0x1800353d7  lea     rcx, [rdi+20h]
0x1800353db  call    ??4?$nullable_any@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@QEAAAEAV0@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; nullable_any<std::wstring>::operator=(std::wstring &&)
0x1800353e0  nop
0x1800353e1  cmp     [rbp+57h+var_50], 8
0x1800353e6  jb      short loc_1800353F3
0x1800353e8  mov     rcx, [rbp+57h+var_68]
0x1800353ec  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800353f2  nop
0x1800353f3  mov     rcx, rbx
0x1800353f6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800353fc  cmp     [rbp+57h+var_8C], r13b
0x180035400  jz      short loc_18003540E
0x180035402  lea     rdx, [rbp+57h+var_78]; ActivityId
0x180035406  mov     ecx, esi; ControlCode
0x180035408  call    cs:__imp_EventActivityIdControl
0x18003540e  mov     [rbp+57h+var_90], r15d
0x180035412  mov     eax, cs:dword_180052170
0x180035418  cmp     eax, esi
0x18003541a  jbe     short loc_180035484
0x18003541c  mov     rcx, cs:qword_180052188
0x180035423  mov     rax, cs:qword_180052180
0x18003542a  mov     rdx, 400000000000h
0x180035434  test    rdx, rax
0x180035437  jz      short loc_180035484
0x180035439  mov     rax, rcx
0x18003543c  and     rax, rdx
0x18003543f  cmp     rax, rcx
0x180035442  jnz     short loc_180035484
0x180035444  mov     dword ptr [rbp+57h+var_D0], r13d
0x180035448  lea     rax, [rbp+57h+var_D0]
0x18003544c  mov     [rbp+57h+var_48], rax
0x180035450  mov     [rbp+57h+var_40], 4
0x180035458  lea     rax, [rbp+57h+var_68]
0x18003545c  mov     [rsp+120h+pvData], rax
0x180035461  mov     dword ptr [rsp+120h+phkResult], 3
0x180035469  xor     r9d, r9d
0x18003546c  lea     r8, [rbp+57h+ActivityId]
0x180035470  lea     rdx, dword_180049C34
0x180035477  lea     rcx, dword_180052170
0x18003547e  call    _tlgWriteTransfer_EventWriteTransfer
0x180035483  nop
0x180035484  mov     rcx, [rbp+57h+hKey]; hKey
0x180035488  test    rcx, rcx
0x18003548b  jz      short loc_180035494
0x18003548d  call    cs:__imp_RegCloseKey
0x180035493  nop
0x180035494  mov     rcx, [rsp+120h+hkey]; hKey
0x180035499  test    rcx, rcx
0x18003549c  jz      short loc_1800354A5
0x18003549e  call    cs:__imp_RegCloseKey
0x1800354a4  nop
0x1800354a5  cmp     [rbp+57h+var_90], 1
0x1800354a9  jnz     short loc_1800354D1
0x1800354ab  cmp     [rbp+57h+var_8C], r13b
0x1800354af  jz      short loc_1800354BD
0x1800354b1  lea     rdx, [rbp+57h+var_78]; ActivityId
0x1800354b5  mov     ecx, esi; ControlCode
0x1800354b7  call    cs:__imp_EventActivityIdControl
0x1800354bd  mov     [rbp+57h+var_90], r15d
0x1800354c1  lea     rdx, [rbp+57h+ActivityId]
0x1800354c5  lea     rcx, dword_180052170
0x1800354cc  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$03@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,4>(_tlgProvider_t const *,_GUID const *)
0x1800354d1  mov     rax, rdi
0x1800354d4  mov     rcx, [rbp+57h+var_38]
0x1800354d8  xor     rcx, rsp; StackCookie
0x1800354db  call    __security_check_cookie
0x1800354e0  mov     rbx, [rsp+120h+arg_18]
0x1800354e8  add     rsp, 0F0h
0x1800354ef  pop     r15
0x1800354f1  pop     r14
0x1800354f3  pop     r13
0x1800354f5  pop     r12
0x1800354f7  pop     rdi
0x1800354f8  pop     rsi
0x1800354f9  pop     rbp
0x1800354fa  retn
0x1800354fb  mov     r9d, eax; char *
0x1800354fe  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035505  mov     edx, 4Ch ; 'L'; void *
0x18003550a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180035510  mov     rcx, [rbp+5Fh]; this
0x180035514  mov     r9d, eax; char *
0x180035517  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003551e  mov     edx, 3Bh ; ';'; void *
0x180035523  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180035529  mov     r9d, eax; char *
0x18003552c  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035533  mov     edx, 20h ; ' '; void *
0x180035538  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003553e  mov     r9d, eax; char *
  ... truncated ...
```
