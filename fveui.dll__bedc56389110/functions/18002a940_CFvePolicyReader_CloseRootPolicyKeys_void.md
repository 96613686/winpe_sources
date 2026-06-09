# CFvePolicyReader::CloseRootPolicyKeys(void)

- ea: `0x18002a940`
- end: `0x18002a97d`
- name: `?CloseRootPolicyKeys@CFvePolicyReader@@AEAAXXZ`
- size: `61`
- prototype: `void __fastcall(CFvePolicyReader *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002a8a8`
- `0x18002a910`
- `0x18002af80`
- `0x18002b0b0`

## callees

- `0x18002a940`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002a952`
- `ADVAPI32!RegCloseKey` at `0x18002a961`
- `ADVAPI32!RegCloseKey` at `0x18002a952`
- `ADVAPI32!RegCloseKey` at `0x18002a961`

## pseudocode

```c
void __fastcall CFvePolicyReader::CloseRootPolicyKeys(CFvePolicyReader *this)
{
  HKEY v2; // rcx
  HKEY v3; // rcx

  v2 = (HKEY)*((_QWORD *)this + 2);
  if ( v2 )
    RegCloseKey(v2);
  v3 = (HKEY)*((_QWORD *)this + 3);
  if ( v3 )
    RegCloseKey(v3);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18002a940  push    rbx
0x18002a942  sub     rsp, 20h
0x18002a946  mov     rbx, rcx
0x18002a949  mov     rcx, [rcx+10h]; hKey
0x18002a94d  test    rcx, rcx
0x18002a950  jz      short loc_18002A958
0x18002a952  call    cs:__imp_RegCloseKey
0x18002a958  mov     rcx, [rbx+18h]; hKey
0x18002a95c  test    rcx, rcx
0x18002a95f  jz      short loc_18002A967
0x18002a961  call    cs:__imp_RegCloseKey
0x18002a967  mov     qword ptr [rbx+10h], 0
0x18002a96f  mov     qword ptr [rbx+18h], 0
0x18002a977  add     rsp, 20h
0x18002a97b  pop     rbx
0x18002a97c  retn
```
