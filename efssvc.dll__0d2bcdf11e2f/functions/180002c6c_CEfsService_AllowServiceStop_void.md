# CEfsService::AllowServiceStop(void)

- ea: `0x180002c6c`
- end: `0x180002ccd`
- name: `?AllowServiceStop@CEfsService@@AEAA_NXZ`
- size: `97`
- prototype: `bool __fastcall(CEfsService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180002fb0`

## callees

- `0x180002c6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002cb4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002cb4`

## string_xrefs

- `0x180002c93`: `AllowServiceStop`
- `0x180002c9e`: `SYSTEM\CurrentControlSet\Services\EFS`

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
0x180002c6c  mov     r11, rsp
0x180002c6f  push    rbx
0x180002c70  sub     rsp, 40h
0x180002c74  lea     rbx, [rcx+38h]
0x180002c78  mov     [rsp+48h+arg_0], 4
0x180002c80  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002c83  jnz     short loc_180002CC0
0x180002c85  lea     rax, [r11+8]
0x180002c89  mov     r9d, 20000010h; dwFlags
0x180002c8f  mov     [r11-18h], rax
0x180002c93  lea     r8, Value; "AllowServiceStop"
0x180002c9a  mov     [r11-20h], rbx
0x180002c9e  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\EF"...
0x180002ca5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180002cac  mov     qword ptr [r11-28h], 0
0x180002cb4  call    cs:__imp_RegGetValueW
0x180002cbb  nop     dword ptr [rax+rax+00h]
0x180002cc0  cmp     dword ptr [rbx], 1
0x180002cc3  setz    al
0x180002cc6  add     rsp, 40h
0x180002cca  pop     rbx
0x180002ccb  retn
```
