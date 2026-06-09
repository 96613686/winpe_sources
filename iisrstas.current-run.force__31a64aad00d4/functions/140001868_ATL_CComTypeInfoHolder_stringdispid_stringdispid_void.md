# ATL::CComTypeInfoHolder::stringdispid::stringdispid(void)

- ea: `0x140001868`
- end: `0x140001881`
- name: `??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ`
- size: `25`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder::stringdispid *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400023fc`

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
0x140001868  mov     qword ptr [rcx], 0
0x14000186f  mov     rax, rcx
0x140001872  mov     dword ptr [rcx+8], 0
0x140001879  mov     dword ptr [rcx+0Ch], 0FFFFFFFFh
0x140001880  retn
```
