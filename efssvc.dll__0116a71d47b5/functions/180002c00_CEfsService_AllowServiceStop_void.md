# CEfsService::AllowServiceStop(void)

- ea: `0x180002c00`
- end: `0x180002c5a`
- name: `?AllowServiceStop@CEfsService@@AEAA_NXZ`
- size: `90`
- prototype: `bool __fastcall(CEfsService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180002ee0`

## callees

- `0x180002c00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002c48`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002c48`

## string_xrefs

- `0x180002c27`: `AllowServiceStop`
- `0x180002c32`: `SYSTEM\CurrentControlSet\Services\EFS`

## pseudocode

```c
bool __fastcall CEfsService::AllowServiceStop(CEfsService *this)
{
  _DWORD *v1; // rbx
  DWORD v3; // [rsp+50h] [rbp+8h] BYREF

  v1 = (_DWORD *)((char *)this + 56);
  v3 = 4;
  if ( *((_DWORD *)this + 14) == -1 )
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"SYSTEM\\CurrentControlSet\\Services\\EFS",
      L"AllowServiceStop",
      0x20000010u,
      0,
      v1,
      &v3);
  return *v1 == 1;
}

```

## disassembly

```asm
0x180002c00  mov     r11, rsp
0x180002c03  push    rbx
0x180002c04  sub     rsp, 40h
0x180002c08  lea     rbx, [rcx+38h]
0x180002c0c  mov     [rsp+48h+arg_0], 4
0x180002c14  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002c17  jnz     short loc_180002C4E
0x180002c19  lea     rax, [r11+8]
0x180002c1d  mov     r9d, 20000010h; dwFlags
0x180002c23  mov     [r11-18h], rax
0x180002c27  lea     r8, Value; "AllowServiceStop"
0x180002c2e  mov     [r11-20h], rbx
0x180002c32  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\EF"...
0x180002c39  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180002c40  mov     qword ptr [r11-28h], 0
0x180002c48  call    cs:__imp_RegGetValueW
0x180002c4e  cmp     dword ptr [rbx], 1
0x180002c51  setz    al
0x180002c54  add     rsp, 40h
0x180002c58  pop     rbx
0x180002c59  retn
```
