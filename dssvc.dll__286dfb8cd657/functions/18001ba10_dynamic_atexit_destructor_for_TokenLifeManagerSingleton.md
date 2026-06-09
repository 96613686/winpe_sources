# _dynamic_atexit_destructor_for__TokenLifeManagerSingleton__

- ea: `0x18001ba10`
- end: `0x18001ba66`
- name: `_dynamic_atexit_destructor_for__TokenLifeManagerSingleton__`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800055a0`
- `0x18001ba10`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001ba37`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001ba37`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001ba55`

## pseudocode

```c
int dynamic_atexit_destructor_for__TokenLifeManagerSingleton__()
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v2; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v2 = 0;
  InitOnceBeginInitialize(&TokenLifeManagerSingleton, 0, &v1, &v2);
  if ( v2 )
    return wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy();
  else
    return InitOnceComplete(&TokenLifeManagerSingleton, 0, 0);
}

```

## disassembly

```asm
0x18001ba10  mov     rax, rsp
0x18001ba13  sub     rsp, 28h
0x18001ba17  lea     r9, [rax+10h]; lpContext
0x18001ba1b  mov     dword ptr [rax+8], 0
0x18001ba22  lea     r8, [rax+8]; fPending
0x18001ba26  mov     qword ptr [rax+10h], 0
0x18001ba2e  xor     edx, edx; dwFlags
0x18001ba30  lea     rcx, ?TokenLifeManagerSingleton@@3V?$static_lazy@VTokenLifeManager@@$0A@V?$lazy_construct@VTokenLifeManager@@@tlx@@@tlx@@A; lpInitOnce
0x18001ba37  call    cs:__imp_InitOnceBeginInitialize
0x18001ba3d  cmp     [rsp+28h+arg_8], 0
0x18001ba43  jnz     short loc_18001BA5C
0x18001ba45  xor     r8d, r8d
0x18001ba48  lea     rcx, ?TokenLifeManagerSingleton@@3V?$static_lazy@VTokenLifeManager@@$0A@V?$lazy_construct@VTokenLifeManager@@@tlx@@@tlx@@A; tlx::static_lazy<TokenLifeManager,0,tlx::lazy_construct<TokenLifeManager>> TokenLifeManagerSingleton
0x18001ba4f  xor     edx, edx
0x18001ba51  add     rsp, 28h
0x18001ba55  jmp     cs:__imp_InitOnceComplete
0x18001ba5c  call    ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18001ba61  add     rsp, 28h
0x18001ba65  retn
```
