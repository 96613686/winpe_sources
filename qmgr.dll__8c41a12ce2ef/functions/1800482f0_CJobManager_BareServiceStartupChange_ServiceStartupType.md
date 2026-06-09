# CJobManager::BareServiceStartupChange(ServiceStartupType)

- ea: `0x1800482f0`
- end: `0x1800487fd`
- name: `?BareServiceStartupChange@CJobManager@@SA_NW4ServiceStartupType@@@Z`
- size: `1293`
- prototype: `char __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180046f5c`
- `0x180047114`

## callees

- `0x180006640`
- `0x1800482f0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800ab7b0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004836f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004840f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004856d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004869b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004872c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004836f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004840f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004856d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004869b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004872c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800487d4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800487e2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800487d4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800487e2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800483f8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800483f8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004835c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004835c`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18004855f`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18004855f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180048691`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180048691`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180048722`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180048722`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800484d3`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800484d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CJobManager::BareServiceStartupChange(unsigned int a1)
{
  char v2; // si
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // r15
  DWORD LastError; // eax
  signed int v6; // ebx
  SC_HANDLE v7; // r12
  DWORD v8; // eax
  signed int v9; // ebx
  DWORD v10; // r13d
  struct _QUERY_SERVICE_CONFIGW *v11; // rbx
  DWORD v12; // eax
  signed int v13; // ebx
  EVENT_LOG *v14; // rcx
  __int64 v15; // rdx
  DWORD v16; // eax
  EVENT_LOG *v17; // rcx
  signed int v18; // ebx
  char result; // al
  SC_HANDLE v20; // [rsp+60h] [rbp-1D8h]
  SC_HANDLE hSCObject; // [rsp+68h] [rbp-1D0h]
  void **pExceptionObject; // [rsp+70h] [rbp-1C8h] BYREF
  __int128 v23; // [rsp+78h] [rbp-1C0h]
  signed int v24; // [rsp+88h] [rbp-1B0h]
  int v25; // [rsp+8Ch] [rbp-1ACh]
  int v26; // [rsp+90h] [rbp-1A8h]
  void **v27; // [rsp+D0h] [rbp-168h] BYREF
  __int128 v28; // [rsp+D8h] [rbp-160h]
  signed int v29; // [rsp+E8h] [rbp-150h]
  int v30; // [rsp+ECh] [rbp-14Ch]
  int v31; // [rsp+F0h] [rbp-148h]
  void **v32; // [rsp+130h] [rbp-108h] BYREF
  __int128 v33; // [rsp+138h] [rbp-100h]
  signed int v34; // [rsp+148h] [rbp-F0h]
  int v35; // [rsp+14Ch] [rbp-ECh]
  int v36; // [rsp+150h] [rbp-E8h]
  void **v37; // [rsp+190h] [rbp-A8h] BYREF
  __int128 v38; // [rsp+198h] [rbp-A0h]
  signed int v39; // [rsp+1A8h] [rbp-90h]
  int v40; // [rsp+1ACh] [rbp-8Ch]
  int v41; // [rsp+1B0h] [rbp-88h]
  ComError *v42; // [rsp+1F0h] [rbp-48h] BYREF
  int Buffer; // [rsp+250h] [rbp+18h] BYREF
  DWORD pcbBytesNeeded; // [rsp+258h] [rbp+20h] BYREF

  v2 = 1;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 255, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, a1);
  v3 = OpenSCManagerW(0, 0, 0x80000000);
  try
  {
    v4 = v3;
    hSCObject = v3;
    if ( !v3 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 256, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, LastError);
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      v23 = 0;
      pExceptionObject = &ComError::`vftable';
      v24 = v6;
      v25 = 6010;
      v26 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v7 = OpenServiceW(v3, L"BITS", 0x80000002);
    v20 = v7;
    if ( !v7 )
    {
      v8 = GetLastError();
      v9 = v8;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 257, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, v8);
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v28 = 0;
      v27 = &ComError::`vftable';
      v29 = v9;
      v30 = 6018;
      v31 = 1;
      throw (ComError *)&v27;
    }
    pcbBytesNeeded = 0;
    v10 = (a1 != 2) + 2;
    v11 = (struct _QUERY_SERVICE_CONFIGW *)operator new(0x2000u);
    if ( !QueryServiceConfigW(v7, v11, 0x2000u, &pcbBytesNeeded) )
    {
      v12 = GetLastError();
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 258, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, v12);
      goto LABEL_23;
    }
    if ( v11->dwStartType == 4 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_39;
      v15 = 259;
    }
    else
    {
      if ( v11->dwStartType != v10 )
      {
LABEL_23:
        if ( !ChangeServiceConfigW(v7, 0xFFFFFFFF, v10, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
        {
          v13 = GetLastError();
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              261,
              &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
              (unsigned int)v13,
              a1);
          if ( v13 > 0 )
            v13 = (unsigned __int16)v13 | 0x80070000;
          v33 = 0;
          v32 = &ComError::`vftable';
          v34 = v13;
          v35 = 6058;
          v36 = 1;
          throw (ComError *)&v32;
        }
LABEL_39:
        Buffer = 0;
        if ( !QueryServiceConfig2W(v7, 3u, (LPBYTE)&Buffer, 4u, &pcbBytesNeeded) )
        {
          v16 = GetLastError();
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_44;
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 262, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, v16);
        }
        v17 = WPP_GLOBAL_Control;
LABEL_44:
        if ( Buffer )
        {
          if ( v17 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)v17 + 2), 263, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
        }
        else
        {
          Buffer = 1;
          if ( !ChangeServiceConfig2W(v7, 3u, &Buffer) )
          {
            v18 = GetLastError();
            if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                264,
                &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
                (unsigned int)v18,
                a1);
            }
            if ( v18 > 0 )
              v18 = (unsigned __int16)v18 | 0x80070000;
            v38 = 0;
            v37 = &ComError::`vftable';
            v39 = v18;
            v40 = 6090;
            v41 = 1;
            throw (ComError *)&v37;
          }
        }
        if ( v11 )
          operator delete(v11, 1u);
        goto LABEL_66;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_39;
      v15 = 260;
    }
    WPP_SF_(*((_QWORD *)v14 + 2), v15, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
    goto LABEL_39;
  }
  catch ( ComError *v42 )
  {
    v7 = v20;
    v2 = 0;
    v4 = hSCObject;
    if ( v20 )
      goto LABEL_66;
LABEL_60:
    if ( v4 )
      CloseServiceHandle(v4);
    result = v2;
  }
LABEL_66:
  CloseServiceHandle(v7);
  goto LABEL_60;
}

```

## disassembly

```asm
0x1800482f0  mov     [rsp+arg_0], ecx
0x1800482f4  push    rbx
0x1800482f5  push    rsi
0x1800482f6  push    r12
0x1800482f8  push    r13
0x1800482fa  push    r14
0x1800482fc  push    r15
0x1800482fe  sub     rsp, 208h
0x180048305  mov     ebx, ecx
0x180048307  mov     esi, 1
0x18004830c  mov     [rsp+238h+var_1D8], 0
0x180048315  lea     r13, WPP_GLOBAL_Control
0x18004831c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048323  cmp     rcx, r13
0x180048326  jz      short loc_18004834B
0x180048328  test    [rcx+1Ch], sil
0x18004832c  jz      short loc_18004834B
0x18004832e  mov     edx, 0FFh
0x180048333  mov     r9d, ebx
0x180048336  lea     r14, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18004833d  mov     r8, r14
0x180048340  mov     rcx, [rcx+10h]
0x180048344  call    WPP_SF_d
0x180048349  jmp     short loc_180048352
0x18004834b  lea     r14, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x180048352  xor     edx, edx; lpDatabaseName
0x180048354  xor     ecx, ecx; lpMachineName
0x180048356  mov     r8d, 80000000h; dwDesiredAccess
0x18004835c  call    cs:__imp_OpenSCManagerW
0x180048362  mov     r15, rax
0x180048365  mov     [rsp+238h+hSCObject], rax
0x18004836a  test    rax, rax
0x18004836d  jnz     short loc_1800483E8
0x18004836f  call    cs:__imp_GetLastError
0x180048375  mov     ebx, eax
0x180048377  mov     rcx, cs:WPP_GLOBAL_Control
0x18004837e  cmp     rcx, r13
0x180048381  jz      short loc_18004839D
0x180048383  test    byte ptr [rcx+1Ch], 4
0x180048387  jz      short loc_18004839D
0x180048389  mov     edx, 100h
0x18004838e  mov     r9d, eax
0x180048391  mov     r8, r14
0x180048394  mov     rcx, [rcx+10h]
0x180048398  call    WPP_SF_d
0x18004839d  test    ebx, ebx
0x18004839f  jle     short loc_1800483AA
0x1800483a1  movzx   ebx, bx
0x1800483a4  or      ebx, 80070000h
0x1800483aa  xorps   xmm0, xmm0
0x1800483ad  movups  [rsp+238h+var_1C0], xmm0
0x1800483b2  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800483b9  mov     [rsp+238h+pExceptionObject], rax
0x1800483be  mov     [rsp+238h+var_1B0], ebx
0x1800483c5  mov     [rsp+238h+var_1AC], 177Ah
0x1800483d0  mov     [rsp+238h+var_1A8], esi
0x1800483d7  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800483de  lea     rcx, [rsp+238h+pExceptionObject]; pExceptionObject
0x1800483e3  call    _CxxThrowException_0
0x1800483e8  mov     r8d, 80000002h; dwDesiredAccess
0x1800483ee  lea     rdx, ServiceName; "BITS"
0x1800483f5  mov     rcx, rax; hSCManager
0x1800483f8  call    cs:__imp_OpenServiceW
0x1800483fe  mov     r12, rax
0x180048401  mov     [rsp+238h+var_1D8], rax
0x180048406  test    rax, rax
0x180048409  jnz     loc_180048491
0x18004840f  call    cs:__imp_GetLastError
0x180048415  mov     ebx, eax
0x180048417  mov     rcx, cs:WPP_GLOBAL_Control
0x18004841e  cmp     rcx, r13
0x180048421  jz      short loc_18004843D
0x180048423  test    byte ptr [rcx+1Ch], 4
0x180048427  jz      short loc_18004843D
0x180048429  mov     edx, 101h
0x18004842e  mov     r9d, eax
0x180048431  mov     r8, r14
0x180048434  mov     rcx, [rcx+10h]
0x180048438  call    WPP_SF_d
0x18004843d  test    ebx, ebx
0x18004843f  jle     short loc_18004844A
0x180048441  movzx   ebx, bx
0x180048444  or      ebx, 80070000h
0x18004844a  xorps   xmm0, xmm0
0x18004844d  movups  [rsp+238h+var_160], xmm0
0x180048455  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18004845c  mov     [rsp+238h+var_168], rax
0x180048464  mov     [rsp+238h+var_150], ebx
0x18004846b  mov     [rsp+238h+var_14C], 1782h
0x180048476  mov     [rsp+238h+var_148], esi
0x18004847d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180048484  lea     rcx, [rsp+238h+var_168]; pExceptionObject
0x18004848c  call    _CxxThrowException_0
0x180048491  mov     [rsp+238h+pcbBytesNeeded], 0
0x18004849c  xor     r13d, r13d
0x18004849f  cmp     ebx, 2
0x1800484a2  setnz   r13b
0x1800484a6  add     r13d, 2
0x1800484aa  mov     ecx, 2000h; dwBytes
0x1800484af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800484b4  mov     rbx, rax
0x1800484b7  mov     [rsp+238h+arg_8], rax
0x1800484bf  lea     r9, [rsp+238h+pcbBytesNeeded]; pcbBytesNeeded
0x1800484c7  mov     r8d, 2000h; cbBufSize
0x1800484cd  mov     rdx, rax; lpServiceConfig
0x1800484d0  mov     rcx, r12; hService
0x1800484d3  call    cs:__imp_QueryServiceConfigW
0x1800484d9  test    eax, eax
0x1800484db  jnz     loc_180048601
0x1800484e1  call    cs:__imp_GetLastError
0x1800484e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484ee  lea     rdx, WPP_GLOBAL_Control
0x1800484f5  cmp     rcx, rdx
0x1800484f8  jz      short loc_180048514
0x1800484fa  test    byte ptr [rcx+1Ch], 4
0x1800484fe  jz      short loc_180048514
0x180048500  mov     edx, 102h
0x180048505  mov     r9d, eax
0x180048508  mov     r8, r14
0x18004850b  mov     rcx, [rcx+10h]
0x18004850f  call    WPP_SF_d
0x180048514  mov     [rsp+238h+lpDisplayName], 0; lpDisplayName
0x18004851d  mov     [rsp+238h+lpPassword], 0; lpPassword
0x180048526  mov     [rsp+238h+lpServiceStartName], 0; lpServiceStartName
0x18004852f  mov     [rsp+238h+lpDependencies], 0; lpDependencies
0x180048538  mov     [rsp+238h+lpdwTagId], 0; lpdwTagId
0x180048541  mov     [rsp+238h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18004854a  mov     [rsp+238h+lpBinaryPathName], 0; lpBinaryPathName
0x180048553  or      edx, 0FFFFFFFFh; dwServiceType
0x180048556  mov     r9d, edx; dwErrorControl
0x180048559  mov     r8d, r13d; dwStartType
0x18004855c  mov     rcx, r12; hService
0x18004855f  call    cs:__imp_ChangeServiceConfigW
0x180048565  test    eax, eax
0x180048567  jnz     loc_18004865D
0x18004856d  call    cs:__imp_GetLastError
0x180048573  mov     ebx, eax
0x180048575  mov     rcx, cs:WPP_GLOBAL_Control
0x18004857c  lea     rax, WPP_GLOBAL_Control
0x180048583  cmp     rcx, rax
0x180048586  jz      short loc_1800485AD
0x180048588  test    byte ptr [rcx+1Ch], 4
0x18004858c  jz      short loc_1800485AD
0x18004858e  mov     edx, 105h
0x180048593  mov     eax, [rsp+238h+arg_0]
0x18004859a  mov     dword ptr [rsp+238h+lpBinaryPathName], eax
0x18004859e  mov     r9d, ebx
0x1800485a1  mov     r8, r14
0x1800485a4  mov     rcx, [rcx+10h]
0x1800485a8  call    WPP_SF_Dd
0x1800485ad  test    ebx, ebx
0x1800485af  jle     short loc_1800485BA
0x1800485b1  movzx   ebx, bx
0x1800485b4  or      ebx, 80070000h
0x1800485ba  xorps   xmm0, xmm0
0x1800485bd  movups  [rsp+238h+var_100], xmm0
0x1800485c5  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800485cc  mov     [rsp+238h+var_108], rax
0x1800485d4  mov     [rsp+238h+var_F0], ebx
0x1800485db  mov     [rsp+238h+var_EC], 17AAh
0x1800485e6  mov     [rsp+238h+var_E8], esi
0x1800485ed  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800485f4  lea     rcx, [rsp+238h+var_108]; pExceptionObject
0x1800485fc  call    _CxxThrowException_0
0x180048601  cmp     dword ptr [rbx+4], 4
0x180048605  jnz     short loc_180048627
0x180048607  mov     rcx, cs:WPP_GLOBAL_Control
0x18004860e  lea     r13, WPP_GLOBAL_Control
0x180048615  cmp     rcx, r13
0x180048618  jz      short loc_180048664
0x18004861a  test    byte ptr [rcx+1Ch], 2
0x18004861e  jz      short loc_180048664
0x180048620  mov     edx, 103h
0x180048625  jmp     short loc_18004864F
0x180048627  cmp     [rbx+4], r13d
0x18004862b  jnz     loc_180048514
0x180048631  mov     rcx, cs:WPP_GLOBAL_Control
0x180048638  lea     r13, WPP_GLOBAL_Control
0x18004863f  cmp     rcx, r13
0x180048642  jz      short loc_180048664
0x180048644  test    [rcx+1Ch], sil
0x180048648  jz      short loc_180048664
0x18004864a  mov     edx, 104h
0x18004864f  mov     r8, r14
0x180048652  mov     rcx, [rcx+10h]
0x180048656  call    WPP_SF_
0x18004865b  jmp     short loc_180048664
0x18004865d  lea     r13, WPP_GLOBAL_Control
0x180048664  mov     [rsp+238h+Buffer], 0
0x18004866f  lea     rax, [rsp+238h+pcbBytesNeeded]
0x180048677  mov     [rsp+238h+lpBinaryPathName], rax; pcbBytesNeeded
0x18004867c  mov     r9d, 4; cbBufSize
0x180048682  lea     r8, [rsp+238h+Buffer]; lpBuffer
0x18004868a  lea     edx, [r9-1]; dwInfoLevel
0x18004868e  mov     rcx, r12; hService
0x180048691  call    cs:__imp_QueryServiceConfig2W
0x180048697  test    eax, eax
0x180048699  jnz     short loc_1800486C7
0x18004869b  call    cs:__imp_GetLastError
0x1800486a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800486a8  cmp     rcx, r13
0x1800486ab  jz      short loc_1800486CE
0x1800486ad  test    byte ptr [rcx+1Ch], 4
0x1800486b1  jz      short loc_1800486CE
0x1800486b3  mov     edx, 106h
0x1800486b8  mov     r9d, eax
0x1800486bb  mov     r8, r14
0x1800486be  mov     rcx, [rcx+10h]
0x1800486c2  call    WPP_SF_d
0x1800486c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800486ce  cmp     [rsp+238h+Buffer], 0
0x1800486d6  jz      short loc_18004870B
0x1800486d8  cmp     rcx, r13
0x1800486db  jz      short loc_1800486F5
0x1800486dd  test    [rcx+1Ch], sil
0x1800486e1  jz      short loc_1800486F5
0x1800486e3  mov     edx, 107h
0x1800486e8  mov     r8, r14
0x1800486eb  mov     rcx, [rcx+10h]
0x1800486ef  call    WPP_SF_
0x1800486f4  nop
0x1800486f5  test    rbx, rbx
0x1800486f8  jz      short loc_180048706
0x1800486fa  mov     rdx, rsi; unsigned __int64
0x1800486fd  mov     rcx, rbx; void *
0x180048700  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048705  nop
0x180048706  jmp     loc_1800487D1
0x18004870b  mov     [rsp+238h+Buffer], esi
0x180048712  lea     r8, [rsp+238h+Buffer]; lpInfo
0x18004871a  mov     edx, 3; dwInfoLevel
0x18004871f  mov     rcx, r12; hService
0x180048722  call    cs:__imp_ChangeServiceConfig2W
0x180048728  test    eax, eax
0x18004872a  jnz     short loc_1800486F5
0x18004872c  call    cs:__imp_GetLastError
0x180048732  mov     ebx, eax
0x180048734  mov     rcx, cs:WPP_GLOBAL_Control
0x18004873b  cmp     rcx, r13
0x18004873e  jz      short loc_180048765
0x180048740  test    byte ptr [rcx+1Ch], 4
0x180048744  jz      short loc_180048765
0x180048746  mov     edx, 108h
0x18004874b  mov     eax, [rsp+238h+arg_0]
0x180048752  mov     dword ptr [rsp+238h+lpBinaryPathName], eax
0x180048756  mov     r9d, ebx
0x180048759  mov     r8, r14
0x18004875c  mov     rcx, [rcx+10h]
0x180048760  call    WPP_SF_Dd
0x180048765  test    ebx, ebx
0x180048767  jle     short loc_180048772
0x180048769  movzx   ebx, bx
0x18004876c  or      ebx, 80070000h
0x180048772  xorps   xmm0, xmm0
0x180048775  movups  [rsp+238h+var_A0], xmm0
0x18004877d  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180048784  mov     [rsp+238h+var_A8], rax
0x18004878c  mov     [rsp+238h+var_90], ebx
0x180048793  mov     [rsp+238h+var_8C], 17CAh
0x18004879e  mov     [rsp+238h+var_88], esi
0x1800487a5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800487ac  lea     rcx, [rsp+238h+var_A8]; pExceptionObject
0x1800487b4  call    _CxxThrowException_0
0x1800487ba  mov     r12, [rsp+238h+var_1D8]
0x1800487bf  mov     sil, byte ptr [rsp+238h+arg_8]
0x1800487c7  mov     r15, [rsp+238h+hSCObject]
0x1800487cc  test    r12, r12
0x1800487cf  jz      short loc_1800487DA
0x1800487d1  mov     rcx, r12; hSCObject
0x1800487d4  call    cs:__imp_CloseServiceHandle
0x1800487da  test    r15, r15
0x1800487dd  jz      short loc_1800487E8
0x1800487df  mov     rcx, r15; hSCObject
0x1800487e2  call    cs:__imp_CloseServiceHandle
0x1800487e8  mov     al, sil
0x1800487eb  add     rsp, 208h
0x1800487f2  pop     r15
0x1800487f4  pop     r14
0x1800487f6  pop     r13
0x1800487f8  pop     r12
0x1800487fa  pop     rsi
0x1800487fb  pop     rbx
0x1800487fc  retn
```
