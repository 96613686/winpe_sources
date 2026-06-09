# InitSaltCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x100c42c0`
- end: `0x100c4324`
- name: `?InitSaltCallback@@YGHPAT_RTL_RUN_ONCE@@PAXPAPAX@Z`
- size: `100`
- prototype: `int __stdcall(_RTL_RUN_ONCE *initOnce, void *parameter, void **context)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100c42c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x100c4307`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x100c4307`
- `bcrypt!BCryptGenRandom` at `0x100c42f4`
- `bcrypt!BCryptGenRandom` at `0x100c42f4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x100c42db`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x100c42db`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x100c4316`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x100c4316`

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
0x100c42c0  mov     edi, edi
0x100c42c2  push    ebp
0x100c42c3  mov     ebp, esp
0x100c42c5  push    ecx
0x100c42c6  push    esi
0x100c42c7  push    edi
0x100c42c8  xor     edi, edi
0x100c42ca  lea     eax, [ebp+handle]
0x100c42cd  push    edi; dwFlags
0x100c42ce  push    edi; pszImplementation
0x100c42cf  push    offset aRng; "RNG"
0x100c42d4  xor     esi, esi
0x100c42d6  mov     [ebp+handle], edi
0x100c42d9  push    eax; phAlgorithm
0x100c42da  inc     esi
0x100c42db  call    ds:__imp__BCryptOpenAlgorithmProvider@16; BCryptOpenAlgorithmProvider(x,x,x,x)
0x100c42e1  test    eax, eax
0x100c42e3  jns     short loc_100C42E9
0x100c42e5  mov     esi, edi
0x100c42e7  jmp     short CleanUp_177
0x100c42e9  push    edi; dwFlags
0x100c42ea  push    8; cbBuffer
0x100c42ec  push    offset salt; pbBuffer
0x100c42f1  push    [ebp+handle]; hAlgorithm
0x100c42f4  call    ds:__imp__BCryptGenRandom@16; BCryptGenRandom(x,x,x,x)
0x100c42fa  xor     ecx, ecx
0x100c42fc  test    eax, eax
0x100c42fe  cmovs   esi, ecx
0x100c4301  or      eax, offset __ImageBase
0x100c4306  push    eax; dwErrCode
0x100c4307  call    ds:__imp__SetLastError@4; SetLastError(x)
0x100c430d  cmp     [ebp+handle], edi
0x100c4310  jz      short loc_100C431C
0x100c4312  push    edi; dwFlags
0x100c4313  push    [ebp+handle]; hAlgorithm
0x100c4316  call    ds:__imp__BCryptCloseAlgorithmProvider@8; BCryptCloseAlgorithmProvider(x,x)
0x100c431c  pop     edi
0x100c431d  mov     eax, esi
0x100c431f  pop     esi
0x100c4320  leave
0x100c4321  retn    0Ch
```
