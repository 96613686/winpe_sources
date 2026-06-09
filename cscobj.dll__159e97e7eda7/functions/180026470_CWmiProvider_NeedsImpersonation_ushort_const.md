# CWmiProvider::_NeedsImpersonation(ushort * const)

- ea: `0x180026470`
- end: `0x18002653a`
- name: `?_NeedsImpersonation@CWmiProvider@@AEAAHQEAG@Z`
- size: `202`
- prototype: `__int64 __fastcall(CWmiProvider *this, unsigned __int16 *const)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023c40`
- `0x180024020`
- `0x180024f40`
- `0x180025700`

## callees

- `0x180006c00`
- `0x180009d50`
- `0x18000b7c0`
- `0x1800226a0`
- `0x1800226fc`
- `0x180022b0c`
- `0x180026470`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800264f7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800264f7`

## string_xrefs

- `0x1800264e5`: `Win32_OfflineFilesUserConfiguration`

## pseudocode

```c
__int64 __fastcall CWmiProvider::_NeedsImpersonation(CWmiProvider *this, unsigned __int16 *const a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // r8d
  struct IWbemPath *v6; // [rsp+30h] [rbp-258h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-250h] BYREF
  WCHAR String2[264]; // [rsp+60h] [rbp-228h] BYREF

  v3 = 0;
  v6 = 0;
  if ( (int)CInterfaceInGITBase::_Unmarshal(
              (CWmiProvider *)((char *)this + 104),
              &GUID_3bc15af2_736c_477e_9e51_238af8667dcc,
              (void **)&v6) >= 0 )
  {
    CWmiObjPath::CWmiObjPath((CWmiObjPath *)v7, v6, a2);
    if ( (int)CWmiObjPath::_GetClassName((CWmiObjPath *)v7, String2, v4) >= 0 )
      LOBYTE(v3) = CompareStringW(0x7Fu, 1u, L"Win32_OfflineFilesUserConfiguration", -1, String2, -1) != 2;
    CWmiObjPath::~CWmiObjPath((CWmiObjPath *)v7);
  }
  ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(&v6);
  return v3;
}

```

## disassembly

```asm
0x180026470  mov     [rsp+arg_10], rbx
0x180026475  push    rdi
0x180026476  sub     rsp, 280h
0x18002647d  mov     rax, cs:__security_cookie
0x180026484  xor     rax, rsp
0x180026487  mov     [rsp+288h+var_18], rax
0x18002648f  mov     rdi, rdx
0x180026492  lea     r8, [rsp+288h+var_258]; void **
0x180026497  xor     ebx, ebx
0x180026499  lea     rdx, _GUID_3bc15af2_736c_477e_9e51_238af8667dcc; struct _GUID *
0x1800264a0  add     rcx, 68h ; 'h'; this
0x1800264a4  mov     [rsp+288h+var_258], rbx
0x1800264a9  call    ?_Unmarshal@CInterfaceInGITBase@@IEAAJAEBU_GUID@@PEAPEAX@Z; CInterfaceInGITBase::_Unmarshal(_GUID const &,void * *)
0x1800264ae  test    eax, eax
0x1800264b0  js      short loc_18002650D
0x1800264b2  mov     rdx, [rsp+288h+var_258]; struct IWbemPath *
0x1800264b7  lea     rcx, [rsp+288h+var_250]; this
0x1800264bc  mov     r8, rdi; unsigned __int16 *
0x1800264bf  call    ??0CWmiObjPath@@QEAA@PEAUIWbemPath@@QEAG@Z; CWmiObjPath::CWmiObjPath(IWbemPath *,ushort * const)
0x1800264c4  lea     rdx, [rsp+288h+String2]; unsigned __int16 *
0x1800264c9  lea     rcx, [rsp+288h+var_250]; this
0x1800264ce  call    ?_GetClassName@CWmiObjPath@@AEAAJPEAGK@Z; CWmiObjPath::_GetClassName(ushort *,ulong)
0x1800264d3  test    eax, eax
0x1800264d5  js      short loc_180026503
0x1800264d7  or      r9d, 0FFFFFFFFh; cchCount1
0x1800264db  lea     rax, [rsp+288h+String2]
0x1800264e0  mov     [rsp+288h+cchCount2], r9d; cchCount2
0x1800264e5  lea     r8, CSCWMI_STR_OFFLINEFILESUSERCONFIGURATION; "Win32_OfflineFilesUserConfiguration"
0x1800264ec  lea     edx, [rbx+1]; dwCmpFlags
0x1800264ef  mov     [rsp+288h+lpString2], rax; lpString2
0x1800264f4  lea     ecx, [rbx+7Fh]; Locale
0x1800264f7  call    cs:__imp_CompareStringW
0x1800264fd  cmp     eax, 2
0x180026500  setnz   bl
0x180026503  lea     rcx, [rsp+288h+var_250]; this
0x180026508  call    ??1CWmiObjPath@@QEAA@XZ; CWmiObjPath::~CWmiObjPath(void)
0x18002650d  lea     rcx, [rsp+288h+var_258]
0x180026512  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x180026517  mov     eax, ebx
0x180026519  mov     rcx, [rsp+288h+var_18]
0x180026521  xor     rcx, rsp; StackCookie
0x180026524  call    __security_check_cookie
0x180026529  mov     rbx, [rsp+288h+arg_10]
0x180026531  add     rsp, 280h
0x180026538  pop     rdi
0x180026539  retn
```
