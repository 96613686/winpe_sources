# wil::init_once_nothrow__lambda_008aa74523cf7437dacc2be58aae67bd___

- ea: `0x18008d7fc`
- end: `0x18008d8c2`
- name: `wil::init_once_nothrow__lambda_008aa74523cf7437dacc2be58aae67bd___`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b040`

## callees

- `0x18008d7fc`
- `0x18008daac`
- `0x18008ead4`
- `0x18013f52c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008d891`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008d8af`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008d891`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008d8af`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18008d82f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18008d82f`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_008aa74523cf7437dacc2be58aae67bd___(
        __int64 a1,
        __int64 a2,
        _BYTE *a3)
{
  const char *v4; // r9
  int v6; // eax
  unsigned int v7; // edi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL fPending; // [rsp+38h] [rbp+10h] BYREF

  fPending = 0;
  if ( a3 )
    *a3 = 0;
  if ( !__std_init_once_begin_initialize(&stru_180244320, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v4);
  if ( fPending )
  {
    v6 = InputConfigContextProvider::Create(&qword_180244990);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v6, v8);
      InitOnceComplete(&stru_180244320, 4u, 0);
      return v7;
    }
    if ( a3 )
      *a3 = 1;
    InitOnceComplete(&stru_180244320, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18008d7fc  mov     [rsp+arg_0], rbx
0x18008d801  mov     byte ptr [rsp+fPending], dl
0x18008d805  push    rdi; int
0x18008d806  sub     rsp, 20h
0x18008d80a  mov     rbx, r8
0x18008d80d  mov     [rsp+28h+fPending], 0
0x18008d815  test    r8, r8
0x18008d818  jz      short loc_18008D81E
0x18008d81a  mov     byte ptr [r8], 0
0x18008d81e  xor     r9d, r9d; lpContext
0x18008d821  lea     r8, [rsp+28h+fPending]; fPending
0x18008d826  xor     edx, edx; dwFlags
0x18008d828  lea     rcx, stru_180244320; lpInitOnce
0x18008d82f  call    cs:__imp___std_init_once_begin_initialize
0x18008d835  test    eax, eax
0x18008d837  jnz     short loc_18008D851
0x18008d839  mov     rcx, [rsp+28h]; this
0x18008d83e  lea     r8, aWil; "wil"
0x18008d845  mov     edx, 37Ah; void *
0x18008d84a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008d84f  jmp     short loc_18008D8B7
0x18008d851  cmp     [rsp+28h+fPending], 0
0x18008d856  jz      short loc_18008D8B5
0x18008d858  lea     rcx, qword_180244990; struct InputConfigContextProvider **
0x18008d85f  call    ?Create@InputConfigContextProvider@@CAJPEAPEAV1@@Z; InputConfigContextProvider::Create(InputConfigContextProvider * *)
0x18008d864  mov     edi, eax
0x18008d866  test    eax, eax
0x18008d868  jns     short loc_18008D89B
0x18008d86a  mov     rcx, [rsp+28h]; this
0x18008d86f  mov     r9d, eax; char *
0x18008d872  lea     r8, aWil; "wil"
0x18008d879  mov     edx, 37Fh; void *
0x18008d87e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d883  xor     r8d, r8d; lpContext
0x18008d886  lea     edx, [r8+4]; dwFlags
0x18008d88a  lea     rcx, stru_180244320; lpInitOnce
0x18008d891  call    cs:__imp_InitOnceComplete
0x18008d897  mov     eax, edi
0x18008d899  jmp     short loc_18008D8B7
0x18008d89b  test    rbx, rbx
0x18008d89e  jz      short loc_18008D8A3
0x18008d8a0  mov     byte ptr [rbx], 1
0x18008d8a3  xor     r8d, r8d; lpContext
0x18008d8a6  xor     edx, edx; dwFlags
0x18008d8a8  lea     rcx, stru_180244320; lpInitOnce
0x18008d8af  call    cs:__imp_InitOnceComplete
0x18008d8b5  xor     eax, eax
0x18008d8b7  mov     rbx, [rsp+28h+arg_0]
0x18008d8bc  add     rsp, 20h
0x18008d8c0  pop     rdi
0x18008d8c1  retn
```
