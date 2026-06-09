# ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vector deleting destructor'(uint)

- ea: `0x180009920`
- end: `0x180009955`
- name: `??_E?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001824`
- `0x180009468`
- `0x180009920`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::~CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>();
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180009920  mov     [rsp+arg_0], rbx
0x180009925  push    rdi
0x180009926  sub     rsp, 20h
0x18000992a  mov     ebx, edx
0x18000992c  mov     rdi, rcx
0x18000992f  call    ??1?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::~CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>(void)
0x180009934  test    bl, 1
0x180009937  jz      short loc_180009946
0x180009939  mov     edx, 10h; unsigned __int64
0x18000993e  mov     rcx, rdi; void *
0x180009941  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009946  mov     rbx, [rsp+28h+arg_0]
0x18000994b  mov     rax, rdi
0x18000994e  add     rsp, 20h
0x180009952  pop     rdi
0x180009953  retn
```
