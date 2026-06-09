# GetEbVersionC(x)

- ea: `0x10122152`
- end: `0x101221a3`
- name: `_GetEbVersionC@4`
- size: `81`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100ab655`
- `0x100abd6f`

## callees

- `0x10050000`
- `0x10121a2a`
- `0x10122152`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x10122167`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x10122167`

## string_xrefs

- `0x10122159`: `msaccess.exe`

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
0x10122152  mov     edi, edi
0x10122154  push    ebp
0x10122155  mov     ebp, esp
0x10122157  push    ecx
0x10122158  push    esi; int
0x10122159  push    offset ModuleName; "msaccess.exe"
0x1012215e  mov     esi, ecx
0x10122160  mov     [ebp+var_4], 0
0x10122167  call    ds:__imp__GetModuleHandleA@4; GetModuleHandleA(x)
0x1012216d  test    eax, eax
0x1012216f  jnz     short loc_1012219B
0x10122171  mov     ecx, esi
0x10122173  call    ?GetIJetESExtensions@@YGPAUIJetESExtensions@@H@Z; GetIJetESExtensions(int)
0x10122178  test    eax, eax
0x1012217a  jz      short loc_10122190
0x1012217c  mov     ecx, [eax]
0x1012217e  lea     edx, [ebp+var_4]
0x10122181  push    edx; unsigned int
0x10122182  push    eax; void *
0x10122183  mov     esi, [ecx+0Ch]
0x10122186  mov     ecx, esi
0x10122188  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012218e  call    esi
0x10122190  cmp     [ebp+var_4], 0
0x10122194  mov     eax, 106h
0x10122199  jz      short loc_101221A0
0x1012219b  mov     eax, 1002h
0x101221a0  pop     esi
0x101221a1  leave
0x101221a2  retn
```
