# CFvePolicyReader::UnloadVolumePolicy(void)

- ea: `0x18002b068`
- end: `0x18002b0a9`
- name: `?UnloadVolumePolicy@CFvePolicyReader@@AEAAXXZ`
- size: `65`
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

- `0x18002b068`

## import_xrefs

- `ADVAPI32!RegUnLoadKeyW` at `0x18002b085`
- `ADVAPI32!RegUnLoadKeyW` at `0x18002b099`
- `ADVAPI32!RegUnLoadKeyW` at `0x18002b085`
- `ADVAPI32!RegUnLoadKeyW` at `0x18002b099`

## pseudocode

```c
void __fastcall CFvePolicyReader::UnloadVolumePolicy(CFvePolicyReader *this)
{
  if ( *((_BYTE *)this + 32) )
  {
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSoftwareRoot");
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot");
  }
  *((_BYTE *)this + 32) = 0;
}

```

## disassembly

```asm
0x18002b068  push    rbx
0x18002b06a  sub     rsp, 20h
0x18002b06e  cmp     byte ptr [rcx+20h], 0
0x18002b072  mov     rbx, rcx
0x18002b075  jz      short loc_18002B09F
0x18002b077  lea     rdx, aBitlockersoftw; "BitLockerSoftwareRoot"
0x18002b07e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b085  call    cs:__imp_RegUnLoadKeyW
0x18002b08b  lea     rdx, aBitlockersyste; "BitLockerSystemRoot"
0x18002b092  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b099  call    cs:__imp_RegUnLoadKeyW
0x18002b09f  mov     byte ptr [rbx+20h], 0
0x18002b0a3  add     rsp, 20h
0x18002b0a7  pop     rbx
0x18002b0a8  retn
```
