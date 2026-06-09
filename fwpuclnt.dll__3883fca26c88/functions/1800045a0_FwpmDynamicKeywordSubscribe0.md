# FwpmDynamicKeywordSubscribe0

- ea: `0x1800045a0`
- end: `0x180004a81`
- name: `FwpmDynamicKeywordSubscribe0`
- size: `1249`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800034e0`
- `0x18000438c`
- `0x180004540`
- `0x1800045a0`
- `0x180004bdc`
- `0x180005fc8`
- `0x18000d6d0`
- `0x180011500`
- `0x180011de0`
- `0x180012bd0`
- `0x18001346a`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004783`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004783`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000476d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000476d`

## string_xrefs

- `0x18000460b`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x1800049c4`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x180004763`: `ntdll.dll`
- `0x18000480a`: `StringCchCopyW`
- `0x1800049d3`: `SharedAccessFirewallPolicy`

## pseudocode

```c
__int64 __fastcall FwpmDynamicKeywordSubscribe0(int a1, __int64 a2, __int64 a3, __int64 *a4)
{
  unsigned int v7; // r14d
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rdi
  unsigned int i; // ecx
  __int64 v13; // rax
  HMODULE ModuleHandleA; // rax
  FARPROC ProcAddress; // rax
  __int64 v16; // rcx
  _WORD *v17; // r8
  size_t v18; // rdx
  _WORD *v19; // rax
  _WORD *v20; // rcx
  __int64 v21; // r8
  const char *v22; // rdx
  __int64 v23; // rax
  __int64 v25; // rdx
  _WORD *v26; // rax
  __int64 v27; // r9
  const wchar_t *v28; // r8
  __int64 v29; // rcx
  _WORD *v30; // rax
  __int64 v31; // rdx
  unsigned int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // r8
  HRESULT v35; // eax
  const wchar_t *v36; // r8
  _OWORD *v37; // [rsp+28h] [rbp-E0h]
  __int64 v38; // [rsp+48h] [rbp-C0h] BYREF
  _WORD pszDest[77]; // [rsp+50h] [rbp-B8h] BYREF
  char v40[382]; // [rsp+EAh] [rbp-1Eh] BYREF
  _OWORD v41[9]; // [rsp+268h] [rbp+160h] BYREF
  wchar_t v42; // [rsp+2F8h] [rbp+1F0h]
  char v43[382]; // [rsp+2FAh] [rbp+1F2h] BYREF

  v7 = 0;
  v38 = 0;
  wcscpy(&pszDest[4], L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy");
  memset_0(v40, 0, 0x176u);
  v42 = aSystemCurrentc[72];
  v41[0] = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy";
  v41[1] = *(_OWORD *)L"urrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy";
  v41[2] = *(_OWORD *)L"ntrolSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy";
  v41[3] = *(_OWORD *)L"\\Services\\SharedAccess\\Parameters\\FirewallPolicy";
  v41[4] = *(_OWORD *)L"s\\SharedAccess\\Parameters\\FirewallPolicy";
  v41[5] = *(_OWORD *)L"Access\\Parameters\\FirewallPolicy";
  v41[6] = *(_OWORD *)L"arameters\\FirewallPolicy";
  v41[7] = *(_OWORD *)L"s\\FirewallPolicy";
  v41[8] = *(_OWORD *)L"llPolicy";
  memset_0(v43, 0, 0x176u);
  if ( !a2 || !a4 )
  {
    v34 = 2150760476LL;
LABEL_43:
    v23 = WfpReportSysErrorAsWinError(v9, "FwpmDynamicKeywordSubscribe0", v34);
    goto LABEL_19;
  }
  if ( (a1 & 4) != 0 || !a1 )
  {
    v34 = 87;
    goto LABEL_43;
  }
  v10 = WfpMemAlloc(0x28u, 0);
  if ( v10 )
    goto LABEL_52;
  v11 = v38;
  for ( i = 0; i < 2; ++i )
  {
    v13 = (int)i;
    *(_QWORD *)(v11 + 8 * v13) = 0;
  }
  *a4 = 0;
  ModuleHandleA = GetModuleHandleA("ntdll.dll");
  ProcAddress = GetProcAddress(ModuleHandleA, "RtlGetPersistedStateLocation");
  if ( ProcAddress )
  {
    v37 = v41;
    v32 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const wchar_t *, _QWORD))ProcAddress)(
            L"SharedAccessFirewallPolicy",
            0,
            L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
            0);
    if ( v32 )
    {
      v23 = WfpReportSysErrorAsNtStatus(v33, "pFuncGetPersistedStateLocation", v32);
LABEL_19:
      v10 = v23;
      goto LABEL_20;
    }
  }
  while ( v7 < 2 )
  {
    v16 = 2147483646;
    v17 = v41;
    v18 = 260;
    v19 = &pszDest[4];
    do
    {
      if ( !v16 )
        break;
      if ( !*v17 )
        break;
      *v19++ = *v17++;
      --v16;
      --v18;
    }
    while ( v18 );
    v20 = v19 - 1;
    if ( v18 )
      v20 = v19;
    *v20 = 0;
    v21 = v18 == 0 ? 0x8007007A : 0;
    if ( !v18 )
    {
      v22 = "StringCchCopyW";
      goto LABEL_18;
    }
    v21 = FWPP_SUB_REG_APPEND_KEYS[v7];
    if ( v21 )
    {
      v35 = StringCchCatW(&pszDest[4], v18, (STRSAFE_LPCWSTR)v21);
      if ( v35 < 0 )
      {
LABEL_51:
        v21 = (unsigned int)v35;
LABEL_28:
        v22 = "StringCchCatW";
LABEL_18:
        v23 = WfpReportSysErrorAsHResult(v20, v22, v21);
        goto LABEL_19;
      }
    }
    if ( (a1 & 3) == 3 )
    {
      v25 = 260;
      v26 = &pszDest[4];
      do
      {
        if ( !*v26 )
          break;
        ++v26;
        --v25;
      }
      while ( v25 );
      v20 = (_WORD *)(260 - v25);
      v21 = v25 == 0 ? 0x80070057 : 0;
      v27 = (260 - v25) & -(__int64)(v25 != 0);
      if ( !v25 )
        goto LABEL_28;
      v28 = L"\\DynamicKeywords\\Addresses";
      v29 = 2147483646;
      v30 = &pszDest[v27 + 4];
      v31 = 260 - v27;
      if ( v27 != 260 )
      {
        do
        {
          if ( !v29 )
            break;
          if ( !*v28 )
            break;
          *v30++ = *v28++;
          --v29;
          --v31;
        }
        while ( v31 );
      }
      v20 = v30 - 1;
      if ( v31 )
        v20 = v30;
      *v20 = 0;
      v21 = v31 == 0 ? 0x8007007A : 0;
      if ( !v31 )
        goto LABEL_28;
    }
    else
    {
      if ( (a1 & 1) != 0 )
      {
        v36 = L"\\DynamicKeywords\\Addresses\\AutoResolve";
      }
      else
      {
        if ( (a1 & 2) == 0 )
          goto LABEL_36;
        v36 = L"\\DynamicKeywords\\Addresses\\NonAutoResolve";
      }
      v35 = StringCchCatW(&pszDest[4], v18, v36);
      if ( v35 < 0 )
        goto LABEL_51;
    }
LABEL_36:
    v10 = WfpRegNotifyCreate(
            (__int64)v20,
            &pszDest[4],
            v21,
            4,
            (__int64)v37,
            (__int64)FwppDynamicKeywordOnChange,
            v11,
            (_QWORD *)(v11 + 8LL * (int)v7));
    if ( v10 )
      goto LABEL_52;
    ++v7;
  }
  *(_QWORD *)(v11 + 16) = a2;
  *(_QWORD *)(v11 + 32) = a3;
  *a4 = v11;
LABEL_20:
  if ( v10 )
LABEL_52:
    WfpMemFree(&v38);
  return WfpErrorToFwpErr(v10);
}

```

## disassembly

```asm
0x1800045a0  mov     rax, rsp
0x1800045a3  push    rbp
0x1800045a4  push    rbx
0x1800045a5  push    rsi
0x1800045a6  push    rdi
0x1800045a7  push    r12
0x1800045a9  push    r13
0x1800045ab  push    r14
0x1800045ad  push    r15
0x1800045af  lea     rbp, [rax-458h]
0x1800045b6  sub     rsp, 518h
0x1800045bd  movaps  xmmword ptr [rax-58h], xmm6
0x1800045c1  movaps  xmmword ptr [rax-68h], xmm7
0x1800045c5  movaps  xmmword ptr [rax-78h], xmm8
0x1800045ca  movaps  xmmword ptr [rax-88h], xmm9
0x1800045d2  movaps  xmmword ptr [rax-98h], xmm10
0x1800045da  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800045e2  movaps  xmmword ptr [rax-0B8h], xmm12
0x1800045ea  movaps  xmmword ptr [rax-0C8h], xmm13
0x1800045f2  movaps  xmmword ptr [rax-0D8h], xmm14
0x1800045fa  mov     rax, cs:__security_cookie
0x180004601  xor     rax, rsp
0x180004604  mov     [rbp+450h+var_E0], rax
0x18000460b  movaps  xmm14, xmmword ptr cs:aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x180004613  mov     r13, r8
0x180004616  movaps  xmm13, xmmword ptr cs:aSystemCurrentc+10h; "urrentControlSet\\Services\\SharedAcces"...
0x18000461e  mov     r12, rdx
0x180004621  movaps  xmm12, xmmword ptr cs:aSystemCurrentc+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x180004629  mov     esi, ecx
0x18000462b  movaps  xmm11, xmmword ptr cs:aSystemCurrentc+30h; "\\Services\\SharedAccess\\Parameters\\F"...
0x180004633  lea     rcx, [rbp+450h+var_46E]; void *
0x180004637  movaps  xmm10, xmmword ptr cs:aSystemCurrentc+40h; "s\\SharedAccess\\Parameters\\FirewallPo"...
0x18000463f  mov     edi, 176h
0x180004644  movaps  xmm9, xmmword ptr cs:aSystemCurrentc+50h; "Access\\Parameters\\FirewallPolicy"
0x18000464c  xor     r14d, r14d
0x18000464f  movaps  xmm8, xmmword ptr cs:aSystemCurrentc+60h; "arameters\\FirewallPolicy"
0x180004657  mov     r8d, edi; Size
0x18000465a  movaps  xmm7, xmmword ptr cs:aSystemCurrentc+70h; "s\\FirewallPolicy"
0x180004661  xor     edx, edx; Val
0x180004663  movaps  xmm6, xmmword ptr cs:aSystemCurrentc+80h; "llPolicy"
0x18000466a  mov     r15, r9
0x18000466d  movzx   ebx, word ptr cs:aSystemCurrentc+90h; ""
0x180004674  mov     [rsp+550h+var_510], r14
0x180004679  movups  xmmword ptr [rsp+550h+pszDest+8], xmm14
0x18000467f  mov     [rbp+450h+var_470], bx
0x180004683  movups  [rsp+550h+var_4F8+8], xmm13
0x180004689  movups  [rsp+550h+var_4E8+8], xmm12
0x18000468f  movups  [rbp+450h+var_4D0], xmm11
0x180004694  movups  [rbp+450h+var_4C0], xmm10
0x180004699  movups  [rbp+450h+var_4B0], xmm9
0x18000469e  movups  [rbp+450h+var_4A0], xmm8
0x1800046a3  movups  [rbp+450h+var_490], xmm7
0x1800046a7  movups  [rbp+450h+var_480], xmm6
0x1800046ab  call    memset_0
0x1800046b0  mov     r8d, edi; Size
0x1800046b3  mov     [rbp+450h+var_260], bx
0x1800046ba  xor     edx, edx; Val
0x1800046bc  lea     rcx, [rbp+450h+var_25E]; void *
0x1800046c3  movups  [rbp+450h+var_2F0], xmm14
0x1800046cb  movups  [rbp+450h+var_2E0], xmm13
0x1800046d3  movups  [rbp+450h+var_2D0], xmm12
0x1800046db  movups  [rbp+450h+var_2C0], xmm11
0x1800046e3  movups  [rbp+450h+var_2B0], xmm10
0x1800046eb  movups  [rbp+450h+var_2A0], xmm9
0x1800046f3  movups  [rbp+450h+var_290], xmm8
0x1800046fb  movups  [rbp+450h+var_280], xmm7
0x180004702  movups  [rbp+450h+var_270], xmm6
0x180004709  call    memset_0
0x18000470e  test    r12, r12
0x180004711  jz      loc_1800049FD
0x180004717  test    r15, r15
0x18000471a  jz      loc_1800049FD
0x180004720  test    sil, 4
0x180004724  jnz     loc_180004A05
0x18000472a  test    esi, esi
0x18000472c  jz      loc_180004A05
0x180004732  xor     edx, edx; dwFlags
0x180004734  lea     r8, [rsp+550h+var_510]
0x180004739  lea     ecx, [rdx+28h]; dwBytes
0x18000473c  call    WfpMemAlloc
0x180004741  mov     rbx, rax
0x180004744  test    rax, rax
0x180004747  jnz     loc_180004A72
0x18000474d  mov     rdi, [rsp+550h+var_510]
0x180004752  mov     ecx, r14d
0x180004755  movsxd  rax, ecx
0x180004758  inc     ecx
0x18000475a  mov     [rdi+rax*8], r14
0x18000475e  cmp     ecx, 2
0x180004761  jb      short loc_180004755
0x180004763  lea     rcx, ModuleName; "ntdll.dll"
0x18000476a  mov     [r15], r14
0x18000476d  call    cs:__imp_GetModuleHandleA
0x180004774  nop     dword ptr [rax+rax+00h]
0x180004779  mov     rcx, rax; hModule
0x18000477c  lea     rdx, ProcName; "RtlGetPersistedStateLocation"
0x180004783  call    cs:__imp_GetProcAddress
0x18000478a  nop     dword ptr [rax+rax+00h]
0x18000478f  test    rax, rax
0x180004792  jnz     loc_1800049B0
0x180004798  xor     r10d, r10d
0x18000479b  mov     r11d, 104h
0x1800047a1  cmp     r14d, 2
0x1800047a5  jnb     loc_1800049A0
0x1800047ab  mov     ecx, 7FFFFFFEh
0x1800047b0  lea     r8, [rbp+450h+var_2F0]
0x1800047b7  mov     edx, r11d
0x1800047ba  lea     rax, [rsp+550h+pszDest+8]
0x1800047bf  test    rcx, rcx
0x1800047c2  jz      short loc_1800047E3
0x1800047c4  movzx   r9d, word ptr [r8]
0x1800047c8  test    r9w, r9w
0x1800047cc  jz      short loc_1800047E3
0x1800047ce  mov     [rax], r9w
0x1800047d2  add     r8, 2
0x1800047d6  add     rax, 2
0x1800047da  dec     rcx
0x1800047dd  sub     rdx, 1; cchDest
0x1800047e1  jnz     short loc_1800047BF
0x1800047e3  test    rdx, rdx
0x1800047e6  lea     rcx, [rax-2]
0x1800047ea  cmovnz  rcx, rax
0x1800047ee  mov     rax, rdx
0x1800047f1  neg     rax
0x1800047f4  sbb     r8d, r8d
0x1800047f7  not     r8d
0x1800047fa  mov     [rcx], r10w
0x1800047fe  and     r8d, 8007007Ah
0x180004805  test    rdx, rdx
0x180004808  jnz     short loc_180004885
0x18000480a  lea     rdx, aStringcchcopyw; "StringCchCopyW"
0x180004811  call    WfpReportSysErrorAsHResult
0x180004816  mov     rbx, rax
0x180004819  test    rbx, rbx
0x18000481c  jnz     loc_180004A72
0x180004822  mov     rcx, rbx
0x180004825  call    WfpErrorToFwpErr
0x18000482a  mov     rcx, [rbp+450h+var_E0]
0x180004831  xor     rcx, rsp; StackCookie
0x180004834  call    __security_check_cookie
0x180004839  lea     r11, [rsp+550h+var_38]
0x180004841  movaps  xmm6, xmmword ptr [r11-18h]
0x180004846  movaps  xmm7, xmmword ptr [r11-28h]
0x18000484b  movaps  xmm8, xmmword ptr [r11-38h]
0x180004850  movaps  xmm9, xmmword ptr [r11-48h]
0x180004855  movaps  xmm10, xmmword ptr [r11-58h]
0x18000485a  movaps  xmm11, xmmword ptr [r11-68h]
0x18000485f  movaps  xmm12, xmmword ptr [r11-78h]
0x180004864  movaps  xmm13, xmmword ptr [r11-88h]
0x18000486c  movaps  xmm14, xmmword ptr [r11-98h]
0x180004874  mov     rsp, r11
0x180004877  pop     r15
0x180004879  pop     r14
0x18000487b  pop     r13
0x18000487d  pop     r12
0x18000487f  pop     rdi
0x180004880  pop     rsi
0x180004881  pop     rbx
0x180004882  pop     rbp
0x180004883  retn
0x180004885  movsxd  rbx, r14d
0x180004888  lea     r8, FWPP_SUB_REG_APPEND_KEYS
0x18000488f  mov     r8, [r8+rbx*8]; pszSrc
0x180004893  test    r8, r8
0x180004896  jnz     loc_180004A1C
0x18000489c  mov     eax, esi
0x18000489e  and     eax, 3
0x1800048a1  cmp     al, 3
0x1800048a3  jnz     loc_180004A38
0x1800048a9  mov     rdx, r11
0x1800048ac  lea     rax, [rsp+550h+pszDest+8]
0x1800048b1  cmp     [rax], r10w
0x1800048b5  jz      short loc_1800048C1
0x1800048b7  add     rax, 2
0x1800048bb  sub     rdx, 1
0x1800048bf  jnz     short loc_1800048B1
0x1800048c1  mov     rax, rdx
0x1800048c4  mov     rcx, r11
0x1800048c7  neg     rax
0x1800048ca  mov     rax, rdx
0x1800048cd  sbb     r8d, r8d
0x1800048d0  sub     rcx, rdx
0x1800048d3  not     r8d
0x1800048d6  and     r8d, 80070057h
0x1800048dd  neg     rax
0x1800048e0  sbb     r9, r9
0x1800048e3  and     r9, rcx
0x1800048e6  test    rdx, rdx
0x1800048e9  jnz     short loc_1800048F7
0x1800048eb  lea     rdx, aStringcchcatw; "StringCchCatW"
0x1800048f2  jmp     loc_180004811
0x1800048f7  mov     rdx, r11
0x1800048fa  lea     rax, [rsp+550h+pszDest+8]
0x1800048ff  lea     r8, aDynamickeyword_1; "\\DynamicKeywords\\Addresses"
0x180004906  mov     ecx, 7FFFFFFEh
0x18000490b  lea     rax, [rax+r9*2]
0x18000490f  sub     rdx, r9
0x180004912  jz      short loc_180004938
0x180004914  test    rcx, rcx
0x180004917  jz      short loc_180004938
0x180004919  movzx   r9d, word ptr [r8]
0x18000491d  test    r9w, r9w
0x180004921  jz      short loc_180004938
0x180004923  mov     [rax], r9w
0x180004927  add     r8, 2
0x18000492b  add     rax, 2
0x18000492f  dec     rcx
0x180004932  sub     rdx, 1
0x180004936  jnz     short loc_180004914
0x180004938  test    rdx, rdx
0x18000493b  lea     rcx, [rax-2]
0x18000493f  cmovnz  rcx, rax
0x180004943  mov     rax, rdx
0x180004946  neg     rax
0x180004949  sbb     r8d, r8d
0x18000494c  not     r8d
0x18000494f  mov     [rcx], r10w
0x180004953  and     r8d, 8007007Ah
0x18000495a  test    rdx, rdx
0x18000495d  jz      short loc_1800048EB
0x18000495f  lea     rax, [rdi+rbx*8]
0x180004963  mov     r9d, 4
0x180004969  mov     [rsp+550h+var_518], rax
0x18000496e  lea     rdx, [rsp+550h+pszDest+8]
0x180004973  lea     rax, FwppDynamicKeywordOnChange
0x18000497a  mov     [rsp+550h+var_520], rdi
0x18000497f  mov     [rsp+550h+var_528], rax
0x180004984  call    WfpRegNotifyCreate
0x180004989  xor     r10d, r10d
0x18000498c  mov     rbx, rax
0x18000498f  test    rax, rax
0x180004992  jnz     loc_180004A72
0x180004998  inc     r14d
0x18000499b  jmp     loc_18000479B
0x1800049a0  mov     [rdi+10h], r12
0x1800049a4  mov     [rdi+20h], r13
0x1800049a8  mov     [r15], rdi
0x1800049ab  jmp     loc_180004819
0x1800049b0  mov     [rsp+550h+var_520], r14
0x1800049b5  lea     rcx, [rbp+450h+var_2F0]
0x1800049bc  mov     dword ptr [rsp+550h+var_528], 208h
0x1800049c4  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x1800049cb  mov     [rsp+550h+var_530], rcx
0x1800049d0  xor     r9d, r9d
0x1800049d3  lea     rcx, aSharedaccessfi; "SharedAccessFirewallPolicy"
0x1800049da  xor     edx, edx
0x1800049dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049e1  test    eax, eax
0x1800049e3  jz      loc_180004798
0x1800049e9  mov     r8d, eax
0x1800049ec  lea     rdx, aPfuncgetpersis; "pFuncGetPersistedStateLocation"
0x1800049f3  call    WfpReportSysErrorAsNtStatus
0x1800049f8  jmp     loc_180004816
0x1800049fd  mov     r8d, 8032001Ch
0x180004a03  jmp     short loc_180004A0B
0x180004a05  mov     r8d, 57h ; 'W'
0x180004a0b  lea     rdx, aFwpmdynamickey_1; "FwpmDynamicKeywordSubscribe0"
0x180004a12  call    WfpReportSysErrorAsWinError
0x180004a17  jmp     loc_180004816
0x180004a1c  lea     rcx, [rsp+550h+pszDest+8]; pszDest
0x180004a21  call    StringCchCatW
0x180004a26  xor     r10d, r10d
0x180004a29  test    eax, eax
0x180004a2b  js      short loc_180004A6A
0x180004a2d  mov     r11d, 104h
0x180004a33  jmp     loc_18000489C
0x180004a38  test    sil, 1
0x180004a3c  jz      short loc_180004A47
0x180004a3e  lea     r8, aDynamickeyword_0; "\\DynamicKeywords\\Addresses\\AutoResol"...
0x180004a45  jmp     short loc_180004A58
0x180004a47  test    sil, 2
0x180004a4b  jz      loc_18000495F
0x180004a51  lea     r8, pszSrc; "\\DynamicKeywords\\Addresses\\NonAutoRe"...
0x180004a58  lea     rcx, [rsp+550h+pszDest+8]; pszDest
0x180004a5d  call    StringCchCatW
0x180004a62  test    eax, eax
0x180004a64  jns     loc_18000495F
0x180004a6a  mov     r8d, eax
0x180004a6d  jmp     loc_1800048EB
0x180004a72  lea     rcx, [rsp+550h+var_510]
0x180004a77  call    WfpMemFree
0x180004a7c  jmp     loc_180004822
```
