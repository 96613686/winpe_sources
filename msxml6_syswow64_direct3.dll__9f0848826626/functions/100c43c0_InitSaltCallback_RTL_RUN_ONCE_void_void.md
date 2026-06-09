# InitSaltCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x100c43c0`
- end: `0x100c4424`
- name: `?InitSaltCallback@@YGHPAT_RTL_RUN_ONCE@@PAXPAPAX@Z`
- size: `100`
- prototype: `int __stdcall(_RTL_RUN_ONCE *initOnce, void *parameter, void **context)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100c43c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x100c4407`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x100c4407`
- `bcrypt!BCryptGenRandom` at `0x100c43f4`
- `bcrypt!BCryptGenRandom` at `0x100c43f4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x100c43db`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x100c43db`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x100c4416`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x100c4416`

## pseudocode

```c
BOOL __stdcall InitSaltCallback(_RTL_RUN_ONCE *initOnce, void *parameter, void **context)
{
  NTSTATUS v3; // eax
  BOOL v4; // esi
  void *handle; // [esp+8h] [ebp-4h] BYREF

  handle = 0;
  v3 = BCryptOpenAlgorithmProvider(&handle, L"RNG", 0, 0);
  if ( v3 >= 0 )
  {
    v3 = BCryptGenRandom(handle, (PUCHAR)&salt, 8u, 0);
    v4 = v3 >= 0;
  }
  else
  {
    v4 = 0;
  }
  SetLastError((unsigned int)&_ImageBase | v3);
  if ( handle )
    BCryptCloseAlgorithmProvider(handle, 0);
  return v4;
}

```

## disassembly

```asm
0x100c43c0  mov     edi, edi
0x100c43c2  push    ebp
0x100c43c3  mov     ebp, esp
0x100c43c5  push    ecx
0x100c43c6  push    esi
0x100c43c7  push    edi
0x100c43c8  xor     edi, edi
0x100c43ca  lea     eax, [ebp+handle]
0x100c43cd  push    edi; dwFlags
0x100c43ce  push    edi; pszImplementation
0x100c43cf  push    offset aRng; "RNG"
0x100c43d4  xor     esi, esi
0x100c43d6  mov     [ebp+handle], edi
0x100c43d9  push    eax; phAlgorithm
0x100c43da  inc     esi
0x100c43db  call    ds:__imp__BCryptOpenAlgorithmProvider@16; BCryptOpenAlgorithmProvider(x,x,x,x)
0x100c43e1  test    eax, eax
0x100c43e3  jns     short loc_100C43E9
0x100c43e5  mov     esi, edi
0x100c43e7  jmp     short CleanUp_177
0x100c43e9  push    edi; dwFlags
0x100c43ea  push    8; cbBuffer
0x100c43ec  push    offset salt; pbBuffer
0x100c43f1  push    [ebp+handle]; hAlgorithm
0x100c43f4  call    ds:__imp__BCryptGenRandom@16; BCryptGenRandom(x,x,x,x)
0x100c43fa  xor     ecx, ecx
0x100c43fc  test    eax, eax
0x100c43fe  cmovs   esi, ecx
0x100c4401  or      eax, offset __ImageBase
0x100c4406  push    eax; dwErrCode
0x100c4407  call    ds:__imp__SetLastError@4; SetLastError(x)
0x100c440d  cmp     [ebp+handle], edi
0x100c4410  jz      short loc_100C441C
0x100c4412  push    edi; dwFlags
0x100c4413  push    [ebp+handle]; hAlgorithm
0x100c4416  call    ds:__imp__BCryptCloseAlgorithmProvider@8; BCryptCloseAlgorithmProvider(x,x)
0x100c441c  pop     edi
0x100c441d  mov     eax, esi
0x100c441f  pop     esi
0x100c4420  leave
0x100c4421  retn    0Ch
```
