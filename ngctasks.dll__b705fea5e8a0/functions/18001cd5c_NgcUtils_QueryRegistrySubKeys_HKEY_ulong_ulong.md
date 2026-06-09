# NgcUtils::QueryRegistrySubKeys(HKEY__ *,ulong *,ulong *)

- ea: `0x18001cd5c`
- end: `0x18001ce0a`
- name: `?QueryRegistrySubKeys@NgcUtils@@YAJPEAUHKEY__@@PEAK1@Z`
- size: `174`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, HKEY, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012438`
- `0x180016850`

## callees

- `0x18000cc58`
- `0x18001cd5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001cdc6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001cdc6`

## string_xrefs

- `0x18001cdd5`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

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
0x18001cd5c  mov     r11, rsp
0x18001cd5f  mov     [r11+8], rbx
0x18001cd63  push    rdi
0x18001cd64  sub     rsp, 70h
0x18001cd68  mov     qword ptr [r11-20h], 0
0x18001cd70  lea     rax, [r11-18h]
0x18001cd74  mov     qword ptr [r11-28h], 0
0x18001cd7c  mov     rbx, r8
0x18001cd7f  mov     qword ptr [r11-30h], 0
0x18001cd87  mov     rdi, rdx
0x18001cd8a  mov     qword ptr [r11-38h], 0
0x18001cd92  xor     r9d, r9d; lpReserved
0x18001cd95  mov     qword ptr [r11-40h], 0
0x18001cd9d  xor     r8d, r8d; lpcchClass
0x18001cda0  mov     qword ptr [r11-48h], 0
0x18001cda8  xor     edx, edx; lpClass
0x18001cdaa  mov     [r11-50h], rax
0x18001cdae  lea     rax, [r11+20h]
0x18001cdb2  mov     [r11-58h], rax
0x18001cdb6  mov     dword ptr [r11+20h], 0
0x18001cdbe  mov     [rsp+78h+var_18], 0
0x18001cdc6  call    cs:__imp_RegQueryInfoKeyW
0x18001cdcc  test    eax, eax
0x18001cdce  jz      short loc_18001CDEB
0x18001cdd0  mov     rcx, [rsp+78h]; this
0x18001cdd5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001cddc  mov     r9d, eax; char *
0x18001cddf  mov     edx, 0A0h; void *
0x18001cde4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001cde9  jmp     short loc_18001CDFC
0x18001cdeb  mov     eax, [rsp+78h+arg_18]
0x18001cdf2  mov     [rdi], eax
0x18001cdf4  mov     eax, [rsp+78h+var_18]
0x18001cdf8  mov     [rbx], eax
0x18001cdfa  xor     eax, eax
0x18001cdfc  mov     rbx, [rsp+78h+arg_0]
0x18001ce04  add     rsp, 70h
0x18001ce08  pop     rdi
0x18001ce09  retn
```
