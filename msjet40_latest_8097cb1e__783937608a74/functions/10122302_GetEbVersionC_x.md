# GetEbVersionC(x)

- ea: `0x10122302`
- end: `0x10122353`
- name: `_GetEbVersionC@4`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100ab7e5`
- `0x100abeff`

## callees

- `0x10050190`
- `0x10121bda`
- `0x10122302`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x10122317`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x10122317`

## string_xrefs

- `0x10122309`: `msaccess.exe`

## pseudocode

```c
int GetEbVersionC()
{
  struct IJetESExtensions *IJetESExtensions; // eax
  int result; // eax
  int v2; // [esp+0h] [ebp-8h]
  unsigned int v3; // [esp+4h] [ebp-4h] BYREF

  v3 = 0;
  if ( GetModuleHandleA("msaccess.exe") )
    return 4098;
  IJetESExtensions = GetIJetESExtensions(v2);
  if ( IJetESExtensions )
    (*(void (__thiscall **)(_DWORD, struct IJetESExtensions *, unsigned int *))(*(_DWORD *)IJetESExtensions + 12))(
      *(_DWORD *)(*(_DWORD *)IJetESExtensions + 12),
      IJetESExtensions,
      &v3);
  result = 262;
  if ( v3 )
    return 4098;
  return result;
}

```

## disassembly

```asm
0x10122302  mov     edi, edi
0x10122304  push    ebp
0x10122305  mov     ebp, esp
0x10122307  push    ecx
0x10122308  push    esi; int
0x10122309  push    offset ModuleName; "msaccess.exe"
0x1012230e  mov     esi, ecx
0x10122310  mov     [ebp+var_4], 0
0x10122317  call    ds:__imp__GetModuleHandleA@4; GetModuleHandleA(x)
0x1012231d  test    eax, eax
0x1012231f  jnz     short loc_1012234B
0x10122321  mov     ecx, esi
0x10122323  call    ?GetIJetESExtensions@@YGPAUIJetESExtensions@@H@Z; GetIJetESExtensions(int)
0x10122328  test    eax, eax
0x1012232a  jz      short loc_10122340
0x1012232c  mov     ecx, [eax]
0x1012232e  lea     edx, [ebp+var_4]
0x10122331  push    edx; unsigned int
0x10122332  push    eax; void *
0x10122333  mov     esi, [ecx+0Ch]
0x10122336  mov     ecx, esi
0x10122338  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012233e  call    esi
0x10122340  cmp     [ebp+var_4], 0
0x10122344  mov     eax, 106h
0x10122349  jz      short loc_10122350
0x1012234b  mov     eax, 1002h
0x10122350  pop     esi
0x10122351  leave
0x10122352  retn
```
