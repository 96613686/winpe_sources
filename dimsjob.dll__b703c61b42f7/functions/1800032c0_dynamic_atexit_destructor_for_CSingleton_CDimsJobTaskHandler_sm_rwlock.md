# _dynamic_atexit_destructor_for__CSingleton_CDimsJobTaskHandler_::sm_rwlock__

- ea: `0x1800032c0`
- end: `0x1800032c5`
- name: `_dynamic_atexit_destructor_for__CSingleton_CDimsJobTaskHandler_::sm_rwlock__`
- size: `5`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003c80`

## pseudocode

```c
// attributes: thunk
__int64 dynamic_atexit_destructor_for__CSingleton_CDimsJobTaskHandler_::sm_rwlock__()
{
  return wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy();
}

```

## disassembly

```asm
0x1800032c0  jmp     ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
```
