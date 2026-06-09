# NcaConfigMgrLoadString(HKEY__ *,ushort const *,int,ushort * *)

- ea: `0x180005bd4`
- end: `0x180005c11`
- name: `?NcaConfigMgrLoadString@@YAJPEAUHKEY__@@PEBGHPEAPEAG@Z`
- size: `61`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005770`

## callees

- `0x18001a95c`

## pseudocode

```c
__int64 __fastcall NcaConfigMgrLoadString(HKEY a1, const unsigned __int16 *a2, __int64 a3, unsigned __int16 **a4)
{
  int String; // ecx
  __int64 result; // rax
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(v6) = 0;
  *a4 = 0;
  String = NcaRegQueryString(a1, (__int64)&v6);
  result = 0;
  if ( String == -2147024882 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x180005bd4  mov     dword ptr [rsp+arg_10], r8d
0x180005bd9  sub     rsp, 38h
0x180005bdd  lea     rax, [rsp+38h+arg_10]
0x180005be2  mov     dword ptr [rsp+38h+arg_10], 0
0x180005bea  mov     r8, rdx
0x180005bed  mov     [rsp+38h+var_18], rax; __int64
0x180005bf2  mov     qword ptr [r9], 0
0x180005bf9  call    NcaRegQueryString
0x180005bfe  mov     ecx, eax
0x180005c00  xor     eax, eax
0x180005c02  cmp     ecx, 8007000Eh
0x180005c08  cmovz   eax, ecx
0x180005c0b  add     rsp, 38h
0x180005c0f  retn
```
