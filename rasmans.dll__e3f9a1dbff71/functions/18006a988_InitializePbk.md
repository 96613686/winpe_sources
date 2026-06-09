# InitializePbk

- ea: `0x18006a988`
- end: `0x18006ae4e`
- name: `InitializePbk`
- size: `1222`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800074c8`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180068260`
- `0x18006a988`
- `0x180080314`
- `0x1800e71d6`
- `0x1800e7206`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aafa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ab39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006abb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ac22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aafa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ab39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006abb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ac22`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18006aae4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18006ab9e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18006aae4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18006ab9e`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18006ab23`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18006ac10`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18006ab23`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18006ac10`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006ad67`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006ad7c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e7bf7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e7c07`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006ad67`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006ad7c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e7bf7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e7c07`

## pseudocode

```c
__int64 InitializePbk()
{
  struct _LIST_ENTRY *v0; // rcx
  unsigned int v1; // ebx
  void *v2; // r15
  unsigned int v3; // eax
  struct _LIST_ENTRY *v4; // rcx
  DWORD LastError; // eax
  DWORD v7; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // [rsp+0h] [rbp-58h] BYREF
  unsigned int v15; // [rsp+20h] [rbp-38h]
  unsigned int v16; // [rsp+24h] [rbp-34h]
  __int64 *v17; // [rsp+28h] [rbp-30h]
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+30h] [rbp-28h] BYREF
  void *v19; // [rsp+60h] [rbp+8h] BYREF
  HGLOBAL hMem; // [rsp+68h] [rbp+10h] BYREF

  v17 = &v14;
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 74, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  v1 = 0;
  v2 = 0;
  v19 = 0;
  hMem = 0;
  if ( g_hmutexPb )
    goto LABEL_50;
  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  memset_0(&g_PbkPathInfo, 0, 0x60u);
  v3 = DwAllocateSecurityDescriptorAllowAccessToWorld(&v19, &hMem);
  v1 = v3;
  v15 = v3;
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 75, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v3);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        WPP_SF_d(v4[1].Flink, 76, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v1);
    }
    v16 = v1;
    local_unwind_0(v17, &loc_18006AAA7);
    return v15;
  }
  MutexAttributes.nLength = 24;
  v2 = v19;
  MutexAttributes.lpSecurityDescriptor = v19;
  MutexAttributes.bInheritHandle = 0;
  g_hmutexPb = CreateMutexW(&MutexAttributes, 0, L"Global\\RasPbFile");
  if ( g_hmutexPb )
    goto LABEL_49;
  LastError = GetLastError();
  v1 = LastError;
  v15 = LastError;
  if ( LastError == 5 )
  {
    v1 = 0;
    v15 = 0;
    g_hmutexPb = OpenMutexW(0x100000u, 0, L"Global\\RasPbFile");
    if ( !g_hmutexPb )
    {
      v7 = GetLastError();
      v1 = v7;
      v15 = v7;
      v0 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 77, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v7);
        v0 = WPP_GLOBAL_Control;
      }
      if ( v1 == 5 || v1 == 2 )
      {
        v1 = 0;
        v15 = 0;
        g_hmutexPb = CreateMutexW(&MutexAttributes, 0, L"RasPbFile");
        if ( g_hmutexPb )
          goto LABEL_36;
        v8 = GetLastError();
        v1 = v8;
        v15 = v8;
        v0 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 78, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v8);
          v0 = WPP_GLOBAL_Control;
        }
        if ( v1 != 5 )
          goto LABEL_37;
        v1 = 0;
        v15 = 0;
        g_hmutexPb = OpenMutexW(0x100000u, 0, L"RasPbFile");
        if ( g_hmutexPb )
        {
LABEL_36:
          v0 = WPP_GLOBAL_Control;
          goto LABEL_37;
        }
        v9 = GetLastError();
        v1 = v9;
        v15 = v9;
        v0 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 79, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v9);
          goto LABEL_36;
        }
      }
LABEL_37:
      if ( !v1 && !g_hmutexPb )
      {
        v1 = 1003;
        v15 = 1003;
        if ( v0 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v0[1].Blink) < 0 && BYTE1(v0[1].Blink) >= 2u )
        {
          v10 = 80;
          v11 = 1003;
LABEL_48:
          WPP_SF_d(v0[1].Flink, v10, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v11);
          goto LABEL_49;
        }
      }
      goto LABEL_50;
    }
LABEL_49:
    v0 = WPP_GLOBAL_Control;
    goto LABEL_50;
  }
  if ( !LastError )
    goto LABEL_49;
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v10 = 81;
    v11 = LastError;
    goto LABEL_48;
  }
LABEL_50:
  if ( hMem )
  {
    GlobalFree(hMem);
    v0 = WPP_GLOBAL_Control;
  }
  if ( v2 )
  {
    GlobalFree(v2);
    v0 = WPP_GLOBAL_Control;
  }
  if ( v1 )
  {
    if ( v0 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || SBYTE4(v0[1].Blink) >= 0 || BYTE1(v0[1].Blink) < 6u )
      return v1;
    v12 = 84;
LABEL_59:
    WPP_SF_d(v0[1].Flink, v12, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v1);
    return v1;
  }
  v13 = PbkPathInfoInit();
  v1 = v13;
  if ( v13 )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return v1;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 85, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v13);
      v0 = WPP_GLOBAL_Control;
    }
    if ( v0 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || SBYTE4(v0[1].Blink) >= 0 || BYTE1(v0[1].Blink) < 6u )
      return v1;
    v12 = 86;
    goto LABEL_59;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 88, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18006a988  mov     [rsp+arg_10], rbx
0x18006a98d  mov     [rsp+arg_18], r14
0x18006a992  push    r15
0x18006a994  sub     rsp, 50h
0x18006a998  mov     [rsp+58h+var_30], rsp
0x18006a99d  lea     r14, WPP_GLOBAL_Control
0x18006a9a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a9ab  cmp     rcx, r14
0x18006a9ae  jz      short loc_18006A9D8
0x18006a9b0  test    byte ptr [rcx+1Ch], 80h
0x18006a9b4  jz      short loc_18006A9D8
0x18006a9b6  cmp     byte ptr [rcx+19h], 6
0x18006a9ba  jb      short loc_18006A9D8
0x18006a9bc  mov     edx, 4Ah ; 'J'
0x18006a9c1  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006a9c8  mov     rcx, [rcx+10h]
0x18006a9cc  call    WPP_SF_
0x18006a9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a9d8  xor     ebx, ebx
0x18006a9da  xor     r15d, r15d
0x18006a9dd  mov     [rsp+58h+arg_0], r15
0x18006a9e2  mov     [rsp+58h+hMem], rbx
0x18006a9e7  cmp     cs:g_hmutexPb, r15
0x18006a9ee  jnz     loc_18006ACD2
0x18006a9f4  xorps   xmm0, xmm0
0x18006a9f7  xor     eax, eax
0x18006a9f9  movups  xmmword ptr [rsp+58h+MutexAttributes.nLength], xmm0
0x18006a9fe  mov     qword ptr [rsp+58h+MutexAttributes.bInheritHandle], rax
0x18006aa03  xor     edx, edx; Val
0x18006aa05  lea     r8d, [rbx+60h]; Size
0x18006aa09  lea     rcx, g_PbkPathInfo; void *
0x18006aa10  call    memset_0
0x18006aa15  lea     rdx, [rsp+58h+hMem]
0x18006aa1a  lea     rcx, [rsp+58h+arg_0]
0x18006aa1f  call    DwAllocateSecurityDescriptorAllowAccessToWorld
0x18006aa24  mov     ebx, eax
0x18006aa26  mov     [rsp+58h+var_38], eax
0x18006aa2a  test    eax, eax
0x18006aa2c  jz      loc_18006AABC
0x18006aa32  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aa39  cmp     rcx, r14
0x18006aa3c  jz      short loc_18006AA91
0x18006aa3e  test    byte ptr [rcx+1Ch], 80h
0x18006aa42  jz      short loc_18006AA68
0x18006aa44  cmp     byte ptr [rcx+19h], 2
0x18006aa48  jb      short loc_18006AA68
0x18006aa4a  lea     edx, [r15+4Bh]
0x18006aa4e  mov     r9d, eax
0x18006aa51  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006aa58  mov     rcx, [rcx+10h]
0x18006aa5c  call    WPP_SF_d
0x18006aa61  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aa68  cmp     rcx, r14
0x18006aa6b  jz      short loc_18006AA91
0x18006aa6d  test    byte ptr [rcx+1Ch], 80h
0x18006aa71  jz      short loc_18006AA91
0x18006aa73  cmp     byte ptr [rcx+19h], 6
0x18006aa77  jb      short loc_18006AA91
0x18006aa79  mov     edx, 4Ch ; 'L'
0x18006aa7e  mov     r9d, ebx
0x18006aa81  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006aa88  mov     rcx, [rcx+10h]
0x18006aa8c  call    WPP_SF_d
0x18006aa91  mov     [rsp+58h+var_34], ebx
0x18006aa95  lea     rdx, loc_18006AAA7
0x18006aa9c  mov     rcx, [rsp+58h+var_30]
0x18006aaa1  call    _local_unwind_0
0x18006aaa6  nop
0x18006aaa7  mov     eax, [rsp+58h+var_38]
0x18006aaab  mov     rbx, [rsp+58h+arg_10]
0x18006aab0  mov     r14, [rsp+58h+arg_18]
0x18006aab5  add     rsp, 50h
0x18006aab9  pop     r15
0x18006aabb  retn
0x18006aabc  mov     [rsp+58h+MutexAttributes.nLength], 18h
0x18006aac4  mov     r15, [rsp+58h+arg_0]
0x18006aac9  mov     [rsp+58h+MutexAttributes.lpSecurityDescriptor], r15
0x18006aace  mov     [rsp+58h+MutexAttributes.bInheritHandle], 0
0x18006aad6  lea     r8, Name; "Global\\RasPbFile"
0x18006aadd  xor     edx, edx; bInitialOwner
0x18006aadf  lea     rcx, [rsp+58h+MutexAttributes]; lpMutexAttributes
0x18006aae4  call    cs:__imp_CreateMutexW
0x18006aaea  mov     cs:g_hmutexPb, rax
0x18006aaf1  test    rax, rax
0x18006aaf4  jnz     loc_18006ACCB
0x18006aafa  call    cs:__imp_GetLastError
0x18006ab00  mov     ebx, eax
0x18006ab02  mov     [rsp+58h+var_38], eax
0x18006ab06  cmp     eax, 5
0x18006ab09  jnz     loc_18006AC97
0x18006ab0f  xor     ebx, ebx
0x18006ab11  mov     [rsp+58h+var_38], ebx
0x18006ab15  lea     r8, Name; "Global\\RasPbFile"
0x18006ab1c  xor     edx, edx; bInheritHandle
0x18006ab1e  mov     ecx, 100000h; dwDesiredAccess
0x18006ab23  call    cs:__imp_OpenMutexW
0x18006ab29  mov     cs:g_hmutexPb, rax
0x18006ab30  test    rax, rax
0x18006ab33  jnz     loc_18006ACCB
0x18006ab39  call    cs:__imp_GetLastError
0x18006ab3f  mov     ebx, eax
0x18006ab41  mov     [rsp+58h+var_38], eax
0x18006ab45  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ab4c  cmp     rcx, r14
0x18006ab4f  jz      short loc_18006AB7C
0x18006ab51  test    byte ptr [rcx+1Ch], 80h
0x18006ab55  jz      short loc_18006AB7C
0x18006ab57  cmp     byte ptr [rcx+19h], 2
0x18006ab5b  jb      short loc_18006AB7C
0x18006ab5d  mov     edx, 4Dh ; 'M'
0x18006ab62  mov     r9d, eax
0x18006ab65  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006ab6c  mov     rcx, [rcx+10h]
0x18006ab70  call    WPP_SF_d
0x18006ab75  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ab7c  cmp     ebx, 5
0x18006ab7f  jz      short loc_18006AB8A
0x18006ab81  cmp     ebx, 2
0x18006ab84  jnz     loc_18006AC65
0x18006ab8a  xor     ebx, ebx
0x18006ab8c  mov     [rsp+58h+var_38], ebx
0x18006ab90  lea     r8, aRaspbfile; "RasPbFile"
0x18006ab97  xor     edx, edx; bInitialOwner
0x18006ab99  lea     rcx, [rsp+58h+MutexAttributes]; lpMutexAttributes
0x18006ab9e  call    cs:__imp_CreateMutexW
0x18006aba4  mov     cs:g_hmutexPb, rax
0x18006abab  test    rax, rax
0x18006abae  jnz     loc_18006AC5E
0x18006abb4  call    cs:__imp_GetLastError
0x18006abba  mov     ebx, eax
0x18006abbc  mov     [rsp+58h+var_38], eax
0x18006abc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006abc7  cmp     rcx, r14
0x18006abca  jz      short loc_18006ABF7
0x18006abcc  test    byte ptr [rcx+1Ch], 80h
0x18006abd0  jz      short loc_18006ABF7
0x18006abd2  cmp     byte ptr [rcx+19h], 2
0x18006abd6  jb      short loc_18006ABF7
0x18006abd8  mov     edx, 4Eh ; 'N'
0x18006abdd  mov     r9d, eax
0x18006abe0  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006abe7  mov     rcx, [rcx+10h]
0x18006abeb  call    WPP_SF_d
0x18006abf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006abf7  cmp     ebx, 5
0x18006abfa  jnz     short loc_18006AC65
0x18006abfc  xor     ebx, ebx
0x18006abfe  mov     [rsp+58h+var_38], ebx
0x18006ac02  lea     r8, aRaspbfile; "RasPbFile"
0x18006ac09  xor     edx, edx; bInheritHandle
0x18006ac0b  mov     ecx, 100000h; dwDesiredAccess
0x18006ac10  call    cs:__imp_OpenMutexW
0x18006ac16  mov     cs:g_hmutexPb, rax
0x18006ac1d  test    rax, rax
0x18006ac20  jnz     short loc_18006AC5E
0x18006ac22  call    cs:__imp_GetLastError
0x18006ac28  mov     ebx, eax
0x18006ac2a  mov     [rsp+58h+var_38], eax
0x18006ac2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ac35  cmp     rcx, r14
0x18006ac38  jz      short loc_18006AC65
0x18006ac3a  test    byte ptr [rcx+1Ch], 80h
0x18006ac3e  jz      short loc_18006AC65
0x18006ac40  cmp     byte ptr [rcx+19h], 2
0x18006ac44  jb      short loc_18006AC65
0x18006ac46  mov     edx, 4Fh ; 'O'
0x18006ac4b  mov     r9d, eax
0x18006ac4e  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006ac55  mov     rcx, [rcx+10h]
0x18006ac59  call    WPP_SF_d
0x18006ac5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ac65  test    ebx, ebx
0x18006ac67  jnz     short loc_18006ACD2
0x18006ac69  cmp     cs:g_hmutexPb, 0
0x18006ac71  jnz     short loc_18006ACD2
0x18006ac73  mov     ebx, 3EBh
0x18006ac78  mov     [rsp+58h+var_38], ebx
0x18006ac7c  cmp     rcx, r14
0x18006ac7f  jz      short loc_18006ACD2
0x18006ac81  test    byte ptr [rcx+1Ch], 80h
0x18006ac85  jz      short loc_18006ACD2
0x18006ac87  cmp     byte ptr [rcx+19h], 2
0x18006ac8b  jb      short loc_18006ACD2
0x18006ac8d  mov     edx, 50h ; 'P'
0x18006ac92  mov     r9d, ebx
0x18006ac95  jmp     short loc_18006ACBB
0x18006ac97  test    eax, eax
0x18006ac99  jz      short loc_18006ACCB
0x18006ac9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aca2  cmp     rcx, r14
0x18006aca5  jz      short loc_18006ACD2
0x18006aca7  test    byte ptr [rcx+1Ch], 80h
0x18006acab  jz      short loc_18006ACD2
0x18006acad  cmp     byte ptr [rcx+19h], 2
0x18006acb1  jb      short loc_18006ACD2
0x18006acb3  mov     edx, 51h ; 'Q'
0x18006acb8  mov     r9d, eax
0x18006acbb  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006acc2  mov     rcx, [rcx+10h]
0x18006acc6  call    WPP_SF_d
0x18006accb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006acd2  jmp     loc_18006AD5A
0x18006acd7  mov     ebx, eax
0x18006acd9  mov     [rsp+58h+var_38], eax
0x18006acdd  test    eax, eax
0x18006acdf  jnz     short loc_18006AD10
0x18006ace1  mov     ebx, 3EBh
0x18006ace6  mov     [rsp+58h+var_38], ebx
0x18006acea  lea     rax, WPP_GLOBAL_Control
0x18006acf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006acf8  cmp     rcx, rax
0x18006acfb  jz      short loc_18006AD4E
0x18006acfd  test    byte ptr [rcx+1Ch], 80h
0x18006ad01  jz      short loc_18006AD4E
0x18006ad03  cmp     byte ptr [rcx+19h], 2
0x18006ad07  jb      short loc_18006AD4E
0x18006ad09  mov     edx, 52h ; 'R'
0x18006ad0e  jmp     short loc_18006AD34
0x18006ad10  lea     rax, WPP_GLOBAL_Control
0x18006ad17  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ad1e  cmp     rcx, rax
0x18006ad21  jz      short loc_18006AD4E
0x18006ad23  test    byte ptr [rcx+1Ch], 80h
0x18006ad27  jz      short loc_18006AD4E
0x18006ad29  cmp     byte ptr [rcx+19h], 2
0x18006ad2d  jb      short loc_18006AD4E
0x18006ad2f  mov     edx, 53h ; 'S'
0x18006ad34  mov     r9d, ebx
0x18006ad37  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006ad3e  mov     rcx, [rcx+10h]
0x18006ad42  call    WPP_SF_d
0x18006ad47  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ad4e  lea     r14, WPP_GLOBAL_Control
0x18006ad55  mov     r15, [rsp+58h+arg_0]
0x18006ad5a  mov     rax, [rsp+58h+hMem]
0x18006ad5f  test    rax, rax
0x18006ad62  jz      short loc_18006AD74
0x18006ad64  mov     rcx, rax; hMem
0x18006ad67  call    cs:__imp_GlobalFree
0x18006ad6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ad74  test    r15, r15
0x18006ad77  jz      short loc_18006AD89
0x18006ad79  mov     rcx, r15; hMem
0x18006ad7c  call    cs:__imp_GlobalFree
0x18006ad82  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ad89  test    ebx, ebx
0x18006ad8b  jz      short loc_18006ADBD
0x18006ad8d  cmp     rcx, r14
0x18006ad90  jz      short loc_18006ADB6
0x18006ad92  test    byte ptr [rcx+1Ch], 80h
0x18006ad96  jz      short loc_18006ADB6
0x18006ad98  cmp     byte ptr [rcx+19h], 6
0x18006ad9c  jb      short loc_18006ADB6
0x18006ad9e  mov     edx, 54h ; 'T'
0x18006ada3  mov     r9d, ebx
0x18006ada6  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006adad  mov     rcx, [rcx+10h]
0x18006adb1  call    WPP_SF_d
0x18006adb6  mov     eax, ebx
0x18006adb8  jmp     loc_18006AAAB
0x18006adbd  call    PbkPathInfoInit
0x18006adc2  mov     ebx, eax
0x18006adc4  test    eax, eax
0x18006adc6  jz      short loc_18006AE17
0x18006adc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006adcf  cmp     rcx, r14
0x18006add2  jz      short loc_18006ADB6
0x18006add4  test    byte ptr [rcx+1Ch], 80h
0x18006add8  jz      short loc_18006ADFF
0x18006adda  cmp     byte ptr [rcx+19h], 2
0x18006adde  jb      short loc_18006ADFF
0x18006ade0  mov     edx, 55h ; 'U'
0x18006ade5  mov     r9d, eax
0x18006ade8  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006adef  mov     rcx, [rcx+10h]
0x18006adf3  call    WPP_SF_d
0x18006adf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006adff  cmp     rcx, r14
0x18006ae02  jz      short loc_18006ADB6
0x18006ae04  test    byte ptr [rcx+1Ch], 80h
0x18006ae08  jz      short loc_18006ADB6
0x18006ae0a  cmp     byte ptr [rcx+19h], 6
0x18006ae0e  jb      short loc_18006ADB6
0x18006ae10  mov     edx, 56h ; 'V'
0x18006ae15  jmp     short loc_18006ADA3
0x18006ae17  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ae1e  cmp     rcx, r14
0x18006ae21  jz      short loc_18006AE47
0x18006ae23  test    byte ptr [rcx+1Ch], 80h
0x18006ae27  jz      short loc_18006AE47
0x18006ae29  cmp     byte ptr [rcx+19h], 6
0x18006ae2d  jb      short loc_18006AE47
0x18006ae2f  mov     edx, 58h ; 'X'
0x18006ae34  xor     r9d, r9d
0x18006ae37  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006ae3e  mov     rcx, [rcx+10h]
0x18006ae42  call    WPP_SF_d
0x18006ae47  xor     eax, eax
0x18006ae49  jmp     loc_18006AAAB
0x1800e7be5  push    rbp
  ... truncated ...
```
