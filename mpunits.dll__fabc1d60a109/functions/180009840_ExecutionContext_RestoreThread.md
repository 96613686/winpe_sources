# ExecutionContext_RestoreThread

- ea: `0x180009840`
- end: `0x18000989f`
- name: `ExecutionContext_RestoreThread`
- size: `95`
- prototype: `__int64 __fastcall(LPGUID ActivityId)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009840`
- `0x180009c08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000988e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000988e`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009873`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009873`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180009882`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180009882`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000986a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000986a`

## pseudocode

```c
void __fastcall ExecutionContext_RestoreThread(LPGUID ActivityId)
{
  DWORD *TLS; // rbx
  ULONG pulNumLanguages; // [rsp+30h] [rbp+8h] BYREF

  if ( ActivityId )
  {
    pulNumLanguages = 0;
    TLS = (DWORD *)GetTLS();
    EventActivityIdControl(2u, ActivityId);
    SetThreadLocale(*(_DWORD *)ActivityId[1].Data4);
    SetThreadPreferredUILanguages(0, 0, &pulNumLanguages);
    TlsSetValue(*TLS, *(LPVOID *)&ActivityId[1].Data1);
  }
}

```

## disassembly

```asm
0x180009840  test    rcx, rcx
0x180009843  jz      short locret_18000989E
0x180009845  mov     [rsp+arg_8], rbx
0x18000984a  push    rdi
0x18000984b  sub     rsp, 20h
0x18000984f  mov     rdi, rcx
0x180009852  mov     [rsp+28h+pulNumLanguages], 0
0x18000985a  call    GetTLS
0x18000985f  mov     rdx, rdi; ActivityId
0x180009862  mov     ecx, 2; ControlCode
0x180009867  mov     rbx, rax
0x18000986a  call    cs:__imp_EventActivityIdControl
0x180009870  mov     ecx, [rdi+18h]; Locale
0x180009873  call    cs:__imp_SetThreadLocale
0x180009879  lea     r8, [rsp+28h+pulNumLanguages]; pulNumLanguages
0x18000987e  xor     edx, edx; pwszLanguagesBuffer
0x180009880  xor     ecx, ecx; dwFlags
0x180009882  call    cs:__imp_SetThreadPreferredUILanguages
0x180009888  mov     rdx, [rdi+10h]; lpTlsValue
0x18000988c  mov     ecx, [rbx]; dwTlsIndex
0x18000988e  call    cs:__imp_TlsSetValue
0x180009894  mov     rbx, [rsp+28h+arg_8]
0x180009899  add     rsp, 20h
0x18000989d  pop     rdi
0x18000989e  retn
```
