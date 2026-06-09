# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x1800218e0`
- end: `0x180021914`
- name: `??_E?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::Windows::Performance::CElfImageEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x18002162c`
- `0x1800218e0`

## pseudocode

```c
Microsoft::Windows::Performance::CElfImageEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CElfImageEventTraceExtender *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800218e0  mov     [rsp+arg_0], rbx
0x1800218e5  push    rdi
0x1800218e6  sub     rsp, 20h
0x1800218ea  mov     ebx, edx
0x1800218ec  mov     rdi, rcx
0x1800218ef  call    ??1?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>(void)
0x1800218f4  test    bl, 1
0x1800218f7  jz      short loc_180021906
0x1800218f9  mov     edx, 50h ; 'P'; unsigned __int64
0x1800218fe  mov     rcx, rdi; void *
0x180021901  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021906  mov     rbx, [rsp+28h+arg_0]
0x18002190b  mov     rax, rdi
0x18002190e  add     rsp, 20h
0x180021912  pop     rdi
0x180021913  retn
```
