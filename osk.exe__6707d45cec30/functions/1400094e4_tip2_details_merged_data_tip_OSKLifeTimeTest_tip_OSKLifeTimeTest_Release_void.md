# tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>::Release(void)

- ea: `0x1400094e4`
- end: `0x14000951c`
- name: `?Release@?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140004f1c`
- `0x14000ba30`
- `0x14000c950`

## callees

- `0x140004f5c`
- `0x1400094e4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140009509`
- `ole32!CoTaskMemFree` at `0x140009509`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>::~merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x1400094e4  mov     [rsp+arg_0], rbx
0x1400094e9  push    rdi
0x1400094ea  sub     rsp, 20h
0x1400094ee  mov     rdi, rcx
0x1400094f1  or      ebx, 0FFFFFFFFh
0x1400094f4  lock xadd [rcx+118h], ebx
0x1400094fc  sub     ebx, 1
0x1400094ff  jnz     short loc_14000950F
0x140009501  call    ??1?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>::~merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>(void)
0x140009506  mov     rcx, rdi; pv
0x140009509  call    cs:__imp_CoTaskMemFree
0x14000950f  mov     eax, ebx
0x140009511  mov     rbx, [rsp+28h+arg_0]
0x140009516  add     rsp, 20h
0x14000951a  pop     rdi
0x14000951b  retn
```
