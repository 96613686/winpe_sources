# GetThreadToken(void * *)

- ea: `0x18000b624`
- end: `0x18000b725`
- name: `?GetThreadToken@@YAJPEAPEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b988`
- `0x18000eeb8`

## callees

- `0x18000b624`
- `0x180010010`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x18000b65b`
- `ADVAPI32!OpenThreadToken` at `0x18000b6d6`
- `ADVAPI32!OpenThreadToken` at `0x18000b65b`
- `ADVAPI32!OpenThreadToken` at `0x18000b6d6`
- `ole32!CoGetCallContext` at `0x18000b696`
- `ole32!CoGetCallContext` at `0x18000b696`
- `KERNEL32!GetCurrentThread` at `0x18000b643`
- `KERNEL32!GetCurrentThread` at `0x18000b643`
- `KERNEL32!GetLastError` at `0x18000b66c`
- `KERNEL32!GetLastError` at `0x18000b6e0`
- `KERNEL32!GetLastError` at `0x18000b66c`
- `KERNEL32!GetLastError` at `0x18000b6e0`

## pseudocode

```c
__int64 __fastcall GetThreadToken(PHANDLE TokenHandle)
{
  int v1; // esi
  HANDLE CurrentThread; // rbp
  signed int v4; // ebx
  signed int LastError; // eax
  HRESULT v6; // eax
  void *ppInterface; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  ppInterface = 0;
  if ( !TokenHandle )
  {
    v4 = -2147024809;
    goto LABEL_15;
  }
  *TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, TokenHandle) )
  {
LABEL_3:
    v4 = 0;
    goto LABEL_15;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError != 1008 )
    goto LABEL_5;
  v6 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  if ( v6 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
    if ( v4 < 0 )
      goto LABEL_15;
    v1 = 1;
    if ( OpenThreadToken(CurrentThread, 0x20008u, 1, TokenHandle) )
      goto LABEL_3;
    LastError = GetLastError();
    v4 = LastError;
LABEL_5:
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_15;
  }
  v4 = 0;
  if ( v6 != -2147417833 )
    v4 = v6;
LABEL_15:
  if ( ppInterface )
  {
    if ( v1 )
      (*(void (**)(void))(*(_QWORD *)ppInterface + 40LL))();
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b624  push    rbx
0x18000b626  push    rbp
0x18000b627  push    rsi
0x18000b628  push    rdi
0x18000b629  sub     rsp, 28h
0x18000b62d  xor     esi, esi
0x18000b62f  mov     rdi, rcx
0x18000b632  mov     [rsp+48h+ppInterface], rsi
0x18000b637  test    rcx, rcx
0x18000b63a  jz      loc_18000B6EA
0x18000b640  mov     [rcx], rsi
0x18000b643  call    cs:__imp_GetCurrentThread
0x18000b649  mov     r9, rdi; TokenHandle
0x18000b64c  lea     r8d, [rsi+1]; OpenAsSelf
0x18000b650  mov     rcx, rax; ThreadHandle
0x18000b653  mov     edx, 20008h; DesiredAccess
0x18000b658  mov     rbp, rax
0x18000b65b  call    cs:__imp_OpenThreadToken
0x18000b661  test    eax, eax
0x18000b663  jz      short loc_18000B66C
0x18000b665  xor     ebx, ebx
0x18000b667  jmp     loc_18000B6EF
0x18000b66c  call    cs:__imp_GetLastError
0x18000b672  mov     ebx, eax
0x18000b674  cmp     eax, 3F0h
0x18000b679  jz      short loc_18000B68A
0x18000b67b  test    eax, eax
0x18000b67d  jle     short loc_18000B6EF
0x18000b67f  movzx   ebx, ax
0x18000b682  or      ebx, 80070000h
0x18000b688  jmp     short loc_18000B6EF
0x18000b68a  lea     rdx, [rsp+48h+ppInterface]; ppInterface
0x18000b68f  lea     rcx, IID_IServerSecurity; riid
0x18000b696  call    cs:__imp_CoGetCallContext
0x18000b69c  test    eax, eax
0x18000b69e  jns     short loc_18000B6AC
0x18000b6a0  xor     ebx, ebx
0x18000b6a2  cmp     eax, 80010117h
0x18000b6a7  cmovnz  ebx, eax
0x18000b6aa  jmp     short loc_18000B6EF
0x18000b6ac  mov     rcx, [rsp+48h+ppInterface]
0x18000b6b1  mov     rax, [rcx]
0x18000b6b4  mov     rax, [rax+20h]
0x18000b6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6bd  mov     ebx, eax
0x18000b6bf  test    eax, eax
0x18000b6c1  js      short loc_18000B6EF
0x18000b6c3  mov     esi, 1
0x18000b6c8  mov     r9, rdi; TokenHandle
0x18000b6cb  mov     r8d, esi; OpenAsSelf
0x18000b6ce  mov     edx, 20008h; DesiredAccess
0x18000b6d3  mov     rcx, rbp; ThreadHandle
0x18000b6d6  call    cs:__imp_OpenThreadToken
0x18000b6dc  test    eax, eax
0x18000b6de  jnz     short loc_18000B665
0x18000b6e0  call    cs:__imp_GetLastError
0x18000b6e6  mov     ebx, eax
0x18000b6e8  jmp     short loc_18000B67B
0x18000b6ea  mov     ebx, 80070057h
0x18000b6ef  mov     rcx, [rsp+48h+ppInterface]
0x18000b6f4  test    rcx, rcx
0x18000b6f7  jz      short loc_18000B71A
0x18000b6f9  test    esi, esi
0x18000b6fb  jz      short loc_18000B709
0x18000b6fd  mov     rax, [rcx]
0x18000b700  mov     rax, [rax+28h]
0x18000b704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b709  mov     rcx, [rsp+48h+ppInterface]
0x18000b70e  mov     rax, [rcx]
0x18000b711  mov     rax, [rax+10h]
0x18000b715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b71a  mov     eax, ebx
0x18000b71c  add     rsp, 28h
0x18000b720  pop     rdi
0x18000b721  pop     rsi
0x18000b722  pop     rbp
0x18000b723  pop     rbx
0x18000b724  retn
```
