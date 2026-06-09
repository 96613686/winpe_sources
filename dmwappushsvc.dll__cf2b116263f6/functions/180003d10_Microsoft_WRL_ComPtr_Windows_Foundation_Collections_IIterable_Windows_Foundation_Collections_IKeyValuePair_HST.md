# Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)

- ea: `0x180003d10`
- end: `0x180003d36`
- name: `?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002dc0`
- `0x180002e94`
- `0x1800030e4`
- `0x180003764`
- `0x180003808`
- `0x1800087c0`

## callees

- `0x180003d10`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(
        __int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180003d10  sub     rsp, 28h
0x180003d14  mov     rdx, rcx
0x180003d17  xor     eax, eax
0x180003d19  mov     rcx, [rcx]
0x180003d1c  test    rcx, rcx
0x180003d1f  jz      short loc_180003D31
0x180003d21  mov     [rdx], rax
0x180003d24  mov     rax, [rcx]
0x180003d27  mov     rax, [rax+10h]
0x180003d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d30  nop
0x180003d31  add     rsp, 28h
0x180003d35  retn
```
