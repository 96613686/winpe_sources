# GetMandatoryPolicy(void *)

- ea: `0x1800647c0`
- end: `0x1800648e7`
- name: `?GetMandatoryPolicy@@YAKPEAX@Z`
- size: `295`
- prototype: `unsigned int __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180044474`

## callees

- `0x1800647c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800647fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800647fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064856`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800648d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800648d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064822`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064822`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180064885`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180064885`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800648b1`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800648b1`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800647ed`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18006484c`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800647ed`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18006484c`

## pseudocode

```c
__int64 __fastcall GetMandatoryPolicy(HANDLE Handle)
{
  unsigned int v1; // esi
  signed int LastError; // eax
  bool v4; // sf
  HLOCAL v5; // rdi
  signed int v6; // eax
  bool v7; // sf
  struct _ACL *v8; // rcx
  WORD i; // bx
  PACL pSacl; // [rsp+30h] [rbp-10h] BYREF
  LPVOID pAce; // [rsp+38h] [rbp-8h] BYREF
  DWORD nLengthNeeded; // [rsp+68h] [rbp+28h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+70h] [rbp+30h] BYREF
  WINBOOL bSaclPresent; // [rsp+78h] [rbp+38h] BYREF

  nLengthNeeded = 0;
  v1 = 0;
  if ( !GetKernelObjectSecurity(Handle, 0x10u, 0, 0, &nLengthNeeded) )
  {
    LastError = GetLastError();
    if ( LastError == 122 )
      goto LABEL_6;
    v4 = LastError < 0;
    if ( LastError > 0 )
      v4 = 1;
    if ( !v4 )
    {
LABEL_6:
      v5 = LocalAlloc(0x40u, nLengthNeeded);
      if ( v5 )
      {
        if ( GetKernelObjectSecurity(Handle, 0x10u, v5, nLengthNeeded, &nLengthNeeded) )
          goto LABEL_11;
        v6 = GetLastError();
        v7 = v6 < 0;
        if ( v6 > 0 )
          v7 = 1;
        if ( !v7 )
        {
LABEL_11:
          pSacl = 0;
          bSaclPresent = 0;
          bSaclDefaulted = 0;
          if ( GetSecurityDescriptorSacl(v5, &bSaclPresent, &pSacl, &bSaclDefaulted) )
          {
            v8 = pSacl;
            if ( pSacl )
            {
              for ( i = 0; i < pSacl->AceCount; ++i )
              {
                pAce = 0;
                if ( GetAce(v8, i, &pAce) )
                  v1 |= *((_DWORD *)pAce + 1);
                v8 = pSacl;
              }
            }
          }
        }
        LocalFree(v5);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800647c0  mov     [rsp-18h+arg_0], rbx
0x1800647c5  push    rbp
0x1800647c6  push    rsi
0x1800647c7  push    rdi
0x1800647c8  mov     rbp, rsp
0x1800647cb  sub     rsp, 40h
0x1800647cf  lea     rax, [rbp+nLengthNeeded]
0x1800647d3  mov     [rbp+nLengthNeeded], 0
0x1800647da  xor     esi, esi
0x1800647dc  mov     [rsp+40h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800647e1  xor     r9d, r9d; nLength
0x1800647e4  xor     r8d, r8d; pSecurityDescriptor
0x1800647e7  mov     rbx, rcx
0x1800647ea  lea     edx, [rsi+10h]; RequestedInformation
0x1800647ed  call    cs:__imp_GetKernelObjectSecurity
0x1800647f3  test    eax, eax
0x1800647f5  jnz     loc_1800648D8
0x1800647fb  call    cs:__imp_GetLastError
0x180064801  cmp     eax, 7Ah ; 'z'
0x180064804  jz      short loc_18006481A
0x180064806  test    eax, eax
0x180064808  jle     short loc_180064814
0x18006480a  movzx   eax, ax
0x18006480d  or      eax, 80070000h
0x180064812  test    eax, eax
0x180064814  js      loc_1800648D8
0x18006481a  mov     edx, [rbp+nLengthNeeded]; uBytes
0x18006481d  mov     ecx, 40h ; '@'; uFlags
0x180064822  call    cs:__imp_LocalAlloc
0x180064828  mov     rdi, rax
0x18006482b  test    rax, rax
0x18006482e  jz      loc_1800648D8
0x180064834  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180064838  lea     rax, [rbp+nLengthNeeded]
0x18006483c  mov     r8, rdi; pSecurityDescriptor
0x18006483f  mov     [rsp+40h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180064844  mov     edx, 10h; RequestedInformation
0x180064849  mov     rcx, rbx; Handle
0x18006484c  call    cs:__imp_GetKernelObjectSecurity
0x180064852  test    eax, eax
0x180064854  jnz     short loc_18006486C
0x180064856  call    cs:__imp_GetLastError
0x18006485c  test    eax, eax
0x18006485e  jle     short loc_18006486A
0x180064860  movzx   eax, ax
0x180064863  or      eax, 80070000h
0x180064868  test    eax, eax
0x18006486a  js      short loc_1800648CF
0x18006486c  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x180064870  mov     [rbp+pSacl], rsi
0x180064874  lea     r8, [rbp+pSacl]; pSacl
0x180064878  mov     [rbp+bSaclPresent], esi
0x18006487b  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x18006487f  mov     [rbp+bSaclDefaulted], esi
0x180064882  mov     rcx, rdi; pSecurityDescriptor
0x180064885  call    cs:__imp_GetSecurityDescriptorSacl
0x18006488b  test    eax, eax
0x18006488d  jz      short loc_1800648CF
0x18006488f  mov     rcx, [rbp+pSacl]; pAcl
0x180064893  test    rcx, rcx
0x180064896  jz      short loc_1800648CF
0x180064898  xor     ebx, ebx
0x18006489a  xor     eax, eax
0x18006489c  cmp     ax, [rcx+4]
0x1800648a0  jnb     short loc_1800648CF
0x1800648a2  movzx   edx, bx; dwAceIndex
0x1800648a5  lea     r8, [rbp+pAce]; pAce
0x1800648a9  mov     [rbp+pAce], 0
0x1800648b1  call    cs:__imp_GetAce
0x1800648b7  test    eax, eax
0x1800648b9  jz      short loc_1800648C2
0x1800648bb  mov     rcx, [rbp+pAce]
0x1800648bf  or      esi, [rcx+4]
0x1800648c2  mov     rcx, [rbp+pSacl]
0x1800648c6  inc     bx
0x1800648c9  cmp     bx, [rcx+4]
0x1800648cd  jb      short loc_1800648A2
0x1800648cf  mov     rcx, rdi; hMem
0x1800648d2  call    cs:__imp_LocalFree
0x1800648d8  mov     rbx, [rsp+40h+arg_0]
0x1800648dd  mov     eax, esi
0x1800648df  add     rsp, 40h
0x1800648e3  pop     rdi
0x1800648e4  pop     rsi
0x1800648e5  pop     rbp
0x1800648e6  retn
```
