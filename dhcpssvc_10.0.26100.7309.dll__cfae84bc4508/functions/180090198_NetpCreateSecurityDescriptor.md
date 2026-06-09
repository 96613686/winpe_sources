# NetpCreateSecurityDescriptor

- ea: `0x180090198`
- end: `0x1800904ef`
- name: `NetpCreateSecurityDescriptor`
- size: `855`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800904f8`

## callees

- `0x180090198`

## import_xrefs

- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18009048b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18009048b`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180090468`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180090468`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180090444`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180090444`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180090420`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180090420`
- `ntdll!RtlAddAce` at `0x1800903e8`
- `ntdll!RtlAddAce` at `0x1800903e8`
- `ntdll!RtlCreateAcl` at `0x18009028f`
- `ntdll!RtlCreateAcl` at `0x1800902bb`
- `ntdll!RtlCreateAcl` at `0x18009028f`
- `ntdll!RtlCreateAcl` at `0x1800902bb`
- `ntdll!RtlLengthSid` at `0x1800901ed`
- `ntdll!RtlLengthSid` at `0x180090342`
- `ntdll!RtlLengthSid` at `0x1800903a9`
- `ntdll!RtlLengthSid` at `0x1800901ed`
- `ntdll!RtlLengthSid` at `0x180090342`
- `ntdll!RtlLengthSid` at `0x1800903a9`
- `ntdll!RtlCopySid` at `0x1800903be`
- `ntdll!RtlCopySid` at `0x1800903be`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800904ae`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800904ae`
- `KERNEL32!LocalAlloc` at `0x180090259`
- `KERNEL32!LocalAlloc` at `0x180090306`
- `KERNEL32!LocalAlloc` at `0x180090259`
- `KERNEL32!LocalAlloc` at `0x180090306`
- `KERNEL32!LocalFree` at `0x1800902d0`
- `KERNEL32!LocalFree` at `0x1800902e8`
- `KERNEL32!LocalFree` at `0x1800902d0`
- `KERNEL32!LocalFree` at `0x1800902e8`

## pseudocode

```c
__int64 __fastcall NetpCreateSecurityDescriptor(__int64 a1, unsigned int a2, void *a3, void *a4, struct _ACL **a5)
{
  ULONG v5; // r14d
  char *v6; // rsi
  unsigned int v7; // r15d
  NTSTATUS Acl; // ebx
  ULONG v10; // edi
  ULONG v11; // r12d
  __int64 v12; // rbp
  ULONG v13; // eax
  ULONG v14; // ecx
  int v15; // eax
  unsigned int v16; // ecx
  struct _ACL *v17; // rax
  struct _ACL *v18; // rbp
  struct _ACL *v19; // r15
  struct _ACL *v20; // rdi
  unsigned int v21; // r12d
  PSID **v22; // r14
  struct _ACL *v23; // r13
  ULONG v24; // eax
  ULONG AceListLength; // r15d
  PSID v26; // rdi
  ULONG v27; // eax
  struct _ACL *Dacl; // [rsp+30h] [rbp-58h]
  struct _ACL *Sacl; // [rsp+38h] [rbp-50h]

  Dacl = 0;
  v5 = 0;
  Sacl = 0;
  v6 = 0;
  v7 = 0;
  Acl = -1073741811;
  v10 = 8;
  v11 = 8;
  if ( a2 )
  {
    v12 = a1;
    do
    {
      v13 = RtlLengthSid(**(PSID **)(v12 + 8));
      if ( !*(_BYTE *)v12 || *(_BYTE *)v12 == 1 )
      {
        v14 = v13 + 8;
        v10 += v13 + 8;
      }
      else
      {
        if ( *(_BYTE *)v12 != 2 )
          return (unsigned int)Acl;
        v14 = v13 + 8;
        v11 += v13 + 8;
      }
      if ( v5 > v14 )
        v14 = v5;
      ++v7;
      v12 += 16;
      v5 = v14;
    }
    while ( v7 < a2 );
  }
  v15 = v10 + 40;
  if ( v10 == 8 )
    v15 = 40;
  v16 = v15 + v11;
  if ( v11 == 8 )
    v16 = v15;
  if ( !v16 )
    return (unsigned int)-1073741801;
  v17 = (struct _ACL *)LocalAlloc(0, v16);
  if ( (v18 = v17) == 0 )
    return (unsigned int)-1073741801;
  v19 = v17 + 5;
  if ( v10 == 8
    || (Dacl = v17 + 5, v19 = (struct _ACL *)((char *)v19 + v10), Acl = RtlCreateAcl(v17 + 5, v10, 2u), Acl >= 0) )
  {
    if ( v11 == 8 )
    {
      v20 = 0;
    }
    else
    {
      Sacl = v19;
      v20 = v19;
      Acl = RtlCreateAcl(v19, v11, 2u);
      if ( Acl < 0 )
        goto LABEL_21;
    }
    if ( !v5 || (v6 = (char *)LocalAlloc(0, v5)) == 0 )
    {
      Acl = -1073741801;
      goto LABEL_21;
    }
    v21 = 0;
    if ( a2 )
    {
      v22 = (PSID **)(a1 + 8);
      while ( 1 )
      {
        v23 = 0;
        v24 = RtlLengthSid(**v22);
        AceListLength = v24;
        if ( !*((_BYTE *)v22 - 8) )
          break;
        if ( *((_BYTE *)v22 - 8) == 1 )
        {
          v26 = **v22;
          *v6 = 1;
LABEL_35:
          v23 = Dacl;
          goto LABEL_36;
        }
        if ( *((_BYTE *)v22 - 8) == 2 )
        {
          v23 = v20;
          v26 = **v22;
          *v6 = 2;
LABEL_36:
          AceListLength = v24 + 8;
          v6[1] = *((_BYTE *)v22 - 6) | *((_BYTE *)v22 - 7);
          *((_DWORD *)v6 + 1) = *((_DWORD *)v22 - 1);
          *((_WORD *)v6 + 1) = v24 + 8;
          v27 = RtlLengthSid(v26);
          Acl = RtlCopySid(v27, v6 + 8, v26);
        }
        if ( Acl < 0 )
          goto LABEL_21;
        Acl = RtlAddAce(v23, 2u, 0xFFFFFFFF, v6, AceListLength);
        if ( Acl < 0 )
          goto LABEL_21;
        v20 = Sacl;
        ++v21;
        v22 += 2;
        if ( v21 >= a2 )
          goto LABEL_40;
      }
      v26 = **v22;
      *v6 = 0;
      goto LABEL_35;
    }
LABEL_40:
    Acl = RtlCreateSecurityDescriptor(v18, 1u);
    if ( Acl >= 0 )
    {
      Acl = RtlSetOwnerSecurityDescriptor(v18, a3, 0);
      if ( Acl >= 0 )
      {
        Acl = RtlSetGroupSecurityDescriptor(v18, a4, 0);
        if ( Acl >= 0 )
        {
          Acl = RtlSetDaclSecurityDescriptor(v18, 1u, Dacl, 0);
          if ( Acl >= 0 )
          {
            Acl = RtlSetSaclSecurityDescriptor(v18, 0, Sacl, 0);
            if ( Acl >= 0 )
            {
              Acl = 0;
              *a5 = v18;
              goto LABEL_22;
            }
          }
        }
      }
    }
  }
LABEL_21:
  LocalFree(v18);
  if ( v6 )
LABEL_22:
    LocalFree(v6);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x180090198  mov     rax, rsp
0x18009019b  mov     [rax+20h], r9
0x18009019f  mov     [rax+18h], r8
0x1800901a3  mov     [rax+10h], edx
0x1800901a6  mov     [rax+8], rcx
0x1800901aa  push    rbx
0x1800901ab  push    rbp
0x1800901ac  push    rsi
0x1800901ad  push    rdi
0x1800901ae  push    r12
0x1800901b0  push    r13
0x1800901b2  push    r14
0x1800901b4  push    r15
0x1800901b6  sub     rsp, 48h
0x1800901ba  and     [rsp+88h+Dacl], 0
0x1800901c0  xor     r8d, r8d
0x1800901c3  xor     r14d, r14d
0x1800901c6  mov     [rsp+88h+Sacl], r8
0x1800901cb  xor     esi, esi
0x1800901cd  xor     r15d, r15d
0x1800901d0  mov     r13d, edx
0x1800901d3  mov     ebx, 0C000000Dh
0x1800901d8  lea     edi, [r8+8]
0x1800901dc  mov     r12d, edi
0x1800901df  test    edx, edx
0x1800901e1  jz      short loc_180090234
0x1800901e3  mov     rbp, rcx
0x1800901e6  mov     rcx, [rbp+8]
0x1800901ea  mov     rcx, [rcx]; Sid
0x1800901ed  call    cs:__imp_RtlLengthSid
0x1800901f4  nop     dword ptr [rax+rax+00h]
0x1800901f9  movzx   edx, byte ptr [rbp+0]
0x1800901fd  mov     ecx, eax
0x1800901ff  test    edx, edx
0x180090201  jz      short loc_180090219
0x180090203  sub     edx, 1
0x180090206  jz      short loc_180090219
0x180090208  cmp     edx, 1
0x18009020b  jnz     loc_1800904DB
0x180090211  add     ecx, 8
0x180090214  add     r12d, ecx
0x180090217  jmp     short loc_18009021E
0x180090219  add     ecx, 8
0x18009021c  add     edi, ecx
0x18009021e  cmp     r14d, ecx
0x180090221  cmova   ecx, r14d
0x180090225  inc     r15d
0x180090228  add     rbp, 10h
0x18009022c  mov     r14d, ecx
0x18009022f  cmp     r15d, r13d
0x180090232  jb      short loc_1800901E6
0x180090234  cmp     edi, 8
0x180090237  lea     eax, [rdi+28h]
0x18009023a  mov     ecx, 28h ; '('
0x18009023f  cmovz   eax, ecx
0x180090242  cmp     r12d, 8
0x180090246  lea     ecx, [rax+r12]
0x18009024a  cmovz   ecx, eax
0x18009024d  test    ecx, ecx
0x18009024f  jz      loc_1800904D6
0x180090255  mov     edx, ecx; uBytes
0x180090257  xor     ecx, ecx; uFlags
0x180090259  call    cs:__imp_LocalAlloc
0x180090260  nop     dword ptr [rax+rax+00h]
0x180090265  mov     rbp, rax
0x180090268  test    rax, rax
0x18009026b  jz      loc_1800904D6
0x180090271  lea     r15, [rax+28h]
0x180090275  cmp     edi, 8
0x180090278  jz      short loc_1800902A1
0x18009027a  mov     rcx, r15; Acl
0x18009027d  mov     eax, edi
0x18009027f  mov     r8d, 2; AclRevision
0x180090285  mov     [rsp+88h+Dacl], rcx
0x18009028a  mov     edx, edi; AclSize
0x18009028c  add     r15, rax
0x18009028f  call    cs:__imp_RtlCreateAcl
0x180090296  nop     dword ptr [rax+rax+00h]
0x18009029b  mov     ebx, eax
0x18009029d  test    eax, eax
0x18009029f  js      short loc_1800902CD
0x1800902a1  cmp     r12d, 8
0x1800902a5  jz      short loc_1800902F9
0x1800902a7  mov     r8d, 2; AclRevision
0x1800902ad  mov     [rsp+88h+Sacl], r15
0x1800902b2  mov     edx, r12d; AclSize
0x1800902b5  mov     rcx, r15; Acl
0x1800902b8  mov     rdi, r15
0x1800902bb  call    cs:__imp_RtlCreateAcl
0x1800902c2  nop     dword ptr [rax+rax+00h]
0x1800902c7  mov     ebx, eax
0x1800902c9  test    eax, eax
0x1800902cb  jns     short loc_1800902FC
0x1800902cd  mov     rcx, rbp; hMem
0x1800902d0  call    cs:__imp_LocalFree
0x1800902d7  nop     dword ptr [rax+rax+00h]
0x1800902dc  test    rsi, rsi
0x1800902df  jz      loc_1800904DB
0x1800902e5  mov     rcx, rsi; hMem
0x1800902e8  call    cs:__imp_LocalFree
0x1800902ef  nop     dword ptr [rax+rax+00h]
0x1800902f4  jmp     loc_1800904DB
0x1800902f9  mov     rdi, rsi
0x1800902fc  test    r14d, r14d
0x1800902ff  jz      short loc_18009031A
0x180090301  mov     edx, r14d; uBytes
0x180090304  xor     ecx, ecx; uFlags
0x180090306  call    cs:__imp_LocalAlloc
0x18009030d  nop     dword ptr [rax+rax+00h]
0x180090312  mov     rsi, rax
0x180090315  test    rax, rax
0x180090318  jnz     short loc_180090321
0x18009031a  mov     ebx, 0C0000017h
0x18009031f  jmp     short loc_1800902CD
0x180090321  xor     r12d, r12d
0x180090324  test    r13d, r13d
0x180090327  jz      loc_180090418
0x18009032d  mov     r14, [rsp+88h+arg_0]
0x180090335  add     r14, 8
0x180090339  mov     rcx, [r14]
0x18009033c  xor     r13d, r13d
0x18009033f  mov     rcx, [rcx]; Sid
0x180090342  call    cs:__imp_RtlLengthSid
0x180090349  nop     dword ptr [rax+rax+00h]
0x18009034e  movzx   edx, byte ptr [r14-8]
0x180090353  mov     r15d, eax
0x180090356  test    edx, edx
0x180090358  jz      short loc_18009037D
0x18009035a  sub     edx, 1
0x18009035d  jz      short loc_180090372
0x18009035f  cmp     edx, 1
0x180090362  jnz     short loc_1800903CC
0x180090364  mov     rax, [r14]
0x180090367  mov     r13, rdi
0x18009036a  mov     rdi, [rax]
0x18009036d  mov     byte ptr [rsi], 2
0x180090370  jmp     short loc_18009038B
0x180090372  mov     rax, [r14]
0x180090375  mov     rdi, [rax]
0x180090378  mov     byte ptr [rsi], 1
0x18009037b  jmp     short loc_180090386
0x18009037d  mov     rax, [r14]
0x180090380  mov     rdi, [rax]
0x180090383  mov     byte ptr [rsi], 0
0x180090386  mov     r13, [rsp+88h+Dacl]
0x18009038b  mov     al, [r14-7]
0x18009038f  add     r15d, 8
0x180090393  or      al, [r14-6]
0x180090397  mov     rcx, rdi; Sid
0x18009039a  mov     [rsi+1], al
0x18009039d  mov     eax, [r14-4]
0x1800903a1  mov     [rsi+4], eax
0x1800903a4  mov     [rsi+2], r15w
0x1800903a9  call    cs:__imp_RtlLengthSid
0x1800903b0  nop     dword ptr [rax+rax+00h]
0x1800903b5  mov     r8, rdi; SourceSid
0x1800903b8  lea     rdx, [rsi+8]; DestinationSid
0x1800903bc  mov     ecx, eax; DestinationSidLength
0x1800903be  call    cs:__imp_RtlCopySid
0x1800903c5  nop     dword ptr [rax+rax+00h]
0x1800903ca  mov     ebx, eax
0x1800903cc  test    ebx, ebx
0x1800903ce  js      loc_1800902CD
0x1800903d4  mov     r9, rsi; AceList
0x1800903d7  mov     [rsp+88h+AceListLength], r15d; AceListLength
0x1800903dc  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x1800903e0  mov     edx, 2; AceRevision
0x1800903e5  mov     rcx, r13; Acl
0x1800903e8  call    cs:__imp_RtlAddAce
0x1800903ef  nop     dword ptr [rax+rax+00h]
0x1800903f4  mov     ebx, eax
0x1800903f6  test    eax, eax
0x1800903f8  js      loc_1800902CD
0x1800903fe  mov     rdi, [rsp+88h+Sacl]
0x180090403  inc     r12d
0x180090406  add     r14, 10h
0x18009040a  cmp     r12d, [rsp+88h+arg_8]
0x180090412  jb      loc_180090339
0x180090418  mov     edx, 1; Revision
0x18009041d  mov     rcx, rbp; SecurityDescriptor
0x180090420  call    cs:__imp_RtlCreateSecurityDescriptor
0x180090427  nop     dword ptr [rax+rax+00h]
0x18009042c  mov     ebx, eax
0x18009042e  test    eax, eax
0x180090430  js      loc_1800902CD
0x180090436  mov     rdx, [rsp+88h+Owner]; Owner
0x18009043e  xor     r8d, r8d; OwnerDefaulted
0x180090441  mov     rcx, rbp; SecurityDescriptor
0x180090444  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18009044b  nop     dword ptr [rax+rax+00h]
0x180090450  mov     ebx, eax
0x180090452  test    eax, eax
0x180090454  js      loc_1800902CD
0x18009045a  mov     rdx, [rsp+88h+Group]; Group
0x180090462  xor     r8d, r8d; GroupDefaulted
0x180090465  mov     rcx, rbp; SecurityDescriptor
0x180090468  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18009046f  nop     dword ptr [rax+rax+00h]
0x180090474  mov     ebx, eax
0x180090476  test    eax, eax
0x180090478  js      loc_1800902CD
0x18009047e  mov     r8, [rsp+88h+Dacl]; Dacl
0x180090483  xor     r9d, r9d; DaclDefaulted
0x180090486  mov     dl, 1; DaclPresent
0x180090488  mov     rcx, rbp; SecurityDescriptor
0x18009048b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180090492  nop     dword ptr [rax+rax+00h]
0x180090497  mov     ebx, eax
0x180090499  test    eax, eax
0x18009049b  js      loc_1800902CD
0x1800904a1  mov     r8, [rsp+88h+Sacl]; Sacl
0x1800904a6  xor     r9d, r9d; SaclDefaulted
0x1800904a9  xor     edx, edx; SaclPresent
0x1800904ab  mov     rcx, rbp; SecurityDescriptor
0x1800904ae  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x1800904b5  nop     dword ptr [rax+rax+00h]
0x1800904ba  mov     ebx, eax
0x1800904bc  test    eax, eax
0x1800904be  js      loc_1800902CD
0x1800904c4  xor     ebx, ebx
0x1800904c6  mov     rax, [rsp+88h+arg_20]
0x1800904ce  mov     [rax], rbp
0x1800904d1  jmp     loc_1800902E5
0x1800904d6  mov     ebx, 0C0000017h
0x1800904db  mov     eax, ebx
0x1800904dd  add     rsp, 48h
0x1800904e1  pop     r15
0x1800904e3  pop     r14
0x1800904e5  pop     r13
0x1800904e7  pop     r12
0x1800904e9  pop     rdi
0x1800904ea  pop     rsi
0x1800904eb  pop     rbp
0x1800904ec  pop     rbx
0x1800904ed  retn
```
