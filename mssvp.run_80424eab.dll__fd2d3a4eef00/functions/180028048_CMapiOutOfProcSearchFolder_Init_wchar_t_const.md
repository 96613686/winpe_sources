# CMapiOutOfProcSearchFolder::Init(wchar_t const *)

- ea: `0x180028048`
- end: `0x1800281ac`
- name: `?Init@CMapiOutOfProcSearchFolder@@QEAAJPEB_W@Z`
- size: `356`
- prototype: `__int64 __fastcall(CMapiOutOfProcSearchFolder *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027b30`

## callees

- `0x180005210`
- `0x180006270`
- `0x180006dcc`
- `0x180028048`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028112`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028112`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180028087`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180028087`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800280aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800280aa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800280e9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800280e9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800280f8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800280f8`

## string_xrefs

- `0x18002810b`: `DllGetClassObject`
- `0x1800280e2`: `%systemroot%\system32\Search.ProtocolHandler.MAPI2.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiOutOfProcSearchFolder::Init(CMapiOutOfProcSearchFolder *this, const wchar_t *a2)
{
  LPVOID *ppv; // rsi
  HRESULT v5; // ebx
  HMODULE v6; // rcx
  FARPROC ProcAddress; // rax
  GUID clsid; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Dst[264]; // [rsp+40h] [rbp-238h] BYREF

  ppv = (LPVOID *)((char *)this + 72);
  clsid = 0;
  v5 = CLSIDFromProgID(L"Search.MAPI2Handler", &clsid);
  if ( v5 >= 0 )
    v5 = CoCreateInstance(&clsid, 0, 1u, &GUID_da24d14e_dd1f_4a1c_9a9c_cd837c8a9b52, ppv);
  if ( v5 != -2147221164 )
    goto LABEL_12;
  if ( !*((_QWORD *)this + 10) )
  {
    memset_0(Dst, 0, 0x208u);
    if ( ExpandEnvironmentStringsW(L"%systemroot%\\system32\\Search.ProtocolHandler.MAPI2.dll", Dst, 0x104u) )
      *((_QWORD *)this + 10) = LoadLibraryW(Dst);
  }
  v6 = (HMODULE)*((_QWORD *)this + 10);
  if ( v6 )
  {
    ProcAddress = GetProcAddress(v6, "DllGetClassObject");
    if ( ProcAddress )
    {
      *(_QWORD *)&clsid.Data1 = 0;
      if ( ((int (__fastcall *)(GUID *, GUID *, GUID *))ProcAddress)(
             &GUID_9e175baf_f52a_11d8_b9a5_505054503030,
             &GUID_00000001_0000_0000_c000_000000000046,
             &clsid) >= 0 )
        v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, LPVOID *))(**(_QWORD **)&clsid.Data1 + 24LL))(
               *(_QWORD *)&clsid.Data1,
               0,
               &GUID_da24d14e_dd1f_4a1c_9a9c_cd837c8a9b52,
               ppv);
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&clsid);
LABEL_12:
      if ( v5 >= 0 )
        return (unsigned int)(*(__int64 (__fastcall **)(LPVOID, const wchar_t *, char *))(*(_QWORD *)*ppv + 24LL))(
                               *ppv,
                               a2,
                               (char *)this + 64);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180028048  mov     [rsp+arg_10], rbx
0x18002804d  push    rbp
0x18002804e  push    rsi
0x18002804f  push    rdi
0x180028050  sub     rsp, 260h
0x180028057  mov     rax, cs:__security_cookie
0x18002805e  xor     rax, rsp
0x180028061  mov     [rsp+278h+var_28], rax
0x180028069  mov     rbp, rdx
0x18002806c  mov     rdi, rcx
0x18002806f  lea     rsi, [rcx+48h]
0x180028073  xorps   xmm0, xmm0
0x180028076  movups  xmmword ptr [rsp+278h+clsid.Data1], xmm0
0x18002807b  lea     rdx, [rsp+278h+clsid]; lpclsid
0x180028080  lea     rcx, szProgID; "Search.MAPI2Handler"
0x180028087  call    cs:__imp_CLSIDFromProgID
0x18002808d  mov     ebx, eax
0x18002808f  test    eax, eax
0x180028091  js      short loc_1800280B2
0x180028093  mov     [rsp+278h+ppv], rsi; ppv
0x180028098  lea     r9, _GUID_da24d14e_dd1f_4a1c_9a9c_cd837c8a9b52; riid
0x18002809f  xor     edx, edx; pUnkOuter
0x1800280a1  lea     r8d, [rdx+1]; dwClsContext
0x1800280a5  lea     rcx, [rsp+278h+clsid]; rclsid
0x1800280aa  call    cs:__imp_CoCreateInstance
0x1800280b0  mov     ebx, eax
0x1800280b2  cmp     ebx, 80040154h
0x1800280b8  jnz     loc_18002816B
0x1800280be  cmp     qword ptr [rdi+50h], 0
0x1800280c3  jnz     short loc_180028102
0x1800280c5  xor     edx, edx; Val
0x1800280c7  mov     r8d, 208h; Size
0x1800280cd  lea     rcx, [rsp+278h+Dst]; void *
0x1800280d2  call    memset_0
0x1800280d7  mov     r8d, 104h; nSize
0x1800280dd  lea     rdx, [rsp+278h+Dst]; lpDst
0x1800280e2  lea     rcx, Src; "%systemroot%\\system32\\Search.Protocol"...
0x1800280e9  call    cs:__imp_ExpandEnvironmentStringsW
0x1800280ef  test    eax, eax
0x1800280f1  jz      short loc_180028102
0x1800280f3  lea     rcx, [rsp+278h+Dst]; lpLibFileName
0x1800280f8  call    cs:__imp_LoadLibraryW
0x1800280fe  mov     [rdi+50h], rax
0x180028102  mov     rcx, [rdi+50h]; hModule
0x180028106  test    rcx, rcx
0x180028109  jz      short loc_180028187
0x18002810b  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180028112  call    cs:__imp_GetProcAddress
0x180028118  test    rax, rax
0x18002811b  jz      short loc_180028187
0x18002811d  mov     qword ptr [rsp+278h+clsid.Data1], 0
0x180028126  lea     r8, [rsp+278h+clsid]
0x18002812b  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x180028132  lea     rcx, _GUID_9e175baf_f52a_11d8_b9a5_505054503030
0x180028139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002813e  test    eax, eax
0x180028140  js      short loc_180028161
0x180028142  mov     rcx, qword ptr [rsp+278h+clsid.Data1]
0x180028147  mov     rax, [rcx]
0x18002814a  mov     r9, rsi
0x18002814d  lea     r8, _GUID_da24d14e_dd1f_4a1c_9a9c_cd837c8a9b52
0x180028154  xor     edx, edx
0x180028156  mov     rax, [rax+18h]
0x18002815a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002815f  mov     ebx, eax
0x180028161  lea     rcx, [rsp+278h+clsid]
0x180028166  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002816b  test    ebx, ebx
0x18002816d  js      short loc_180028187
0x18002816f  mov     rcx, [rsi]
0x180028172  mov     rax, [rcx]
0x180028175  lea     r8, [rdi+40h]
0x180028179  mov     rdx, rbp
0x18002817c  mov     rax, [rax+18h]
0x180028180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028185  mov     ebx, eax
0x180028187  mov     eax, ebx
0x180028189  mov     rcx, [rsp+278h+var_28]
0x180028191  xor     rcx, rsp; StackCookie
0x180028194  call    __security_check_cookie
0x180028199  mov     rbx, [rsp+278h+arg_10]
0x1800281a1  add     rsp, 260h
0x1800281a8  pop     rdi
0x1800281a9  pop     rsi
0x1800281aa  pop     rbp
0x1800281ab  retn
```
