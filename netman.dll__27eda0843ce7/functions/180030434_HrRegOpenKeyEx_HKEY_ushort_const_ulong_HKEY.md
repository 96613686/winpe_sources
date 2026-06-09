# HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x180030434`
- end: `0x18003046b`
- name: `?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `55`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004a80`
- `0x18001ab80`
- `0x18001b1e8`
- `0x18001ccd0`
- `0x18001e7c4`
- `0x180025c44`
- `0x18002c960`
- `0x180030324`
- `0x180031b1c`
- `0x180031db8`

## callees

- `0x180030434`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180030448`
- `ADVAPI32!RegOpenKeyExW` at `0x180030448`

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
0x180030434  push    rbx
0x180030436  sub     rsp, 30h
0x18003043a  mov     rbx, r9
0x18003043d  mov     r9d, r8d; samDesired
0x180030440  xor     r8d, r8d; ulOptions
0x180030443  mov     [rsp+38h+phkResult], rbx; phkResult
0x180030448  call    cs:__imp_RegOpenKeyExW
0x18003044e  test    eax, eax
0x180030450  jle     short loc_18003045C
0x180030452  movzx   eax, ax
0x180030455  or      eax, 80070000h
0x18003045a  test    eax, eax
0x18003045c  jns     short loc_180030465
0x18003045e  mov     qword ptr [rbx], 0
0x180030465  add     rsp, 30h
0x180030469  pop     rbx
0x18003046a  retn
```
