# ExceptionStateInit

- ea: `0x180007860`
- end: `0x1800078dc`
- name: `ExceptionStateInit`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000175c`
- `0x180007840`
- `0x180007860`
- `0x18000b518`
- `0x180042e68`

## import_xrefs

- `msvcrt!abort` at `0x1800078be`
- `msvcrt!abort` at `0x1800078be`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800078cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800078cf`

## string_xrefs

- `0x18000787f`: `admin\wmi\winomi\mp\common\exceptions.c`

## pseudocode

```c
__int64 __fastcall ExceptionStateInit(__int64 a1, _QWORD *a2)
{
  _QWORD v3[2]; // [rsp+20h] [rbp-28h] BYREF
  int v4; // [rsp+30h] [rbp-18h]
  int v5; // [rsp+34h] [rbp-14h]

  v4 = 31;
  v3[0] = "ExceptionStateInit";
  *a2 = &dwTlsIndex;
  v3[1] = "admin\\wmi\\winomi\\mp\\common\\exceptions.c";
  v5 = -1;
  if ( (unsigned int)TLS_Init_Injected(&dwTlsIndex, v3) )
  {
LABEL_4:
    trace_TLSAllocationFailure();
    abort();
  }
  if ( atexit(ExceptionStateDestroy) )
  {
    ExceptionStateDestroy();
    goto LABEL_4;
  }
  TlsSetValue(dwTlsIndex, (LPVOID)0xFFFFFFFFFFFFFFFFLL);
  return 0;
}

```

## disassembly

```asm
0x180007860  sub     rsp, 48h
0x180007864  lea     rax, aExceptionstate; "ExceptionStateInit"
0x18000786b  mov     [rsp+48h+var_18], 1Fh
0x180007873  lea     rcx, dwTlsIndex
0x18000787a  mov     [rsp+48h+var_28], rax
0x18000787f  lea     rax, aAdminWmiWinomi_8; "admin\\wmi\\winomi\\mp\\common\\excepti"...
0x180007886  mov     [rdx], rcx
0x180007889  lea     rdx, [rsp+48h+var_28]
0x18000788e  mov     [rsp+48h+var_20], rax
0x180007893  mov     [rsp+48h+var_14], 0FFFFFFFFh
0x18000789b  call    TLS_Init_Injected
0x1800078a0  test    eax, eax
0x1800078a2  jnz     short loc_1800078B9
0x1800078a4  lea     rcx, ExceptionStateDestroy; void (__cdecl *)()
0x1800078ab  call    atexit
0x1800078b0  test    eax, eax
0x1800078b2  jz      short loc_1800078C5
0x1800078b4  call    ExceptionStateDestroy
0x1800078b9  call    trace_TLSAllocationFailure
0x1800078be  call    cs:__imp_abort
0x1800078c5  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800078cb  or      rdx, 0FFFFFFFFFFFFFFFFh; lpTlsValue
0x1800078cf  call    cs:__imp_TlsSetValue
0x1800078d5  xor     eax, eax
0x1800078d7  add     rsp, 48h
0x1800078db  retn
```
