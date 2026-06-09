# HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x1800302b8`
- end: `0x18003031c`
- name: `?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z`
- size: `100`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031b1c`

## callees

- `0x1800302b8`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1800302f9`
- `ADVAPI32!RegCreateKeyExW` at `0x1800302f9`

## pseudocode

```c
int __fastcall HrRegCreateKeyEx(
        HKEY a1,
        const unsigned __int16 *a2,
        __int64 a3,
        REGSAM a4,
        struct _SECURITY_ATTRIBUTES *a5,
        HKEY *a6,
        unsigned int *a7)
{
  int result; // eax
  bool v8; // sf

  result = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, a4, 0, a6, a7);
  v8 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v8 = result < 0;
  }
  if ( v8 )
    *a6 = 0;
  return result;
}

```

## disassembly

```asm
0x1800302b8  mov     r11, rsp
0x1800302bb  push    rbx
0x1800302bc  sub     rsp, 50h
0x1800302c0  mov     rax, [rsp+58h+arg_30]
0x1800302c8  xor     r8d, r8d; Reserved
0x1800302cb  mov     rbx, [rsp+58h+arg_28]
0x1800302d3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800302da  mov     [r11-18h], rax
0x1800302de  mov     [r11-20h], rbx
0x1800302e2  mov     qword ptr [r11-28h], 0
0x1800302ea  mov     [r11-30h], r9d
0x1800302ee  xor     r9d, r9d; lpClass
0x1800302f1  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800302f9  call    cs:__imp_RegCreateKeyExW
0x1800302ff  test    eax, eax
0x180030301  jle     short loc_18003030D
0x180030303  movzx   eax, ax
0x180030306  or      eax, 80070000h
0x18003030b  test    eax, eax
0x18003030d  jns     short loc_180030316
0x18003030f  mov     qword ptr [rbx], 0
0x180030316  add     rsp, 50h
0x18003031a  pop     rbx
0x18003031b  retn
```
