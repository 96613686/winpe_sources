# MsoFMNOResolveSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)

- ea: `0x180123210`
- end: `0x1801234b9`
- name: `?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z`
- size: `681`
- prototype: `int(unsigned int, struct _SECURITY_ATTRIBUTES **, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037cf4`
- `0x180121d78`
- `0x180121ee8`
- `0x180122030`

## callees

- `0x1800264b4`
- `0x1801225b8`
- `0x180122660`
- `0x180122748`
- `0x180122838`
- `0x180122f4c`
- `0x180123210`
- `0x180123508`
- `0x180123538`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1801233d2`
- `KERNEL32!LocalFree` at `0x1801233e0`
- `KERNEL32!LocalFree` at `0x1801233ee`
- `KERNEL32!LocalFree` at `0x1801233d2`
- `KERNEL32!LocalFree` at `0x1801233e0`
- `KERNEL32!LocalFree` at `0x1801233ee`
- `KERNEL32!LocalAlloc` at `0x180123339`
- `KERNEL32!LocalAlloc` at `0x18012337a`
- `KERNEL32!LocalAlloc` at `0x180123465`
- `KERNEL32!LocalAlloc` at `0x180123339`
- `KERNEL32!LocalAlloc` at `0x18012337a`
- `KERNEL32!LocalAlloc` at `0x180123465`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180123390`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180123390`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1801233a7`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1801233a7`

## pseudocode

```c
__int64 __fastcall MsoFMNOResolveSecurity(int a1, struct _SECURITY_ATTRIBUTES **a2, unsigned int a3)
{
  unsigned __int8 v5; // r12
  __int64 v7; // rbp
  struct _SECURITY_ATTRIBUTES * near **v8; // rsi
  struct _SECURITY_ATTRIBUTES *v9; // rax
  __int64 v10; // rbp
  __int64 v11; // rbp
  ACL *v12; // rbp
  void *v13; // r14
  int v14; // r15d
  struct _SECURITY_ATTRIBUTES *v15; // rax
  struct _SECURITY_ATTRIBUTES *v16; // rsi
  int v17; // eax
  HLOCAL v18; // rax
  unsigned int *v19; // rax
  int v20; // ebx
  struct _SECURITY_ATTRIBUTES *v21; // rax
  struct _SECURITY_ATTRIBUTES *v22; // rbx
  PACL pDacl; // [rsp+58h] [rbp+10h] BYREF

  v5 = 1;
  if ( !a2 )
    return 0;
  if ( (a1 & 0x2000) != 0 )
  {
    v7 = (int)a3;
    v8 = &vrgpsaEveryone;
    if ( (a1 & 0x40000) != 0 )
    {
      if ( !(&vrgpsaEveryoneAA)[a3] )
        sub_180122660(a3);
    }
    else if ( !(&vrgpsaEveryone)[a3] )
    {
      sub_180122748(a3);
    }
    if ( (a1 & 0x40000) != 0 )
      v8 = &vrgpsaEveryoneAA;
    v9 = (struct _SECURITY_ATTRIBUTES *)v8[v7];
  }
  else if ( (a1 & 0x4000) != 0 )
  {
    v9 = MsoPsaLogonIdDacl(a3);
  }
  else if ( (a1 & 0x8000) != 0 )
  {
    v9 = MsoPsaUserDacl(a3);
  }
  else if ( (a1 & 0x10000) != 0 )
  {
    v10 = (int)a3;
    if ( !(&vrgpsaInteractiveUser)[a3] )
      sub_180122838(a3);
    v9 = (struct _SECURITY_ATTRIBUTES *)(&vrgpsaInteractiveUser)[v10];
  }
  else
  {
    if ( (a1 & 0x20000) == 0 )
    {
      if ( (a1 & 0x100000) != 0 )
      {
        v12 = 0;
        pDacl = 0;
        v5 = 0;
        v13 = 0;
        v14 = dword_1801AF4A0[a3];
        v15 = (struct _SECURITY_ATTRIBUTES *)LocalAlloc(0x40u, 0x18u);
        *a2 = v15;
        v16 = v15;
        if ( v15 )
        {
          v17 = MsoFCreateImpersonatedAcl(&pDacl, v14 & 0xEEE0FFFF | 0x120000);
          v12 = pDacl;
          if ( v17 )
          {
            if ( pDacl )
            {
              v18 = LocalAlloc(0x40u, 0x28u);
              v13 = v18;
              if ( v18 )
              {
                if ( InitializeSecurityDescriptor(v18, 1u) && SetSecurityDescriptorDacl(v13, 1, v12, 0) )
                {
                  v16->nLength = 24;
                  v5 = 1;
                  v16->lpSecurityDescriptor = v13;
                  v16->bInheritHandle = 0;
                }
              }
            }
          }
        }
        if ( !v5 )
        {
          if ( v12 )
            LocalFree(v12);
          if ( v13 )
            LocalFree(v13);
          if ( v16 )
            LocalFree(v16);
          *a2 = 0;
        }
      }
      else if ( (a1 & 0x80000) == 0 )
      {
        MsoShipAssertTagProc(1422217);
      }
      goto LABEL_43;
    }
    v11 = (int)a3;
    if ( !(&vrgpsaAdministrators)[a3] )
      sub_1801225B8(a3);
    v9 = (struct _SECURITY_ATTRIBUTES *)(&vrgpsaAdministrators)[v11];
  }
  *a2 = v9;
LABEL_43:
  v19 = (unsigned int *)*a2;
  if ( *a2 && (a1 & 0x800000) != 0 )
  {
    v20 = a1 & 0x1FE000;
    if ( v20 == 0x2000 || v20 == 0x4000 || v20 == 0x8000 || v20 == 0x10000 || v20 == 0x20000 )
    {
      v21 = (struct _SECURITY_ATTRIBUTES *)LocalAlloc(0x40u, *v19);
      v22 = v21;
      if ( v21 )
      {
        v21->nLength = (*a2)->nLength;
        v21->lpSecurityDescriptor = (*a2)->lpSecurityDescriptor;
        v21->bInheritHandle = 1;
      }
      else
      {
        MsoShipAssertTagProc(1422219);
        v5 = 0;
      }
      *a2 = v22;
    }
    else if ( v20 == 0x100000 )
    {
      v19[4] = 1;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180123210  mov     [rsp+arg_0], rbx
0x180123215  mov     [rsp+arg_10], rbp
0x18012321a  push    rsi
0x18012321b  push    rdi
0x18012321c  push    r12
0x18012321e  push    r14
0x180123220  push    r15
0x180123222  sub     rsp, 20h
0x180123226  mov     rdi, rdx
0x180123229  mov     ebx, ecx
0x18012322b  mov     r12b, 1
0x18012322e  test    rdx, rdx
0x180123231  jnz     short loc_18012323A
0x180123233  xor     eax, eax
0x180123235  jmp     loc_1801234A2
0x18012323a  bt      ebx, 0Dh
0x18012323e  jnb     short loc_18012328A
0x180123240  mov     r14d, ebx
0x180123243  movsxd  rbp, r8d
0x180123246  lea     rsi, ?vrgpsaEveryone@@3PAPEAU_SECURITY_ATTRIBUTES@@A; _SECURITY_ATTRIBUTES * near * vrgpsaEveryone
0x18012324d  lea     r15, ?vrgpsaEveryoneAA@@3PAPEAU_SECURITY_ATTRIBUTES@@A; _SECURITY_ATTRIBUTES * near * vrgpsaEveryoneAA
0x180123254  and     r14d, 40000h
0x18012325b  jnz     short loc_18012326E
0x18012325d  cmp     qword ptr [rsi+rbp*8], 0
0x180123262  jnz     short loc_18012327D
0x180123264  mov     ecx, r8d
0x180123267  call    sub_180122748
0x18012326c  jmp     short loc_18012327D
0x18012326e  cmp     qword ptr [r15+rbp*8], 0
0x180123273  jnz     short loc_18012327D
0x180123275  mov     ecx, r8d
0x180123278  call    sub_180122660
0x18012327d  test    r14d, r14d
0x180123280  cmovnz  rsi, r15
0x180123284  mov     rax, [rsi+rbp*8]
0x180123288  jmp     short loc_180123302
0x18012328a  bt      ebx, 0Eh
0x18012328e  jnb     short loc_18012329A
0x180123290  mov     ecx, r8d; int
0x180123293  call    ?MsoPsaLogonIdDacl@@YAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoPsaLogonIdDacl(int)
0x180123298  jmp     short loc_180123302
0x18012329a  bt      ebx, 0Fh
0x18012329e  jnb     short loc_1801232AA
0x1801232a0  mov     ecx, r8d; int
0x1801232a3  call    ?MsoPsaUserDacl@@YAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoPsaUserDacl(int)
0x1801232a8  jmp     short loc_180123302
0x1801232aa  bt      ebx, 10h
0x1801232ae  jnb     short loc_1801232D7
0x1801232b0  movsxd  rbp, r8d
0x1801232b3  lea     rsi, __NULL_IMPORT_DESCRIPTOR
0x1801232ba  cmp     rva ?vrgpsaInteractiveUser@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rsi+rbp*8], 0; _SECURITY_ATTRIBUTES * near * vrgpsaInteractiveUser ...
0x1801232c3  jnz     short loc_1801232CD
0x1801232c5  mov     ecx, r8d
0x1801232c8  call    sub_180122838
0x1801232cd  mov     rax, rva ?vrgpsaInteractiveUser@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rsi+rbp*8]; _SECURITY_ATTRIBUTES * near * vrgpsaInteractiveUser ...
0x1801232d5  jmp     short loc_180123302
0x1801232d7  bt      ebx, 11h
0x1801232db  jnb     short loc_18012330A
0x1801232dd  movsxd  rbp, r8d
0x1801232e0  lea     rsi, __NULL_IMPORT_DESCRIPTOR
0x1801232e7  cmp     rva ?vrgpsaAdministrators@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rsi+rbp*8], 0; _SECURITY_ATTRIBUTES * near * vrgpsaAdministrators ...
0x1801232f0  jnz     short loc_1801232FA
0x1801232f2  mov     ecx, r8d
0x1801232f5  call    sub_1801225B8
0x1801232fa  mov     rax, rva ?vrgpsaAdministrators@@3PAPEAU_SECURITY_ATTRIBUTES@@A[rsi+rbp*8]; _SECURITY_ATTRIBUTES * near * vrgpsaAdministrators ...
0x180123302  mov     [rdi], rax
0x180123305  jmp     loc_18012340D
0x18012330a  bt      ebx, 14h
0x18012330e  jnb     loc_1801233FD
0x180123314  xor     ebp, ebp
0x180123316  movsxd  rax, r8d
0x180123319  lea     rsi, __NULL_IMPORT_DESCRIPTOR
0x180123320  mov     [rsp+48h+pDacl], rbp
0x180123325  xor     r12b, r12b
0x180123328  xor     r14d, r14d
0x18012332b  mov     r15d, ds:rva dword_1801AF4A0[rsi+rax*4]
0x180123333  lea     edx, [rbp+18h]; uBytes
0x180123336  lea     ecx, [rbp+40h]; uFlags
0x180123339  call    cs:__imp_LocalAlloc
0x18012333f  mov     [rdi], rax
0x180123342  mov     rsi, rax
0x180123345  test    rax, rax
0x180123348  jz      short loc_1801233C5
0x18012334a  and     r15d, 0EEF2FFFFh
0x180123351  lea     rcx, [rsp+48h+pDacl]; struct _ACL **
0x180123356  or      r15d, 120000h
0x18012335d  mov     edx, r15d; unsigned int
0x180123360  call    ?MsoFCreateImpersonatedAcl@@YAHPEAPEAU_ACL@@K@Z; MsoFCreateImpersonatedAcl(_ACL * *,ulong)
0x180123365  mov     rbp, [rsp+48h+pDacl]
0x18012336a  test    eax, eax
0x18012336c  jz      short loc_1801233C5
0x18012336e  test    rbp, rbp
0x180123371  jz      short loc_1801233C5
0x180123373  lea     edx, [r14+28h]; uBytes
0x180123377  lea     ecx, [rdx+18h]; uFlags
0x18012337a  call    cs:__imp_LocalAlloc
0x180123380  mov     r14, rax
0x180123383  test    rax, rax
0x180123386  jz      short loc_1801233C5
0x180123388  mov     edx, 1; dwRevision
0x18012338d  mov     rcx, rax; pSecurityDescriptor
0x180123390  call    cs:__imp_InitializeSecurityDescriptor
0x180123396  test    eax, eax
0x180123398  jz      short loc_1801233C5
0x18012339a  xor     r9d, r9d; bDaclDefaulted
0x18012339d  mov     r8, rbp; pDacl
0x1801233a0  mov     rcx, r14; pSecurityDescriptor
0x1801233a3  lea     edx, [r9+1]; bDaclPresent
0x1801233a7  call    cs:__imp_SetSecurityDescriptorDacl
0x1801233ad  test    eax, eax
0x1801233af  jz      short loc_1801233C5
0x1801233b1  mov     dword ptr [rsi], 18h
0x1801233b7  mov     r12b, 1
0x1801233ba  mov     [rsi+8], r14
0x1801233be  mov     dword ptr [rsi+10h], 0
0x1801233c5  test    r12b, r12b
0x1801233c8  jnz     short loc_18012340D
0x1801233ca  test    rbp, rbp
0x1801233cd  jz      short loc_1801233D8
0x1801233cf  mov     rcx, rbp; hMem
0x1801233d2  call    cs:__imp_LocalFree
0x1801233d8  test    r14, r14
0x1801233db  jz      short loc_1801233E6
0x1801233dd  mov     rcx, r14; hMem
0x1801233e0  call    cs:__imp_LocalFree
0x1801233e6  test    rsi, rsi
0x1801233e9  jz      short loc_1801233F4
0x1801233eb  mov     rcx, rsi; hMem
0x1801233ee  call    cs:__imp_LocalFree
0x1801233f4  mov     qword ptr [rdi], 0
0x1801233fb  jmp     short loc_18012340D
0x1801233fd  bt      ebx, 13h
0x180123401  jb      short loc_18012340D
0x180123403  mov     ecx, 15B389h
0x180123408  call    MsoShipAssertTagProc
0x18012340d  mov     rax, [rdi]
0x180123410  test    rax, rax
0x180123413  jz      loc_18012349E
0x180123419  bt      ebx, 17h
0x18012341d  jnb     short loc_18012349E
0x18012341f  and     ebx, 1FE000h
0x180123425  cmp     ebx, 2000h
0x18012342b  jz      short loc_18012345E
0x18012342d  cmp     ebx, 4000h
0x180123433  jz      short loc_18012345E
0x180123435  cmp     ebx, 8000h
0x18012343b  jz      short loc_18012345E
0x18012343d  cmp     ebx, 10000h
0x180123443  jz      short loc_18012345E
0x180123445  cmp     ebx, 20000h
0x18012344b  jz      short loc_18012345E
0x18012344d  cmp     ebx, 100000h
0x180123453  jnz     short loc_18012349E
0x180123455  mov     dword ptr [rax+10h], 1
0x18012345c  jmp     short loc_18012349E
0x18012345e  mov     edx, [rax]; uBytes
0x180123460  mov     ecx, 40h ; '@'; uFlags
0x180123465  call    cs:__imp_LocalAlloc
0x18012346b  mov     rbx, rax
0x18012346e  test    rax, rax
0x180123471  jz      short loc_18012348E
0x180123473  mov     rcx, [rdi]
0x180123476  mov     edx, [rcx]
0x180123478  mov     [rax], edx
0x18012347a  mov     rcx, [rdi]
0x18012347d  mov     rdx, [rcx+8]
0x180123481  mov     [rax+8], rdx
0x180123485  mov     dword ptr [rax+10h], 1
0x18012348c  jmp     short loc_18012349B
0x18012348e  mov     ecx, 15B38Bh
0x180123493  call    MsoShipAssertTagProc
0x180123498  xor     r12b, r12b
0x18012349b  mov     [rdi], rbx
0x18012349e  movzx   eax, r12b
0x1801234a2  mov     rbx, [rsp+48h+arg_0]
0x1801234a7  mov     rbp, [rsp+48h+arg_10]
0x1801234ac  add     rsp, 20h
0x1801234b0  pop     r15
0x1801234b2  pop     r14
0x1801234b4  pop     r12
0x1801234b6  pop     rdi
0x1801234b7  pop     rsi
0x1801234b8  retn
```
