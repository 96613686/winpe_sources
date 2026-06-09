# ATL::CComPtr<IMMDeviceEnumerator>::~CComPtr<IMMDeviceEnumerator>(void)

- ea: `0x18001d7a4`
- end: `0x18001d7c2`
- name: `??1?$CComPtr@UIMMDeviceEnumerator@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021c81`
- `0x180021c93`
- `0x180021ca5`
- `0x180021cb7`
- `0x180021cc9`
- `0x180021cdb`

## callees

- `0x18001d7a4`
- `0x180022010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IMMDeviceEnumerator>::~CComPtr<IMMDeviceEnumerator>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18001d7a4  sub     rsp, 28h
0x18001d7a8  mov     rcx, [rcx]
0x18001d7ab  test    rcx, rcx
0x18001d7ae  jz      short loc_18001D7BD
0x18001d7b0  mov     rax, [rcx]
0x18001d7b3  mov     rax, [rax+10h]
0x18001d7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7bc  nop
0x18001d7bd  add     rsp, 28h
0x18001d7c1  retn
```
