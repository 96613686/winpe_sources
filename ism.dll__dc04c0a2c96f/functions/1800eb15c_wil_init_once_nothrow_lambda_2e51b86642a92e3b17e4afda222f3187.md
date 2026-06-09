# wil::init_once_nothrow__lambda_2e51b86642a92e3b17e4afda222f3187___

- ea: `0x1800eb15c`
- end: `0x1800eb222`
- name: `wil::init_once_nothrow__lambda_2e51b86642a92e3b17e4afda222f3187___`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800eb0c8`

## callees

- `0x18008daac`
- `0x18008ead4`
- `0x1800eb15c`
- `0x1801a1ea8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800eb1f1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800eb20f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800eb1f1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800eb20f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800eb18f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800eb18f`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_2e51b86642a92e3b17e4afda222f3187___(
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
  if ( !__std_init_once_begin_initialize(&stru_180244608, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v4);
  if ( fPending )
  {
    v6 = DisplayOcclusionContextProvider::Create(&qword_180244AB8);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v6, v8);
      InitOnceComplete(&stru_180244608, 4u, 0);
      return v7;
    }
    if ( a3 )
      *a3 = 1;
    InitOnceComplete(&stru_180244608, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800eb15c  mov     [rsp+arg_0], rbx
0x1800eb161  mov     byte ptr [rsp+fPending], dl
0x1800eb165  push    rdi; int
0x1800eb166  sub     rsp, 20h
0x1800eb16a  mov     rbx, r8
0x1800eb16d  mov     [rsp+28h+fPending], 0
0x1800eb175  test    r8, r8
0x1800eb178  jz      short loc_1800EB17E
0x1800eb17a  mov     byte ptr [r8], 0
0x1800eb17e  xor     r9d, r9d; lpContext
0x1800eb181  lea     r8, [rsp+28h+fPending]; fPending
0x1800eb186  xor     edx, edx; dwFlags
0x1800eb188  lea     rcx, stru_180244608; lpInitOnce
0x1800eb18f  call    cs:__imp___std_init_once_begin_initialize
0x1800eb195  test    eax, eax
0x1800eb197  jnz     short loc_1800EB1B1
0x1800eb199  mov     rcx, [rsp+28h]; this
0x1800eb19e  lea     r8, aWil; "wil"
0x1800eb1a5  mov     edx, 37Ah; void *
0x1800eb1aa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800eb1af  jmp     short loc_1800EB217
0x1800eb1b1  cmp     [rsp+28h+fPending], 0
0x1800eb1b6  jz      short loc_1800EB215
0x1800eb1b8  lea     rcx, qword_180244AB8; struct DisplayOcclusionContextProvider **
0x1800eb1bf  call    ?Create@DisplayOcclusionContextProvider@@CAJPEAPEAV1@@Z; DisplayOcclusionContextProvider::Create(DisplayOcclusionContextProvider * *)
0x1800eb1c4  mov     edi, eax
0x1800eb1c6  test    eax, eax
0x1800eb1c8  jns     short loc_1800EB1FB
0x1800eb1ca  mov     rcx, [rsp+28h]; this
0x1800eb1cf  mov     r9d, eax; char *
0x1800eb1d2  lea     r8, aWil; "wil"
0x1800eb1d9  mov     edx, 37Fh; void *
0x1800eb1de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb1e3  xor     r8d, r8d; lpContext
0x1800eb1e6  lea     edx, [r8+4]; dwFlags
0x1800eb1ea  lea     rcx, stru_180244608; lpInitOnce
0x1800eb1f1  call    cs:__imp_InitOnceComplete
0x1800eb1f7  mov     eax, edi
0x1800eb1f9  jmp     short loc_1800EB217
0x1800eb1fb  test    rbx, rbx
0x1800eb1fe  jz      short loc_1800EB203
0x1800eb200  mov     byte ptr [rbx], 1
0x1800eb203  xor     r8d, r8d; lpContext
0x1800eb206  xor     edx, edx; dwFlags
0x1800eb208  lea     rcx, stru_180244608; lpInitOnce
0x1800eb20f  call    cs:__imp_InitOnceComplete
0x1800eb215  xor     eax, eax
0x1800eb217  mov     rbx, [rsp+28h+arg_0]
0x1800eb21c  add     rsp, 20h
0x1800eb220  pop     rdi
0x1800eb221  retn
```
