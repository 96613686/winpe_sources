# CCellularSettingHelperCommon::DisconnectPublisher(void)

- ea: `0x180046e2c`
- end: `0x180046fab`
- name: `?DisconnectPublisher@CCellularSettingHelperCommon@@QEAAXXZ`
- size: `383`
- prototype: `void __fastcall(CCellularSettingHelperCommon *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001b2c0`

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18001105c`
- `0x1800172bc`
- `0x18001dd10`
- `0x180046e2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046f93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046f93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046e48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046e48`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180046e7e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180046e7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046f84`

## string_xrefs

- `0x180046f1f`: `CCellularSettingHelperCommon::DisconnectPublisher`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CCellularSettingHelperCommon::DisconnectPublisher(CCellularSettingHelperCommon *this)
{
  unsigned __int16 *v2; // rdi
  bool v3; // bl
  void *v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  void *v8; // rcx
  int v9; // [rsp+20h] [rbp-40h]
  LPOLESTR lpsz[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v11; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v12[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v13; // [rsp+58h] [rbp-8h]
  LPVOID pv; // [rsp+70h] [rbp+10h] BYREF
  unsigned __int16 *v15; // [rsp+78h] [rbp+18h] BYREF

  v2 = (unsigned __int16 *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v15 = v2;
  *((_QWORD *)this + 3) = 0;
  pv = 0;
  lpsz[0] = (LPOLESTR)&pv;
  lpsz[1] = 0;
  LOBYTE(v11) = 1;
  v3 = StringFromCLSID((const IID *const)((char *)this + 8), &lpsz[1]) >= 0;
  if ( (_BYTE)v11 )
  {
    v4 = *(void **)lpsz[0];
    *(_QWORD *)lpsz[0] = lpsz[1];
    if ( v4 )
      CoTaskMemFree(v4);
  }
  if ( v3 )
  {
    *(_OWORD *)v12 = 0;
    v13 = 0;
    *(_OWORD *)lpsz = 0;
    v11 = 0;
    std::vector<unsigned short>::resize(v12);
    std::vector<unsigned short>::resize(lpsz);
    StringCchPrintfW(v12[0], v12[1] - v12[0], L"Disconnecting publisher for interface %s", pv);
    v9 = 79;
    StringCchPrintfW(
      lpsz[0],
      lpsz[1] - lpsz[0],
      L"%S(%d):%s",
      "CCellularSettingHelperCommon::DisconnectPublisher",
      v9,
      v12[0]);
    v5 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v15 = lpsz[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v5,
        (__int64)&word_18007934E,
        v6,
        v7,
        (const unsigned __int16 **)&v15);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)lpsz);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v12);
  }
  v8 = pv;
  pv = 0;
  if ( v8 )
    CoTaskMemFree(v8);
  if ( v2 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v2);
}

```

## disassembly

```asm
0x180046e2c  mov     [rsp-8+arg_10], rbx
0x180046e31  mov     [rsp-8+arg_18], rdi
0x180046e36  push    rbp
0x180046e37  mov     rbp, rsp
0x180046e3a  sub     rsp, 60h
0x180046e3e  mov     rbx, rcx
0x180046e41  lea     rdi, [rcx+30h]
0x180046e45  mov     rcx, rdi; lpCriticalSection
0x180046e48  call    cs:__imp_EnterCriticalSection
0x180046e4e  mov     [rbp+arg_8], rdi
0x180046e52  mov     qword ptr [rbx+18h], 0
0x180046e5a  mov     [rbp+pv], 0
0x180046e62  lea     rax, [rbp+pv]
0x180046e66  mov     [rbp+lpsz], rax
0x180046e6a  mov     [rbp+lpsz+8], 0
0x180046e72  mov     byte ptr [rbp+var_20], 1
0x180046e76  lea     rcx, [rbx+8]; rclsid
0x180046e7a  lea     rdx, [rbp+lpsz+8]; lplpsz
0x180046e7e  call    cs:__imp_StringFromCLSID
0x180046e84  mov     ebx, eax
0x180046e86  shr     ebx, 1Fh
0x180046e89  xor     bl, 1
0x180046e8c  cmp     byte ptr [rbp+var_20], 0
0x180046e90  jz      short loc_180046EAB
0x180046e92  mov     r8, [rbp+lpsz]
0x180046e96  mov     rcx, [r8]; pv
0x180046e99  mov     rdx, [rbp+lpsz+8]
0x180046e9d  mov     [r8], rdx
0x180046ea0  test    rcx, rcx
0x180046ea3  jz      short loc_180046EAB
0x180046ea5  call    cs:__imp_CoTaskMemFree
0x180046eab  test    bl, bl
0x180046ead  jz      loc_180046F73
0x180046eb3  xorps   xmm0, xmm0
0x180046eb6  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180046ebb  mov     [rbp+var_8], 0
0x180046ec3  movdqu  xmmword ptr [rbp+lpsz], xmm0
0x180046ec8  mov     [rbp+var_20], 0
0x180046ed0  lea     rcx, [rbp+var_18]
0x180046ed4  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180046ed9  lea     rcx, [rbp+lpsz]
0x180046edd  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180046ee2  mov     rdx, [rbp+var_18+8]
0x180046ee6  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180046eea  sub     rdx, rcx
0x180046eed  sar     rdx, 1; unsigned __int64
0x180046ef0  mov     r9, [rbp+pv]
0x180046ef4  lea     r8, aDisconnectingP; "Disconnecting publisher for interface %"...
0x180046efb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046f00  mov     rdx, [rbp+lpsz+8]
0x180046f04  mov     rcx, [rbp+lpsz]; unsigned __int16 *
0x180046f08  sub     rdx, rcx
0x180046f0b  sar     rdx, 1; unsigned __int64
0x180046f0e  mov     rax, [rbp+var_18]
0x180046f12  mov     [rsp+60h+var_38], rax
0x180046f17  mov     dword ptr [rsp+60h+var_40], 4Fh ; 'O'
0x180046f1f  lea     r9, aCcellularsetti_15; "CCellularSettingHelperCommon::Disconnec"...
0x180046f26  lea     r8, aSDS; "%S(%d):%s"
0x180046f2d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046f32  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180046f37  mov     ecx, [rax]
0x180046f39  cmp     ecx, 5
0x180046f3c  jbe     short loc_180046F5F
0x180046f3e  mov     rcx, [rbp+lpsz]
0x180046f42  mov     [rbp+arg_8], rcx
0x180046f46  lea     rcx, [rbp+arg_8]
0x180046f4a  mov     [rsp+60h+var_40], rcx
0x180046f4f  lea     rdx, word_18007934E
0x180046f56  mov     rcx, rax
0x180046f59  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180046f5e  nop
0x180046f5f  lea     rcx, [rbp+lpsz]
0x180046f63  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046f68  nop
0x180046f69  lea     rcx, [rbp+var_18]
0x180046f6d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046f72  nop
0x180046f73  mov     rcx, [rbp+pv]; pv
0x180046f77  mov     [rbp+pv], 0
0x180046f7f  test    rcx, rcx
0x180046f82  jz      short loc_180046F8B
0x180046f84  call    cs:__imp_CoTaskMemFree
0x180046f8a  nop
0x180046f8b  test    rdi, rdi
0x180046f8e  jz      short loc_180046F99
0x180046f90  mov     rcx, rdi; lpCriticalSection
0x180046f93  call    cs:__imp_LeaveCriticalSection
0x180046f99  lea     r11, [rsp+60h+var_s0]
0x180046f9e  mov     rbx, [r11+20h]
0x180046fa2  mov     rdi, [r11+28h]
0x180046fa6  mov     rsp, r11
0x180046fa9  pop     rbp
0x180046faa  retn
```
