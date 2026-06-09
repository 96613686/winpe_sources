# _dynamic_atexit_destructor_for__g_work__

- ea: `0x18000ce50`
- end: `0x18000ce7f`
- name: `_dynamic_atexit_destructor_for__g_work__`
- size: `47`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ce50`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000ce6a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000ce6a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000ce73`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000ce73`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_work__()
{
  struct _TP_WORK *v0; // rbx

  v0 = pwk;
  if ( pwk )
  {
    WaitForThreadpoolWorkCallbacks(pwk, 1);
    CloseThreadpoolWork(v0);
  }
}

```

## disassembly

```asm
0x18000ce50  push    rbx
0x18000ce52  sub     rsp, 20h
0x18000ce56  mov     rbx, cs:pwk
0x18000ce5d  test    rbx, rbx
0x18000ce60  jz      short loc_18000CE79
0x18000ce62  mov     edx, 1; fCancelPendingCallbacks
0x18000ce67  mov     rcx, rbx; pwk
0x18000ce6a  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000ce70  mov     rcx, rbx; pwk
0x18000ce73  call    cs:__imp_CloseThreadpoolWork
0x18000ce79  add     rsp, 20h
0x18000ce7d  pop     rbx
0x18000ce7e  retn
```
