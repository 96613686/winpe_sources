# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180022630`
- end: `0x180022665`
- name: `??_E?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001824`
- `0x180022368`
- `0x180022630`

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
0x180022630  mov     [rsp+arg_0], rbx
0x180022635  push    rdi
0x180022636  sub     rsp, 20h
0x18002263a  mov     ebx, edx
0x18002263c  mov     rdi, rcx
0x18002263f  call    ??1?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>(void)
0x180022644  test    bl, 1
0x180022647  jz      short loc_180022656
0x180022649  mov     edx, 50h ; 'P'; unsigned __int64
0x18002264e  mov     rcx, rdi; void *
0x180022651  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022656  mov     rbx, [rsp+28h+arg_0]
0x18002265b  mov     rax, rdi
0x18002265e  add     rsp, 20h
0x180022662  pop     rdi
0x180022663  retn
```
