# _ConvertDaclToNT4Format

- ea: `0x1800227e4`
- end: `0x180022a3a`
- name: `_ConvertDaclToNT4Format`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180021d10`

## callees

- `0x1800049ac`
- `0x1800136f0`
- `0x18001722c`
- `0x1800227e4`
- `0x180022a40`

## import_xrefs

- `msvcrt!free` at `0x18002288d`
- `msvcrt!free` at `0x18002296e`
- `msvcrt!free` at `0x1800229c8`
- `msvcrt!free` at `0x180022a1d`
- `msvcrt!free` at `0x18002288d`
- `msvcrt!free` at `0x18002296e`
- `msvcrt!free` at `0x1800229c8`
- `msvcrt!free` at `0x180022a1d`
- `ADVAPI32!GetAce` at `0x1800228bc`
- `ADVAPI32!GetAce` at `0x180022909`
- `ADVAPI32!GetAce` at `0x1800228bc`
- `ADVAPI32!GetAce` at `0x180022909`
- `ADVAPI32!InitializeAcl` at `0x180022831`
- `ADVAPI32!InitializeAcl` at `0x180022831`
- `KERNEL32!GetLastError` at `0x18002283b`
- `KERNEL32!GetLastError` at `0x180022998`
- `KERNEL32!GetLastError` at `0x1800229ed`
- `KERNEL32!GetLastError` at `0x18002283b`
- `KERNEL32!GetLastError` at `0x180022998`
- `KERNEL32!GetLastError` at `0x1800229ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConvertDaclToNT4Format(unsigned int a1, struct _ACL *a2, DWORD *a3, struct _ACL **a4)
{
  DWORD AclSize; // eax
  DWORD AceCount; // esi
  struct _ACL *v9; // rbx
  DWORD v10; // edi
  DWORD v12; // edi
  DWORD v13; // r12d
  DWORD v14; // r14d
  int v15; // ebp
  int v16; // eax
  DWORD v17; // eax
  DWORD LastError; // eax
  LPVOID pAce; // [rsp+88h] [rbp+10h] BYREF
  struct _ACL *v21; // [rsp+90h] [rbp+18h]
  PACL *v22; // [rsp+98h] [rbp+20h]

  v22 = a4;
  AclSize = a2->AclSize;
  AceCount = a2->AceCount;
  *a3 = AclSize;
  v9 = (struct _ACL *)MmAllocate(AclSize);
  v21 = v9;
  *a4 = v9;
  if ( InitializeAcl(v9, *a3, 2u) )
  {
    v12 = 0;
    while ( 1 )
    {
      pAce = 0;
      if ( !GetAce(a2, v12, &pAce) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            21,
            &WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids,
            v12,
            LastError);
        }
        goto LABEL_35;
      }
      if ( (*((_BYTE *)pAce + 1) & 8) == 0 )
        break;
      ++v12;
LABEL_26:
      if ( v12 >= AceCount )
      {
        free(0);
        return 0;
      }
    }
    v13 = v12;
    v14 = v12;
    v15 = !*(_BYTE *)pAce || *(_BYTE *)pAce == 5;
    while ( 1 )
    {
      if ( ++v12 >= AceCount )
      {
LABEL_25:
        ConvertGroupOfNt5DaclAces(a1, a2, v13, v14, v15, *v22);
        goto LABEL_26;
      }
      if ( !GetAce(a2, v12, &pAce) )
        break;
      if ( (*((_BYTE *)pAce + 1) & 8) != 0 )
        goto LABEL_25;
      v16 = !*(_BYTE *)pAce || *(_BYTE *)pAce == 5;
      if ( v15 != v16 )
        goto LABEL_25;
      v14 = v12;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v17 = GetLastError();
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 32), 22, &WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, v12, v17);
    }
LABEL_35:
    free(v9);
    return 3222146058LL;
  }
  else
  {
    v10 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 20, &WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, v10);
    if ( (int)v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    free(v9);
    return v10;
  }
}

```

## disassembly

```asm
0x1800227e4  mov     [rsp+arg_18], r9
0x1800227e9  mov     [rsp+arg_0], ecx
0x1800227ed  push    rbx
0x1800227ee  push    rbp
0x1800227ef  push    rsi
0x1800227f0  push    rdi
0x1800227f1  push    r12
0x1800227f3  push    r13
0x1800227f5  push    r14
0x1800227f7  push    r15
0x1800227f9  sub     rsp, 38h
0x1800227fd  mov     r14, r9
0x180022800  mov     rdi, r8
0x180022803  mov     r13, rdx
0x180022806  movzx   eax, word ptr [rdx+2]
0x18002280a  movzx   esi, word ptr [rdx+4]
0x18002280e  mov     [r8], eax
0x180022811  mov     ecx, eax; unsigned __int64
0x180022813  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180022818  mov     rbx, rax
0x18002281b  mov     [rsp+78h+arg_10], rax
0x180022823  mov     [r14], rax
0x180022826  mov     r8d, 2; dwAclRevision
0x18002282c  mov     edx, [rdi]; nAclLength
0x18002282e  mov     rcx, rax; pAcl
0x180022831  call    cs:__imp_InitializeAcl
0x180022837  test    eax, eax
0x180022839  jnz     short loc_18002289B
0x18002283b  call    cs:__imp_GetLastError
0x180022841  mov     edi, eax
0x180022843  lea     rax, WPP_GLOBAL_Control
0x18002284a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022851  cmp     rcx, rax
0x180022854  jz      short loc_18002287D
0x180022856  mov     esi, 1
0x18002285b  test    [rcx+10Ch], sil
0x180022862  jz      short loc_18002287D
0x180022864  lea     edx, [rsi+13h]
0x180022867  mov     r9d, edi
0x18002286a  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180022871  mov     rcx, [rcx+100h]
0x180022878  call    WPP_SF_d
0x18002287d  test    edi, edi
0x18002287f  jle     short loc_18002288A
0x180022881  movzx   edi, di
0x180022884  or      edi, 80070000h
0x18002288a  mov     rcx, rbx; Block
0x18002288d  call    cs:__imp_free
0x180022893  nop
0x180022894  mov     eax, edi
0x180022896  jmp     loc_180022A29
0x18002289b  mov     r15d, esi
0x18002289e  xor     edi, edi
0x1800228a0  lea     esi, [rdi+1]
0x1800228a3  mov     [rsp+78h+pAce], 0
0x1800228af  lea     r8, [rsp+78h+pAce]; pAce
0x1800228b7  mov     edx, edi; dwAceIndex
0x1800228b9  mov     rcx, r13; pAcl
0x1800228bc  call    cs:__imp_GetAce
0x1800228c2  test    eax, eax
0x1800228c4  jz      loc_1800229D1
0x1800228ca  mov     rax, [rsp+78h+pAce]
0x1800228d2  test    byte ptr [rax+1], 8
0x1800228d6  jz      short loc_1800228DF
0x1800228d8  add     edi, esi
0x1800228da  jmp     loc_180022963
0x1800228df  mov     r12d, edi
0x1800228e2  mov     r14d, edi
0x1800228e5  cmp     byte ptr [rax], 0
0x1800228e8  jz      short loc_1800228F3
0x1800228ea  cmp     byte ptr [rax], 5
0x1800228ed  jz      short loc_1800228F3
0x1800228ef  xor     ebp, ebp
0x1800228f1  jmp     short loc_1800228F5
0x1800228f3  mov     ebp, esi
0x1800228f5  add     edi, esi
0x1800228f7  cmp     edi, r15d
0x1800228fa  jnb     short loc_18002293A
0x1800228fc  lea     r8, [rsp+78h+pAce]; pAce
0x180022904  mov     edx, edi; dwAceIndex
0x180022906  mov     rcx, r13; pAcl
0x180022909  call    cs:__imp_GetAce
0x18002290f  test    eax, eax
0x180022911  jz      short loc_18002297C
0x180022913  mov     rax, [rsp+78h+pAce]
0x18002291b  test    byte ptr [rax+1], 8
0x18002291f  jnz     short loc_18002293A
0x180022921  mov     al, [rax]
0x180022923  test    al, al
0x180022925  jz      short loc_18002292F
0x180022927  cmp     al, 5
0x180022929  jz      short loc_18002292F
0x18002292b  xor     eax, eax
0x18002292d  jmp     short loc_180022931
0x18002292f  mov     eax, esi
0x180022931  cmp     ebp, eax
0x180022933  jnz     short loc_18002293A
0x180022935  mov     r14d, edi
0x180022938  jmp     short loc_1800228F5
0x18002293a  mov     rax, [rsp+78h+arg_18]
0x180022942  mov     rax, [rax]
0x180022945  mov     [rsp+78h+var_50], rax
0x18002294a  mov     [rsp+78h+var_58], ebp
0x18002294e  mov     r9d, r14d
0x180022951  mov     r8d, r12d
0x180022954  mov     rdx, r13
0x180022957  mov     ecx, [rsp+78h+arg_0]
0x18002295e  call    _ConvertGroupOfNt5DaclAces
0x180022963  cmp     edi, r15d
0x180022966  jb      loc_1800228A3
0x18002296c  xor     ecx, ecx; Block
0x18002296e  call    cs:__imp_free
0x180022974  nop
0x180022975  xor     eax, eax
0x180022977  jmp     loc_180022A29
0x18002297c  lea     rax, WPP_GLOBAL_Control
0x180022983  mov     rcx, cs:WPP_GLOBAL_Control
0x18002298a  cmp     rcx, rax
0x18002298d  jz      short loc_1800229C5
0x18002298f  test    [rcx+10Ch], sil
0x180022996  jz      short loc_1800229C5
0x180022998  call    cs:__imp_GetLastError
0x18002299e  mov     edx, 16h
0x1800229a3  mov     [rsp+78h+var_58], eax
0x1800229a7  mov     r9d, edi
0x1800229aa  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x1800229b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229b8  mov     rcx, [rcx+100h]
0x1800229bf  call    WPP_SF_dd
0x1800229c4  nop
0x1800229c5  mov     rcx, rbx; Block
0x1800229c8  call    cs:__imp_free
0x1800229ce  nop
0x1800229cf  jmp     short loc_180022A24
0x1800229d1  lea     rax, WPP_GLOBAL_Control
0x1800229d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229df  cmp     rcx, rax
0x1800229e2  jz      short loc_180022A1A
0x1800229e4  test    [rcx+10Ch], sil
0x1800229eb  jz      short loc_180022A1A
0x1800229ed  call    cs:__imp_GetLastError
0x1800229f3  mov     edx, 15h
0x1800229f8  mov     [rsp+78h+var_58], eax
0x1800229fc  mov     r9d, edi
0x1800229ff  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180022a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a0d  mov     rcx, [rcx+100h]
0x180022a14  call    WPP_SF_dd
0x180022a19  nop
0x180022a1a  mov     rcx, rbx; Block
0x180022a1d  call    cs:__imp_free
0x180022a23  nop
0x180022a24  mov     eax, 0C00E0C0Ah
0x180022a29  add     rsp, 38h
0x180022a2d  pop     r15
0x180022a2f  pop     r14
0x180022a31  pop     r13
0x180022a33  pop     r12
0x180022a35  pop     rdi
0x180022a36  pop     rsi
0x180022a37  pop     rbp
0x180022a38  pop     rbx
0x180022a39  retn
```
