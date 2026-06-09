# CSharedMemBlock::CreateSids(void * *,void * *,void * *,void * *,void * *)

- ea: `0x18001dd84`
- end: `0x18001dfcb`
- name: `?CreateSids@CSharedMemBlock@@AEAAJPEAPEAX0000@Z`
- size: `583`
- prototype: `int(CSharedMemBlock *__hidden this, void **, void **, void **, void **, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ecd0`

## callees

- `0x18001dd84`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001debe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001debe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df9d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001df0d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001df1f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001df42`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001df54`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001df0d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001df1f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001df42`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001df54`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001df93`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001df93`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001de0b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001de45`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001de7b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001deb4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001de0b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001de45`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001de7b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001deb4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dedd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dedd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dfa8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dfa8`

## pseudocode

```c
__int64 __fastcall CSharedMemBlock::CreateSids(
        CSharedMemBlock *this,
        void **pSid,
        void **a3,
        void **a4,
        void **a5,
        void **a6)
{
  PSID *v8; // rdi
  signed int v9; // ebx
  signed int LastError; // eax
  HLOCAL v11; // rax
  void *v12; // rsi
  signed int v13; // edi
  DWORD cbSid; // [rsp+60h] [rbp-20h] BYREF
  void **v16; // [rsp+68h] [rbp-18h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *pSid = 0;
  v8 = pSid;
  *a3 = 0;
  *a4 = 0;
  v16 = pSid;
  *a5 = 0;
  *a6 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, pSid)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x223u, 0, 0, 0, 0, 0, 0, a3)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x22Eu, 0, 0, 0, 0, 0, 0, a5)
    || (v9 = 0, !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x22Fu, 0, 0, 0, 0, 0, 0, a6)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  cbSid = 68;
  v11 = LocalAlloc(0, 0x44u);
  v12 = v11;
  if ( !v11 )
  {
    LOWORD(v13) = 8;
    goto LABEL_9;
  }
  if ( !CreateWellKnownSid(WinBuiltinIUsersSid, 0, v11, &cbSid) )
  {
    v13 = GetLastError();
    LocalFree(v12);
    if ( !v13 )
      goto LABEL_10;
    if ( v13 <= 0 )
    {
      v9 = v13;
      goto LABEL_10;
    }
LABEL_9:
    v9 = (unsigned __int16)v13 | 0x80070000;
LABEL_10:
    v8 = v16;
    goto LABEL_11;
  }
  *a4 = v12;
LABEL_11:
  if ( v9 < 0 )
  {
    if ( *v8 )
    {
      FreeSid(*v8);
      *v8 = 0;
    }
    if ( *a3 )
    {
      FreeSid(*a3);
      *a3 = 0;
    }
    if ( *a4 )
    {
      LocalFree(*a4);
      *a4 = 0;
    }
    if ( *a5 )
    {
      FreeSid(*a5);
      *a5 = 0;
    }
    if ( *a6 )
    {
      FreeSid(*a6);
      *a6 = 0;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001dd84  mov     [rsp-38h+arg_0], rbx
0x18001dd89  push    rbp
0x18001dd8a  push    rsi
0x18001dd8b  push    rdi
0x18001dd8c  push    r12
0x18001dd8e  push    r13
0x18001dd90  push    r14
0x18001dd92  push    r15
0x18001dd94  mov     rbp, rsp
0x18001dd97  sub     rsp, 80h
0x18001dd9e  mov     rax, cs:__security_cookie
0x18001dda5  xor     rax, rsp
0x18001dda8  mov     [rbp+var_8], rax
0x18001ddac  mov     r15, [rbp+arg_20]
0x18001ddb0  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18001ddb4  mov     r12, [rbp+arg_28]
0x18001ddb8  xor     esi, esi
0x18001ddba  mov     [rsp+80h+pSid], rdx; pSid
0x18001ddbf  mov     r14, r9
0x18001ddc2  mov     [rdx], rsi
0x18001ddc5  mov     r13, r8
0x18001ddc8  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x18001ddcc  mov     rdi, rdx
0x18001ddcf  mov     [r8], rsi
0x18001ddd2  lea     ebx, [rsi+20h]
0x18001ddd5  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x18001ddd9  mov     r8d, ebx; nSubAuthority0
0x18001dddc  mov     [r9], rsi
0x18001dddf  mov     r9d, 220h; nSubAuthority1
0x18001dde5  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x18001dde9  mov     [rbp+var_18], rdx
0x18001dded  mov     dl, 2; nSubAuthorityCount
0x18001ddef  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x18001ddf3  mov     [r15], rsi
0x18001ddf6  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x18001ddfa  mov     [r12], rsi
0x18001ddfe  mov     dword ptr [rbp+pIdentifierAuthority.Value], esi
0x18001de01  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18001de07  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x18001de0b  call    cs:__imp_AllocateAndInitializeSid
0x18001de11  test    eax, eax
0x18001de13  jz      loc_18001DEBE
0x18001de19  mov     [rsp+80h+pSid], r13; pSid
0x18001de1e  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18001de22  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x18001de26  mov     r9d, 223h; nSubAuthority1
0x18001de2c  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x18001de30  mov     r8d, ebx; nSubAuthority0
0x18001de33  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x18001de37  mov     dl, 2; nSubAuthorityCount
0x18001de39  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x18001de3d  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x18001de41  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x18001de45  call    cs:__imp_AllocateAndInitializeSid
0x18001de4b  test    eax, eax
0x18001de4d  jz      short loc_18001DEBE
0x18001de4f  mov     [rsp+80h+pSid], r15; pSid
0x18001de54  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18001de58  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x18001de5c  mov     r9d, 22Eh; nSubAuthority1
0x18001de62  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x18001de66  mov     r8d, ebx; nSubAuthority0
0x18001de69  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x18001de6d  mov     dl, 2; nSubAuthorityCount
0x18001de6f  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x18001de73  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x18001de77  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x18001de7b  call    cs:__imp_AllocateAndInitializeSid
0x18001de81  test    eax, eax
0x18001de83  jz      short loc_18001DEBE
0x18001de85  mov     [rsp+80h+pSid], r12; pSid
0x18001de8a  lea     r8d, [rsi+20h]; nSubAuthority0
0x18001de8e  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x18001de92  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18001de96  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x18001de9a  mov     r9d, 22Fh; nSubAuthority1
0x18001dea0  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x18001dea4  mov     dl, 2; nSubAuthorityCount
0x18001dea6  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x18001deaa  mov     ebx, esi
0x18001deac  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x18001deb0  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x18001deb4  call    cs:__imp_AllocateAndInitializeSid
0x18001deba  test    eax, eax
0x18001debc  jnz     short loc_18001DED3
0x18001debe  call    cs:__imp_GetLastError
0x18001dec4  mov     ebx, eax
0x18001dec6  test    eax, eax
0x18001dec8  jle     short loc_18001DED3
0x18001deca  movzx   ebx, ax
0x18001decd  or      ebx, 80070000h
0x18001ded3  mov     edx, 44h ; 'D'; uBytes
0x18001ded8  xor     ecx, ecx; uFlags
0x18001deda  mov     [rbp+cbSid], edx
0x18001dedd  call    cs:__imp_LocalAlloc
0x18001dee3  mov     rsi, rax
0x18001dee6  test    rax, rax
0x18001dee9  jnz     loc_18001DF87
0x18001deef  lea     edi, [rax+8]
0x18001def2  movzx   ebx, di
0x18001def5  or      ebx, 80070000h
0x18001defb  mov     rdi, [rbp+var_18]
0x18001deff  xor     esi, esi
0x18001df01  test    ebx, ebx
0x18001df03  jns     short loc_18001DF5E
0x18001df05  mov     rcx, [rdi]; pSid
0x18001df08  test    rcx, rcx
0x18001df0b  jz      short loc_18001DF16
0x18001df0d  call    cs:__imp_FreeSid
0x18001df13  mov     [rdi], rsi
0x18001df16  mov     rcx, [r13+0]; pSid
0x18001df1a  test    rcx, rcx
0x18001df1d  jz      short loc_18001DF29
0x18001df1f  call    cs:__imp_FreeSid
0x18001df25  mov     [r13+0], rsi
0x18001df29  mov     rcx, [r14]; hMem
0x18001df2c  test    rcx, rcx
0x18001df2f  jz      short loc_18001DF3A
0x18001df31  call    cs:__imp_LocalFree
0x18001df37  mov     [r14], rsi
0x18001df3a  mov     rcx, [r15]; pSid
0x18001df3d  test    rcx, rcx
0x18001df40  jz      short loc_18001DF4B
0x18001df42  call    cs:__imp_FreeSid
0x18001df48  mov     [r15], rsi
0x18001df4b  mov     rcx, [r12]; pSid
0x18001df4f  test    rcx, rcx
0x18001df52  jz      short loc_18001DF5E
0x18001df54  call    cs:__imp_FreeSid
0x18001df5a  mov     [r12], rsi
0x18001df5e  mov     eax, ebx
0x18001df60  mov     rcx, [rbp+var_8]
0x18001df64  xor     rcx, rsp; StackCookie
0x18001df67  call    __security_check_cookie
0x18001df6c  mov     rbx, [rsp+80h+arg_0]
0x18001df74  add     rsp, 80h
0x18001df7b  pop     r15
0x18001df7d  pop     r14
0x18001df7f  pop     r13
0x18001df81  pop     r12
0x18001df83  pop     rdi
0x18001df84  pop     rsi
0x18001df85  pop     rbp
0x18001df86  retn
0x18001df87  xor     edx, edx; DomainSid
0x18001df89  lea     r9, [rbp+cbSid]; cbSid
0x18001df8d  mov     r8, rsi; pSid
0x18001df90  lea     ecx, [rdx+3Eh]; WellKnownSidType
0x18001df93  call    cs:__imp_CreateWellKnownSid
0x18001df99  test    eax, eax
0x18001df9b  jnz     short loc_18001DFC3
0x18001df9d  call    cs:__imp_GetLastError
0x18001dfa3  mov     rcx, rsi; hMem
0x18001dfa6  mov     edi, eax
0x18001dfa8  call    cs:__imp_LocalFree
0x18001dfae  test    edi, edi
0x18001dfb0  jz      loc_18001DEFB
0x18001dfb6  jg      loc_18001DEF2
0x18001dfbc  mov     ebx, edi
0x18001dfbe  jmp     loc_18001DEFB
0x18001dfc3  mov     [r14], rsi
0x18001dfc6  jmp     loc_18001DEFF
```
