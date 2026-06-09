# std::_Tree<std::_Tmap_traits<SidHandle,std::vector<ServiceAccountUserSession *,std::allocator<ServiceAccountUserSession *>> *,CSidSorter,std::allocator<std::pair<SidHandle const,std::vector<ServiceAccountUserSession *,std::allocator<ServiceAccountUserSession *>> *>>,1>>::_Find<SidHandle>(SidHandle const &)

- ea: `0x18002fc2c`
- end: `0x18002fd80`
- name: `??$_Find@VSidHandle@@@?$_Tree@V?$_Tmap_traits@VSidHandle@@PEAV?$vector@PEAVServiceAccountUserSession@@V?$allocator@PEAVServiceAccountUserSession@@@std@@@std@@VCSidSorter@@V?$allocator@U?$pair@$$CBVSidHandle@@PEAV?$vector@PEAVServiceAccountUserSession@@V?$allocator@PEAVServiceAccountUserSession@@@std@@@std@@@std@@@3@$00@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBVSidHandle@@PEAV?$vector@PEAVServiceAccountUserSession@@V?$allocator@PEAVServiceAccountUserSession@@@std@@@std@@@std@@PEAX@1@AEBVSidHandle@@@Z`
- size: `340`
- prototype: `__int64 *__fastcall(__int64, PSID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800945a8`

## callees

- `0x18002e5c0`
- `0x18002fc2c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fcd8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fce7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fcf9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fd08`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fcd8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fce7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fcf9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002fd08`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fc83`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fc8f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fca5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fcb1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fcc3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fc83`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fc8f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fca5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fcb1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002fcc3`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tmap_traits<SidHandle,std::vector<ServiceAccountUserSession *> *,CSidSorter,std::allocator<std::pair<SidHandle const,std::vector<ServiceAccountUserSession *> *>>,1>>::_Find<SidHandle>(
        __int64 a1,
        PSID *a2)
{
  __int64 *v2; // rbp
  __int64 v3; // r12
  __int64 *v4; // rdi
  PSID *v5; // r12
  PSID v6; // rsi
  PSID v7; // r14
  PUCHAR SidSubAuthorityCount; // rbx
  PUCHAR v9; // rbx
  UCHAR i; // r15
  PDWORD SidSubAuthority; // rbx
  PDWORD v12; // rax
  PDWORD v13; // rbx
  PDWORD v14; // rax
  __int64 *v15; // rax
  bool v16; // zf
  __int64 *result; // rax
  __int64 v18; // [rsp+80h] [rbp+8h]
  PSID *v19; // [rsp+88h] [rbp+10h]

  v19 = a2;
  v18 = a1;
  v2 = *(__int64 **)a1;
  v3 = a1;
  v4 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  if ( !*((_BYTE *)v4 + 25) )
  {
    v5 = a2;
    while ( 1 )
    {
      v6 = (PSID)v4[4];
      v7 = *v5;
      if ( v6 && v7 )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(*v5);
        if ( *GetSidSubAuthorityCount(v6) >= *SidSubAuthorityCount )
        {
          v9 = GetSidSubAuthorityCount(v7);
          if ( *GetSidSubAuthorityCount(v6) <= *v9 )
          {
            for ( i = 0; i < *GetSidSubAuthorityCount(v6); ++i )
            {
              SidSubAuthority = GetSidSubAuthority(v7, i);
              v12 = GetSidSubAuthority(v6, i);
              a1 = *SidSubAuthority;
              if ( *v12 < (unsigned int)a1 )
                goto LABEL_6;
              v13 = GetSidSubAuthority(v7, i);
              v14 = GetSidSubAuthority(v6, i);
              a1 = *v13;
              if ( *v14 > (unsigned int)a1 )
                break;
            }
          }
LABEL_14:
          LOBYTE(a1) = 0;
          v2 = v4;
          goto LABEL_15;
        }
      }
      else if ( (__int64)v6 >= (__int64)v7 )
      {
        goto LABEL_14;
      }
LABEL_6:
      LOBYTE(a1) = 1;
LABEL_15:
      v15 = v4 + 2;
      if ( !(_BYTE)a1 )
        v15 = v4;
      v4 = (__int64 *)*v15;
      if ( *(_BYTE *)(*v15 + 25) )
      {
        v3 = v18;
        a2 = v19;
        break;
      }
    }
  }
  if ( *((_BYTE *)v2 + 25) )
    return *(__int64 **)v3;
  v16 = (unsigned __int8)CSidSorter::operator()(a1, a2, v2 + 4) == 0;
  result = v2;
  if ( !v16 )
    return *(__int64 **)v3;
  return result;
}

```

## disassembly

```asm
0x18002fc2c  mov     r11, rsp
0x18002fc2f  mov     [r11+18h], rbx
0x18002fc33  mov     [r11+10h], rdx
0x18002fc37  mov     [r11+8], rcx
0x18002fc3b  push    rbp
0x18002fc3c  push    rsi
0x18002fc3d  push    rdi
0x18002fc3e  push    r12
0x18002fc40  push    r13
0x18002fc42  push    r14
0x18002fc44  push    r15
0x18002fc46  sub     rsp, 40h
0x18002fc4a  mov     rbp, [rcx]
0x18002fc4d  xor     eax, eax
0x18002fc4f  mov     r12, rcx
0x18002fc52  mov     [rsp+78h+var_4C], eax
0x18002fc56  mov     rdi, [rbp+8]
0x18002fc5a  cmp     [rdi+19h], al
0x18002fc5d  jnz     loc_18002FD4E
0x18002fc63  mov     r12, rdx
0x18002fc66  mov     rsi, [rdi+20h]
0x18002fc6a  mov     r14, [r12]
0x18002fc6e  test    rsi, rsi
0x18002fc71  jz      loc_18002FD19
0x18002fc77  test    r14, r14
0x18002fc7a  jz      loc_18002FD19
0x18002fc80  mov     rcx, r14; pSid
0x18002fc83  call    cs:__imp_GetSidSubAuthorityCount
0x18002fc89  mov     rcx, rsi; pSid
0x18002fc8c  mov     rbx, rax
0x18002fc8f  call    cs:__imp_GetSidSubAuthorityCount
0x18002fc95  mov     cl, [rbx]
0x18002fc97  cmp     [rax], cl
0x18002fc99  jnb     short loc_18002FCA2
0x18002fc9b  mov     cl, 1
0x18002fc9d  jmp     loc_18002FD27
0x18002fca2  mov     rcx, r14; pSid
0x18002fca5  call    cs:__imp_GetSidSubAuthorityCount
0x18002fcab  mov     rcx, rsi; pSid
0x18002fcae  mov     rbx, rax
0x18002fcb1  call    cs:__imp_GetSidSubAuthorityCount
0x18002fcb7  mov     cl, [rbx]
0x18002fcb9  cmp     [rax], cl
0x18002fcbb  ja      short loc_18002FD22
0x18002fcbd  xor     r15b, r15b
0x18002fcc0  mov     rcx, rsi; pSid
0x18002fcc3  call    cs:__imp_GetSidSubAuthorityCount
0x18002fcc9  cmp     r15b, [rax]
0x18002fccc  jnb     short loc_18002FD22
0x18002fcce  movzx   r13d, r15b
0x18002fcd2  mov     rcx, r14; pSid
0x18002fcd5  mov     edx, r13d; nSubAuthority
0x18002fcd8  call    cs:__imp_GetSidSubAuthority
0x18002fcde  mov     edx, r13d; nSubAuthority
0x18002fce1  mov     rcx, rsi; pSid
0x18002fce4  mov     rbx, rax
0x18002fce7  call    cs:__imp_GetSidSubAuthority
0x18002fced  mov     ecx, [rbx]
0x18002fcef  cmp     [rax], ecx
0x18002fcf1  jb      short loc_18002FC9B
0x18002fcf3  mov     edx, r13d; nSubAuthority
0x18002fcf6  mov     rcx, r14; pSid
0x18002fcf9  call    cs:__imp_GetSidSubAuthority
0x18002fcff  mov     edx, r13d; nSubAuthority
0x18002fd02  mov     rcx, rsi; pSid
0x18002fd05  mov     rbx, rax
0x18002fd08  call    cs:__imp_GetSidSubAuthority
0x18002fd0e  mov     ecx, [rbx]
0x18002fd10  cmp     [rax], ecx
0x18002fd12  ja      short loc_18002FD22
0x18002fd14  inc     r15b
0x18002fd17  jmp     short loc_18002FCC0
0x18002fd19  cmp     rsi, r14
0x18002fd1c  jl      loc_18002FC9B
0x18002fd22  xor     cl, cl
0x18002fd24  mov     rbp, rdi
0x18002fd27  test    cl, cl
0x18002fd29  lea     rax, [rdi+10h]
0x18002fd2d  cmovz   rax, rdi
0x18002fd31  mov     rdi, [rax]
0x18002fd34  cmp     byte ptr [rdi+19h], 0
0x18002fd38  jz      loc_18002FC66
0x18002fd3e  mov     r12, [rsp+78h+arg_0]
0x18002fd46  mov     rdx, [rsp+78h+arg_8]
0x18002fd4e  cmp     byte ptr [rbp+19h], 0
0x18002fd52  jnz     short loc_18002FD64
0x18002fd54  lea     r8, [rbp+20h]
0x18002fd58  call    ??RCSidSorter@@QEBA_NAEBVSidHandle@@0@Z; CSidSorter::operator()(SidHandle const &,SidHandle const &)
0x18002fd5d  test    al, al
0x18002fd5f  mov     rax, rbp
0x18002fd62  jz      short loc_18002FD68
0x18002fd64  mov     rax, [r12]
0x18002fd68  mov     rbx, [rsp+78h+arg_10]
0x18002fd70  add     rsp, 40h
0x18002fd74  pop     r15
0x18002fd76  pop     r14
0x18002fd78  pop     r13
0x18002fd7a  pop     r12
0x18002fd7c  pop     rdi
0x18002fd7d  pop     rsi
0x18002fd7e  pop     rbp
0x18002fd7f  retn
```
