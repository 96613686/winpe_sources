# ATL::CComPtrBase<ITPLangMod>::~CComPtrBase<ITPLangMod>(void)

- ea: `0x14000f93c`
- end: `0x14000f95a`
- name: `??1?$CComPtrBase@UITPLangMod@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000f930`
- `0x14000f960`
- `0x14000fe10`
- `0x140014408`
- `0x140018a60`
- `0x140019dc4`
- `0x14001a018`
- `0x14001acc0`

## callees

- `0x14000f93c`
- `0x140027010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<ITPLangMod>::~CComPtrBase<ITPLangMod>(__int64 *a1)
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
0x14000f93c  sub     rsp, 28h
0x14000f940  mov     rcx, [rcx]
0x14000f943  test    rcx, rcx
0x14000f946  jz      short loc_14000F955
0x14000f948  mov     rax, [rcx]
0x14000f94b  mov     rax, [rax+10h]
0x14000f94f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f954  nop
0x14000f955  add     rsp, 28h
0x14000f959  retn
```
