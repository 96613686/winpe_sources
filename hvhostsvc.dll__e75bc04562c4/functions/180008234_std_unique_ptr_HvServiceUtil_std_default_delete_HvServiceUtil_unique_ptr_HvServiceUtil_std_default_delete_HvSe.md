# std::unique_ptr<HvServiceUtil,std::default_delete<HvServiceUtil>>::~unique_ptr<HvServiceUtil,std::default_delete<HvServiceUtil>>(void)

- ea: `0x180008234`
- end: `0x18000824a`
- name: `??1?$unique_ptr@VHvServiceUtil@@U?$default_delete@VHvServiceUtil@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800082fc`
- `0x1800084f4`

## callees

- `0x180008234`
- `0x180008380`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<HvServiceUtil>::~unique_ptr<HvServiceUtil>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<HvServiceUtil>::operator()();
  return result;
}

```

## disassembly

```asm
0x180008234  sub     rsp, 28h
0x180008238  mov     rdx, [rcx]
0x18000823b  test    rdx, rdx
0x18000823e  jz      short loc_180008245
0x180008240  call    ??R?$default_delete@VHvServiceUtil@@@std@@QEBAXPEAVHvServiceUtil@@@Z; std::default_delete<HvServiceUtil>::operator()(HvServiceUtil *)
0x180008245  add     rsp, 28h
0x180008249  retn
```
