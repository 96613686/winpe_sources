# std::unique_ptr<IWpxConfig,ProvReleaser<IWpxConfig>>::~unique_ptr<IWpxConfig,ProvReleaser<IWpxConfig>>(void)

- ea: `0x180026600`
- end: `0x180026622`
- name: `??1?$unique_ptr@UIWpxConfig@@U?$ProvReleaser@UIWpxConfig@@@@@std@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180036d47`
- `0x180036e5e`

## callees

- `0x180026600`
- `0x180038010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<IWpxConfig,ProvReleaser<IWpxConfig>>::~unique_ptr<IWpxConfig,ProvReleaser<IWpxConfig>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 304LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180026600  sub     rsp, 28h
0x180026604  mov     rcx, [rcx]
0x180026607  test    rcx, rcx
0x18002660a  jz      short loc_18002661C
0x18002660c  mov     rax, [rcx]
0x18002660f  mov     rax, [rax+130h]
0x180026616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002661b  nop
0x18002661c  add     rsp, 28h
0x180026620  retn
```
