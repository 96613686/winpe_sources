# tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::Release(void)

- ea: `0x1800295c4`
- end: `0x180029603`
- name: `?Release@?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@AEAAKXZ`
- size: `63`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800237b4`
- `0x180023b80`
- `0x18002e0f8`

## callees

- `0x1800237ec`
- `0x1800295c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295e9`

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
0x1800295c4  mov     [rsp+arg_0], rbx
0x1800295c9  push    rdi
0x1800295ca  sub     rsp, 20h
0x1800295ce  mov     rdi, rcx
0x1800295d1  or      ebx, 0FFFFFFFFh
0x1800295d4  lock xadd [rcx+150h], ebx
0x1800295dc  sub     ebx, 1
0x1800295df  jnz     short loc_1800295F5
0x1800295e1  call    ??1?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::~merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(void)
0x1800295e6  mov     rcx, rdi; pv
0x1800295e9  call    cs:__imp_CoTaskMemFree
0x1800295f0  nop     dword ptr [rax+rax+00h]
0x1800295f5  mov     eax, ebx
0x1800295f7  mov     rbx, [rsp+28h+arg_0]
0x1800295fc  add     rsp, 20h
0x180029600  pop     rdi
0x180029601  retn
```
