# Microsoft::WRL::ComPtr<AutoDeleteFileStream>::~ComPtr<AutoDeleteFileStream>(void)

- ea: `0x14000d2b4`
- end: `0x14000d2d4`
- name: `??1?$ComPtr@VAutoDeleteFileStream@@@WRL@Microsoft@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000edfa`

## callees

- `0x14000d2b4`
- `0x14000d6f0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<AutoDeleteFileStream>::~ComPtr<AutoDeleteFileStream>(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IStream>::Release(result);
  }
  return result;
}

```

## disassembly

```asm
0x14000d2b4  sub     rsp, 28h
0x14000d2b8  mov     rax, [rcx]
0x14000d2bb  test    rax, rax
0x14000d2be  jz      short loc_14000D2CF
0x14000d2c0  mov     qword ptr [rcx], 0
0x14000d2c7  mov     rcx, rax
0x14000d2ca  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIStream@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IStream>::Release(void)
0x14000d2cf  add     rsp, 28h
0x14000d2d3  retn
```
