# wil::init_once_nothrow__lambda_ca82685424ac054990721f288eeb0943___

- ea: `0x1800d1868`
- end: `0x1800d192e`
- name: `wil::init_once_nothrow__lambda_ca82685424ac054990721f288eeb0943___`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800d1434`

## callees

- `0x18008daac`
- `0x18008ead4`
- `0x1800d1868`
- `0x1801a1928`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800d18fd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800d191b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800d18fd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800d191b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800d189b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800d189b`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_ca82685424ac054990721f288eeb0943___(
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
  if ( !__std_init_once_begin_initialize(&stru_180244600, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v4);
  if ( fPending )
  {
    v6 = VirtualTouchpadContextProvider::Create(&qword_180244AA8);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v6, v8);
      InitOnceComplete(&stru_180244600, 4u, 0);
      return v7;
    }
    if ( a3 )
      *a3 = 1;
    InitOnceComplete(&stru_180244600, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800d1868  mov     [rsp+arg_0], rbx
0x1800d186d  mov     byte ptr [rsp+fPending], dl
0x1800d1871  push    rdi; int
0x1800d1872  sub     rsp, 20h
0x1800d1876  mov     rbx, r8
0x1800d1879  mov     [rsp+28h+fPending], 0
0x1800d1881  test    r8, r8
0x1800d1884  jz      short loc_1800D188A
0x1800d1886  mov     byte ptr [r8], 0
0x1800d188a  xor     r9d, r9d; lpContext
0x1800d188d  lea     r8, [rsp+28h+fPending]; fPending
0x1800d1892  xor     edx, edx; dwFlags
0x1800d1894  lea     rcx, stru_180244600; lpInitOnce
0x1800d189b  call    cs:__imp___std_init_once_begin_initialize
0x1800d18a1  test    eax, eax
0x1800d18a3  jnz     short loc_1800D18BD
0x1800d18a5  mov     rcx, [rsp+28h]; this
0x1800d18aa  lea     r8, aWil; "wil"
0x1800d18b1  mov     edx, 37Ah; void *
0x1800d18b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d18bb  jmp     short loc_1800D1923
0x1800d18bd  cmp     [rsp+28h+fPending], 0
0x1800d18c2  jz      short loc_1800D1921
0x1800d18c4  lea     rcx, qword_180244AA8; struct VirtualTouchpadContextProvider **
0x1800d18cb  call    ?Create@VirtualTouchpadContextProvider@@CAJPEAPEAV1@@Z; VirtualTouchpadContextProvider::Create(VirtualTouchpadContextProvider * *)
0x1800d18d0  mov     edi, eax
0x1800d18d2  test    eax, eax
0x1800d18d4  jns     short loc_1800D1907
0x1800d18d6  mov     rcx, [rsp+28h]; this
0x1800d18db  mov     r9d, eax; char *
0x1800d18de  lea     r8, aWil; "wil"
0x1800d18e5  mov     edx, 37Fh; void *
0x1800d18ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d18ef  xor     r8d, r8d; lpContext
0x1800d18f2  lea     edx, [r8+4]; dwFlags
0x1800d18f6  lea     rcx, stru_180244600; lpInitOnce
0x1800d18fd  call    cs:__imp_InitOnceComplete
0x1800d1903  mov     eax, edi
0x1800d1905  jmp     short loc_1800D1923
0x1800d1907  test    rbx, rbx
0x1800d190a  jz      short loc_1800D190F
0x1800d190c  mov     byte ptr [rbx], 1
0x1800d190f  xor     r8d, r8d; lpContext
0x1800d1912  xor     edx, edx; dwFlags
0x1800d1914  lea     rcx, stru_180244600; lpInitOnce
0x1800d191b  call    cs:__imp_InitOnceComplete
0x1800d1921  xor     eax, eax
0x1800d1923  mov     rbx, [rsp+28h+arg_0]
0x1800d1928  add     rsp, 20h
0x1800d192c  pop     rdi
0x1800d192d  retn
```
