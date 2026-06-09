# CUserList<UserManagerUserSession>::FindSid(SidHandle)

- ea: `0x18002fa84`
- end: `0x18002fc24`
- name: `?FindSid@?$CUserList@VUserManagerUserSession@@@@QEAAPEAV?$vector@PEAVUserManagerUserSession@@V?$allocator@PEAVUserManagerUserSession@@@std@@@std@@VSidHandle@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18007f434`
- `0x1800c1810`
- `0x1800c19e4`
- `0x1800c1bbc`

## callees

- `0x18002e5c0`
- `0x18002fa84`
- `0x1800a3444`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fb1f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fb2e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fb40`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fb4f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fb1f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fb2e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fb40`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fb4f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fad1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fadd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002faec`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002faf8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fb0a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fad1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fadd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002faec`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002faf8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fb0a`

## pseudocode

```c
__int64 __fastcall CUserList<UserManagerUserSession>::FindSid(__int64 a1, PSID *a2)
{
  __int64 *v2; // rbp
  __int64 **v4; // rbx
  __int64 *v5; // rsi
  PSID v6; // r14
  PSID v7; // r15
  PUCHAR SidSubAuthorityCount; // rbx
  PUCHAR v9; // rax
  PUCHAR v10; // rbx
  PUCHAR v11; // rax
  UCHAR i; // r12
  PDWORD SidSubAuthority; // rbx
  PDWORD v14; // rax
  PDWORD v15; // rbx
  PDWORD v16; // rax
  __int64 v17; // rbx
  __int64 **v19; // [rsp+90h] [rbp+8h]

  v19 = (__int64 **)a1;
  v2 = *(__int64 **)a1;
  v4 = (__int64 **)a1;
  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  if ( !*((_BYTE *)v5 + 25) )
  {
    while ( 1 )
    {
      v6 = (PSID)v5[4];
      v7 = *a2;
      if ( v6 && v7 )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(*a2);
        v9 = GetSidSubAuthorityCount(v6);
        LOBYTE(a1) = *SidSubAuthorityCount;
        if ( *v9 >= *SidSubAuthorityCount )
        {
          v10 = GetSidSubAuthorityCount(v7);
          v11 = GetSidSubAuthorityCount(v6);
          LOBYTE(a1) = *v10;
          if ( *v11 <= *v10 )
          {
            for ( i = 0; i < *GetSidSubAuthorityCount(v6); ++i )
            {
              SidSubAuthority = GetSidSubAuthority(v7, i);
              v14 = GetSidSubAuthority(v6, i);
              a1 = *SidSubAuthority;
              if ( *v14 < (unsigned int)a1 )
                goto LABEL_12;
              v15 = GetSidSubAuthority(v7, i);
              v16 = GetSidSubAuthority(v6, i);
              a1 = *v15;
              if ( *v16 > (unsigned int)a1 )
                break;
            }
          }
LABEL_13:
          v2 = v5;
          goto LABEL_14;
        }
      }
      else if ( (__int64)v6 >= (__int64)v7 )
      {
        goto LABEL_13;
      }
LABEL_12:
      v5 += 2;
LABEL_14:
      v5 = (__int64 *)*v5;
      if ( *((_BYTE *)v5 + 25) )
      {
        v4 = v19;
        break;
      }
    }
  }
  if ( *((_BYTE *)v2 + 25) || CSidSorter::operator()(a1, a2, (void **)v2 + 4) || v2 == *v4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2[1], 0xFFFFFFFF) == 1 )
    {
      operator delete(a2[1], 4u);
      operator delete(*a2, 0);
      a2[1] = 0;
      *a2 = 0;
    }
    return 0;
  }
  else
  {
    v17 = v2[6];
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2[1], 0xFFFFFFFF) == 1 )
    {
      operator delete(a2[1], 4u);
      operator delete(*a2, 0);
      a2[1] = 0;
      *a2 = 0;
    }
    return v17;
  }
}

```

## disassembly

```asm
0x18002fa84  mov     [rsp+arg_0], rcx
0x18002fa89  push    rbx
0x18002fa8a  push    rbp
0x18002fa8b  push    rsi
0x18002fa8c  push    rdi
0x18002fa8d  push    r12
0x18002fa8f  push    r13
0x18002fa91  push    r14
0x18002fa93  push    r15
0x18002fa95  sub     rsp, 48h
0x18002fa99  mov     rbp, [rcx]
0x18002fa9c  xor     eax, eax
0x18002fa9e  mov     rdi, rdx
0x18002faa1  mov     [rsp+88h+var_5C], eax
0x18002faa5  mov     rbx, rcx
0x18002faa8  mov     rsi, [rbp+8]
0x18002faac  cmp     [rsi+19h], al
0x18002faaf  jnz     loc_18002FB83
0x18002fab5  mov     r14, [rsi+20h]
0x18002fab9  mov     r15, [rdi]
0x18002fabc  test    r14, r14
0x18002fabf  jz      loc_18002FB60
0x18002fac5  test    r15, r15
0x18002fac8  jz      loc_18002FB60
0x18002face  mov     rcx, r15; pSid
0x18002fad1  call    cs:__imp_GetSidSubAuthorityCount
0x18002fad7  mov     rcx, r14; pSid
0x18002fada  mov     rbx, rax
0x18002fadd  call    cs:__imp_GetSidSubAuthorityCount
0x18002fae3  mov     cl, [rbx]
0x18002fae5  cmp     [rax], cl
0x18002fae7  jb      short loc_18002FB65
0x18002fae9  mov     rcx, r15; pSid
0x18002faec  call    cs:__imp_GetSidSubAuthorityCount
0x18002faf2  mov     rcx, r14; pSid
0x18002faf5  mov     rbx, rax
0x18002faf8  call    cs:__imp_GetSidSubAuthorityCount
0x18002fafe  mov     cl, [rbx]
0x18002fb00  cmp     [rax], cl
0x18002fb02  ja      short loc_18002FB6B
0x18002fb04  xor     r12b, r12b
0x18002fb07  mov     rcx, r14; pSid
0x18002fb0a  call    cs:__imp_GetSidSubAuthorityCount
0x18002fb10  cmp     r12b, [rax]
0x18002fb13  jnb     short loc_18002FB6B
0x18002fb15  movzx   r13d, r12b
0x18002fb19  mov     rcx, r15; pSid
0x18002fb1c  mov     edx, r13d; nSubAuthority
0x18002fb1f  call    cs:__imp_GetSidSubAuthority
0x18002fb25  mov     edx, r13d; nSubAuthority
0x18002fb28  mov     rcx, r14; pSid
0x18002fb2b  mov     rbx, rax
0x18002fb2e  call    cs:__imp_GetSidSubAuthority
0x18002fb34  mov     ecx, [rbx]
0x18002fb36  cmp     [rax], ecx
0x18002fb38  jb      short loc_18002FB65
0x18002fb3a  mov     edx, r13d; nSubAuthority
0x18002fb3d  mov     rcx, r15; pSid
0x18002fb40  call    cs:__imp_GetSidSubAuthority
0x18002fb46  mov     edx, r13d; nSubAuthority
0x18002fb49  mov     rcx, r14; pSid
0x18002fb4c  mov     rbx, rax
0x18002fb4f  call    cs:__imp_GetSidSubAuthority
0x18002fb55  mov     ecx, [rbx]
0x18002fb57  cmp     [rax], ecx
0x18002fb59  ja      short loc_18002FB6B
0x18002fb5b  inc     r12b
0x18002fb5e  jmp     short loc_18002FB07
0x18002fb60  cmp     r14, r15
0x18002fb63  jge     short loc_18002FB6B
0x18002fb65  add     rsi, 10h
0x18002fb69  jmp     short loc_18002FB6E
0x18002fb6b  mov     rbp, rsi
0x18002fb6e  mov     rsi, [rsi]
0x18002fb71  cmp     byte ptr [rsi+19h], 0
0x18002fb75  jz      loc_18002FAB5
0x18002fb7b  mov     rbx, [rsp+88h+arg_0]
0x18002fb83  cmp     byte ptr [rbp+19h], 0
0x18002fb87  jnz     short loc_18002FBDC
0x18002fb89  lea     r8, [rbp+20h]
0x18002fb8d  mov     rdx, rdi
0x18002fb90  call    ??RCSidSorter@@QEBA_NAEBVSidHandle@@0@Z; CSidSorter::operator()(SidHandle const &,SidHandle const &)
0x18002fb95  test    al, al
0x18002fb97  jnz     short loc_18002FBDC
0x18002fb99  cmp     rbp, [rbx]
0x18002fb9c  jz      short loc_18002FBDC
0x18002fb9e  mov     rbx, [rbp+30h]
0x18002fba2  or      ecx, 0FFFFFFFFh
0x18002fba5  mov     rax, [rdi+8]
0x18002fba9  lock xadd [rax], ecx
0x18002fbad  cmp     ecx, 1
0x18002fbb0  jnz     short loc_18002FBD7
0x18002fbb2  lea     edx, [rcx+3]; unsigned __int64
0x18002fbb5  mov     rcx, [rdi+8]; void *
0x18002fbb9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fbbe  mov     rcx, [rdi]; void *
0x18002fbc1  xor     edx, edx; unsigned __int64
0x18002fbc3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fbc8  mov     qword ptr [rdi+8], 0
0x18002fbd0  mov     qword ptr [rdi], 0
0x18002fbd7  mov     rax, rbx
0x18002fbda  jmp     short loc_18002FC13
0x18002fbdc  mov     rcx, [rdi+8]
0x18002fbe0  or      eax, 0FFFFFFFFh
0x18002fbe3  lock xadd [rcx], eax
0x18002fbe7  cmp     eax, 1
0x18002fbea  jnz     short loc_18002FC11
0x18002fbec  mov     rcx, [rdi+8]; void *
0x18002fbf0  lea     edx, [rax+3]; unsigned __int64
0x18002fbf3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fbf8  mov     rcx, [rdi]; void *
0x18002fbfb  xor     edx, edx; unsigned __int64
0x18002fbfd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fc02  mov     qword ptr [rdi+8], 0
0x18002fc0a  mov     qword ptr [rdi], 0
0x18002fc11  xor     eax, eax
0x18002fc13  add     rsp, 48h
0x18002fc17  pop     r15
0x18002fc19  pop     r14
0x18002fc1b  pop     r13
0x18002fc1d  pop     r12
0x18002fc1f  pop     rdi
0x18002fc20  pop     rsi
0x18002fc21  pop     rbp
0x18002fc22  pop     rbx
0x18002fc23  retn
```
