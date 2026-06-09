# RasSelectNextTriggerProfile

- ea: `0x1800c7c64`
- end: `0x1800c8020`
- name: `RasSelectNextTriggerProfile`
- size: `956`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18006aa88`
- `0x18007a750`
- `0x18007c380`

## callees

- `0x180007710`
- `0x1800079c0`
- `0x18000d9a0`
- `0x180010d10`
- `0x18004e580`
- `0x18004e984`
- `0x18007e5f0`
- `0x1800c7c64`
- `0x1800ded06`
- `0x1800ded50`
- `0x1800e0010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x1800c7d1c`
- `rtutils!TracePrintfExA` at `0x1800c7d52`
- `rtutils!TracePrintfExA` at `0x1800c7dc0`
- `rtutils!TracePrintfExA` at `0x1800c7e7b`
- `rtutils!TracePrintfExA` at `0x1800c7ecb`
- `rtutils!TracePrintfExA` at `0x1800c7f66`
- `rtutils!TracePrintfExA` at `0x1800c7d1c`
- `rtutils!TracePrintfExA` at `0x1800c7d52`
- `rtutils!TracePrintfExA` at `0x1800c7dc0`
- `rtutils!TracePrintfExA` at `0x1800c7e7b`
- `rtutils!TracePrintfExA` at `0x1800c7ecb`
- `rtutils!TracePrintfExA` at `0x1800c7f66`

## string_xrefs

- `0x1800c7d49`: `RasSelectNextTriggerProfile: RasGetPbkPathInternal failed %X.`
- `0x1800c7e6f`: `RasSelectNextTriggerProfile: g_pRasUpdateAutoTriggerRegKeys failed %X.`
- `0x1800c7db7`: `RasSelectNextTriggerProfile: ReadPhonebookFile failed %X.`

## pseudocode

```c
__int64 RasSelectNextTriggerProfile()
{
  unsigned int PbkPathInternal; // eax
  unsigned int v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  unsigned int PhonebookFile; // eax
  __int64 v5; // rdi
  __int64 v6; // rsi
  unsigned int v7; // eax
  int v8; // eax
  unsigned int v9; // ebx
  __int128 v11; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v12; // [rsp+50h] [rbp-B0h]
  __int128 v13; // [rsp+60h] [rbp-A0h]
  __int64 v14; // [rsp+70h] [rbp-90h]
  wchar_t v15; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[526]; // [rsp+82h] [rbp-7Eh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids);
  }
  v15 = 0;
  memset_0(v16, 0, 0x208u);
  v11 = 0;
  v14 = 0;
  v12 = 0;
  v13 = 0;
  DebugInit();
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasSelectNextTriggerProfile");
  PbkPathInternal = RasGetPbkPathInternal(1, 0, &v15, 261);
  v1 = PbkPathInternal;
  if ( PbkPathInternal )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "RasSelectNextTriggerProfile: RasGetPbkPathInternal failed %X.",
        PbkPathInternal);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = 129;
LABEL_52:
      WPP_SF_d(v2[2], v3, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v1);
      goto LABEL_53;
    }
    goto LABEL_53;
  }
  PhonebookFile = ReadPhonebookFile((unsigned int)&v15, 0, 0, 1032, (__int64)&v11);
  v1 = PhonebookFile;
  if ( !PhonebookFile )
  {
    v5 = 0;
    if ( (_QWORD)v12 )
      v5 = *(_QWORD *)v12;
    while ( v5 )
    {
      v6 = *(_QWORD *)(v5 + 16);
      if ( *(_DWORD *)(v6 + 704) )
      {
        v7 = ((__int64 (__fastcall *)(wchar_t *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))g_pRasUpdateAutoTriggerRegKeys)(
               &v15,
               *(_QWORD *)(v6 + 8),
               *(_QWORD *)(v6 + 464),
               0,
               0,
               0,
               0);
        v1 = v7;
        if ( !v7 )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "RasSelectNextTriggerProfile: Active Trigger profile is %S.",
              *(const wchar_t **)(v6 + 8));
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              131,
              &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids,
              *(_QWORD *)(v6 + 8));
          }
          goto LABEL_53;
        }
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "RasSelectNextTriggerProfile: g_pRasUpdateAutoTriggerRegKeys failed %X.",
            v7);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v1);
        }
        v5 = *(_QWORD *)(v5 + 8);
      }
      else
      {
        v5 = *(_QWORD *)(v5 + 8);
      }
    }
    v8 = ((__int64 (__fastcall *)(const size_t *, const size_t *, _QWORD, __int64, _DWORD, _QWORD, _DWORD))g_pRasUpdateAutoTriggerRegKeys)(
           &Data,
           &Data,
           0,
           1,
           0,
           0,
           0);
    v9 = v8;
    if ( v8 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "RasSelectNextTriggerProfile: Could not cleanup auto-trigger regkeys 0x%.8x",
          v8);
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_48:
        v1 = 259;
        if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x1000) != 0 && *((_BYTE *)v2 + 25) >= 2u )
        {
          v3 = 134;
          goto LABEL_52;
        }
        goto LABEL_53;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v9);
    }
    v2 = WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasSelectNextTriggerProfile: ReadPhonebookFile failed %X.", PhonebookFile);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = 130;
    goto LABEL_52;
  }
LABEL_53:
  ClosePhonebookFile((__int64)&v11);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v1);
  }
  return v1;
}

```

## disassembly

```asm
0x1800c7c64  push    rbp
0x1800c7c66  push    rbx
0x1800c7c67  push    rsi
0x1800c7c68  push    rdi
0x1800c7c69  push    r12
0x1800c7c6b  push    r13
0x1800c7c6d  push    r15
0x1800c7c6f  lea     rbp, [rsp-1A0h]
0x1800c7c77  sub     rsp, 2A0h
0x1800c7c7e  mov     rax, cs:__security_cookie
0x1800c7c85  xor     rax, rsp
0x1800c7c88  mov     [rbp+1D0h+var_40], rax
0x1800c7c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7c96  lea     r12, WPP_GLOBAL_Control
0x1800c7c9d  lea     r13, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c7ca4  mov     r15d, 1000h
0x1800c7caa  cmp     rcx, r12
0x1800c7cad  jz      short loc_1800C7CCC
0x1800c7caf  test    [rcx+1Ch], r15d
0x1800c7cb3  jz      short loc_1800C7CCC
0x1800c7cb5  cmp     byte ptr [rcx+19h], 6
0x1800c7cb9  jb      short loc_1800C7CCC
0x1800c7cbb  mov     rcx, [rcx+10h]
0x1800c7cbf  mov     edx, 80h
0x1800c7cc4  mov     r8, r13
0x1800c7cc7  call    WPP_SF_
0x1800c7ccc  xor     eax, eax
0x1800c7cce  lea     rcx, [rbp+1D0h+var_24E]; void *
0x1800c7cd2  xor     edx, edx; Val
0x1800c7cd4  mov     [rbp+1D0h+var_250], ax
0x1800c7cd8  mov     r8d, 208h; Size
0x1800c7cde  call    memset_0
0x1800c7ce3  xorps   xmm0, xmm0
0x1800c7ce6  xor     eax, eax
0x1800c7ce8  movups  [rsp+2D0h+var_290], xmm0
0x1800c7ced  mov     [rsp+2D0h+var_260], rax
0x1800c7cf2  movups  [rsp+2D0h+var_280], xmm0
0x1800c7cf7  movups  [rsp+2D0h+var_270], xmm0
0x1800c7cfc  call    DebugInit
0x1800c7d01  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7d07  or      esi, 0FFFFFFFFh
0x1800c7d0a  mov     edi, 0Ch
0x1800c7d0f  cmp     ecx, esi
0x1800c7d11  jz      short loc_1800C7D22
0x1800c7d13  lea     r8, aRasselectnextt_3; "RasSelectNextTriggerProfile"
0x1800c7d1a  mov     edx, edi; dwFlags
0x1800c7d1c  call    cs:__imp_TracePrintfExA
0x1800c7d22  xor     edx, edx
0x1800c7d24  lea     r8, [rbp+1D0h+var_250]
0x1800c7d28  mov     r9d, 105h
0x1800c7d2e  lea     ecx, [rdx+1]
0x1800c7d31  call    RasGetPbkPathInternal
0x1800c7d36  mov     ebx, eax
0x1800c7d38  test    eax, eax
0x1800c7d3a  jz      short loc_1800C7D86
0x1800c7d3c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7d42  cmp     ecx, esi
0x1800c7d44  jz      short loc_1800C7D58
0x1800c7d46  mov     r9d, eax
0x1800c7d49  lea     r8, aRasselectnextt_2; "RasSelectNextTriggerProfile: RasGetPbkP"...
0x1800c7d50  mov     edx, edi; dwFlags
0x1800c7d52  call    cs:__imp_TracePrintfExA
0x1800c7d58  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7d5f  cmp     rcx, r12
0x1800c7d62  jz      loc_1800C7FC7
0x1800c7d68  test    [rcx+1Ch], r15d
0x1800c7d6c  jz      loc_1800C7FC7
0x1800c7d72  cmp     byte ptr [rcx+19h], 2
0x1800c7d76  jb      loc_1800C7FC7
0x1800c7d7c  mov     edx, 81h
0x1800c7d81  jmp     loc_1800C7FB8
0x1800c7d86  lea     rax, [rsp+2D0h+var_290]
0x1800c7d8b  mov     r9d, 408h
0x1800c7d91  xor     r8d, r8d
0x1800c7d94  mov     [rsp+2D0h+var_2B0], rax
0x1800c7d99  xor     edx, edx
0x1800c7d9b  lea     rcx, [rbp+1D0h+var_250]
0x1800c7d9f  call    ReadPhonebookFile
0x1800c7da4  mov     ebx, eax
0x1800c7da6  test    eax, eax
0x1800c7da8  jz      short loc_1800C7DF4
0x1800c7daa  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7db0  cmp     ecx, esi
0x1800c7db2  jz      short loc_1800C7DC6
0x1800c7db4  mov     r9d, eax
0x1800c7db7  lea     r8, aRasselectnextt_4; "RasSelectNextTriggerProfile: ReadPhoneb"...
0x1800c7dbe  mov     edx, edi; dwFlags
0x1800c7dc0  call    cs:__imp_TracePrintfExA
0x1800c7dc6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7dcd  cmp     rcx, r12
0x1800c7dd0  jz      loc_1800C7FC7
0x1800c7dd6  test    [rcx+1Ch], r15d
0x1800c7dda  jz      loc_1800C7FC7
0x1800c7de0  cmp     byte ptr [rcx+19h], 2
0x1800c7de4  jb      loc_1800C7FC7
0x1800c7dea  mov     edx, 82h
0x1800c7def  jmp     loc_1800C7FB8
0x1800c7df4  mov     rax, qword ptr [rsp+2D0h+var_280]
0x1800c7df9  xor     edi, edi
0x1800c7dfb  test    rax, rax
0x1800c7dfe  jz      short loc_1800C7E03
0x1800c7e00  mov     rdi, [rax]
0x1800c7e03  test    rdi, rdi
0x1800c7e06  jz      loc_1800C7F0F
0x1800c7e0c  mov     rsi, [rdi+10h]
0x1800c7e10  cmp     dword ptr [rsi+2C0h], 0
0x1800c7e17  jnz     short loc_1800C7E22
0x1800c7e19  mov     rdi, [rdi+8]
0x1800c7e1d  or      esi, 0FFFFFFFFh
0x1800c7e20  jmp     short loc_1800C7E03
0x1800c7e22  mov     r8, [rsi+1D0h]
0x1800c7e29  lea     rcx, [rbp+1D0h+var_250]
0x1800c7e2d  mov     rdx, [rsi+8]
0x1800c7e31  xor     r9d, r9d
0x1800c7e34  mov     rax, cs:g_pRasUpdateAutoTriggerRegKeys
0x1800c7e3b  mov     [rsp+2D0h+var_2A0], 0
0x1800c7e43  mov     [rsp+2D0h+var_2A8], 0
0x1800c7e4c  mov     dword ptr [rsp+2D0h+var_2B0], 0
0x1800c7e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7e59  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7e5f  mov     ebx, eax
0x1800c7e61  test    eax, eax
0x1800c7e63  jz      short loc_1800C7EB6
0x1800c7e65  or      esi, 0FFFFFFFFh
0x1800c7e68  cmp     ecx, esi
0x1800c7e6a  jz      short loc_1800C7E81
0x1800c7e6c  mov     r9d, eax
0x1800c7e6f  lea     r8, aRasselectnextt; "RasSelectNextTriggerProfile: g_pRasUpda"...
0x1800c7e76  mov     edx, 0Ch; dwFlags
0x1800c7e7b  call    cs:__imp_TracePrintfExA
0x1800c7e81  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7e88  cmp     rcx, r12
0x1800c7e8b  jz      short loc_1800C7EAD
0x1800c7e8d  test    [rcx+1Ch], r15d
0x1800c7e91  jz      short loc_1800C7EAD
0x1800c7e93  cmp     byte ptr [rcx+19h], 2
0x1800c7e97  jb      short loc_1800C7EAD
0x1800c7e99  mov     rcx, [rcx+10h]
0x1800c7e9d  mov     edx, 84h
0x1800c7ea2  mov     r9d, ebx
0x1800c7ea5  mov     r8, r13
0x1800c7ea8  call    WPP_SF_d
0x1800c7ead  mov     rdi, [rdi+8]
0x1800c7eb1  jmp     loc_1800C7E03
0x1800c7eb6  cmp     ecx, 0FFFFFFFFh
0x1800c7eb9  jz      short loc_1800C7ED1
0x1800c7ebb  mov     r9, [rsi+8]
0x1800c7ebf  lea     r8, aRasselectnextt_1; "RasSelectNextTriggerProfile: Active Tri"...
0x1800c7ec6  mov     edx, 0Ch; dwFlags
0x1800c7ecb  call    cs:__imp_TracePrintfExA
0x1800c7ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7ed8  cmp     rcx, r12
0x1800c7edb  jz      loc_1800C7FC7
0x1800c7ee1  test    [rcx+1Ch], r15d
0x1800c7ee5  jz      loc_1800C7FC7
0x1800c7eeb  cmp     byte ptr [rcx+19h], 5
0x1800c7eef  jb      loc_1800C7FC7
0x1800c7ef5  mov     r9, [rsi+8]
0x1800c7ef9  mov     edx, 83h
0x1800c7efe  mov     rcx, [rcx+10h]
0x1800c7f02  mov     r8, r13
0x1800c7f05  call    WPP_SF_S
0x1800c7f0a  jmp     loc_1800C7FC7
0x1800c7f0f  mov     rax, cs:g_pRasUpdateAutoTriggerRegKeys
0x1800c7f16  lea     rcx, Data
0x1800c7f1d  mov     [rsp+2D0h+var_2A0], 0
0x1800c7f25  mov     rdx, rcx
0x1800c7f28  mov     [rsp+2D0h+var_2A8], 0
0x1800c7f31  mov     r9d, 1
0x1800c7f37  xor     r8d, r8d
0x1800c7f3a  mov     dword ptr [rsp+2D0h+var_2B0], 0
0x1800c7f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7f47  mov     ebx, eax
0x1800c7f49  test    eax, eax
0x1800c7f4b  jz      short loc_1800C7F98
0x1800c7f4d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7f53  cmp     ecx, esi
0x1800c7f55  jz      short loc_1800C7F6C
0x1800c7f57  mov     r9d, eax
0x1800c7f5a  lea     r8, aRasselectnextt_0; "RasSelectNextTriggerProfile: Could not "...
0x1800c7f61  mov     edx, 0Ch; dwFlags
0x1800c7f66  call    cs:__imp_TracePrintfExA
0x1800c7f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7f73  cmp     rcx, r12
0x1800c7f76  jz      short loc_1800C7F9F
0x1800c7f78  test    [rcx+1Ch], r15d
0x1800c7f7c  jz      short loc_1800C7F9F
0x1800c7f7e  cmp     byte ptr [rcx+19h], 2
0x1800c7f82  jb      short loc_1800C7F9F
0x1800c7f84  mov     rcx, [rcx+10h]
0x1800c7f88  mov     edx, 85h
0x1800c7f8d  mov     r9d, ebx
0x1800c7f90  mov     r8, r13
0x1800c7f93  call    WPP_SF_d
0x1800c7f98  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7f9f  mov     ebx, 103h
0x1800c7fa4  cmp     rcx, r12
0x1800c7fa7  jz      short loc_1800C7FC7
0x1800c7fa9  test    [rcx+1Ch], r15d
0x1800c7fad  jz      short loc_1800C7FC7
0x1800c7faf  cmp     byte ptr [rcx+19h], 2
0x1800c7fb3  jb      short loc_1800C7FC7
0x1800c7fb5  lea     edx, [rbx-7Dh]
0x1800c7fb8  mov     rcx, [rcx+10h]
0x1800c7fbc  mov     r9d, ebx
0x1800c7fbf  mov     r8, r13
0x1800c7fc2  call    WPP_SF_d
0x1800c7fc7  lea     rcx, [rsp+2D0h+var_290]
0x1800c7fcc  call    ClosePhonebookFile
0x1800c7fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7fd8  cmp     rcx, r12
0x1800c7fdb  jz      short loc_1800C7FFD
0x1800c7fdd  test    [rcx+1Ch], r15d
0x1800c7fe1  jz      short loc_1800C7FFD
0x1800c7fe3  cmp     byte ptr [rcx+19h], 6
0x1800c7fe7  jb      short loc_1800C7FFD
0x1800c7fe9  mov     rcx, [rcx+10h]
0x1800c7fed  mov     edx, 87h
0x1800c7ff2  mov     r9d, ebx
0x1800c7ff5  mov     r8, r13
0x1800c7ff8  call    WPP_SF_d
0x1800c7ffd  mov     eax, ebx
0x1800c7fff  mov     rcx, [rbp+1D0h+var_40]
0x1800c8006  xor     rcx, rsp; StackCookie
0x1800c8009  call    __security_check_cookie
0x1800c800e  add     rsp, 2A0h
0x1800c8015  pop     r15
0x1800c8017  pop     r13
0x1800c8019  pop     r12
0x1800c801b  pop     rdi
0x1800c801c  pop     rsi
0x1800c801d  pop     rbx
0x1800c801e  pop     rbp
0x1800c801f  retn
```
