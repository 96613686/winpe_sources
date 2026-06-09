# MVConfigurationHelper::GetStringValue(ushort const *,ulong,ulong,ushort const *,ushort *)

- ea: `0x180032750`
- end: `0x1800329f1`
- name: `?GetStringValue@MVConfigurationHelper@@QEAAJPEBGKK0PEAG@Z`
- size: `673`
- prototype: `__int64 __fastcall(MVConfigurationHelper *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, LPBYTE)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180015a60`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800172bc`
- `0x18001dd10`
- `0x18003240c`
- `0x180032750`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800327e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032908`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800329e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800327e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032908`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800329e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800327cf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800327cf`

## string_xrefs

- `0x18003286f`: `MVConfigurationHelper::GetStringValue`
- `0x180032987`: `MVConfigurationHelper::GetStringValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MVConfigurationHelper::GetStringValue(
        MVConfigurationHelper *this,
        unsigned __int16 *a2,
        __int64 a3,
        DWORD a4,
        const unsigned __int16 *a5,
        LPBYTE a6)
{
  int v6; // edi
  int v8; // eax
  int v9; // ebx
  BYTE *v10; // rsi
  int v11; // eax
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  const struct _tlgProvider_t *v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  LPBYTE lpData; // [rsp+20h] [rbp-40h]
  LPBYTE lpDataa; // [rsp+20h] [rbp-40h]
  LPBYTE lpDatab; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v22[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v23; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v24[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v25; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+40h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  Type = a4;
  hKey = (HKEY)a2;
  v6 = a3;
  v8 = a3 & 0xF;
  v9 = 1;
  if ( (a3 & 0xF) != 0 )
  {
    v10 = a6;
    while ( 1 )
    {
      hKey = 0;
      cbData = 512;
      Type = 0;
      if ( MVConfigurationHelper::GetRegKeyHandleAndName(this, v8, a3, &hKey) >= 0
        && RegQueryValueExW(hKey, L"BrandingName", 0, &Type, v10, &cbData) >= 0 )
      {
        break;
      }
      if ( hKey )
        RegCloseKey(hKey);
      v11 = 15 << (4 * v9++);
      v8 = v6 & v11;
      if ( !v8 )
        goto LABEL_8;
    }
    if ( Type == 1 )
    {
      *(_OWORD *)v24 = 0;
      v25 = 0;
      *(_OWORD *)v22 = 0;
      v23 = 0;
      std::vector<unsigned short>::resize(v24);
      std::vector<unsigned short>::resize(v22);
      StringCchPrintfW(v24[0], v24[1] - v24[0], L"GetStringValue from %d: %ws=%ws", 0, L"BrandingName", v10);
      LODWORD(lpDatab) = 201;
      StringCchPrintfW(v22[0], v22[1] - v22[0], L"%S(%d):%s", "MVConfigurationHelper::GetStringValue", lpDatab, v24[0]);
      v16 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v16 > 4u )
      {
        a5 = v22[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v16,
          (__int64)qword_180076170,
          v17,
          v18,
          &a5);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v22);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\utils.cpp",
        (const char *)0x8000FFFFLL,
        (int)lpData);
      if ( hKey )
        RegCloseKey(hKey);
      return 2147549183LL;
    }
  }
  else
  {
LABEL_8:
    *(_OWORD *)v22 = 0;
    v23 = 0;
    *(_OWORD *)v24 = 0;
    v25 = 0;
    std::vector<unsigned short>::resize(v22);
    std::vector<unsigned short>::resize(v24);
    LODWORD(lpData) = v6;
    StringCchPrintfW(
      v22[0],
      v22[1] - v22[0],
      L"ERROR_NOT_FOUND GetStringValue for %ws with rule 0x%08x",
      L"BrandingName",
      lpData);
    LODWORD(lpDataa) = 208;
    StringCchPrintfW(v24[0], v24[1] - v24[0], L"%S(%d):%s", "MVConfigurationHelper::GetStringValue", lpDataa, v22[0]);
    v12 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v12 > 3u )
    {
      hKey = (HKEY)v24[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v12,
        (__int64)word_18007612A,
        v13,
        v14,
        (const unsigned __int16 **)&hKey);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v22);
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x180032750  mov     [rsp-28h+arg_0], rbx
0x180032755  mov     [rsp-28h+Type], r9d
0x18003275a  mov     [rsp-28h+hKey], rdx
0x18003275f  push    rbp
0x180032760  push    rsi
0x180032761  push    rdi
0x180032762  push    r12
0x180032764  push    r14
0x180032766  mov     rbp, rsp
0x180032769  sub     rsp, 60h
0x18003276d  mov     edi, r8d
0x180032770  mov     r14, rcx
0x180032773  mov     eax, r8d
0x180032776  lea     r12, aBrandingname; "BrandingName"
0x18003277d  and     eax, 0Fh
0x180032780  mov     ebx, 1
0x180032785  jz      short loc_180032800
0x180032787  mov     rsi, [rbp+arg_28]
0x18003278b  mov     [rbp+hKey], 0
0x180032793  mov     [rbp+cbData], 200h
0x18003279a  mov     [rbp+Type], 0
0x1800327a1  lea     r9, [rbp+hKey]
0x1800327a5  mov     edx, eax
0x1800327a7  mov     rcx, r14
0x1800327aa  call    ?GetRegKeyHandleAndName@MVConfigurationHelper@@AEAAJW4MVConfigurationReadingLocation@1@QEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MVConfigurationHelper::GetRegKeyHandleAndName(MVConfigurationHelper::MVConfigurationReadingLocation,ushort const * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x1800327af  test    eax, eax
0x1800327b1  js      short loc_1800327DD
0x1800327b3  lea     rax, [rbp+cbData]
0x1800327b7  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800327bc  mov     [rsp+60h+lpData], rsi; int
0x1800327c1  lea     r9, [rbp+Type]; lpType
0x1800327c5  xor     r8d, r8d; lpReserved
0x1800327c8  mov     rdx, r12; lpValueName
0x1800327cb  mov     rcx, [rbp+hKey]; hKey
0x1800327cf  call    cs:__imp_RegQueryValueExW
0x1800327d5  test    eax, eax
0x1800327d7  jns     loc_1800328DB
0x1800327dd  mov     rcx, [rbp+hKey]; hKey
0x1800327e1  test    rcx, rcx
0x1800327e4  jz      short loc_1800327EC
0x1800327e6  call    cs:__imp_RegCloseKey
0x1800327ec  lea     ecx, ds:0[rbx*4]
0x1800327f3  mov     eax, 0Fh
0x1800327f8  shl     eax, cl
0x1800327fa  inc     ebx
0x1800327fc  and     eax, edi
0x1800327fe  jnz     short loc_18003278B
0x180032800  xorps   xmm0, xmm0
0x180032803  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180032808  mov     [rbp+var_20], 0
0x180032810  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180032815  mov     [rbp+var_8], 0
0x18003281d  lea     rcx, [rbp+var_30]
0x180032821  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180032826  lea     rcx, [rbp+var_18]
0x18003282a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003282f  mov     rdx, [rbp+var_30+8]
0x180032833  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180032837  sub     rdx, rcx
0x18003283a  sar     rdx, 1; unsigned __int64
0x18003283d  mov     dword ptr [rsp+60h+lpData], edi
0x180032841  mov     r9, r12
0x180032844  lea     r8, aErrorNotFoundG; "ERROR_NOT_FOUND GetStringValue for %ws "...
0x18003284b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032850  mov     rdx, [rbp+var_18+8]
0x180032854  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180032858  sub     rdx, rcx
0x18003285b  sar     rdx, 1; unsigned __int64
0x18003285e  mov     rax, [rbp+var_30]
0x180032862  mov     [rsp+60h+lpcbData], rax
0x180032867  mov     dword ptr [rsp+60h+lpData], 0D0h
0x18003286f  lea     r9, aMvconfiguratio_0; "MVConfigurationHelper::GetStringValue"
0x180032876  lea     r8, aSDS; "%S(%d):%s"
0x18003287d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032882  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180032887  mov     ecx, [rax]
0x180032889  cmp     ecx, 3
0x18003288c  jbe     short loc_1800328AF
0x18003288e  mov     rcx, [rbp+var_18]
0x180032892  mov     [rbp+hKey], rcx
0x180032896  lea     rcx, [rbp+hKey]
0x18003289a  mov     [rsp+60h+lpData], rcx
0x18003289f  lea     rdx, word_18007612A
0x1800328a6  mov     rcx, rax
0x1800328a9  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800328ae  nop
0x1800328af  lea     rcx, [rbp+var_18]
0x1800328b3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800328b8  nop
0x1800328b9  lea     rcx, [rbp+var_30]
0x1800328bd  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800328c2  mov     eax, 80070490h
0x1800328c7  mov     rbx, [rsp+60h+arg_0]
0x1800328cf  add     rsp, 60h
0x1800328d3  pop     r14
0x1800328d5  pop     r12
0x1800328d7  pop     rdi
0x1800328d8  pop     rsi
0x1800328d9  pop     rbp
0x1800328da  retn
0x1800328db  cmp     [rbp+Type], 1
0x1800328df  jz      short loc_180032912
0x1800328e1  mov     rcx, [rbp+28h]; this
0x1800328e5  mov     ebx, 8000FFFFh
0x1800328ea  mov     r9d, ebx; char *
0x1800328ed  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800328f4  mov     edx, 0C7h; void *
0x1800328f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800328fe  nop
0x1800328ff  mov     rcx, [rbp+hKey]; hKey
0x180032903  test    rcx, rcx
0x180032906  jz      short loc_18003290E
0x180032908  call    cs:__imp_RegCloseKey
0x18003290e  mov     eax, ebx
0x180032910  jmp     short loc_1800328C7
0x180032912  xorps   xmm0, xmm0
0x180032915  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18003291a  mov     [rbp+var_8], 0
0x180032922  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180032927  mov     [rbp+var_20], 0
0x18003292f  lea     rcx, [rbp+var_18]
0x180032933  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180032938  lea     rcx, [rbp+var_30]
0x18003293c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180032941  mov     rdx, [rbp+var_18+8]
0x180032945  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180032949  sub     rdx, rcx
0x18003294c  sar     rdx, 1; unsigned __int64
0x18003294f  mov     [rsp+60h+lpcbData], rsi
0x180032954  mov     [rsp+60h+lpData], r12
0x180032959  xor     r9d, r9d
0x18003295c  lea     r8, aGetstringvalue; "GetStringValue from %d: %ws=%ws"
0x180032963  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032968  mov     rdx, [rbp+var_30+8]
0x18003296c  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180032970  sub     rdx, rcx
0x180032973  sar     rdx, 1; unsigned __int64
0x180032976  mov     rax, [rbp+var_18]
0x18003297a  mov     [rsp+60h+lpcbData], rax
0x18003297f  mov     dword ptr [rsp+60h+lpData], 0C9h
0x180032987  lea     r9, aMvconfiguratio_0; "MVConfigurationHelper::GetStringValue"
0x18003298e  lea     r8, aSDS; "%S(%d):%s"
0x180032995  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003299a  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003299f  mov     ecx, [rax]
0x1800329a1  cmp     ecx, 4
0x1800329a4  jbe     short loc_1800329C7
0x1800329a6  mov     rcx, [rbp+var_30]
0x1800329aa  mov     [rbp+arg_20], rcx
0x1800329ae  lea     rcx, [rbp+arg_20]
0x1800329b2  mov     [rsp+60h+lpData], rcx
0x1800329b7  lea     rdx, qword_180076170
0x1800329be  mov     rcx, rax
0x1800329c1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800329c6  nop
0x1800329c7  lea     rcx, [rbp+var_30]
0x1800329cb  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800329d0  nop
0x1800329d1  lea     rcx, [rbp+var_18]
0x1800329d5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800329da  nop
0x1800329db  mov     rcx, [rbp+hKey]; hKey
0x1800329df  test    rcx, rcx
0x1800329e2  jz      short loc_1800329EA
0x1800329e4  call    cs:__imp_RegCloseKey
0x1800329ea  xor     eax, eax
0x1800329ec  jmp     loc_1800328C7
```
