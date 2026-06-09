# SHRegCreateOrOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18000b204`
- end: `0x18000b267`
- name: `?SHRegCreateOrOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `99`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000b770`
- `0x18000b7e8`

## callees

- `0x18000b204`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b23d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b23d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b250`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b250`

## pseudocode

```c
LSTATUS __fastcall SHRegCreateOrOpenKeyEx(HKEY a1, const unsigned __int16 *a2, char a3, HKEY *phkResult)
{
  LSTATUS result; // eax

  *phkResult = 0;
  if ( (a3 & 4) != 0 )
    result = RegCreateKeyExW(a1, a2, 0, 0, 0, a3, 0, phkResult, 0);
  else
    result = RegOpenKeyExW(a1, a2, 0, a3, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000b204  mov     rax, rsp
0x18000b207  sub     rsp, 58h
0x18000b20b  mov     qword ptr [r9], 0
0x18000b212  test    r8b, 4
0x18000b216  jz      short loc_18000B245
0x18000b218  mov     qword ptr [rax-18h], 0
0x18000b220  mov     [rax-20h], r9
0x18000b224  xor     r9d, r9d; lpClass
0x18000b227  mov     qword ptr [rax-28h], 0
0x18000b22f  mov     [rax-30h], r8d
0x18000b233  xor     r8d, r8d; Reserved
0x18000b236  mov     dword ptr [rax-38h], 0
0x18000b23d  call    cs:__imp_RegCreateKeyExW
0x18000b243  jmp     short loc_18000B256
0x18000b245  mov     [rsp+58h+phkResult], r9; phkResult
0x18000b24a  mov     r9d, r8d; samDesired
0x18000b24d  xor     r8d, r8d; ulOptions
0x18000b250  call    cs:__imp_RegOpenKeyExW
0x18000b256  test    eax, eax
0x18000b258  jle     short loc_18000B262
0x18000b25a  movzx   eax, ax
0x18000b25d  or      eax, 80070000h
0x18000b262  add     rsp, 58h
0x18000b266  retn
```
