# GetCurrentProcessIntegrityLevel(bool *,bool *,bool *)

- ea: `0x180024d04`
- end: `0x180024e0a`
- name: `?GetCurrentProcessIntegrityLevel@@YAXPEA_N00@Z`
- size: `262`
- prototype: `void __fastcall(bool *, bool *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023d98`

## callees

- `0x180024d04`
- `0x1800252e0`
- `0x180025c18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024d3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024d3d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024d50`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024d83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024d83`

## pseudocode

```c
void __fastcall GetCurrentProcessIntegrityLevel(bool *a1, bool *a2, bool *a3)
{
  DWORD v6; // ebx
  HANDLE CurrentProcess; // rax
  int ErrorError; // edi
  char v9; // cl
  DWORD v10; // [rsp+50h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  if ( byte_180299FF2 )
  {
    v9 = byte_180299FF1;
    goto LABEL_14;
  }
  v6 = 0x2000;
  TokenHandle = 0;
  v10 = 0x2000;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    ErrorError = TokenIntegrityRIDFromToken(TokenHandle, &v10);
    if ( ErrorError == -1073741821 )
      ErrorError = 1;
    CloseHandle(TokenHandle);
    v6 = v10;
  }
  else
  {
    ErrorError = HRESULTFromLastErrorError();
  }
  if ( ErrorError < 0 )
    goto LABEL_10;
  if ( v6 >= 0x2000 )
  {
    if ( v6 >= 0x3000 )
      byte_180299FF3 = 1;
LABEL_10:
    v9 = byte_180299FF1;
    if ( !byte_180299FF1 && !byte_180299FF3 )
      byte_18029A128 = 1;
    goto LABEL_13;
  }
  v9 = 1;
  byte_180299FF1 = 1;
LABEL_13:
  byte_180299FF2 = 1;
LABEL_14:
  *a1 = byte_180299FF3;
  *a2 = byte_18029A128;
  *a3 = v9;
}

```

## disassembly

```asm
0x180024d04  mov     [rsp+arg_10], rbx
0x180024d09  push    rsi
0x180024d0a  push    rdi
0x180024d0b  push    r12
0x180024d0d  push    r14
0x180024d0f  push    r15
0x180024d11  sub     rsp, 20h
0x180024d15  cmp     cs:byte_180299FF2, 0
0x180024d1c  mov     rsi, r8
0x180024d1f  mov     r14, rdx
0x180024d22  mov     r15, rcx
0x180024d25  jnz     loc_180024DEE
0x180024d2b  mov     ebx, 2000h
0x180024d30  mov     [rsp+48h+TokenHandle], 0
0x180024d39  mov     [rsp+48h+arg_0], ebx
0x180024d3d  call    cs:__imp_GetCurrentProcess
0x180024d43  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180024d48  mov     edx, 8; DesiredAccess
0x180024d4d  mov     rcx, rax; ProcessHandle
0x180024d50  call    cs:__imp_OpenProcessToken
0x180024d56  mov     r12d, 1
0x180024d5c  test    eax, eax
0x180024d5e  jz      loc_180024E01
0x180024d64  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180024d69  lea     rdx, [rsp+48h+arg_0]
0x180024d6e  call    _TokenIntegrityRIDFromToken
0x180024d73  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180024d78  cmp     eax, 0C0000003h
0x180024d7d  mov     edi, eax
0x180024d7f  cmovz   edi, r12d
0x180024d83  call    cs:__imp_CloseHandle
0x180024d89  mov     ebx, [rsp+48h+arg_0]
0x180024d8d  test    edi, edi
0x180024d8f  js      short loc_180024DA8
0x180024d91  cmp     ebx, 2000h
0x180024d97  jb      short loc_180024DF6
0x180024d99  cmp     ebx, 3000h
0x180024d9f  jb      short loc_180024DA8
0x180024da1  mov     cs:byte_180299FF3, r12b
0x180024da8  mov     cl, cs:byte_180299FF1
0x180024dae  test    cl, cl
0x180024db0  jnz     short loc_180024DC1
0x180024db2  cmp     cs:byte_180299FF3, cl
0x180024db8  jnz     short loc_180024DC1
0x180024dba  mov     cs:byte_18029A128, r12b
0x180024dc1  mov     cs:byte_180299FF2, r12b
0x180024dc8  mov     al, cs:byte_180299FF3
0x180024dce  mov     rbx, [rsp+48h+arg_10]
0x180024dd3  mov     [r15], al
0x180024dd6  mov     al, cs:byte_18029A128
0x180024ddc  mov     [r14], al
0x180024ddf  mov     [rsi], cl
0x180024de1  add     rsp, 20h
0x180024de5  pop     r15
0x180024de7  pop     r14
0x180024de9  pop     r12
0x180024deb  pop     rdi
0x180024dec  pop     rsi
0x180024ded  retn
0x180024dee  mov     cl, cs:byte_180299FF1
0x180024df4  jmp     short loc_180024DC8
0x180024df6  mov     cl, r12b
0x180024df9  mov     cs:byte_180299FF1, cl
0x180024dff  jmp     short loc_180024DC1
0x180024e01  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180024e06  mov     edi, eax
0x180024e08  jmp     short loc_180024D8D
```
