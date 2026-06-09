# NgcUtils::QueryRegistrySubKeys(HKEY__ *,ulong *,ulong *)

- ea: `0x180023264`
- end: `0x180023312`
- name: `?QueryRegistrySubKeys@NgcUtils@@YAJPEAUHKEY__@@PEAK1@Z`
- size: `174`
- prototype: `int __fastcall(NgcUtils *this, _DWORD *, unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aae8`
- `0x18001c2f8`
- `0x18001ca98`
- `0x18001e4f0`

## callees

- `0x1800136b0`
- `0x180023264`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800232ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800232ce`

## string_xrefs

- `0x1800232dd`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
int __fastcall NgcUtils::QueryRegistrySubKeys(NgcUtils *this, _DWORD *a2, unsigned int *a3, unsigned int *a4)
{
  unsigned int v6; // eax
  unsigned int v8; // [rsp+20h] [rbp-58h]
  DWORD v9[6]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD v11; // [rsp+98h] [rbp+20h] BYREF

  v11 = 0;
  v9[0] = 0;
  v6 = RegQueryInfoKeyW((HKEY)this, 0, 0, 0, &v11, v9, 0, 0, 0, 0, 0, 0);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xA0,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
             (const char *)v6,
             v8);
  *a2 = v11;
  *a3 = v9[0];
  return 0;
}

```

## disassembly

```asm
0x180023264  mov     r11, rsp
0x180023267  mov     [r11+8], rbx
0x18002326b  push    rdi
0x18002326c  sub     rsp, 70h
0x180023270  mov     qword ptr [r11-20h], 0
0x180023278  lea     rax, [r11-18h]
0x18002327c  mov     qword ptr [r11-28h], 0
0x180023284  mov     rbx, r8
0x180023287  mov     qword ptr [r11-30h], 0
0x18002328f  mov     rdi, rdx
0x180023292  mov     qword ptr [r11-38h], 0
0x18002329a  xor     r9d, r9d; lpReserved
0x18002329d  mov     qword ptr [r11-40h], 0
0x1800232a5  xor     r8d, r8d; lpcchClass
0x1800232a8  mov     qword ptr [r11-48h], 0
0x1800232b0  xor     edx, edx; lpClass
0x1800232b2  mov     [r11-50h], rax
0x1800232b6  lea     rax, [r11+20h]
0x1800232ba  mov     [r11-58h], rax
0x1800232be  mov     dword ptr [r11+20h], 0
0x1800232c6  mov     [rsp+78h+var_18], 0
0x1800232ce  call    cs:__imp_RegQueryInfoKeyW
0x1800232d4  test    eax, eax
0x1800232d6  jz      short loc_1800232F3
0x1800232d8  mov     rcx, [rsp+78h]; this
0x1800232dd  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800232e4  mov     r9d, eax; char *
0x1800232e7  mov     edx, 0A0h; void *
0x1800232ec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800232f1  jmp     short loc_180023304
0x1800232f3  mov     eax, [rsp+78h+arg_18]
0x1800232fa  mov     [rdi], eax
0x1800232fc  mov     eax, [rsp+78h+var_18]
0x180023300  mov     [rbx], eax
0x180023302  xor     eax, eax
0x180023304  mov     rbx, [rsp+78h+arg_0]
0x18002330c  add     rsp, 70h
0x180023310  pop     rdi
0x180023311  retn
```
