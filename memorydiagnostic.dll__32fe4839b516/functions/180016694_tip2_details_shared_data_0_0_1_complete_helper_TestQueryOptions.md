# tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)

- ea: `0x180016694`
- end: `0x180016739`
- name: `?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007bf0`
- `0x1800165dc`

## callees

- `0x1800026b0`
- `0x180016694`
- `0x180016b34`
- `0x18001a5fc`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180016719`
- `ole32!CoTaskMemFree` at `0x180016719`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::complete_helper(__int64 a1, __int64 a2)
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
    tip2::details::shared_data<0,0,1>::evaluate_and_report((_DWORD *)a1, v8);
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x180016694  push    rbx
0x180016696  sub     rsp, 60h
0x18001669a  mov     rax, cs:__security_cookie
0x1800166a1  xor     rax, rsp
0x1800166a4  mov     [rsp+68h+var_18], rax
0x1800166a9  cmp     dword ptr [rcx+0E8h], 0
0x1800166b0  xorps   xmm0, xmm0
0x1800166b3  movups  [rsp+68h+var_48], xmm0
0x1800166b8  mov     rbx, rcx
0x1800166bb  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1800166c0  movups  [rsp+68h+var_28], xmm0
0x1800166c5  jbe     short loc_1800166CA
0x1800166c7  or      edx, 8
0x1800166ca  mov     r8d, [rcx+0B8h]
0x1800166d1  lea     r9, [rsp+68h+var_48]
0x1800166d6  mov     rcx, [rcx+0F0h]
0x1800166dd  and     qword ptr [rbx+0F0h], 0
0x1800166e5  call    TestQueryData
0x1800166ea  test    eax, eax
0x1800166ec  jz      short loc_180016714
0x1800166ee  mov     eax, dword ptr [rsp+68h+pv+4]
0x1800166f2  or      [rbx+40h], eax
0x1800166f5  cmp     [rsp+68h+pv+8], 0
0x1800166fb  jnz     short loc_180016707
0x1800166fd  mov     eax, dword ptr [rsp+68h+pv]
0x180016701  mov     [rbx+0B8h], eax
0x180016707  mov     rdx, qword ptr [rsp+68h+var_28]
0x18001670c  mov     rcx, rbx
0x18001670f  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)
0x180016714  mov     rcx, [rsp+68h+pv+8]; pv
0x180016719  call    cs:__imp_CoTaskMemFree
0x180016720  nop     dword ptr [rax+rax+00h]
0x180016725  mov     rcx, [rsp+68h+var_18]
0x18001672a  xor     rcx, rsp; StackCookie
0x18001672d  call    __security_check_cookie
0x180016732  add     rsp, 60h
0x180016736  pop     rbx
0x180016737  retn
```
