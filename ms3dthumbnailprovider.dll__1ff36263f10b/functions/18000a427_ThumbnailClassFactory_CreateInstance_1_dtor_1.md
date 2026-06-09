# _ThumbnailClassFactory::CreateInstance_::_1_::dtor$1

- ea: `0x18000a427`
- end: `0x18000a44d`
- name: `_ThumbnailClassFactory::CreateInstance_::_1_::dtor$1`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002b68`
- `0x18000a427`

## pseudocode

```c
_QWORD *__fastcall ThumbnailClassFactory::CreateInstance_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 120) & 1);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 120) &= ~1u;
    return Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>((_QWORD *)(a2 + 32));
  }
  return result;
}

```

## disassembly

```asm
0x18000a427  push    rbp
0x18000a429  sub     rsp, 20h
0x18000a42d  mov     rbp, rdx
0x18000a430  mov     eax, [rbp+78h]
0x18000a433  and     eax, 1
0x18000a436  test    eax, eax
0x18000a438  jz      short loc_18000A447
0x18000a43a  and     dword ptr [rbp+78h], 0FFFFFFFEh
0x18000a43e  lea     rcx, [rbp+20h]
0x18000a442  call    ??1?$ComPtr@UIShellItemArray@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>(void)
0x18000a447  add     rsp, 20h
0x18000a44b  pop     rbp
0x18000a44c  retn
```
