# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180028530`
- end: `0x1800289b2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `1154`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180022d20`
- `0x180023100`

## callees

- `0x18001e1d0`
- `0x180024c00`
- `0x180027a30`
- `0x180027a50`
- `0x180028530`
- `0x180029320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180028635`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800287f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180028635`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800287f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028651`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028734`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028651`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028734`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180028691`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800286b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800286e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180028710`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180028691`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800286b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800286e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180028710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002871e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002871e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002882d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002883e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028856`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028879`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002882d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002883e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028856`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028879`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288e2`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rbp
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v10; // rcx
  WCHAR *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  const wchar_t *v14; // r8
  bool v15; // zf
  __int64 v16; // rax
  __int64 v17; // rcx
  WCHAR *v18; // rdx
  WCHAR *v19; // rcx
  HANDLE v20; // rax
  void *v21; // rdi
  DWORD v22; // eax
  unsigned int v23; // r8d
  const char *v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rdx
  DWORD v27; // eax
  unsigned int LastError; // ebx
  unsigned int v29; // r8d
  int v30; // r14d
  __int64 v31; // rcx
  WCHAR *v32; // rax
  WCHAR *v33; // rax
  const wchar_t *v34; // rdx
  __int64 v35; // rsi
  WCHAR *v36; // rdx
  HANDLE v37; // rax
  unsigned int v38; // r8d
  const char *v39; // r9
  void *v40; // rbx
  int ValueFromSemaphore; // eax
  unsigned int v42; // r8d
  unsigned int v43; // esi
  unsigned int v44; // r8d
  const char *v45; // r9
  unsigned int v46; // r8d
  const char *v47; // r9
  unsigned int v49; // r8d
  const char *v50; // r9
  unsigned int v51; // r8d
  const char *v52; // r9
  unsigned int v53; // r8d
  const char *v54; // r9
  unsigned int v55; // r8d
  const char *v56; // r9
  unsigned int v57; // r8d
  const char *v58; // r9
  int v59; // [rsp+20h] [rbp-258h] BYREF
  int PreviousCount; // [rsp+24h] [rbp-254h] BYREF
  int v61; // [rsp+28h] [rbp-250h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v10 = v4 - 1;
  if ( v7 )
    v10 = v4;
  v11 = Name;
  *v10 = 0;
  v12 = 260;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v12;
  }
  while ( v12 );
  v13 = 260 - v12;
  if ( v12 )
  {
    v14 = L"_p0";
    v16 = v12;
    v15 = v13 == 260;
    v17 = 2147483646;
    v18 = &Name[v13];
    if ( !v15 )
    {
      do
      {
        if ( !v17 )
          break;
        if ( !*v14 )
          break;
        *v18++ = *v14++;
        --v17;
        --v16;
      }
      while ( v16 );
    }
    v19 = v18 - 1;
    if ( v16 )
      v19 = v18;
    *v19 = 0;
  }
  v20 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v20;
  if ( !v20 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v57, v58);
    return 0;
  }
  v59 = 0;
  v22 = WaitForSingleObject(v20, 0);
  if ( v22 == -1 )
  {
    v25 = 156;
    goto LABEL_38;
  }
  if ( v22 && v22 != 258 )
  {
    v26 = 157;
LABEL_65:
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v26, v23, (const char *)0x8000FFFFLL, v59);
    goto LABEL_66;
  }
  PreviousCount = 0;
  if ( !v22 )
  {
    if ( !ReleaseSemaphore(v21, 1, &PreviousCount) )
    {
      v25 = 165;
      goto LABEL_38;
    }
    ++PreviousCount;
    if ( ReleaseSemaphore(v21, 1, 0) || GetLastError() != 298 )
    {
      v26 = 170;
      goto LABEL_65;
    }
LABEL_42:
    v30 = PreviousCount;
    goto LABEL_43;
  }
  v61 = 0;
  if ( ReleaseSemaphore(v21, 1, &v61) )
  {
    if ( v61 )
    {
      v26 = 181;
      goto LABEL_65;
    }
    if ( ReleaseSemaphore(v21, 1, 0) || GetLastError() != 298 )
    {
      v26 = 184;
      goto LABEL_65;
    }
    v27 = WaitForSingleObject(v21, 0);
    if ( v27 != -1 )
    {
      if ( v27 )
      {
        v26 = 188;
        goto LABEL_65;
      }
      goto LABEL_42;
    }
    v25 = 187;
  }
  else
  {
    v25 = 180;
  }
LABEL_38:
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)v25, v23, v24);
  v30 = 0;
  if ( (LastError & 0x80000000) != 0 )
  {
LABEL_66:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v29, (const char *)LastError, v59);
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v55, v56);
    return LastError;
  }
LABEL_43:
  v31 = 260;
  v32 = Name;
  do
  {
    if ( !*v32 )
      break;
    ++v32;
    --v31;
  }
  while ( v31 );
  if ( v31 )
  {
    v33 = &Name[260 - v31];
    v34 = L"h";
    v35 = v31;
    do
    {
      if ( !v5 )
        break;
      if ( !*v34 )
        break;
      *v33++ = *v34++;
      --v5;
      --v35;
    }
    while ( v35 );
    v36 = v33 - 1;
    if ( v35 )
      v36 = v33;
    *v36 = 0;
  }
  v37 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v40 = v37;
  if ( !v37 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v38, v39);
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v53, v54);
    return LastError;
  }
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v37, &v59);
  v43 = ValueFromSemaphore;
  if ( ValueFromSemaphore >= 0 )
  {
    if ( !CloseHandle(v40) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v49, v50);
    *a3 = v30 | (unsigned __int64)((__int64)v59 << 31);
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v51, v52);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v42, (const char *)(unsigned int)ValueFromSemaphore, v59);
  if ( !CloseHandle(v40) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v44, v45);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v46, v47);
  return v43;
}

```

## disassembly

```asm
0x180028530  push    rbp
0x180028532  push    rsi
0x180028533  push    rdi
0x180028534  push    r12
0x180028536  push    r15
0x180028538  sub     rsp, 250h
0x18002853f  mov     rax, cs:__security_cookie
0x180028546  xor     rax, rsp
0x180028549  mov     [rsp+278h+var_38], rax
0x180028551  xor     r12d, r12d
0x180028554  lea     rax, [rsp+278h+Name]
0x180028559  mov     ebp, 7FFFFFFEh
0x18002855e  mov     [r8], r12
0x180028561  mov     esi, 104h
0x180028566  mov     edx, ebp
0x180028568  mov     r9d, esi
0x18002856b  mov     r15, r8
0x18002856e  mov     r10, rcx
0x180028571  test    rdx, rdx
0x180028574  jz      short loc_180028593
0x180028576  movzx   ecx, word ptr [r10]
0x18002857a  test    cx, cx
0x18002857d  jz      short loc_180028593
0x18002857f  mov     [rax], cx
0x180028582  add     r10, 2
0x180028586  add     rax, 2
0x18002858a  dec     rdx
0x18002858d  sub     r9, 1
0x180028591  jnz     short loc_180028571
0x180028593  lea     rcx, [rax-2]
0x180028597  test    r9, r9
0x18002859a  cmovnz  rcx, rax
0x18002859e  lea     rax, [rsp+278h+Name]
0x1800285a3  mov     [rcx], r12w
0x1800285a7  mov     rcx, rsi
0x1800285aa  nop     word ptr [rax+rax+00h]
0x1800285b0  cmp     [rax], r12w
0x1800285b4  jz      short loc_1800285C0
0x1800285b6  add     rax, 2
0x1800285ba  sub     rcx, 1
0x1800285be  jnz     short loc_1800285B0
0x1800285c0  mov     rdx, rsi
0x1800285c3  sub     rdx, rcx
0x1800285c6  test    rcx, rcx
0x1800285c9  cmovz   rdx, r12
0x1800285cd  jz      short loc_180028619
0x1800285cf  mov     rax, rsi
0x1800285d2  lea     r8, aP0; "_p0"
0x1800285d9  sub     rax, rdx
0x1800285dc  mov     rcx, rbp
0x1800285df  lea     rdx, [rsp+rdx*2+278h+Name]
0x1800285e4  jz      short loc_18002860A
0x1800285e6  test    rcx, rcx
0x1800285e9  jz      short loc_18002860A
0x1800285eb  movzx   r9d, word ptr [r8]
0x1800285ef  test    r9w, r9w
0x1800285f3  jz      short loc_18002860A
0x1800285f5  mov     [rdx], r9w
0x1800285f9  add     r8, 2
0x1800285fd  add     rdx, 2
0x180028601  dec     rcx
0x180028604  sub     rax, 1
0x180028608  jnz     short loc_1800285E6
0x18002860a  test    rax, rax
0x18002860d  lea     rcx, [rdx-2]
0x180028611  cmovnz  rcx, rdx
0x180028615  mov     [rcx], r12w
0x180028619  mov     [rsp+278h+arg_0], rbx
0x180028621  lea     r8, [rsp+278h+Name]; lpName
0x180028626  xor     edx, edx; bInheritHandle
0x180028628  mov     [rsp+278h+arg_8], r14
0x180028630  mov     ecx, 1F0003h; dwDesiredAccess
0x180028635  call    cs:__imp_OpenSemaphoreW
0x18002863b  mov     rdi, rax
0x18002863e  test    rax, rax
0x180028641  jz      loc_1800288F0
0x180028647  xor     edx, edx; dwMilliseconds
0x180028649  mov     [rsp+278h+var_258], r12d; int
0x18002864e  mov     rcx, rax; hHandle
0x180028651  call    cs:__imp_WaitForSingleObject
0x180028657  cmp     eax, 0FFFFFFFFh
0x18002865a  jnz     short loc_180028666
0x18002865c  mov     edx, 9Ch
0x180028661  jmp     loc_180028744
0x180028666  test    eax, eax
0x180028668  jz      short loc_18002867B
0x18002866a  cmp     eax, 102h
0x18002866f  jz      short loc_18002867B
0x180028671  mov     edx, 9Dh
0x180028676  jmp     loc_1800288B5
0x18002867b  mov     [rsp+278h+PreviousCount], r12d
0x180028680  mov     edx, 1; lReleaseCount
0x180028685  mov     rcx, rdi; hSemaphore
0x180028688  test    eax, eax
0x18002868a  jnz     short loc_1800286D9
0x18002868c  lea     r8, [rsp+278h+PreviousCount]; lpPreviousCount
0x180028691  call    cs:__imp_ReleaseSemaphore
0x180028697  test    eax, eax
0x180028699  jnz     short loc_1800286A5
0x18002869b  mov     edx, 0A5h
0x1800286a0  jmp     loc_180028744
0x1800286a5  inc     [rsp+278h+PreviousCount]
0x1800286a9  xor     r8d, r8d; lpPreviousCount
0x1800286ac  mov     edx, 1; lReleaseCount
0x1800286b1  mov     rcx, rdi; hSemaphore
0x1800286b4  call    cs:__imp_ReleaseSemaphore
0x1800286ba  test    eax, eax
0x1800286bc  jnz     short loc_1800286CF
0x1800286be  call    cs:__imp_GetLastError
0x1800286c4  cmp     eax, 12Ah
0x1800286c9  jz      loc_18002876D
0x1800286cf  mov     edx, 0AAh
0x1800286d4  jmp     loc_1800288B5
0x1800286d9  lea     r8, [rsp+278h+var_250]; lpPreviousCount
0x1800286de  mov     [rsp+278h+var_250], r12d
0x1800286e3  call    cs:__imp_ReleaseSemaphore
0x1800286e9  test    eax, eax
0x1800286eb  jnz     short loc_1800286F4
0x1800286ed  mov     edx, 0B4h
0x1800286f2  jmp     short loc_180028744
0x1800286f4  cmp     [rsp+278h+var_250], r12d
0x1800286f9  jz      short loc_180028705
0x1800286fb  mov     edx, 0B5h
0x180028700  jmp     loc_1800288B5
0x180028705  xor     r8d, r8d; lpPreviousCount
0x180028708  mov     edx, 1; lReleaseCount
0x18002870d  mov     rcx, rdi; hSemaphore
0x180028710  call    cs:__imp_ReleaseSemaphore
0x180028716  test    eax, eax
0x180028718  jnz     loc_1800288B0
0x18002871e  call    cs:__imp_GetLastError
0x180028724  cmp     eax, 12Ah
0x180028729  jnz     loc_1800288B0
0x18002872f  xor     edx, edx; dwMilliseconds
0x180028731  mov     rcx, rdi; hHandle
0x180028734  call    cs:__imp_WaitForSingleObject
0x18002873a  cmp     eax, 0FFFFFFFFh
0x18002873d  jnz     short loc_18002875F
0x18002873f  mov     edx, 0BBh; void *
0x180028744  mov     rcx, [rsp+278h]; this
0x18002874c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028751  mov     ebx, eax
0x180028753  mov     r14d, r12d
0x180028756  test    eax, eax
0x180028758  jns     short loc_180028772
0x18002875a  jmp     loc_1800288CA
0x18002875f  test    eax, eax
0x180028761  jz      short loc_18002876D
0x180028763  mov     edx, 0BCh
0x180028768  jmp     loc_1800288B5
0x18002876d  mov     r14d, [rsp+278h+PreviousCount]
0x180028772  mov     rcx, rsi
0x180028775  lea     rax, [rsp+278h+Name]
0x18002877a  nop     word ptr [rax+rax+00h]
0x180028780  cmp     [rax], r12w
0x180028784  jz      short loc_180028790
0x180028786  add     rax, 2
0x18002878a  sub     rcx, 1
0x18002878e  jnz     short loc_180028780
0x180028790  mov     r8, rsi
0x180028793  sub     r8, rcx
0x180028796  test    rcx, rcx
0x180028799  cmovz   r8, r12
0x18002879d  jz      short loc_1800287E4
0x18002879f  lea     rax, [rsp+278h+Name]
0x1800287a4  lea     rax, [rax+r8*2]
0x1800287a8  lea     rdx, asc_180034568; "h"
0x1800287af  sub     rsi, r8
0x1800287b2  jz      short loc_1800287D5
0x1800287b4  test    rbp, rbp
0x1800287b7  jz      short loc_1800287D5
0x1800287b9  movzx   ecx, word ptr [rdx]
0x1800287bc  test    cx, cx
0x1800287bf  jz      short loc_1800287D5
0x1800287c1  mov     [rax], cx
0x1800287c4  add     rdx, 2
0x1800287c8  add     rax, 2
0x1800287cc  dec     rbp
0x1800287cf  sub     rsi, 1
0x1800287d3  jnz     short loc_1800287B4
0x1800287d5  test    rsi, rsi
0x1800287d8  lea     rdx, [rax-2]
0x1800287dc  cmovnz  rdx, rax
0x1800287e0  mov     [rdx], r12w
0x1800287e4  lea     r8, [rsp+278h+Name]; lpName
0x1800287e9  xor     edx, edx; bInheritHandle
0x1800287eb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800287f0  call    cs:__imp_OpenSemaphoreW
0x1800287f6  mov     rbx, rax
0x1800287f9  test    rax, rax
0x1800287fc  jz      loc_180028889
0x180028802  lea     rdx, [rsp+278h+var_258]; int *
0x180028807  mov     rcx, rax; hHandle
0x18002880a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002880f  mov     esi, eax
0x180028811  test    eax, eax
0x180028813  jns     short loc_180028853
0x180028815  mov     rcx, [rsp+278h]; this
0x18002881d  mov     r9d, eax; char *
0x180028820  mov     edx, 0DEh; void *
0x180028825  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002882a  mov     rcx, rbx; hObject
0x18002882d  call    cs:__imp_CloseHandle
0x180028833  test    eax, eax
0x180028835  jz      loc_180028979
0x18002883b  mov     rcx, rdi; hObject
0x18002883e  call    cs:__imp_CloseHandle
0x180028844  test    eax, eax
0x180028846  jz      loc_18002898C
0x18002884c  mov     eax, esi
0x18002884e  jmp     loc_180028911
0x180028853  mov     rcx, rbx; hObject
0x180028856  call    cs:__imp_CloseHandle
0x18002885c  test    eax, eax
0x18002885e  jz      loc_18002899F
0x180028864  movsxd  rcx, [rsp+278h+var_258]
0x180028869  shl     rcx, 1Fh
0x18002886d  movsxd  rax, r14d
0x180028870  or      rcx, rax
0x180028873  mov     [r15], rcx
0x180028876  mov     rcx, rdi; hObject
0x180028879  call    cs:__imp_CloseHandle
0x18002887f  test    eax, eax
0x180028881  jz      loc_180028953
0x180028887  jmp     short loc_1800288FB
0x180028889  mov     rcx, [rsp+278h]; this
0x180028891  mov     edx, 0DCh; void *
0x180028896  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002889b  mov     rcx, rdi; hObject
0x18002889e  mov     ebx, eax
0x1800288a0  call    cs:__imp_CloseHandle
0x1800288a6  test    eax, eax
0x1800288a8  jz      loc_180028966
0x1800288ae  jmp     short loc_1800288EC
0x1800288b0  mov     edx, 0B8h; void *
0x1800288b5  mov     rcx, [rsp+278h]; this
0x1800288bd  mov     ebx, 8000FFFFh
0x1800288c2  mov     r9d, ebx; char *
0x1800288c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800288ca  mov     rcx, [rsp+278h]; this
0x1800288d2  mov     r9d, ebx; char *
0x1800288d5  mov     edx, 0D6h; void *
0x1800288da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800288df  mov     rcx, rdi; hObject
0x1800288e2  call    cs:__imp_CloseHandle
0x1800288e8  test    eax, eax
0x1800288ea  jz      short loc_180028940
0x1800288ec  mov     eax, ebx
0x1800288ee  jmp     short loc_180028911
0x1800288f0  call    cs:__imp_GetLastError
0x1800288f6  cmp     eax, 2
0x1800288f9  jnz     short loc_1800288FF
0x1800288fb  xor     eax, eax
0x1800288fd  jmp     short loc_180028911
0x1800288ff  mov     rcx, [rsp+278h]; this
0x180028907  mov     edx, 0D0h; void *
0x18002890c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028911  mov     r14, [rsp+278h+arg_8]
0x180028919  mov     rbx, [rsp+278h+arg_0]
0x180028921  mov     rcx, [rsp+278h+var_38]
0x180028929  xor     rcx, rsp; StackCookie
0x18002892c  call    __security_check_cookie
0x180028931  add     rsp, 250h
0x180028938  pop     r15
0x18002893a  pop     r12
0x18002893c  pop     rdi
0x18002893d  pop     rsi
0x18002893e  pop     rbp
0x18002893f  retn
0x180028940  mov     rcx, [rsp+278h]; this
0x180028948  mov     edx, 0A0Bh; void *
0x18002894d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028953  mov     rcx, [rsp+278h]; this
0x18002895b  mov     edx, 0A0Bh; void *
0x180028960  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028966  mov     rcx, [rsp+278h]; this
0x18002896e  mov     edx, 0A0Bh; void *
0x180028973  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028979  mov     rcx, [rsp+278h]; this
0x180028981  mov     edx, 0A0Bh; void *
0x180028986  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002898c  mov     rcx, [rsp+278h]; this
0x180028994  mov     edx, 0A0Bh; void *
0x180028999  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002899f  mov     rcx, [rsp+278h]; this
0x1800289a7  mov     edx, 0A0Bh; void *
0x1800289ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
