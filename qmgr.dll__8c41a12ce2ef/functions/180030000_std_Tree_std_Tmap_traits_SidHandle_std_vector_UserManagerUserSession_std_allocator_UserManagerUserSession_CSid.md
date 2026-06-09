# std::_Tree<std::_Tmap_traits<SidHandle,std::vector<UserManagerUserSession *,std::allocator<UserManagerUserSession *>> *,CSidSorter,std::allocator<std::pair<SidHandle const,std::vector<UserManagerUserSession *,std::allocator<UserManagerUserSession *>> *>>,1>>::find(SidHandle const &)

- ea: `0x180030000`
- end: `0x18003016c`
- name: `?find@?$_Tree@V?$_Tmap_traits@VSidHandle@@PEAV?$vector@PEAVUserManagerUserSession@@V?$allocator@PEAVUserManagerUserSession@@@std@@@std@@VCSidSorter@@V?$allocator@U?$pair@$$CBVSidHandle@@PEAV?$vector@PEAVUserManagerUserSession@@V?$allocator@PEAVUserManagerUserSession@@@std@@@std@@@std@@@3@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSidHandle@@PEAV?$vector@PEAVUserManagerUserSession@@V?$allocator@PEAVUserManagerUserSession@@@std@@@std@@@std@@@std@@@std@@@2@AEBVSidHandle@@@Z`
- size: `364`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c34a0`
- `0x1800c3574`

## callees

- `0x18002e5c0`
- `0x180030000`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800300b6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800300c5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800300d7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800300e6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800300b6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800300c5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800300d7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800300e6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180030061`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003006d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180030083`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003008f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800300a1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180030061`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003006d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180030083`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003008f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800300a1`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<SidHandle,std::vector<UserManagerUserSession *> *,CSidSorter,std::allocator<std::pair<SidHandle const,std::vector<UserManagerUserSession *> *>>,1>>::find(
        __int64 *a1,
        _QWORD *a2,
        PSID *a3)
{
  __int64 *v3; // rdi
  __int64 *v4; // rbx
  __int64 v5; // rcx
  void **v6; // rax
  _QWORD *v7; // r12
  __int64 *v8; // rbp
  PSID v10; // rsi
  PSID v11; // r14
  PUCHAR SidSubAuthorityCount; // rbx
  PUCHAR v13; // rbx
  UCHAR i; // r15
  PDWORD SidSubAuthority; // rbx
  PDWORD v16; // rax
  PDWORD v17; // rbx
  PDWORD v18; // rax
  __int64 *v19; // rax
  _QWORD *result; // rax

  v3 = (__int64 *)*a1;
  v4 = a1;
  v5 = 0;
  v6 = a3;
  v7 = a2;
  v8 = (__int64 *)v3[1];
  if ( !*((_BYTE *)v8 + 25) )
  {
    while ( 1 )
    {
      v10 = (PSID)v8[4];
      v11 = *a3;
      if ( v10 && v11 )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(*a3);
        if ( *GetSidSubAuthorityCount(v10) >= *SidSubAuthorityCount )
        {
          v13 = GetSidSubAuthorityCount(v11);
          if ( *GetSidSubAuthorityCount(v10) <= *v13 )
          {
            for ( i = 0; i < *GetSidSubAuthorityCount(v10); ++i )
            {
              SidSubAuthority = GetSidSubAuthority(v11, i);
              v16 = GetSidSubAuthority(v10, i);
              v5 = *SidSubAuthority;
              if ( *v16 < (unsigned int)v5 )
                goto LABEL_5;
              v17 = GetSidSubAuthority(v11, i);
              v18 = GetSidSubAuthority(v10, i);
              v5 = *v17;
              if ( *v18 > (unsigned int)v5 )
                break;
            }
          }
LABEL_13:
          LOBYTE(v5) = 0;
          v3 = v8;
          goto LABEL_14;
        }
      }
      else if ( (__int64)v10 >= (__int64)v11 )
      {
        goto LABEL_13;
      }
LABEL_5:
      LOBYTE(v5) = 1;
LABEL_14:
      v19 = v8 + 2;
      if ( !(_BYTE)v5 )
        v19 = v8;
      v8 = (__int64 *)*v19;
      if ( *(_BYTE *)(*v19 + 25) )
      {
        v7 = a2;
        v4 = a1;
        v6 = a3;
        break;
      }
    }
  }
  if ( *((_BYTE *)v3 + 25) || CSidSorter::operator()(v5, v6, (void **)v3 + 4) )
    v3 = (__int64 *)*v4;
  result = v7;
  *v7 = v3;
  return result;
}

```

## disassembly

```asm
0x180030000  mov     r11, rsp
0x180030003  mov     [r11+20h], rbx
0x180030007  mov     [r11+18h], r8
0x18003000b  mov     [r11+10h], rdx
0x18003000f  mov     [r11+8], rcx
0x180030013  push    rbp
0x180030014  push    rsi
0x180030015  push    rdi
0x180030016  push    r12
0x180030018  push    r13
0x18003001a  push    r14
0x18003001c  push    r15
0x18003001e  sub     rsp, 40h
0x180030022  mov     rdi, [rcx]
0x180030025  mov     rbx, rcx
0x180030028  xor     ecx, ecx
0x18003002a  mov     rax, r8
0x18003002d  mov     r12, rdx
0x180030030  mov     [rsp+78h+var_4C], ecx
0x180030034  mov     rbp, [rdi+8]
0x180030038  cmp     [rbp+19h], cl
0x18003003b  jnz     loc_180030134
0x180030041  mov     r12, r8
0x180030044  mov     rsi, [rbp+20h]
0x180030048  mov     r14, [r12]
0x18003004c  test    rsi, rsi
0x18003004f  jz      loc_1800300F7
0x180030055  test    r14, r14
0x180030058  jz      loc_1800300F7
0x18003005e  mov     rcx, r14; pSid
0x180030061  call    cs:__imp_GetSidSubAuthorityCount
0x180030067  mov     rcx, rsi; pSid
0x18003006a  mov     rbx, rax
0x18003006d  call    cs:__imp_GetSidSubAuthorityCount
0x180030073  mov     cl, [rbx]
0x180030075  cmp     [rax], cl
0x180030077  jnb     short loc_180030080
0x180030079  mov     cl, 1
0x18003007b  jmp     loc_180030105
0x180030080  mov     rcx, r14; pSid
0x180030083  call    cs:__imp_GetSidSubAuthorityCount
0x180030089  mov     rcx, rsi; pSid
0x18003008c  mov     rbx, rax
0x18003008f  call    cs:__imp_GetSidSubAuthorityCount
0x180030095  mov     cl, [rbx]
0x180030097  cmp     [rax], cl
0x180030099  ja      short loc_180030100
0x18003009b  xor     r15b, r15b
0x18003009e  mov     rcx, rsi; pSid
0x1800300a1  call    cs:__imp_GetSidSubAuthorityCount
0x1800300a7  cmp     r15b, [rax]
0x1800300aa  jnb     short loc_180030100
0x1800300ac  movzx   r13d, r15b
0x1800300b0  mov     rcx, r14; pSid
0x1800300b3  mov     edx, r13d; nSubAuthority
0x1800300b6  call    cs:__imp_GetSidSubAuthority
0x1800300bc  mov     edx, r13d; nSubAuthority
0x1800300bf  mov     rcx, rsi; pSid
0x1800300c2  mov     rbx, rax
0x1800300c5  call    cs:__imp_GetSidSubAuthority
0x1800300cb  mov     ecx, [rbx]
0x1800300cd  cmp     [rax], ecx
0x1800300cf  jb      short loc_180030079
0x1800300d1  mov     edx, r13d; nSubAuthority
0x1800300d4  mov     rcx, r14; pSid
0x1800300d7  call    cs:__imp_GetSidSubAuthority
0x1800300dd  mov     edx, r13d; nSubAuthority
0x1800300e0  mov     rcx, rsi; pSid
0x1800300e3  mov     rbx, rax
0x1800300e6  call    cs:__imp_GetSidSubAuthority
0x1800300ec  mov     ecx, [rbx]
0x1800300ee  cmp     [rax], ecx
0x1800300f0  ja      short loc_180030100
0x1800300f2  inc     r15b
0x1800300f5  jmp     short loc_18003009E
0x1800300f7  cmp     rsi, r14
0x1800300fa  jl      loc_180030079
0x180030100  xor     cl, cl
0x180030102  mov     rdi, rbp
0x180030105  test    cl, cl
0x180030107  lea     rax, [rbp+10h]
0x18003010b  cmovz   rax, rbp
0x18003010f  mov     rbp, [rax]
0x180030112  cmp     byte ptr [rbp+19h], 0
0x180030116  jz      loc_180030044
0x18003011c  mov     r12, [rsp+78h+arg_8]
0x180030124  mov     rbx, [rsp+78h+arg_0]
0x18003012c  mov     rax, [rsp+78h+arg_10]
0x180030134  cmp     byte ptr [rdi+19h], 0
0x180030138  jnz     short loc_18003014A
0x18003013a  lea     r8, [rdi+20h]
0x18003013e  mov     rdx, rax
0x180030141  call    ??RCSidSorter@@QEBA_NAEBVSidHandle@@0@Z; CSidSorter::operator()(SidHandle const &,SidHandle const &)
0x180030146  test    al, al
0x180030148  jz      short loc_18003014D
0x18003014a  mov     rdi, [rbx]
0x18003014d  mov     rbx, [rsp+78h+arg_18]
0x180030155  mov     rax, r12
0x180030158  mov     [r12], rdi
0x18003015c  add     rsp, 40h
0x180030160  pop     r15
0x180030162  pop     r14
0x180030164  pop     r13
0x180030166  pop     r12
0x180030168  pop     rdi
0x180030169  pop     rsi
0x18003016a  pop     rbp
0x18003016b  retn
```
