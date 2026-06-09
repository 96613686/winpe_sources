# CSxGlobalTracer::_ReadRegistry(HINSTANCE__ *)

- ea: `0x18002e444`
- end: `0x18002e4fd`
- name: `?_ReadRegistry@CSxGlobalTracer@@AEAAJPEAUHINSTANCE__@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(CSxGlobalTracer *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18004b9e0`

## callees

- `0x18002e444`
- `0x18004bab8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e47a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e47a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e4f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e4f0`

## string_xrefs

- `0x18002e46c`: `SYSTEM\CurrentControlSet\Services\SPP\Debug\Tracing`

## pseudocode

```c
__int64 __fastcall CSxGlobalTracer::_ReadRegistry(CSxGlobalTracer *this, HINSTANCE a2)
{
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  HINSTANCE v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = a2;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\SPP\\Debug\\Tracing",
          0,
          0x20019u,
          &hKey) )
  {
    LODWORD(v4) = 0;
    if ( (int)QueryDWORDValue(hKey, &v4, L"TrackFailure") >= 0 && ((int)v4 < 0 || (_DWORD)v4 == 1) )
      dword_180084364 = (int)v4;
    LODWORD(v4) = 0;
    if ( (int)QueryDWORDValue(hKey, &v4, L"BreakOnTrackedError") >= 0 )
      dword_180084368 = (_DWORD)v4 != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18002e444  mov     r11, rsp
0x18002e447  mov     [r11+10h], rdx
0x18002e44b  mov     [r11+8], rcx
0x18002e44f  sub     rsp, 38h
0x18002e453  lea     rax, [r11+8]
0x18002e457  mov     qword ptr [r11+8], 0
0x18002e45f  mov     r9d, 20019h; samDesired
0x18002e465  mov     [r11-18h], rax
0x18002e469  xor     r8d, r8d; ulOptions
0x18002e46c  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\SP"...
0x18002e473  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e47a  call    cs:__imp_RegOpenKeyExW
0x18002e480  test    eax, eax
0x18002e482  jnz     short loc_18002E4E6
0x18002e484  mov     rcx, [rsp+38h+hKey]
0x18002e489  lea     r8, aTrackfailure; "TrackFailure"
0x18002e490  lea     rdx, [rsp+38h+arg_8]
0x18002e495  mov     dword ptr [rsp+38h+arg_8], eax
0x18002e499  call    QueryDWORDValue
0x18002e49e  test    eax, eax
0x18002e4a0  js      short loc_18002E4B5
0x18002e4a2  mov     eax, dword ptr [rsp+38h+arg_8]
0x18002e4a6  test    eax, eax
0x18002e4a8  js      short loc_18002E4AF
0x18002e4aa  cmp     eax, 1
0x18002e4ad  jnz     short loc_18002E4B5
0x18002e4af  mov     cs:dword_180084364, eax
0x18002e4b5  mov     rcx, [rsp+38h+hKey]
0x18002e4ba  lea     r8, aBreakontracked; "BreakOnTrackedError"
0x18002e4c1  lea     rdx, [rsp+38h+arg_8]
0x18002e4c6  mov     dword ptr [rsp+38h+arg_8], 0
0x18002e4ce  call    QueryDWORDValue
0x18002e4d3  test    eax, eax
0x18002e4d5  js      short loc_18002E4E6
0x18002e4d7  xor     eax, eax
0x18002e4d9  cmp     dword ptr [rsp+38h+arg_8], eax
0x18002e4dd  setnz   al
0x18002e4e0  mov     cs:dword_180084368, eax
0x18002e4e6  mov     rcx, [rsp+38h+hKey]; hKey
0x18002e4eb  test    rcx, rcx
0x18002e4ee  jz      short loc_18002E4F6
0x18002e4f0  call    cs:__imp_RegCloseKey
0x18002e4f6  xor     eax, eax
0x18002e4f8  add     rsp, 38h
0x18002e4fc  retn
```
