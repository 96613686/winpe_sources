# Mso::Security::HrGetEffectiveIL(ulong *)

- ea: `0x1801223c0`
- end: `0x180122447`
- name: `?HrGetEffectiveIL@Security@Mso@@YAJPEAK@Z`
- size: `135`
- prototype: `__int64 __fastcall(Mso::Security *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801123f0`

## callees

- `0x1801223c0`
- `0x180122448`
- `0x1801224d8`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180122412`
- `KERNEL32!GetCurrentProcess` at `0x180122412`
- `KERNEL32!CloseHandle` at `0x180122438`
- `KERNEL32!CloseHandle` at `0x180122438`
- `KERNEL32!GetCurrentThread` at `0x1801223e4`
- `KERNEL32!GetCurrentThread` at `0x1801223e4`
- `ADVAPI32!OpenThreadToken` at `0x1801223f9`
- `ADVAPI32!OpenThreadToken` at `0x1801223f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Mso::Security::HrGetEffectiveIL(Mso::Security *this, unsigned int *a2)
{
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  unsigned int *v5; // r8
  int TokenIL; // eax
  Mso::Security *CurrentProcess; // rax
  unsigned int *v8; // r8
  HANDLE v9; // rcx
  HANDLE TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  if ( this )
  {
    *(_DWORD *)this = 0x2000;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      TokenIL = Mso::Security::HrGetTokenIL((Mso::Security *)TokenHandle, this, v5);
    }
    else
    {
      CurrentProcess = (Mso::Security *)GetCurrentProcess();
      TokenIL = Mso::Security::HrGetProcessIL(CurrentProcess, this, v8);
    }
    v3 = TokenIL;
    v9 = TokenHandle;
    if ( TokenHandle )
    {
      TokenHandle = 0;
      CloseHandle(v9);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v3;
}

```

## disassembly

```asm
0x1801223c0  push    rbx
0x1801223c2  sub     rsp, 20h
0x1801223c6  mov     rbx, rcx
0x1801223c9  mov     [rsp+28h+TokenHandle], 0
0x1801223d2  test    rcx, rcx
0x1801223d5  jnz     short loc_1801223DE
0x1801223d7  mov     ebx, 80004003h
0x1801223dc  jmp     short loc_18012243F
0x1801223de  mov     dword ptr [rcx], 2000h
0x1801223e4  call    cs:__imp_GetCurrentThread
0x1801223ea  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1801223ef  xor     r8d, r8d; OpenAsSelf
0x1801223f2  lea     edx, [r8+8]; DesiredAccess
0x1801223f6  mov     rcx, rax; ThreadHandle
0x1801223f9  call    cs:__imp_OpenThreadToken
0x1801223ff  test    eax, eax
0x180122401  jz      short loc_180122412
0x180122403  mov     rdx, rbx; void *
0x180122406  mov     rcx, [rsp+28h+TokenHandle]; this
0x18012240b  call    ?HrGetTokenIL@Security@Mso@@YAJPEAXPEAK@Z; Mso::Security::HrGetTokenIL(void *,ulong *)
0x180122410  jmp     short loc_180122423
0x180122412  call    cs:__imp_GetCurrentProcess
0x180122418  mov     rcx, rax; this
0x18012241b  mov     rdx, rbx; void *
0x18012241e  call    ?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z; Mso::Security::HrGetProcessIL(void *,ulong *)
0x180122423  mov     ebx, eax
0x180122425  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18012242a  test    rcx, rcx
0x18012242d  jz      short loc_18012243F
0x18012242f  mov     [rsp+28h+TokenHandle], 0
0x180122438  call    cs:__imp_CloseHandle
0x18012243e  nop
0x18012243f  mov     eax, ebx
0x180122441  add     rsp, 20h
0x180122445  pop     rbx
0x180122446  retn
```
