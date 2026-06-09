# CSpCluster::_GetDriveLetterMask(ulong *)

- ea: `0x18004f4bc`
- end: `0x18004f84b`
- name: `?_GetDriveLetterMask@CSpCluster@@AEAA?AV_status_t@@PEAK@Z`
- size: `911`
- prototype: `struct _status_t __high(unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180048f24`
- `0x18004d590`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x180006350`
- `0x18000e3ac`
- `0x18000f100`
- `0x18000f484`
- `0x18004f4bc`
- `0x180052074`

## import_xrefs

- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceTypeControl` at `0x18004f689`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceTypeControl` at `0x18004f689`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x18004f63c`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x18004f63c`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterEnum` at `0x18004f60f`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterEnum` at `0x18004f60f`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x18004f6b5`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x18004f6f0`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x18004f6b5`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x18004f6f0`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterCloseEnum` at `0x18004f704`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterCloseEnum` at `0x18004f704`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterOpenEnum` at `0x18004f569`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterOpenEnum` at `0x18004f569`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterGetEnumCount` at `0x18004f5d7`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterGetEnumCount` at `0x18004f5d7`

## pseudocode

```c
_status_t *__fastcall CSpCluster::_GetDriveLetterMask(__int64 a1, _status_t *a2, char *a3, int a4)
{
  struct _HCLUSENUM *v6; // rsi
  struct _HNODE *v7; // rdi
  struct _HCLUSTER *v8; // rcx
  struct _HCLUSENUM *v9; // rax
  signed int LastError; // ecx
  int v11; // r8d
  int v12; // r9d
  char *v13; // rdx
  int *v14; // rax
  int v15; // r12d
  DWORD v16; // r15d
  DWORD EnumCount; // r13d
  signed int v18; // eax
  int v19; // r8d
  int v20; // r9d
  signed int v21; // ecx
  signed int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int *lpOutBuffer; // [rsp+30h] [rbp-49h]
  int v28; // [rsp+50h] [rbp-29h] BYREF
  int v29; // [rsp+54h] [rbp-25h] BYREF
  char *v30; // [rsp+58h] [rbp-21h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-19h] BYREF
  int OutBuffer; // [rsp+64h] [rbp-15h] BYREF
  const char *v33; // [rsp+68h] [rbp-11h] BYREF
  DWORD dwType; // [rsp+70h] [rbp-9h] BYREF
  WCHAR szName[16]; // [rsp+78h] [rbp-1h] BYREF

  v30 = a3;
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v28 = 2468;
    v33 = "CSpCluster::_GetDriveLetterMask";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)byte_18030BC43,
      (_DWORD)a3,
      a4,
      (__int64)&v33,
      (__int64)&v28);
  }
  v6 = 0;
  cchName = 16;
  OutBuffer = 0;
  dwType = 0;
  v7 = 0;
  *(_QWORD *)a2 = 0;
  *((_BYTE *)a2 + 8) = 0;
  wil::EnterCriticalSection(&v33, a1 + 8);
  v8 = *(struct _HCLUSTER **)(a1 + 72);
  if ( !v8 )
  {
    *(_DWORD *)a2 = -2147019846;
    goto LABEL_19;
  }
  v9 = ClusterOpenEnum(v8, 1u);
  v6 = v9;
  if ( !v9 )
  {
    LastError = _status_t::GetLastError(a2);
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_19;
    v28 = LastError;
    lpOutBuffer = &v28;
    v13 = byte_18030B62B;
    v14 = &v29;
    v29 = 2492;
    goto LABEL_8;
  }
  v15 = -1;
  v16 = 0;
  EnumCount = ClusterGetEnumCount(v9);
  if ( EnumCount )
  {
    while ( 1 )
    {
      cchName = 16;
      v18 = ClusterEnum(v6, v16, &dwType, szName, &cchName);
      v21 = v18;
      if ( v18 > 0 )
        v21 = (unsigned __int16)v18 | 0x80070000;
      *(_DWORD *)a2 = v21;
      if ( v21 < 0 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          v29 = v21;
          v28 = 2510;
          v30 = "CSpCluster::_GetDriveLetterMask";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v21,
            (unsigned int)byte_180309F19,
            v19,
            v20,
            (__int64)&v30,
            (__int64)&v28,
            (__int64)&v29);
        }
        v7 = 0;
        goto LABEL_19;
      }
      v7 = OpenClusterNode(*(HCLUSTER *)(a1 + 72), szName);
      if ( !v7 )
        break;
      v22 = ClusterResourceTypeControl(
              *(HCLUSTER *)(a1 + 72),
              L"Physical Disk",
              v7,
              0x20001EDu,
              0,
              0,
              &OutBuffer,
              4u,
              0);
      LastError = v22;
      if ( v22 > 0 )
        LastError = (unsigned __int16)v22 | 0x80070000;
      *(_DWORD *)a2 = LastError;
      if ( LastError < 0 )
      {
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_19;
        v29 = LastError;
        lpOutBuffer = &v29;
        v14 = &v28;
        v28 = 2534;
        v13 = (char *)&unk_18030C598;
        goto LABEL_8;
      }
      v15 &= OutBuffer;
      CloseClusterNode(v7);
      if ( ++v16 >= EnumCount )
        goto LABEL_18;
    }
    LastError = _status_t::GetLastError(a2);
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_19;
    v29 = LastError;
    lpOutBuffer = &v29;
    v14 = &v28;
    v28 = 2518;
    v13 = byte_180307FD3;
LABEL_8:
    v30 = "CSpCluster::_GetDriveLetterMask";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      LastError,
      (_DWORD)v13,
      v11,
      v12,
      (__int64)&v30,
      (__int64)v14,
      (__int64)lpOutBuffer);
    goto LABEL_19;
  }
LABEL_18:
  v7 = 0;
  *(_DWORD *)v30 = v15;
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
    &v33,
    0);
  if ( v7 )
    CloseClusterNode(v7);
  if ( v6 )
    ClusterCloseEnum(v6);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v29 = 2564;
    v30 = "CSpCluster::_GetDriveLetterMask";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)byte_18030C8CD,
      v24,
      v25,
      (__int64)&v30,
      (__int64)&v29);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
  return a2;
}

```

## disassembly

```asm
0x18004f4bc  mov     [rsp-8+arg_18], rbx
0x18004f4c1  push    rbp
0x18004f4c2  push    rsi
0x18004f4c3  push    rdi
0x18004f4c4  push    r12
0x18004f4c6  push    r13
0x18004f4c8  push    r14
0x18004f4ca  push    r15
0x18004f4cc  lea     rbp, [rsp-27h]
0x18004f4d1  sub     rsp, 0A0h
0x18004f4d8  mov     rax, cs:__security_cookie
0x18004f4df  xor     rax, rsp
0x18004f4e2  mov     [rbp+57h+var_38], rax
0x18004f4e6  mov     eax, cs:dword_18039EB68
0x18004f4ec  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004f4f3  mov     [rbp+57h+var_78], r8
0x18004f4f7  mov     rbx, rdx
0x18004f4fa  mov     r14, rcx
0x18004f4fd  cmp     eax, 5
0x18004f500  jbe     short loc_18004F52B
0x18004f502  lea     rax, [rbp+57h+var_80]
0x18004f506  mov     [rbp+57h+var_80], 9A4h
0x18004f50d  mov     qword ptr [rsp+0D0h+nInBufferSize], rax
0x18004f512  lea     rdx, byte_18030BC43
0x18004f519  lea     rax, [rbp+57h+var_68]
0x18004f51d  mov     [rbp+57h+var_68], r15
0x18004f521  mov     [rsp+0D0h+lpcchName], rax
0x18004f526  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004f52b  xor     esi, esi
0x18004f52d  mov     [rbp+57h+cchName], 10h
0x18004f534  lea     rdx, [r14+8]
0x18004f538  mov     [rbp+57h+OutBuffer], esi
0x18004f53b  lea     rcx, [rbp+57h+var_68]
0x18004f53f  mov     [rbp+57h+dwType], esi
0x18004f542  mov     edi, esi
0x18004f544  mov     [rbx], rsi
0x18004f547  mov     [rbx+8], sil
0x18004f54b  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004f550  mov     rcx, [r14+48h]; hCluster
0x18004f554  test    rcx, rcx
0x18004f557  jnz     short loc_18004F564
0x18004f559  mov     dword ptr [rbx], 800713BAh
0x18004f55f  jmp     loc_18004F6DD
0x18004f564  mov     edx, 1; dwType
0x18004f569  call    cs:__imp_ClusterOpenEnum
0x18004f570  nop     dword ptr [rax+rax+00h]
0x18004f575  mov     rsi, rax
0x18004f578  test    rax, rax
0x18004f57b  jnz     short loc_18004F5D0
0x18004f57d  mov     rcx, rbx; this
0x18004f580  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x18004f585  mov     ecx, eax
0x18004f587  mov     eax, cs:dword_18039EB68
0x18004f58d  cmp     eax, 2
0x18004f590  jbe     loc_18004F6DD
0x18004f596  lea     rax, [rbp+57h+var_80]
0x18004f59a  mov     [rbp+57h+var_80], ecx
0x18004f59d  mov     [rsp+0D0h+lpOutBuffer], rax
0x18004f5a2  lea     rdx, byte_18030B62B
0x18004f5a9  lea     rax, [rbp+57h+var_7C]
0x18004f5ad  mov     [rbp+57h+var_7C], 9BCh
0x18004f5b4  mov     qword ptr [rsp+0D0h+nInBufferSize], rax
0x18004f5b9  lea     rax, [rbp+57h+var_78]
0x18004f5bd  mov     [rsp+0D0h+lpcchName], rax
0x18004f5c2  mov     [rbp+57h+var_78], r15
0x18004f5c6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004f5cb  jmp     loc_18004F6DD
0x18004f5d0  mov     rcx, rsi; hEnum
0x18004f5d3  or      r12d, 0FFFFFFFFh
0x18004f5d7  call    cs:__imp_ClusterGetEnumCount
0x18004f5de  nop     dword ptr [rax+rax+00h]
0x18004f5e3  xor     r15d, r15d
0x18004f5e6  mov     r13d, eax
0x18004f5e9  test    eax, eax
0x18004f5eb  jz      loc_18004F6CD
0x18004f5f1  lea     rax, [rbp+57h+cchName]
0x18004f5f5  mov     [rbp+57h+cchName], 10h
0x18004f5fc  lea     r9, [rbp+57h+szName]; lpszName
0x18004f600  mov     [rsp+0D0h+lpcchName], rax; lpcchName
0x18004f605  lea     r8, [rbp+57h+dwType]; lpdwType
0x18004f609  mov     edx, r15d; dwIndex
0x18004f60c  mov     rcx, rsi; hEnum
0x18004f60f  call    cs:__imp_ClusterEnum
0x18004f616  nop     dword ptr [rax+rax+00h]
0x18004f61b  mov     ecx, eax
0x18004f61d  test    eax, eax
0x18004f61f  jle     short loc_18004F62A
0x18004f621  movzx   ecx, ax
0x18004f624  or      ecx, 80070000h
0x18004f62a  mov     [rbx], ecx
0x18004f62c  test    ecx, ecx
0x18004f62e  js      loc_18004F7F4
0x18004f634  mov     rcx, [r14+48h]; hCluster
0x18004f638  lea     rdx, [rbp+57h+szName]; lpszNodeName
0x18004f63c  call    cs:__imp_OpenClusterNode
0x18004f643  nop     dword ptr [rax+rax+00h]
0x18004f648  xor     ecx, ecx
0x18004f64a  mov     rdi, rax
0x18004f64d  test    rax, rax
0x18004f650  jz      loc_18004F7B1
0x18004f656  mov     [rsp+0D0h+lpBytesReturned], rcx; lpBytesReturned
0x18004f65b  lea     rax, [rbp+57h+OutBuffer]
0x18004f65f  mov     [rsp+0D0h+nOutBufferSize], 4; nOutBufferSize
0x18004f667  lea     rdx, szResourceTypeName; "Physical Disk"
0x18004f66e  mov     [rsp+0D0h+lpOutBuffer], rax; lpOutBuffer
0x18004f673  mov     r9d, 20001EDh; dwControlCode
0x18004f679  mov     [rsp+0D0h+nInBufferSize], ecx; nInBufferSize
0x18004f67d  mov     r8, rdi; hHostNode
0x18004f680  mov     [rsp+0D0h+lpcchName], rcx; lpInBuffer
0x18004f685  mov     rcx, [r14+48h]; hCluster
0x18004f689  call    cs:__imp_ClusterResourceTypeControl
0x18004f690  nop     dword ptr [rax+rax+00h]
0x18004f695  mov     ecx, eax
0x18004f697  test    eax, eax
0x18004f699  jle     short loc_18004F6A4
0x18004f69b  movzx   ecx, ax
0x18004f69e  or      ecx, 80070000h
0x18004f6a4  mov     [rbx], ecx
0x18004f6a6  test    ecx, ecx
0x18004f6a8  js      loc_18004F778
0x18004f6ae  and     r12d, [rbp+57h+OutBuffer]
0x18004f6b2  mov     rcx, rdi; hNode
0x18004f6b5  call    cs:__imp_CloseClusterNode
0x18004f6bc  nop     dword ptr [rax+rax+00h]
0x18004f6c1  inc     r15d
0x18004f6c4  cmp     r15d, r13d
0x18004f6c7  jb      loc_18004F5F1
0x18004f6cd  mov     rax, [rbp+57h+var_78]
0x18004f6d1  xor     edi, edi
0x18004f6d3  mov     [rax], r12d
0x18004f6d6  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004f6dd  xor     edx, edx
0x18004f6df  lea     rcx, [rbp+57h+var_68]
0x18004f6e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18004f6e8  test    rdi, rdi
0x18004f6eb  jz      short loc_18004F6FC
0x18004f6ed  mov     rcx, rdi; hNode
0x18004f6f0  call    cs:__imp_CloseClusterNode
0x18004f6f7  nop     dword ptr [rax+rax+00h]
0x18004f6fc  test    rsi, rsi
0x18004f6ff  jz      short loc_18004F710
0x18004f701  mov     rcx, rsi; hEnum
0x18004f704  call    cs:__imp_ClusterCloseEnum
0x18004f70b  nop     dword ptr [rax+rax+00h]
0x18004f710  mov     eax, cs:dword_18039EB68
0x18004f716  cmp     eax, 5
0x18004f719  jbe     short loc_18004F744
0x18004f71b  lea     rax, [rbp+57h+var_7C]
0x18004f71f  mov     [rbp+57h+var_7C], 0A04h
0x18004f726  mov     qword ptr [rsp+0D0h+nInBufferSize], rax
0x18004f72b  lea     rdx, byte_18030C8CD
0x18004f732  lea     rax, [rbp+57h+var_78]
0x18004f736  mov     [rbp+57h+var_78], r15
0x18004f73a  mov     [rsp+0D0h+lpcchName], rax
0x18004f73f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004f744  lea     rcx, [rbp+57h+var_68]
0x18004f748  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004f74d  mov     rax, rbx
0x18004f750  mov     rcx, [rbp+57h+var_38]
0x18004f754  xor     rcx, rsp; StackCookie
0x18004f757  call    __security_check_cookie
0x18004f75c  mov     rbx, [rsp+0D0h+arg_18]
0x18004f764  add     rsp, 0A0h
0x18004f76b  pop     r15
0x18004f76d  pop     r14
0x18004f76f  pop     r13
0x18004f771  pop     r12
0x18004f773  pop     rdi
0x18004f774  pop     rsi
0x18004f775  pop     rbp
0x18004f776  retn
0x18004f778  mov     eax, cs:dword_18039EB68
0x18004f77e  cmp     eax, 2
0x18004f781  jbe     loc_18004F6D6
0x18004f787  lea     rax, [rbp+57h+var_7C]
0x18004f78b  mov     [rbp+57h+var_7C], ecx
0x18004f78e  mov     [rsp+0D0h+lpOutBuffer], rax
0x18004f793  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004f79a  lea     rax, [rbp+57h+var_80]
0x18004f79e  mov     [rbp+57h+var_80], 9E6h
0x18004f7a5  lea     rdx, unk_18030C598
0x18004f7ac  jmp     loc_18004F5B4
0x18004f7b1  mov     rcx, rbx; this
0x18004f7b4  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x18004f7b9  mov     ecx, eax
0x18004f7bb  mov     eax, cs:dword_18039EB68
0x18004f7c1  cmp     eax, 2
0x18004f7c4  jbe     loc_18004F6D6
0x18004f7ca  lea     rax, [rbp+57h+var_7C]
0x18004f7ce  mov     [rbp+57h+var_7C], ecx
0x18004f7d1  mov     [rsp+0D0h+lpOutBuffer], rax
0x18004f7d6  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004f7dd  lea     rax, [rbp+57h+var_80]
0x18004f7e1  mov     [rbp+57h+var_80], 9D6h
0x18004f7e8  lea     rdx, byte_180307FD3
0x18004f7ef  jmp     loc_18004F5B4
0x18004f7f4  mov     eax, cs:dword_18039EB68
0x18004f7fa  cmp     eax, 2
0x18004f7fd  jbe     short loc_18004F83D
0x18004f7ff  lea     rax, [rbp+57h+var_7C]
0x18004f803  mov     [rbp+57h+var_7C], ecx
0x18004f806  mov     [rsp+0D0h+lpOutBuffer], rax
0x18004f80b  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004f812  lea     rax, [rbp+57h+var_80]
0x18004f816  mov     [rbp+57h+var_80], 9CEh
0x18004f81d  mov     qword ptr [rsp+0D0h+nInBufferSize], rax
0x18004f822  lea     rdx, byte_180309F19
0x18004f829  lea     rax, [rbp+57h+var_78]
0x18004f82d  mov     [rbp+57h+var_78], r15
0x18004f831  mov     [rsp+0D0h+lpcchName], rax
0x18004f836  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004f83b  jmp     short loc_18004F844
0x18004f83d  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004f844  xor     edi, edi
0x18004f846  jmp     loc_18004F6DD
```
