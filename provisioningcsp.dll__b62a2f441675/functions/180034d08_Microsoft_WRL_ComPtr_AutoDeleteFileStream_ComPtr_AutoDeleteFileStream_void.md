# Microsoft::WRL::ComPtr<AutoDeleteFileStream>::~ComPtr<AutoDeleteFileStream>(void)

- ea: `0x180034d08`
- end: `0x180034d29`
- name: `??1?$ComPtr@VAutoDeleteFileStream@@@WRL@Microsoft@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180037815`

## callees

- `0x180034d08`
- `0x1800350e0`

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
0x180034d08  sub     rsp, 28h
0x180034d0c  mov     rax, [rcx]
0x180034d0f  test    rax, rax
0x180034d12  jz      short loc_180034D23
0x180034d14  mov     qword ptr [rcx], 0
0x180034d1b  mov     rcx, rax
0x180034d1e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIStream@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IStream>::Release(void)
0x180034d23  add     rsp, 28h
0x180034d27  retn
```
