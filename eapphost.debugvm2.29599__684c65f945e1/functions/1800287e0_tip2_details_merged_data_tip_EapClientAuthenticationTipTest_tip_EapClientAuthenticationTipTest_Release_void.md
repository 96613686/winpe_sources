# tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::Release(void)

- ea: `0x1800287e0`
- end: `0x180028818`
- name: `?Release@?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022b84`
- `0x180022f18`
- `0x18002d08c`

## callees

- `0x180022bb8`
- `0x1800287e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028805`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028805`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 84);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::~merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x1800287e0  mov     [rsp+arg_0], rbx
0x1800287e5  push    rdi
0x1800287e6  sub     rsp, 20h
0x1800287ea  mov     rdi, rcx
0x1800287ed  or      ebx, 0FFFFFFFFh
0x1800287f0  lock xadd [rcx+150h], ebx
0x1800287f8  sub     ebx, 1
0x1800287fb  jnz     short loc_18002880B
0x1800287fd  call    ??1?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::~merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(void)
0x180028802  mov     rcx, rdi; pv
0x180028805  call    cs:__imp_CoTaskMemFree
0x18002880b  mov     eax, ebx
0x18002880d  mov     rbx, [rsp+28h+arg_0]
0x180028812  add     rsp, 20h
0x180028816  pop     rdi
0x180028817  retn
```
