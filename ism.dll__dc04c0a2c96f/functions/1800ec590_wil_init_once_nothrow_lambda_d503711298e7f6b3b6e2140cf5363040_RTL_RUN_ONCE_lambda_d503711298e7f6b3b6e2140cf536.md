# wil::init_once_nothrow<_lambda_d503711298e7f6b3b6e2140cf5363040_>(_RTL_RUN_ONCE &,_lambda_d503711298e7f6b3b6e2140cf5363040_,bool *)

- ea: `0x1800ec590`
- end: `0x1800ec632`
- name: `??$init_once_nothrow@V_lambda_d503711298e7f6b3b6e2140cf5363040_@@@wil@@YAJAEAT_RTL_RUN_ONCE@@V_lambda_d503711298e7f6b3b6e2140cf5363040_@@PEA_N@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800ec34c`

## callees

- `0x18008daac`
- `0x18008ead4`
- `0x1800ce224`
- `0x1800ec590`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800ec60e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800ec624`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800ec60e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800ec624`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800ec5b3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800ec5b3`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow<_lambda_d503711298e7f6b3b6e2140cf5363040_>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const char *v3; // r9
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL fPending; // [rsp+40h] [rbp+18h] BYREF
  int v10; // [rsp+44h] [rbp+1Ch]

  v10 = HIDWORD(a3);
  fPending = 0;
  if ( !__std_init_once_begin_initialize(
          &`IsHolographicWin32SlatesFeatureEnabled'::`2'::s_win32SlatesKeyQueried,
          0,
          &fPending,
          0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( fPending )
  {
    v5 = _lambda_d503711298e7f6b3b6e2140cf5363040_::operator()();
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v5, v7);
      InitOnceComplete(&`IsHolographicWin32SlatesFeatureEnabled'::`2'::s_win32SlatesKeyQueried, 4u, 0);
      return v6;
    }
    InitOnceComplete(&`IsHolographicWin32SlatesFeatureEnabled'::`2'::s_win32SlatesKeyQueried, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ec590  mov     qword ptr [rsp+fPending], r8
0x1800ec595  push    rbx; int
0x1800ec596  sub     rsp, 20h
0x1800ec59a  xor     r9d, r9d; lpContext
0x1800ec59d  mov     [rsp+28h+fPending], 0
0x1800ec5a5  lea     r8, [rsp+28h+fPending]; fPending
0x1800ec5aa  xor     edx, edx; dwFlags
0x1800ec5ac  lea     rcx, ?s_win32SlatesKeyQueried@?1??IsHolographicWin32SlatesFeatureEnabled@@YA_NXZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x1800ec5b3  call    cs:__imp___std_init_once_begin_initialize
0x1800ec5b9  test    eax, eax
0x1800ec5bb  jnz     short loc_1800EC5D5
0x1800ec5bd  mov     rcx, [rsp+28h]; this
0x1800ec5c2  lea     r8, aWil; "wil"
0x1800ec5c9  mov     edx, 37Ah; void *
0x1800ec5ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ec5d3  jmp     short loc_1800EC62C
0x1800ec5d5  cmp     [rsp+28h+fPending], 0
0x1800ec5da  jz      short loc_1800EC62A
0x1800ec5dc  call    ??R_lambda_d503711298e7f6b3b6e2140cf5363040_@@QEBA@XZ; _lambda_d503711298e7f6b3b6e2140cf5363040_::operator()(void)
0x1800ec5e1  mov     ebx, eax
0x1800ec5e3  test    eax, eax
0x1800ec5e5  jns     short loc_1800EC618
0x1800ec5e7  mov     rcx, [rsp+28h]; this
0x1800ec5ec  lea     r8, aWil; "wil"
0x1800ec5f3  mov     r9d, eax; char *
0x1800ec5f6  mov     edx, 37Fh; void *
0x1800ec5fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec600  xor     r8d, r8d; lpContext
0x1800ec603  lea     rcx, ?s_win32SlatesKeyQueried@?1??IsHolographicWin32SlatesFeatureEnabled@@YA_NXZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x1800ec60a  lea     edx, [r8+4]; dwFlags
0x1800ec60e  call    cs:__imp_InitOnceComplete
0x1800ec614  mov     eax, ebx
0x1800ec616  jmp     short loc_1800EC62C
0x1800ec618  xor     r8d, r8d; lpContext
0x1800ec61b  lea     rcx, ?s_win32SlatesKeyQueried@?1??IsHolographicWin32SlatesFeatureEnabled@@YA_NXZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x1800ec622  xor     edx, edx; dwFlags
0x1800ec624  call    cs:__imp_InitOnceComplete
0x1800ec62a  xor     eax, eax
0x1800ec62c  add     rsp, 20h
0x1800ec630  pop     rbx
0x1800ec631  retn
```
