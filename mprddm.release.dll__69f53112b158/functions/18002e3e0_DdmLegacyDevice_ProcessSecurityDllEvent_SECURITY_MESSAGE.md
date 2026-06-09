# DdmLegacyDevice::ProcessSecurityDllEvent(_SECURITY_MESSAGE *)

- ea: `0x18002e3e0`
- end: `0x18002e7a0`
- name: `?ProcessSecurityDllEvent@DdmLegacyDevice@@UEAAXPEAU_SECURITY_MESSAGE@@@Z`
- size: `960`
- prototype: `void __fastcall(DdmLegacyDevice *__hidden this, struct _SECURITY_MESSAGE *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007d00`
- `0x180020260`
- `0x18002e3e0`
- `0x18003d278`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18002e719`
- `KERNEL32!SetEvent` at `0x18002e719`
- `KERNEL32!MultiByteToWideChar` at `0x18002e580`
- `KERNEL32!MultiByteToWideChar` at `0x18002e6a2`
- `KERNEL32!MultiByteToWideChar` at `0x18002e6d1`
- `KERNEL32!MultiByteToWideChar` at `0x18002e580`
- `KERNEL32!MultiByteToWideChar` at `0x18002e6a2`
- `KERNEL32!MultiByteToWideChar` at `0x18002e6d1`
- `rtutils!RouterLogEventW` at `0x18002e5d1`
- `rtutils!RouterLogEventW` at `0x18002e5d1`
- `rtutils!RouterLogEventStringW` at `0x18002e4bc`
- `rtutils!RouterLogEventStringW` at `0x18002e4bc`
- `rasman!RasFreeBuffer` at `0x18002e66f`
- `rasman!RasFreeBuffer` at `0x18002e66f`
- `rasman!RasPortConnectComplete` at `0x18002e6eb`
- `rasman!RasPortConnectComplete` at `0x18002e6eb`

## string_xrefs

- `0x18002e759`: `SecurityDllEventHandler: Security DLL success \n`
- `0x18002e612`: `SecurityDllEventHandler:Security DLL failure %hs\n`
- `0x18002e4f9`: `SecurityDllEventHandler:Security DLL failure %x\n`

## pseudocode

```c
void __fastcall DdmLegacyDevice::ProcessSecurityDllEvent(DdmLegacyDevice *this, struct _SECURITY_MESSAGE *a2)
{
  DWORD dwMsgId; // ecx
  DWORD v5; // ecx
  DWORD v6; // ecx
  unsigned int *p_dwError; // rsi
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  struct DdmDeviceTable *Instance; // rax
  __int64 v14; // rdx
  __int128 v15; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR plpszSubStringArray[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+70h] [rbp-90h] BYREF
  __int128 v19; // [rsp+74h] [rbp-8Ch]
  __int128 v20; // [rsp+84h] [rbp-7Ch]
  int v21; // [rsp+94h] [rbp-6Ch]
  WCHAR WideCharStr[264]; // [rsp+A0h] [rbp-60h] BYREF
  int v23; // [rsp+2B0h] [rbp+1B0h] BYREF
  char v24[2044]; // [rsp+2B4h] [rbp+1B4h] BYREF

  v23 = 0;
  *(_OWORD *)plpszSubStringArray = 0;
  v17 = 0;
  memset_0(v24, 0, sizeof(v24));
  dwMsgId = a2->dwMsgId;
  v18 = 0;
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
      p_dwError = &a2->dwError;
      plpszSubStringArray[0] = (LPWSTR)((char *)this + 714);
      if ( dword_1800CF4E4 )
        RouterLogEventStringW(hLogHandle, 1u, 0x4E7Eu, 1u, plpszSubStringArray, *p_dwError, 2u);
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_13;
      LOWORD(v23) = 0;
      LOWORD(v18) = 0;
      if ( this )
        v8 = *((unsigned int *)this + 24);
      else
        v8 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v18, v8);
      FormatRRASErrorString(&v23, L"SecurityDllEventHandler:Security DLL failure %x\n", *p_dwError);
    }
    else
    {
      MultiByteToWideChar(0, 0, a2->UserName, -1, WideCharStr, 257);
      plpszSubStringArray[0] = WideCharStr;
      plpszSubStringArray[1] = (LPWSTR)((char *)this + 714);
      if ( dword_1800CF4E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E7Du, 2u, plpszSubStringArray, 0);
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_13;
      LOWORD(v23) = 0;
      LOWORD(v18) = 0;
      if ( this )
        v10 = *((unsigned int *)this + 24);
      else
        v10 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v18, v10);
      FormatRRASErrorString(&v23, L"SecurityDllEventHandler:Security DLL failure %hs\n", a2->UserName);
    }
    if ( (byte_1800CF404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v23,
        (unsigned int)&v15,
        0,
        (__int64)&v18);
LABEL_13:
    v9 = *((_DWORD *)this + 300);
    if ( v9 )
    {
      if ( v9 == 1 )
      {
        v11 = *(_QWORD *)this;
        *((_DWORD *)this + 300) = 2;
        (*(void (__fastcall **)(DdmLegacyDevice *))(v11 + 184))(this);
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
  v12 = *((_QWORD *)this + 12);
  *((_DWORD *)this + 300) = 2;
  RasPortConnectComplete(v12);
  Instance = DdmDeviceTable::GetInstance(0x11u);
  SetEvent(gblSupervisorEvents[*((_DWORD *)this + 24) % *(_DWORD *)Instance + 6]);
  if ( (byte_1800CF404 & 8) != 0 )
  {
    v14 = *((unsigned int *)this + 24);
    LOWORD(v18) = 0;
    ConvertPortNoToString(&v18, v14);
    if ( (byte_1800CF404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)L"SecurityDllEventHandler: Security DLL success \n",
        (unsigned int)&v15,
        0,
        (__int64)&v18);
  }
}

```

## disassembly

```asm
0x18002e3e0  mov     [rsp-8+arg_10], rbx
0x18002e3e5  mov     [rsp-8+arg_18], rsi
0x18002e3ea  push    rbp
0x18002e3eb  push    rdi
0x18002e3ec  push    r14
0x18002e3ee  lea     rbp, [rsp-9C0h]
0x18002e3f6  sub     rsp, 0AC0h
0x18002e3fd  mov     rax, cs:__security_cookie
0x18002e404  xor     rax, rsp
0x18002e407  mov     [rbp+9D0h+var_20], rax
0x18002e40e  xorps   xmm0, xmm0
0x18002e411  mov     rdi, rdx
0x18002e414  mov     rbx, rcx
0x18002e417  xor     r14d, r14d
0x18002e41a  xor     edx, edx; Val
0x18002e41c  mov     [rbp+9D0h+var_820], r14d
0x18002e423  lea     rcx, [rbp+9D0h+var_81C]; void *
0x18002e42a  mov     r8d, 7FCh; Size
0x18002e430  movups  xmmword ptr [rsp+0AD0h+var_A80], xmm0
0x18002e435  movups  [rsp+0AD0h+var_A70], xmm0
0x18002e43a  call    memset_0
0x18002e43f  mov     ecx, [rdi]
0x18002e441  xorps   xmm0, xmm0
0x18002e444  xor     eax, eax
0x18002e446  mov     [rsp+0AD0h+var_A60], r14d
0x18002e44b  mov     [rbp+9D0h+var_A3C], eax
0x18002e44e  movups  [rsp+0AD0h+var_A5C], xmm0
0x18002e453  movups  [rbp+9D0h+var_A4C], xmm0
0x18002e457  movups  [rsp+0AD0h+var_A90], xmm0
0x18002e45c  sub     ecx, 1
0x18002e45f  jz      loc_18002E653
0x18002e465  sub     ecx, 1
0x18002e468  jz      loc_18002E560
0x18002e46e  cmp     ecx, 1
0x18002e471  jnz     loc_18002E778
0x18002e477  cmp     cs:dword_1800CF4E4, r14d
0x18002e47e  lea     rax, [rbx+2CAh]
0x18002e485  lea     rsi, [rdi+10h]
0x18002e489  mov     [rsp+0AD0h+var_A80], rax
0x18002e48e  mov     edi, ecx
0x18002e490  jbe     short loc_18002E4C8
0x18002e492  mov     eax, [rsi]
0x18002e494  mov     r9d, ecx; dwSubStringCount
0x18002e497  mov     [rsp+0AD0h+dwErrorIndex], 2; dwErrorIndex
0x18002e49f  mov     edx, ecx; dwEventType
0x18002e4a1  mov     rcx, cs:hLogHandle; hLogHandle
0x18002e4a8  mov     r8d, 4E7Eh; dwMessageId
0x18002e4ae  mov     [rsp+0AD0h+dwErrorCode], eax; dwErrorCode
0x18002e4b2  lea     rax, [rsp+0AD0h+var_A80]
0x18002e4b7  mov     [rsp+0AD0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002e4bc  call    cs:__imp_RouterLogEventStringW
0x18002e4c3  nop     dword ptr [rax+rax+00h]
0x18002e4c8  test    cs:byte_1800CF404, 8
0x18002e4cf  jz      short loc_18002E543
0x18002e4d1  mov     word ptr [rbp+9D0h+var_820], r14w
0x18002e4d9  mov     word ptr [rsp+0AD0h+var_A60], r14w
0x18002e4df  test    rbx, rbx
0x18002e4e2  jz      short loc_18002E4E9
0x18002e4e4  mov     edx, [rbx+60h]
0x18002e4e7  jmp     short loc_18002E4EC
0x18002e4e9  or      edx, 0FFFFFFFFh
0x18002e4ec  lea     rcx, [rsp+0AD0h+var_A60]
0x18002e4f1  call    ConvertPortNoToString
0x18002e4f6  mov     r8d, [rsi]
0x18002e4f9  lea     rdx, aSecuritydlleve_1; "SecurityDllEventHandler:Security DLL fa"...
0x18002e500  lea     rcx, [rbp+9D0h+var_820]
0x18002e507  call    FormatRRASErrorString
0x18002e50c  test    cs:byte_1800CF404, 8
0x18002e513  jz      short loc_18002E543
0x18002e515  lea     rax, [rsp+0AD0h+var_A60]
0x18002e51a  mov     qword ptr [rsp+0AD0h+dwErrorCode], rax
0x18002e51f  lea     r9, [rsp+0AD0h+var_A90]
0x18002e524  lea     r8, [rbp+9D0h+var_820]
0x18002e52b  mov     [rsp+0AD0h+plpszSubStringArray], r14
0x18002e530  lea     rdx, RasDdmParamTraceError
0x18002e537  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002e53e  call    McTemplateU0zjzz_EventWriteTransfer
0x18002e543  mov     eax, [rbx+4B0h]
0x18002e549  test    eax, eax
0x18002e54b  jnz     loc_18002E62A
0x18002e551  mov     rax, [rbx]
0x18002e554  mov     rax, [rax+0B0h]
0x18002e55b  jmp     loc_18002E646
0x18002e560  lea     rax, [rbp+9D0h+WideCharStr]
0x18002e564  mov     [rsp+0AD0h+dwErrorCode], 101h; cchWideChar
0x18002e56c  lea     rsi, [rdi+14h]
0x18002e570  mov     [rsp+0AD0h+plpszSubStringArray], rax; lpWideCharStr
0x18002e575  mov     r8, rsi; lpMultiByteStr
0x18002e578  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002e57c  xor     edx, edx; dwFlags
0x18002e57e  xor     ecx, ecx; CodePage
0x18002e580  call    cs:__imp_MultiByteToWideChar
0x18002e587  nop     dword ptr [rax+rax+00h]
0x18002e58c  cmp     cs:dword_1800CF4E4, r14d
0x18002e593  lea     rax, [rbp+9D0h+WideCharStr]
0x18002e597  mov     [rsp+0AD0h+var_A80], rax
0x18002e59c  mov     edi, 1
0x18002e5a1  lea     rax, [rbx+2CAh]
0x18002e5a8  mov     [rsp+0AD0h+var_A80+8], rax
0x18002e5ad  jbe     short loc_18002E5DD
0x18002e5af  mov     rcx, cs:hLogHandle; hLogHandle
0x18002e5b6  lea     rax, [rsp+0AD0h+var_A80]
0x18002e5bb  mov     [rsp+0AD0h+dwErrorCode], r14d; dwErrorCode
0x18002e5c0  lea     r9d, [rdi+1]; dwSubStringCount
0x18002e5c4  mov     r8d, 4E7Dh; dwMessageId
0x18002e5ca  mov     [rsp+0AD0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002e5cf  mov     edx, edi; dwEventType
0x18002e5d1  call    cs:__imp_RouterLogEventW
0x18002e5d8  nop     dword ptr [rax+rax+00h]
0x18002e5dd  test    cs:byte_1800CF404, 8
0x18002e5e4  jz      loc_18002E543
0x18002e5ea  mov     word ptr [rbp+9D0h+var_820], r14w
0x18002e5f2  mov     word ptr [rsp+0AD0h+var_A60], r14w
0x18002e5f8  test    rbx, rbx
0x18002e5fb  jz      short loc_18002E602
0x18002e5fd  mov     edx, [rbx+60h]
0x18002e600  jmp     short loc_18002E605
0x18002e602  or      edx, 0FFFFFFFFh
0x18002e605  lea     rcx, [rsp+0AD0h+var_A60]
0x18002e60a  call    ConvertPortNoToString
0x18002e60f  mov     r8, rsi
0x18002e612  lea     rdx, aSecuritydlleve; "SecurityDllEventHandler:Security DLL fa"...
0x18002e619  lea     rcx, [rbp+9D0h+var_820]
0x18002e620  call    FormatRRASErrorString
0x18002e625  jmp     loc_18002E50C
0x18002e62a  cmp     eax, edi
0x18002e62c  jnz     loc_18002E778
0x18002e632  mov     rax, [rbx]
0x18002e635  mov     dword ptr [rbx+4B0h], 2
0x18002e63f  mov     rax, [rax+0B8h]
0x18002e646  mov     rcx, rbx
0x18002e649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e64e  jmp     loc_18002E778
0x18002e653  mov     rcx, [rbx+60h]
0x18002e657  lea     rdx, ?SvSecurityTimeout@@YAXPEAX@Z; SvSecurityTimeout(void *)
0x18002e65e  call    TimerQRemove
0x18002e663  mov     rcx, [rbx+4B8h]
0x18002e66a  test    rcx, rcx
0x18002e66d  jz      short loc_18002E682
0x18002e66f  call    cs:__imp_RasFreeBuffer
0x18002e676  nop     dword ptr [rax+rax+00h]
0x18002e67b  mov     [rbx+4B8h], r14
0x18002e682  lea     rax, [rbx+0A8h]
0x18002e689  mov     [rsp+0AD0h+dwErrorCode], 101h; cchWideChar
0x18002e691  lea     r8, [rdi+14h]; lpMultiByteStr
0x18002e695  mov     [rsp+0AD0h+plpszSubStringArray], rax; lpWideCharStr
0x18002e69a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002e69e  xor     edx, edx; dwFlags
0x18002e6a0  xor     ecx, ecx; CodePage
0x18002e6a2  call    cs:__imp_MultiByteToWideChar
0x18002e6a9  nop     dword ptr [rax+rax+00h]
0x18002e6ae  lea     rax, [rbx+2AAh]
0x18002e6b5  mov     [rsp+0AD0h+dwErrorCode], 10h; cchWideChar
0x18002e6bd  lea     r8, [rdi+115h]; lpMultiByteStr
0x18002e6c4  mov     [rsp+0AD0h+plpszSubStringArray], rax; lpWideCharStr
0x18002e6c9  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002e6cd  xor     edx, edx; dwFlags
0x18002e6cf  xor     ecx, ecx; CodePage
0x18002e6d1  call    cs:__imp_MultiByteToWideChar
0x18002e6d8  nop     dword ptr [rax+rax+00h]
0x18002e6dd  mov     rcx, [rbx+60h]
0x18002e6e1  mov     dword ptr [rbx+4B0h], 2
0x18002e6eb  call    cs:__imp_RasPortConnectComplete
0x18002e6f2  nop     dword ptr [rax+rax+00h]
0x18002e6f7  mov     ecx, 11h; unsigned int
0x18002e6fc  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18002e701  mov     rcx, rax
0x18002e704  xor     edx, edx
0x18002e706  mov     eax, [rbx+60h]
0x18002e709  div     dword ptr [rcx]
0x18002e70b  mov     rcx, cs:gblSupervisorEvents
0x18002e712  add     edx, 6
0x18002e715  mov     rcx, [rcx+rdx*8]; hEvent
0x18002e719  call    cs:__imp_SetEvent
0x18002e720  nop     dword ptr [rax+rax+00h]
0x18002e725  test    cs:byte_1800CF404, 8
0x18002e72c  jz      short loc_18002E778
0x18002e72e  mov     edx, [rbx+60h]
0x18002e731  lea     rcx, [rsp+0AD0h+var_A60]
0x18002e736  mov     word ptr [rsp+0AD0h+var_A60], r14w
0x18002e73c  call    ConvertPortNoToString
0x18002e741  test    cs:byte_1800CF404, 8
0x18002e748  jz      short loc_18002E778
0x18002e74a  lea     rax, [rsp+0AD0h+var_A60]
0x18002e74f  mov     qword ptr [rsp+0AD0h+dwErrorCode], rax
0x18002e754  lea     r9, [rsp+0AD0h+var_A90]
0x18002e759  lea     r8, aSecuritydlleve_0; "SecurityDllEventHandler: Security DLL s"...
0x18002e760  mov     [rsp+0AD0h+plpszSubStringArray], r14
0x18002e765  lea     rdx, RasDdmParamTraceError
0x18002e76c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002e773  call    McTemplateU0zjzz_EventWriteTransfer
0x18002e778  mov     rcx, [rbp+9D0h+var_20]
0x18002e77f  xor     rcx, rsp; StackCookie
0x18002e782  call    __security_check_cookie
0x18002e787  lea     r11, [rsp+0AD0h+var_10]
0x18002e78f  mov     rbx, [r11+30h]
0x18002e793  mov     rsi, [r11+38h]
0x18002e797  mov     rsp, r11
0x18002e79a  pop     r14
0x18002e79c  pop     rdi
0x18002e79d  pop     rbp
0x18002e79e  retn
```
