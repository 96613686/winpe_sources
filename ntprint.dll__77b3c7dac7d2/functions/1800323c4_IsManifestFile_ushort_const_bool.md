# IsManifestFile(ushort const *,bool *)

- ea: `0x1800323c4`
- end: `0x180032429`
- name: `?IsManifestFile@@YAJPEBGPEA_N@Z`
- size: `101`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800314b0`
- `0x1800319d0`

## callees

- `0x18000d290`
- `0x1800323c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003240f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003240f`

## string_xrefs

- `0x180032404`: `-manifest.ini`

## pseudocode

```c
__int64 __fastcall IsManifestFile(const unsigned __int16 *a1, bool *a2)
{
  int v3; // eax
  __int64 v4; // r11
  unsigned int v5; // ebx
  unsigned __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v3 = StringCchLengthW(a1, 0x7FFFFFFFu, &v7);
  *a2 = 0;
  v5 = v3;
  if ( v3 >= 0 && v7 >= 0xD && !(unsigned int)_o__wcsicmp(v4 + 2 * (v7 - 13), L"-manifest.ini") )
    *a2 = 1;
  return v5;
}

```

## disassembly

```asm
0x1800323c4  mov     [rsp+arg_0], rbx
0x1800323c9  push    rdi
0x1800323ca  sub     rsp, 20h
0x1800323ce  mov     rdi, rdx
0x1800323d1  mov     [rsp+28h+arg_8], 0
0x1800323da  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800323df  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x1800323e4  mov     r11, rcx
0x1800323e7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800323ec  mov     byte ptr [rdi], 0
0x1800323ef  mov     ebx, eax
0x1800323f1  test    eax, eax
0x1800323f3  js      short loc_18003241C
0x1800323f5  mov     r8, [rsp+28h+arg_8]
0x1800323fa  cmp     r8, 0Dh
0x1800323fe  jb      short loc_18003241C
0x180032400  add     r8, 0FFFFFFFFFFFFFFF3h
0x180032404  lea     rdx, aManifestIni; "-manifest.ini"
0x18003240b  lea     rcx, [r11+r8*2]
0x18003240f  call    cs:__imp__o__wcsicmp
0x180032415  test    eax, eax
0x180032417  jnz     short loc_18003241C
0x180032419  mov     byte ptr [rdi], 1
0x18003241c  mov     eax, ebx
0x18003241e  mov     rbx, [rsp+28h+arg_0]
0x180032423  add     rsp, 20h
0x180032427  pop     rdi
0x180032428  retn
```
