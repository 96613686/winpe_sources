# wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>::reset(void *)

- ea: `0x180026be0`
- end: `0x180026c3d`
- name: `?reset@?$unique_storage@U?$handle_null_resource_policy@P6AJPEAX@Z$1?NtCloseCompositionInputSink@@YAJ0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `93`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800150f0`
- `0x180025620`
- `0x180032bb0`
- `0x180154740`
- `0x1801547e8`
- `0x1801ac114`

## callees

- `0x180026be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026c2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026c2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c1a`
- `win32u!NtCloseCompositionInputSink` at `0x180026c25`
- `win32u!NtCloseCompositionInputSink` at `0x180026c25`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>::reset(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rbp
  DWORD LastError; // edi

  v2 = *a1;
  if ( (unsigned __int64)(*a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    NtCloseCompositionInputSink(v2);
    SetLastError(LastError);
    *a1 = a2;
  }
  else
  {
    *a1 = a2;
  }
}

```

## disassembly

```asm
0x180026be0  mov     [rsp+arg_8], rbx
0x180026be5  mov     [rsp+arg_10], rbp
0x180026bea  push    rsi
0x180026beb  sub     rsp, 20h
0x180026bef  mov     rbp, [rcx]
0x180026bf2  mov     rsi, rdx
0x180026bf5  mov     rbx, rcx
0x180026bf8  lea     rax, [rbp-1]
0x180026bfc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026c00  jbe     short loc_180026C15
0x180026c02  mov     [rcx], rdx
0x180026c05  mov     rbx, [rsp+28h+arg_8]
0x180026c0a  mov     rbp, [rsp+28h+arg_10]
0x180026c0f  add     rsp, 20h
0x180026c13  pop     rsi
0x180026c14  retn
0x180026c15  mov     [rsp+28h+arg_0], rdi
0x180026c1a  call    cs:__imp_GetLastError
0x180026c20  mov     rcx, rbp
0x180026c23  mov     edi, eax
0x180026c25  call    cs:__imp_NtCloseCompositionInputSink
0x180026c2b  mov     ecx, edi; dwErrCode
0x180026c2d  call    cs:__imp_SetLastError
0x180026c33  mov     rdi, [rsp+28h+arg_0]
0x180026c38  mov     [rbx], rsi
0x180026c3b  jmp     short loc_180026C05
```
