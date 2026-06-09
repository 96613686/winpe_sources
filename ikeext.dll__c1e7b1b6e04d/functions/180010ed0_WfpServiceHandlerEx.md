# WfpServiceHandlerEx

- ea: `0x180010ed0`
- end: `0x18001133b`
- name: `WfpServiceHandlerEx`
- size: `1131`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004508`
- `0x1800061ec`
- `0x180010db0`
- `0x180010ed0`
- `0x180011350`
- `0x180011680`
- `0x18004890c`
- `0x180050850`
- `0x180052350`
- `0x1800523fc`
- `0x180052534`
- `0x1800528e4`
- `0x1800529a4`
- `0x180119010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112a3`
- `ntdll!RtlNtStatusToDosError` at `0x180010fb4`
- `ntdll!RtlNtStatusToDosError` at `0x180010fb4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011295`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011295`

## string_xrefs

- `0x180010f82`: `WfpComponentDispatch`
- `0x180010f91`: `WfpComponentsDispatchForward`
- `0x180011072`: `WfpServiceHandlerEx`
- `0x1800110ff`: `WfpServiceHandlerEx`

## pseudocode

```c
__int64 __fastcall WfpServiceHandlerEx(__int64 dwControl, DWORD dwEventType, __int64 lpEventData, LPVOID lpContext)
{
  _BYTE *v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // r15
  __int64 v10; // rax
  __int64 result; // rax
  int v12; // eax
  int v13; // r8d
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // r8d
  int v18; // eax
  int v19; // edx
  int v20; // r8d
  int v21; // eax
  int TlsPeerAddr; // eax
  int v23; // r8d
  int v24; // eax
  int v25; // r8d
  DWORD LastError; // eax
  __int64 v27; // rcx
  int v28; // eax
  int v29; // r8d
  __int64 v30; // rax
  int v31; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v32[16]; // [rsp+38h] [rbp-60h] BYREF
  const char *v33; // [rsp+48h] [rbp-50h]
  __int64 v34; // [rsp+50h] [rbp-48h]
  int *v35; // [rsp+58h] [rbp-40h]
  __int64 v36; // [rsp+60h] [rbp-38h]

  if ( lpContext )
  {
    if ( (_DWORD)dwControl != 13 )
    {
      LODWORD(v7) = 0;
      v14 = (unsigned int)(dwControl - 1);
      if ( (_DWORD)v14 )
      {
        v15 = (unsigned int)(v14 - 3);
        if ( !(_DWORD)v15 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            TlsPeerAddr = IkeGetTlsPeerAddr(v15);
            WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v23, TlsPeerAddr, *(_QWORD *)lpContext);
          }
          goto LABEL_16;
        }
        if ( (_DWORD)v15 != 1 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v18 = IkeGetTlsPeerAddr(v15);
            WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, v18, (__int64)"WfpServiceHandlerEx", 120);
          }
          if ( gWfpLogUserModeErrors && (byte_180178161 & 1) != 0 )
          {
            v31 = 120;
            v35 = &v31;
            v33 = "WfpServiceHandlerEx";
            v34 = 20;
            v36 = 4;
            McGenEventWrite_EtwEventWriteTransfer(
              &MICROSOFT_WFP_PROVIDER_Context,
              (__int64)WFP_USERMODE_ERROR,
              lpEventData,
              3,
              (__int64)v32);
          }
          LODWORD(v7) = -2147024776;
          goto LABEL_16;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v21 = IkeGetTlsPeerAddr(v15);
          WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, *(_QWORD *)lpContext, v21, *(_QWORD *)lpContext);
        }
        *((_DWORD *)lpContext + 15) = 2;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v24 = IkeGetTlsPeerAddr(v14);
          WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v25, v24, *(_QWORD *)lpContext);
        }
        *((_DWORD *)lpContext + 15) = 1;
      }
      WfpServiceChangeState(lpContext, 3);
      if ( !SetEvent(*((HANDLE *)lpContext + 8)) )
      {
        LastError = GetLastError();
        LODWORD(v7) = WfpReportSysErrorAsWinError(v27, "SetEvent", LastError, 1);
      }
      goto LABEL_16;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v28 = IkeGetTlsPeerAddr(dwControl);
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v29, v28, *(_QWORD *)lpContext);
      v6 = WPP_GLOBAL_Control;
    }
    LODWORD(v7) = 0;
    v8 = 0;
    if ( *((_QWORD *)lpContext + 2) )
    {
      while ( 1 )
      {
        v9 = *((_QWORD *)lpContext + 1) + 16 * v8;
        if ( v6 != (_BYTE *)&WPP_GLOBAL_Control && v6[25] >= 3u && (v6[28] & 1) != 0 )
        {
          v12 = IkeGetTlsPeerAddr(dwControl);
          WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v13, v12, (__int64)L"POWER_EVENT", *(_QWORD *)(v9 + 8));
        }
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))v9)(3, dwEventType, lpEventData);
        v7 = v10;
        if ( v10 )
          break;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v30 = IkeGetTlsPeerAddr(dwControl);
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_afd810515d1c3db64468bc5743bd872b_Traceguids, v30);
          v6 = WPP_GLOBAL_Control;
        }
        if ( (unsigned __int64)++v8 >= *((_QWORD *)lpContext + 2) )
          goto LABEL_16;
      }
      WfpReportError(v10, "WfpComponentDispatch");
      WfpReportError(v7, "WfpComponentsDispatchForward");
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = IkeGetTlsPeerAddr(dwControl);
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v17, v16, (__int64)"WfpServiceHandlerEx", 13);
    }
    LODWORD(v7) = RtlNtStatusToDosError(-1073741811);
    WfpCallUsermodeErrorUTMacro("WfpServiceHandlerEx", (unsigned int)v7);
    if ( (int)v7 > 0 )
      LODWORD(v7) = (unsigned __int16)v7 | 0x80070000;
  }
LABEL_16:
  result = (unsigned __int16)v7;
  if ( (v7 & 0x1FFF0000) != 0x70000 )
    return (unsigned int)v7;
  return result;
}

```

## disassembly

```asm
0x180010ed0  push    rbx
0x180010ed2  push    rbp
0x180010ed3  push    rdi
0x180010ed4  push    r14
0x180010ed6  sub     rsp, 78h
0x180010eda  mov     rax, cs:__security_cookie
0x180010ee1  xor     rax, rsp
0x180010ee4  mov     [rsp+98h+var_30], rax
0x180010ee9  mov     rdi, r9
0x180010eec  mov     r14d, edx
0x180010eef  test    r9, r9
0x180010ef2  jz      loc_1800110F1
0x180010ef8  cmp     ecx, 0Dh
0x180010efb  jnz     loc_180011047
0x180010f01  mov     rdx, cs:WPP_GLOBAL_Control
0x180010f08  lea     rbp, WPP_GLOBAL_Control
0x180010f0f  mov     [rsp+98h+arg_0], rsi
0x180010f17  cmp     rdx, rbp
0x180010f1a  jz      short loc_180010F26
0x180010f1c  cmp     byte ptr [rdx+19h], 3
0x180010f20  jnb     loc_1800112C6
0x180010f26  xor     ebx, ebx
0x180010f28  mov     esi, ebx
0x180010f2a  cmp     [rdi+10h], rbx
0x180010f2e  jbe     short loc_180010FA5
0x180010f30  mov     [rsp+98h+var_28], r15
0x180010f35  mov     r15, rsi
0x180010f38  shl     r15, 4
0x180010f3c  add     r15, [rdi+8]
0x180010f40  cmp     rdx, rbp
0x180010f43  jnz     loc_180010FFC
0x180010f49  mov     rax, [r15]
0x180010f4c  mov     edx, r14d
0x180010f4f  mov     ecx, 3
0x180010f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f59  mov     rbx, rax
0x180010f5c  test    rax, rax
0x180010f5f  jnz     short loc_180010F82
0x180010f61  mov     rdx, cs:WPP_GLOBAL_Control
0x180010f68  cmp     rdx, rbp
0x180010f6b  jz      short loc_180010F77
0x180010f6d  cmp     byte ptr [rdx+19h], 3
0x180010f71  jnb     loc_180011301
0x180010f77  inc     rsi
0x180010f7a  cmp     rsi, [rdi+10h]
0x180010f7e  jb      short loc_180010F35
0x180010f80  jmp     short loc_180010FA0
0x180010f82  lea     rdx, aWfpcomponentdi; "WfpComponentDispatch"
0x180010f89  mov     rcx, rbx
0x180010f8c  call    WfpReportError
0x180010f91  lea     rdx, aWfpcomponentsd; "WfpComponentsDispatchForward"
0x180010f98  mov     rcx, rbx
0x180010f9b  call    WfpReportError
0x180010fa0  mov     r15, [rsp+98h+var_28]
0x180010fa5  mov     rsi, [rsp+98h+arg_0]
0x180010fad  jmp     short loc_180010FD1
0x180010faf  mov     ecx, 0C000000Dh; Status
0x180010fb4  call    cs:__imp_RtlNtStatusToDosError
0x180010fba  mov     edx, eax
0x180010fbc  mov     rcx, rdi
0x180010fbf  mov     ebx, eax
0x180010fc1  call    WfpCallUsermodeErrorUTMacro
0x180010fc6  test    ebx, ebx
0x180010fc8  jg      loc_180011152
0x180010fce  movsxd  rbx, ebx
0x180010fd1  mov     ecx, ebx
0x180010fd3  movzx   eax, bx
0x180010fd6  and     ecx, 1FFF0000h
0x180010fdc  cmp     ecx, 70000h
0x180010fe2  cmovnz  eax, ebx
0x180010fe5  mov     rcx, [rsp+98h+var_30]
0x180010fea  xor     rcx, rsp; StackCookie
0x180010fed  call    __security_check_cookie
0x180010ff2  add     rsp, 78h
0x180010ff6  pop     r14
0x180010ff8  pop     rdi
0x180010ff9  pop     rbp
0x180010ffa  pop     rbx
0x180010ffb  retn
0x180010ffc  cmp     byte ptr [rdx+19h], 3
0x180011000  jb      loc_180010F49
0x180011006  test    byte ptr [rdx+1Ch], 1
0x18001100a  jz      loc_180010F49
0x180011010  mov     rbx, cs:off_18011A1E0; "POWER_EVENT"
0x180011017  call    IkeGetTlsPeerAddr
0x18001101c  mov     rcx, [r15+8]
0x180011020  mov     edx, 0Ah
0x180011025  mov     [rsp+98h+var_70], rcx
0x18001102a  mov     r9, rax
0x18001102d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011034  mov     [rsp+98h+var_78], rbx
0x180011039  mov     rcx, [rcx+10h]
0x18001103d  call    WPP_SF_SSS
0x180011042  jmp     loc_180010F49
0x180011047  xor     ebx, ebx
0x180011049  sub     ecx, 1
0x18001104c  jz      loc_180011239
0x180011052  sub     ecx, 3
0x180011055  jz      loc_1800111E4
0x18001105b  cmp     ecx, 1
0x18001105e  jz      loc_180011194
0x180011064  mov     rax, cs:WPP_GLOBAL_Control
0x18001106b  lea     rbp, WPP_GLOBAL_Control
0x180011072  lea     rdi, aWfpservicehand; "WfpServiceHandlerEx"
0x180011079  cmp     rax, rbp
0x18001107c  jz      short loc_180011088
0x18001107e  cmp     byte ptr [rax+19h], 2
0x180011082  jnb     loc_180011160
0x180011088  cmp     cs:gWfpLogUserModeErrors, ebx
0x18001108e  jz      short loc_1800110E5
0x180011090  test    cs:byte_180178161, 1
0x180011097  jz      short loc_1800110E5
0x180011099  lea     rax, [rsp+98h+var_68]
0x18001109e  mov     [rsp+98h+var_68], 78h ; 'x'
0x1800110a6  mov     [rsp+98h+var_40], rax
0x1800110ab  lea     rdx, WFP_USERMODE_ERROR
0x1800110b2  lea     rax, [rsp+98h+var_60]
0x1800110b7  mov     [rsp+98h+var_50], rdi
0x1800110bc  mov     r9d, 3
0x1800110c2  mov     [rsp+98h+var_78], rax
0x1800110c7  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800110ce  mov     [rsp+98h+var_48], 14h
0x1800110d7  mov     [rsp+98h+var_38], 4
0x1800110e0  call    McGenEventWrite_EtwEventWriteTransfer
0x1800110e5  mov     rbx, 0FFFFFFFF80070078h
0x1800110ec  jmp     loc_180010FD1
0x1800110f1  mov     rax, cs:WPP_GLOBAL_Control
0x1800110f8  lea     rbp, WPP_GLOBAL_Control
0x1800110ff  lea     rdi, aWfpservicehand; "WfpServiceHandlerEx"
0x180011106  cmp     rax, rbp
0x180011109  jz      loc_180010FAF
0x18001110f  cmp     byte ptr [rax+19h], 2
0x180011113  jb      loc_180010FAF
0x180011119  test    byte ptr [rax+1Ch], 1
0x18001111d  jz      loc_180010FAF
0x180011123  call    IkeGetTlsPeerAddr
0x180011128  mov     rcx, cs:WPP_GLOBAL_Control
0x18001112f  mov     edx, 16h
0x180011134  mov     dword ptr [rsp+98h+var_70], 0C000000Dh
0x18001113c  mov     r9, rax
0x18001113f  mov     [rsp+98h+var_78], rdi
0x180011144  mov     rcx, [rcx+10h]
0x180011148  call    WPP_SF_Ssd
0x18001114d  jmp     loc_180010FAF
0x180011152  movzx   ebx, bx
0x180011155  or      ebx, 80070000h
0x18001115b  jmp     loc_180010FCE
0x180011160  test    byte ptr [rax+1Ch], 1
0x180011164  jz      loc_180011088
0x18001116a  call    IkeGetTlsPeerAddr
0x18001116f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011176  mov     r9, rax
0x180011179  mov     dword ptr [rsp+98h+var_70], 78h ; 'x'
0x180011181  mov     [rsp+98h+var_78], rdi
0x180011186  mov     rcx, [rcx+10h]
0x18001118a  call    WPP_SF_SsD
0x18001118f  jmp     loc_180011088
0x180011194  mov     rax, cs:WPP_GLOBAL_Control
0x18001119b  lea     rbp, WPP_GLOBAL_Control
0x1800111a2  cmp     rax, rbp
0x1800111a5  jz      short loc_1800111D8
0x1800111a7  cmp     byte ptr [rax+19h], 3
0x1800111ab  jb      short loc_1800111D8
0x1800111ad  test    byte ptr [rax+1Ch], 1
0x1800111b1  jz      short loc_1800111D8
0x1800111b3  call    IkeGetTlsPeerAddr
0x1800111b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111bf  mov     edx, 0Eh
0x1800111c4  mov     r8, [rdi]
0x1800111c7  mov     r9, rax
0x1800111ca  mov     [rsp+98h+var_78], r8
0x1800111cf  mov     rcx, [rcx+10h]
0x1800111d3  call    WPP_SF_SS
0x1800111d8  mov     dword ptr [rdi+3Ch], 2
0x1800111df  jmp     loc_180011284
0x1800111e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800111eb  lea     rbp, WPP_GLOBAL_Control
0x1800111f2  cmp     rax, rbp
0x1800111f5  jz      loc_180010FD1
0x1800111fb  cmp     byte ptr [rax+19h], 3
0x1800111ff  jb      loc_180010FD1
0x180011205  test    byte ptr [rax+1Ch], 1
0x180011209  jz      loc_180010FD1
0x18001120f  call    IkeGetTlsPeerAddr
0x180011214  mov     rcx, [rdi]
0x180011217  mov     edx, 0Fh
0x18001121c  mov     [rsp+98h+var_78], rcx
0x180011221  mov     r9, rax
0x180011224  mov     rcx, cs:WPP_GLOBAL_Control
0x18001122b  mov     rcx, [rcx+10h]
0x18001122f  call    WPP_SF_SS
0x180011234  jmp     loc_180010FD1
0x180011239  mov     rax, cs:WPP_GLOBAL_Control
0x180011240  lea     rbp, WPP_GLOBAL_Control
0x180011247  cmp     rax, rbp
0x18001124a  jz      short loc_18001127D
0x18001124c  cmp     byte ptr [rax+19h], 3
0x180011250  jb      short loc_18001127D
0x180011252  test    byte ptr [rax+1Ch], 1
0x180011256  jz      short loc_18001127D
0x180011258  call    IkeGetTlsPeerAddr
0x18001125d  mov     rcx, [rdi]
0x180011260  mov     edx, 0Dh
0x180011265  mov     [rsp+98h+var_78], rcx
0x18001126a  mov     r9, rax
0x18001126d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011274  mov     rcx, [rcx+10h]
0x180011278  call    WPP_SF_SS
0x18001127d  mov     dword ptr [rdi+3Ch], 1
0x180011284  mov     edx, 3
0x180011289  mov     rcx, rdi
0x18001128c  call    WfpServiceChangeState
0x180011291  mov     rcx, [rdi+40h]; hEvent
0x180011295  call    cs:__imp_SetEvent
0x18001129b  test    eax, eax
0x18001129d  jnz     loc_180010FD1
0x1800112a3  call    cs:__imp_GetLastError
0x1800112a9  mov     r9d, 1
0x1800112af  lea     rdx, aSetevent; "SetEvent"
0x1800112b6  mov     r8d, eax
0x1800112b9  call    WfpReportSysErrorAsWinError
0x1800112be  mov     rbx, rax
0x1800112c1  jmp     loc_180010FD1
0x1800112c6  test    byte ptr [rdx+1Ch], 1
0x1800112ca  jz      loc_180010F26
0x1800112d0  call    IkeGetTlsPeerAddr
0x1800112d5  mov     rcx, [rdi]
0x1800112d8  mov     edx, 10h
0x1800112dd  mov     [rsp+98h+var_78], rcx
0x1800112e2  mov     r9, rax
0x1800112e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112ec  mov     rcx, [rcx+10h]
0x1800112f0  call    WPP_SF_SS
0x1800112f5  mov     rdx, cs:WPP_GLOBAL_Control
0x1800112fc  jmp     loc_180010F26
0x180011301  test    byte ptr [rdx+1Ch], 1
0x180011305  jz      loc_180010F77
0x18001130b  call    IkeGetTlsPeerAddr
0x180011310  mov     rcx, cs:WPP_GLOBAL_Control
0x180011317  lea     r8, WPP_afd810515d1c3db64468bc5743bd872b_Traceguids
0x18001131e  mov     edx, 0Bh
0x180011323  mov     r9, rax
0x180011326  mov     rcx, [rcx+10h]
0x18001132a  call    WPP_SF_S
0x18001132f  mov     rdx, cs:WPP_GLOBAL_Control
0x180011336  jmp     loc_180010F77
```
