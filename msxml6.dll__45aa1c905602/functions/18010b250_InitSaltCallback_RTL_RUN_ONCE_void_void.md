# InitSaltCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18010b250`
- end: `0x18010b2e5`
- name: `?InitSaltCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `149`
- prototype: `int __fastcall(_RTL_RUN_ONCE *initOnce, void *parameter, void **context)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18010b250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010b2b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010b2b8`
- `bcrypt!BCryptGenRandom` at `0x18010b29f`
- `bcrypt!BCryptGenRandom` at `0x18010b29f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18010b271`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18010b271`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18010b2d0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18010b2d0`

## pseudocode

```c
_BOOL8 __fastcall InitSaltCallback(_RTL_RUN_ONCE *initOnce, void *parameter, void **context)
{
  NTSTATUS v3; // ecx
  BOOL v4; // ebx
  void *handle; // [rsp+48h] [rbp+20h] BYREF

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
  SetLastError(v3 | 0x10000000);
  if ( handle )
    BCryptCloseAlgorithmProvider(handle, 0);
  return v4;
}

```

## disassembly

```asm
0x18010b250  push    rbx
0x18010b252  sub     rsp, 20h
0x18010b256  xor     r9d, r9d; dwFlags
0x18010b259  mov     [rsp+28h+handle], 0
0x18010b262  xor     r8d, r8d; pszImplementation
0x18010b265  lea     parameter, aRng; "RNG"
0x18010b26c  lea     initOnce, [rsp+28h+handle]; phAlgorithm
0x18010b271  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18010b278  nop     dword ptr [rax+rax+00h]
0x18010b27d  mov     ecx, eax
0x18010b27f  test    eax, eax
0x18010b281  jns     short loc_18010B287
0x18010b283  xor     ebx, ebx
0x18010b285  jmp     short $CleanUp_274
0x18010b287  mov     initOnce, [rsp+28h+handle]; hAlgorithm
0x18010b28c  lea     parameter, salt; pbBuffer
0x18010b293  mov     ebx, 1
0x18010b298  xor     r9d, r9d; dwFlags
0x18010b29b  lea     r8d, [rbx+7]; cbBuffer
0x18010b29f  call    cs:__imp_BCryptGenRandom
0x18010b2a6  nop     dword ptr [rax+rax+00h]
0x18010b2ab  mov     ecx, eax
0x18010b2ad  xor     eax, eax
0x18010b2af  test    ecx, ecx
0x18010b2b1  cmovs   ebx, eax
0x18010b2b4  bts     ecx, 1Ch; dwErrCode
0x18010b2b8  call    cs:__imp_SetLastError
0x18010b2bf  nop     dword ptr [rax+rax+00h]
0x18010b2c4  mov     initOnce, [rsp+28h+handle]; hAlgorithm
0x18010b2c9  test    initOnce, initOnce
0x18010b2cc  jz      short loc_18010B2DC
0x18010b2ce  xor     edx, edx; dwFlags
0x18010b2d0  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18010b2d7  nop     dword ptr [rax+rax+00h]
0x18010b2dc  mov     eax, ebx
0x18010b2de  add     rsp, 20h
0x18010b2e2  pop     rbx
0x18010b2e3  retn
```
