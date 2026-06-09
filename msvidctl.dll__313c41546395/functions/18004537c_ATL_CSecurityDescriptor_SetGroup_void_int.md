# ATL::CSecurityDescriptor::SetGroup(void *,int)

- ea: `0x18004537c`
- end: `0x180045484`
- name: `?SetGroup@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z`
- size: `264`
- prototype: `int(ATL::CSecurityDescriptor *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003acc0`

## callees

- `0x18004537c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800453c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180045467`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800453c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180045467`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800453fc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800453fc`
- `KERNEL32!GetLastError` at `0x18004539d`
- `KERNEL32!GetLastError` at `0x180045424`
- `KERNEL32!GetLastError` at `0x18004544f`
- `KERNEL32!GetLastError` at `0x18004539d`
- `KERNEL32!GetLastError` at `0x180045424`
- `KERNEL32!GetLastError` at `0x18004544f`
- `ADVAPI32!IsValidSid` at `0x1800453db`
- `ADVAPI32!IsValidSid` at `0x1800453db`
- `ADVAPI32!GetLengthSid` at `0x1800453f2`
- `ADVAPI32!GetLengthSid` at `0x1800453f2`
- `ADVAPI32!CopySid` at `0x18004541a`
- `ADVAPI32!CopySid` at `0x18004541a`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180045393`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180045445`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180045393`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180045445`

## pseudocode

```c
int __fastcall ATL::CSecurityDescriptor::SetGroup(ATL::CSecurityDescriptor *this, void *a2, BOOL a3)
{
  int result; // eax
  void *v7; // rcx
  DWORD LengthSid; // esi
  void *v9; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  signed int v12; // eax

  if ( SetSecurityDescriptorGroup(*(PSECURITY_DESCRIPTOR *)this, 0, a3) )
  {
    v7 = (void *)*((_QWORD *)this + 2);
    if ( v7 )
    {
      free(v7);
      *((_QWORD *)this + 2) = 0;
    }
    if ( a2 )
    {
      if ( !IsValidSid(a2) )
        return -2147024809;
      LengthSid = GetLengthSid(a2);
      v9 = malloc(LengthSid);
      *((_QWORD *)this + 2) = v9;
      if ( !v9 )
        return -2147024882;
      if ( !CopySid(LengthSid, v9, a2) )
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
        free(*((void **)this + 2));
        result = v11;
        *((_QWORD *)this + 2) = 0;
        return result;
      }
      if ( !SetSecurityDescriptorGroup(*(PSECURITY_DESCRIPTOR *)this, *((PSID *)this + 2), a3) )
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
0x18004537c  push    rbx
0x18004537e  push    rbp
0x18004537f  push    rsi
0x180045380  push    rdi
0x180045381  sub     rsp, 28h
0x180045385  mov     rbx, rdx
0x180045388  mov     rdi, rcx
0x18004538b  mov     rcx, [rcx]; pSecurityDescriptor
0x18004538e  xor     edx, edx; pGroup
0x180045390  mov     ebp, r8d
0x180045393  call    cs:__imp_SetSecurityDescriptorGroup
0x180045399  test    eax, eax
0x18004539b  jnz     short loc_1800453B8
0x18004539d  call    cs:__imp_GetLastError
0x1800453a3  test    eax, eax
0x1800453a5  jle     loc_18004547B
0x1800453ab  movzx   eax, ax
0x1800453ae  or      eax, 80070000h
0x1800453b3  jmp     loc_18004547B
0x1800453b8  mov     rcx, [rdi+10h]; Block
0x1800453bc  test    rcx, rcx
0x1800453bf  jz      short loc_1800453CF
0x1800453c1  call    cs:__imp_free
0x1800453c7  mov     qword ptr [rdi+10h], 0
0x1800453cf  test    rbx, rbx
0x1800453d2  jz      loc_180045479
0x1800453d8  mov     rcx, rbx; pSid
0x1800453db  call    cs:__imp_IsValidSid
0x1800453e1  test    eax, eax
0x1800453e3  jnz     short loc_1800453EF
0x1800453e5  mov     eax, 80070057h
0x1800453ea  jmp     loc_18004547B
0x1800453ef  mov     rcx, rbx; pSid
0x1800453f2  call    cs:__imp_GetLengthSid
0x1800453f8  mov     ecx, eax; Size
0x1800453fa  mov     esi, eax
0x1800453fc  call    cs:__imp_malloc
0x180045402  mov     [rdi+10h], rax
0x180045406  test    rax, rax
0x180045409  jnz     short loc_180045412
0x18004540b  mov     eax, 8007000Eh
0x180045410  jmp     short loc_18004547B
0x180045412  mov     r8, rbx; pSourceSid
0x180045415  mov     rdx, rax; pDestinationSid
0x180045418  mov     ecx, esi; nDestinationSidLength
0x18004541a  call    cs:__imp_CopySid
0x180045420  test    eax, eax
0x180045422  jnz     short loc_18004543B
0x180045424  call    cs:__imp_GetLastError
0x18004542a  mov     ebx, eax
0x18004542c  test    eax, eax
0x18004542e  jle     short loc_180045463
0x180045430  movzx   ebx, ax
0x180045433  or      ebx, 80070000h
0x180045439  jmp     short loc_180045463
0x18004543b  mov     rdx, [rdi+10h]; pGroup
0x18004543f  mov     r8d, ebp; bGroupDefaulted
0x180045442  mov     rcx, [rdi]; pSecurityDescriptor
0x180045445  call    cs:__imp_SetSecurityDescriptorGroup
0x18004544b  test    eax, eax
0x18004544d  jnz     short loc_180045479
0x18004544f  call    cs:__imp_GetLastError
0x180045455  test    eax, eax
0x180045457  jle     short loc_180045461
0x180045459  movzx   eax, ax
0x18004545c  or      eax, 80070000h
0x180045461  mov     ebx, eax
0x180045463  mov     rcx, [rdi+10h]; Block
0x180045467  call    cs:__imp_free
0x18004546d  mov     eax, ebx
0x18004546f  mov     qword ptr [rdi+10h], 0
0x180045477  jmp     short loc_18004547B
0x180045479  xor     eax, eax
0x18004547b  add     rsp, 28h
0x18004547f  pop     rdi
0x180045480  pop     rsi
0x180045481  pop     rbp
0x180045482  pop     rbx
0x180045483  retn
```
