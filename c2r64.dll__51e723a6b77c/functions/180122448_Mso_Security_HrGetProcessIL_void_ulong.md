# Mso::Security::HrGetProcessIL(void *,ulong *)

- ea: `0x180122448`
- end: `0x1801224d8`
- name: `?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z`
- size: `144`
- prototype: `int(Mso::Security *__hidden this, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801223c0`

## callees

- `0x180122448`
- `0x1801224d8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180122489`
- `KERNEL32!GetLastError` at `0x180122489`
- `KERNEL32!CloseHandle` at `0x1801224c4`
- `KERNEL32!CloseHandle` at `0x1801224c4`
- `ADVAPI32!OpenProcessToken` at `0x18012247f`
- `ADVAPI32!OpenProcessToken` at `0x18012247f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Mso::Security::HrGetProcessIL(Mso::Security *this, DWORD *a2, unsigned int *a3)
{
  unsigned int TokenIL; // ebx
  unsigned int *v5; // r8
  signed int LastError; // eax
  HANDLE v7; // rcx
  HANDLE TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  if ( a2 && (*a2 = 0x2000, this) )
  {
    if ( OpenProcessToken(this, 8u, &TokenHandle) )
      goto LABEL_8;
    LastError = GetLastError();
    TokenIL = LastError;
    if ( LastError > 0 )
      TokenIL = (unsigned __int16)LastError | 0x80070000;
    if ( !TokenIL )
LABEL_8:
      TokenIL = Mso::Security::HrGetTokenIL((Mso::Security *)TokenHandle, a2, v5);
    v7 = TokenHandle;
    if ( TokenHandle )
    {
      TokenHandle = 0;
      CloseHandle(v7);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return TokenIL;
}

```

## disassembly

```asm
0x180122448  mov     [rsp+arg_0], rbx
0x18012244d  push    rdi
0x18012244e  sub     rsp, 20h
0x180122452  mov     rdi, rdx
0x180122455  mov     [rsp+28h+TokenHandle], 0
0x18012245e  test    rdx, rdx
0x180122461  jnz     short loc_18012246A
0x180122463  mov     ebx, 80004003h
0x180122468  jmp     short loc_1801224CB
0x18012246a  mov     dword ptr [rdx], 2000h
0x180122470  test    rcx, rcx
0x180122473  jz      short loc_180122463
0x180122475  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18012247a  mov     edx, 8; DesiredAccess
0x18012247f  call    cs:__imp_OpenProcessToken
0x180122485  test    eax, eax
0x180122487  jnz     short loc_1801224A2
0x180122489  call    cs:__imp_GetLastError
0x18012248f  mov     ebx, eax
0x180122491  test    eax, eax
0x180122493  jle     short loc_18012249E
0x180122495  movzx   ebx, ax
0x180122498  or      ebx, 80070000h
0x18012249e  test    ebx, ebx
0x1801224a0  jnz     short loc_1801224B1
0x1801224a2  mov     rdx, rdi; void *
0x1801224a5  mov     rcx, [rsp+28h+TokenHandle]; this
0x1801224aa  call    ?HrGetTokenIL@Security@Mso@@YAJPEAXPEAK@Z; Mso::Security::HrGetTokenIL(void *,ulong *)
0x1801224af  mov     ebx, eax
0x1801224b1  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1801224b6  test    rcx, rcx
0x1801224b9  jz      short loc_1801224CB
0x1801224bb  mov     [rsp+28h+TokenHandle], 0
0x1801224c4  call    cs:__imp_CloseHandle
0x1801224ca  nop
0x1801224cb  mov     eax, ebx
0x1801224cd  mov     rbx, [rsp+28h+arg_0]
0x1801224d2  add     rsp, 20h
0x1801224d6  pop     rdi
0x1801224d7  retn
```
