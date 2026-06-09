# CUMRDPConnection::OnDriverLoad(ulong,ushort const *)

- ea: `0x18004f5e0`
- end: `0x18004f87a`
- name: `?OnDriverLoad@CUMRDPConnection@@UEAAJKPEBG@Z`
- size: `666`
- prototype: `__int64 __fastcall(CUMRDPConnection *this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800015f0`
- `0x180022ee8`
- `0x18004f5e0`
- `0x18004f880`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f785`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004f776`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004f776`
- `OLEAUT32!__imp_SysAllocString` at `0x18004f65a`
- `OLEAUT32!__imp_SysAllocString` at `0x18004f65a`
- `OLEAUT32!__imp_VariantInit` at `0x18004f648`
- `OLEAUT32!__imp_VariantInit` at `0x18004f648`
- `OLEAUT32!__imp_VariantClear` at `0x18004f68d`
- `OLEAUT32!__imp_VariantClear` at `0x18004f68d`

## string_xrefs

- `0x18004f734`: `Failed to start protocol`
- `0x18004f7ad`: `Fail to open Indirect Display device`

## pseudocode

```c
__int64 __fastcall CUMRDPConnection::OnDriverLoad(CUMRDPConnection *this, unsigned int a2, const unsigned __int16 *a3)
{
  BSTR v6; // rax
  __int64 v7; // rcx
  signed int started; // ebx
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  char *v12; // rdx
  const char **v13; // rax
  const char *v14; // rax
  HANDLE FileW; // rdi
  signed int LastError; // eax
  const char **hTemplateFile; // [rsp+30h] [rbp-19h]
  const char **v19; // [rsp+40h] [rbp-9h]
  const char **v20; // [rsp+48h] [rbp-1h]
  signed int v21; // [rsp+50h] [rbp+7h] BYREF
  const char *v22; // [rsp+58h] [rbp+Fh] BYREF
  const char *v23; // [rsp+60h] [rbp+17h] BYREF
  const char *v24; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v25; // [rsp+70h] [rbp+27h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp+2Fh] BYREF
  int v27; // [rsp+B0h] [rbp+67h] BYREF
  int v28; // [rsp+C8h] [rbp+7Fh] BYREF

  v27 = 0;
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)this + 8) + 32LL))(
         *((_QWORD *)this + 8),
         L"EnablePipeMgrLite",
         &v27) < 0
    || !v27 )
  {
    FileW = CreateFileW(a3, 0x10000000u, 3u, 0, 4u, 0x800080u, 0);
    if ( FileW != (HANDLE)-1LL )
      goto LABEL_15;
    LastError = GetLastError();
    started = LastError;
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
    if ( started < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        return (unsigned int)started;
      v14 = "Fail to open Indirect Display device";
      v28 = 3435;
      v12 = (char *)word_1801963A2;
    }
    else
    {
LABEL_15:
      started = CUMRDPConnection::OnDriverLoad((CUMRDPConnection *)((char *)this - 8), a2, (unsigned __int64)FileW);
      if ( started >= 0 || (unsigned int)dword_1801B76C8 <= 2 )
        return (unsigned int)started;
      v14 = "OnDriverLoad failed";
      v28 = 3439;
      v12 = byte_180196351;
    }
LABEL_18:
    v25 = v14;
    v24 = "OnDriverLoad";
    v23 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v22 = "Error HResult failed";
    v20 = &v25;
    v19 = &v24;
    hTemplateFile = &v23;
    v13 = &v22;
    goto LABEL_19;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 8;
  v6 = SysAllocString(a3);
  v7 = *((_QWORD *)this + 8);
  pvarg.llVal = (LONGLONG)v6;
  started = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v7 + 56LL))(
              v7,
              L"IddDeviceInstance",
              &pvarg);
  if ( started >= 0 )
  {
    started = CUMRDPConnection::StartGfxPlugin((CUMRDPConnection *)((char *)this - 120));
    if ( started >= 0 || (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)started;
    v14 = "Failed to start protocol";
    v28 = 3419;
    v12 = byte_1801963F3;
    goto LABEL_18;
  }
  VariantClear(&pvarg);
  v11 = dword_1801B76C8;
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v28 = 3412;
    v22 = "Failed to set property CONN_PROPERTY_IDD_DEVICE_INSTANCE";
    v12 = (char *)&dword_180196444;
    v23 = "OnDriverLoad";
    v24 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v25 = "Error HResult failed";
    v20 = &v22;
    v19 = &v23;
    hTemplateFile = &v24;
    v13 = &v25;
LABEL_19:
    v21 = started;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v11,
      (_DWORD)v12,
      v9,
      v10,
      (__int64)v13,
      (__int64)&v21,
      (__int64)hTemplateFile,
      (__int64)&v28,
      (__int64)v19,
      (__int64)v20);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18004f5e0  mov     [rsp-8+arg_8], rbx
0x18004f5e5  mov     [rsp-8+arg_10], rsi
0x18004f5ea  push    rbp
0x18004f5eb  push    rdi
0x18004f5ec  push    r14
0x18004f5ee  lea     rbp, [rsp-47h]
0x18004f5f3  sub     rsp, 90h
0x18004f5fa  mov     rsi, rcx
0x18004f5fd  mov     [rbp+57h+arg_0], 0
0x18004f604  mov     rcx, [rcx+40h]
0x18004f608  mov     rbx, r8
0x18004f60b  mov     r14d, edx
0x18004f60e  lea     r8, [rbp+57h+arg_0]
0x18004f612  lea     rdx, aEnablepipemgrl; "EnablePipeMgrLite"
0x18004f619  mov     rax, [rcx]
0x18004f61c  mov     rax, [rax+20h]
0x18004f620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f625  test    eax, eax
0x18004f627  js      loc_18004F74E
0x18004f62d  cmp     [rbp+57h+arg_0], 0
0x18004f631  jz      loc_18004F74E
0x18004f637  xorps   xmm0, xmm0
0x18004f63a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004f63e  xor     eax, eax
0x18004f640  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18004f644  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18004f648  call    cs:__imp_VariantInit
0x18004f64e  mov     eax, 8
0x18004f653  mov     rcx, rbx; psz
0x18004f656  mov     word ptr [rbp+57h+pvarg], ax
0x18004f65a  call    cs:__imp_SysAllocString
0x18004f660  mov     rcx, [rsi+40h]
0x18004f664  lea     r8, [rbp+57h+pvarg]
0x18004f668  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18004f66c  lea     rdx, aIdddeviceinsta; "IddDeviceInstance"
0x18004f673  mov     rax, [rcx]
0x18004f676  mov     rax, [rax+38h]
0x18004f67a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f67f  mov     ebx, eax
0x18004f681  test    eax, eax
0x18004f683  jns     loc_18004F712
0x18004f689  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004f68d  call    cs:__imp_VariantClear
0x18004f693  mov     ecx, cs:dword_1801B76C8
0x18004f699  cmp     ecx, 2
0x18004f69c  jbe     loc_18004F860
0x18004f6a2  lea     rax, aFailedToSetPro_0; "Failed to set property CONN_PROPERTY_ID"...
0x18004f6a9  mov     [rbp+57h+arg_18], 0D54h
0x18004f6b0  mov     [rbp+57h+var_48], rax
0x18004f6b4  lea     rdx, dword_180196444
0x18004f6bb  lea     rax, aOndriverload; "OnDriverLoad"
0x18004f6c2  mov     [rbp+57h+var_40], rax
0x18004f6c6  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004f6cd  mov     [rbp+57h+var_38], rax
0x18004f6d1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18004f6d8  mov     [rbp+57h+var_30], rax
0x18004f6dc  lea     rax, [rbp+57h+var_48]
0x18004f6e0  mov     [rsp+0A0h+var_58], rax
0x18004f6e5  lea     rax, [rbp+57h+var_40]
0x18004f6e9  mov     [rsp+0A0h+var_60], rax
0x18004f6ee  lea     rax, [rbp+57h+arg_18]
0x18004f6f2  mov     [rsp+0A0h+var_68], rax
0x18004f6f7  lea     rax, [rbp+57h+var_38]
0x18004f6fb  mov     [rsp+0A0h+hTemplateFile], rax
0x18004f700  lea     rax, [rbp+57h+var_50]
0x18004f704  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], rax
0x18004f709  lea     rax, [rbp+57h+var_30]
0x18004f70d  jmp     loc_18004F853
0x18004f712  lea     rcx, [rsi-78h]; this
0x18004f716  call    ?StartGfxPlugin@CUMRDPConnection@@IEAAJXZ; CUMRDPConnection::StartGfxPlugin(void)
0x18004f71b  mov     ebx, eax
0x18004f71d  test    eax, eax
0x18004f71f  jns     loc_18004F860
0x18004f725  mov     eax, cs:dword_1801B76C8
0x18004f72b  cmp     eax, 2
0x18004f72e  jbe     loc_18004F860
0x18004f734  lea     rax, aFailedToStartP; "Failed to start protocol"
0x18004f73b  mov     [rbp+57h+arg_18], 0D5Bh
0x18004f742  lea     rdx, byte_1801963F3
0x18004f749  jmp     loc_18004F7FD
0x18004f74e  xor     r9d, r9d; lpSecurityAttributes
0x18004f751  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x18004f75a  mov     [rsp+0A0h+dwFlagsAndAttributes], 800080h; dwFlagsAndAttributes
0x18004f762  mov     edx, 10000000h; dwDesiredAccess
0x18004f767  mov     rcx, rbx; lpFileName
0x18004f76a  mov     [rsp+0A0h+dwCreationDisposition], 4; dwCreationDisposition
0x18004f772  lea     r8d, [r9+3]; dwShareMode
0x18004f776  call    cs:__imp_CreateFileW
0x18004f77c  mov     rdi, rax
0x18004f77f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f783  jnz     short loc_18004F7C4
0x18004f785  call    cs:__imp_GetLastError
0x18004f78b  mov     ebx, eax
0x18004f78d  test    eax, eax
0x18004f78f  jle     short loc_18004F79A
0x18004f791  movzx   ebx, ax
0x18004f794  or      ebx, 80070000h
0x18004f79a  test    ebx, ebx
0x18004f79c  jns     short loc_18004F7C4
0x18004f79e  mov     eax, cs:dword_1801B76C8
0x18004f7a4  cmp     eax, 2
0x18004f7a7  jbe     loc_18004F860
0x18004f7ad  lea     rax, aFailToOpenIndi; "Fail to open Indirect Display device"
0x18004f7b4  mov     [rbp+57h+arg_18], 0D6Bh
0x18004f7bb  lea     rdx, word_1801963A2
0x18004f7c2  jmp     short loc_18004F7FD
0x18004f7c4  lea     rcx, [rsi-8]; this
0x18004f7c8  mov     r8, rdi; unsigned __int64
0x18004f7cb  mov     edx, r14d; unsigned int
0x18004f7ce  call    ?OnDriverLoad@CUMRDPConnection@@UEAAJK_K@Z; CUMRDPConnection::OnDriverLoad(ulong,unsigned __int64)
0x18004f7d3  mov     ebx, eax
0x18004f7d5  test    eax, eax
0x18004f7d7  jns     loc_18004F860
0x18004f7dd  mov     eax, cs:dword_1801B76C8
0x18004f7e3  cmp     eax, 2
0x18004f7e6  jbe     short loc_18004F860
0x18004f7e8  lea     rax, aOndriverloadFa; "OnDriverLoad failed"
0x18004f7ef  mov     [rbp+57h+arg_18], 0D6Fh
0x18004f7f6  lea     rdx, byte_180196351
0x18004f7fd  mov     [rbp+57h+var_30], rax
0x18004f801  lea     rax, aOndriverload; "OnDriverLoad"
0x18004f808  mov     [rbp+57h+var_38], rax
0x18004f80c  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004f813  mov     [rbp+57h+var_40], rax
0x18004f817  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18004f81e  mov     [rbp+57h+var_48], rax
0x18004f822  lea     rax, [rbp+57h+var_30]
0x18004f826  mov     [rsp+0A0h+var_58], rax
0x18004f82b  lea     rax, [rbp+57h+var_38]
0x18004f82f  mov     [rsp+0A0h+var_60], rax
0x18004f834  lea     rax, [rbp+57h+arg_18]
0x18004f838  mov     [rsp+0A0h+var_68], rax
0x18004f83d  lea     rax, [rbp+57h+var_40]
0x18004f841  mov     [rsp+0A0h+hTemplateFile], rax
0x18004f846  lea     rax, [rbp+57h+var_50]
0x18004f84a  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], rax
0x18004f84f  lea     rax, [rbp+57h+var_48]
0x18004f853  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax
0x18004f858  mov     [rbp+57h+var_50], ebx
0x18004f85b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18004f860  lea     r11, [rsp+0A0h+var_10]
0x18004f868  mov     eax, ebx
0x18004f86a  mov     rbx, [r11+28h]
0x18004f86e  mov     rsi, [r11+30h]
0x18004f872  mov     rsp, r11
0x18004f875  pop     r14
0x18004f877  pop     rdi
0x18004f878  pop     rbp
0x18004f879  retn
```
