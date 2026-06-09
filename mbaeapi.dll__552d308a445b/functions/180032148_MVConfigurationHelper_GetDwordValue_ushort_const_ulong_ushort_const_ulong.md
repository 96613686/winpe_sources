# MVConfigurationHelper::GetDwordValue(ushort const *,ulong,ushort const *,ulong &)

- ea: `0x180032148`
- end: `0x180032404`
- name: `?GetDwordValue@MVConfigurationHelper@@QEAAJPEBGK0AEAK@Z`
- size: `700`
- prototype: `__int64 __fastcall(MVConfigurationHelper *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, LPBYTE)`
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
- `0x180032148`
- `0x18003240c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800321f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003231a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800323f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800321f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003231a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800323f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800321d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800321d1`

## string_xrefs

- `0x180032281`: `MVConfigurationHelper::GetDwordValue`
- `0x18003239a`: `MVConfigurationHelper::GetDwordValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MVConfigurationHelper::GetDwordValue(
        MVConfigurationHelper *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        LPBYTE a5)
{
  int v5; // edi
  BYTE *v7; // rsi
  int v8; // eax
  int v9; // ebx
  LSTATUS v10; // eax
  bool v11; // sf
  int v12; // eax
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  const struct _tlgProvider_t *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  LPBYTE lpData; // [rsp+20h] [rbp-40h]
  LPBYTE lpDataa; // [rsp+20h] [rbp-40h]
  LPBYTE lpDatab; // [rsp+20h] [rbp-40h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-38h]
  unsigned __int16 *v24[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v25; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v26[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v27; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 *cbData; // [rsp+A8h] [rbp+48h] BYREF

  cbData = a4;
  hKey = (HKEY)a2;
  v5 = a3;
  v7 = a5;
  *(_DWORD *)a5 = 0;
  v8 = a3 & 0xF;
  v9 = 1;
  if ( (a3 & 0xF) != 0 )
  {
    while ( 1 )
    {
      hKey = 0;
      LODWORD(cbData) = 4;
      Type = 0;
      if ( MVConfigurationHelper::GetRegKeyHandleAndName(this, v8, a3, &hKey) >= 0 )
      {
        v10 = RegQueryValueExW(hKey, L"UseBrandingNameOnRoaming", 0, &Type, v7, (LPDWORD)&cbData);
        v11 = v10 < 0;
        if ( v10 > 0 )
          v11 = 1;
        if ( !v11 )
          break;
      }
      if ( hKey )
        RegCloseKey(hKey);
      v12 = 15 << (4 * v9++);
      v8 = v5 & v12;
      if ( !v8 )
        goto LABEL_9;
    }
    if ( Type == 4 )
    {
      *(_OWORD *)v26 = 0;
      v27 = 0;
      *(_OWORD *)v24 = 0;
      v25 = 0;
      std::vector<unsigned short>::resize(v26);
      std::vector<unsigned short>::resize(v24);
      LODWORD(lpcbData) = *(_DWORD *)v7;
      StringCchPrintfW(
        v26[0],
        v26[1] - v26[0],
        L"GetDwordValue from %d: %ws=0x%08x",
        0,
        L"UseBrandingNameOnRoaming",
        lpcbData);
      LODWORD(lpDatab) = 171;
      StringCchPrintfW(v24[0], v24[1] - v24[0], L"%S(%d):%s", "MVConfigurationHelper::GetDwordValue", lpDatab, v26[0]);
      v17 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v17 > 4u )
      {
        a5 = (LPBYTE)v24[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v17,
          (__int64)qword_180076190,
          v18,
          v19,
          (const unsigned __int16 **)&a5);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9,
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
LABEL_9:
    *(_OWORD *)v24 = 0;
    v25 = 0;
    *(_OWORD *)v26 = 0;
    v27 = 0;
    std::vector<unsigned short>::resize(v24);
    std::vector<unsigned short>::resize(v26);
    LODWORD(lpData) = v5;
    StringCchPrintfW(
      v24[0],
      v24[1] - v24[0],
      L"ERROR_NOT_FOUND GetDwordValue for %ws with rule 0x%08x",
      L"UseBrandingNameOnRoaming",
      lpData);
    LODWORD(lpDataa) = 178;
    StringCchPrintfW(v26[0], v26[1] - v26[0], L"%S(%d):%s", "MVConfigurationHelper::GetDwordValue", lpDataa, v24[0]);
    v13 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v13 > 3u )
    {
      cbData = v26[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v13,
        (__int64)byte_18007614D,
        v14,
        v15,
        (const unsigned __int16 **)&cbData);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x180032148  mov     [rsp-28h+arg_0], rbx
0x18003214d  mov     [rsp-28h+cbData], r9
0x180032152  mov     [rsp-28h+hKey], rdx
0x180032157  push    rbp
0x180032158  push    rsi
0x180032159  push    rdi
0x18003215a  push    r12
0x18003215c  push    r14
0x18003215e  mov     rbp, rsp
0x180032161  sub     rsp, 60h
0x180032165  mov     edi, r8d
0x180032168  mov     r14, rcx
0x18003216b  mov     rsi, [rbp+arg_20]
0x18003216f  mov     dword ptr [rsi], 0
0x180032175  mov     eax, r8d
0x180032178  lea     r12, ValueName; "UseBrandingNameOnRoaming"
0x18003217f  and     eax, 0Fh
0x180032182  mov     ebx, 1
0x180032187  jz      loc_180032212
0x18003218d  mov     [rbp+hKey], 0
0x180032195  mov     dword ptr [rbp+cbData], 4
0x18003219c  mov     [rbp+Type], 0
0x1800321a3  lea     r9, [rbp+hKey]
0x1800321a7  mov     edx, eax
0x1800321a9  mov     rcx, r14
0x1800321ac  call    ?GetRegKeyHandleAndName@MVConfigurationHelper@@AEAAJW4MVConfigurationReadingLocation@1@QEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MVConfigurationHelper::GetRegKeyHandleAndName(MVConfigurationHelper::MVConfigurationReadingLocation,ushort const * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x1800321b1  test    eax, eax
0x1800321b3  js      short loc_1800321EB
0x1800321b5  lea     rax, [rbp+cbData]
0x1800321b9  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800321be  mov     [rsp+60h+lpData], rsi; int
0x1800321c3  lea     r9, [rbp+Type]; lpType
0x1800321c7  xor     r8d, r8d; lpReserved
0x1800321ca  mov     rdx, r12; lpValueName
0x1800321cd  mov     rcx, [rbp+hKey]; hKey
0x1800321d1  call    cs:__imp_RegQueryValueExW
0x1800321d7  test    eax, eax
0x1800321d9  jle     short loc_1800321E5
0x1800321db  movzx   eax, ax
0x1800321de  or      eax, 80070000h
0x1800321e3  test    eax, eax
0x1800321e5  jns     loc_1800322ED
0x1800321eb  mov     rcx, [rbp+hKey]; hKey
0x1800321ef  test    rcx, rcx
0x1800321f2  jz      short loc_1800321FA
0x1800321f4  call    cs:__imp_RegCloseKey
0x1800321fa  lea     ecx, ds:0[rbx*4]
0x180032201  mov     eax, 0Fh
0x180032206  shl     eax, cl
0x180032208  inc     ebx
0x18003220a  and     eax, edi
0x18003220c  jnz     loc_18003218D
0x180032212  xorps   xmm0, xmm0
0x180032215  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18003221a  mov     [rbp+var_20], 0
0x180032222  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180032227  mov     [rbp+var_8], 0
0x18003222f  lea     rcx, [rbp+var_30]
0x180032233  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180032238  lea     rcx, [rbp+var_18]
0x18003223c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180032241  mov     rdx, [rbp+var_30+8]
0x180032245  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180032249  sub     rdx, rcx
0x18003224c  sar     rdx, 1; unsigned __int64
0x18003224f  mov     dword ptr [rsp+60h+lpData], edi
0x180032253  mov     r9, r12
0x180032256  lea     r8, aErrorNotFoundG_0; "ERROR_NOT_FOUND GetDwordValue for %ws w"...
0x18003225d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032262  mov     rdx, [rbp+var_18+8]
0x180032266  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18003226a  sub     rdx, rcx
0x18003226d  sar     rdx, 1; unsigned __int64
0x180032270  mov     rax, [rbp+var_30]
0x180032274  mov     [rsp+60h+lpcbData], rax
0x180032279  mov     dword ptr [rsp+60h+lpData], 0B2h
0x180032281  lea     r9, aMvconfiguratio; "MVConfigurationHelper::GetDwordValue"
0x180032288  lea     r8, aSDS; "%S(%d):%s"
0x18003228f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032294  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180032299  mov     ecx, [rax]
0x18003229b  cmp     ecx, 3
0x18003229e  jbe     short loc_1800322C1
0x1800322a0  mov     rcx, [rbp+var_18]
0x1800322a4  mov     [rbp+cbData], rcx
0x1800322a8  lea     rcx, [rbp+cbData]
0x1800322ac  mov     [rsp+60h+lpData], rcx
0x1800322b1  lea     rdx, byte_18007614D
0x1800322b8  mov     rcx, rax
0x1800322bb  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800322c0  nop
0x1800322c1  lea     rcx, [rbp+var_18]
0x1800322c5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800322ca  nop
0x1800322cb  lea     rcx, [rbp+var_30]
0x1800322cf  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800322d4  mov     eax, 80070490h
0x1800322d9  mov     rbx, [rsp+60h+arg_0]
0x1800322e1  add     rsp, 60h
0x1800322e5  pop     r14
0x1800322e7  pop     r12
0x1800322e9  pop     rdi
0x1800322ea  pop     rsi
0x1800322eb  pop     rbp
0x1800322ec  retn
0x1800322ed  cmp     [rbp+Type], 4
0x1800322f1  jz      short loc_180032324
0x1800322f3  mov     rcx, [rbp+28h]; this
0x1800322f7  mov     ebx, 8000FFFFh
0x1800322fc  mov     r9d, ebx; char *
0x1800322ff  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180032306  mov     edx, 0A9h; void *
0x18003230b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032310  nop
0x180032311  mov     rcx, [rbp+hKey]; hKey
0x180032315  test    rcx, rcx
0x180032318  jz      short loc_180032320
0x18003231a  call    cs:__imp_RegCloseKey
0x180032320  mov     eax, ebx
0x180032322  jmp     short loc_1800322D9
0x180032324  xorps   xmm0, xmm0
0x180032327  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18003232c  mov     [rbp+var_8], 0
0x180032334  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180032339  mov     [rbp+var_20], 0
0x180032341  lea     rcx, [rbp+var_18]
0x180032345  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003234a  lea     rcx, [rbp+var_30]
0x18003234e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180032353  mov     rdx, [rbp+var_18+8]
0x180032357  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18003235b  sub     rdx, rcx
0x18003235e  sar     rdx, 1; unsigned __int64
0x180032361  mov     eax, [rsi]
0x180032363  mov     dword ptr [rsp+60h+lpcbData], eax
0x180032367  mov     [rsp+60h+lpData], r12
0x18003236c  xor     r9d, r9d
0x18003236f  lea     r8, aGetdwordvalueF; "GetDwordValue from %d: %ws=0x%08x"
0x180032376  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003237b  mov     rdx, [rbp+var_30+8]
0x18003237f  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180032383  sub     rdx, rcx
0x180032386  sar     rdx, 1; unsigned __int64
0x180032389  mov     rax, [rbp+var_18]
0x18003238d  mov     [rsp+60h+lpcbData], rax
0x180032392  mov     dword ptr [rsp+60h+lpData], 0ABh
0x18003239a  lea     r9, aMvconfiguratio; "MVConfigurationHelper::GetDwordValue"
0x1800323a1  lea     r8, aSDS; "%S(%d):%s"
0x1800323a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800323ad  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800323b2  mov     ecx, [rax]
0x1800323b4  cmp     ecx, 4
0x1800323b7  jbe     short loc_1800323DA
0x1800323b9  mov     rcx, [rbp+var_30]
0x1800323bd  mov     [rbp+arg_20], rcx
0x1800323c1  lea     rcx, [rbp+arg_20]
0x1800323c5  mov     [rsp+60h+lpData], rcx
0x1800323ca  lea     rdx, qword_180076190
0x1800323d1  mov     rcx, rax
0x1800323d4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800323d9  nop
0x1800323da  lea     rcx, [rbp+var_30]
0x1800323de  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800323e3  nop
0x1800323e4  lea     rcx, [rbp+var_18]
0x1800323e8  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800323ed  nop
0x1800323ee  mov     rcx, [rbp+hKey]; hKey
0x1800323f2  test    rcx, rcx
0x1800323f5  jz      short loc_1800323FD
0x1800323f7  call    cs:__imp_RegCloseKey
0x1800323fd  xor     eax, eax
0x1800323ff  jmp     loc_1800322D9
```
