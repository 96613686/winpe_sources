# DdmLegacyDevice::ProcessSecurityDllEvent(_SECURITY_MESSAGE *)

- ea: `0x18002c260`
- end: `0x18002c604`
- name: `?ProcessSecurityDllEvent@DdmLegacyDevice@@UEAAXPEAU_SECURITY_MESSAGE@@@Z`
- size: `932`
- prototype: `void __fastcall(DdmLegacyDevice *__hidden this, struct _SECURITY_MESSAGE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007c50`
- `0x18001f5e0`
- `0x18002c260`
- `0x18003b8f4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18002c35f`
- `msvcrt!_itow_s` at `0x18002c475`
- `msvcrt!_itow_s` at `0x18002c59d`
- `msvcrt!_itow_s` at `0x18002c35f`
- `msvcrt!_itow_s` at `0x18002c475`
- `msvcrt!_itow_s` at `0x18002c59d`
- `KERNEL32!SetEvent` at `0x18002c570`
- `KERNEL32!SetEvent` at `0x18002c570`
- `KERNEL32!MultiByteToWideChar` at `0x18002c3ee`
- `KERNEL32!MultiByteToWideChar` at `0x18002c50b`
- `KERNEL32!MultiByteToWideChar` at `0x18002c534`
- `KERNEL32!MultiByteToWideChar` at `0x18002c3ee`
- `KERNEL32!MultiByteToWideChar` at `0x18002c50b`
- `KERNEL32!MultiByteToWideChar` at `0x18002c534`
- `rtutils!RouterLogEventW` at `0x18002c43d`
- `rtutils!RouterLogEventW` at `0x18002c43d`
- `rtutils!RouterLogEventStringW` at `0x18002c32b`
- `rtutils!RouterLogEventStringW` at `0x18002c32b`
- `rasman!RasFreeBuffer` at `0x18002c4da`
- `rasman!RasFreeBuffer` at `0x18002c4da`
- `rasman!RasPortConnectComplete` at `0x18002c548`
- `rasman!RasPortConnectComplete` at `0x18002c548`

## string_xrefs

- `0x18002c5bd`: `SecurityDllEventHandler: Security DLL success \n`
- `0x18002c47f`: `SecurityDllEventHandler:Security DLL failure %hs\n`
- `0x18002c369`: `SecurityDllEventHandler:Security DLL failure %x\n`

## pseudocode

```c
void __fastcall DdmLegacyDevice::ProcessSecurityDllEvent(DdmLegacyDevice *this, struct _SECURITY_MESSAGE *a2)
{
  DWORD dwMsgId; // ecx
  DWORD v5; // ecx
  DWORD v6; // ecx
  int v7; // ecx
  int v8; // eax
  int v9; // ecx
  __int64 v10; // rax
  __int64 v11; // rcx
  struct DdmDeviceTable *Instance; // rax
  char v13; // dl
  int v14; // ecx
  __int128 v15; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR plpszSubStringArray[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v17; // [rsp+60h] [rbp-A0h]
  wchar_t Buffer[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v19; // [rsp+74h] [rbp-8Ch]
  __int128 v20; // [rsp+84h] [rbp-7Ch]
  int v21; // [rsp+94h] [rbp-6Ch]
  int v22; // [rsp+A0h] [rbp-60h] BYREF
  char v23[2044]; // [rsp+A4h] [rbp-5Ch] BYREF
  WCHAR WideCharStr[264]; // [rsp+8A0h] [rbp+7A0h] BYREF

  v22 = 0;
  *(_OWORD *)plpszSubStringArray = 0;
  v17 = 0;
  memset_0(v23, 0, sizeof(v23));
  dwMsgId = a2->dwMsgId;
  *(_DWORD *)Buffer = 0;
  v21 = 0;
  v19 = 0;
  v20 = 0;
  v15 = 0;
  v5 = dwMsgId - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        return;
      plpszSubStringArray[0] = (LPWSTR)((char *)this + 714);
      if ( dword_1800C84E4 )
        RouterLogEventStringW(hLogHandle, 1u, 0x4E7Eu, 1u, plpszSubStringArray, a2->dwError, 2u);
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_13;
      LOWORD(v22) = 0;
      Buffer[0] = 0;
      if ( this )
      {
        v7 = *((_DWORD *)this + 24);
        if ( v7 != -1 )
          _itow_s(v7, Buffer, 0x14u, 10);
      }
      FormatRRASErrorString(&v22, L"SecurityDllEventHandler:Security DLL failure %x\n", a2->dwError);
    }
    else
    {
      MultiByteToWideChar(0, 0, a2->UserName, -1, WideCharStr, 257);
      plpszSubStringArray[0] = WideCharStr;
      plpszSubStringArray[1] = (LPWSTR)((char *)this + 714);
      if ( dword_1800C84E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E7Du, 2u, plpszSubStringArray, 0);
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_13;
      LOWORD(v22) = 0;
      Buffer[0] = 0;
      if ( this )
      {
        v9 = *((_DWORD *)this + 24);
        if ( v9 != -1 )
          _itow_s(v9, Buffer, 0x14u, 10);
      }
      FormatRRASErrorString(&v22, L"SecurityDllEventHandler:Security DLL failure %hs\n", a2->UserName);
    }
    if ( (byte_1800C8404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v22,
        (unsigned int)&v15,
        0,
        (__int64)Buffer);
LABEL_13:
    v8 = *((_DWORD *)this + 300);
    if ( v8 )
    {
      if ( v8 == 1 )
      {
        v10 = *(_QWORD *)this;
        *((_DWORD *)this + 300) = 2;
        (*(void (__fastcall **)(DdmLegacyDevice *))(v10 + 184))(this);
      }
    }
    else
    {
      (*(void (__fastcall **)(DdmLegacyDevice *))(*(_QWORD *)this + 176LL))(this);
    }
    return;
  }
  TimerQRemove(*((_QWORD *)this + 12), SvSecurityTimeout);
  if ( *((_QWORD *)this + 151) )
  {
    RasFreeBuffer();
    *((_QWORD *)this + 151) = 0;
  }
  MultiByteToWideChar(0, 0, a2->UserName, -1, (LPWSTR)this + 84, 257);
  MultiByteToWideChar(0, 0, a2->Domain, -1, (LPWSTR)this + 341, 16);
  v11 = *((_QWORD *)this + 12);
  *((_DWORD *)this + 300) = 2;
  RasPortConnectComplete(v11);
  Instance = DdmDeviceTable::GetInstance(0x11u);
  SetEvent(gblSupervisorEvents[*((_DWORD *)this + 24) % *(_DWORD *)Instance + 6]);
  v13 = byte_1800C8404;
  if ( (byte_1800C8404 & 8) != 0 )
  {
    v14 = *((_DWORD *)this + 24);
    Buffer[0] = 0;
    if ( v14 != -1 )
    {
      _itow_s(v14, Buffer, 0x14u, 10);
      v13 = byte_1800C8404;
    }
    if ( (v13 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)L"SecurityDllEventHandler: Security DLL success \n",
        (unsigned int)&v15,
        0,
        (__int64)Buffer);
  }
}

```

## disassembly

```asm
0x18002c260  mov     [rsp-8+arg_10], rbx
0x18002c265  mov     [rsp-8+arg_18], rsi
0x18002c26a  push    rbp
0x18002c26b  lea     rbp, [rsp-9C0h]
0x18002c273  sub     rsp, 0AC0h
0x18002c27a  mov     rax, cs:__security_cookie
0x18002c281  xor     rax, rsp
0x18002c284  mov     [rbp+9C0h+var_10], rax
0x18002c28b  xorps   xmm0, xmm0
0x18002c28e  mov     rsi, rdx
0x18002c291  mov     rbx, rcx
0x18002c294  xor     eax, eax
0x18002c296  xor     edx, edx; Val
0x18002c298  mov     [rbp+9C0h+var_A20], eax
0x18002c29b  lea     rcx, [rbp+9C0h+var_A1C]; void *
0x18002c29f  mov     r8d, 7FCh; Size
0x18002c2a5  movups  xmmword ptr [rsp+0AC0h+var_A70], xmm0
0x18002c2aa  movups  [rsp+0AC0h+var_A60], xmm0
0x18002c2af  call    memset_0
0x18002c2b4  mov     ecx, [rsi]
0x18002c2b6  xor     eax, eax
0x18002c2b8  mov     dword ptr [rsp+0AC0h+Buffer], eax
0x18002c2bc  xorps   xmm0, xmm0
0x18002c2bf  mov     [rbp+9C0h+var_A2C], eax
0x18002c2c2  movups  [rsp+0AC0h+var_A4C], xmm0
0x18002c2c7  movups  [rbp+9C0h+var_A3C], xmm0
0x18002c2cb  movups  [rsp+0AC0h+var_A80], xmm0
0x18002c2d0  sub     ecx, 1
0x18002c2d3  jz      loc_18002C4BE
0x18002c2d9  sub     ecx, 1
0x18002c2dc  jz      loc_18002C3CE
0x18002c2e2  cmp     ecx, 1
0x18002c2e5  jnz     loc_18002C5E0
0x18002c2eb  cmp     cs:dword_1800C84E4, 0
0x18002c2f2  lea     rax, [rbx+2CAh]
0x18002c2f9  mov     [rsp+0AC0h+var_A70], rax
0x18002c2fe  jbe     short loc_18002C331
0x18002c300  mov     eax, [rsi+10h]
0x18002c303  mov     edx, ecx; dwEventType
0x18002c305  mov     [rsp+0AC0h+dwErrorIndex], 2; dwErrorIndex
0x18002c30d  mov     r9d, ecx; dwSubStringCount
0x18002c310  mov     rcx, cs:hLogHandle; hLogHandle
0x18002c317  mov     r8d, 4E7Eh; dwMessageId
0x18002c31d  mov     [rsp+0AC0h+dwErrorCode], eax; dwErrorCode
0x18002c321  lea     rax, [rsp+0AC0h+var_A70]
0x18002c326  mov     [rsp+0AC0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002c32b  call    cs:__imp_RouterLogEventStringW
0x18002c331  test    cs:byte_1800C8404, 8
0x18002c338  jz      short loc_18002C3B1
0x18002c33a  xor     eax, eax
0x18002c33c  mov     word ptr [rbp+9C0h+var_A20], ax
0x18002c340  mov     [rsp+0AC0h+Buffer], ax
0x18002c345  test    rbx, rbx
0x18002c348  jz      short loc_18002C365
0x18002c34a  mov     ecx, [rbx+60h]; Value
0x18002c34d  cmp     ecx, 0FFFFFFFFh
0x18002c350  jz      short loc_18002C365
0x18002c352  lea     r9d, [rax+0Ah]; Radix
0x18002c356  lea     r8d, [rax+14h]; BufferCount
0x18002c35a  lea     rdx, [rsp+0AC0h+Buffer]; Buffer
0x18002c35f  call    cs:__imp__itow_s
0x18002c365  mov     r8d, [rsi+10h]
0x18002c369  lea     rdx, aSecuritydlleve_1; "SecurityDllEventHandler:Security DLL fa"...
0x18002c370  lea     rcx, [rbp+9C0h+var_A20]
0x18002c374  call    FormatRRASErrorString
0x18002c379  test    cs:byte_1800C8404, 8
0x18002c380  jz      short loc_18002C3B1
0x18002c382  lea     rax, [rsp+0AC0h+Buffer]
0x18002c387  mov     qword ptr [rsp+0AC0h+dwErrorCode], rax
0x18002c38c  lea     r9, [rsp+0AC0h+var_A80]
0x18002c391  lea     r8, [rbp+9C0h+var_A20]
0x18002c395  mov     [rsp+0AC0h+plpszSubStringArray], 0
0x18002c39e  lea     rdx, RasDdmParamTraceError
0x18002c3a5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002c3ac  call    McTemplateU0zjzz_EventWriteTransfer
0x18002c3b1  mov     eax, [rbx+4B0h]
0x18002c3b7  test    eax, eax
0x18002c3b9  jnz     loc_18002C494
0x18002c3bf  mov     rax, [rbx]
0x18002c3c2  mov     rax, [rax+0B0h]
0x18002c3c9  jmp     loc_18002C4B1
0x18002c3ce  lea     rax, [rbp+9C0h+WideCharStr]
0x18002c3d5  mov     [rsp+0AC0h+dwErrorCode], 101h; cchWideChar
0x18002c3dd  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002c3e1  mov     [rsp+0AC0h+plpszSubStringArray], rax; lpWideCharStr
0x18002c3e6  lea     r8, [rsi+14h]; lpMultiByteStr
0x18002c3ea  xor     edx, edx; dwFlags
0x18002c3ec  xor     ecx, ecx; CodePage
0x18002c3ee  call    cs:__imp_MultiByteToWideChar
0x18002c3f4  cmp     cs:dword_1800C84E4, 0
0x18002c3fb  lea     rax, [rbp+9C0h+WideCharStr]
0x18002c402  mov     [rsp+0AC0h+var_A70], rax
0x18002c407  lea     rax, [rbx+2CAh]
0x18002c40e  mov     [rsp+0AC0h+var_A70+8], rax
0x18002c413  jbe     short loc_18002C443
0x18002c415  mov     rcx, cs:hLogHandle; hLogHandle
0x18002c41c  lea     rax, [rsp+0AC0h+var_A70]
0x18002c421  mov     edx, 1; dwEventType
0x18002c426  mov     [rsp+0AC0h+dwErrorCode], 0; dwErrorCode
0x18002c42e  mov     r8d, 4E7Dh; dwMessageId
0x18002c434  mov     [rsp+0AC0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002c439  lea     r9d, [rdx+1]; dwSubStringCount
0x18002c43d  call    cs:__imp_RouterLogEventW
0x18002c443  test    cs:byte_1800C8404, 8
0x18002c44a  jz      loc_18002C3B1
0x18002c450  xor     eax, eax
0x18002c452  mov     word ptr [rbp+9C0h+var_A20], ax
0x18002c456  mov     [rsp+0AC0h+Buffer], ax
0x18002c45b  test    rbx, rbx
0x18002c45e  jz      short loc_18002C47B
0x18002c460  mov     ecx, [rbx+60h]; Value
0x18002c463  cmp     ecx, 0FFFFFFFFh
0x18002c466  jz      short loc_18002C47B
0x18002c468  lea     r9d, [rax+0Ah]; Radix
0x18002c46c  lea     r8d, [rax+14h]; BufferCount
0x18002c470  lea     rdx, [rsp+0AC0h+Buffer]; Buffer
0x18002c475  call    cs:__imp__itow_s
0x18002c47b  lea     r8, [rsi+14h]
0x18002c47f  lea     rdx, aSecuritydlleve; "SecurityDllEventHandler:Security DLL fa"...
0x18002c486  lea     rcx, [rbp+9C0h+var_A20]
0x18002c48a  call    FormatRRASErrorString
0x18002c48f  jmp     loc_18002C379
0x18002c494  cmp     eax, 1
0x18002c497  jnz     loc_18002C5E0
0x18002c49d  mov     rax, [rbx]
0x18002c4a0  mov     dword ptr [rbx+4B0h], 2
0x18002c4aa  mov     rax, [rax+0B8h]
0x18002c4b1  mov     rcx, rbx
0x18002c4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4b9  jmp     loc_18002C5E0
0x18002c4be  mov     rcx, [rbx+60h]
0x18002c4c2  lea     rdx, ?SvSecurityTimeout@@YAXPEAX@Z; SvSecurityTimeout(void *)
0x18002c4c9  call    TimerQRemove
0x18002c4ce  mov     rcx, [rbx+4B8h]
0x18002c4d5  test    rcx, rcx
0x18002c4d8  jz      short loc_18002C4EB
0x18002c4da  call    cs:__imp_RasFreeBuffer
0x18002c4e0  mov     qword ptr [rbx+4B8h], 0
0x18002c4eb  lea     rax, [rbx+0A8h]
0x18002c4f2  mov     [rsp+0AC0h+dwErrorCode], 101h; cchWideChar
0x18002c4fa  lea     r8, [rsi+14h]; lpMultiByteStr
0x18002c4fe  mov     [rsp+0AC0h+plpszSubStringArray], rax; lpWideCharStr
0x18002c503  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002c507  xor     edx, edx; dwFlags
0x18002c509  xor     ecx, ecx; CodePage
0x18002c50b  call    cs:__imp_MultiByteToWideChar
0x18002c511  lea     rax, [rbx+2AAh]
0x18002c518  mov     [rsp+0AC0h+dwErrorCode], 10h; cchWideChar
0x18002c520  lea     r8, [rsi+115h]; lpMultiByteStr
0x18002c527  mov     [rsp+0AC0h+plpszSubStringArray], rax; lpWideCharStr
0x18002c52c  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002c530  xor     edx, edx; dwFlags
0x18002c532  xor     ecx, ecx; CodePage
0x18002c534  call    cs:__imp_MultiByteToWideChar
0x18002c53a  mov     rcx, [rbx+60h]
0x18002c53e  mov     dword ptr [rbx+4B0h], 2
0x18002c548  call    cs:__imp_RasPortConnectComplete
0x18002c54e  mov     ecx, 11h; unsigned int
0x18002c553  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18002c558  mov     rcx, rax
0x18002c55b  xor     edx, edx
0x18002c55d  mov     eax, [rbx+60h]
0x18002c560  div     dword ptr [rcx]
0x18002c562  mov     rcx, cs:gblSupervisorEvents
0x18002c569  add     edx, 6
0x18002c56c  mov     rcx, [rcx+rdx*8]; hEvent
0x18002c570  call    cs:__imp_SetEvent
0x18002c576  mov     dl, cs:byte_1800C8404
0x18002c57c  test    dl, 8
0x18002c57f  jz      short loc_18002C5E0
0x18002c581  mov     ecx, [rbx+60h]; Value
0x18002c584  xor     eax, eax
0x18002c586  mov     [rsp+0AC0h+Buffer], ax
0x18002c58b  cmp     ecx, 0FFFFFFFFh
0x18002c58e  jz      short loc_18002C5A9
0x18002c590  lea     r9d, [rax+0Ah]; Radix
0x18002c594  lea     r8d, [rax+14h]; BufferCount
0x18002c598  lea     rdx, [rsp+0AC0h+Buffer]; Buffer
0x18002c59d  call    cs:__imp__itow_s
0x18002c5a3  mov     dl, cs:byte_1800C8404
0x18002c5a9  test    dl, 8
0x18002c5ac  jz      short loc_18002C5E0
0x18002c5ae  lea     rax, [rsp+0AC0h+Buffer]
0x18002c5b3  mov     qword ptr [rsp+0AC0h+dwErrorCode], rax
0x18002c5b8  lea     r9, [rsp+0AC0h+var_A80]
0x18002c5bd  lea     r8, aSecuritydlleve_0; "SecurityDllEventHandler: Security DLL s"...
0x18002c5c4  mov     [rsp+0AC0h+plpszSubStringArray], 0
0x18002c5cd  lea     rdx, RasDdmParamTraceError
0x18002c5d4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002c5db  call    McTemplateU0zjzz_EventWriteTransfer
0x18002c5e0  mov     rcx, [rbp+9C0h+var_10]
0x18002c5e7  xor     rcx, rsp; StackCookie
0x18002c5ea  call    __security_check_cookie
0x18002c5ef  lea     r11, [rsp+0AC0h+var_s0]
0x18002c5f7  mov     rbx, [r11+20h]
0x18002c5fb  mov     rsi, [r11+28h]
0x18002c5ff  mov     rsp, r11
0x18002c602  pop     rbp
0x18002c603  retn
```
