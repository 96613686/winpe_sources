# ExecutionContextStateInit

- ea: `0x180009440`
- end: `0x1800094ac`
- name: `ExecutionContextStateInit`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000175c`
- `0x180009420`
- `0x180009440`
- `0x18000b518`
- `0x180042e68`

## import_xrefs

- `msvcrt!abort` at `0x18000949e`
- `msvcrt!abort` at `0x18000949e`

## string_xrefs

- `0x18000945f`: `admin\wmi\winomi\mp\common\executioncontext.c`

## pseudocode

```c
__int64 __fastcall ExecutionContextStateInit(__int64 a1, _QWORD *a2)
{
  _QWORD v3[2]; // [rsp+20h] [rbp-28h] BYREF
  int v4; // [rsp+30h] [rbp-18h]
  int v5; // [rsp+34h] [rbp-14h]

  v4 = 57;
  v3[0] = "ExecutionContextStateInit";
  *a2 = &dword_18008E454;
  v3[1] = "admin\\wmi\\winomi\\mp\\common\\executioncontext.c";
  v5 = -1;
  if ( (unsigned int)TLS_Init_Injected(&dword_18008E454, v3) )
  {
LABEL_4:
    trace_TLSAllocationFailure();
    abort();
  }
  if ( atexit(ExecutionContextStateDestroy) )
  {
    ExecutionContextStateDestroy();
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x180009440  sub     rsp, 48h
0x180009444  lea     rax, aExecutionconte; "ExecutionContextStateInit"
0x18000944b  mov     [rsp+48h+var_18], 39h ; '9'
0x180009453  lea     rcx, dword_18008E454
0x18000945a  mov     [rsp+48h+var_28], rax
0x18000945f  lea     rax, aAdminWmiWinomi_0; "admin\\wmi\\winomi\\mp\\common\\executi"...
0x180009466  mov     [rdx], rcx
0x180009469  lea     rdx, [rsp+48h+var_28]
0x18000946e  mov     [rsp+48h+var_20], rax
0x180009473  mov     [rsp+48h+var_14], 0FFFFFFFFh
0x18000947b  call    TLS_Init_Injected
0x180009480  test    eax, eax
0x180009482  jnz     short loc_180009499
0x180009484  lea     rcx, ExecutionContextStateDestroy; void (__cdecl *)()
0x18000948b  call    atexit
0x180009490  test    eax, eax
0x180009492  jz      short loc_1800094A5
0x180009494  call    ExecutionContextStateDestroy
0x180009499  call    trace_TLSAllocationFailure
0x18000949e  call    cs:__imp_abort
0x1800094a5  xor     eax, eax
0x1800094a7  add     rsp, 48h
0x1800094ab  retn
```
