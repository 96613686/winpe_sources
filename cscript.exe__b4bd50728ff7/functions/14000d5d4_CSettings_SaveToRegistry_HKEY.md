# CSettings::SaveToRegistry(HKEY__ *)

- ea: `0x14000d5d4`
- end: `0x14000d66b`
- name: `?SaveToRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(CSettings *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003e2c`

## callees

- `0x140005610`
- `0x14000d5d4`
- `0x140014e0c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000d658`
- `ADVAPI32!RegCloseKey` at `0x14000d658`

## pseudocode

```c
signed int __fastcall CSettings::SaveToRegistry(CSettings *this, HKEY a2)
{
  signed int result; // eax
  int v4; // r8d
  signed int v5; // edi
  HKEY hKey; // [rsp+38h] [rbp+10h] BYREF

  hKey = 0;
  result = CreateRegSettings(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20006u, &hKey);
  if ( result >= 0 )
  {
    if ( *((_BYTE *)this + 4) )
      v4 = *(_DWORD *)this;
    else
      v4 = 0;
    v5 = PutRegSettingsInt(hKey, L"Timeout", v4);
    if ( v5 >= 0 )
      v5 = PutRegSettingsInt(hKey, L"DisplayLogo", *((_BYTE *)this + 6) != 0);
    RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x14000d5d4  mov     rax, rsp
0x14000d5d7  mov     [rax+8], rbx
0x14000d5db  mov     [rax+10h], rdx
0x14000d5df  push    rdi
0x14000d5e0  sub     rsp, 20h
0x14000d5e4  mov     rbx, rcx
0x14000d5e7  mov     qword ptr [rax+10h], 0
0x14000d5ef  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000d5f6  lea     r9, [rax+10h]; phkResult
0x14000d5fa  mov     r8d, 20006h; samDesired
0x14000d600  lea     rdx, WideCharStr; "Software\\Microsoft\\Windows Script Hos"...
0x14000d607  call    ?CreateRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CreateRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x14000d60c  test    eax, eax
0x14000d60e  js      short loc_14000D660
0x14000d610  cmp     byte ptr [rbx+4], 0
0x14000d614  jz      short loc_14000D61B
0x14000d616  mov     r8d, [rbx]
0x14000d619  jmp     short loc_14000D61E
0x14000d61b  xor     r8d, r8d; unsigned int
0x14000d61e  mov     rcx, [rsp+28h+hKey]; hKey
0x14000d623  lea     rdx, ValueName; "Timeout"
0x14000d62a  call    ?PutRegSettingsInt@@YAJPEAUHKEY__@@PEBGK@Z; PutRegSettingsInt(HKEY__ *,ushort const *,ulong)
0x14000d62f  mov     edi, eax
0x14000d631  test    eax, eax
0x14000d633  js      short loc_14000D653
0x14000d635  mov     rcx, [rsp+28h+hKey]; hKey
0x14000d63a  lea     rdx, aDisplaylogo; "DisplayLogo"
0x14000d641  xor     r8d, r8d
0x14000d644  cmp     [rbx+6], r8b
0x14000d648  setnz   r8b; unsigned int
0x14000d64c  call    ?PutRegSettingsInt@@YAJPEAUHKEY__@@PEBGK@Z; PutRegSettingsInt(HKEY__ *,ushort const *,ulong)
0x14000d651  mov     edi, eax
0x14000d653  mov     rcx, [rsp+28h+hKey]; hKey
0x14000d658  call    cs:__imp_RegCloseKey
0x14000d65e  mov     eax, edi
0x14000d660  mov     rbx, [rsp+28h+arg_0]
0x14000d665  add     rsp, 20h
0x14000d669  pop     rdi
0x14000d66a  retn
```
