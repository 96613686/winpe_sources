# ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x1800098e0`
- end: `0x180009915`
- name: `??_E?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001824`
- `0x180009428`
- `0x1800098e0`

## pseudocode

```c
Microsoft::Windows::Performance::CEventTraceExtenderBase *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800098e0  mov     [rsp+arg_0], rbx
0x1800098e5  push    rdi
0x1800098e6  sub     rsp, 20h
0x1800098ea  mov     ebx, edx
0x1800098ec  mov     rdi, rcx
0x1800098ef  call    ??1?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(void)
0x1800098f4  test    bl, 1
0x1800098f7  jz      short loc_180009906
0x1800098f9  mov     edx, 28h ; '('; unsigned __int64
0x1800098fe  mov     rcx, rdi; void *
0x180009901  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009906  mov     rbx, [rsp+28h+arg_0]
0x18000990b  mov     rax, rdi
0x18000990e  add     rsp, 20h
0x180009912  pop     rdi
0x180009913  retn
```
