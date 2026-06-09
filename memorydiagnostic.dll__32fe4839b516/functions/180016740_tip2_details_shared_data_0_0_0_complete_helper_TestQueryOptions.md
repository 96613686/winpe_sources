# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180016740`
- end: `0x1800167e5`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `165`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800087a4`
- `0x180008be0`
- `0x180010ba8`

## callees

- `0x1800026b0`
- `0x180016740`
- `0x180016dfc`
- `0x18001a5fc`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800167c5`
- `ole32!CoTaskMemFree` at `0x1800167c5`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, __int64 a2)
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
    if ( !pv[1] )
      *(_DWORD *)(a1 + 184) = pv[0];
    tip2::details::shared_data<0,0,0>::evaluate_and_report(a1, v8);
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x180016740  push    rbx
0x180016742  sub     rsp, 60h
0x180016746  mov     rax, cs:__security_cookie
0x18001674d  xor     rax, rsp
0x180016750  mov     [rsp+68h+var_18], rax
0x180016755  cmp     dword ptr [rcx+0E8h], 0
0x18001675c  xorps   xmm0, xmm0
0x18001675f  movups  [rsp+68h+var_48], xmm0
0x180016764  mov     rbx, rcx
0x180016767  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18001676c  movups  [rsp+68h+var_28], xmm0
0x180016771  jbe     short loc_180016776
0x180016773  or      edx, 8
0x180016776  mov     r8d, [rcx+0B8h]
0x18001677d  lea     r9, [rsp+68h+var_48]
0x180016782  mov     rcx, [rcx+0F0h]
0x180016789  and     qword ptr [rbx+0F0h], 0
0x180016791  call    TestQueryData
0x180016796  test    eax, eax
0x180016798  jz      short loc_1800167C0
0x18001679a  mov     eax, dword ptr [rsp+68h+pv+4]
0x18001679e  or      [rbx+40h], eax
0x1800167a1  cmp     [rsp+68h+pv+8], 0
0x1800167a7  jnz     short loc_1800167B3
0x1800167a9  mov     eax, dword ptr [rsp+68h+pv]
0x1800167ad  mov     [rbx+0B8h], eax
0x1800167b3  mov     rdx, qword ptr [rsp+68h+var_28]
0x1800167b8  mov     rcx, rbx
0x1800167bb  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x1800167c0  mov     rcx, [rsp+68h+pv+8]; pv
0x1800167c5  call    cs:__imp_CoTaskMemFree
0x1800167cc  nop     dword ptr [rax+rax+00h]
0x1800167d1  mov     rcx, [rsp+68h+var_18]
0x1800167d6  xor     rcx, rsp; StackCookie
0x1800167d9  call    __security_check_cookie
0x1800167de  add     rsp, 60h
0x1800167e2  pop     rbx
0x1800167e3  retn
```
