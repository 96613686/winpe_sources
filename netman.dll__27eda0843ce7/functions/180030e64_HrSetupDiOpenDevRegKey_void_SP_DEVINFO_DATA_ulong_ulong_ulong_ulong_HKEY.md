# HrSetupDiOpenDevRegKey(void *,_SP_DEVINFO_DATA *,ulong,ulong,ulong,ulong,HKEY__ * *)

- ea: `0x180030e64`
- end: `0x180030ea6`
- name: `?HrSetupDiOpenDevRegKey@@YAJPEAXPEAU_SP_DEVINFO_DATA@@KKKKPEAPEAUHKEY__@@@Z`
- size: `66`
- prototype: `__int64 __fastcall(void *, struct _SP_DEVINFO_DATA *, unsigned int, unsigned int, unsigned int, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18001eb7c`
- `0x1800259a4`

## callees

- `0x18003060c`
- `0x180030e64`

## import_xrefs

- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180030e7f`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180030e7f`

## pseudocode

```c
__int64 __fastcall HrSetupDiOpenDevRegKey(
        void *a1,
        struct _SP_DEVINFO_DATA *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        HKEY *a7)
{
  HKEY v7; // rdx
  __int64 result; // rax

  v7 = SetupDiOpenDevRegKey(a1, a2, 1u, 0, 2u, 0x20019u);
  if ( v7 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    result = HrFromLastWin32Error();
    v7 = 0;
  }
  else
  {
    result = 0;
  }
  *a7 = v7;
  return result;
}

```

## disassembly

```asm
0x180030e64  sub     rsp, 38h
0x180030e68  xor     r9d, r9d; HwProfile
0x180030e6b  mov     [rsp+38h+samDesired], 20019h; samDesired
0x180030e73  mov     [rsp+38h+KeyType], 2; KeyType
0x180030e7b  lea     r8d, [r9+1]; Scope
0x180030e7f  call    cs:__imp_SetupDiOpenDevRegKey
0x180030e85  mov     rdx, rax
0x180030e88  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030e8c  jz      short loc_180030E92
0x180030e8e  xor     eax, eax
0x180030e90  jmp     short loc_180030E99
0x180030e92  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180030e97  xor     edx, edx
0x180030e99  mov     rcx, [rsp+38h+arg_30]
0x180030e9e  mov     [rcx], rdx
0x180030ea1  add     rsp, 38h
0x180030ea5  retn
```
