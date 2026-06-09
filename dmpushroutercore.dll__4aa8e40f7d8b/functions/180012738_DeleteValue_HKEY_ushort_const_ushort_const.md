# DeleteValue(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180012738`
- end: `0x1800127bc`
- name: `?DeleteValue@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `132`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012e24`

## callees

- `0x180012738`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800127ac`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800127ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001278b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001278b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012765`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012765`

## pseudocode

```c
__int64 __fastcall DeleteValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = a1;
  if ( !a2 )
    goto LABEL_10;
  v4 = RegOpenKeyExW(a1, a2, 0, 0xF003Fu, &hKey);
  v5 = v4;
  if ( !v4 )
  {
    a1 = hKey;
LABEL_10:
    v5 = 0;
    v4 = RegDeleteValueW(a1, L"QueueId");
    if ( !v4 )
      goto LABEL_5;
    if ( v4 <= 0 )
    {
      v5 = v4;
      goto LABEL_5;
    }
    goto LABEL_4;
  }
  if ( v4 > 0 )
LABEL_4:
    v5 = (unsigned __int16)v4 | 0x80070000;
LABEL_5:
  if ( hKey && a2 )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180012738  mov     r11, rsp
0x18001273b  mov     [r11+8], rbx
0x18001273f  mov     [r11+18h], r8
0x180012743  push    rdi
0x180012744  sub     rsp, 30h
0x180012748  mov     [r11+18h], rcx
0x18001274c  mov     rdi, rdx
0x18001274f  test    rdx, rdx
0x180012752  jz      short loc_1800127A3
0x180012754  lea     rax, [r11+18h]
0x180012758  mov     r9d, 0F003Fh; samDesired
0x18001275e  xor     r8d, r8d; ulOptions
0x180012761  mov     [r11-18h], rax
0x180012765  call    cs:__imp_RegOpenKeyExW
0x18001276b  mov     ebx, eax
0x18001276d  test    eax, eax
0x18001276f  jz      short loc_18001279E
0x180012771  jle     short loc_18001277C
0x180012773  movzx   ebx, ax
0x180012776  or      ebx, 80070000h
0x18001277c  mov     rcx, [rsp+38h+hKey]; hKey
0x180012781  test    rcx, rcx
0x180012784  jz      short loc_180012791
0x180012786  test    rdi, rdi
0x180012789  jz      short loc_180012791
0x18001278b  call    cs:__imp_RegCloseKey
0x180012791  mov     eax, ebx
0x180012793  mov     rbx, [rsp+38h+arg_0]
0x180012798  add     rsp, 30h
0x18001279c  pop     rdi
0x18001279d  retn
0x18001279e  mov     rcx, [rsp+38h+hKey]; hKey
0x1800127a3  lea     rdx, ?c_szQueueId@@3QBGB; "QueueId"
0x1800127aa  xor     ebx, ebx
0x1800127ac  call    cs:__imp_RegDeleteValueW
0x1800127b2  test    eax, eax
0x1800127b4  jz      short loc_18001277C
0x1800127b6  jg      short loc_180012773
0x1800127b8  mov     ebx, eax
0x1800127ba  jmp     short loc_18001277C
```
