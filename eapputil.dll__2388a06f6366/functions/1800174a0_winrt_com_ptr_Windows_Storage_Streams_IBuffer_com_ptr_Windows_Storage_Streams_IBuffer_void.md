# winrt::com_ptr<Windows::Storage::Streams::IBuffer>::~com_ptr<Windows::Storage::Streams::IBuffer>(void)

- ea: `0x1800174a0`
- end: `0x1800174b4`
- name: `??1?$com_ptr@UIBuffer@Streams@Storage@Windows@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180031b72`
- `0x180031c02`
- `0x180031d0d`
- `0x180031d1f`
- `0x180031ecf`
- `0x180031ee1`
- `0x180031ef3`
- `0x180031f05`
- `0x180032672`
- `0x180032684`
- `0x180032735`

## callees

- `0x1800174a0`
- `0x180024f14`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<Windows::Storage::Streams::IBuffer>::~com_ptr<Windows::Storage::Streams::IBuffer>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x1800174a0  sub     rsp, 28h
0x1800174a4  cmp     qword ptr [rcx], 0
0x1800174a8  jz      short loc_1800174AF
0x1800174aa  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x1800174af  add     rsp, 28h
0x1800174b3  retn
```
