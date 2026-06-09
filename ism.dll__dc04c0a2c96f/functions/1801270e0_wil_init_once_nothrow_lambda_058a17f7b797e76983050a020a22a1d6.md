# wil::init_once_nothrow__lambda_058a17f7b797e76983050a020a22a1d6___

- ea: `0x1801270e0`
- end: `0x180127182`
- name: `wil::init_once_nothrow__lambda_058a17f7b797e76983050a020a22a1d6___`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180127220`

## callees

- `0x18008daac`
- `0x18008ead4`
- `0x1801270e0`
- `0x180127188`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18012715e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180127174`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18012715e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180127174`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180127103`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180127103`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_058a17f7b797e76983050a020a22a1d6___(
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
  if ( !__std_init_once_begin_initialize(&stru_180244248, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( fPending )
  {
    v5 = lambda_058a17f7b797e76983050a020a22a1d6_::operator()();
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v5, v7);
      InitOnceComplete(&stru_180244248, 4u, 0);
      return v6;
    }
    InitOnceComplete(&stru_180244248, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1801270e0  mov     qword ptr [rsp+fPending], r8
0x1801270e5  push    rbx; int
0x1801270e6  sub     rsp, 20h
0x1801270ea  xor     r9d, r9d; lpContext
0x1801270ed  mov     [rsp+28h+fPending], 0
0x1801270f5  lea     r8, [rsp+28h+fPending]; fPending
0x1801270fa  xor     edx, edx; dwFlags
0x1801270fc  lea     rcx, stru_180244248; lpInitOnce
0x180127103  call    cs:__imp___std_init_once_begin_initialize
0x180127109  test    eax, eax
0x18012710b  jnz     short loc_180127125
0x18012710d  mov     rcx, [rsp+28h]; this
0x180127112  lea     r8, aWil; "wil"
0x180127119  mov     edx, 37Ah; void *
0x18012711e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180127123  jmp     short loc_18012717C
0x180127125  cmp     [rsp+28h+fPending], 0
0x18012712a  jz      short loc_18012717A
0x18012712c  call    _lambda_058a17f7b797e76983050a020a22a1d6___operator__
0x180127131  mov     ebx, eax
0x180127133  test    eax, eax
0x180127135  jns     short loc_180127168
0x180127137  mov     rcx, [rsp+28h]; this
0x18012713c  lea     r8, aWil; "wil"
0x180127143  mov     r9d, eax; char *
0x180127146  mov     edx, 37Fh; void *
0x18012714b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180127150  xor     r8d, r8d; lpContext
0x180127153  lea     rcx, stru_180244248; lpInitOnce
0x18012715a  lea     edx, [r8+4]; dwFlags
0x18012715e  call    cs:__imp_InitOnceComplete
0x180127164  mov     eax, ebx
0x180127166  jmp     short loc_18012717C
0x180127168  xor     r8d, r8d; lpContext
0x18012716b  lea     rcx, stru_180244248; lpInitOnce
0x180127172  xor     edx, edx; dwFlags
0x180127174  call    cs:__imp_InitOnceComplete
0x18012717a  xor     eax, eax
0x18012717c  add     rsp, 20h
0x180127180  pop     rbx
0x180127181  retn
```
