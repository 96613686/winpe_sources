# MVConfigurationHelper::GetRegKeyHandleAndName(MVConfigurationHelper::MVConfigurationReadingLocation,ushort const * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x18003240c`
- end: `0x180032749`
- name: `?GetRegKeyHandleAndName@MVConfigurationHelper@@AEAAJW4MVConfigurationReadingLocation@1@QEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `829`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180032148`
- `0x180032750`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180002f68`
- `0x180009ffc`
- `0x18001105c`
- `0x1800172bc`
- `0x18001dd10`
- `0x18003240c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800326ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800326ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032711`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032711`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800326e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800326e6`
- `MobileNetworking!GetPersistentRegPath` at `0x18003245a`
- `MobileNetworking!GetPersistentRegPath` at `0x18003245a`

## string_xrefs

- `0x180032588`: `\IMSISpecific`
- `0x18003249d`: `\IMSISpecific\Default`
- `0x180032526`: `MVConfigurationHelper::GetRegKeyHandleAndName`
- `0x180032622`: `MVConfigurationHelper::GetRegKeyHandleAndName`
- `0x1800324f8`: `Asking for per-ICCID value but ICCID is not ready yet.`
- `0x1800325f4`: `Asking for per-IMSI value of IMSI is not ready yet.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall MVConfigurationHelper::GetRegKeyHandleAndName(_WORD *a1, int a2, __int64 a3, HKEY *a4)
{
  int result; // eax
  bool v8; // sf
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  const wchar_t *v12; // rax
  const wchar_t *v13; // rax
  const struct _tlgProvider_t *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned __int16 **v17; // rcx
  const struct _tlgProvider_t *v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  HKEY v21; // rdi
  DWORD LastError; // ebx
  unsigned __int16 *v23[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v25[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v28; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Buffer[512]; // [rsp+70h] [rbp-90h] BYREF

  v27 = 512;
  result = GetPersistentRegPath(1, 0, &v27, Buffer);
  v8 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v8 = result < 0;
  }
  if ( !v8 )
  {
    v9 = a2 - 1;
    if ( !v9 )
    {
      v12 = L"\\DeviceSpecific";
LABEL_23:
      swprintf_s(Buffer, 0x200u, L"%s%s", Buffer, v12);
      goto LABEL_24;
    }
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 2;
      if ( v11 )
      {
        if ( v11 != 4 )
          return -2147024809;
        v12 = L"\\IMSISpecific\\Default";
        goto LABEL_23;
      }
      if ( *a1 )
      {
        v13 = L"\\ICCIDSpecific";
LABEL_17:
        swprintf_s(Buffer, 0x200u, L"%s%s\\%s", Buffer, v13, a1);
LABEL_24:
        swprintf_s(Buffer, 0x200u, L"%s%s", Buffer, L"\\CellUX");
        v21 = *a4;
        if ( *a4 )
        {
          LastError = GetLastError();
          RegCloseKey(v21);
          SetLastError(LastError);
        }
        *a4 = 0;
        result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, a4);
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
        return result;
      }
      *(_OWORD *)v25 = 0;
      v26 = 0;
      *(_OWORD *)v23 = 0;
      v24 = 0;
      std::vector<unsigned short>::resize(v25);
      std::vector<unsigned short>::resize(v23);
      StringCchPrintfW(v25[0], v25[1] - v25[0], L"Asking for per-ICCID value but ICCID is not ready yet.");
      StringCchPrintfW(
        v23[0],
        v23[1] - v23[0],
        L"%S(%d):%s",
        "MVConfigurationHelper::GetRegKeyHandleAndName",
        236,
        v25[0]);
      v14 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v14 > 3u )
      {
        v28 = v23[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v14,
          (__int64)&byte_180076107,
          v15,
          v16,
          (const unsigned __int16 **)&v28);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v23);
      v17 = v25;
    }
    else
    {
      a1 += 22;
      if ( *a1 )
      {
        v13 = L"\\IMSISpecific";
        goto LABEL_17;
      }
      *(_OWORD *)v23 = 0;
      v24 = 0;
      *(_OWORD *)v25 = 0;
      v26 = 0;
      std::vector<unsigned short>::resize(v23);
      std::vector<unsigned short>::resize(v25);
      StringCchPrintfW(v23[0], v23[1] - v23[0], L"Asking for per-IMSI value of IMSI is not ready yet.");
      StringCchPrintfW(
        v25[0],
        v25[1] - v25[0],
        L"%S(%d):%s",
        "MVConfigurationHelper::GetRegKeyHandleAndName",
        247,
        v23[0]);
      v18 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v18 > 3u )
      {
        v28 = v25[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v18,
          (__int64)&dword_1800760E4,
          v19,
          v20,
          (const unsigned __int16 **)&v28);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v25);
      v17 = v23;
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v17);
    return -2147023728;
  }
  return result;
}

```

## disassembly

```asm
0x18003240c  mov     [rsp-8+arg_8], rbx
0x180032411  push    rbp
0x180032412  push    rsi
0x180032413  push    rdi
0x180032414  push    r14
0x180032416  push    r15
0x180032418  lea     rbp, [rsp-380h]
0x180032420  sub     rsp, 480h
0x180032427  mov     rax, cs:__security_cookie
0x18003242e  xor     rax, rsp
0x180032431  mov     [rbp+3A0h+var_30], rax
0x180032438  mov     rsi, r9
0x18003243b  mov     ebx, edx
0x18003243d  mov     rdi, rcx
0x180032440  mov     r15d, 200h
0x180032446  mov     [rsp+4A0h+var_440], r15d
0x18003244b  lea     r9, [rsp+4A0h+Buffer]
0x180032450  lea     r8, [rsp+4A0h+var_440]
0x180032455  xor     edx, edx
0x180032457  lea     ecx, [rdx+1]
0x18003245a  call    cs:__imp_GetPersistentRegPath
0x180032460  xor     r14d, r14d
0x180032463  test    eax, eax
0x180032465  jle     short loc_180032471
0x180032467  movzx   eax, ax
0x18003246a  or      eax, 80070000h
0x18003246f  test    eax, eax
0x180032471  js      loc_180032723
0x180032477  sub     ebx, 1
0x18003247a  jz      loc_180032689
0x180032480  sub     ebx, 1
0x180032483  jz      loc_18003257E
0x180032489  sub     ebx, 2
0x18003248c  jz      short loc_1800324A9
0x18003248e  cmp     ebx, 4
0x180032491  jz      short loc_18003249D
0x180032493  mov     eax, 80070057h
0x180032498  jmp     loc_180032723
0x18003249d  lea     rax, aImsispecificDe; "\\IMSISpecific\\Default"
0x1800324a4  jmp     loc_180032690
0x1800324a9  cmp     [rdi], r14w
0x1800324ad  jz      short loc_1800324BB
0x1800324af  lea     rax, aIccidspecific; "\\ICCIDSpecific"
0x1800324b6  jmp     loc_18003258F
0x1800324bb  xorps   xmm0, xmm0
0x1800324be  movdqu  xmmword ptr [rsp+4A0h+var_458], xmm0
0x1800324c4  mov     [rsp+4A0h+var_448], r14
0x1800324c9  movdqu  xmmword ptr [rsp+4A0h+var_470], xmm0
0x1800324cf  mov     [rsp+4A0h+var_460], r14
0x1800324d4  lea     rcx, [rsp+4A0h+var_458]
0x1800324d9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800324de  lea     rcx, [rsp+4A0h+var_470]
0x1800324e3  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800324e8  mov     rdx, [rsp+4A0h+var_458+8]
0x1800324ed  mov     rcx, [rsp+4A0h+var_458]; unsigned __int16 *
0x1800324f2  sub     rdx, rcx
0x1800324f5  sar     rdx, 1; unsigned __int64
0x1800324f8  lea     r8, aAskingForPerIc; "Asking for per-ICCID value but ICCID is"...
0x1800324ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032504  mov     rdx, [rsp+4A0h+var_470+8]
0x180032509  mov     rcx, [rsp+4A0h+var_470]; unsigned __int16 *
0x18003250e  sub     rdx, rcx
0x180032511  sar     rdx, 1; unsigned __int64
0x180032514  mov     rax, [rsp+4A0h+var_458]
0x180032519  mov     [rsp+4A0h+var_478], rax
0x18003251e  mov     dword ptr [rsp+4A0h+phkResult], 0ECh
0x180032526  lea     r9, aMvconfiguratio_1; "MVConfigurationHelper::GetRegKeyHandleA"...
0x18003252d  lea     r8, aSDS; "%S(%d):%s"
0x180032534  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032539  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003253e  mov     rcx, rax
0x180032541  mov     eax, [rax]
0x180032543  cmp     eax, 3
0x180032546  jbe     short loc_180032569
0x180032548  mov     rax, [rsp+4A0h+var_470]
0x18003254d  mov     [rsp+4A0h+var_438], rax
0x180032552  lea     rax, [rsp+4A0h+var_438]
0x180032557  mov     [rsp+4A0h+phkResult], rax
0x18003255c  lea     rdx, byte_180076107
0x180032563  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180032568  nop
0x180032569  lea     rcx, [rsp+4A0h+var_470]
0x18003256e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180032573  nop
0x180032574  lea     rcx, [rsp+4A0h+var_458]
0x180032579  jmp     loc_180032675
0x18003257e  add     rdi, 2Ch ; ','
0x180032582  cmp     [rdi], r14w
0x180032586  jz      short loc_1800325B7
0x180032588  lea     rax, aImsispecific; "\\IMSISpecific"
0x18003258f  mov     [rsp+4A0h+var_478], rdi
0x180032594  mov     [rsp+4A0h+phkResult], rax
0x180032599  lea     r9, [rsp+4A0h+Buffer]
0x18003259e  lea     r8, aSSS; "%s%s\\%s"
0x1800325a5  mov     rdx, r15; BufferCount
0x1800325a8  lea     rcx, [rsp+4A0h+Buffer]; Buffer
0x1800325ad  call    swprintf_s
0x1800325b2  jmp     loc_1800326AE
0x1800325b7  xorps   xmm0, xmm0
0x1800325ba  movdqu  xmmword ptr [rsp+4A0h+var_470], xmm0
0x1800325c0  mov     [rsp+4A0h+var_460], r14
0x1800325c5  movdqu  xmmword ptr [rsp+4A0h+var_458], xmm0
0x1800325cb  mov     [rsp+4A0h+var_448], r14
0x1800325d0  lea     rcx, [rsp+4A0h+var_470]
0x1800325d5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800325da  lea     rcx, [rsp+4A0h+var_458]
0x1800325df  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800325e4  mov     rdx, [rsp+4A0h+var_470+8]
0x1800325e9  mov     rcx, [rsp+4A0h+var_470]; unsigned __int16 *
0x1800325ee  sub     rdx, rcx
0x1800325f1  sar     rdx, 1; unsigned __int64
0x1800325f4  lea     r8, aAskingForPerIm; "Asking for per-IMSI value of IMSI is no"...
0x1800325fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032600  mov     rdx, [rsp+4A0h+var_458+8]
0x180032605  mov     rcx, [rsp+4A0h+var_458]; unsigned __int16 *
0x18003260a  sub     rdx, rcx
0x18003260d  sar     rdx, 1; unsigned __int64
0x180032610  mov     rax, [rsp+4A0h+var_470]
0x180032615  mov     [rsp+4A0h+var_478], rax
0x18003261a  mov     dword ptr [rsp+4A0h+phkResult], 0F7h
0x180032622  lea     r9, aMvconfiguratio_1; "MVConfigurationHelper::GetRegKeyHandleA"...
0x180032629  lea     r8, aSDS; "%S(%d):%s"
0x180032630  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032635  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003263a  mov     rcx, rax
0x18003263d  mov     eax, [rax]
0x18003263f  cmp     eax, 3
0x180032642  jbe     short loc_180032665
0x180032644  mov     rax, [rsp+4A0h+var_458]
0x180032649  mov     [rsp+4A0h+var_438], rax
0x18003264e  lea     rax, [rsp+4A0h+var_438]
0x180032653  mov     [rsp+4A0h+phkResult], rax
0x180032658  lea     rdx, dword_1800760E4
0x18003265f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180032664  nop
0x180032665  lea     rcx, [rsp+4A0h+var_458]
0x18003266a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003266f  nop
0x180032670  lea     rcx, [rsp+4A0h+var_470]
0x180032675  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003267a  mov     eax, 80070490h
0x18003267f  test    eax, eax
0x180032681  js      loc_180032723
0x180032687  jmp     short loc_1800326AE
0x180032689  lea     rax, aDevicespecific_0; "\\DeviceSpecific"
0x180032690  mov     [rsp+4A0h+phkResult], rax
0x180032695  lea     r9, [rsp+4A0h+Buffer]
0x18003269a  lea     r8, aSS; "%s%s"
0x1800326a1  mov     rdx, r15; BufferCount
0x1800326a4  lea     rcx, [rsp+4A0h+Buffer]; Buffer
0x1800326a9  call    swprintf_s
0x1800326ae  lea     rax, aCellux_0; "\\CellUX"
0x1800326b5  mov     [rsp+4A0h+phkResult], rax
0x1800326ba  lea     r9, [rsp+4A0h+Buffer]
0x1800326bf  lea     r8, aSS; "%s%s"
0x1800326c6  mov     rdx, r15; BufferCount
0x1800326c9  lea     rcx, [rsp+4A0h+Buffer]; Buffer
0x1800326ce  call    swprintf_s
0x1800326d3  mov     rdi, [rsi]
0x1800326d6  test    rdi, rdi
0x1800326d9  jz      short loc_1800326F4
0x1800326db  call    cs:__imp_GetLastError
0x1800326e1  mov     ebx, eax
0x1800326e3  mov     rcx, rdi; hKey
0x1800326e6  call    cs:__imp_RegCloseKey
0x1800326ec  mov     ecx, ebx; dwErrCode
0x1800326ee  call    cs:__imp_SetLastError
0x1800326f4  mov     [rsi], r14
0x1800326f7  mov     [rsp+4A0h+phkResult], rsi; phkResult
0x1800326fc  mov     r9d, 20019h; samDesired
0x180032702  xor     r8d, r8d; ulOptions
0x180032705  lea     rdx, [rsp+4A0h+Buffer]; lpSubKey
0x18003270a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032711  call    cs:__imp_RegOpenKeyExW
0x180032717  test    eax, eax
0x180032719  jle     short loc_180032723
0x18003271b  movzx   eax, ax
0x18003271e  or      eax, 80070000h
0x180032723  mov     rcx, [rbp+3A0h+var_30]
0x18003272a  xor     rcx, rsp; StackCookie
0x18003272d  call    __security_check_cookie
0x180032732  mov     rbx, [rsp+4A0h+arg_8]
0x18003273a  add     rsp, 480h
0x180032741  pop     r15
0x180032743  pop     r14
0x180032745  pop     rdi
0x180032746  pop     rsi
0x180032747  pop     rbp
0x180032748  retn
```
