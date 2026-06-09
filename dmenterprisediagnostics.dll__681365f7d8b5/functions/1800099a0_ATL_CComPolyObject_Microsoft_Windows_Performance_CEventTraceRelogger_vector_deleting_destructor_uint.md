# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(uint)

- ea: `0x1800099a0`
- end: `0x1800099d5`
- name: `??_E?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001824`
- `0x1800094d4`
- `0x1800099a0`

## pseudocode

```c
void *__fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::~CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800099a0  mov     [rsp+arg_0], rbx
0x1800099a5  push    rdi
0x1800099a6  sub     rsp, 20h
0x1800099aa  mov     ebx, edx
0x1800099ac  mov     rdi, rcx
0x1800099af  call    ??1?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::~CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>(void)
0x1800099b4  test    bl, 1
0x1800099b7  jz      short loc_1800099C6
0x1800099b9  mov     edx, 0C0h; unsigned __int64
0x1800099be  mov     rcx, rdi; void *
0x1800099c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800099c6  mov     rbx, [rsp+28h+arg_0]
0x1800099cb  mov     rax, rdi
0x1800099ce  add     rsp, 20h
0x1800099d2  pop     rdi
0x1800099d3  retn
```
