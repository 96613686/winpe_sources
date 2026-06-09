# ReaderMonitorUpdateCerts

- ea: `0x1800062e0`
- end: `0x18000646e`
- name: `ReaderMonitorUpdateCerts`
- size: `398`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180011c10`
- `0x1800180f4`

## callees

- `0x180004600`
- `0x1800062e0`
- `0x18000c8f0`
- `0x1800115c0`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x1800243f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800063de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800063de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063ba`

## pseudocode

```c
__int64 __fastcall ReaderMonitorUpdateCerts(__int64 a1, __int64 a2)
{
  STRSAFE_LPSTR v4; // rcx
  unsigned int v5; // esi
  unsigned int v6; // ebp
  _BYTE v8[8]; // [rsp+30h] [rbp-68h] BYREF
  _OWORD v9[2]; // [rsp+38h] [rbp-60h] BYREF
  int v10; // [rsp+58h] [rbp-40h]

  v10 = 0;
  memset(v9, 0, sizeof(v9));
  WppTraceIndent(a1, 0);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( a2 && a1 && (v5 = *(unsigned __int8 *)(a2 + 76), (unsigned __int8)v5 <= 0x24u) )
  {
    memcpy_0(v9, (const void *)(a2 + 40), *(unsigned __int8 *)(a2 + 76));
    v6 = I_ReaderListClearReader(a1, *(_QWORD *)a2, v8);
    if ( !v6 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
      v6 = I_ReaderListCollectCertificates((int *)a1, a2, *(_DWORD *)(a2 + 8), v9, v5);
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    }
  }
  else
  {
    v6 = 87;
  }
  WppTraceIndent(v4, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      238,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800062e0  sub     rsp, 98h
0x1800062e7  mov     rax, cs:__security_cookie
0x1800062ee  xor     rax, rsp
0x1800062f1  mov     [rsp+98h+var_38], rax
0x1800062f6  mov     [rsp+98h+arg_10], rbx
0x1800062fe  xorps   xmm0, xmm0
0x180006301  mov     rbx, rdx
0x180006304  mov     [rsp+98h+var_20], r14
0x180006309  xor     eax, eax
0x18000630b  mov     [rsp+98h+var_28], r15
0x180006310  xor     edx, edx
0x180006312  mov     [rsp+98h+var_40], eax
0x180006316  mov     r14, rcx
0x180006319  movups  [rsp+98h+var_60], xmm0
0x18000631e  movups  [rsp+98h+var_50], xmm0
0x180006323  call    WppTraceIndent
0x180006328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000632f  lea     r15, WPP_GLOBAL_Control
0x180006336  cmp     rcx, r15
0x180006339  jz      short loc_180006363
0x18000633b  test    byte ptr [rcx+1Ch], 2
0x18000633f  jz      short loc_180006363
0x180006341  cmp     byte ptr [rcx+19h], 5
0x180006345  jb      short loc_180006363
0x180006347  mov     r9, cs:WPP_pszIndent
0x18000634e  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180006355  mov     rcx, [rcx+10h]
0x180006359  mov     edx, 0EDh
0x18000635e  call    WPP_SF_s
0x180006363  mov     [rsp+98h+var_8], rbp
0x18000636b  mov     [rsp+98h+var_10], rsi
0x180006373  test    rbx, rbx
0x180006376  jz      short loc_1800063EE
0x180006378  test    r14, r14
0x18000637b  jz      short loc_1800063EE
0x18000637d  movzx   esi, byte ptr [rbx+4Ch]
0x180006381  cmp     sil, 24h ; '$'
0x180006385  ja      short loc_1800063EE
0x180006387  mov     r8d, esi; Size
0x18000638a  lea     rdx, [rbx+28h]; Src
0x18000638e  lea     rcx, [rsp+98h+var_60]; void *
0x180006393  call    memcpy_0
0x180006398  mov     rdx, [rbx]
0x18000639b  lea     r8, [rsp+98h+var_68]
0x1800063a0  mov     rcx, r14
0x1800063a3  call    I_ReaderListClearReader
0x1800063a8  mov     ebp, eax
0x1800063aa  test    eax, eax
0x1800063ac  jnz     short loc_1800063F3
0x1800063ae  lea     rcx, [r14+30h]; lpCriticalSection
0x1800063b2  mov     [rsp+98h+var_18], rdi
0x1800063ba  call    cs:__imp_EnterCriticalSection
0x1800063c0  mov     r8d, [rbx+8]
0x1800063c4  lea     r9, [rsp+98h+var_60]
0x1800063c9  mov     rdx, rbx
0x1800063cc  mov     [rsp+98h+var_78], esi
0x1800063d0  mov     rcx, r14
0x1800063d3  call    I_ReaderListCollectCertificates
0x1800063d8  lea     rcx, [r14+30h]; lpCriticalSection
0x1800063dc  mov     ebp, eax
0x1800063de  call    cs:__imp_LeaveCriticalSection
0x1800063e4  mov     rdi, [rsp+98h+var_18]
0x1800063ec  jmp     short loc_1800063F3
0x1800063ee  mov     ebp, 57h ; 'W'
0x1800063f3  mov     edx, 1
0x1800063f8  call    WppTraceIndent
0x1800063fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180006404  mov     r14, [rsp+98h+var_20]
0x180006409  cmp     rcx, r15
0x18000640c  mov     r15, [rsp+98h+var_28]
0x180006411  mov     rsi, [rsp+98h+var_10]
0x180006419  mov     rbx, [rsp+98h+arg_10]
0x180006421  jz      short loc_18000644F
0x180006423  test    byte ptr [rcx+1Ch], 2
0x180006427  jz      short loc_18000644F
0x180006429  cmp     byte ptr [rcx+19h], 5
0x18000642d  jb      short loc_18000644F
0x18000642f  mov     r9, cs:WPP_pszIndent
0x180006436  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000643d  mov     rcx, [rcx+10h]
0x180006441  mov     edx, 0EEh
0x180006446  mov     [rsp+98h+var_78], ebp
0x18000644a  call    WPP_SF_sD
0x18000644f  mov     eax, ebp
0x180006451  mov     rbp, [rsp+98h+var_8]
0x180006459  mov     rcx, [rsp+98h+var_38]
0x18000645e  xor     rcx, rsp; StackCookie
0x180006461  call    __security_check_cookie
0x180006466  add     rsp, 98h
0x18000646d  retn
```
