# std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(void)

- ea: `0x1800159ac`
- end: `0x1800159ca`
- name: `??1?$unique_ptr@UIUnknown@@UReleaseDelete@XmlReader@@@std@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `23`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013ca4`
- `0x18001443c`
- `0x180014ff4`
- `0x18001cdcc`
- `0x18001cfb0`
- `0x18001d5c8`
- `0x18001dc58`
- `0x180029f04`
- `0x180033924`
- `0x18004a234`
- `0x18004a26a`
- `0x18004a28e`
- `0x18004a2c4`
- `0x18004a2d6`
- `0x18004a342`
- `0x18004a3e4`
- `0x18004a450`
- `0x18004a462`
- `0x18004a474`
- `0x18004a486`
- `0x18004a698`
- `0x18004a745`
- `0x18004a757`

## callees

- `0x1800159ac`
- `0x18004c010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(
        __int64 *a1)
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
0x1800159ac  sub     rsp, 28h
0x1800159b0  mov     rcx, [rcx]
0x1800159b3  test    rcx, rcx
0x1800159b6  jz      short loc_1800159C5
0x1800159b8  mov     rax, [rcx]
0x1800159bb  mov     rax, [rax+10h]
0x1800159bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159c4  nop
0x1800159c5  add     rsp, 28h
0x1800159c9  retn
```
