# DdmDeviceTable::AddPnPDevice(_RASMAN_PORT *,RasObjPtr<DdmDevice> &)

- ea: `0x18003c7f0`
- end: `0x18003cc5a`
- name: `?AddPnPDevice@DdmDeviceTable@@QEAAKPEAU_RASMAN_PORT@@AEAV?$RasObjPtr@VDdmDevice@@@@@Z`
- size: `1130`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003d41c`
- `0x180048e90`

## callees

- `0x180007d00`
- `0x18003c4a0`
- `0x18003c7f0`
- `0x18003cc60`
- `0x18003d100`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18003c9eb`
- `KERNEL32!MultiByteToWideChar` at `0x18003c9eb`
- `KERNEL32!LeaveCriticalSection` at `0x18003cb93`
- `KERNEL32!LeaveCriticalSection` at `0x18003cb93`
- `KERNEL32!EnterCriticalSection` at `0x18003cb34`
- `KERNEL32!EnterCriticalSection` at `0x18003cb34`
- `rtutils!RouterLogEventW` at `0x18003ca8e`
- `rtutils!RouterLogEventW` at `0x18003ca8e`
- `rtutils!RouterLogEventStringW` at `0x18003ca3b`
- `rtutils!RouterLogEventStringW` at `0x18003ca3b`
- `rasman!RasPortOpen` at `0x18003c9bb`
- `rasman!RasPortOpen` at `0x18003c9bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdmDeviceTable::AddPnPDevice(WCHAR *a1, const CHAR *a2)
{
  DWORD v4; // r14d
  __int64 v6; // rbx
  char v7; // al
  __int64 v8; // rcx
  DWORD v9; // eax
  __int64 v10; // rdx
  __int64 v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v14; // [rsp+58h] [rbp-A8h] BYREF
  int v15; // [rsp+68h] [rbp-98h] BYREF
  __int128 v16; // [rsp+6Ch] [rbp-94h]
  __int128 v17; // [rsp+7Ch] [rbp-84h]
  int v18; // [rsp+8Ch] [rbp-74h]
  WCHAR WideCharStr[24]; // [rsp+90h] [rbp-70h] BYREF
  int v20; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v21[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  plpszSubStringArray = a1;
  v4 = 0;
  v12 = 0;
  v11 = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v14 = 0;
  if ( dword_1800CF654 )
    return 50;
  DdmDeviceTable::FindDevice(a1, *(_QWORD *)a2, &v11);
  v6 = v11;
  if ( v11 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v20) = 0;
      LOWORD(v15) = 0;
      ConvertPortNoToString(&v15, *(unsigned int *)a2);
      FormatRRASErrorString(&v20, L"Error:Recvd add new port notification for existing port %d", *(_QWORD *)a2);
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v20,
          (unsigned int)&v14,
          0,
          (__int64)&v15);
    }
    if ( v6 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 8), 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
    }
    return 183;
  }
  v7 = byte_1800CF404;
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v20) = 0;
    LOWORD(v15) = 0;
    ConvertPortNoToString(&v15, *(unsigned int *)a2);
    FormatRRASErrorString(&v20, L"Adding new port hPort=%d", *(_QWORD *)a2);
    v7 = byte_1800CF404;
    if ( (byte_1800CF404 & 8) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v20,
        (unsigned int)&v14,
        0,
        (__int64)&v15);
      v7 = byte_1800CF404;
    }
  }
  if ( (a2[32] & 5) == 0 )
  {
    if ( (v7 & 8) != 0 )
    {
      LOWORD(v20) = 0;
      LOWORD(v15) = 0;
      ConvertPortNoToString(&v15, *(unsigned int *)a2);
      FormatRRASErrorString(
        &v20,
        L"Conf. usage wrong, not adding port hPort=%d usage=%d",
        *(_QWORD *)a2,
        *((unsigned int *)a2 + 8));
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v20,
          (unsigned int)&v14,
          0,
          (__int64)&v15);
    }
    goto LABEL_34;
  }
  v4 = RasPortOpen(a2 + 8, &v12, 0);
  if ( v4 )
  {
    MultiByteToWideChar(0, 0, a2 + 8, -1, WideCharStr, 17);
    plpszSubStringArray = WideCharStr;
    if ( dword_1800CF4E4 )
      RouterLogEventStringW(hLogHandle, 1u, 0x4E8Cu, 1u, &plpszSubStringArray, v4, 1u);
  }
  else
  {
    v9 = DdmDeviceTable::CreateNewDevice(v8, v12, a2, &v11);
    v4 = v9;
    if ( v9 )
    {
      if ( dword_1800CF4E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, v9);
    }
    else
    {
      v4 = DdmDeviceTable::AddDevice((DdmDeviceTable *)plpszSubStringArray);
      if ( !v4 )
      {
        v6 = v11;
        EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
        ((void (*)(void))qword_1800CF570)();
        if ( (*(_DWORD *)(v6 + 136) & 0xFFFF0000) != 0x20000 )
        {
          LOBYTE(v10) = 1;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 32LL))(
            g_pIDimInterfaceTable,
            v10);
        }
        if ( *(_WORD *)(v6 + 136) != 13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 168LL))(v6);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 16));
        goto LABEL_34;
      }
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v20) = 0;
        LOWORD(v15) = 0;
        ConvertPortNoToString(&v15, (unsigned int)v12);
        FormatRRASErrorString(&v20, L"AddDevice failed for port hPort=%d. Error: %d", *(_QWORD *)a2, v4);
        if ( (byte_1800CF404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v20,
            (unsigned int)&v14,
            0,
            (__int64)&v15);
      }
    }
    v6 = v11;
  }
LABEL_34:
  if ( v6 && _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
  return v4;
}

```

## disassembly

```asm
0x18003c7f0  mov     [rsp-8+arg_10], rbx
0x18003c7f5  push    rbp
0x18003c7f6  push    rsi
0x18003c7f7  push    rdi
0x18003c7f8  push    r13
0x18003c7fa  push    r14
0x18003c7fc  lea     rbp, [rsp-7D0h]
0x18003c804  sub     rsp, 8D0h
0x18003c80b  mov     rax, cs:__security_cookie
0x18003c812  xor     rax, rsp
0x18003c815  mov     [rbp+7F0h+var_30], rax
0x18003c81c  mov     rsi, rdx
0x18003c81f  mov     rbx, rcx
0x18003c822  mov     [rsp+8F0h+plpszSubStringArray], rcx
0x18003c827  xor     r13d, r13d
0x18003c82a  mov     r14d, r13d
0x18003c82d  mov     [rsp+8F0h+var_8A8], r13
0x18003c832  mov     [rsp+8F0h+var_8B0], r13
0x18003c837  mov     [rbp+7F0h+var_830], r13d
0x18003c83b  xor     edx, edx; Val
0x18003c83d  mov     r8d, 7FCh; Size
0x18003c843  lea     rcx, [rbp+7F0h+var_82C]; void *
0x18003c847  call    memset_0
0x18003c84c  mov     [rsp+8F0h+var_888], r13d
0x18003c851  xorps   xmm0, xmm0
0x18003c854  xor     eax, eax
0x18003c856  movups  [rsp+8F0h+var_884], xmm0
0x18003c85b  movups  [rsp+8F0h+var_874], xmm0
0x18003c860  mov     [rbp+7F0h+var_864], eax
0x18003c863  movups  [rsp+8F0h+var_898], xmm0
0x18003c868  cmp     cs:dword_1800CF654, r13d
0x18003c86f  jz      short loc_18003C87A
0x18003c871  lea     eax, [r13+32h]
0x18003c875  jmp     loc_18003CC33
0x18003c87a  lea     r8, [rsp+8F0h+var_8B0]
0x18003c87f  mov     rdx, [rsi]
0x18003c882  mov     rcx, rbx
0x18003c885  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x18003c88a  mov     rbx, [rsp+8F0h+var_8B0]
0x18003c88f  mov     dil, 8
0x18003c892  test    rbx, rbx
0x18003c895  jz      loc_18003C934
0x18003c89b  test    cs:byte_1800CF404, dil
0x18003c8a2  jz      short loc_18003C903
0x18003c8a4  mov     word ptr [rbp+7F0h+var_830], r13w
0x18003c8a9  mov     word ptr [rsp+8F0h+var_888], r13w
0x18003c8af  mov     edx, [rsi]
0x18003c8b1  lea     rcx, [rsp+8F0h+var_888]
0x18003c8b6  call    ConvertPortNoToString
0x18003c8bb  mov     r8, [rsi]
0x18003c8be  lea     rdx, aErrorRecvdAddN; "Error:Recvd add new port notification f"...
0x18003c8c5  lea     rcx, [rbp+7F0h+var_830]
0x18003c8c9  call    FormatRRASErrorString
0x18003c8ce  test    cs:byte_1800CF404, dil
0x18003c8d5  jz      short loc_18003C903
0x18003c8d7  lea     rax, [rsp+8F0h+var_888]
0x18003c8dc  mov     qword ptr [rsp+8F0h+cchWideChar], rax
0x18003c8e1  mov     [rsp+8F0h+lpWideCharStr], r13
0x18003c8e6  lea     r9, [rsp+8F0h+var_898]
0x18003c8eb  lea     r8, [rbp+7F0h+var_830]
0x18003c8ef  lea     rdx, RasDdmParamTraceError
0x18003c8f6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003c8fd  call    McTemplateU0zjzz_EventWriteTransfer
0x18003c902  nop
0x18003c903  test    rbx, rbx
0x18003c906  jz      short loc_18003C92A
0x18003c908  or      eax, 0FFFFFFFFh
0x18003c90b  lock xadd [rbx+8], eax
0x18003c910  cmp     eax, 1
0x18003c913  jnz     short loc_18003C92A
0x18003c915  mov     rcx, [rsp+8F0h+var_8B0]
0x18003c91a  mov     rax, [rcx]
0x18003c91d  mov     edx, 1
0x18003c922  mov     rax, [rax]
0x18003c925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c92a  mov     eax, 0B7h
0x18003c92f  jmp     loc_18003CC33
0x18003c934  mov     al, cs:byte_1800CF404
0x18003c93a  test    dil, al
0x18003c93d  jz      short loc_18003C9A5
0x18003c93f  mov     word ptr [rbp+7F0h+var_830], r13w
0x18003c944  mov     word ptr [rsp+8F0h+var_888], r13w
0x18003c94a  mov     edx, [rsi]
0x18003c94c  lea     rcx, [rsp+8F0h+var_888]
0x18003c951  call    ConvertPortNoToString
0x18003c956  mov     r8, [rsi]
0x18003c959  lea     rdx, aAddingNewPortH; "Adding new port hPort=%d"
0x18003c960  lea     rcx, [rbp+7F0h+var_830]
0x18003c964  call    FormatRRASErrorString
0x18003c969  mov     al, cs:byte_1800CF404
0x18003c96f  test    dil, al
0x18003c972  jz      short loc_18003C9A5
0x18003c974  lea     rax, [rsp+8F0h+var_888]
0x18003c979  mov     qword ptr [rsp+8F0h+cchWideChar], rax
0x18003c97e  mov     [rsp+8F0h+lpWideCharStr], r13
0x18003c983  lea     r9, [rsp+8F0h+var_898]
0x18003c988  lea     r8, [rbp+7F0h+var_830]
0x18003c98c  lea     rdx, RasDdmParamTraceError
0x18003c993  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003c99a  call    McTemplateU0zjzz_EventWriteTransfer
0x18003c99f  mov     al, cs:byte_1800CF404
0x18003c9a5  test    byte ptr [rsi+20h], 5
0x18003c9a9  jz      loc_18003CBA1
0x18003c9af  xor     r8d, r8d
0x18003c9b2  lea     rdx, [rsp+8F0h+var_8A8]
0x18003c9b7  lea     rcx, [rsi+8]
0x18003c9bb  call    cs:__imp_RasPortOpen
0x18003c9c2  nop     dword ptr [rax+rax+00h]
0x18003c9c7  mov     r14d, eax
0x18003c9ca  test    eax, eax
0x18003c9cc  jz      short loc_18003CA4C
0x18003c9ce  mov     [rsp+8F0h+cchWideChar], 11h; cchWideChar
0x18003c9d6  lea     rax, [rbp+7F0h+WideCharStr]
0x18003c9da  mov     [rsp+8F0h+lpWideCharStr], rax; lpWideCharStr
0x18003c9df  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18003c9e3  lea     r8, [rsi+8]; lpMultiByteStr
0x18003c9e7  xor     edx, edx; dwFlags
0x18003c9e9  xor     ecx, ecx; CodePage
0x18003c9eb  call    cs:__imp_MultiByteToWideChar
0x18003c9f2  nop     dword ptr [rax+rax+00h]
0x18003c9f7  lea     rax, [rbp+7F0h+WideCharStr]
0x18003c9fb  mov     [rsp+8F0h+plpszSubStringArray], rax
0x18003ca00  xor     r13d, r13d
0x18003ca03  cmp     cs:dword_1800CF4E4, r13d
0x18003ca0a  jbe     loc_18003CC09
0x18003ca10  mov     [rsp+8F0h+dwErrorIndex], 1; dwErrorIndex
0x18003ca18  mov     [rsp+8F0h+cchWideChar], r14d; dwErrorCode
0x18003ca1d  lea     rax, [rsp+8F0h+plpszSubStringArray]
0x18003ca22  mov     [rsp+8F0h+lpWideCharStr], rax; plpszSubStringArray
0x18003ca27  lea     edx, [r13+1]; dwEventType
0x18003ca2b  mov     r9d, edx; dwSubStringCount
0x18003ca2e  mov     r8d, 4E8Ch; dwMessageId
0x18003ca34  mov     rcx, cs:hLogHandle; hLogHandle
0x18003ca3b  call    cs:__imp_RouterLogEventStringW
0x18003ca42  nop     dword ptr [rax+rax+00h]
0x18003ca47  jmp     loc_18003CC09
0x18003ca4c  lea     r9, [rsp+8F0h+var_8B0]
0x18003ca51  mov     r8, rsi
0x18003ca54  mov     rdx, [rsp+8F0h+var_8A8]
0x18003ca59  call    ?CreateNewDevice@DdmDeviceTable@@QEAAKPEAXPEAU_RASMAN_PORT@@AEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::CreateNewDevice(void *,_RASMAN_PORT *,RasObjPtr<DdmDevice> &)
0x18003ca5e  mov     r14d, eax
0x18003ca61  xor     r13d, r13d
0x18003ca64  test    eax, eax
0x18003ca66  jz      short loc_18003CAA4
0x18003ca68  cmp     cs:dword_1800CF4E4, r13d
0x18003ca6f  jbe     short loc_18003CA9A
0x18003ca71  mov     [rsp+8F0h+cchWideChar], eax; dwErrorCode
0x18003ca75  mov     [rsp+8F0h+lpWideCharStr], r13; plpszSubStringArray
0x18003ca7a  xor     r9d, r9d; dwSubStringCount
0x18003ca7d  lea     edx, [r13+1]; dwEventType
0x18003ca81  mov     r8d, 4E88h; dwMessageId
0x18003ca87  mov     rcx, cs:hLogHandle; hLogHandle
0x18003ca8e  call    cs:__imp_RouterLogEventW
0x18003ca95  nop     dword ptr [rax+rax+00h]
0x18003ca9a  mov     rbx, [rsp+8F0h+var_8B0]
0x18003ca9f  jmp     loc_18003CC09
0x18003caa4  lea     rdx, [rsp+8F0h+var_8B0]
0x18003caa9  mov     rcx, [rsp+8F0h+plpszSubStringArray]; this
0x18003caae  call    ?AddDevice@DdmDeviceTable@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::AddDevice(RasObjPtr<DdmDevice> &)
0x18003cab3  mov     r14d, eax
0x18003cab6  test    eax, eax
0x18003cab8  jz      short loc_18003CB2B
0x18003caba  test    cs:byte_1800CF404, dil
0x18003cac1  jz      short loc_18003CA9A
0x18003cac3  mov     word ptr [rbp+7F0h+var_830], r13w
0x18003cac8  mov     word ptr [rsp+8F0h+var_888], r13w
0x18003cace  mov     edx, dword ptr [rsp+8F0h+var_8A8]
0x18003cad2  lea     rcx, [rsp+8F0h+var_888]
0x18003cad7  call    ConvertPortNoToString
0x18003cadc  mov     r9d, r14d
0x18003cadf  mov     r8, [rsi]
0x18003cae2  lea     rdx, aAdddeviceFaile; "AddDevice failed for port hPort=%d. Err"...
0x18003cae9  lea     rcx, [rbp+7F0h+var_830]
0x18003caed  call    FormatRRASErrorString
0x18003caf2  test    cs:byte_1800CF404, dil
0x18003caf9  jz      short loc_18003CA9A
0x18003cafb  lea     rax, [rsp+8F0h+var_888]
0x18003cb00  mov     qword ptr [rsp+8F0h+cchWideChar], rax
0x18003cb05  mov     [rsp+8F0h+lpWideCharStr], r13
0x18003cb0a  lea     r9, [rsp+8F0h+var_898]
0x18003cb0f  lea     r8, [rbp+7F0h+var_830]
0x18003cb13  lea     rdx, RasDdmParamTraceError
0x18003cb1a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003cb21  call    McTemplateU0zjzz_EventWriteTransfer
0x18003cb26  jmp     loc_18003CA9A
0x18003cb2b  mov     rbx, [rsp+8F0h+var_8B0]
0x18003cb30  lea     rcx, [rbx+10h]; lpCriticalSection
0x18003cb34  call    cs:__imp_EnterCriticalSection
0x18003cb3b  nop     dword ptr [rax+rax+00h]
0x18003cb40  mov     rax, cs:qword_1800CF570
0x18003cb47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb4c  mov     eax, [rbx+88h]
0x18003cb52  and     eax, 0FFFF0000h
0x18003cb57  cmp     eax, 20000h
0x18003cb5c  jz      short loc_18003CB73
0x18003cb5e  mov     rcx, cs:g_pIDimInterfaceTable
0x18003cb65  mov     rax, [rcx]
0x18003cb68  mov     dl, 1
0x18003cb6a  mov     rax, [rax+20h]
0x18003cb6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb73  cmp     word ptr [rbx+88h], 0Dh
0x18003cb7b  jz      short loc_18003CB8F
0x18003cb7d  mov     rax, [rbx]
0x18003cb80  mov     rcx, rbx
0x18003cb83  mov     rax, [rax+0A8h]
0x18003cb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb8f  lea     rcx, [rbx+10h]; lpCriticalSection
0x18003cb93  call    cs:__imp_LeaveCriticalSection
0x18003cb9a  nop     dword ptr [rax+rax+00h]
0x18003cb9f  jmp     short loc_18003CC09
0x18003cba1  test    dil, al
0x18003cba4  jz      short loc_18003CC09
0x18003cba6  mov     word ptr [rbp+7F0h+var_830], r13w
0x18003cbab  mov     word ptr [rsp+8F0h+var_888], r13w
0x18003cbb1  mov     edx, [rsi]
0x18003cbb3  lea     rcx, [rsp+8F0h+var_888]
0x18003cbb8  call    ConvertPortNoToString
0x18003cbbd  mov     r9d, [rsi+20h]
0x18003cbc1  mov     r8, [rsi]
0x18003cbc4  lea     rdx, aConfUsageWrong; "Conf. usage wrong, not adding port hPor"...
0x18003cbcb  lea     rcx, [rbp+7F0h+var_830]
0x18003cbcf  call    FormatRRASErrorString
0x18003cbd4  test    cs:byte_1800CF404, dil
0x18003cbdb  jz      short loc_18003CC09
0x18003cbdd  lea     rax, [rsp+8F0h+var_888]
0x18003cbe2  mov     qword ptr [rsp+8F0h+cchWideChar], rax
0x18003cbe7  mov     [rsp+8F0h+lpWideCharStr], r13
0x18003cbec  lea     r9, [rsp+8F0h+var_898]
0x18003cbf1  lea     r8, [rbp+7F0h+var_830]
0x18003cbf5  lea     rdx, RasDdmParamTraceError
0x18003cbfc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003cc03  call    McTemplateU0zjzz_EventWriteTransfer
0x18003cc08  nop
0x18003cc09  test    rbx, rbx
0x18003cc0c  jz      short loc_18003CC30
0x18003cc0e  or      eax, 0FFFFFFFFh
0x18003cc11  lock xadd [rbx+8], eax
0x18003cc16  cmp     eax, 1
0x18003cc19  jnz     short loc_18003CC30
0x18003cc1b  mov     rcx, [rsp+8F0h+var_8B0]
0x18003cc20  mov     rax, [rcx]
0x18003cc23  mov     edx, 1
0x18003cc28  mov     rax, [rax]
0x18003cc2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc30  mov     eax, r14d
0x18003cc33  mov     rcx, [rbp+7F0h+var_30]
0x18003cc3a  xor     rcx, rsp; StackCookie
0x18003cc3d  call    __security_check_cookie
0x18003cc42  mov     rbx, [rsp+8F0h+arg_10]
0x18003cc4a  add     rsp, 8D0h
0x18003cc51  pop     r14
0x18003cc53  pop     r13
0x18003cc55  pop     rdi
0x18003cc56  pop     rsi
0x18003cc57  pop     rbp
0x18003cc58  retn
```
