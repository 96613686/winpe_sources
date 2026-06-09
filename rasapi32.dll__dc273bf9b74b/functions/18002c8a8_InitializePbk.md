# InitializePbk

- ea: `0x18002c8a8`
- end: `0x18002cd84`
- name: `InitializePbk`
- size: `1244`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180042c88`

## callees

- `0x18000b0f4`
- `0x18002c8a8`
- `0x18002cd8c`
- `0x18002d300`
- `0x18004e580`
- `0x18004e984`
- `0x1800decd6`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002c952`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002cacb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002c952`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002cacb`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18002c98d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18002cb3d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18002c98d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18002cb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb4f`

## pseudocode

```c
__int64 InitializePbk()
{
  unsigned int v0; // ebx
  void *v1; // r15
  unsigned int v2; // eax
  DWORD LastError; // eax
  char *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  char *v7; // rcx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  char *v11; // rcx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // [rsp+0h] [rbp-58h] BYREF
  int v16; // [rsp+20h] [rbp-38h]
  unsigned int v17; // [rsp+24h] [rbp-34h]
  __int64 *v18; // [rsp+28h] [rbp-30h]
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+30h] [rbp-28h] BYREF
  void *v20; // [rsp+60h] [rbp+8h] BYREF
  struct _ACL *v21; // [rsp+68h] [rbp+10h] BYREF

  v18 = &v15;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  }
  v0 = 0;
  v1 = 0;
  v20 = 0;
  v21 = 0;
  if ( g_hmutexPb )
    goto LABEL_47;
  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  memset_0(&g_PbkPathInfo, 0, 0x60u);
  v2 = DwAllocateSecurityDescriptorAllowAccessToWorld(&v20, &v21);
  v0 = v2;
  v16 = v2;
  if ( v2 )
  {
    v7 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v2);
        v7 = (char *)WPP_GLOBAL_Control;
      }
      if ( v7 != (char *)&WPP_GLOBAL_Control && v7[28] < 0 && (unsigned __int8)v7[25] >= 6u )
        WPP_SF_d(*((_QWORD *)v7 + 2), 76, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v0);
    }
    v17 = v0;
    local_unwind_0(v18, &loc_18002CCCD);
    goto LABEL_23;
  }
  MutexAttributes.nLength = 24;
  v1 = v20;
  MutexAttributes.lpSecurityDescriptor = v20;
  MutexAttributes.bInheritHandle = 0;
  g_hmutexPb = CreateMutexW(&MutexAttributes, 0, L"Global\\RasPbFile");
  if ( g_hmutexPb )
    goto LABEL_47;
  LastError = GetLastError();
  v0 = LastError;
  v16 = LastError;
  if ( LastError == 5 )
  {
    v0 = 0;
    v16 = 0;
    g_hmutexPb = OpenMutexW(0x100000u, 0, L"Global\\RasPbFile");
    if ( g_hmutexPb )
      goto LABEL_47;
LABEL_23:
    v8 = GetLastError();
    v0 = v8;
    v16 = v8;
    v4 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v8);
      v4 = (char *)WPP_GLOBAL_Control;
    }
    if ( v0 == 5 || v0 == 2 )
    {
      v0 = 0;
      v16 = 0;
      g_hmutexPb = CreateMutexW(&MutexAttributes, 0, L"RasPbFile");
      if ( g_hmutexPb )
        goto LABEL_40;
      v9 = GetLastError();
      v0 = v9;
      v16 = v9;
      v4 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v9);
        v4 = (char *)WPP_GLOBAL_Control;
      }
      if ( v0 != 5 )
        goto LABEL_41;
      v0 = 0;
      v16 = 0;
      g_hmutexPb = OpenMutexW(0x100000u, 0, L"RasPbFile");
      if ( g_hmutexPb )
      {
LABEL_40:
        v4 = (char *)WPP_GLOBAL_Control;
        goto LABEL_41;
      }
      v10 = GetLastError();
      v0 = v10;
      v16 = v10;
      v4 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v10);
        goto LABEL_40;
      }
    }
LABEL_41:
    if ( !v0 && !g_hmutexPb )
    {
      v0 = 1003;
      v16 = 1003;
      if ( v4 != (char *)&WPP_GLOBAL_Control && v4[28] < 0 && (unsigned __int8)v4[25] >= 2u )
      {
        v5 = 80;
        v6 = 1003;
        goto LABEL_13;
      }
    }
    goto LABEL_47;
  }
  if ( LastError )
  {
    v4 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 81;
      v6 = LastError;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v6);
    }
  }
LABEL_47:
  Free0(v21);
  Free0(v1);
  if ( v0 )
  {
    v11 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
      return v0;
    }
    v14 = 84;
LABEL_60:
    WPP_SF_d(*((_QWORD *)v11 + 2), v14, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v0);
    return v0;
  }
  v13 = PbkPathInfoInit();
  v0 = v13;
  if ( v13 )
  {
    v11 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v0;
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v13);
      v11 = (char *)WPP_GLOBAL_Control;
    }
    if ( v11 == (char *)&WPP_GLOBAL_Control || v11[28] >= 0 || (unsigned __int8)v11[25] < 6u )
      return v0;
    v14 = 86;
    goto LABEL_60;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18002c8a8  mov     [rsp+arg_10], rbx
0x18002c8ad  mov     [rsp+arg_18], r14
0x18002c8b2  push    r15
0x18002c8b4  sub     rsp, 50h
0x18002c8b8  mov     [rsp+58h+var_30], rsp
0x18002c8bd  lea     r14, WPP_GLOBAL_Control
0x18002c8c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8cb  cmp     rcx, r14
0x18002c8ce  jnz     loc_18002CC9F
0x18002c8d4  xor     ebx, ebx
0x18002c8d6  xor     r15d, r15d
0x18002c8d9  mov     [rsp+58h+arg_0], r15
0x18002c8de  mov     [rsp+58h+arg_8], rbx
0x18002c8e3  cmp     cs:g_hmutexPb, r15
0x18002c8ea  jnz     loc_18002CBC7
0x18002c8f0  xorps   xmm0, xmm0
0x18002c8f3  xor     eax, eax
0x18002c8f5  movups  xmmword ptr [rsp+58h+MutexAttributes.nLength], xmm0
0x18002c8fa  mov     qword ptr [rsp+58h+MutexAttributes.bInheritHandle], rax
0x18002c8ff  xor     edx, edx; Val
0x18002c901  lea     r8d, [rbx+60h]; Size
0x18002c905  lea     rcx, g_PbkPathInfo; void *
0x18002c90c  call    memset_0
0x18002c911  lea     rdx, [rsp+58h+arg_8]
0x18002c916  lea     rcx, [rsp+58h+arg_0]
0x18002c91b  call    DwAllocateSecurityDescriptorAllowAccessToWorld
0x18002c920  mov     ebx, eax
0x18002c922  mov     [rsp+58h+var_38], eax
0x18002c926  test    eax, eax
0x18002c928  jnz     loc_18002C9F1
0x18002c92e  mov     [rsp+58h+MutexAttributes.nLength], 18h
0x18002c936  mov     r15, [rsp+58h+arg_0]
0x18002c93b  mov     [rsp+58h+MutexAttributes.lpSecurityDescriptor], r15
0x18002c940  mov     [rsp+58h+MutexAttributes.bInheritHandle], eax
0x18002c944  lea     r8, Name; "Global\\RasPbFile"
0x18002c94b  xor     edx, edx; bInitialOwner
0x18002c94d  lea     rcx, [rsp+58h+MutexAttributes]; lpMutexAttributes
0x18002c952  call    cs:__imp_CreateMutexW
0x18002c958  mov     cs:g_hmutexPb, rax
0x18002c95f  test    rax, rax
0x18002c962  jnz     loc_18002CBC7
0x18002c968  call    cs:__imp_GetLastError
0x18002c96e  mov     ebx, eax
0x18002c970  mov     [rsp+58h+var_38], eax
0x18002c974  cmp     eax, 5
0x18002c977  jnz     short loc_18002C9A8
0x18002c979  xor     ebx, ebx
0x18002c97b  mov     [rsp+58h+var_38], ebx
0x18002c97f  lea     r8, Name; "Global\\RasPbFile"
0x18002c986  xor     edx, edx; bInheritHandle
0x18002c988  mov     ecx, 100000h; dwDesiredAccess
0x18002c98d  call    cs:__imp_OpenMutexW
0x18002c993  mov     cs:g_hmutexPb, rax
0x18002c99a  test    rax, rax
0x18002c99d  jz      loc_18002CA66
0x18002c9a3  jmp     loc_18002CBC7
0x18002c9a8  test    eax, eax
0x18002c9aa  jz      loc_18002CBC7
0x18002c9b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c9b7  cmp     rcx, r14
0x18002c9ba  jz      loc_18002CBC7
0x18002c9c0  test    byte ptr [rcx+1Ch], 80h
0x18002c9c4  jz      loc_18002CBC7
0x18002c9ca  cmp     byte ptr [rcx+19h], 2
0x18002c9ce  jb      loc_18002CBC7
0x18002c9d4  mov     edx, 51h ; 'Q'
0x18002c9d9  mov     r9d, eax
0x18002c9dc  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002c9e3  mov     rcx, [rcx+10h]
0x18002c9e7  call    WPP_SF_d
0x18002c9ec  jmp     loc_18002CBC7
0x18002c9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c9f8  cmp     rcx, r14
0x18002c9fb  jz      short loc_18002CA51
0x18002c9fd  test    byte ptr [rcx+1Ch], 80h
0x18002ca01  jz      short loc_18002CA28
0x18002ca03  cmp     byte ptr [rcx+19h], 2
0x18002ca07  jb      short loc_18002CA28
0x18002ca09  mov     edx, 4Bh ; 'K'
0x18002ca0e  mov     r9d, ebx
0x18002ca11  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002ca18  mov     rcx, [rcx+10h]
0x18002ca1c  call    WPP_SF_d
0x18002ca21  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca28  cmp     rcx, r14
0x18002ca2b  jz      short loc_18002CA51
0x18002ca2d  test    byte ptr [rcx+1Ch], 80h
0x18002ca31  jz      short loc_18002CA51
0x18002ca33  cmp     byte ptr [rcx+19h], 6
0x18002ca37  jb      short loc_18002CA51
0x18002ca39  mov     edx, 4Ch ; 'L'
0x18002ca3e  mov     r9d, ebx
0x18002ca41  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002ca48  mov     rcx, [rcx+10h]
0x18002ca4c  call    WPP_SF_d
0x18002ca51  mov     [rsp+58h+var_34], ebx
0x18002ca55  lea     rdx, loc_18002CCCD
0x18002ca5c  mov     rcx, [rsp+58h+var_30]
0x18002ca61  call    _local_unwind_0
0x18002ca66  call    cs:__imp_GetLastError
0x18002ca6c  mov     ebx, eax
0x18002ca6e  mov     [rsp+58h+var_38], eax
0x18002ca72  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca79  cmp     rcx, r14
0x18002ca7c  jz      short loc_18002CAA9
0x18002ca7e  test    byte ptr [rcx+1Ch], 80h
0x18002ca82  jz      short loc_18002CAA9
0x18002ca84  cmp     byte ptr [rcx+19h], 2
0x18002ca88  jb      short loc_18002CAA9
0x18002ca8a  mov     edx, 4Dh ; 'M'
0x18002ca8f  mov     r9d, eax
0x18002ca92  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002ca99  mov     rcx, [rcx+10h]
0x18002ca9d  call    WPP_SF_d
0x18002caa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002caa9  cmp     ebx, 5
0x18002caac  jz      short loc_18002CAB7
0x18002caae  cmp     ebx, 2
0x18002cab1  jnz     loc_18002CB92
0x18002cab7  xor     ebx, ebx
0x18002cab9  mov     [rsp+58h+var_38], ebx
0x18002cabd  lea     r8, aRaspbfile; "RasPbFile"
0x18002cac4  xor     edx, edx; bInitialOwner
0x18002cac6  lea     rcx, [rsp+58h+MutexAttributes]; lpMutexAttributes
0x18002cacb  call    cs:__imp_CreateMutexW
0x18002cad1  mov     cs:g_hmutexPb, rax
0x18002cad8  test    rax, rax
0x18002cadb  jnz     loc_18002CB8B
0x18002cae1  call    cs:__imp_GetLastError
0x18002cae7  mov     ebx, eax
0x18002cae9  mov     [rsp+58h+var_38], eax
0x18002caed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002caf4  cmp     rcx, r14
0x18002caf7  jz      short loc_18002CB24
0x18002caf9  test    byte ptr [rcx+1Ch], 80h
0x18002cafd  jz      short loc_18002CB24
0x18002caff  cmp     byte ptr [rcx+19h], 2
0x18002cb03  jb      short loc_18002CB24
0x18002cb05  mov     edx, 4Eh ; 'N'
0x18002cb0a  mov     r9d, eax
0x18002cb0d  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002cb14  mov     rcx, [rcx+10h]
0x18002cb18  call    WPP_SF_d
0x18002cb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb24  cmp     ebx, 5
0x18002cb27  jnz     short loc_18002CB92
0x18002cb29  xor     ebx, ebx
0x18002cb2b  mov     [rsp+58h+var_38], ebx
0x18002cb2f  lea     r8, aRaspbfile; "RasPbFile"
0x18002cb36  xor     edx, edx; bInheritHandle
0x18002cb38  mov     ecx, 100000h; dwDesiredAccess
0x18002cb3d  call    cs:__imp_OpenMutexW
0x18002cb43  mov     cs:g_hmutexPb, rax
0x18002cb4a  test    rax, rax
0x18002cb4d  jnz     short loc_18002CB8B
0x18002cb4f  call    cs:__imp_GetLastError
0x18002cb55  mov     ebx, eax
0x18002cb57  mov     [rsp+58h+var_38], eax
0x18002cb5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb62  cmp     rcx, r14
0x18002cb65  jz      short loc_18002CB92
0x18002cb67  test    byte ptr [rcx+1Ch], 80h
0x18002cb6b  jz      short loc_18002CB92
0x18002cb6d  cmp     byte ptr [rcx+19h], 2
0x18002cb71  jb      short loc_18002CB92
0x18002cb73  mov     edx, 4Fh ; 'O'
0x18002cb78  mov     r9d, eax
0x18002cb7b  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002cb82  mov     rcx, [rcx+10h]
0x18002cb86  call    WPP_SF_d
0x18002cb8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb92  test    ebx, ebx
0x18002cb94  jnz     short loc_18002CBC7
0x18002cb96  cmp     cs:g_hmutexPb, 0
0x18002cb9e  jnz     short loc_18002CBC7
0x18002cba0  mov     ebx, 3EBh
0x18002cba5  mov     [rsp+58h+var_38], ebx
0x18002cba9  cmp     rcx, r14
0x18002cbac  jz      short loc_18002CBC7
0x18002cbae  test    byte ptr [rcx+1Ch], 80h
0x18002cbb2  jz      short loc_18002CBC7
0x18002cbb4  cmp     byte ptr [rcx+19h], 2
0x18002cbb8  jb      short loc_18002CBC7
0x18002cbba  mov     edx, 50h ; 'P'
0x18002cbbf  mov     r9d, ebx
0x18002cbc2  jmp     loc_18002C9DC
0x18002cbc7  jmp     short loc_18002CC45
0x18002cbc9  mov     ebx, eax
0x18002cbcb  mov     [rsp+58h+var_38], eax
0x18002cbcf  test    eax, eax
0x18002cbd1  jnz     short loc_18002CC02
0x18002cbd3  mov     ebx, 3EBh
0x18002cbd8  mov     [rsp+58h+var_38], ebx
0x18002cbdc  lea     rax, WPP_GLOBAL_Control
0x18002cbe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbea  cmp     rcx, rax
0x18002cbed  jz      short loc_18002CC39
0x18002cbef  test    byte ptr [rcx+1Ch], 80h
0x18002cbf3  jz      short loc_18002CC39
0x18002cbf5  cmp     byte ptr [rcx+19h], 2
0x18002cbf9  jb      short loc_18002CC39
0x18002cbfb  mov     edx, 52h ; 'R'
0x18002cc00  jmp     short loc_18002CC26
0x18002cc02  lea     rax, WPP_GLOBAL_Control
0x18002cc09  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc10  cmp     rcx, rax
0x18002cc13  jz      short loc_18002CC39
0x18002cc15  test    byte ptr [rcx+1Ch], 80h
0x18002cc19  jz      short loc_18002CC39
0x18002cc1b  cmp     byte ptr [rcx+19h], 2
0x18002cc1f  jb      short loc_18002CC39
0x18002cc21  mov     edx, 53h ; 'S'
0x18002cc26  mov     r9d, ebx
0x18002cc29  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002cc30  mov     rcx, [rcx+10h]
0x18002cc34  call    WPP_SF_d
0x18002cc39  lea     r14, WPP_GLOBAL_Control
0x18002cc40  mov     r15, [rsp+58h+arg_0]
0x18002cc45  mov     rcx, [rsp+58h+arg_8]
0x18002cc4a  call    Free0
0x18002cc4f  mov     rcx, r15
0x18002cc52  call    Free0
0x18002cc57  test    ebx, ebx
0x18002cc59  jz      short loc_18002CC7A
0x18002cc5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc62  cmp     rcx, r14
0x18002cc65  jnz     short loc_18002CCD3
0x18002cc67  mov     eax, ebx
0x18002cc69  mov     rbx, [rsp+58h+arg_10]
0x18002cc6e  mov     r14, [rsp+58h+arg_18]
0x18002cc73  add     rsp, 50h
0x18002cc77  pop     r15
0x18002cc79  retn
0x18002cc7a  call    PbkPathInfoInit
0x18002cc7f  mov     ebx, eax
0x18002cc81  test    eax, eax
0x18002cc83  jnz     short loc_18002CD03
0x18002cc85  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc8c  cmp     rcx, r14
0x18002cc8f  jz      short loc_18002CC9B
0x18002cc91  test    byte ptr [rcx+1Ch], 80h
0x18002cc95  jnz     loc_18002CD5D
0x18002cc9b  xor     eax, eax
0x18002cc9d  jmp     short loc_18002CC69
0x18002cc9f  test    byte ptr [rcx+1Ch], 80h
0x18002cca3  jz      loc_18002C8D4
0x18002cca9  cmp     byte ptr [rcx+19h], 6
0x18002ccad  jb      loc_18002C8D4
0x18002ccb3  mov     edx, 4Ah ; 'J'
0x18002ccb8  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002ccbf  mov     rcx, [rcx+10h]
0x18002ccc3  call    WPP_SF_
0x18002ccc8  jmp     loc_18002C8D4
0x18002cccd  mov     eax, [rsp+58h+var_38]
0x18002ccd1  jmp     short loc_18002CC69
0x18002ccd3  test    byte ptr [rcx+1Ch], 80h
0x18002ccd7  jz      short loc_18002CC67
0x18002ccd9  cmp     byte ptr [rcx+19h], 6
0x18002ccdd  jb      short loc_18002CC67
0x18002ccdf  mov     edx, 54h ; 'T'
0x18002cce4  jmp     short loc_18002CCEB
0x18002cce6  mov     edx, 56h ; 'V'
0x18002cceb  mov     r9d, ebx
0x18002ccee  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002ccf5  mov     rcx, [rcx+10h]
0x18002ccf9  call    WPP_SF_d
0x18002ccfe  jmp     loc_18002CC67
0x18002cd03  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd0a  cmp     rcx, r14
0x18002cd0d  jz      loc_18002CC67
0x18002cd13  test    byte ptr [rcx+1Ch], 80h
0x18002cd17  jz      short loc_18002CD3E
0x18002cd19  cmp     byte ptr [rcx+19h], 2
0x18002cd1d  jb      short loc_18002CD3E
0x18002cd1f  mov     edx, 55h ; 'U'
0x18002cd24  mov     r9d, ebx
0x18002cd27  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002cd2e  mov     rcx, [rcx+10h]
0x18002cd32  call    WPP_SF_d
0x18002cd37  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd3e  cmp     rcx, r14
0x18002cd41  jz      loc_18002CC67
0x18002cd47  test    byte ptr [rcx+1Ch], 80h
0x18002cd4b  jz      loc_18002CC67
0x18002cd51  cmp     byte ptr [rcx+19h], 6
0x18002cd55  jb      loc_18002CC67
0x18002cd5b  jmp     short loc_18002CCE6
0x18002cd5d  cmp     byte ptr [rcx+19h], 6
0x18002cd61  jb      loc_18002CC9B
0x18002cd67  mov     edx, 58h ; 'X'
0x18002cd6c  xor     r9d, r9d
0x18002cd6f  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002cd76  mov     rcx, [rcx+10h]
0x18002cd7a  call    WPP_SF_d
0x18002cd7f  jmp     loc_18002CC9B
0x1800dee63  push    rbp
0x1800dee65  sub     rsp, 20h
0x1800dee69  mov     rbp, rdx
0x1800dee6c  mov     rcx, [rbp+68h]
0x1800dee70  call    Free0
  ... truncated ...
```
