# EapMSCHAPv2Initialize

- ea: `0x1800042f0`
- end: `0x1800045b8`
- name: `EapMSCHAPv2Initialize`
- size: `712`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002ec8`
- `0x180003bd0`
- `0x180003c10`
- `0x180003fa0`
- `0x1800042f0`
- `0x1800045c0`
- `0x180004690`
- `0x180006a20`
- `0x18000e240`
- `0x1800125ec`
- `0x1800147cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044e2`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800043ff`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18000459f`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800043ff`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18000459f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x1800044d8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x1800044d8`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigIgnoreIASLogon` at `0x18000434b`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigIgnoreIASLogon` at `0x1800043e9`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigIgnoreIASLogon` at `0x18000434b`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigIgnoreIASLogon` at `0x1800043e9`

## pseudocode

```c
__int64 __fastcall EapMSCHAPv2Initialize(unsigned int a1, __int64 a2, __int64 a3)
{
  DWORD v4; // edi
  DWORD v5; // eax
  DWORD v6; // ebx
  int v7; // eax
  DWORD inited; // eax
  DWORD v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  DWORD nSize; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      214,
      &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids,
      a1,
      dword_1800336C0);
  if ( a1 )
  {
    if ( dword_180033334 )
    {
      if ( (unsigned __int8)IsRasChapExt_GetConfigIgnoreIASLogonPresent() )
      {
        if ( !(unsigned int)RasChapExt_GetConfigIgnoreIASLogon() )
        {
          v5 = IASLogonInitialize();
          v6 = v5;
          if ( v5 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, v5);
            v4 = v6;
          }
          else
          {
            dword_180033334 = 0;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 216, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
      }
    }
    if ( !dword_1800336C0 )
      EapProvPlugin_Initialize();
    ++dword_1800336C0;
  }
  else if ( dword_1800336C0 )
  {
    if ( !--dword_1800336C0 )
    {
      if ( (unsigned __int8)IsRasChapExt_GetConfigIgnoreIASLogonPresent() )
      {
        if ( !(unsigned int)RasChapExt_GetConfigIgnoreIASLogon() && theLogonProcess )
        {
          LsaDeregisterLogonProcess(theLogonProcess);
          theLogonProcess = 0;
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
      }
      EapProvPlugin_Deinitialize();
      dword_180033334 = 1;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, a1);
  v7 = g_dwRefCount;
  if ( !a1 )
  {
    if ( g_dwRefCount )
    {
      --g_dwRefCount;
      if ( v7 == 1 )
      {
        DebuggingInit(0);
        if ( g_hLsa != (HANDLE)-1LL )
        {
          LsaDeregisterLogonProcess(g_hLsa);
          g_hLsa = (HANDLE)-1LL;
        }
      }
    }
    goto LABEL_40;
  }
  if ( g_dwRefCount )
  {
LABEL_39:
    g_dwRefCount = v7 + 1;
LABEL_40:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, a3, a1);
    v9 = 0;
    goto LABEL_43;
  }
  DebuggingInit(1);
  if ( g_hLsa == (HANDLE)-1LL )
  {
    inited = InitLSA();
    v9 = inited;
    if ( inited )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_43;
      v11 = 11;
      goto LABEL_34;
    }
  }
  nSize = 16;
  if ( GetComputerNameA(szComputerName, &nSize) )
  {
    v7 = g_dwRefCount;
    goto LABEL_39;
  }
  inited = GetLastError();
  v9 = inited;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v11 = 12;
LABEL_34:
    WPP_SF_d(v10[2], v11, &WPP_d3ccaec7459834abcb1c6432c7781bd4_Traceguids, inited);
  }
LABEL_43:
  if ( v9 )
    v4 = v9;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      218,
      &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids,
      a1,
      dword_1800336C0);
  return v4;
}

```

## disassembly

```asm
0x1800042f0  push    rbx
0x1800042f2  push    rbp
0x1800042f3  push    rsi
0x1800042f4  push    rdi
0x1800042f5  sub     rsp, 38h
0x1800042f9  mov     esi, ecx
0x1800042fb  xor     edi, edi
0x1800042fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004304  lea     rbp, WPP_GLOBAL_Control
0x18000430b  cmp     rcx, rbp
0x18000430e  jz      short loc_180004332
0x180004310  mov     eax, cs:dword_1800336C0
0x180004316  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x18000431d  mov     rcx, [rcx+10h]
0x180004321  mov     edx, 0D6h
0x180004326  mov     r9d, esi
0x180004329  mov     [rsp+58h+var_38], eax
0x18000432d  call    WPP_SF_dd
0x180004332  test    esi, esi
0x180004334  jz      loc_1800043C7
0x18000433a  cmp     cs:dword_180033334, edi
0x180004340  jz      short loc_1800043B1
0x180004342  call    IsRasChapExt_GetConfigIgnoreIASLogonPresent
0x180004347  test    al, al
0x180004349  jz      short loc_180004390
0x18000434b  call    cs:__imp_RasChapExt_GetConfigIgnoreIASLogon
0x180004351  test    eax, eax
0x180004353  jnz     short loc_1800043B1
0x180004355  call    IASLogonInitialize
0x18000435a  mov     ebx, eax
0x18000435c  test    eax, eax
0x18000435e  jz      short loc_180004388
0x180004360  mov     rcx, cs:WPP_GLOBAL_Control
0x180004367  cmp     rcx, rbp
0x18000436a  jz      short loc_180004384
0x18000436c  mov     rcx, [rcx+10h]
0x180004370  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x180004377  mov     edx, 0D7h
0x18000437c  mov     r9d, eax
0x18000437f  call    WPP_SF_d
0x180004384  mov     edi, ebx
0x180004386  jmp     short loc_1800043B1
0x180004388  mov     cs:dword_180033334, edi
0x18000438e  jmp     short loc_1800043B1
0x180004390  mov     rcx, cs:WPP_GLOBAL_Control
0x180004397  cmp     rcx, rbp
0x18000439a  jz      short loc_1800043B1
0x18000439c  mov     rcx, [rcx+10h]
0x1800043a0  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x1800043a7  mov     edx, 0D8h
0x1800043ac  call    WPP_SF_
0x1800043b1  cmp     cs:dword_1800336C0, 0
0x1800043b8  jnz     short loc_1800043BF
0x1800043ba  call    EapProvPlugin_Initialize
0x1800043bf  inc     cs:dword_1800336C0
0x1800043c5  jmp     short loc_18000443E
0x1800043c7  cmp     cs:dword_1800336C0, edi
0x1800043cd  jz      short loc_18000443E
0x1800043cf  mov     eax, cs:dword_1800336C0
0x1800043d5  add     eax, 0FFFFFFFFh
0x1800043d8  mov     cs:dword_1800336C0, eax
0x1800043de  jnz     short loc_18000443E
0x1800043e0  call    IsRasChapExt_GetConfigIgnoreIASLogonPresent
0x1800043e5  test    al, al
0x1800043e7  jz      short loc_18000440E
0x1800043e9  call    cs:__imp_RasChapExt_GetConfigIgnoreIASLogon
0x1800043ef  test    eax, eax
0x1800043f1  jnz     short loc_18000442F
0x1800043f3  mov     rcx, cs:theLogonProcess; LsaHandle
0x1800043fa  test    rcx, rcx
0x1800043fd  jz      short loc_18000442F
0x1800043ff  call    cs:__imp_LsaDeregisterLogonProcess
0x180004405  mov     cs:theLogonProcess, rdi
0x18000440c  jmp     short loc_18000442F
0x18000440e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004415  cmp     rcx, rbp
0x180004418  jz      short loc_18000442F
0x18000441a  mov     rcx, [rcx+10h]
0x18000441e  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x180004425  mov     edx, 0D9h
0x18000442a  call    WPP_SF_
0x18000442f  call    EapProvPlugin_Deinitialize
0x180004434  mov     cs:dword_180033334, 1
0x18000443e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004445  cmp     rcx, rbp
0x180004448  jz      short loc_180004465
0x18000444a  mov     eax, dword ptr cs:g_hLsa
0x180004450  mov     edx, 0Ah
0x180004455  mov     rcx, [rcx+10h]
0x180004459  mov     r9d, esi
0x18000445c  mov     [rsp+58h+var_30], eax
0x180004460  call    WPP_SF_DDD
0x180004465  mov     eax, cs:g_dwRefCount
0x18000446b  test    esi, esi
0x18000446d  jz      loc_180004575
0x180004473  test    eax, eax
0x180004475  jnz     loc_180004503
0x18000447b  mov     ecx, 1
0x180004480  call    DebuggingInit
0x180004485  cmp     cs:g_hLsa, 0FFFFFFFFFFFFFFFFh
0x18000448d  jnz     short loc_1800044C4
0x18000448f  call    InitLSA
0x180004494  mov     ebx, eax
0x180004496  test    eax, eax
0x180004498  jz      short loc_1800044C4
0x18000449a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044a1  cmp     rcx, rbp
0x1800044a4  jz      loc_180004535
0x1800044aa  mov     edx, 0Bh
0x1800044af  mov     rcx, [rcx+10h]
0x1800044b3  lea     r8, WPP_d3ccaec7459834abcb1c6432c7781bd4_Traceguids
0x1800044ba  mov     r9d, eax
0x1800044bd  call    WPP_SF_d
0x1800044c2  jmp     short loc_180004535
0x1800044c4  lea     rdx, [rsp+58h+nSize]; nSize
0x1800044c9  mov     [rsp+58h+nSize], 10h
0x1800044d1  lea     rcx, szComputerName; lpBuffer
0x1800044d8  call    cs:__imp_GetComputerNameA
0x1800044de  test    eax, eax
0x1800044e0  jnz     short loc_1800044FD
0x1800044e2  call    cs:__imp_GetLastError
0x1800044e8  mov     ebx, eax
0x1800044ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044f1  cmp     rcx, rbp
0x1800044f4  jz      short loc_180004535
0x1800044f6  mov     edx, 0Ch
0x1800044fb  jmp     short loc_1800044AF
0x1800044fd  mov     eax, cs:g_dwRefCount
0x180004503  inc     eax
0x180004505  mov     cs:g_dwRefCount, eax
0x18000450b  mov     rax, cs:g_hLsa
0x180004512  mov     rcx, cs:WPP_GLOBAL_Control
0x180004519  cmp     rcx, rbp
0x18000451c  jz      short loc_180004533
0x18000451e  mov     rcx, [rcx+10h]
0x180004522  mov     edx, 0Dh
0x180004527  mov     r9d, esi
0x18000452a  mov     [rsp+58h+var_30], eax
0x18000452e  call    WPP_SF_DDD
0x180004533  xor     ebx, ebx
0x180004535  mov     rcx, cs:WPP_GLOBAL_Control
0x18000453c  test    ebx, ebx
0x18000453e  cmovnz  edi, ebx
0x180004541  cmp     rcx, rbp
0x180004544  jz      short loc_18000456A
0x180004546  mov     r9d, cs:dword_1800336C0
0x18000454d  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x180004554  mov     rcx, [rcx+10h]
0x180004558  mov     edx, 0DAh
0x18000455d  mov     [rsp+58h+var_38], r9d
0x180004562  mov     r9d, esi
0x180004565  call    WPP_SF_dd
0x18000456a  mov     eax, edi
0x18000456c  add     rsp, 38h
0x180004570  pop     rdi
0x180004571  pop     rsi
0x180004572  pop     rbp
0x180004573  pop     rbx
0x180004574  retn
0x180004575  test    eax, eax
0x180004577  jz      short loc_18000450B
0x180004579  add     eax, 0FFFFFFFFh
0x18000457c  mov     cs:g_dwRefCount, eax
0x180004582  jnz     short loc_18000450B
0x180004584  xor     ecx, ecx
0x180004586  call    DebuggingInit
0x18000458b  mov     rax, cs:g_hLsa
0x180004592  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004596  jz      loc_180004512
0x18000459c  mov     rcx, rax; LsaHandle
0x18000459f  call    cs:__imp_LsaDeregisterLogonProcess
0x1800045a5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800045ac  mov     cs:g_hLsa, rax
0x1800045b3  jmp     loc_180004512
```
