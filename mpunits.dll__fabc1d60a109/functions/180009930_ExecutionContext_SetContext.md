# ExecutionContext_SetContext

- ea: `0x180009930`
- end: `0x18000999a`
- name: `ExecutionContext_SetContext`
- size: `106`
- prototype: `__int64 __fastcall(LPVOID lpTlsValue)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009c08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009966`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009966`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009946`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009946`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000997e`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000997e`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x180009988`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x180009988`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009975`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009975`

## pseudocode

```c
LPVOID __fastcall ExecutionContext_SetContext(GUID *lpTlsValue)
{
  DWORD *TLS; // rdi
  GUID *v3; // rsi
  LPVOID Value; // rbp

  TLS = (DWORD *)GetTLS();
  v3 = (GUID *)&unk_18006C620;
  Value = TlsGetValue(*TLS);
  if ( lpTlsValue )
    v3 = lpTlsValue;
  v3[3].Data4[0] = 0;
  TlsSetValue(*TLS, v3);
  EventActivityIdControl(2u, v3 + 1);
  SetThreadLocale(v3[2].Data1);
  SetThreadUILanguage(v3[2].Data2);
  return Value;
}

```

## disassembly

```asm
0x180009930  push    rbx
0x180009932  push    rbp
0x180009933  push    rsi
0x180009934  push    rdi
0x180009935  sub     rsp, 28h
0x180009939  mov     rbx, rcx
0x18000993c  call    GetTLS
0x180009941  mov     rdi, rax
0x180009944  mov     ecx, [rax]; dwTlsIndex
0x180009946  call    cs:__imp_TlsGetValue
0x18000994c  test    rbx, rbx
0x18000994f  lea     rsi, unk_18006C620
0x180009956  mov     rbp, rax
0x180009959  cmovnz  rsi, rbx
0x18000995d  mov     rdx, rsi; lpTlsValue
0x180009960  mov     byte ptr [rsi+38h], 0
0x180009964  mov     ecx, [rdi]; dwTlsIndex
0x180009966  call    cs:__imp_TlsSetValue
0x18000996c  lea     rdx, [rsi+10h]; ActivityId
0x180009970  mov     ecx, 2; ControlCode
0x180009975  call    cs:__imp_EventActivityIdControl
0x18000997b  mov     ecx, [rsi+20h]; Locale
0x18000997e  call    cs:__imp_SetThreadLocale
0x180009984  movzx   ecx, word ptr [rsi+24h]; LangId
0x180009988  call    cs:__imp_SetThreadUILanguage
0x18000998e  mov     rax, rbp
0x180009991  add     rsp, 28h
0x180009995  pop     rdi
0x180009996  pop     rsi
0x180009997  pop     rbp
0x180009998  pop     rbx
0x180009999  retn
```
