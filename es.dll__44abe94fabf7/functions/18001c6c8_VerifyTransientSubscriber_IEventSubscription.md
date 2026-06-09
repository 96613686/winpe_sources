# VerifyTransientSubscriber(IEventSubscription *)

- ea: `0x18001c6c8`
- end: `0x18001c8e9`
- name: `?VerifyTransientSubscriber@@YAXPEAUIEventSubscription@@@Z`
- size: `545`
- prototype: `void __fastcall(struct IEventSubscription *)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b698`
- `0x18001b860`
- `0x18001c110`

## callees

- `0x180003d54`
- `0x180008938`
- `0x180016680`
- `0x180018340`
- `0x18001c6c8`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001c888`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c893`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c89e`
- `OLEAUT32!__imp_SysFreeString` at `0x180044a29`
- `OLEAUT32!__imp_SysFreeString` at `0x180044a33`
- `OLEAUT32!__imp_SysFreeString` at `0x180044a3d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c888`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c893`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c89e`
- `OLEAUT32!__imp_SysFreeString` at `0x180044a29`
- `OLEAUT32!__imp_SysFreeString` at `0x180044a33`
- `OLEAUT32!__imp_SysFreeString` at `0x180044a3d`

## string_xrefs

- `0x18001c727`: `com\complus\src\events\tier1\agent.cpp`
- `0x18001c798`: `com\complus\src\events\tier1\agent.cpp`
- `0x18001c7cf`: `com\complus\src\events\tier1\agent.cpp`
- `0x18001c806`: `com\complus\src\events\tier1\agent.cpp`
- `0x18001c842`: `com\complus\src\events\tier1\agent.cpp`
- `0x18001c876`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c
void __fastcall VerifyTransientSubscriber(struct IEventSubscription *a1)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  __int64 v5; // r9
  int v6; // eax
  int v7; // eax
  __int64 v8; // [rsp+30h] [rbp-138h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-130h] BYREF
  BSTR v10; // [rsp+40h] [rbp-128h] BYREF
  BSTR v11; // [rsp+48h] [rbp-120h] BYREF
  struct IEventSystemTier2 *v12; // [rsp+50h] [rbp-118h] BYREF
  unsigned __int16 v13[120]; // [rsp+60h] [rbp-108h] BYREF

  bstrString = 0;
  v10 = 0;
  v11 = 0;
  v8 = 0;
  v12 = 0;
  if ( !a1 )
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1816u, 0x80001203, 0x12u);
  if ( (int)ConnectToEventSystemTier2(3u, 0x40u, (IUnknown **)&v12) >= 0
    && ((__int64 (__fastcall *)(struct IEventSubscription *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &IID_IEventSubscription3,
         &v8) >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 56LL))(v8, &bstrString);
    if ( v2 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1827u, 0x12u, v2);
    v3 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 392LL))(v8, &v10);
    if ( v3 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x182Au, 0x12u, v3);
    v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 408LL))(v8, &v11);
    if ( v4 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x182Du, 0x12u, v4);
    v6 = ConcatenateECID_PARTID_APPID_WSZ(bstrString, v10, v11, v5, v13);
    if ( v6 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1834u, 0x12u, v6);
    v7 = (*(__int64 (__fastcall **)(struct IEventSystemTier2 *, unsigned __int16 *))(*(_QWORD *)v12 + 96LL))(v12, v13);
    if ( v7 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1837u, 0x12u, v7);
  }
  SysFreeString(bstrString);
  SysFreeString(v10);
  SysFreeString(v11);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v12 )
    (*(void (__fastcall **)(struct IEventSystemTier2 *))(*(_QWORD *)v12 + 16LL))(v12);
}

```

## disassembly

```asm
0x18001c6c8  push    rsi
0x18001c6ca  sub     rsp, 160h
0x18001c6d1  mov     rax, cs:__security_cookie
0x18001c6d8  xor     rax, rsp
0x18001c6db  mov     [rsp+168h+var_18], rax
0x18001c6e3  mov     rsi, rcx
0x18001c6e6  mov     [rsp+168h+bstrString], 0
0x18001c6ef  mov     [rsp+168h+var_128], 0
0x18001c6f8  mov     [rsp+168h+var_120], 0
0x18001c701  mov     [rsp+168h+var_138], 0
0x18001c70a  mov     [rsp+168h+var_118], 0
0x18001c713  test    rcx, rcx
0x18001c716  jnz     short loc_18001C734
0x18001c718  mov     edx, 1816h; unsigned int
0x18001c71d  lea     r9d, [rcx+12h]; unsigned __int16
0x18001c721  mov     r8d, 80001203h; unsigned int
0x18001c727  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18001c72e  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001c733  nop
0x18001c734  lea     r8, [rsp+168h+var_118]; struct IEventSystemTier2 **
0x18001c739  mov     edx, 40h ; '@'; dwCapabilities
0x18001c73e  lea     ecx, [rdx-3Dh]; dwImpLevel
0x18001c741  call    ?ConnectToEventSystemTier2@@YAJKKPEAPEAUIEventSystemTier2@@@Z; ConnectToEventSystemTier2(ulong,ulong,IEventSystemTier2 * *)
0x18001c746  test    eax, eax
0x18001c748  js      loc_18001C883
0x18001c74e  mov     rax, [rsi]
0x18001c751  lea     r8, [rsp+168h+var_138]
0x18001c756  lea     rdx, IID_IEventSubscription3
0x18001c75d  mov     rcx, rsi
0x18001c760  mov     rax, [rax]
0x18001c763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c768  test    eax, eax
0x18001c76a  js      loc_18001C883
0x18001c770  mov     rcx, [rsp+168h+var_138]
0x18001c775  mov     rax, [rcx]
0x18001c778  lea     rdx, [rsp+168h+bstrString]
0x18001c77d  mov     rax, [rax+38h]
0x18001c781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c786  test    eax, eax
0x18001c788  jns     short loc_18001C7A4
0x18001c78a  mov     r8d, 12h; unsigned __int16
0x18001c790  mov     r9d, eax; int
0x18001c793  mov     edx, 1827h; unsigned int
0x18001c798  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18001c79f  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001c7a4  mov     rcx, [rsp+168h+var_138]
0x18001c7a9  mov     rax, [rcx]
0x18001c7ac  lea     rdx, [rsp+168h+var_128]
0x18001c7b1  mov     rax, [rax+188h]
0x18001c7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7bd  test    eax, eax
0x18001c7bf  jns     short loc_18001C7DB
0x18001c7c1  mov     r8d, 12h; unsigned __int16
0x18001c7c7  mov     r9d, eax; int
0x18001c7ca  mov     edx, 182Ah; unsigned int
0x18001c7cf  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18001c7d6  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001c7db  mov     rcx, [rsp+168h+var_138]
0x18001c7e0  mov     rax, [rcx]
0x18001c7e3  lea     rdx, [rsp+168h+var_120]
0x18001c7e8  mov     rax, [rax+198h]
0x18001c7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7f4  test    eax, eax
0x18001c7f6  jns     short loc_18001C812
0x18001c7f8  mov     r8d, 12h; unsigned __int16
0x18001c7fe  mov     r9d, eax; int
0x18001c801  mov     edx, 182Dh; unsigned int
0x18001c806  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18001c80d  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001c812  lea     rax, [rsp+168h+var_108]
0x18001c817  mov     [rsp+168h+var_148], rax; unsigned __int16 *
0x18001c81c  mov     r8, [rsp+168h+var_120]; LPCOLESTR
0x18001c821  mov     rdx, [rsp+168h+var_128]; unsigned __int16 *
0x18001c826  mov     rcx, [rsp+168h+bstrString]; lpsz
0x18001c82b  call    ?ConcatenateECID_PARTID_APPID_WSZ@@YAJPEAG00K0@Z; ConcatenateECID_PARTID_APPID_WSZ(ushort *,ushort *,ushort *,ulong,ushort *)
0x18001c830  test    eax, eax
0x18001c832  jns     short loc_18001C84E
0x18001c834  mov     r8d, 12h; unsigned __int16
0x18001c83a  mov     r9d, eax; int
0x18001c83d  mov     edx, 1834h; unsigned int
0x18001c842  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18001c849  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001c84e  mov     rcx, [rsp+168h+var_118]
0x18001c853  mov     rax, [rcx]
0x18001c856  lea     rdx, [rsp+168h+var_108]
0x18001c85b  mov     rax, [rax+60h]
0x18001c85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c864  test    eax, eax
0x18001c866  jns     short loc_18001C883
0x18001c868  mov     r8d, 12h; unsigned __int16
0x18001c86e  mov     r9d, eax; int
0x18001c871  mov     edx, 1837h; unsigned int
0x18001c876  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18001c87d  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001c882  nop
0x18001c883  mov     rcx, [rsp+168h+bstrString]; bstrString
0x18001c888  call    cs:__imp_SysFreeString
0x18001c88e  mov     rcx, [rsp+168h+var_128]; bstrString
0x18001c893  call    cs:__imp_SysFreeString
0x18001c899  mov     rcx, [rsp+168h+var_120]; bstrString
0x18001c89e  call    cs:__imp_SysFreeString
0x18001c8a4  mov     rcx, [rsp+168h+var_138]
0x18001c8a9  test    rcx, rcx
0x18001c8ac  jz      short loc_18001C8BA
0x18001c8ae  mov     rax, [rcx]
0x18001c8b1  mov     rax, [rax+10h]
0x18001c8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8ba  mov     rcx, [rsp+168h+var_118]
0x18001c8bf  test    rcx, rcx
0x18001c8c2  jz      short loc_18001C8D0
0x18001c8c4  mov     rax, [rcx]
0x18001c8c7  mov     rax, [rax+10h]
0x18001c8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8d0  mov     rcx, [rsp+168h+var_18]
0x18001c8d8  xor     rcx, rsp; StackCookie
0x18001c8db  call    __security_check_cookie
0x18001c8e0  add     rsp, 160h
0x18001c8e7  pop     rsi
0x18001c8e8  retn
0x180044a1c  push    rbp
0x180044a1e  sub     rsp, 30h
0x180044a22  mov     rbp, rdx
0x180044a25  mov     rcx, [rbp+38h]; bstrString
0x180044a29  call    cs:__imp_SysFreeString
0x180044a2f  mov     rcx, [rbp+40h]; bstrString
0x180044a33  call    cs:__imp_SysFreeString
0x180044a39  mov     rcx, [rbp+48h]; bstrString
0x180044a3d  call    cs:__imp_SysFreeString
0x180044a43  mov     rcx, [rbp+30h]
0x180044a47  test    rcx, rcx
0x180044a4a  jz      short loc_180044A59
0x180044a4c  mov     rax, [rcx]
0x180044a4f  mov     rax, [rax+10h]
0x180044a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a58  nop
0x180044a59  mov     rcx, [rbp+50h]
0x180044a5d  test    rcx, rcx
0x180044a60  jz      short loc_180044A6F
0x180044a62  mov     rax, [rcx]
0x180044a65  mov     rax, [rax+10h]
0x180044a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a6e  nop
0x180044a6f  add     rsp, 30h
0x180044a73  pop     rbp
0x180044a74  retn
```
