# wil::init_once_nothrow__lambda_dcfa4c4accc7a4c0ffedb44f9f29ee27___

- ea: `0x18000ddfc`
- end: `0x18000dec2`
- name: `wil::init_once_nothrow__lambda_dcfa4c4accc7a4c0ffedb44f9f29ee27___`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000dd64`

## callees

- `0x18000ddfc`
- `0x1800806e0`
- `0x18008daac`
- `0x18008ead4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000de91`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000deaf`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000de91`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000deaf`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000de2f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000de2f`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_dcfa4c4accc7a4c0ffedb44f9f29ee27___(
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
  if ( !__std_init_once_begin_initialize(&InitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v4);
  if ( fPending )
  {
    v6 = KernelContextProvider::Create(&qword_1802449A0);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v6, v8);
      InitOnceComplete(&InitOnce, 4u, 0);
      return v7;
    }
    if ( a3 )
      *a3 = 1;
    InitOnceComplete(&InitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ddfc  mov     [rsp+arg_0], rbx
0x18000de01  mov     byte ptr [rsp+fPending], dl
0x18000de05  push    rdi; int
0x18000de06  sub     rsp, 20h
0x18000de0a  mov     rbx, r8
0x18000de0d  mov     [rsp+28h+fPending], 0
0x18000de15  test    r8, r8
0x18000de18  jz      short loc_18000DE1E
0x18000de1a  mov     byte ptr [r8], 0
0x18000de1e  xor     r9d, r9d; lpContext
0x18000de21  lea     r8, [rsp+28h+fPending]; fPending
0x18000de26  xor     edx, edx; dwFlags
0x18000de28  lea     rcx, InitOnce; lpInitOnce
0x18000de2f  call    cs:__imp___std_init_once_begin_initialize
0x18000de35  test    eax, eax
0x18000de37  jnz     short loc_18000DE51
0x18000de39  mov     rcx, [rsp+28h]; this
0x18000de3e  lea     r8, aWil; "wil"
0x18000de45  mov     edx, 37Ah; void *
0x18000de4a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000de4f  jmp     short loc_18000DEB7
0x18000de51  cmp     [rsp+28h+fPending], 0
0x18000de56  jz      short loc_18000DEB5
0x18000de58  lea     rcx, qword_1802449A0; struct KernelContextProvider **
0x18000de5f  call    ?Create@KernelContextProvider@@CAJPEAPEAV1@@Z; KernelContextProvider::Create(KernelContextProvider * *)
0x18000de64  mov     edi, eax
0x18000de66  test    eax, eax
0x18000de68  jns     short loc_18000DE9B
0x18000de6a  mov     rcx, [rsp+28h]; this
0x18000de6f  mov     r9d, eax; char *
0x18000de72  lea     r8, aWil; "wil"
0x18000de79  mov     edx, 37Fh; void *
0x18000de7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de83  xor     r8d, r8d; lpContext
0x18000de86  lea     edx, [r8+4]; dwFlags
0x18000de8a  lea     rcx, InitOnce; lpInitOnce
0x18000de91  call    cs:__imp_InitOnceComplete
0x18000de97  mov     eax, edi
0x18000de99  jmp     short loc_18000DEB7
0x18000de9b  test    rbx, rbx
0x18000de9e  jz      short loc_18000DEA3
0x18000dea0  mov     byte ptr [rbx], 1
0x18000dea3  xor     r8d, r8d; lpContext
0x18000dea6  xor     edx, edx; dwFlags
0x18000dea8  lea     rcx, InitOnce; lpInitOnce
0x18000deaf  call    cs:__imp_InitOnceComplete
0x18000deb5  xor     eax, eax
0x18000deb7  mov     rbx, [rsp+28h+arg_0]
0x18000debc  add     rsp, 20h
0x18000dec0  pop     rdi
0x18000dec1  retn
```
