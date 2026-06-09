# GetDefaultLocalCacheGrowthPolicy(void)

- ea: `0x18012fe90`
- end: `0x18012ff54`
- name: `?GetDefaultLocalCacheGrowthPolicy@@YA?AUCacheGrowthPolicy@@XZ`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18012fd48`

## callees

- `0x18012fe90`
- `0x180130a20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012fecf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012fecf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012ff45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012ff45`

## string_xrefs

- `0x18012fec1`: `SYSTEM\CurrentControlSet\Services\FontCache\Parameters`
- `0x18012fee4`: `ClientCacheSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 GetDefaultLocalCacheGrowthPolicy()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  bool v2; // di
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v0 = dword_1804B87CC;
  if ( !dword_1804B87CC )
  {
    v1 = 0;
    LODWORD(v4) = 0;
    hKey = 0;
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\FontCache\\Parameters", 0, 0x20019u, &hKey);
    if ( hKey )
    {
      v2 = (unsigned int)GetNumber(hKey, L"ClientCacheSize", (unsigned int *)&v4) == 0;
      if ( hKey )
        RegCloseKey(hKey);
      v1 = v4;
    }
    else
    {
      v2 = 0;
    }
    if ( v2 )
    {
      v0 = 0x10000;
      if ( v1 >= 0x10000 )
      {
        v0 = v1;
        if ( v1 > 0x1000000 )
          v0 = 0x1000000;
      }
    }
    else
    {
      v0 = 0x400000;
    }
    dword_1804B87CC = v0;
  }
  return v0 | 0x32000000000LL;
}

```

## disassembly

```asm
0x18012fe90  mov     r11, rsp
0x18012fe93  mov     [r11+18h], rbx
0x18012fe97  push    rdi
0x18012fe98  sub     rsp, 30h
0x18012fe9c  mov     eax, cs:dword_1804B87CC
0x18012fea2  test    eax, eax
0x18012fea4  jnz     short loc_18012FF24
0x18012fea6  xor     ebx, ebx
0x18012fea8  mov     dword ptr [rsp+38h+arg_0], ebx
0x18012feac  mov     [r11+10h], rbx
0x18012feb0  lea     rax, [r11+10h]
0x18012feb4  mov     [r11-18h], rax
0x18012feb8  mov     r9d, 20019h; samDesired
0x18012febe  xor     r8d, r8d; ulOptions
0x18012fec1  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Fo"...
0x18012fec8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18012fecf  call    cs:__imp_RegOpenKeyExW
0x18012fed5  mov     rcx, [rsp+38h+hKey]; HKEY
0x18012feda  test    rcx, rcx
0x18012fedd  jz      short loc_18012FF40
0x18012fedf  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x18012fee4  lea     rdx, aClientcachesiz; "ClientCacheSize"
0x18012feeb  call    ?GetNumber@@YAJPEAUHKEY__@@PEB_WPEAI@Z; GetNumber(HKEY__ *,wchar_t const *,uint *)
0x18012fef0  test    eax, eax
0x18012fef2  setz    dil
0x18012fef6  mov     rcx, [rsp+38h+hKey]; hKey
0x18012fefb  test    rcx, rcx
0x18012fefe  jnz     short loc_18012FF45
0x18012ff00  mov     ebx, dword ptr [rsp+38h+arg_0]
0x18012ff04  test    dil, dil
0x18012ff07  jz      short loc_18012FF4D
0x18012ff09  mov     eax, 10000h
0x18012ff0e  cmp     ebx, eax
0x18012ff10  jb      short loc_18012FF1E
0x18012ff12  mov     eax, ebx
0x18012ff14  mov     ecx, 1000000h
0x18012ff19  cmp     ebx, ecx
0x18012ff1b  cmova   eax, ecx
0x18012ff1e  mov     cs:dword_1804B87CC, eax
0x18012ff24  mov     dword ptr [rsp+38h+arg_0], eax
0x18012ff28  mov     dword ptr [rsp+38h+arg_0+4], 320h
0x18012ff30  mov     rax, [rsp+38h+arg_0]
0x18012ff35  mov     rbx, [rsp+38h+arg_10]
0x18012ff3a  add     rsp, 30h
0x18012ff3e  pop     rdi
0x18012ff3f  retn
0x18012ff40  xor     dil, dil
0x18012ff43  jmp     short loc_18012FF04
0x18012ff45  call    cs:__imp_RegCloseKey
0x18012ff4b  jmp     short loc_18012FF00
0x18012ff4d  mov     eax, 400000h
0x18012ff52  jmp     short loc_18012FF1E
```
