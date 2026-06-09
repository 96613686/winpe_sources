# ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vector deleting destructor'(uint)

- ea: `0x180009470`
- end: `0x1800094a4`
- name: `??_E?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x180008fe8`
- `0x180009470`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::~CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180009470  mov     [rsp+arg_0], rbx
0x180009475  push    rdi
0x180009476  sub     rsp, 20h
0x18000947a  mov     ebx, edx
0x18000947c  mov     rdi, rcx
0x18000947f  call    ??1?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::~CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>(void)
0x180009484  test    bl, 1
0x180009487  jz      short loc_180009496
0x180009489  mov     edx, 10h; unsigned __int64
0x18000948e  mov     rcx, rdi; void *
0x180009491  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009496  mov     rbx, [rsp+28h+arg_0]
0x18000949b  mov     rax, rdi
0x18000949e  add     rsp, 20h
0x1800094a2  pop     rdi
0x1800094a3  retn
```
