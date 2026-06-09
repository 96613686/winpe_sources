# ATL::CComTypeInfoHolder::stringdispid::stringdispid(void)

- ea: `0x18000d600`
- end: `0x18000d619`
- name: `??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ`
- size: `25`
- prototype: `ATL::CComTypeInfoHolder::stringdispid *__fastcall(ATL::CComTypeInfoHolder::stringdispid *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
ATL::CComTypeInfoHolder::stringdispid *__fastcall ATL::CComTypeInfoHolder::stringdispid::stringdispid(
        ATL::CComTypeInfoHolder::stringdispid *this)
{
  ATL::CComTypeInfoHolder::stringdispid *result; // rax

  *(_QWORD *)this = 0;
  result = this;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 3) = -1;
  return result;
}

```

## disassembly

```asm
0x18000d600  mov     qword ptr [rcx], 0
0x18000d607  mov     rax, rcx
0x18000d60a  mov     dword ptr [rcx+8], 0
0x18000d611  mov     dword ptr [rcx+0Ch], 0FFFFFFFFh
0x18000d618  retn
```
