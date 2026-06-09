# wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(void)

- ea: `0x18001134c`
- end: `0x18001136a`
- name: `??1?$com_ptr_t@UIOfflineFilesCache@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007bd0`
- `0x180016158`
- `0x180016b68`
- `0x18001e882`
- `0x18001ee65`
- `0x18001ee77`
- `0x18001ee9b`
- `0x18001eead`
- `0x18001eebf`

## callees

- `0x18001134c`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(
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
0x18001134c  sub     rsp, 28h
0x180011350  mov     rcx, [rcx]
0x180011353  test    rcx, rcx
0x180011356  jz      short loc_180011365
0x180011358  mov     rax, [rcx]
0x18001135b  mov     rax, [rax+10h]
0x18001135f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011364  nop
0x180011365  add     rsp, 28h
0x180011369  retn
```
