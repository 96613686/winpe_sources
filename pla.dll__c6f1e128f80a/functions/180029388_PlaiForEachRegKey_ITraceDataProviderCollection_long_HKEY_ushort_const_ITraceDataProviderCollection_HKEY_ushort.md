# PlaiForEachRegKey<ITraceDataProviderCollection *,long (*)(HKEY__ *,ushort const *,ITraceDataProviderCollection *)>(HKEY__ *,ushort const *,long (*)(HKEY__ *,ushort const *,ITraceDataProviderCollection *),long (*)(HKEY__ *,ushort const *,ITraceDataProviderCollection *),ITraceDataProviderCollection *)

- ea: `0x180029388`
- end: `0x180029a54`
- name: `??$PlaiForEachRegKey@PEAUITraceDataProviderCollection@@P6AJPEAUHKEY__@@PEBGPEAU1@@Z@@YAJPEAUHKEY__@@PEBGP6AJ01PEAUITraceDataProviderCollection@@@Z32@Z`
- size: `1740`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, __int64, __int64, struct ITraceDataProviderCollection *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180099d3c`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180029388`
- `0x18002b3a0`
- `0x18002b3bc`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180029735`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180029735`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800293ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800293ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029a22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029a22`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800294da`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800294da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800295d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800295d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800295c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800295c5`

## pseudocode

```c
__int64 __fastcall PlaiForEachRegKey<ITraceDataProviderCollection *,long (*)(HKEY__ *,unsigned short const *,ITraceDataProviderCollection *)>(
        HKEY a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        struct ITraceDataProviderCollection *a5)
{
  DWORD v5; // esi
  LSTATUS v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rax
  LSTATUS v10; // eax
  int v11; // eax
  __int64 v12; // rax
  DWORD v13; // eax
  unsigned __int64 v14; // rax
  __int64 v15; // r13
  HANDLE ProcessHeap; // rax
  WCHAR *v17; // rax
  int v18; // edx
  unsigned __int64 v19; // rcx
  WCHAR *v20; // r15
  __int64 v21; // rax
  LSTATUS v22; // eax
  int v23; // eax
  int Provider; // eax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  int v30; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cbMaxValueNameLen; // [rsp+88h] [rbp-78h] BYREF
  DWORD cSubKeys; // [rsp+8Ch] [rbp-74h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  DWORD cValues; // [rsp+98h] [rbp-68h] BYREF
  WCHAR *v38; // [rsp+A0h] [rbp-60h] BYREF
  struct ITraceDataProviderCollection *v39; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v40[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v41[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v42[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v43[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v44[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v45[64]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v46[64]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v5 = 0;
  v39 = a5;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cchName = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v7 = PlaiHResultFromWin32(v6);
  v8 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v31) = 0;
    v30 = v7;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v40, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v40[v9] );
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v30, 4, qword_180147320, 1, &v31, 4, "PlaiForEachRegKey", 18);
    }
    goto LABEL_61;
  }
  v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  v11 = PlaiHResultFromWin32(v10);
  v8 = v11;
  if ( v11 < 0 )
  {
    v30 = 0;
    LODWORD(v31) = v11;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_61;
    }
    PlaiWhoAmI(v41, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v41[v12] );
    goto LABEL_60;
  }
  v13 = cbMaxValueNameLen;
  if ( cbMaxSubKeyLen > cbMaxValueNameLen )
    v13 = cbMaxSubKeyLen;
  if ( v13 + 1 < v13 )
  {
    v8 = -2147024362;
    cchName = -1;
    LODWORD(v31) = -2147024362;
    v30 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_61;
    }
    PlaiWhoAmI(v46, 0x4000000000000800uLL);
    v28 = -1;
    do
      ++v28;
    while ( v46[v28] );
LABEL_60:
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v31, 4, qword_180147320, 1, &v30, 4, "PlaiForEachRegKey", 18);
    goto LABEL_61;
  }
  cchName = v13 + 1;
  v14 = 2LL * (v13 + 1);
  if ( v14 > 0xFFFFFFFF )
  {
    v8 = -2147024362;
    LODWORD(v31) = -2147024362;
    v30 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_61;
    }
    PlaiWhoAmI(v45, 0x4000000000000800uLL);
    v27 = -1;
    do
      ++v27;
    while ( v45[v27] );
    goto LABEL_60;
  }
  v15 = (unsigned int)v14;
  ProcessHeap = GetProcessHeap();
  v17 = (WCHAR *)HeapAlloc(ProcessHeap, 0, (unsigned int)v15);
  v18 = xmmword_180169738;
  v19 = qword_180169748;
  v31 = v15;
  v20 = v17;
  v38 = v17;
  v30 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ALLOC, 4, qword_180147320, 1, &v30, 4, &v38, 8, &v31, 8);
    v19 = qword_180169748;
    v18 = xmmword_180169738;
  }
  if ( !v20 )
  {
    v30 = 0;
    v8 = -2147024882;
    LODWORD(v31) = -2147024882;
    if ( !v18 || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0 || v19 != (v19 & 0x4000000000000800LL) )
      goto LABEL_61;
    PlaiWhoAmI(v42, 0x4000000000000800uLL);
    v21 = -1;
    do
      ++v21;
    while ( v42[v21] );
    goto LABEL_60;
  }
  v8 = 0;
  while ( 1 )
  {
    if ( v5 >= cSubKeys )
      goto LABEL_48;
    cchName = (unsigned int)v15 >> 1;
    v22 = RegEnumKeyExW(hKey, v5, v20, &cchName, 0, 0, 0, 0);
    v23 = PlaiHResultFromWin32(v22);
    v8 = v23;
    if ( v23 < 0 )
      break;
    Provider = PlaiReadProvider(hKey, v20, v39);
    v8 = Provider;
    if ( Provider < 0 )
    {
      LODWORD(v31) = Provider;
      v30 = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v43, 0x4000000000000800uLL);
        v25 = -1;
        do
          ++v25;
        while ( v43[v25] );
LABEL_47:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v31,
          4,
          qword_180147320,
          1,
          &v30,
          4,
          "PlaiForEachRegKey",
          18);
        goto LABEL_48;
      }
      goto LABEL_48;
    }
    if ( Provider == 1 )
      goto LABEL_48;
    ++v5;
  }
  LODWORD(v31) = v23;
  v30 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v44, 0x4000000000000800uLL);
    v26 = -1;
    do
      ++v26;
    while ( v44[v26] );
    goto LABEL_47;
  }
LABEL_48:
  PlaiFree(v20, 1);
LABEL_61:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180029388  mov     [rsp-8+arg_10], rbx
0x18002938d  push    rbp
0x18002938e  push    rsi
0x18002938f  push    rdi
0x180029390  push    r12
0x180029392  push    r13
0x180029394  push    r14
0x180029396  push    r15
0x180029398  lea     rbp, [rsp-340h]
0x1800293a0  sub     rsp, 440h
0x1800293a7  mov     rax, cs:__security_cookie
0x1800293ae  xor     rax, rsp
0x1800293b1  mov     [rbp+370h+var_40], rax
0x1800293b8  mov     rax, [rbp+370h+arg_20]
0x1800293bf  xor     esi, esi
0x1800293c1  mov     [rbp+370h+var_3C8], rax
0x1800293c5  mov     r9d, 20019h; samDesired
0x1800293cb  lea     rax, [rbp+370h+hKey]
0x1800293cf  mov     [rbp+370h+cSubKeys], esi
0x1800293d2  xor     r8d, r8d; ulOptions
0x1800293d5  mov     [rsp+470h+phkResult], rax; phkResult
0x1800293da  mov     [rbp+370h+cbMaxSubKeyLen], esi
0x1800293dd  mov     [rbp+370h+cValues], esi
0x1800293e0  mov     [rbp+370h+cbMaxValueNameLen], esi
0x1800293e3  mov     [rbp+370h+cchName], esi
0x1800293e6  mov     [rbp+370h+hKey], rsi
0x1800293ea  call    cs:__imp_RegOpenKeyExW
0x1800293f0  mov     ecx, eax; unsigned int
0x1800293f2  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800293f7  mov     ebx, eax
0x1800293f9  test    eax, eax
0x1800293fb  jns     loc_180029496
0x180029401  cmp     dword ptr cs:xmmword_180169738, esi
0x180029407  mov     dword ptr [rsp+470h+var_3F8], esi
0x18002940b  mov     [rsp+470h+var_400], eax
0x18002940f  jz      loc_180029A19
0x180029415  mov     rdx, 4000000000000800h; unsigned __int64
0x18002941f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180029426  jz      loc_180029A19
0x18002942c  mov     rax, cs:qword_180169748
0x180029433  and     rax, rdx
0x180029436  cmp     cs:qword_180169748, rax
0x18002943d  jnz     loc_180029A19
0x180029443  lea     rcx, [rbp+370h+var_3C0]; unsigned __int16 *
0x180029447  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002944c  lea     rcx, [rbp+370h+var_3C0]
0x180029450  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029454  inc     rax
0x180029457  cmp     [rcx+rax*2], si
0x18002945b  jnz     short loc_180029454
0x18002945d  lea     ecx, [rax+rax]
0x180029460  lea     rax, [rbp+370h+var_3C0]
0x180029464  add     rcx, 2
0x180029468  mov     [rsp+470h+var_410], rcx
0x18002946d  lea     r9, [rsp+470h+var_400]
0x180029472  mov     [rsp+470h+lpftLastWriteTime], rax
0x180029477  lea     rax, aPlaiforeachreg; "PlaiForEachRegKey"
0x18002947e  mov     [rsp+470h+lpcbSecurityDescriptor], 12h
0x180029487  mov     [rsp+470h+lpcbMaxValueLen], rax
0x18002948c  lea     rax, [rsp+470h+var_3F8]
0x180029491  jmp     loc_1800299D6
0x180029496  mov     rcx, [rbp+370h+hKey]; hKey
0x18002949a  lea     rax, [rbp+370h+cbMaxValueNameLen]
0x18002949e  mov     [rsp+470h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800294a3  xor     r9d, r9d; lpReserved
0x1800294a6  mov     [rsp+470h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800294ab  xor     r8d, r8d; lpcchClass
0x1800294ae  mov     [rsp+470h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1800294b3  xor     edx, edx; lpClass
0x1800294b5  mov     [rsp+470h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800294ba  lea     rax, [rbp+370h+cValues]
0x1800294be  mov     [rsp+470h+lpcValues], rax; lpcValues
0x1800294c3  lea     rax, [rbp+370h+cbMaxSubKeyLen]
0x1800294c7  mov     [rsp+470h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800294cc  mov     [rsp+470h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800294d1  lea     rax, [rbp+370h+cSubKeys]
0x1800294d5  mov     [rsp+470h+phkResult], rax; lpcSubKeys
0x1800294da  call    cs:__imp_RegQueryInfoKeyW
0x1800294e0  mov     ecx, eax; unsigned int
0x1800294e2  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800294e7  mov     ebx, eax
0x1800294e9  test    eax, eax
0x1800294eb  jns     loc_180029597
0x1800294f1  cmp     dword ptr cs:xmmword_180169738, esi
0x1800294f7  mov     [rsp+470h+var_400], esi
0x1800294fb  mov     dword ptr [rsp+470h+var_3F8], eax
0x1800294ff  jz      loc_180029A19
0x180029505  mov     rdx, 4000000000000800h; unsigned __int64
0x18002950f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180029516  jz      loc_180029A19
0x18002951c  mov     rax, cs:qword_180169748
0x180029523  and     rax, rdx
0x180029526  cmp     cs:qword_180169748, rax
0x18002952d  jnz     loc_180029A19
0x180029533  lea     rcx, [rbp+370h+var_340]; unsigned __int16 *
0x180029537  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002953c  lea     rcx, [rbp+370h+var_340]
0x180029540  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029544  inc     rax
0x180029547  cmp     [rcx+rax*2], si
0x18002954b  jnz     short loc_180029544
0x18002954d  lea     ecx, [rax+rax]
0x180029550  lea     rax, [rbp+370h+var_340]
0x180029554  mov     r14d, 4
0x18002955a  lea     r12, qword_180147320
0x180029561  lea     edi, [r14-3]
0x180029565  add     rcx, 2
0x180029569  lea     r9, [rsp+470h+var_3F8]
0x18002956e  mov     [rsp+470h+var_410], rcx
0x180029573  mov     [rsp+470h+lpftLastWriteTime], rax
0x180029578  lea     rax, aPlaiforeachreg; "PlaiForEachRegKey"
0x18002957f  mov     [rsp+470h+lpcbSecurityDescriptor], 12h
0x180029588  mov     [rsp+470h+lpcbMaxValueLen], rax
0x18002958d  lea     rax, [rsp+470h+var_400]
0x180029592  jmp     loc_1800299E7
0x180029597  mov     eax, [rbp+370h+cbMaxValueNameLen]
0x18002959a  cmp     [rbp+370h+cbMaxSubKeyLen], eax
0x18002959d  cmova   eax, [rbp+370h+cbMaxSubKeyLen]
0x1800295a1  lea     ecx, [rax+1]
0x1800295a4  cmp     ecx, eax
0x1800295a6  jb      loc_180029930
0x1800295ac  mov     eax, ecx
0x1800295ae  mov     [rbp+370h+cchName], ecx
0x1800295b1  add     rax, rax
0x1800295b4  mov     ecx, 0FFFFFFFFh
0x1800295b9  cmp     rax, rcx
0x1800295bc  ja      loc_1800298BA
0x1800295c2  mov     r13d, eax
0x1800295c5  call    cs:__imp_GetProcessHeap
0x1800295cb  mov     r8d, r13d; dwBytes
0x1800295ce  xor     edx, edx; dwFlags
0x1800295d0  mov     rcx, rax; hHeap
0x1800295d3  call    cs:__imp_HeapAlloc
0x1800295d9  mov     edx, dword ptr cs:xmmword_180169738
0x1800295df  lea     r12, qword_180147320
0x1800295e6  mov     rcx, cs:qword_180169748
0x1800295ed  mov     edi, 1
0x1800295f2  mov     [rsp+470h+var_3F8], r13
0x1800295f7  mov     r15, rax
0x1800295fa  mov     [rbp+370h+var_3D0], rax
0x1800295fe  mov     [rsp+470h+var_400], esi
0x180029602  lea     r14d, [rdi+3]
0x180029606  test    edx, edx
0x180029608  jz      short loc_180029682
0x18002960a  mov     r8, 4000000000000200h
0x180029614  test    qword ptr cs:xmmword_180169738+8, r8
0x18002961b  jz      short loc_180029682
0x18002961d  mov     rax, rcx
0x180029620  and     rax, r8
0x180029623  cmp     rcx, rax
0x180029626  jnz     short loc_180029682
0x180029628  lea     ecx, [rdi+7]
0x18002962b  mov     r9, r12
0x18002962e  mov     [rsp+470h+lpcbSecurityDescriptor], rcx
0x180029633  lea     rax, [rsp+470h+var_3F8]
0x180029638  mov     [rsp+470h+lpcbMaxValueLen], rax
0x18002963d  lea     rdx, PLA_EVENT_ALLOC
0x180029644  mov     [rsp+470h+lpcbMaxValueNameLen], rcx
0x180029649  lea     rax, [rbp+370h+var_3D0]
0x18002964d  mov     [rsp+470h+lpcValues], rax
0x180029652  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180029659  lea     rax, [rsp+470h+var_400]
0x18002965e  mov     [rsp+470h+lpcbMaxClassLen], r14
0x180029663  mov     [rsp+470h+lpcbMaxSubKeyLen], rax
0x180029668  mov     r8d, r14d
0x18002966b  mov     [rsp+470h+phkResult], rdi
0x180029670  call    EventingWriteEvent
0x180029675  mov     rcx, cs:qword_180169748
0x18002967c  mov     edx, dword ptr cs:xmmword_180169738
0x180029682  test    r15, r15
0x180029685  jnz     short loc_1800296F1
0x180029687  mov     [rsp+470h+var_400], esi
0x18002968b  mov     ebx, 8007000Eh
0x180029690  mov     dword ptr [rsp+470h+var_3F8], ebx
0x180029694  test    edx, edx
0x180029696  jz      loc_180029A19
0x18002969c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800296a6  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800296ad  jz      loc_180029A19
0x1800296b3  mov     rax, rcx
0x1800296b6  and     rax, rdx
0x1800296b9  cmp     rcx, rax
0x1800296bc  jnz     loc_180029A19
0x1800296c2  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x1800296c9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800296ce  lea     rcx, [rbp+370h+var_2C0]
0x1800296d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800296d9  inc     rax
0x1800296dc  cmp     [rcx+rax*2], si
0x1800296e0  jnz     short loc_1800296D9
0x1800296e2  lea     ecx, [rax+rax]
0x1800296e5  lea     rax, [rbp+370h+var_2C0]
0x1800296ec  jmp     loc_180029565
0x1800296f1  xor     ebx, ebx
0x1800296f3  cmp     esi, [rbp+370h+cSubKeys]
0x1800296f6  jnb     loc_1800298AB
0x1800296fc  mov     rcx, [rbp+370h+hKey]; hKey
0x180029700  lea     r9, [rbp+370h+cchName]; lpcchName
0x180029704  mov     [rsp+470h+lpcValues], 0; lpftLastWriteTime
0x18002970d  mov     eax, r13d
0x180029710  shr     eax, 1
0x180029712  mov     r8, r15; lpName
0x180029715  mov     [rsp+470h+lpcbMaxClassLen], 0; lpcchClass
0x18002971e  mov     edx, esi; dwIndex
0x180029720  mov     [rsp+470h+lpcbMaxSubKeyLen], 0; lpClass
0x180029729  mov     [rbp+370h+cchName], eax
0x18002972c  mov     [rsp+470h+phkResult], 0; lpReserved
0x180029735  call    cs:__imp_RegEnumKeyExW
0x18002973b  mov     ecx, eax; unsigned int
0x18002973d  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180029742  mov     ebx, eax
0x180029744  test    eax, eax
0x180029746  js      loc_1800297DE
0x18002974c  mov     r8, [rbp+370h+var_3C8]; struct ITraceDataProviderCollection *
0x180029750  mov     rdx, r15; unsigned __int16 *
0x180029753  mov     rcx, [rbp+370h+hKey]; HKEY
0x180029757  call    ?PlaiReadProvider@@YAJPEAUHKEY__@@PEBGPEAUITraceDataProviderCollection@@@Z; PlaiReadProvider(HKEY__ *,ushort const *,ITraceDataProviderCollection *)
0x18002975c  mov     ebx, eax
0x18002975e  test    eax, eax
0x180029760  js      short loc_18002976E
0x180029762  cmp     eax, edi
0x180029764  jz      loc_1800298AB
0x18002976a  add     esi, edi
0x18002976c  jmp     short loc_1800296F3
0x18002976e  xor     esi, esi
0x180029770  mov     dword ptr [rsp+470h+var_3F8], eax
0x180029774  cmp     dword ptr cs:xmmword_180169738, esi
0x18002977a  mov     [rsp+470h+var_400], esi
0x18002977e  jz      loc_1800298AB
0x180029784  mov     rdx, 4000000000000800h; unsigned __int64
0x18002978e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180029795  jz      loc_1800298AB
0x18002979b  mov     rax, cs:qword_180169748
0x1800297a2  and     rax, rdx
0x1800297a5  cmp     cs:qword_180169748, rax
0x1800297ac  jnz     loc_1800298AB
0x1800297b2  lea     rcx, [rbp+370h+var_240]; unsigned __int16 *
0x1800297b9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800297be  lea     rcx, [rbp+370h+var_240]
0x1800297c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800297c9  inc     rax
0x1800297cc  cmp     [rcx+rax*2], si
0x1800297d0  jnz     short loc_1800297C9
0x1800297d2  lea     ecx, [rax+rax]
0x1800297d5  lea     rax, [rbp+370h+var_240]
0x1800297dc  jmp     short loc_18002984C
0x1800297de  xor     esi, esi
0x1800297e0  mov     dword ptr [rsp+470h+var_3F8], eax
0x1800297e4  cmp     dword ptr cs:xmmword_180169738, esi
0x1800297ea  mov     [rsp+470h+var_400], esi
0x1800297ee  jz      loc_1800298AB
0x1800297f4  mov     rdx, 4000000000000800h; unsigned __int64
0x1800297fe  test    qword ptr cs:xmmword_180169738+8, rdx
0x180029805  jz      loc_1800298AB
0x18002980b  mov     rax, cs:qword_180169748
0x180029812  and     rax, rdx
0x180029815  cmp     cs:qword_180169748, rax
0x18002981c  jnz     loc_1800298AB
0x180029822  lea     rcx, [rbp+370h+var_1C0]; unsigned __int16 *
0x180029829  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002982e  lea     rcx, [rbp+370h+var_1C0]
0x180029835  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029839  inc     rax
0x18002983c  cmp     [rcx+rax*2], si
0x180029840  jnz     short loc_180029839
0x180029842  lea     ecx, [rax+rax]
0x180029845  lea     rax, [rbp+370h+var_1C0]
0x18002984c  add     rcx, 2
0x180029850  lea     r9, [rsp+470h+var_3F8]
0x180029855  mov     [rsp+470h+var_410], rcx
0x18002985a  lea     rdx, PLA_EVENT_ERROR
0x180029861  mov     [rsp+470h+lpftLastWriteTime], rax
0x180029866  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18002986d  mov     [rsp+470h+lpcbSecurityDescriptor], 12h
0x180029876  lea     rax, aPlaiforeachreg; "PlaiForEachRegKey"
0x18002987d  mov     [rsp+470h+lpcbMaxValueLen], rax
0x180029882  mov     r8d, 5
0x180029888  mov     [rsp+470h+lpcbMaxValueNameLen], r14
0x18002988d  lea     rax, [rsp+470h+var_400]
0x180029892  mov     [rsp+470h+lpcValues], rax
0x180029897  mov     [rsp+470h+lpcbMaxClassLen], rdi
0x18002989c  mov     [rsp+470h+lpcbMaxSubKeyLen], r12
0x1800298a1  mov     [rsp+470h+phkResult], r14
0x1800298a6  call    EventingWriteEvent
0x1800298ab  mov     edx, edi; int
0x1800298ad  mov     rcx, r15; lpMem
0x1800298b0  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x1800298b5  jmp     loc_180029A19
0x1800298ba  cmp     dword ptr cs:xmmword_180169738, esi
0x1800298c0  mov     ebx, 80070216h
0x1800298c5  mov     dword ptr [rsp+470h+var_3F8], ebx
0x1800298c9  mov     [rsp+470h+var_400], esi
0x1800298cd  jz      loc_180029A19
0x1800298d3  mov     rdx, 4000000000000800h; unsigned __int64
0x1800298dd  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800298e4  jz      loc_180029A19
0x1800298ea  mov     rax, cs:qword_180169748
0x1800298f1  and     rax, rdx
0x1800298f4  cmp     cs:qword_180169748, rax
0x1800298fb  jnz     loc_180029A19
  ... truncated ...
```
