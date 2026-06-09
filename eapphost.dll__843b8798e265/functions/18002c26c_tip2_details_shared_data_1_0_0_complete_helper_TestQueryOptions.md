# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18002c26c`
- end: `0x18002c323`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800237ec`
- `0x180024604`

## callees

- `0x180002af0`
- `0x18002c26c`
- `0x18002c4bc`
- `0x18002ca94`
- `0x18002f550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c303`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c303`

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
0x18002c26c  push    rbx
0x18002c26e  sub     rsp, 60h
0x18002c272  mov     rax, cs:__security_cookie
0x18002c279  xor     rax, rsp
0x18002c27c  mov     [rsp+68h+var_18], rax
0x18002c281  cmp     dword ptr [rcx+0E8h], 0
0x18002c288  xorps   xmm0, xmm0
0x18002c28b  movups  [rsp+68h+var_48], xmm0
0x18002c290  mov     rbx, rcx
0x18002c293  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18002c298  movups  [rsp+68h+var_28], xmm0
0x18002c29d  jbe     short loc_18002C2A2
0x18002c29f  or      edx, 8
0x18002c2a2  mov     r8d, [rcx+0B8h]
0x18002c2a9  lea     r9, [rsp+68h+var_48]
0x18002c2ae  mov     rcx, [rcx+0F0h]
0x18002c2b5  mov     qword ptr [rbx+0F0h], 0
0x18002c2c0  call    TestQueryData
0x18002c2c5  test    eax, eax
0x18002c2c7  jz      short loc_18002C2FE
0x18002c2c9  mov     eax, dword ptr [rsp+68h+pv+4]
0x18002c2cd  or      [rbx+40h], eax
0x18002c2d0  cmp     [rsp+68h+pv+8], 0
0x18002c2d6  jz      short loc_18002C2E7
0x18002c2d8  lea     rdx, [rsp+68h+var_48]
0x18002c2dd  mov     rcx, rbx
0x18002c2e0  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18002c2e5  jmp     short loc_18002C2F1
0x18002c2e7  mov     eax, dword ptr [rsp+68h+pv]
0x18002c2eb  mov     [rbx+0B8h], eax
0x18002c2f1  mov     rdx, qword ptr [rsp+68h+var_28]
0x18002c2f6  mov     rcx, rbx
0x18002c2f9  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x18002c2fe  mov     rcx, [rsp+68h+pv+8]; pv
0x18002c303  call    cs:__imp_CoTaskMemFree
0x18002c30a  nop     dword ptr [rax+rax+00h]
0x18002c30f  mov     rcx, [rsp+68h+var_18]
0x18002c314  xor     rcx, rsp; StackCookie
0x18002c317  call    __security_check_cookie
0x18002c31c  add     rsp, 60h
0x18002c320  pop     rbx
0x18002c321  retn
```
