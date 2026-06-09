# InitializePbk

- ea: `0x18006e3fc`
- end: `0x18006e8ff`
- name: `InitializePbk`
- size: `1283`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800073ac`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18006bb54`
- `0x18006e3fc`
- `0x1800844e0`
- `0x1800e8e66`
- `0x1800e8e96`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e6c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e6c1`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18006e5a4`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18006e6a9`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18006e5a4`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18006e6a9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18006e559`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18006e62b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18006e559`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18006e62b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006e80c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006e827`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e98e1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e98f7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006e80c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006e827`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e98e1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e98f7`

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
  v3 = DwAllocateSecurityDescriptorAllowAccessToWorld(&v19, (struct _ACL **)&hMem);
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
    local_unwind_0(v17, &loc_18006E51B);
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
0x18006e3fc  mov     [rsp+arg_10], rbx
0x18006e401  mov     [rsp+arg_18], r14
0x18006e406  push    r15
0x18006e408  sub     rsp, 50h
0x18006e40c  mov     [rsp+58h+var_30], rsp
0x18006e411  lea     r14, WPP_GLOBAL_Control
0x18006e418  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e41f  cmp     rcx, r14
0x18006e422  jz      short loc_18006E44C
0x18006e424  test    byte ptr [rcx+1Ch], 80h
0x18006e428  jz      short loc_18006E44C
0x18006e42a  cmp     byte ptr [rcx+19h], 6
0x18006e42e  jb      short loc_18006E44C
0x18006e430  mov     edx, 4Ah ; 'J'
0x18006e435  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006e43c  mov     rcx, [rcx+10h]
0x18006e440  call    WPP_SF_
0x18006e445  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e44c  xor     ebx, ebx
0x18006e44e  xor     r15d, r15d
0x18006e451  mov     [rsp+58h+arg_0], r15
0x18006e456  mov     [rsp+58h+hMem], rbx
0x18006e45b  cmp     cs:g_hmutexPb, r15
0x18006e462  jnz     loc_18006E777
0x18006e468  xorps   xmm0, xmm0
0x18006e46b  xor     eax, eax
0x18006e46d  movups  xmmword ptr [rsp+58h+MutexAttributes.nLength], xmm0
0x18006e472  mov     qword ptr [rsp+58h+MutexAttributes.bInheritHandle], rax
0x18006e477  xor     edx, edx; Val
0x18006e479  lea     r8d, [rbx+60h]; Size
0x18006e47d  lea     rcx, g_PbkPathInfo; void *
0x18006e484  call    memset_0
0x18006e489  lea     rdx, [rsp+58h+hMem]
0x18006e48e  lea     rcx, [rsp+58h+arg_0]
0x18006e493  call    DwAllocateSecurityDescriptorAllowAccessToWorld
0x18006e498  mov     ebx, eax
0x18006e49a  mov     [rsp+58h+var_38], eax
0x18006e49e  test    eax, eax
0x18006e4a0  jz      loc_18006E531
0x18006e4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e4ad  cmp     rcx, r14
0x18006e4b0  jz      short loc_18006E505
0x18006e4b2  test    byte ptr [rcx+1Ch], 80h
0x18006e4b6  jz      short loc_18006E4DC
0x18006e4b8  cmp     byte ptr [rcx+19h], 2
0x18006e4bc  jb      short loc_18006E4DC
0x18006e4be  lea     edx, [r15+4Bh]
0x18006e4c2  mov     r9d, eax
0x18006e4c5  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006e4cc  mov     rcx, [rcx+10h]
0x18006e4d0  call    WPP_SF_d
0x18006e4d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e4dc  cmp     rcx, r14
0x18006e4df  jz      short loc_18006E505
0x18006e4e1  test    byte ptr [rcx+1Ch], 80h
0x18006e4e5  jz      short loc_18006E505
0x18006e4e7  cmp     byte ptr [rcx+19h], 6
0x18006e4eb  jb      short loc_18006E505
0x18006e4ed  mov     edx, 4Ch ; 'L'
0x18006e4f2  mov     r9d, ebx
0x18006e4f5  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006e4fc  mov     rcx, [rcx+10h]
0x18006e500  call    WPP_SF_d
0x18006e505  mov     [rsp+58h+var_34], ebx
0x18006e509  lea     rdx, loc_18006E51B
0x18006e510  mov     rcx, [rsp+58h+var_30]
0x18006e515  call    _local_unwind_0
0x18006e51a  nop
0x18006e51b  mov     eax, [rsp+58h+var_38]
0x18006e51f  mov     rbx, [rsp+58h+arg_10]
0x18006e524  mov     r14, [rsp+58h+arg_18]
0x18006e529  add     rsp, 50h
0x18006e52d  pop     r15
0x18006e52f  retn
0x18006e531  mov     [rsp+58h+MutexAttributes.nLength], 18h
0x18006e539  mov     r15, [rsp+58h+arg_0]
0x18006e53e  mov     [rsp+58h+MutexAttributes.lpSecurityDescriptor], r15
0x18006e543  mov     [rsp+58h+MutexAttributes.bInheritHandle], 0
0x18006e54b  lea     r8, Name; "Global\\RasPbFile"
0x18006e552  xor     edx, edx; bInitialOwner
0x18006e554  lea     rcx, [rsp+58h+MutexAttributes]; lpMutexAttributes
0x18006e559  call    cs:__imp_CreateMutexW
0x18006e560  nop     dword ptr [rax+rax+00h]
0x18006e565  mov     cs:g_hmutexPb, rax
0x18006e56c  test    rax, rax
0x18006e56f  jnz     loc_18006E770
0x18006e575  call    cs:__imp_GetLastError
0x18006e57c  nop     dword ptr [rax+rax+00h]
0x18006e581  mov     ebx, eax
0x18006e583  mov     [rsp+58h+var_38], eax
0x18006e587  cmp     eax, 5
0x18006e58a  jnz     loc_18006E73C
0x18006e590  xor     ebx, ebx
0x18006e592  mov     [rsp+58h+var_38], ebx
0x18006e596  lea     r8, Name; "Global\\RasPbFile"
0x18006e59d  xor     edx, edx; bInheritHandle
0x18006e59f  mov     ecx, 100000h; dwDesiredAccess
0x18006e5a4  call    cs:__imp_OpenMutexW
0x18006e5ab  nop     dword ptr [rax+rax+00h]
0x18006e5b0  mov     cs:g_hmutexPb, rax
0x18006e5b7  test    rax, rax
0x18006e5ba  jnz     loc_18006E770
0x18006e5c0  call    cs:__imp_GetLastError
0x18006e5c7  nop     dword ptr [rax+rax+00h]
0x18006e5cc  mov     ebx, eax
0x18006e5ce  mov     [rsp+58h+var_38], eax
0x18006e5d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e5d9  cmp     rcx, r14
0x18006e5dc  jz      short loc_18006E609
0x18006e5de  test    byte ptr [rcx+1Ch], 80h
0x18006e5e2  jz      short loc_18006E609
0x18006e5e4  cmp     byte ptr [rcx+19h], 2
0x18006e5e8  jb      short loc_18006E609
0x18006e5ea  mov     edx, 4Dh ; 'M'
0x18006e5ef  mov     r9d, eax
0x18006e5f2  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006e5f9  mov     rcx, [rcx+10h]
0x18006e5fd  call    WPP_SF_d
0x18006e602  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e609  cmp     ebx, 5
0x18006e60c  jz      short loc_18006E617
0x18006e60e  cmp     ebx, 2
0x18006e611  jnz     loc_18006E70A
0x18006e617  xor     ebx, ebx
0x18006e619  mov     [rsp+58h+var_38], ebx
0x18006e61d  lea     r8, aRaspbfile; "RasPbFile"
0x18006e624  xor     edx, edx; bInitialOwner
0x18006e626  lea     rcx, [rsp+58h+MutexAttributes]; lpMutexAttributes
0x18006e62b  call    cs:__imp_CreateMutexW
0x18006e632  nop     dword ptr [rax+rax+00h]
0x18006e637  mov     cs:g_hmutexPb, rax
0x18006e63e  test    rax, rax
0x18006e641  jnz     loc_18006E703
0x18006e647  call    cs:__imp_GetLastError
0x18006e64e  nop     dword ptr [rax+rax+00h]
0x18006e653  mov     ebx, eax
0x18006e655  mov     [rsp+58h+var_38], eax
0x18006e659  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e660  cmp     rcx, r14
0x18006e663  jz      short loc_18006E690
0x18006e665  test    byte ptr [rcx+1Ch], 80h
0x18006e669  jz      short loc_18006E690
0x18006e66b  cmp     byte ptr [rcx+19h], 2
0x18006e66f  jb      short loc_18006E690
0x18006e671  mov     edx, 4Eh ; 'N'
0x18006e676  mov     r9d, eax
0x18006e679  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006e680  mov     rcx, [rcx+10h]
0x18006e684  call    WPP_SF_d
0x18006e689  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e690  cmp     ebx, 5
0x18006e693  jnz     short loc_18006E70A
0x18006e695  xor     ebx, ebx
0x18006e697  mov     [rsp+58h+var_38], ebx
0x18006e69b  lea     r8, aRaspbfile; "RasPbFile"
0x18006e6a2  xor     edx, edx; bInheritHandle
0x18006e6a4  mov     ecx, 100000h; dwDesiredAccess
0x18006e6a9  call    cs:__imp_OpenMutexW
0x18006e6b0  nop     dword ptr [rax+rax+00h]
0x18006e6b5  mov     cs:g_hmutexPb, rax
0x18006e6bc  test    rax, rax
0x18006e6bf  jnz     short loc_18006E703
0x18006e6c1  call    cs:__imp_GetLastError
0x18006e6c8  nop     dword ptr [rax+rax+00h]
0x18006e6cd  mov     ebx, eax
0x18006e6cf  mov     [rsp+58h+var_38], eax
0x18006e6d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e6da  cmp     rcx, r14
0x18006e6dd  jz      short loc_18006E70A
0x18006e6df  test    byte ptr [rcx+1Ch], 80h
0x18006e6e3  jz      short loc_18006E70A
0x18006e6e5  cmp     byte ptr [rcx+19h], 2
0x18006e6e9  jb      short loc_18006E70A
0x18006e6eb  mov     edx, 4Fh ; 'O'
0x18006e6f0  mov     r9d, eax
0x18006e6f3  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006e6fa  mov     rcx, [rcx+10h]
0x18006e6fe  call    WPP_SF_d
0x18006e703  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e70a  test    ebx, ebx
0x18006e70c  jnz     short loc_18006E777
0x18006e70e  cmp     cs:g_hmutexPb, 0
0x18006e716  jnz     short loc_18006E777
0x18006e718  mov     ebx, 3EBh
0x18006e71d  mov     [rsp+58h+var_38], ebx
0x18006e721  cmp     rcx, r14
0x18006e724  jz      short loc_18006E777
0x18006e726  test    byte ptr [rcx+1Ch], 80h
0x18006e72a  jz      short loc_18006E777
0x18006e72c  cmp     byte ptr [rcx+19h], 2
0x18006e730  jb      short loc_18006E777
0x18006e732  mov     edx, 50h ; 'P'
0x18006e737  mov     r9d, ebx
0x18006e73a  jmp     short loc_18006E760
0x18006e73c  test    eax, eax
0x18006e73e  jz      short loc_18006E770
0x18006e740  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e747  cmp     rcx, r14
0x18006e74a  jz      short loc_18006E777
0x18006e74c  test    byte ptr [rcx+1Ch], 80h
0x18006e750  jz      short loc_18006E777
0x18006e752  cmp     byte ptr [rcx+19h], 2
0x18006e756  jb      short loc_18006E777
0x18006e758  mov     edx, 51h ; 'Q'
0x18006e75d  mov     r9d, eax
0x18006e760  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006e767  mov     rcx, [rcx+10h]
0x18006e76b  call    WPP_SF_d
0x18006e770  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e777  jmp     loc_18006E7FF
0x18006e77c  mov     ebx, eax
0x18006e77e  mov     [rsp+58h+var_38], eax
0x18006e782  test    eax, eax
0x18006e784  jnz     short loc_18006E7B5
0x18006e786  mov     ebx, 3EBh
0x18006e78b  mov     [rsp+58h+var_38], ebx
0x18006e78f  lea     rax, WPP_GLOBAL_Control
0x18006e796  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e79d  cmp     rcx, rax
0x18006e7a0  jz      short loc_18006E7F3
0x18006e7a2  test    byte ptr [rcx+1Ch], 80h
0x18006e7a6  jz      short loc_18006E7F3
0x18006e7a8  cmp     byte ptr [rcx+19h], 2
0x18006e7ac  jb      short loc_18006E7F3
0x18006e7ae  mov     edx, 52h ; 'R'
0x18006e7b3  jmp     short loc_18006E7D9
0x18006e7b5  lea     rax, WPP_GLOBAL_Control
0x18006e7bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e7c3  cmp     rcx, rax
0x18006e7c6  jz      short loc_18006E7F3
0x18006e7c8  test    byte ptr [rcx+1Ch], 80h
0x18006e7cc  jz      short loc_18006E7F3
0x18006e7ce  cmp     byte ptr [rcx+19h], 2
0x18006e7d2  jb      short loc_18006E7F3
0x18006e7d4  mov     edx, 53h ; 'S'
0x18006e7d9  mov     r9d, ebx
0x18006e7dc  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006e7e3  mov     rcx, [rcx+10h]
0x18006e7e7  call    WPP_SF_d
0x18006e7ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e7f3  lea     r14, WPP_GLOBAL_Control
0x18006e7fa  mov     r15, [rsp+58h+arg_0]
0x18006e7ff  mov     rax, [rsp+58h+hMem]
0x18006e804  test    rax, rax
0x18006e807  jz      short loc_18006E81F
0x18006e809  mov     rcx, rax; hMem
0x18006e80c  call    cs:__imp_GlobalFree
0x18006e813  nop     dword ptr [rax+rax+00h]
0x18006e818  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e81f  test    r15, r15
0x18006e822  jz      short loc_18006E83A
0x18006e824  mov     rcx, r15; hMem
0x18006e827  call    cs:__imp_GlobalFree
0x18006e82e  nop     dword ptr [rax+rax+00h]
0x18006e833  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e83a  test    ebx, ebx
0x18006e83c  jz      short loc_18006E86E
0x18006e83e  cmp     rcx, r14
0x18006e841  jz      short loc_18006E867
0x18006e843  test    byte ptr [rcx+1Ch], 80h
0x18006e847  jz      short loc_18006E867
0x18006e849  cmp     byte ptr [rcx+19h], 6
0x18006e84d  jb      short loc_18006E867
0x18006e84f  mov     edx, 54h ; 'T'
0x18006e854  mov     r9d, ebx
0x18006e857  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006e85e  mov     rcx, [rcx+10h]
0x18006e862  call    WPP_SF_d
0x18006e867  mov     eax, ebx
0x18006e869  jmp     loc_18006E51F
0x18006e86e  call    PbkPathInfoInit
0x18006e873  mov     ebx, eax
0x18006e875  test    eax, eax
0x18006e877  jz      short loc_18006E8C8
0x18006e879  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e880  cmp     rcx, r14
0x18006e883  jz      short loc_18006E867
0x18006e885  test    byte ptr [rcx+1Ch], 80h
0x18006e889  jz      short loc_18006E8B0
0x18006e88b  cmp     byte ptr [rcx+19h], 2
0x18006e88f  jb      short loc_18006E8B0
0x18006e891  mov     edx, 55h ; 'U'
0x18006e896  mov     r9d, eax
0x18006e899  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006e8a0  mov     rcx, [rcx+10h]
0x18006e8a4  call    WPP_SF_d
0x18006e8a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e8b0  cmp     rcx, r14
0x18006e8b3  jz      short loc_18006E867
0x18006e8b5  test    byte ptr [rcx+1Ch], 80h
0x18006e8b9  jz      short loc_18006E867
0x18006e8bb  cmp     byte ptr [rcx+19h], 6
0x18006e8bf  jb      short loc_18006E867
0x18006e8c1  mov     edx, 56h ; 'V'
0x18006e8c6  jmp     short loc_18006E854
0x18006e8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e8cf  cmp     rcx, r14
0x18006e8d2  jz      short loc_18006E8F8
0x18006e8d4  test    byte ptr [rcx+1Ch], 80h
0x18006e8d8  jz      short loc_18006E8F8
  ... truncated ...
```
