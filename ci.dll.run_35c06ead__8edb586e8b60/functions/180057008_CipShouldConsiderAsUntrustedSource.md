# CipShouldConsiderAsUntrustedSource

- ea: `0x180057008`
- end: `0x18005712d`
- name: `CipShouldConsiderAsUntrustedSource`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18008c95c`

## callees

- `0x180057008`
- `0x180057134`
- `0x1800912c0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1800570a3`
- `ntoskrnl!ObfDereferenceObject` at `0x1800570a3`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x180057112`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x180057112`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800570e1`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800570e1`

## pseudocode

```c
bool __fastcall CipShouldConsiderAsUntrustedSource(__int64 a1, struct _FILE_OBJECT *a2, int a3, _DWORD *a4)
{
  char v5; // si
  int v9; // ebx
  PVOID Object[5]; // [rsp+20h] [rbp-28h] BYREF
  char v11; // [rsp+58h] [rbp+10h] BYREF

  v5 = a3;
  if ( (a2->DeviceObject->Flags & 0x100) != 0 )
  {
    *a4 |= 0x8000u;
    return 0;
  }
  if ( (a3 & 0x20000000) != 0 || (a3 & 2) != 0 || (a3 & 0x40000000) != 0 || (g_CiOptions & 0x100) != 0 )
    return 0;
  Object[0] = 0;
  v11 = 0;
  if ( (int)CipIsCimBackedFile(a2, &v11, Object) >= 0 )
  {
    if ( v11 )
    {
      v9 = *(_DWORD *)(*((_QWORD *)Object[0] + 1) + 48LL);
      ObfDereferenceObject(Object[0]);
      if ( (v9 & 0x100) != 0 )
      {
        *a4 |= 0x8000u;
        return 0;
      }
    }
  }
  v11 = 0;
  if ( (int)CipGetVolumeFlags(a2) >= 0 )
  {
    if ( v11 )
    {
      *a4 |= 0x10000u;
      if ( (unsigned __int8)PsIsCurrentThreadInServerSilo() )
        return 0;
    }
  }
  return (v5 & 5) == 0 && ((v5 & 8) != 0 || (v5 & 0x10) == 0 && (unsigned int)PsIsProtectedProcessLight(a1));
}

```

## disassembly

```asm
0x180057008  mov     [rsp+arg_0], rbx
0x18005700d  mov     [rsp+arg_10], rbp
0x180057012  push    rsi
0x180057013  push    rdi
0x180057014  push    r14
0x180057016  sub     rsp, 30h
0x18005701a  mov     rax, [rdx+8]
0x18005701e  mov     rdi, r9
0x180057021  mov     esi, r8d
0x180057024  mov     rbp, rdx
0x180057027  mov     r14, rcx
0x18005702a  test    dword ptr [rax+30h], 100h
0x180057031  jz      short loc_18005704E
0x180057033  bts     dword ptr [r9], 0Fh
0x180057038  xor     al, al
0x18005703a  mov     rbx, [rsp+48h+arg_0]
0x18005703f  mov     rbp, [rsp+48h+arg_10]
0x180057044  add     rsp, 30h
0x180057048  pop     r14
0x18005704a  pop     rdi
0x18005704b  pop     rsi
0x18005704c  retn
0x18005704e  bt      esi, 1Dh
0x180057052  jb      short loc_180057038
0x180057054  test    sil, 2
0x180057058  jnz     short loc_180057038
0x18005705a  bt      esi, 1Eh
0x18005705e  jb      short loc_180057038
0x180057060  test    cs:g_CiOptions, 100h
0x18005706a  jnz     short loc_180057038
0x18005706c  lea     r8, [rsp+48h+Object]
0x180057071  mov     [rsp+48h+Object], 0
0x18005707a  lea     rdx, [rsp+48h+arg_8]
0x18005707f  mov     [rsp+48h+arg_8], 0
0x180057084  mov     rcx, rbp
0x180057087  call    CipIsCimBackedFile
0x18005708c  test    eax, eax
0x18005708e  js      short loc_1800570BE
0x180057090  cmp     [rsp+48h+arg_8], 0
0x180057095  jz      short loc_1800570BE
0x180057097  mov     rcx, [rsp+48h+Object]; Object
0x18005709c  mov     rax, [rcx+8]
0x1800570a0  mov     ebx, [rax+30h]
0x1800570a3  call    cs:__imp_ObfDereferenceObject
0x1800570aa  nop     dword ptr [rax+rax+00h]
0x1800570af  bt      ebx, 8
0x1800570b3  jnb     short loc_1800570BE
0x1800570b5  bts     dword ptr [rdi], 0Fh
0x1800570b9  jmp     loc_180057038
0x1800570be  lea     r8, [rsp+48h+arg_8]
0x1800570c3  mov     [rsp+48h+arg_8], 0
0x1800570c8  xor     edx, edx
0x1800570ca  mov     rcx, rbp; FileObject
0x1800570cd  call    CipGetVolumeFlags
0x1800570d2  test    eax, eax
0x1800570d4  js      short loc_1800570F5
0x1800570d6  cmp     [rsp+48h+arg_8], 0
0x1800570db  jz      short loc_1800570F5
0x1800570dd  bts     dword ptr [rdi], 10h
0x1800570e1  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x1800570e8  nop     dword ptr [rax+rax+00h]
0x1800570ed  test    al, al
0x1800570ef  jnz     loc_180057038
0x1800570f5  test    sil, 5
0x1800570f9  jnz     loc_180057038
0x1800570ff  test    sil, 8
0x180057103  jnz     short loc_180057126
0x180057105  test    sil, 10h
0x180057109  jnz     loc_180057038
0x18005710f  mov     rcx, r14
0x180057112  call    cs:__imp_PsIsProtectedProcessLight
0x180057119  nop     dword ptr [rax+rax+00h]
0x18005711e  test    eax, eax
0x180057120  jz      loc_180057038
0x180057126  mov     al, 1
0x180057128  jmp     loc_18005703A
```
