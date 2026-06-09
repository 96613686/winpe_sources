# CDwmHwndData::RemoveElement(HWND__ *)

- ea: `0x180001008`
- end: `0x180001051`
- name: `?RemoveElement@CDwmHwndData@@CA_NPEAUHWND__@@@Z`
- size: `73`
- prototype: `bool __fastcall(HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800019b0`

## callees

- `0x180001008`
- `0x180005c64`
- `0x1800061c0`
- `0x180009adc`

## import_xrefs

- `ntdll!RtlNumberGenericTableElements` at `0x18000103a`
- `ntdll!RtlNumberGenericTableElements` at `0x18000103a`

## pseudocode

```c
bool __fastcall CDwmHwndData::RemoveElement(__int64 a1)
{
  CDwmHwndData *Element; // rax
  CDwmHwndData *v2; // rbx
  bool v3; // bl

  Element = (CDwmHwndData *)CGenericTableMap<unsigned __int64,CDwmHwndData>::FindElement(a1, a1);
  v2 = Element;
  if ( Element )
    CGenericTableMap<unsigned __int64,CDwmHwndData>::RemoveElement(&CDwmHwndData::s_dwmHwndDataMap, Element);
  v3 = v2 != 0;
  if ( !RtlNumberGenericTableElements(&CDwmHwndData::s_dwmHwndDataMap) )
    CDwmHwndData::RemoveWindowCleanupHook();
  return v3;
}

```

## disassembly

```asm
0x180001008  push    rbx
0x18000100a  sub     rsp, 20h
0x18000100e  mov     rdx, rcx
0x180001011  call    ?FindElement@?$CGenericTableMap@_KVCDwmHwndData@@@@QEAAPEAVCDwmHwndData@@_K@Z; CGenericTableMap<unsigned __int64,CDwmHwndData>::FindElement(unsigned __int64)
0x180001016  mov     rbx, rax
0x180001019  test    rax, rax
0x18000101c  jz      short loc_18000102D
0x18000101e  mov     rdx, rax; this
0x180001021  lea     rcx, ?s_dwmHwndDataMap@CDwmHwndData@@0V?$CGenericTableMap@_KVCDwmHwndData@@@@A; Table
0x180001028  call    ?RemoveElement@?$CGenericTableMap@_KVCDwmHwndData@@@@QEAAXPEAVCDwmHwndData@@@Z; CGenericTableMap<unsigned __int64,CDwmHwndData>::RemoveElement(CDwmHwndData *)
0x18000102d  test    rbx, rbx
0x180001030  lea     rcx, ?s_dwmHwndDataMap@CDwmHwndData@@0V?$CGenericTableMap@_KVCDwmHwndData@@@@A; Table
0x180001037  setnz   bl
0x18000103a  call    cs:__imp_RtlNumberGenericTableElements
0x180001040  test    eax, eax
0x180001042  jnz     short loc_180001049
0x180001044  call    ?RemoveWindowCleanupHook@CDwmHwndData@@SAXXZ; CDwmHwndData::RemoveWindowCleanupHook(void)
0x180001049  mov     al, bl
0x18000104b  add     rsp, 20h
0x18000104f  pop     rbx
0x180001050  retn
```
