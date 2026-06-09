# _register_thread_local_exe_atexit_callback_0

- ea: `0x140013d48`
- end: `0x140013d4e`
- name: `_register_thread_local_exe_atexit_callback_0`
- size: `6`
- prototype: `void __cdecl(_tls_callback_type Callback)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14001304c`

## import_xrefs

- `ucrtbase_clr0400!_register_thread_local_exe_atexit_callback` at `0x140013d48`

## pseudocode

```c
// attributes: thunk
void __cdecl register_thread_local_exe_atexit_callback_0(_tls_callback_type Callback)
{
  _register_thread_local_exe_atexit_callback(Callback);
}

```

## disassembly

```asm
0x140013d48  jmp     cs:__imp__register_thread_local_exe_atexit_callback
```
