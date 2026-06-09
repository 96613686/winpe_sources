# InitSaltCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180108b60`
- end: `0x180108bdc`
- name: `?InitSaltCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `124`
- prototype: `int __fastcall(_RTL_RUN_ONCE *initOnce, void *parameter, void **context)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180108b60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180108bbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180108bbc`
- `bcrypt!BCryptGenRandom` at `0x180108ba9`
- `bcrypt!BCryptGenRandom` at `0x180108ba9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180108b81`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180108b81`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180108bce`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180108bce`

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
0x180108b60  push    rbx
0x180108b62  sub     rsp, 20h
0x180108b66  xor     r9d, r9d; dwFlags
0x180108b69  mov     [rsp+28h+handle], 0
0x180108b72  xor     r8d, r8d; pszImplementation
0x180108b75  lea     parameter, aRng; "RNG"
0x180108b7c  lea     initOnce, [rsp+28h+handle]; phAlgorithm
0x180108b81  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180108b87  mov     ecx, eax
0x180108b89  test    eax, eax
0x180108b8b  jns     short loc_180108B91
0x180108b8d  xor     ebx, ebx
0x180108b8f  jmp     short $CleanUp_274
0x180108b91  mov     initOnce, [rsp+28h+handle]; hAlgorithm
0x180108b96  lea     parameter, salt; pbBuffer
0x180108b9d  mov     ebx, 1
0x180108ba2  xor     r9d, r9d; dwFlags
0x180108ba5  lea     r8d, [rbx+7]; cbBuffer
0x180108ba9  call    cs:__imp_BCryptGenRandom
0x180108baf  mov     ecx, eax
0x180108bb1  xor     eax, eax
0x180108bb3  test    ecx, ecx
0x180108bb5  cmovs   ebx, eax
0x180108bb8  bts     ecx, 1Ch; dwErrCode
0x180108bbc  call    cs:__imp_SetLastError
0x180108bc2  mov     initOnce, [rsp+28h+handle]; hAlgorithm
0x180108bc7  test    initOnce, initOnce
0x180108bca  jz      short loc_180108BD4
0x180108bcc  xor     edx, edx; dwFlags
0x180108bce  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180108bd4  mov     eax, ebx
0x180108bd6  add     rsp, 20h
0x180108bda  pop     rbx
0x180108bdb  retn
```
