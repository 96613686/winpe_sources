# com_autoptr<IShellFolder>::~com_autoptr<IShellFolder>(void)

- ea: `0x180005bf0`
- end: `0x180005c2e`
- name: `??1?$com_autoptr@UIShellFolder@@@@UEAA@XZ`
- size: `62`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d05f`
- `0x18001d071`
- `0x18001d083`
- `0x18001d3e5`
- `0x18001d409`
- `0x18001d41b`
- `0x18001e113`

## callees

- `0x180005bf0`
- `0x18001f010`

## pseudocode

```c
void **__fastcall com_autoptr<IShellFolder>::~com_autoptr<IShellFolder>(__int64 a1)
{
  __int64 v2; // rcx
  void **result; // rax

  *(_QWORD *)a1 = &com_autoptr<IDiskQuotaControl>::`vftable';
  if ( *(_DWORD *)(a1 + 8) )
  {
    v2 = *(_QWORD *)(a1 + 16);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  result = &a_ptr<IDiskQuotaUser>::`vftable';
  *(_QWORD *)a1 = &a_ptr<IDiskQuotaUser>::`vftable';
  return result;
}

```

## disassembly

```asm
0x180005bf0  push    rbx
0x180005bf2  sub     rsp, 20h
0x180005bf6  mov     rbx, rcx
0x180005bf9  lea     rax, ??_7?$com_autoptr@UIDiskQuotaControl@@@@6B@; const com_autoptr<IDiskQuotaControl>::`vftable'
0x180005c00  mov     [rcx], rax
0x180005c03  cmp     dword ptr [rcx+8], 0
0x180005c07  jz      short loc_180005C1E
0x180005c09  mov     rcx, [rcx+10h]
0x180005c0d  test    rcx, rcx
0x180005c10  jz      short loc_180005C1E
0x180005c12  mov     rax, [rcx]
0x180005c15  mov     rax, [rax+10h]
0x180005c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c1e  lea     rax, ??_7?$a_ptr@UIDiskQuotaUser@@@@6B@; const a_ptr<IDiskQuotaUser>::`vftable'
0x180005c25  mov     [rbx], rax
0x180005c28  add     rsp, 20h
0x180005c2c  pop     rbx
0x180005c2d  retn
```
