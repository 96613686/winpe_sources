# InitializeProcessImageNameUM

- ea: `0x180019060`
- end: `0x18001944f`
- name: `InitializeProcessImageNameUM`
- size: `1007`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180013a7c`

## callees

- `0x180005384`
- `0x180016c38`
- `0x180019060`
- `0x180019458`
- `0x18001c9e8`
- `0x18001f175`
- `0x18001f1b0`

## import_xrefs

- `ntdll!wcsncpy_s` at `0x180019255`
- `ntdll!wcsncpy_s` at `0x1800192bb`
- `ntdll!wcsncpy_s` at `0x180019255`
- `ntdll!wcsncpy_s` at `0x1800192bb`
- `ntdll!_wcsnicmp` at `0x1800191e2`
- `ntdll!_wcsnicmp` at `0x1800191e2`
- `ntdll!_wsplitpath_s` at `0x180019183`
- `ntdll!_wsplitpath_s` at `0x180019183`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019260`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001909a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001910f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001909a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001910f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019089`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019089`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800191fe`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800191fe`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180019105`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180019105`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180019230`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180019283`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180019230`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180019283`

## pseudocode

```c
unsigned int InitializeProcessImageNameUM()
{
  HANDLE CurrentProcess; // rdi
  unsigned int result; // eax
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  PVOID v4; // rcx
  __int64 v5; // rsi
  wchar_t *v6; // r8
  __int64 v7; // r14
  DWORD ProcessId; // eax
  DWORD v9; // edi
  wchar_t *v10; // rcx
  int v11; // eax
  wchar_t *v12; // rdi
  __int64 v13; // rax
  const wchar_t *v14; // r8
  PVOID *v15; // r10
  __int64 v16; // rcx
  wchar_t *p_String1; // rdx
  wchar_t *v18; // rax
  wchar_t *v19; // rcx
  DWORD dwSize; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v21[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h]
  wchar_t *Source; // [rsp+68h] [rbp-98h]
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  wchar_t String1; // [rsp+80h] [rbp-80h] BYREF
  char v26[510]; // [rsp+82h] [rbp-7Eh] BYREF
  wchar_t Destination; // [rsp+280h] [rbp+180h] BYREF
  char v28[526]; // [rsp+282h] [rbp+182h] BYREF
  WCHAR ExeName; // [rsp+490h] [rbp+390h] BYREF
  char v30[526]; // [rsp+492h] [rbp+392h] BYREF

  CurrentProcess = GetCurrentProcess();
  if ( !CurrentProcess )
  {
    result = GetLastError();
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v3 = 10;
LABEL_5:
      v4 = (PVOID)v2[2];
      return WPP_SF_D(v4, v3, WPP_e1d0dcb54b7b37c40c9d35ea35f91ff9_Traceguids, result);
    }
    return result;
  }
  ExeName = 0;
  memset_0(v30, 0, 0x206u);
  v5 = 260;
  dwSize = 260;
  if ( QueryFullProcessImageNameW(CurrentProcess, 0, &ExeName, &dwSize) )
  {
    String1 = 0;
    memset_0(v26, 0, sizeof(v26));
    result = _wsplitpath_s(&ExeName, 0, 0, 0, 0, &String1, 0x100u, 0, 0);
    if ( result )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v3 = 12;
        goto LABEL_5;
      }
      return result;
    }
    Destination = 0;
    memset_0(v28, 0, 0x206u);
    v7 = -1;
    if ( _wcsnicmp(&String1, L"svchost", 7u) )
      goto LABEL_30;
    ProcessId = GetProcessId(CurrentProcess);
    v22 = 0;
    v9 = ProcessId;
    Source = 0;
    v21[0] = ProcessId;
    v21[1] = NtCurrentTeb()->SubProcessTag;
    if ( (unsigned int)I_QueryTagInformation(0, 1, v21) )
    {
      v24 = 0;
      LODWORD(v24) = v9;
      v11 = I_QueryTagInformation(0, 3, &v24);
      if ( !v11 )
      {
        v12 = (wchar_t *)*((_QWORD *)&v24 + 1);
        if ( !*((_QWORD *)&v24 + 1) )
          goto LABEL_30;
        if ( **((_DWORD **)&v24 + 1) == 1 )
        {
          v13 = *(_QWORD *)(*((_QWORD *)&v24 + 1) + 8LL);
          if ( *(_DWORD *)v13 == 1 )
          {
            v14 = *(const wchar_t **)(v13 + 8);
            if ( v14 )
              wcsncpy_s(&Destination, 0x104u, v14, 0xFFFFFFFFFFFFFFFFuLL);
          }
        }
        v10 = v12;
        goto LABEL_18;
      }
      if ( v11 < 0 )
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_31;
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_e1d0dcb54b7b37c40c9d35ea35f91ff9_Traceguids,
          (unsigned int)v11);
      }
    }
    else
    {
      v6 = Source;
      if ( Source )
      {
        wcsncpy_s(&Destination, 0x104u, Source, 0xFFFFFFFFFFFFFFFFuLL);
        v10 = Source;
LABEL_18:
        LocalFree(v10);
      }
    }
LABEL_30:
    v15 = (PVOID *)WPP_GLOBAL_Control;
    do
LABEL_31:
      ++v7;
    while ( *(_WORD *)&v28[2 * v7 - 2] );
    if ( v7 )
    {
      result = StringCchPrintfW(g_processImageNameNcrypt, 0x104u, L"%ls[%ls]", &String1, &Destination);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v16 = 2147483646;
      p_String1 = &String1;
      v18 = g_processImageNameNcrypt;
      do
      {
        if ( !v16 )
          break;
        v6 = (wchar_t *)*p_String1;
        if ( !(_WORD)v6 )
          break;
        *v18 = (unsigned __int16)v6;
        ++p_String1;
        ++v18;
        --v16;
        --v5;
      }
      while ( v5 );
      v19 = v18 - 1;
      if ( v5 )
        v19 = v18;
      result = v5 == 0 ? 0x8007007A : 0;
      *v19 = 0;
    }
    if ( result == -2147024774 )
    {
      if ( v15 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v15 + 28) & 2) != 0 )
        {
          result = WPP_SF_(v15[2], 14, WPP_e1d0dcb54b7b37c40c9d35ea35f91ff9_Traceguids);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v15 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v15 + 28) & 2) != 0 )
          {
            result = WPP_SF_S(v15[2], 15, v6, &String1);
            v15 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
            return WPP_SF_S(v15[2], 16, v6, &Destination);
        }
      }
    }
    else if ( (result & 0x80000000) != 0 && v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
    {
      v4 = v15[2];
      v3 = 17;
      return WPP_SF_D(v4, v3, WPP_e1d0dcb54b7b37c40c9d35ea35f91ff9_Traceguids, result);
    }
    return result;
  }
  result = GetLastError();
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v3 = 11;
    goto LABEL_5;
  }
  return result;
}

```

## disassembly

```asm
0x180019060  push    rbp
0x180019062  push    rbx
0x180019063  push    rsi
0x180019064  push    rdi
0x180019065  push    r14
0x180019067  push    r15
0x180019069  lea     rbp, [rsp-5B8h]
0x180019071  sub     rsp, 6B8h
0x180019078  mov     rax, cs:__security_cookie
0x18001907f  xor     rax, rsp
0x180019082  mov     [rbp+5E0h+var_40], rax
0x180019089  call    cs:__imp_GetCurrentProcess
0x18001908f  xor     r15d, r15d
0x180019092  mov     rdi, rax
0x180019095  test    rax, rax
0x180019098  jnz     short loc_1800190CD
0x18001909a  call    cs:__imp_GetLastError
0x1800190a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190a7  lea     rbx, WPP_GLOBAL_Control
0x1800190ae  cmp     rcx, rbx
0x1800190b1  jz      loc_180019430
0x1800190b7  test    byte ptr [rcx+1Ch], 2
0x1800190bb  jz      loc_180019430
0x1800190c1  lea     edx, [rdi+0Ah]
0x1800190c4  mov     rcx, [rcx+10h]
0x1800190c8  jmp     loc_180019421
0x1800190cd  mov     ebx, 206h
0x1800190d2  mov     [rbp+5E0h+ExeName], r15w
0x1800190da  mov     r8d, ebx; Size
0x1800190dd  lea     rcx, [rbp+5E0h+var_24E]; void *
0x1800190e4  xor     edx, edx; Val
0x1800190e6  call    memset_0
0x1800190eb  mov     esi, 104h
0x1800190f0  lea     r9, [rsp+6E0h+dwSize]; lpdwSize
0x1800190f5  lea     r8, [rbp+5E0h+ExeName]; lpExeName
0x1800190fc  mov     [rsp+6E0h+dwSize], esi
0x180019100  xor     edx, edx; dwFlags
0x180019102  mov     rcx, rdi; hProcess
0x180019105  call    cs:__imp_QueryFullProcessImageNameW
0x18001910b  test    eax, eax
0x18001910d  jnz     short loc_18001913D
0x18001910f  call    cs:__imp_GetLastError
0x180019115  mov     rcx, cs:WPP_GLOBAL_Control
0x18001911c  lea     rbx, WPP_GLOBAL_Control
0x180019123  cmp     rcx, rbx
0x180019126  jz      loc_180019430
0x18001912c  test    byte ptr [rcx+1Ch], 2
0x180019130  jz      loc_180019430
0x180019136  mov     edx, 0Bh
0x18001913b  jmp     short loc_1800190C4
0x18001913d  xor     edx, edx; Val
0x18001913f  mov     [rbp+5E0h+String1], r15w
0x180019144  mov     r8d, 1FEh; Size
0x18001914a  lea     rcx, [rbp+5E0h+var_65E]; void *
0x18001914e  call    memset_0
0x180019153  mov     [rsp+6E0h+ExtCount], r15; ExtCount
0x180019158  lea     rax, [rbp+5E0h+String1]
0x18001915c  mov     [rsp+6E0h+Ext], r15; Ext
0x180019161  lea     rcx, [rbp+5E0h+ExeName]; FullPath
0x180019168  mov     [rsp+6E0h+FilenameCount], 100h; FilenameCount
0x180019171  xor     r9d, r9d; Dir
0x180019174  mov     [rsp+6E0h+Filename], rax; Filename
0x180019179  xor     r8d, r8d; DriveCount
0x18001917c  xor     edx, edx; Drive
0x18001917e  mov     [rsp+6E0h+DirCount], r15; DirCount
0x180019183  call    cs:__imp__wsplitpath_s
0x180019189  test    eax, eax
0x18001918b  jz      short loc_1800191B8
0x18001918d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019194  lea     rbx, WPP_GLOBAL_Control
0x18001919b  cmp     rcx, rbx
0x18001919e  jz      loc_180019430
0x1800191a4  test    byte ptr [rcx+1Ch], 2
0x1800191a8  jz      loc_180019430
0x1800191ae  mov     edx, 0Ch
0x1800191b3  jmp     loc_1800190C4
0x1800191b8  mov     r8, rbx; Size
0x1800191bb  mov     [rbp+5E0h+Destination], r15w
0x1800191c3  xor     edx, edx; Val
0x1800191c5  lea     rcx, [rbp+5E0h+var_45E]; void *
0x1800191cc  call    memset_0
0x1800191d1  mov     r8d, 7; MaxCount
0x1800191d7  lea     rdx, aSvchost; "svchost"
0x1800191de  lea     rcx, [rbp+5E0h+String1]; String1
0x1800191e2  call    cs:__imp__wcsnicmp
0x1800191e8  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800191ec  lea     rbx, WPP_GLOBAL_Control
0x1800191f3  test    eax, eax
0x1800191f5  jnz     loc_1800192F3
0x1800191fb  mov     rcx, rdi; Process
0x1800191fe  call    cs:__imp_GetProcessId
0x180019204  xorps   xmm0, xmm0
0x180019207  lea     r8, [rsp+6E0h+var_688]
0x18001920c  movups  [rsp+6E0h+var_688], xmm0
0x180019211  mov     edi, eax
0x180019213  xor     eax, eax
0x180019215  mov     [rsp+6E0h+Source], rax
0x18001921a  mov     dword ptr [rsp+6E0h+var_688], edi
0x18001921e  mov     rcx, gs:1720h
0x180019227  mov     dword ptr [rsp+6E0h+var_688+4], ecx
0x18001922b  lea     edx, [rax+1]
0x18001922e  xor     ecx, ecx
0x180019230  call    cs:__imp_I_QueryTagInformation
0x180019236  test    eax, eax
0x180019238  jnz     short loc_18001926B
0x18001923a  mov     r8, [rsp+6E0h+Source]; Source
0x18001923f  test    r8, r8
0x180019242  jz      loc_1800192F3
0x180019248  mov     r9, r14; MaxCount
0x18001924b  lea     rcx, [rbp+5E0h+Destination]; Destination
0x180019252  mov     rdx, rsi; SizeInWords
0x180019255  call    cs:__imp_wcsncpy_s
0x18001925b  mov     rcx, [rsp+6E0h+Source]; hMem
0x180019260  call    cs:__imp_LocalFree
0x180019266  jmp     loc_1800192F3
0x18001926b  xorps   xmm0, xmm0
0x18001926e  lea     r8, [rsp+6E0h+var_670]
0x180019273  movups  [rsp+6E0h+var_670], xmm0
0x180019278  mov     edx, 3
0x18001927d  mov     dword ptr [rsp+6E0h+var_670], edi
0x180019281  xor     ecx, ecx
0x180019283  call    cs:__imp_I_QueryTagInformation
0x180019289  test    eax, eax
0x18001928b  jnz     short loc_1800192C6
0x18001928d  mov     rdi, qword ptr [rsp+6E0h+var_670+8]
0x180019292  test    rdi, rdi
0x180019295  jz      short loc_1800192F3
0x180019297  cmp     dword ptr [rdi], 1
0x18001929a  jnz     short loc_1800192C1
0x18001929c  mov     rax, [rdi+8]
0x1800192a0  cmp     dword ptr [rax], 1
0x1800192a3  jnz     short loc_1800192C1
0x1800192a5  mov     r8, [rax+8]; Source
0x1800192a9  test    r8, r8
0x1800192ac  jz      short loc_1800192C1
0x1800192ae  mov     r9, r14; MaxCount
0x1800192b1  lea     rcx, [rbp+5E0h+Destination]; Destination
0x1800192b8  mov     rdx, rsi; SizeInWords
0x1800192bb  call    cs:__imp_wcsncpy_s
0x1800192c1  mov     rcx, rdi
0x1800192c4  jmp     short loc_180019260
0x1800192c6  jns     short loc_1800192F3
0x1800192c8  mov     r10, cs:WPP_GLOBAL_Control
0x1800192cf  cmp     r10, rbx
0x1800192d2  jz      short loc_1800192FA
0x1800192d4  test    byte ptr [r10+1Ch], 2
0x1800192d9  jz      short loc_1800192FA
0x1800192db  mov     rcx, [r10+10h]
0x1800192df  lea     r8, WPP_e1d0dcb54b7b37c40c9d35ea35f91ff9_Traceguids
0x1800192e6  mov     edx, 0Dh
0x1800192eb  mov     r9d, eax
0x1800192ee  call    WPP_SF_D
0x1800192f3  mov     r10, cs:WPP_GLOBAL_Control
0x1800192fa  lea     rax, [rbp+5E0h+Destination]
0x180019301  inc     r14
0x180019304  cmp     [rax+r14*2], r15w
0x180019309  jnz     short loc_180019301
0x18001930b  mov     edi, 8007007Ah
0x180019310  test    r14, r14
0x180019313  jz      short loc_180019344
0x180019315  lea     rax, [rbp+5E0h+Destination]
0x18001931c  mov     rdx, rsi; cchDest
0x18001931f  lea     r9, [rbp+5E0h+String1]
0x180019323  mov     [rsp+6E0h+DirCount], rax
0x180019328  lea     r8, aLsLs_0; "%ls[%ls]"
0x18001932f  lea     rcx, g_processImageNameNcrypt; "UNKNOWN"
0x180019336  call    StringCchPrintfW
0x18001933b  mov     r10, cs:WPP_GLOBAL_Control
0x180019342  jmp     short loc_180019390
0x180019344  mov     ecx, 7FFFFFFEh
0x180019349  lea     rdx, [rbp+5E0h+String1]
0x18001934d  lea     rax, g_processImageNameNcrypt; "UNKNOWN"
0x180019354  test    rcx, rcx
0x180019357  jz      short loc_180019378
0x180019359  movzx   r8d, word ptr [rdx]
0x18001935d  test    r8w, r8w
0x180019361  jz      short loc_180019378
0x180019363  mov     [rax], r8w
0x180019367  add     rdx, 2
0x18001936b  add     rax, 2
0x18001936f  dec     rcx
0x180019372  sub     rsi, 1
0x180019376  jnz     short loc_180019354
0x180019378  lea     rcx, [rax-2]
0x18001937c  test    rsi, rsi
0x18001937f  cmovnz  rcx, rax
0x180019383  neg     rsi
0x180019386  sbb     eax, eax
0x180019388  not     eax
0x18001938a  and     eax, edi
0x18001938c  mov     [rcx], r15w
0x180019390  cmp     eax, edi
0x180019392  jnz     short loc_180019408
0x180019394  cmp     r10, rbx
0x180019397  jz      loc_180019430
0x18001939d  test    byte ptr [r10+1Ch], 2
0x1800193a2  jz      short loc_1800193C0
0x1800193a4  mov     rcx, [r10+10h]
0x1800193a8  lea     r8, WPP_e1d0dcb54b7b37c40c9d35ea35f91ff9_Traceguids
0x1800193af  mov     edx, 0Eh
0x1800193b4  call    WPP_SF_
0x1800193b9  mov     r10, cs:WPP_GLOBAL_Control
0x1800193c0  cmp     r10, rbx
0x1800193c3  jz      short loc_180019430
0x1800193c5  test    byte ptr [r10+1Ch], 2
0x1800193ca  jz      short loc_1800193E5
0x1800193cc  mov     rcx, [r10+10h]
0x1800193d0  lea     r9, [rbp+5E0h+String1]
0x1800193d4  mov     edx, 0Fh
0x1800193d9  call    WPP_SF_S
0x1800193de  mov     r10, cs:WPP_GLOBAL_Control
0x1800193e5  cmp     r10, rbx
0x1800193e8  jz      short loc_180019430
0x1800193ea  test    byte ptr [r10+1Ch], 2
0x1800193ef  jz      short loc_180019430
0x1800193f1  mov     rcx, [r10+10h]
0x1800193f5  lea     r9, [rbp+5E0h+Destination]
0x1800193fc  mov     edx, 10h
0x180019401  call    WPP_SF_S
0x180019406  jmp     short loc_180019430
0x180019408  test    eax, eax
0x18001940a  jns     short loc_180019430
0x18001940c  cmp     r10, rbx
0x18001940f  jz      short loc_180019430
0x180019411  test    byte ptr [r10+1Ch], 1
0x180019416  jz      short loc_180019430
0x180019418  mov     rcx, [r10+10h]
0x18001941c  mov     edx, 11h
0x180019421  mov     r9d, eax
0x180019424  lea     r8, WPP_e1d0dcb54b7b37c40c9d35ea35f91ff9_Traceguids
0x18001942b  call    WPP_SF_D
0x180019430  mov     rcx, [rbp+5E0h+var_40]
0x180019437  xor     rcx, rsp; StackCookie
0x18001943a  call    __security_check_cookie
0x18001943f  add     rsp, 6B8h
0x180019446  pop     r15
0x180019448  pop     r14
0x18001944a  pop     rdi
0x18001944b  pop     rsi
0x18001944c  pop     rbx
0x18001944d  pop     rbp
0x18001944e  retn
```
