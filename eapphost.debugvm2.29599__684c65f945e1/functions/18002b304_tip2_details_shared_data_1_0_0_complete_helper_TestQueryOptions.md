# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18002b304`
- end: `0x18002b3b4`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022bb8`
- `0x180023924`

## callees

- `0x180002a90`
- `0x18002b304`
- `0x18002b548`
- `0x18002bb04`
- `0x18002e4a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b39b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b39b`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::complete_helper(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 v4; // r8
  __int64 v5; // rcx
  __int128 v6; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-38h]
  __int128 v8; // [rsp+40h] [rbp-28h]

  v2 = *(_DWORD *)(a1 + 232) == 0;
  v6 = 0;
  *(_OWORD *)pv = 0;
  v8 = 0;
  if ( !v2 )
    a2 = (unsigned int)a2 | 8;
  v4 = *(unsigned int *)(a1 + 184);
  v5 = *(_QWORD *)(a1 + 240);
  *(_QWORD *)(a1 + 240) = 0;
  if ( (unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *))TestQueryData)(v5, a2, v4, &v6) )
  {
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( pv[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v6);
    else
      *(_DWORD *)(a1 + 184) = pv[0];
    tip2::details::shared_data<1,0,0>::evaluate_and_report(a1, v8);
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x18002b304  push    rbx
0x18002b306  sub     rsp, 60h
0x18002b30a  mov     rax, cs:__security_cookie
0x18002b311  xor     rax, rsp
0x18002b314  mov     [rsp+68h+var_18], rax
0x18002b319  cmp     dword ptr [rcx+0E8h], 0
0x18002b320  xorps   xmm0, xmm0
0x18002b323  movups  [rsp+68h+var_48], xmm0
0x18002b328  mov     rbx, rcx
0x18002b32b  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18002b330  movups  [rsp+68h+var_28], xmm0
0x18002b335  jbe     short loc_18002B33A
0x18002b337  or      edx, 8
0x18002b33a  mov     r8d, [rcx+0B8h]
0x18002b341  lea     r9, [rsp+68h+var_48]
0x18002b346  mov     rcx, [rcx+0F0h]
0x18002b34d  mov     qword ptr [rbx+0F0h], 0
0x18002b358  call    TestQueryData
0x18002b35d  test    eax, eax
0x18002b35f  jz      short loc_18002B396
0x18002b361  mov     eax, dword ptr [rsp+68h+pv+4]
0x18002b365  or      [rbx+40h], eax
0x18002b368  cmp     [rsp+68h+pv+8], 0
0x18002b36e  jz      short loc_18002B37F
0x18002b370  lea     rdx, [rsp+68h+var_48]
0x18002b375  mov     rcx, rbx
0x18002b378  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18002b37d  jmp     short loc_18002B389
0x18002b37f  mov     eax, dword ptr [rsp+68h+pv]
0x18002b383  mov     [rbx+0B8h], eax
0x18002b389  mov     rdx, qword ptr [rsp+68h+var_28]
0x18002b38e  mov     rcx, rbx
0x18002b391  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x18002b396  mov     rcx, [rsp+68h+pv+8]; pv
0x18002b39b  call    cs:__imp_CoTaskMemFree
0x18002b3a1  mov     rcx, [rsp+68h+var_18]
0x18002b3a6  xor     rcx, rsp; StackCookie
0x18002b3a9  call    __security_check_cookie
0x18002b3ae  add     rsp, 60h
0x18002b3b2  pop     rbx
0x18002b3b3  retn
```
