# StSecpGetAppSid

- ea: `0x140011810`
- end: `0x140011a1d`
- name: `StSecpGetAppSid`
- size: `525`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000dd68`
- `0x140011350`

## callees

- `0x140003540`
- `0x140011810`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400119bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400119d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400119bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400119d5`
- `ntoskrnl!ExAllocatePool2` at `0x14001185d`
- `ntoskrnl!ExAllocatePool2` at `0x140011886`
- `ntoskrnl!ExAllocatePool2` at `0x14001185d`
- `ntoskrnl!ExAllocatePool2` at `0x140011886`
- `ntoskrnl!RtlInitializeSid` at `0x14001192e`
- `ntoskrnl!RtlInitializeSid` at `0x14001192e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140011947`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140011968`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140011947`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140011968`
- `ntoskrnl!SeConvertSidToStringSid` at `0x14001198b`
- `ntoskrnl!SeConvertSidToStringSid` at `0x14001198b`
- `ksecdd!BCryptFinishHash` at `0x14001190f`
- `ksecdd!BCryptFinishHash` at `0x14001190f`
- `ksecdd!BCryptHashData` at `0x1400118e7`
- `ksecdd!BCryptHashData` at `0x1400118e7`
- `ksecdd!BCryptCreateHash` at `0x1400118c1`
- `ksecdd!BCryptCreateHash` at `0x1400118c1`
- `ksecdd!BCryptDestroyHash` at `0x1400119a3`
- `ksecdd!BCryptDestroyHash` at `0x1400119a3`

## pseudocode

```c
__int64 __fastcall StSecpGetAppSid(PUCHAR *a1, __int64 a2)
{
  UCHAR *Pool2; // rbp
  UCHAR *v5; // rsi
  NTSTATUS v6; // ebx
  ULONG *v7; // rdi
  unsigned __int8 v8; // bl
  PULONG v9; // rax
  ULONG v10; // ecx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-58h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+48h] [rbp-50h] BYREF
  _BYTE Sid[40]; // [rsp+50h] [rbp-48h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  phHash = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  Pool2 = (UCHAR *)ExAllocatePool2(256, *(unsigned int *)&g_cbHashObject, 1884517459);
  if ( Pool2 )
  {
    v5 = (UCHAR *)ExAllocatePool2(256, *(unsigned int *)&g_cbHashValue, 1884517459);
    if ( v5 )
    {
      v6 = BCryptCreateHash(g_HashProvider, &phHash, Pool2, *(ULONG *)&g_cbHashObject, 0, 0, 0);
      if ( v6 >= 0 )
      {
        v6 = BCryptHashData(phHash, a1[1], *(unsigned __int16 *)a1, 0);
        if ( v6 >= 0 )
        {
          v6 = BCryptFinishHash(phHash, v5, *(ULONG *)&g_cbHashValue, 0);
          if ( v6 >= 0 )
          {
            v6 = RtlInitializeSid(Sid, &IdentifierAuthority, 8u);
            if ( v6 >= 0 )
            {
              v7 = (ULONG *)v5;
              v8 = 1;
              *RtlSubAuthoritySid(Sid, 0) = 2;
              do
              {
                v9 = RtlSubAuthoritySid(Sid, v8);
                v10 = *v7++;
                ++v8;
                *v9 = v10;
              }
              while ( v8 < 8u );
              v6 = SeConvertSidToStringSid(Sid, a2);
            }
          }
        }
      }
    }
    else
    {
      v6 = -1073741801;
    }
  }
  else
  {
    v5 = 0;
    v6 = -1073741801;
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x70537453u);
  if ( v5 )
    ExFreePoolWithTag(v5, 0x70537453u);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140011810  mov     [rsp+arg_10], rbx
0x140011815  mov     [rsp+arg_18], rbp
0x14001181a  push    rsi
0x14001181b  push    rdi
0x14001181c  push    r14
0x14001181e  sub     rsp, 80h
0x140011825  mov     rax, cs:__security_cookie
0x14001182c  xor     rax, rsp
0x14001182f  mov     [rsp+98h+var_20], rax
0x140011834  mov     r14, rdx
0x140011837  mov     word ptr [rsp+98h+IdentifierAuthority.Value+4], 0F00h
0x14001183e  mov     edx, cs:g_cbHashObject
0x140011844  mov     rdi, rcx
0x140011847  xor     ebx, ebx
0x140011849  mov     ecx, 100h
0x14001184e  mov     r8d, 70537453h
0x140011854  mov     [rsp+98h+phHash], rbx
0x140011859  mov     dword ptr [rsp+98h+IdentifierAuthority.Value], ebx
0x14001185d  call    cs:__imp_ExAllocatePool2
0x140011864  nop     dword ptr [rax+rax+00h]
0x140011869  mov     rbp, rax
0x14001186c  test    rax, rax
0x14001186f  jz      loc_140011A10
0x140011875  mov     edx, cs:g_cbHashValue
0x14001187b  mov     ecx, 100h
0x140011880  mov     r8d, 70537453h
0x140011886  call    cs:__imp_ExAllocatePool2
0x14001188d  nop     dword ptr [rax+rax+00h]
0x140011892  mov     rsi, rax
0x140011895  test    rax, rax
0x140011898  jz      loc_140011A09
0x14001189e  mov     r9d, cs:g_cbHashObject; cbHashObject
0x1400118a5  lea     rdx, [rsp+98h+phHash]; phHash
0x1400118aa  mov     rcx, cs:g_HashProvider; hAlgorithm
0x1400118b1  mov     r8, rbp; pbHashObject
0x1400118b4  mov     [rsp+98h+dwFlags], ebx; dwFlags
0x1400118b8  mov     [rsp+98h+cbSecret], ebx; cbSecret
0x1400118bc  mov     [rsp+98h+pbSecret], rbx; pbSecret
0x1400118c1  call    cs:__imp_BCryptCreateHash
0x1400118c8  nop     dword ptr [rax+rax+00h]
0x1400118cd  mov     ebx, eax
0x1400118cf  test    eax, eax
0x1400118d1  js      loc_140011999
0x1400118d7  movzx   r8d, word ptr [rdi]; cbInput
0x1400118db  xor     r9d, r9d; dwFlags
0x1400118de  mov     rdx, [rdi+8]; pbInput
0x1400118e2  mov     rcx, [rsp+98h+phHash]; hHash
0x1400118e7  call    cs:__imp_BCryptHashData
0x1400118ee  nop     dword ptr [rax+rax+00h]
0x1400118f3  mov     ebx, eax
0x1400118f5  test    eax, eax
0x1400118f7  js      loc_140011999
0x1400118fd  mov     r8d, cs:g_cbHashValue; cbOutput
0x140011904  xor     r9d, r9d; dwFlags
0x140011907  mov     rcx, [rsp+98h+phHash]; hHash
0x14001190c  mov     rdx, rsi; pbOutput
0x14001190f  call    cs:__imp_BCryptFinishHash
0x140011916  nop     dword ptr [rax+rax+00h]
0x14001191b  mov     ebx, eax
0x14001191d  test    eax, eax
0x14001191f  js      short loc_140011999
0x140011921  mov     r8b, 8; SubAuthorityCount
0x140011924  lea     rdx, [rsp+98h+IdentifierAuthority]; IdentifierAuthority
0x140011929  lea     rcx, [rsp+98h+Sid]; Sid
0x14001192e  call    cs:__imp_RtlInitializeSid
0x140011935  nop     dword ptr [rax+rax+00h]
0x14001193a  mov     ebx, eax
0x14001193c  test    eax, eax
0x14001193e  js      short loc_140011999
0x140011940  xor     edx, edx; SubAuthority
0x140011942  lea     rcx, [rsp+98h+Sid]; Sid
0x140011947  call    cs:__imp_RtlSubAuthoritySid
0x14001194e  nop     dword ptr [rax+rax+00h]
0x140011953  mov     rdi, rsi
0x140011956  mov     bl, 1
0x140011958  mov     dword ptr [rax], 2
0x14001195e  xchg    ax, ax
0x140011960  movzx   edx, bl; SubAuthority
0x140011963  lea     rcx, [rsp+98h+Sid]; Sid
0x140011968  call    cs:__imp_RtlSubAuthoritySid
0x14001196f  nop     dword ptr [rax+rax+00h]
0x140011974  mov     ecx, [rdi]
0x140011976  lea     rdi, [rdi+4]
0x14001197a  inc     bl
0x14001197c  mov     [rax], ecx
0x14001197e  cmp     bl, 8
0x140011981  jb      short loc_140011960
0x140011983  mov     rdx, r14
0x140011986  lea     rcx, [rsp+98h+Sid]
0x14001198b  call    cs:__imp_SeConvertSidToStringSid
0x140011992  nop     dword ptr [rax+rax+00h]
0x140011997  mov     ebx, eax
0x140011999  mov     rcx, [rsp+98h+phHash]; hHash
0x14001199e  test    rcx, rcx
0x1400119a1  jz      short loc_1400119AF
0x1400119a3  call    cs:__imp_BCryptDestroyHash
0x1400119aa  nop     dword ptr [rax+rax+00h]
0x1400119af  test    rbp, rbp
0x1400119b2  jz      short loc_1400119C8
0x1400119b4  mov     edx, 70537453h; Tag
0x1400119b9  mov     rcx, rbp; P
0x1400119bc  call    cs:__imp_ExFreePoolWithTag
0x1400119c3  nop     dword ptr [rax+rax+00h]
0x1400119c8  test    rsi, rsi
0x1400119cb  jz      short loc_1400119E1
0x1400119cd  mov     edx, 70537453h; Tag
0x1400119d2  mov     rcx, rsi; P
0x1400119d5  call    cs:__imp_ExFreePoolWithTag
0x1400119dc  nop     dword ptr [rax+rax+00h]
0x1400119e1  mov     eax, ebx
0x1400119e3  mov     rcx, [rsp+98h+var_20]
0x1400119e8  xor     rcx, rsp; StackCookie
0x1400119eb  call    __security_check_cookie
0x1400119f0  lea     r11, [rsp+98h+var_18]
0x1400119f8  mov     rbx, [r11+30h]
0x1400119fc  mov     rbp, [r11+38h]
0x140011a00  mov     rsp, r11
0x140011a03  pop     r14
0x140011a05  pop     rdi
0x140011a06  pop     rsi
0x140011a07  retn
0x140011a09  mov     ebx, 0C0000017h
0x140011a0e  jmp     short loc_140011999
0x140011a10  mov     rsi, rbx
0x140011a13  mov     ebx, 0C0000017h
0x140011a18  jmp     loc_140011999
```
