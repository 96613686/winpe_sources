# SetTlsSlotData

- ea: `0x18000ccc8`
- end: `0x18000cd4e`
- name: `SetTlsSlotData`
- size: `134`
- prototype: `__int64 __fastcall(LPVOID lpTlsValue)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c994`
- `0x18000cb50`

## callees

- `0x18000c130`
- `0x18000c548`
- `0x18000ccc8`
- `0x18000cecc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000cd1f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000cd1f`

## string_xrefs

- `0x18000cce5`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000ccfe`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000cd2e`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall SetTlsSlotData(LPVOID lpTlsValue, __int64 a2, __int64 a3)
{
  int inited; // eax
  unsigned int v5; // ebx
  const char *v7; // r9
  int v8; // [rsp+20h] [rbp-8h]
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  inited = wil::init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___((__int64)lpTlsValue, a2, a3);
  v5 = inited;
  if ( inited >= 0 )
  {
    if ( TlsSetValue(g_tlsTaskPool, lpTlsValue) )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x8F,
               (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
               v7);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)inited,
      v8);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)v5,
      v9);
    return v5;
  }
}

```

## disassembly

```asm
0x18000ccc8  mov     [rsp+arg_0], rbx
0x18000cccd  push    rdi; int
0x18000ccce  sub     rsp, 20h
0x18000ccd2  mov     rdi, rcx
0x18000ccd5  call    wil__init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___
0x18000ccda  mov     ebx, eax
0x18000ccdc  test    eax, eax
0x18000ccde  jns     short loc_18000CD16
0x18000cce0  mov     rcx, [rsp+28h]; this
0x18000cce5  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000ccec  mov     r9d, eax; char *
0x18000ccef  mov     edx, 70h ; 'p'; void *
0x18000ccf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ccf9  mov     rcx, [rsp+28h]; this
0x18000ccfe  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000cd05  mov     r9d, ebx; char *
0x18000cd08  mov     edx, 8Eh; void *
0x18000cd0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd12  mov     eax, ebx
0x18000cd14  jmp     short loc_18000CD43
0x18000cd16  mov     ecx, cs:?g_tlsTaskPool@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@KP6AHK@Z$1?TlsFree@@YAHK@ZU?$integral_constant@_K$0A@@wistd@@KK$0PPPPPPPP@K@details@wil@@@details@wil@@@wil@@A; dwTlsIndex
0x18000cd1c  mov     rdx, rdi; lpTlsValue
0x18000cd1f  call    cs:__imp_TlsSetValue
0x18000cd25  test    eax, eax
0x18000cd27  jnz     short loc_18000CD41
0x18000cd29  mov     rcx, [rsp+28h]; this
0x18000cd2e  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000cd35  mov     edx, 8Fh; void *
0x18000cd3a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cd3f  jmp     short loc_18000CD43
0x18000cd41  xor     eax, eax
0x18000cd43  mov     rbx, [rsp+28h+arg_0]
0x18000cd48  add     rsp, 20h
0x18000cd4c  pop     rdi
0x18000cd4d  retn
```
