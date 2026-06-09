# ATL::CSecurityDescriptor::SetOwner(void *,int)

- ea: `0x18004548c`
- end: `0x180045594`
- name: `?SetOwner@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z`
- size: `264`
- prototype: `int(ATL::CSecurityDescriptor *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003acc0`

## callees

- `0x18004548c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800454d1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180045577`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800454d1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180045577`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004550c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004550c`
- `KERNEL32!GetLastError` at `0x1800454ad`
- `KERNEL32!GetLastError` at `0x180045534`
- `KERNEL32!GetLastError` at `0x18004555f`
- `KERNEL32!GetLastError` at `0x1800454ad`
- `KERNEL32!GetLastError` at `0x180045534`
- `KERNEL32!GetLastError` at `0x18004555f`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800454a3`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180045555`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800454a3`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180045555`
- `ADVAPI32!IsValidSid` at `0x1800454eb`
- `ADVAPI32!IsValidSid` at `0x1800454eb`
- `ADVAPI32!GetLengthSid` at `0x180045502`
- `ADVAPI32!GetLengthSid` at `0x180045502`
- `ADVAPI32!CopySid` at `0x18004552a`
- `ADVAPI32!CopySid` at `0x18004552a`

## pseudocode

```c
int __fastcall ATL::CSecurityDescriptor::SetOwner(ATL::CSecurityDescriptor *this, void *a2, BOOL a3)
{
  int result; // eax
  void *v7; // rcx
  DWORD LengthSid; // esi
  void *v9; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  signed int v12; // eax

  if ( SetSecurityDescriptorOwner(*(PSECURITY_DESCRIPTOR *)this, 0, a3) )
  {
    v7 = (void *)*((_QWORD *)this + 1);
    if ( v7 )
    {
      free(v7);
      *((_QWORD *)this + 1) = 0;
    }
    if ( a2 )
    {
      if ( !IsValidSid(a2) )
        return -2147024809;
      LengthSid = GetLengthSid(a2);
      v9 = malloc(LengthSid);
      *((_QWORD *)this + 1) = v9;
      if ( !v9 )
        return -2147024882;
      if ( !CopySid(LengthSid, v9, a2) )
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
        free(*((void **)this + 1));
        result = v11;
        *((_QWORD *)this + 1) = 0;
        return result;
      }
      if ( !SetSecurityDescriptorOwner(*(PSECURITY_DESCRIPTOR *)this, *((PSID *)this + 1), a3) )
      {
        v12 = GetLastError();
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        v11 = v12;
        goto LABEL_18;
      }
    }
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18004548c  push    rbx
0x18004548e  push    rbp
0x18004548f  push    rsi
0x180045490  push    rdi
0x180045491  sub     rsp, 28h
0x180045495  mov     rbx, rdx
0x180045498  mov     rdi, rcx
0x18004549b  mov     rcx, [rcx]; pSecurityDescriptor
0x18004549e  xor     edx, edx; pOwner
0x1800454a0  mov     ebp, r8d
0x1800454a3  call    cs:__imp_SetSecurityDescriptorOwner
0x1800454a9  test    eax, eax
0x1800454ab  jnz     short loc_1800454C8
0x1800454ad  call    cs:__imp_GetLastError
0x1800454b3  test    eax, eax
0x1800454b5  jle     loc_18004558B
0x1800454bb  movzx   eax, ax
0x1800454be  or      eax, 80070000h
0x1800454c3  jmp     loc_18004558B
0x1800454c8  mov     rcx, [rdi+8]; Block
0x1800454cc  test    rcx, rcx
0x1800454cf  jz      short loc_1800454DF
0x1800454d1  call    cs:__imp_free
0x1800454d7  mov     qword ptr [rdi+8], 0
0x1800454df  test    rbx, rbx
0x1800454e2  jz      loc_180045589
0x1800454e8  mov     rcx, rbx; pSid
0x1800454eb  call    cs:__imp_IsValidSid
0x1800454f1  test    eax, eax
0x1800454f3  jnz     short loc_1800454FF
0x1800454f5  mov     eax, 80070057h
0x1800454fa  jmp     loc_18004558B
0x1800454ff  mov     rcx, rbx; pSid
0x180045502  call    cs:__imp_GetLengthSid
0x180045508  mov     ecx, eax; Size
0x18004550a  mov     esi, eax
0x18004550c  call    cs:__imp_malloc
0x180045512  mov     [rdi+8], rax
0x180045516  test    rax, rax
0x180045519  jnz     short loc_180045522
0x18004551b  mov     eax, 8007000Eh
0x180045520  jmp     short loc_18004558B
0x180045522  mov     r8, rbx; pSourceSid
0x180045525  mov     rdx, rax; pDestinationSid
0x180045528  mov     ecx, esi; nDestinationSidLength
0x18004552a  call    cs:__imp_CopySid
0x180045530  test    eax, eax
0x180045532  jnz     short loc_18004554B
0x180045534  call    cs:__imp_GetLastError
0x18004553a  mov     ebx, eax
0x18004553c  test    eax, eax
0x18004553e  jle     short loc_180045573
0x180045540  movzx   ebx, ax
0x180045543  or      ebx, 80070000h
0x180045549  jmp     short loc_180045573
0x18004554b  mov     rdx, [rdi+8]; pOwner
0x18004554f  mov     r8d, ebp; bOwnerDefaulted
0x180045552  mov     rcx, [rdi]; pSecurityDescriptor
0x180045555  call    cs:__imp_SetSecurityDescriptorOwner
0x18004555b  test    eax, eax
0x18004555d  jnz     short loc_180045589
0x18004555f  call    cs:__imp_GetLastError
0x180045565  test    eax, eax
0x180045567  jle     short loc_180045571
0x180045569  movzx   eax, ax
0x18004556c  or      eax, 80070000h
0x180045571  mov     ebx, eax
0x180045573  mov     rcx, [rdi+8]; Block
0x180045577  call    cs:__imp_free
0x18004557d  mov     eax, ebx
0x18004557f  mov     qword ptr [rdi+8], 0
0x180045587  jmp     short loc_18004558B
0x180045589  xor     eax, eax
0x18004558b  add     rsp, 28h
0x18004558f  pop     rdi
0x180045590  pop     rsi
0x180045591  pop     rbp
0x180045592  pop     rbx
0x180045593  retn
```
