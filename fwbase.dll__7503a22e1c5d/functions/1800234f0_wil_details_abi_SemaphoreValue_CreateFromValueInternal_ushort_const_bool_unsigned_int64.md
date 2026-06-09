# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800234f0`
- end: `0x180023815`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `805`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180022d20`
- `0x180023100`

## callees

- `0x18001e1d0`
- `0x1800234f0`
- `0x180024870`
- `0x180027a50`
- `0x180029310`
- `0x180029320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180023639`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180023739`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180023639`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180023739`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023698`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023791`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023698`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002366e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002367d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002376b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002377a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002366e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002367d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002376b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002377a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023785`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023785`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  __int64 v12; // rcx
  WCHAR *v13; // rax
  __int64 v14; // rdx
  const wchar_t *v15; // r8
  bool v16; // zf
  __int64 v17; // rax
  __int64 v18; // rcx
  WCHAR *v19; // rdx
  WCHAR *v20; // rcx
  LONG v21; // r15d
  LONG v22; // r8d
  wil::details *v23; // rcx
  HANDLE Semaphore; // r14
  int LastErrorFailHr; // eax
  unsigned int v26; // r8d
  unsigned int v27; // esi
  void *v29; // rsi
  DWORD LastError; // ebp
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned __int64 v33; // r12
  WCHAR *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  WCHAR *v37; // rax
  const wchar_t *v38; // rcx
  __int64 v39; // rbx
  WCHAR *v40; // rcx
  wil::details *v41; // rcx
  HANDLE v42; // rdi
  int v43; // eax
  unsigned int v44; // r8d
  unsigned int v45; // ebx
  void *v46; // rbx
  DWORD v47; // esi
  unsigned int v48; // r8d
  const char *v49; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 2147483646;
  v10 = 260;
  do
  {
    if ( !v9 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v9;
    --v10;
  }
  while ( v10 );
  v11 = v7 - 1;
  if ( v10 )
    v11 = v7;
  *v11 = 0;
  v12 = 260;
  v13 = Name;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v14 = 260 - v12;
  if ( v12 )
  {
    v15 = L"_p0";
    v17 = v12;
    v16 = v14 == 260;
    v18 = 2147483646;
    v19 = &Name[v14];
    if ( !v16 )
    {
      do
      {
        if ( !v18 )
          break;
        if ( !*v15 )
          break;
        *v19++ = *v15++;
        --v18;
        --v17;
      }
      while ( v17 );
    }
    v20 = v19 - 1;
    if ( v17 )
      v20 = v19;
    *v20 = 0;
  }
  v21 = 1;
  v22 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v22 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v22, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v29 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v23);
    v27 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        v26,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v27;
    }
  }
  v33 = a4 >> 31;
  v34 = Name;
  v35 = 260;
  do
  {
    if ( !*v34 )
      break;
    ++v34;
    --v35;
  }
  while ( v35 );
  v36 = 260 - v35;
  if ( v35 )
  {
    v37 = &Name[v36];
    v38 = L"h";
    v39 = 260 - v36;
    if ( 260 != v36 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v38 )
          break;
        *v37++ = *v38++;
        --v8;
        --v39;
      }
      while ( v39 );
    }
    v40 = v37 - 1;
    if ( v39 )
      v40 = v37;
    *v40 = 0;
  }
  if ( (_DWORD)v33 )
    v21 = v33;
  v42 = CreateSemaphoreExW(0, v33, v21, Name, 0, 0x1F0003u);
  if ( v42 )
  {
    GetLastError();
    v46 = (void *)*((_QWORD *)this + 1);
    if ( v46 )
    {
      v47 = GetLastError();
      if ( !CloseHandle(v46) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v48, v49);
      SetLastError(v47);
    }
    *((_QWORD *)this + 1) = v42;
  }
  else
  {
    v43 = wil::details::GetLastErrorFailHr(v41);
    v45 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v44, (const char *)(unsigned int)v43, dwFlagsa);
      return v45;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800234f0  mov     r11, rsp
0x1800234f3  push    r12
0x1800234f5  push    r13
0x1800234f7  sub     rsp, 278h
0x1800234fe  mov     rax, cs:__security_cookie
0x180023505  xor     rax, rsp
0x180023508  mov     [rsp+288h+var_48], rax
0x180023510  mov     rax, 0C000000000000000h
0x18002351a  mov     r12, r9
0x18002351d  mov     r8, rdx
0x180023520  mov     r13, rcx
0x180023523  test    rax, r9
0x180023526  jnz     loc_1800237FC
0x18002352c  mov     [r11+10h], rbx
0x180023530  lea     rax, [rsp+288h+Name]
0x180023535  mov     [r11-28h], rdi
0x180023539  mov     ebx, 104h
0x18002353e  mov     edi, 7FFFFFFEh
0x180023543  mov     [r11-30h], r14
0x180023547  mov     ecx, edi
0x180023549  mov     [r11-38h], r15
0x18002354d  mov     edx, ebx
0x18002354f  nop
0x180023550  test    rcx, rcx
0x180023553  jz      short loc_180023574
0x180023555  movzx   r9d, word ptr [r8]
0x180023559  test    r9w, r9w
0x18002355d  jz      short loc_180023574
0x18002355f  mov     [rax], r9w
0x180023563  add     r8, 2
0x180023567  add     rax, 2
0x18002356b  dec     rcx
0x18002356e  sub     rdx, 1
0x180023572  jnz     short loc_180023550
0x180023574  lea     rcx, [rax-2]
0x180023578  test    rdx, rdx
0x18002357b  cmovnz  rcx, rax
0x18002357f  xor     eax, eax
0x180023581  mov     [rcx], ax
0x180023584  mov     rcx, rbx
0x180023587  lea     rax, [rsp+288h+Name]
0x18002358c  nop     dword ptr [rax+00h]
0x180023590  cmp     word ptr [rax], 0
0x180023594  jz      short loc_1800235A0
0x180023596  add     rax, 2
0x18002359a  sub     rcx, 1
0x18002359e  jnz     short loc_180023590
0x1800235a0  xor     eax, eax
0x1800235a2  mov     rdx, rbx
0x1800235a5  sub     rdx, rcx
0x1800235a8  test    rcx, rcx
0x1800235ab  cmovz   rdx, rax
0x1800235af  jz      short loc_1800235FC
0x1800235b1  mov     rax, rbx
0x1800235b4  lea     r8, aP0; "_p0"
0x1800235bb  sub     rax, rdx
0x1800235be  mov     rcx, rdi
0x1800235c1  lea     rdx, [rsp+rdx*2+288h+Name]
0x1800235c6  jz      short loc_1800235EC
0x1800235c8  test    rcx, rcx
0x1800235cb  jz      short loc_1800235EC
0x1800235cd  movzx   r9d, word ptr [r8]
0x1800235d1  test    r9w, r9w
0x1800235d5  jz      short loc_1800235EC
0x1800235d7  mov     [rdx], r9w
0x1800235db  add     r8, 2
0x1800235df  add     rdx, 2
0x1800235e3  dec     rcx
0x1800235e6  sub     rax, 1
0x1800235ea  jnz     short loc_1800235C8
0x1800235ec  test    rax, rax
0x1800235ef  lea     rcx, [rdx-2]
0x1800235f3  cmovnz  rcx, rdx
0x1800235f7  xor     eax, eax
0x1800235f9  mov     [rcx], ax
0x1800235fc  mov     edx, r12d
0x1800235ff  mov     [rsp+288h+var_18], rbp
0x180023607  and     edx, 7FFFFFFFh; lInitialCount
0x18002360d  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180023615  mov     r15d, 1
0x18002361b  mov     [rsp+288h+var_20], rsi
0x180023623  mov     r8d, r15d
0x180023626  mov     [rsp+288h+dwFlags], 0; int
0x18002362e  cmova   r8d, edx; lMaximumCount
0x180023632  lea     r9, [rsp+288h+Name]; lpName
0x180023637  xor     ecx, ecx; lpSemaphoreAttributes
0x180023639  call    cs:__imp_CreateSemaphoreExW
0x18002363f  mov     r14, rax
0x180023642  test    rax, rax
0x180023645  jnz     short loc_18002366E
0x180023647  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002364c  mov     esi, eax
0x18002364e  test    eax, eax
0x180023650  jns     short loc_1800236A2
0x180023652  mov     rcx, [rsp+288h]; this
0x18002365a  mov     r9d, eax; char *
0x18002365d  mov     edx, 8Bh; void *
0x180023662  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023667  mov     eax, esi
0x180023669  jmp     loc_18002379D
0x18002366e  call    cs:__imp_GetLastError
0x180023674  mov     rsi, [r13+0]
0x180023678  test    rsi, rsi
0x18002367b  jz      short loc_18002369E
0x18002367d  call    cs:__imp_GetLastError
0x180023683  mov     rcx, rsi; hObject
0x180023686  mov     ebp, eax
0x180023688  call    cs:__imp_CloseHandle
0x18002368e  test    eax, eax
0x180023690  jz      loc_180023802
0x180023696  mov     ecx, ebp; dwErrCode
0x180023698  call    cs:__imp_SetLastError
0x18002369e  mov     [r13+0], r14
0x1800236a2  shr     r12, 1Fh
0x1800236a6  lea     rax, [rsp+288h+Name]
0x1800236ab  mov     rcx, rbx
0x1800236ae  xchg    ax, ax
0x1800236b0  cmp     word ptr [rax], 0
0x1800236b4  jz      short loc_1800236BF
0x1800236b6  add     rax, 2
0x1800236ba  sub     rcx, r15
0x1800236bd  jnz     short loc_1800236B0
0x1800236bf  xor     eax, eax
0x1800236c1  mov     rdx, rbx
0x1800236c4  sub     rdx, rcx
0x1800236c7  test    rcx, rcx
0x1800236ca  cmovz   rdx, rax
0x1800236ce  jz      short loc_180023715
0x1800236d0  lea     rax, [rsp+288h+Name]
0x1800236d5  lea     rax, [rax+rdx*2]
0x1800236d9  lea     rcx, asc_180034568; "h"
0x1800236e0  sub     rbx, rdx
0x1800236e3  jz      short loc_180023705
0x1800236e5  test    rdi, rdi
0x1800236e8  jz      short loc_180023705
0x1800236ea  movzx   edx, word ptr [rcx]
0x1800236ed  test    dx, dx
0x1800236f0  jz      short loc_180023705
0x1800236f2  mov     [rax], dx
0x1800236f5  add     rcx, 2
0x1800236f9  add     rax, 2
0x1800236fd  dec     rdi
0x180023700  sub     rbx, r15
0x180023703  jnz     short loc_1800236E5
0x180023705  test    rbx, rbx
0x180023708  lea     rcx, [rax-2]
0x18002370c  cmovnz  rcx, rax
0x180023710  xor     eax, eax
0x180023712  mov     [rcx], ax
0x180023715  test    r12d, r12d
0x180023718  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180023720  lea     r9, [rsp+288h+Name]; lpName
0x180023725  mov     [rsp+288h+dwFlags], 0; int
0x18002372d  cmovnz  r15d, r12d
0x180023731  mov     edx, r12d; lInitialCount
0x180023734  mov     r8d, r15d; lMaximumCount
0x180023737  xor     ecx, ecx; lpSemaphoreAttributes
0x180023739  call    cs:__imp_CreateSemaphoreExW
0x18002373f  mov     rdi, rax
0x180023742  test    rax, rax
0x180023745  jnz     short loc_18002376B
0x180023747  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002374c  mov     ebx, eax
0x18002374e  test    eax, eax
0x180023750  jns     short loc_18002379B
0x180023752  mov     rcx, [rsp+288h]; this
0x18002375a  mov     r9d, eax; char *
0x18002375d  mov     edx, 90h; void *
0x180023762  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023767  mov     eax, ebx
0x180023769  jmp     short loc_18002379D
0x18002376b  call    cs:__imp_GetLastError
0x180023771  mov     rbx, [r13+8]
0x180023775  test    rbx, rbx
0x180023778  jz      short loc_180023797
0x18002377a  call    cs:__imp_GetLastError
0x180023780  mov     rcx, rbx; hObject
0x180023783  mov     esi, eax
0x180023785  call    cs:__imp_CloseHandle
0x18002378b  test    eax, eax
0x18002378d  jz      short loc_1800237E9
0x18002378f  mov     ecx, esi; dwErrCode
0x180023791  call    cs:__imp_SetLastError
0x180023797  mov     [r13+8], rdi
0x18002379b  xor     eax, eax
0x18002379d  mov     rsi, [rsp+288h+var_20]
0x1800237a5  mov     rbp, [rsp+288h+var_18]
0x1800237ad  mov     rdi, [rsp+288h+var_28]
0x1800237b5  mov     r14, [rsp+288h+var_30]
0x1800237bd  mov     rbx, [rsp+288h+arg_8]
0x1800237c5  mov     r15, [rsp+288h+var_38]
0x1800237cd  mov     rcx, [rsp+288h+var_48]
0x1800237d5  xor     rcx, rsp; StackCookie
0x1800237d8  call    __security_check_cookie
0x1800237dd  add     rsp, 278h
0x1800237e4  pop     r13
0x1800237e6  pop     r12
0x1800237e8  retn
0x1800237e9  mov     rcx, [rsp+288h]; this
0x1800237f1  mov     edx, 0A0Bh; void *
0x1800237f6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800237fc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180023802  mov     rcx, [rsp+288h]; this
0x18002380a  mov     edx, 0A0Bh; void *
0x18002380f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
