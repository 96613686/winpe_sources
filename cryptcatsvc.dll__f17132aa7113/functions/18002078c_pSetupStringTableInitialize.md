# pSetupStringTableInitialize

- ea: `0x18002078c`
- end: `0x1800207cb`
- name: `pSetupStringTableInitialize`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001e39c`
- `0x18001e890`

## callees

- `0x180020510`
- `0x180020598`
- `0x18002078c`
- `0x180020d6c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180020792`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180020792`

## pseudocode

```c
__int64 pSetupStringTableInitialize()
{
  int v0; // edx
  int v1; // ecx
  int v2; // r8d
  int v3; // r9d
  __int64 v4; // rax
  __int64 v5; // rbx

  GetThreadLocale();
  v4 = pSpUtilsStringTableInitializeEx(v1, v0, v2, v3);
  v5 = v4;
  if ( v4 )
  {
    if ( (unsigned int)pSpUtilsInitializeSynchronizedAccess(v4 + 16) )
      return v5;
    pSpUtilsStringTableDestroy(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x18002078c  push    rbx
0x18002078e  sub     rsp, 40h
0x180020792  call    cs:__imp_GetThreadLocale
0x180020798  mov     [rsp+48h+var_20], eax
0x18002079c  call    _pSpUtilsStringTableInitializeEx
0x1800207a1  mov     rbx, rax
0x1800207a4  test    rax, rax
0x1800207a7  jz      short loc_1800207C3
0x1800207a9  lea     rcx, [rax+10h]
0x1800207ad  call    _pSpUtilsInitializeSynchronizedAccess
0x1800207b2  test    eax, eax
0x1800207b4  jz      short loc_1800207BB
0x1800207b6  mov     rax, rbx
0x1800207b9  jmp     short loc_1800207C5
0x1800207bb  mov     rcx, rbx
0x1800207be  call    _pSpUtilsStringTableDestroy
0x1800207c3  xor     eax, eax
0x1800207c5  add     rsp, 40h
0x1800207c9  pop     rbx
0x1800207ca  retn
```
