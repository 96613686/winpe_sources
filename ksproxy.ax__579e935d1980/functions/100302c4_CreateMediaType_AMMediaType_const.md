# CreateMediaType(_AMMediaType const *)

- ea: `0x100302c4`
- end: `0x100302f7`
- name: `?CreateMediaType@@YGPAU_AMMediaType@@PBU1@@Z`
- size: `51`
- prototype: `struct _AMMediaType *__stdcall(const struct _AMMediaType *)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10016a04`
- `0x1001b560`
- `0x1002cd60`
- `0x100328c0`
- `0x10032910`
- `0x10032a10`

## callees

- `0x100302c4`
- `0x100302fd`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x100302cc`
- `ole32!CoTaskMemAlloc` at `0x100302cc`
- `ole32!CoTaskMemFree` at `0x100302ea`
- `ole32!CoTaskMemFree` at `0x100302ea`

## pseudocode

```c
struct _AMMediaType *__stdcall CreateMediaType()
{
  void *v0; // esi
  struct _AMMediaType *v2; // [esp+0h] [ebp-8h]
  const struct _AMMediaType *v3; // [esp+4h] [ebp-4h]

  v0 = CoTaskMemAlloc(0x48u);
  if ( !v0 )
    return 0;
  if ( CopyMediaType(v2, v3) < 0 )
  {
    CoTaskMemFree(v0);
    return 0;
  }
  return (struct _AMMediaType *)v0;
}

```

## disassembly

```asm
0x100302c4  mov     edi, edi
0x100302c6  push    esi; const struct _AMMediaType *
0x100302c7  push    edi; struct _AMMediaType *
0x100302c8  push    48h ; 'H'; cb
0x100302ca  mov     edi, ecx
0x100302cc  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100302d2  mov     esi, eax
0x100302d4  test    esi, esi
0x100302d6  jnz     short loc_100302DC
0x100302d8  xor     eax, eax
0x100302da  jmp     short loc_100302F4
0x100302dc  mov     edx, edi
0x100302de  mov     ecx, esi
0x100302e0  call    ?CopyMediaType@@YGJPAU_AMMediaType@@PBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x100302e5  test    eax, eax
0x100302e7  jns     short loc_100302F2
0x100302e9  push    esi; pv
0x100302ea  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x100302f0  jmp     short loc_100302D8
0x100302f2  mov     eax, esi
0x100302f4  pop     edi
0x100302f5  pop     esi
0x100302f6  retn
```
