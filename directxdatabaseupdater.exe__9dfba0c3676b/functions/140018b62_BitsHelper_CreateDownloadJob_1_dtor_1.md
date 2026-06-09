# _BitsHelper::CreateDownloadJob_::_1_::dtor$1

- ea: `0x140018b62`
- end: `0x140018b8b`
- name: `_BitsHelper::CreateDownloadJob_::_1_::dtor$1`
- size: `41`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005c14`
- `0x140018b62`

## pseudocode

```c
__int64 __fastcall BitsHelper::CreateDownloadJob_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 56) & 2;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 56) &= ~2u;
    return std::wstring::~wstring(a2 + 144);
  }
  return result;
}

```

## disassembly

```asm
0x140018b62  push    rbp
0x140018b64  sub     rsp, 20h
0x140018b68  mov     rbp, rdx
0x140018b6b  mov     eax, [rbp+38h]
0x140018b6e  and     eax, 2
0x140018b71  test    eax, eax
0x140018b73  jz      short loc_140018B85
0x140018b75  and     dword ptr [rbp+38h], 0FFFFFFFDh
0x140018b79  lea     rcx, [rbp+90h]
0x140018b80  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018b85  add     rsp, 20h
0x140018b89  pop     rbp
0x140018b8a  retn
```
