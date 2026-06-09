# CRdpHintManager::InitializeHintRpcServer(void)

- ea: `0x1400343f0`
- end: `0x140034729`
- name: `?InitializeHintRpcServer@CRdpHintManager@@EEAAJXZ`
- size: `825`
- prototype: `__int64 __fastcall(CRdpHintManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400340a4`

## callees

- `0x140004b1c`
- `0x140004cf4`
- `0x140005704`
- `0x140005750`
- `0x140008ce0`
- `0x14000a640`
- `0x14000cae0`
- `0x1400343f0`
- `0x140035e34`
- `0x14005a978`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003447f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003447f`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14003443e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14003443e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140034431`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140034431`
- `RPCRT4!RpcServerListen` at `0x140034668`
- `RPCRT4!RpcServerListen` at `0x140034668`

## string_xrefs

- `0x1400345c7`: `Failed TSCreateLpcServer`

## pseudocode

```c
__int64 __fastcall CRdpHintManager::InitializeHintRpcServer(CRdpHintManager *this)
{
  struct CLrpcServer *v2; // rbx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  signed int v5; // esi
  DWORD v6; // edi
  unsigned int v7; // eax
  struct ITSPlatform *v8; // rcx
  unsigned int v9; // eax
  int v10; // edx
  const char *v11; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v13; // eax
  RPC_STATUS v14; // eax
  RPC_STATUS v15; // r15d
  unsigned int v16; // eax
  struct CLrpcServer *v18; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pSessionId; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v20[264]; // [rsp+40h] [rbp-C0h] BYREF

  v2 = 0;
  v18 = 0;
  TCntPtr<CRdpWindowTracker>::SafeAddRef(&v18);
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    v5 = StringCchPrintfW(v20, 0x104u, L"HintApiRPCEntry#%d", pSessionId);
    if ( v5 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          108,
          (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v20);
      }
      v5 = TSCreateLrpcServer(v8, v20, &v18);
      if ( v5 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            109,
            (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
            v13,
            (__int64)"Failed TSCreateLpcServer",
            v5);
        }
        v2 = v18;
        goto LABEL_39;
      }
      v2 = v18;
      v5 = (*(__int64 (__fastcall **)(struct CLrpcServer *, __int64 *))(*(_QWORD *)v18 + 24LL))(v18, qword_14006EBD0);
      if ( v5 >= 0 )
      {
        v14 = RpcServerListen(1u, 0x4D2u, 1u);
        v15 = 0;
        if ( v14 != 1713 )
          v15 = v14;
        if ( v15 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              111,
              &WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
              v16,
              v15);
          }
          v5 = -2147467259;
          goto LABEL_39;
        }
        if ( v2 != *((struct CLrpcServer **)this + 16) )
        {
          TCntPtr<CRdpClipMainWnd>::SafeRelease((char *)this + 128);
          *((_QWORD *)this + 16) = v2;
          TCntPtr<CRdpWindowTracker>::SafeAddRef((char *)this + 128);
        }
        goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 110;
        v11 = "spLrpcServer->StartServer() failed";
        goto LABEL_15;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 107;
      v11 = "StringCchPrintf() failed";
LABEL_15:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        v9,
        (__int64)v11,
        v5);
    }
LABEL_39:
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*((_QWORD *)v2 + 1) + 24LL))((__int64)v2 + 8);
    goto LABEL_43;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = GetLastError();
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids, v7, v6, v5);
  }
  if ( v5 < 0 )
    goto LABEL_39;
LABEL_43:
  TCntPtr<CRdpClipMainWnd>::SafeRelease(&v18);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400343f0  push    rbp
0x1400343f2  push    rbx
0x1400343f3  push    rsi
0x1400343f4  push    rdi
0x1400343f5  push    r13
0x1400343f7  push    r15
0x1400343f9  lea     rbp, [rsp-168h]
0x140034401  sub     rsp, 268h
0x140034408  mov     rax, cs:__security_cookie
0x14003440f  xor     rax, rsp
0x140034412  mov     [rbp+190h+var_40], rax
0x140034419  mov     r13, rcx
0x14003441c  xor     ebx, ebx
0x14003441e  lea     rcx, [rsp+290h+var_260]
0x140034423  mov     [rsp+290h+var_260], rbx
0x140034428  call    ?SafeAddRef@?$TCntPtr@VCRdpWindowTracker@@@@AEAAXXZ; TCntPtr<CRdpWindowTracker>::SafeAddRef(void)
0x14003442d  mov     [rsp+290h+pSessionId], ebx
0x140034431  call    cs:__imp_GetCurrentProcessId
0x140034437  mov     ecx, eax; dwProcessId
0x140034439  lea     rdx, [rsp+290h+pSessionId]; pSessionId
0x14003443e  call    cs:__imp_ProcessIdToSessionId
0x140034444  test    eax, eax
0x140034446  jnz     short loc_1400344C0
0x140034448  call    cs:__imp_GetLastError
0x14003444e  mov     esi, eax
0x140034450  test    eax, eax
0x140034452  jle     short loc_14003445D
0x140034454  movzx   esi, ax
0x140034457  or      esi, 80070000h
0x14003445d  mov     rax, cs:WPP_GLOBAL_Control
0x140034464  lea     rdi, WPP_GLOBAL_Control
0x14003446b  cmp     rax, rdi
0x14003446e  jz      short loc_1400344B3
0x140034470  test    dword ptr [rax+1Ch], 200h
0x140034477  jz      short loc_1400344B3
0x140034479  cmp     byte ptr [rax+19h], 2
0x14003447d  jb      short loc_1400344B3
0x14003447f  call    cs:__imp_GetLastError
0x140034485  mov     edi, eax
0x140034487  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003448c  mov     rcx, cs:WPP_GLOBAL_Control
0x140034493  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x14003449a  mov     edx, 6Ah ; 'j'
0x14003449f  mov     [rsp+290h+var_268], esi
0x1400344a3  mov     r9d, eax
0x1400344a6  mov     dword ptr [rsp+290h+var_270], edi
0x1400344aa  mov     rcx, [rcx+10h]
0x1400344ae  call    WPP_SF_DdD
0x1400344b3  test    esi, esi
0x1400344b5  jns     loc_1400346FE
0x1400344bb  jmp     loc_1400346C8
0x1400344c0  mov     r9d, [rsp+290h+pSessionId]
0x1400344c5  lea     r8, aHintapirpcentr; "HintApiRPCEntry#%d"
0x1400344cc  mov     edx, 104h; unsigned __int64
0x1400344d1  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x1400344d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400344db  mov     esi, eax
0x1400344dd  test    eax, eax
0x1400344df  jns     short loc_140034545
0x1400344e1  mov     rax, cs:WPP_GLOBAL_Control
0x1400344e8  lea     rdi, WPP_GLOBAL_Control
0x1400344ef  cmp     rax, rdi
0x1400344f2  jz      loc_1400346C8
0x1400344f8  test    byte ptr [rax+1Ch], 8
0x1400344fc  jz      loc_1400346C8
0x140034502  cmp     byte ptr [rax+19h], 2
0x140034506  jb      loc_1400346C8
0x14003450c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140034511  mov     edx, 6Bh ; 'k'
0x140034516  lea     rcx, aStringcchprint_0; "StringCchPrintf() failed"
0x14003451d  mov     [rsp+290h+var_268], esi
0x140034521  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140034528  mov     [rsp+290h+var_270], rcx
0x14003452d  mov     r9d, eax
0x140034530  mov     rcx, cs:WPP_GLOBAL_Control
0x140034537  mov     rcx, [rcx+10h]
0x14003453b  call    WPP_SF_DsD
0x140034540  jmp     loc_1400346C8
0x140034545  mov     rax, cs:WPP_GLOBAL_Control
0x14003454c  lea     rdi, WPP_GLOBAL_Control
0x140034553  cmp     rax, rdi
0x140034556  jz      short loc_140034595
0x140034558  test    dword ptr [rax+1Ch], 200h
0x14003455f  jz      short loc_140034595
0x140034561  cmp     byte ptr [rax+19h], 4
0x140034565  jb      short loc_140034595
0x140034567  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003456c  lea     rcx, [rsp+290h+var_250]
0x140034571  mov     edx, 6Ch ; 'l'
0x140034576  mov     [rsp+290h+var_270], rcx
0x14003457b  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140034582  mov     rcx, cs:WPP_GLOBAL_Control
0x140034589  mov     r9d, eax
0x14003458c  mov     rcx, [rcx+10h]
0x140034590  call    WPP_SF_DS
0x140034595  lea     r8, [rsp+290h+var_260]; struct CLrpcServer **
0x14003459a  lea     rdx, [rsp+290h+var_250]; unsigned __int16 *
0x14003459f  call    ?TSCreateLrpcServer@@YAJPEAVITSPlatform@@PEBGPEAPEAVCLrpcServer@@@Z; TSCreateLrpcServer(ITSPlatform *,ushort const *,CLrpcServer * *)
0x1400345a4  mov     esi, eax
0x1400345a6  test    eax, eax
0x1400345a8  jns     short loc_140034600
0x1400345aa  mov     rax, cs:WPP_GLOBAL_Control
0x1400345b1  cmp     rax, rdi
0x1400345b4  jz      short loc_1400345F6
0x1400345b6  test    byte ptr [rax+1Ch], 8
0x1400345ba  jz      short loc_1400345F6
0x1400345bc  cmp     byte ptr [rax+19h], 2
0x1400345c0  jb      short loc_1400345F6
0x1400345c2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400345c7  lea     rcx, aFailedTscreate; "Failed TSCreateLpcServer"
0x1400345ce  mov     [rsp+290h+var_268], esi
0x1400345d2  mov     [rsp+290h+var_270], rcx
0x1400345d7  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x1400345de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400345e5  mov     edx, 6Dh ; 'm'
0x1400345ea  mov     r9d, eax
0x1400345ed  mov     rcx, [rcx+10h]
0x1400345f1  call    WPP_SF_DsD
0x1400345f6  mov     rbx, [rsp+290h+var_260]
0x1400345fb  jmp     loc_1400346C8
0x140034600  mov     rbx, [rsp+290h+var_260]
0x140034605  lea     rdx, qword_14006EBD0
0x14003460c  mov     rcx, rbx
0x14003460f  mov     rax, [rbx]
0x140034612  mov     rax, [rax+18h]
0x140034616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003461b  mov     esi, eax
0x14003461d  test    eax, eax
0x14003461f  jns     short loc_14003465B
0x140034621  mov     rax, cs:WPP_GLOBAL_Control
0x140034628  cmp     rax, rdi
0x14003462b  jz      loc_1400346C8
0x140034631  test    byte ptr [rax+1Ch], 8
0x140034635  jz      loc_1400346C8
0x14003463b  cmp     byte ptr [rax+19h], 2
0x14003463f  jb      loc_1400346C8
0x140034645  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003464a  mov     edx, 6Eh ; 'n'
0x14003464f  lea     rcx, aSplrpcserverSt; "spLrpcServer->StartServer() failed"
0x140034656  jmp     loc_14003451D
0x14003465b  mov     ecx, 1; MinimumCallThreads
0x140034660  mov     edx, 4D2h; MaxCalls
0x140034665  mov     r8d, ecx; DontWait
0x140034668  call    cs:__imp_RpcServerListen
0x14003466e  xor     r15d, r15d
0x140034671  cmp     eax, 6B1h
0x140034676  cmovnz  r15d, eax
0x14003467a  test    r15d, r15d
0x14003467d  jz      short loc_1400346DF
0x14003467f  mov     rax, cs:WPP_GLOBAL_Control
0x140034686  cmp     rax, rdi
0x140034689  jz      short loc_1400346C3
0x14003468b  test    dword ptr [rax+1Ch], 200h
0x140034692  jz      short loc_1400346C3
0x140034694  cmp     byte ptr [rax+19h], 2
0x140034698  jb      short loc_1400346C3
0x14003469a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003469f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400346a6  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x1400346ad  mov     edx, 6Fh ; 'o'
0x1400346b2  mov     dword ptr [rsp+290h+var_270], r15d
0x1400346b7  mov     r9d, eax
0x1400346ba  mov     rcx, [rcx+10h]
0x1400346be  call    WPP_SF_Dd
0x1400346c3  mov     esi, 80004005h
0x1400346c8  test    rbx, rbx
0x1400346cb  jz      short loc_1400346FE
0x1400346cd  lea     rcx, [rbx+8]
0x1400346d1  mov     rax, [rcx]
0x1400346d4  mov     rax, [rax+18h]
0x1400346d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400346dd  jmp     short loc_1400346FE
0x1400346df  lea     rdi, [r13+80h]
0x1400346e6  cmp     rbx, [rdi]
0x1400346e9  jz      short loc_1400346FE
0x1400346eb  mov     rcx, rdi
0x1400346ee  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x1400346f3  mov     rcx, rdi
0x1400346f6  mov     [rdi], rbx
0x1400346f9  call    ?SafeAddRef@?$TCntPtr@VCRdpWindowTracker@@@@AEAAXXZ; TCntPtr<CRdpWindowTracker>::SafeAddRef(void)
0x1400346fe  lea     rcx, [rsp+290h+var_260]
0x140034703  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x140034708  mov     eax, esi
0x14003470a  mov     rcx, [rbp+190h+var_40]
0x140034711  xor     rcx, rsp; StackCookie
0x140034714  call    __security_check_cookie
0x140034719  add     rsp, 268h
0x140034720  pop     r15
0x140034722  pop     r13
0x140034724  pop     rdi
0x140034725  pop     rsi
0x140034726  pop     rbx
0x140034727  pop     rbp
0x140034728  retn
```
