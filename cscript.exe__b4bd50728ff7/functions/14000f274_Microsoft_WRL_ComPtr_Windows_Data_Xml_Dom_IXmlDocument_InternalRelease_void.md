# Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)

- ea: `0x14000f274`
- end: `0x14000f299`
- name: `?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ee7c`
- `0x14000f464`

## callees

- `0x14000f274`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(__int64 *a1)
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
0x14000f274  sub     rsp, 28h
0x14000f278  mov     rdx, rcx
0x14000f27b  xor     eax, eax
0x14000f27d  mov     rcx, [rcx]
0x14000f280  test    rcx, rcx
0x14000f283  jz      short loc_14000F294
0x14000f285  mov     [rdx], rax
0x14000f288  mov     rax, [rcx]
0x14000f28b  mov     rax, [rax+10h]
0x14000f28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f294  add     rsp, 28h
0x14000f298  retn
```
