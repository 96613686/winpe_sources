# CUserList<RemotePowerShellSession>::FindSid(SidHandle)

- ea: `0x180075e94`
- end: `0x180075ffc`
- name: `?FindSid@?$CUserList@VRemotePowerShellSession@@@@QEAAPEAV?$vector@PEAVRemotePowerShellSession@@V?$allocator@PEAVRemotePowerShellSession@@@std@@@std@@VSidHandle@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002d330`
- `0x18007f434`
- `0x1800c1810`
- `0x1800c19e4`
- `0x1800c1bbc`

## callees

- `0x180016d60`
- `0x18002e5c0`
- `0x180075e94`
- `0x1800a3444`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180075f28`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180075f38`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180075f4b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180075f5b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180075f28`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180075f38`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180075f4b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180075f5b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180075edd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180075ee9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180075ef8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180075f04`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180075f16`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180075edd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180075ee9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180075ef8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180075f04`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180075f16`

## pseudocode

```c
__int64 __fastcall CUserList<RemotePowerShellSession>::FindSid(__int64 a1, PSID *a2)
{
  __int64 *v2; // rbp
  __int64 **v4; // r13
  __int64 *i; // rdi
  PSID v6; // r14
  PSID v7; // r15
  PUCHAR SidSubAuthorityCount; // rbx
  PUCHAR v9; // rax
  PUCHAR v10; // rbx
  PUCHAR v11; // rax
  UCHAR j; // r12
  PDWORD SidSubAuthority; // rbx
  PDWORD v14; // rax
  PDWORD v15; // rbx
  PDWORD v16; // rax
  __int64 v17; // rbx

  v2 = *(__int64 **)a1;
  v4 = (__int64 **)a1;
  for ( i = *(__int64 **)(*(_QWORD *)a1 + 8LL); !*((_BYTE *)i + 25); i = (__int64 *)*i )
  {
    v6 = (PSID)i[4];
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
          for ( j = 0; j < *GetSidSubAuthorityCount(v6); ++j )
          {
            SidSubAuthority = GetSidSubAuthority(v7, j);
            v14 = GetSidSubAuthority(v6, j);
            a1 = *SidSubAuthority;
            if ( *v14 < (unsigned int)a1 )
              goto LABEL_12;
            v15 = GetSidSubAuthority(v7, j);
            v16 = GetSidSubAuthority(v6, j);
            a1 = *v15;
            if ( *v16 > (unsigned int)a1 )
              break;
          }
        }
LABEL_13:
        v2 = i;
        continue;
      }
    }
    else if ( (__int64)v6 >= (__int64)v7 )
    {
      goto LABEL_13;
    }
LABEL_12:
    i += 2;
  }
  if ( *((_BYTE *)v2 + 25) || CSidSorter::operator()(a1, a2, (void **)v2 + 4) || v2 == *v4 )
  {
    SidHandle::~SidHandle((SidHandle *)a2);
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
0x180075e94  push    rbx
0x180075e96  push    rbp
0x180075e97  push    rsi
0x180075e98  push    rdi
0x180075e99  push    r12
0x180075e9b  push    r13
0x180075e9d  push    r14
0x180075e9f  push    r15
0x180075ea1  sub     rsp, 48h
0x180075ea5  mov     rbp, [rcx]
0x180075ea8  xor     eax, eax
0x180075eaa  mov     rsi, rdx
0x180075ead  mov     [rsp+88h+var_5C], eax
0x180075eb1  mov     r13, rcx
0x180075eb4  mov     rdi, [rbp+8]
0x180075eb8  cmp     [rdi+19h], al
0x180075ebb  jnz     loc_180075F87
0x180075ec1  mov     r14, [rdi+20h]
0x180075ec5  mov     r15, [rsi]
0x180075ec8  test    r14, r14
0x180075ecb  jz      loc_180075F6C
0x180075ed1  test    r15, r15
0x180075ed4  jz      loc_180075F6C
0x180075eda  mov     rcx, r15; pSid
0x180075edd  call    cs:__imp_GetSidSubAuthorityCount
0x180075ee3  mov     rcx, r14; pSid
0x180075ee6  mov     rbx, rax
0x180075ee9  call    cs:__imp_GetSidSubAuthorityCount
0x180075eef  mov     cl, [rbx]
0x180075ef1  cmp     [rax], cl
0x180075ef3  jb      short loc_180075F71
0x180075ef5  mov     rcx, r15; pSid
0x180075ef8  call    cs:__imp_GetSidSubAuthorityCount
0x180075efe  mov     rcx, r14; pSid
0x180075f01  mov     rbx, rax
0x180075f04  call    cs:__imp_GetSidSubAuthorityCount
0x180075f0a  mov     cl, [rbx]
0x180075f0c  cmp     [rax], cl
0x180075f0e  ja      short loc_180075F77
0x180075f10  xor     r12b, r12b
0x180075f13  mov     rcx, r14; pSid
0x180075f16  call    cs:__imp_GetSidSubAuthorityCount
0x180075f1c  cmp     r12b, [rax]
0x180075f1f  jnb     short loc_180075F77
0x180075f21  movzx   edx, r12b; nSubAuthority
0x180075f25  mov     rcx, r15; pSid
0x180075f28  call    cs:__imp_GetSidSubAuthority
0x180075f2e  movzx   edx, r12b; nSubAuthority
0x180075f32  mov     rcx, r14; pSid
0x180075f35  mov     rbx, rax
0x180075f38  call    cs:__imp_GetSidSubAuthority
0x180075f3e  mov     ecx, [rbx]
0x180075f40  cmp     [rax], ecx
0x180075f42  jb      short loc_180075F71
0x180075f44  movzx   edx, r12b; nSubAuthority
0x180075f48  mov     rcx, r15; pSid
0x180075f4b  call    cs:__imp_GetSidSubAuthority
0x180075f51  movzx   edx, r12b; nSubAuthority
0x180075f55  mov     rcx, r14; pSid
0x180075f58  mov     rbx, rax
0x180075f5b  call    cs:__imp_GetSidSubAuthority
0x180075f61  mov     ecx, [rbx]
0x180075f63  cmp     [rax], ecx
0x180075f65  ja      short loc_180075F77
0x180075f67  inc     r12b
0x180075f6a  jmp     short loc_180075F13
0x180075f6c  cmp     r14, r15
0x180075f6f  jge     short loc_180075F77
0x180075f71  add     rdi, 10h
0x180075f75  jmp     short loc_180075F7A
0x180075f77  mov     rbp, rdi
0x180075f7a  mov     rdi, [rdi]
0x180075f7d  cmp     byte ptr [rdi+19h], 0
0x180075f81  jz      loc_180075EC1
0x180075f87  cmp     byte ptr [rbp+19h], 0
0x180075f8b  jnz     short loc_180075FE1
0x180075f8d  lea     r8, [rbp+20h]
0x180075f91  mov     rdx, rsi
0x180075f94  call    ??RCSidSorter@@QEBA_NAEBVSidHandle@@0@Z; CSidSorter::operator()(SidHandle const &,SidHandle const &)
0x180075f99  test    al, al
0x180075f9b  jnz     short loc_180075FE1
0x180075f9d  cmp     rbp, [r13+0]
0x180075fa1  jz      short loc_180075FE1
0x180075fa3  mov     rbx, [rbp+30h]
0x180075fa7  or      ecx, 0FFFFFFFFh
0x180075faa  mov     rdx, [rsi+8]
0x180075fae  lock xadd [rdx], ecx
0x180075fb2  cmp     ecx, 1
0x180075fb5  jnz     short loc_180075FDC
0x180075fb7  lea     edx, [rcx+3]; unsigned __int64
0x180075fba  mov     rcx, [rsi+8]; void *
0x180075fbe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180075fc3  mov     rcx, [rsi]; void *
0x180075fc6  xor     edx, edx; unsigned __int64
0x180075fc8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180075fcd  mov     qword ptr [rsi+8], 0
0x180075fd5  mov     qword ptr [rsi], 0
0x180075fdc  mov     rax, rbx
0x180075fdf  jmp     short loc_180075FEB
0x180075fe1  mov     rcx, rsi; this
0x180075fe4  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x180075fe9  xor     eax, eax
0x180075feb  add     rsp, 48h
0x180075fef  pop     r15
0x180075ff1  pop     r14
0x180075ff3  pop     r13
0x180075ff5  pop     r12
0x180075ff7  pop     rdi
0x180075ff8  pop     rsi
0x180075ff9  pop     rbp
0x180075ffa  pop     rbx
0x180075ffb  retn
```
