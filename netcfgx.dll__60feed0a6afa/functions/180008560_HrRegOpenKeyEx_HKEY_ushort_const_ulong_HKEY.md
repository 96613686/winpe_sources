# HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x180008560`
- end: `0x180008597`
- name: `?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `55`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007a4c`
- `0x180008e2c`
- `0x18000af5c`
- `0x180010a00`
- `0x180011270`
- `0x180011c38`

## callees

- `0x180008560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008574`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008574`

## pseudocode

```c
int __fastcall HrRegOpenKeyEx(HKEY a1, const unsigned __int16 *a2, REGSAM a3, HKEY *phkResult)
{
  int result; // eax
  bool v6; // sf

  result = RegOpenKeyExW(a1, a2, 0, a3, phkResult);
  v6 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v6 = result < 0;
  }
  if ( v6 )
    *phkResult = 0;
  return result;
}

```

## disassembly

```asm
0x180008560  push    rbx
0x180008562  sub     rsp, 30h
0x180008566  mov     rbx, r9
0x180008569  mov     r9d, r8d; samDesired
0x18000856c  xor     r8d, r8d; ulOptions
0x18000856f  mov     [rsp+38h+phkResult], rbx; phkResult
0x180008574  call    cs:__imp_RegOpenKeyExW
0x18000857a  test    eax, eax
0x18000857c  jle     short loc_180008588
0x18000857e  movzx   eax, ax
0x180008581  or      eax, 80070000h
0x180008586  test    eax, eax
0x180008588  jns     short loc_180008591
0x18000858a  mov     qword ptr [rbx], 0
0x180008591  add     rsp, 30h
0x180008595  pop     rbx
0x180008596  retn
```
