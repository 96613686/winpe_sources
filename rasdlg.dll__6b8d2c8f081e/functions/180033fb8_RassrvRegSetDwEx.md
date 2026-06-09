# RassrvRegSetDwEx

- ea: `0x180033fb8`
- end: `0x180034077`
- name: `RassrvRegSetDwEx`
- size: `191`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180035134`
- `0x1800365a8`
- `0x180036a3c`
- `0x180036d34`
- `0x180037e48`
- `0x180037f48`
- `0x180038038`

## callees

- `0x180033fb8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003400b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003400b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034023`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034023`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034064`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034064`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034052`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034052`

## pseudocode

```c
__int64 __fastcall RassrvRegSetDwEx(int a1, const WCHAR *a2, const WCHAR *a3, int a4)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  HKEY phkResult[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD v9; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Data = a1;
  phkResult[0] = 0;
  if ( a4 )
  {
    v9 = 0;
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0x20006u, 0, phkResult, &v9);
  }
  else
  {
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20006u, phkResult);
  }
  v6 = v5;
  if ( !v5 )
    v6 = RegSetValueExW(phkResult[0], a3, 0, 4u, (const BYTE *)&Data, 4u);
  if ( phkResult[0] )
    RegCloseKey(phkResult[0]);
  return v6;
}

```

## disassembly

```asm
0x180033fb8  mov     r11, rsp
0x180033fbb  mov     [r11+10h], rbx
0x180033fbf  push    rdi
0x180033fc0  sub     rsp, 60h
0x180033fc4  mov     rdi, r8
0x180033fc7  mov     [r11+20h], ecx
0x180033fcb  xor     r8d, r8d; ulOptions
0x180033fce  mov     qword ptr [r11-18h], 0
0x180033fd6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033fdd  test    r9d, r9d
0x180033fe0  jz      short loc_180034013
0x180033fe2  lea     rax, [r11+8]
0x180033fe6  mov     [rsp+68h+arg_0], r8d
0x180033feb  mov     [r11-28h], rax
0x180033fef  xor     r9d, r9d; lpClass
0x180033ff2  lea     rax, [r11-18h]
0x180033ff6  mov     [r11-30h], rax
0x180033ffa  mov     [r11-38h], r8
0x180033ffe  mov     [rsp+68h+samDesired], 20006h; samDesired
0x180034006  mov     [rsp+68h+dwOptions], r8d; dwOptions
0x18003400b  call    cs:__imp_RegCreateKeyExW
0x180034011  jmp     short loc_180034029
0x180034013  lea     rax, [rsp+68h+phkResult]
0x180034018  mov     r9d, 20006h; samDesired
0x18003401e  mov     qword ptr [rsp+68h+dwOptions], rax; phkResult
0x180034023  call    cs:__imp_RegOpenKeyExW
0x180034029  mov     ebx, eax
0x18003402b  test    eax, eax
0x18003402d  jnz     short loc_18003405A
0x18003402f  mov     rcx, [rsp+68h+phkResult]; hKey
0x180034034  lea     rax, [rsp+68h+Data]
0x18003403c  mov     r9d, 4; dwType
0x180034042  xor     r8d, r8d; Reserved
0x180034045  mov     [rsp+68h+samDesired], r9d; cbData
0x18003404a  mov     rdx, rdi; lpValueName
0x18003404d  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180034052  call    cs:__imp_RegSetValueExW
0x180034058  mov     ebx, eax
0x18003405a  mov     rcx, [rsp+68h+phkResult]; hKey
0x18003405f  test    rcx, rcx
0x180034062  jz      short loc_18003406A
0x180034064  call    cs:__imp_RegCloseKey
0x18003406a  mov     eax, ebx
0x18003406c  mov     rbx, [rsp+68h+arg_8]
0x180034071  add     rsp, 60h
0x180034075  pop     rdi
0x180034076  retn
```
