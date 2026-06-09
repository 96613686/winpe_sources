# CoRegGetICR

- ea: `0x180002464`
- end: `0x180002574`
- name: `CoRegGetICR`
- size: `272`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014d0`
- `0x180002430`

## callees

- `0x180002464`
- `0x1800029c8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800024ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002563`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800024ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002549`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000248e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000248e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000249c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000253b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000249c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000253b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002479`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002479`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800024c7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000250c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800024c7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000250c`

## pseudocode

```c
__int64 __fastcall CoRegGetICR(struct IComponentRecords **a1)
{
  signed int v1; // ebx
  int v3; // esi
  HANDLE CurrentThread; // rax
  int i; // edi
  int ICR; // eax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  v1 = 0;
  TokenHandle = 0;
  v3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) && !SetThreadToken(0, 0) )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  for ( i = 0; i < 10; ++i )
  {
    if ( i == 5 )
      Sleep(0x3E8u);
    ICR = _RegGetICR(a1, v3);
    v1 = ICR;
    if ( ICR >= 0 )
    {
      if ( !*a1 )
        v1 = -2147418113;
      break;
    }
    switch ( ICR )
    {
      case -2147217387:
        goto LABEL_17;
      case -2147217392:
        continue;
      case -2147024894:
        if ( i != 3 )
          continue;
LABEL_17:
        v3 = 1;
        continue;
      case -2147024893:
        goto LABEL_17;
    }
    if ( ICR != -2147024891 )
    {
      if ( ICR != -2147024864 )
        break;
      Sleep(0x1F4u);
    }
  }
  if ( TokenHandle )
  {
    if ( !SetThreadToken(0, TokenHandle) && v1 >= 0 )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180002464  push    rbx
0x180002466  push    rbp
0x180002467  push    rsi
0x180002468  push    rdi
0x180002469  sub     rsp, 28h
0x18000246d  xor     ebx, ebx
0x18000246f  mov     rbp, rcx
0x180002472  mov     [rsp+48h+TokenHandle], rbx
0x180002477  xor     esi, esi
0x180002479  call    cs:__imp_GetCurrentThread
0x18000247f  mov     rcx, rax; ThreadHandle
0x180002482  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180002487  lea     edx, [rbx+4]; DesiredAccess
0x18000248a  lea     r8d, [rbx+1]; OpenAsSelf
0x18000248e  call    cs:__imp_OpenThreadToken
0x180002494  test    eax, eax
0x180002496  jz      short loc_1800024B6
0x180002498  xor     edx, edx; Token
0x18000249a  xor     ecx, ecx; Thread
0x18000249c  call    cs:__imp_SetThreadToken
0x1800024a2  test    eax, eax
0x1800024a4  jnz     short loc_1800024B6
0x1800024a6  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800024ab  call    cs:__imp_CloseHandle
0x1800024b1  mov     [rsp+48h+TokenHandle], rbx
0x1800024b6  xor     edi, edi
0x1800024b8  cmp     edi, 0Ah
0x1800024bb  jge     short loc_18000252F
0x1800024bd  cmp     edi, 5
0x1800024c0  jnz     short loc_1800024CD
0x1800024c2  mov     ecx, 3E8h; dwMilliseconds
0x1800024c7  call    cs:__imp_Sleep
0x1800024cd  mov     edx, esi; int
0x1800024cf  mov     rcx, rbp; struct IComponentRecords **
0x1800024d2  call    ?_RegGetICR@@YAJPEAPEAUIComponentRecords@@H@Z; _RegGetICR(IComponentRecords * *,int)
0x1800024d7  mov     ebx, eax
0x1800024d9  test    eax, eax
0x1800024db  jns     short loc_180002522
0x1800024dd  cmp     eax, 80041015h
0x1800024e2  jz      short loc_180002519
0x1800024e4  cmp     eax, 80041010h
0x1800024e9  jz      short loc_18000251E
0x1800024eb  cmp     eax, 80070002h
0x1800024f0  jz      short loc_180002514
0x1800024f2  cmp     eax, 80070003h
0x1800024f7  jz      short loc_180002519
0x1800024f9  cmp     eax, 80070005h
0x1800024fe  jz      short loc_18000251E
0x180002500  cmp     eax, 80070020h
0x180002505  jnz     short loc_18000252F
0x180002507  mov     ecx, 1F4h; dwMilliseconds
0x18000250c  call    cs:__imp_Sleep
0x180002512  jmp     short loc_18000251E
0x180002514  cmp     edi, 3
0x180002517  jnz     short loc_18000251E
0x180002519  mov     esi, 1
0x18000251e  inc     edi
0x180002520  jmp     short loc_1800024B8
0x180002522  cmp     qword ptr [rbp+0], 0
0x180002527  mov     eax, 8000FFFFh
0x18000252c  cmovz   ebx, eax
0x18000252f  mov     rdx, [rsp+48h+TokenHandle]; Token
0x180002534  test    rdx, rdx
0x180002537  jz      short loc_180002569
0x180002539  xor     ecx, ecx; Thread
0x18000253b  call    cs:__imp_SetThreadToken
0x180002541  test    eax, eax
0x180002543  jnz     short loc_18000255E
0x180002545  test    ebx, ebx
0x180002547  js      short loc_18000255E
0x180002549  call    cs:__imp_GetLastError
0x18000254f  mov     ebx, eax
0x180002551  test    eax, eax
0x180002553  jle     short loc_18000255E
0x180002555  movzx   ebx, ax
0x180002558  or      ebx, 80070000h
0x18000255e  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180002563  call    cs:__imp_CloseHandle
0x180002569  mov     eax, ebx
0x18000256b  add     rsp, 28h
0x18000256f  pop     rdi
0x180002570  pop     rsi
0x180002571  pop     rbp
0x180002572  pop     rbx
0x180002573  retn
```
