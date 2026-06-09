# NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x18002308c`
- end: `0x18002311b`
- name: `?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `143`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a698`
- `0x18001aae8`
- `0x18001bbdc`
- `0x18001c2f8`
- `0x18001c508`
- `0x18001c760`

## callees

- `0x18000b0fc`
- `0x18002308c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800230c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800230c9`

## string_xrefs

- `0x1800230f0`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetRegistryDwordValue(
        NgcUtils *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  LSTATUS ValueW; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-38h]
  int v9; // [rsp+40h] [rbp-18h] BYREF
  DWORD v10[5]; // [rsp+44h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v10[0] = 4;
  v9 = 0;
  ValueW = RegGetValueW((HKEY)this, a2, a3, 0x10u, 0, &v9, v10);
  v6 = ValueW;
  if ( ValueW > 0 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
  {
    *(_DWORD *)a4 = v9;
    return 0;
  }
  else
  {
    result = 2147942402LL;
    if ( v6 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
        (const char *)v6,
        v8);
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002308c  mov     r11, rsp
0x18002308f  mov     [r11+8], rbx
0x180023093  push    rdi
0x180023094  sub     rsp, 50h
0x180023098  lea     rax, [r11-14h]
0x18002309c  mov     [rsp+58h+var_14], 4
0x1800230a4  mov     [r11-28h], rax
0x1800230a8  mov     rdi, r9
0x1800230ab  lea     rax, [r11-18h]
0x1800230af  mov     [rsp+58h+var_18], 0
0x1800230b7  mov     [r11-30h], rax
0x1800230bb  mov     r9d, 10h; dwFlags
0x1800230c1  mov     qword ptr [r11-38h], 0
0x1800230c9  call    cs:__imp_RegGetValueW
0x1800230cf  mov     ebx, eax
0x1800230d1  test    eax, eax
0x1800230d3  jle     short loc_1800230DE
0x1800230d5  movzx   ebx, ax
0x1800230d8  or      ebx, 80070000h
0x1800230de  test    ebx, ebx
0x1800230e0  jns     short loc_180023108
0x1800230e2  mov     eax, 80070002h
0x1800230e7  cmp     ebx, eax
0x1800230e9  jz      short loc_180023110
0x1800230eb  mov     rcx, [rsp+58h]; this
0x1800230f0  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800230f7  mov     r9d, ebx; char *
0x1800230fa  mov     edx, 4Eh ; 'N'; void *
0x1800230ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023104  mov     eax, ebx
0x180023106  jmp     short loc_180023110
0x180023108  mov     eax, [rsp+58h+var_18]
0x18002310c  mov     [rdi], eax
0x18002310e  xor     eax, eax
0x180023110  mov     rbx, [rsp+58h+arg_0]
0x180023115  add     rsp, 50h
0x180023119  pop     rdi
0x18002311a  retn
```
