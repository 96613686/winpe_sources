# HrRaiseWlanProperties(CNetStatisticsEngine *)

- ea: `0x18005985c`
- end: `0x180059a26`
- name: `?HrRaiseWlanProperties@@YAJPEAVCNetStatisticsEngine@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(struct CNetStatisticsEngine *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18005ac00`

## callees

- `0x180009930`
- `0x18000a730`
- `0x180018d74`
- `0x18001e1e0`
- `0x18001eb7c`
- `0x1800228a4`
- `0x180040790`
- `0x18005985c`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800598c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800598c9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800599f7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800599f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800598b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800598b4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800598a6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800598a6`

## string_xrefs

- `0x180059896`: `wlanui.dll`

## pseudocode

```c
__int64 __fastcall HrRaiseWlanProperties(struct CNetStatisticsEngine *this)
{
  HMODULE LibraryW; // rax
  HMODULE v3; // rsi
  signed int LastError; // eax
  FARPROC ProcAddress; // r14
  signed int ConnectionFromPersistData; // ebx
  __int64 v7; // r9
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  NETCON_PROPERTIES *pProps; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown v11; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v12[256]; // [rsp+60h] [rbp-A0h] BYREF

  v11.lpVtbl = 0;
  pProps = 0;
  LibraryW = LoadLibraryW(L"wlanui.dll");
  v3 = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "WlanUIEditProfile")) != 0 )
  {
    ConnectionFromPersistData = HrGetConnectionFromPersistData(
                                  (const struct _GUID *)((char *)this + 180),
                                  *((const unsigned __int8 **)this + 21),
                                  *((_DWORD *)this + 44),
                                  &IID_INetConnection,
                                  &v11,
                                  0);
    if ( ConnectionFromPersistData < 0 )
      goto LABEL_13;
    if ( !v11.lpVtbl )
      goto LABEL_13;
    ConnectionFromPersistData = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, NETCON_PROPERTIES **))v11.lpVtbl->QueryInterface
                                 + 7))(
                                  v11.lpVtbl,
                                  &pProps);
    if ( ConnectionFromPersistData < 0 )
      goto LABEL_13;
    if ( !*((_QWORD *)this + 36) )
    {
      ConnectionFromPersistData = CWlanStatEngine::GetWlanConnectionAttributes(this);
      if ( ConnectionFromPersistData < 0 )
        goto LABEL_13;
    }
    memset_0(v12, 0, sizeof(v12));
    ConnectionFromPersistData = StringCchCopyW(v12, 0x100u, (const unsigned __int16 *)(*((_QWORD *)this + 36) + 8LL));
    if ( ConnectionFromPersistData < 0 )
      goto LABEL_13;
    v7 = *((_QWORD *)this + 26);
    v9 = 0;
    LastError = ((__int64 (__fastcall *)(__int64, unsigned __int16 *, NETCON_PROPERTIES *, __int64, _DWORD, _QWORD, int *))ProcAddress)(
                  1,
                  v12,
                  pProps,
                  v7,
                  0,
                  0,
                  &v9);
  }
  else
  {
    LastError = GetLastError();
  }
  ConnectionFromPersistData = LastError;
  if ( LastError > 0 )
    ConnectionFromPersistData = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
  NcFreeNetconProperties(pProps);
  ReleaseObj((struct IUnknown *)v11.lpVtbl);
  if ( v3 )
    FreeLibrary(v3);
  return (unsigned int)ConnectionFromPersistData;
}

```

## disassembly

```asm
0x18005985c  mov     [rsp-8+arg_8], rbx
0x180059861  mov     [rsp-8+arg_10], rsi
0x180059866  push    rbp
0x180059867  push    rdi
0x180059868  push    r14
0x18005986a  lea     rbp, [rsp-170h]
0x180059872  sub     rsp, 270h
0x180059879  mov     rax, cs:__security_cookie
0x180059880  xor     rax, rsp
0x180059883  mov     [rbp+180h+var_20], rax
0x18005988a  mov     rdi, rcx
0x18005988d  mov     [rsp+280h+var_230.lpVtbl], 0
0x180059896  lea     rcx, aWlanuiDll; "wlanui.dll"
0x18005989d  mov     [rsp+280h+pProps], 0
0x1800598a6  call    cs:__imp_LoadLibraryW
0x1800598ac  mov     rsi, rax
0x1800598af  test    rax, rax
0x1800598b2  jnz     short loc_1800598BF
0x1800598b4  call    cs:__imp_GetLastError
0x1800598ba  jmp     loc_1800599CC
0x1800598bf  lea     rdx, aWlanuieditprof; "WlanUIEditProfile"
0x1800598c6  mov     rcx, rsi; hModule
0x1800598c9  call    cs:__imp_GetProcAddress
0x1800598cf  mov     r14, rax
0x1800598d2  test    rax, rax
0x1800598d5  jz      short loc_1800598B4
0x1800598d7  mov     r8d, [rdi+0B0h]; unsigned int
0x1800598de  lea     rax, [rsp+280h+var_230]
0x1800598e3  mov     rdx, [rdi+0A8h]; unsigned __int8 *
0x1800598ea  lea     rcx, [rdi+0B4h]; struct _GUID *
0x1800598f1  mov     [rsp+280h+var_258], 0; int
0x1800598f9  lea     r9, IID_INetConnection; struct _GUID *
0x180059900  mov     [rsp+280h+var_260], rax; struct IUnknown *
0x180059905  call    ?HrGetConnectionFromPersistData@@YAJAEBU_GUID@@PEBEK0PEAPEAXH@Z; HrGetConnectionFromPersistData(_GUID const &,uchar const *,ulong,_GUID const &,void * *,int)
0x18005990a  mov     ebx, eax
0x18005990c  test    eax, eax
0x18005990e  js      loc_1800599DB
0x180059914  mov     rcx, [rsp+280h+var_230.lpVtbl]
0x180059919  test    rcx, rcx
0x18005991c  jz      loc_1800599DB
0x180059922  mov     rax, [rcx]
0x180059925  lea     rdx, [rsp+280h+pProps]
0x18005992a  mov     rax, [rax+38h]
0x18005992e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059933  mov     ebx, eax
0x180059935  test    eax, eax
0x180059937  js      loc_1800599DB
0x18005993d  cmp     qword ptr [rdi+120h], 0
0x180059945  jnz     short loc_180059959
0x180059947  mov     rcx, rdi; this
0x18005994a  call    ?GetWlanConnectionAttributes@CWlanStatEngine@@IEAAJXZ; CWlanStatEngine::GetWlanConnectionAttributes(void)
0x18005994f  mov     ebx, eax
0x180059951  test    eax, eax
0x180059953  js      loc_1800599DB
0x180059959  xor     edx, edx; Val
0x18005995b  lea     rcx, [rsp+280h+var_220]; void *
0x180059960  mov     r8d, 200h; Size
0x180059966  call    memset_0
0x18005996b  mov     r8, [rdi+120h]
0x180059972  lea     rcx, [rsp+280h+var_220]; unsigned __int16 *
0x180059977  add     r8, 8; unsigned __int16 *
0x18005997b  mov     edx, 100h; unsigned __int64
0x180059980  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180059985  mov     ebx, eax
0x180059987  test    eax, eax
0x180059989  js      short loc_1800599DB
0x18005998b  mov     r9, [rdi+0D0h]
0x180059992  lea     rax, [rsp+280h+var_240]
0x180059997  mov     r8, [rsp+280h+pProps]
0x18005999c  lea     rdx, [rsp+280h+var_220]
0x1800599a1  mov     [rsp+280h+var_250], rax
0x1800599a6  mov     ecx, 1
0x1800599ab  mov     qword ptr [rsp+280h+var_258], 0
0x1800599b4  mov     rax, r14
0x1800599b7  mov     dword ptr [rsp+280h+var_260], 0
0x1800599bf  mov     [rsp+280h+var_240], 0
0x1800599c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800599cc  mov     ebx, eax
0x1800599ce  test    eax, eax
0x1800599d0  jle     short loc_1800599DB
0x1800599d2  movzx   ebx, ax
0x1800599d5  or      ebx, 80070000h
0x1800599db  mov     rcx, [rsp+280h+pProps]; pProps
0x1800599e0  call    NcFreeNetconProperties
0x1800599e5  mov     rcx, [rsp+280h+var_230.lpVtbl]; struct IUnknown *
0x1800599ea  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x1800599ef  test    rsi, rsi
0x1800599f2  jz      short loc_1800599FD
0x1800599f4  mov     rcx, rsi; hLibModule
0x1800599f7  call    cs:__imp_FreeLibrary
0x1800599fd  mov     eax, ebx
0x1800599ff  mov     rcx, [rbp+180h+var_20]
0x180059a06  xor     rcx, rsp; StackCookie
0x180059a09  call    __security_check_cookie
0x180059a0e  lea     r11, [rsp+280h+var_10]
0x180059a16  mov     rbx, [r11+28h]
0x180059a1a  mov     rsi, [r11+30h]
0x180059a1e  mov     rsp, r11
0x180059a21  pop     r14
0x180059a23  pop     rdi
0x180059a24  pop     rbp
0x180059a25  retn
```
