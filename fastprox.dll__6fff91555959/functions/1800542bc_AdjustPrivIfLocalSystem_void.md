# AdjustPrivIfLocalSystem(void *)

- ea: `0x1800542bc`
- end: `0x180054445`
- name: `?AdjustPrivIfLocalSystem@@YAXPEAX@Z`
- size: `393`
- prototype: `void __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800541a0`

## callees

- `0x1800542bc`
- `0x180091966`
- `0x1800919b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054415`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005431f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005432b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005431f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005432b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800542f9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180054370`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800543aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800542f9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180054370`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800543aa`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180054400`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180054400`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054383`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054383`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005440a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005440a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AdjustPrivIfLocalSystem(HANDLE TokenHandle)
{
  PSID v2; // rbx
  size_t LengthSid; // rdi
  struct _TOKEN_PRIVILEGES *v4; // rax
  struct _TOKEN_PRIVILEGES *v5; // rbx
  int v6; // ecx
  DWORD v7; // edx
  DWORD Attributes; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-59h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-55h] BYREF
  struct _TOKEN_PRIVILEGES *v11; // [rsp+38h] [rbp-51h]
  _DWORD pSid[4]; // [rsp+40h] [rbp-49h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-39h] BYREF

  ReturnLength = 88;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
  {
    pSid[0] = 257;
    pSid[1] = 83886080;
    pSid[2] = 18;
    v2 = TokenInformation[0];
    LengthSid = GetLengthSid(TokenInformation[0]);
    if ( (_DWORD)LengthSid == GetLengthSid(pSid) && !memcmp_0(pSid, v2, LengthSid) )
    {
      TokenInformationLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
      {
        v4 = (struct _TOKEN_PRIVILEGES *)LocalAlloc(0, TokenInformationLength);
        v5 = v4;
        if ( v4 )
        {
          v11 = v4;
          if ( GetTokenInformation(TokenHandle, TokenPrivileges, v4, TokenInformationLength, &TokenInformationLength) )
          {
            v6 = 0;
            v7 = 0;
            if ( v5->PrivilegeCount )
            {
              do
              {
                Attributes = v5->Privileges[v7].Attributes;
                if ( (Attributes & 2) == 0 )
                {
                  v6 = 1;
                  v5->Privileges[v7].Attributes = Attributes | 2;
                }
                ++v7;
              }
              while ( v7 < v5->PrivilegeCount );
              if ( v6 )
                AdjustTokenPrivileges(TokenHandle, 0, v5, 0, 0, 0);
            }
          }
          LocalFree(v5);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800542bc  push    rbp
0x1800542be  push    rbx
0x1800542bf  push    rsi
0x1800542c0  push    rdi
0x1800542c1  lea     rbp, [rsp-3Fh]
0x1800542c6  sub     rsp, 0C8h
0x1800542cd  mov     rax, cs:__security_cookie
0x1800542d4  xor     rax, rsp
0x1800542d7  mov     [rbp+57h+var_30], rax
0x1800542db  mov     rsi, rcx
0x1800542de  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800542e4  mov     [rbp+57h+var_AC], r9d
0x1800542e8  lea     rax, [rbp+57h+var_AC]
0x1800542ec  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800542f1  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800542f5  lea     edx, [r9-57h]; TokenInformationClass
0x1800542f9  call    cs:__imp_GetTokenInformation
0x1800542ff  test    eax, eax
0x180054301  jz      short loc_180054339
0x180054303  mov     [rbp+57h+pSid], 101h
0x18005430a  mov     [rbp+57h+var_9C], 5000000h
0x180054311  mov     [rbp+57h+var_98], 12h
0x180054318  mov     rbx, [rbp+57h+TokenInformation]
0x18005431c  mov     rcx, rbx; pSid
0x18005431f  call    cs:__imp_GetLengthSid
0x180054325  mov     edi, eax
0x180054327  lea     rcx, [rbp+57h+pSid]; pSid
0x18005432b  call    cs:__imp_GetLengthSid
0x180054331  cmp     edi, eax
0x180054333  jz      loc_180054429
0x180054339  mov     rcx, [rbp+57h+var_30]
0x18005433d  xor     rcx, rsp; StackCookie
0x180054340  call    __security_check_cookie
0x180054345  add     rsp, 0C8h
0x18005434c  pop     rdi
0x18005434d  pop     rsi
0x18005434e  pop     rbx
0x18005434f  pop     rbp
0x180054350  retn
0x180054351  mov     [rbp+57h+TokenInformationLength], 0
0x180054358  lea     rax, [rbp+57h+TokenInformationLength]
0x18005435c  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180054361  xor     r9d, r9d; TokenInformationLength
0x180054364  xor     r8d, r8d; TokenInformation
0x180054367  lea     edi, [r9+3]
0x18005436b  mov     edx, edi; TokenInformationClass
0x18005436d  mov     rcx, rsi; TokenHandle
0x180054370  call    cs:__imp_GetTokenInformation
0x180054376  test    eax, eax
0x180054378  jz      loc_180054415
0x18005437e  mov     edx, [rbp+57h+TokenInformationLength]; uBytes
0x180054381  xor     ecx, ecx; uFlags
0x180054383  call    cs:__imp_LocalAlloc
0x180054389  mov     rbx, rax
0x18005438c  test    rax, rax
0x18005438f  jz      short loc_180054339
0x180054391  mov     [rbp+57h+var_A8], rax
0x180054395  lea     rax, [rbp+57h+TokenInformationLength]
0x180054399  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18005439e  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800543a2  mov     r8, rbx; TokenInformation
0x1800543a5  mov     edx, edi; TokenInformationClass
0x1800543a7  mov     rcx, rsi; TokenHandle
0x1800543aa  call    cs:__imp_GetTokenInformation
0x1800543b0  test    eax, eax
0x1800543b2  jz      short loc_180054407
0x1800543b4  xor     ecx, ecx
0x1800543b6  xor     edx, edx
0x1800543b8  cmp     [rbx], ecx
0x1800543ba  jbe     short loc_180054407
0x1800543bc  mov     eax, edx
0x1800543be  inc     rax
0x1800543c1  lea     r8, [rax+rax*2]
0x1800543c5  mov     eax, [rbx+r8*4]
0x1800543c9  test    al, 2
0x1800543cb  jnz     short loc_1800543D9
0x1800543cd  mov     ecx, 1
0x1800543d2  or      eax, 2
0x1800543d5  mov     [rbx+r8*4], eax
0x1800543d9  inc     edx
0x1800543db  cmp     edx, [rbx]
0x1800543dd  jb      short loc_1800543BC
0x1800543df  test    ecx, ecx
0x1800543e1  jz      short loc_180054407
0x1800543e3  mov     [rsp+0E0h+var_B8], 0; ReturnLength
0x1800543ec  mov     [rsp+0E0h+ReturnLength], 0; PreviousState
0x1800543f5  xor     r9d, r9d; BufferLength
0x1800543f8  mov     r8, rbx; NewState
0x1800543fb  xor     edx, edx; DisableAllPrivileges
0x1800543fd  mov     rcx, rsi; TokenHandle
0x180054400  call    cs:__imp_AdjustTokenPrivileges
0x180054406  nop
0x180054407  mov     rcx, rbx; hMem
0x18005440a  call    cs:__imp_LocalFree
0x180054410  jmp     loc_180054339
0x180054415  call    cs:__imp_GetLastError
0x18005441b  cmp     eax, 7Ah ; 'z'
0x18005441e  jz      loc_18005437E
0x180054424  jmp     loc_180054339
0x180054429  mov     r8, rdi; Size
0x18005442c  mov     rdx, rbx; Buf2
0x18005442f  lea     rcx, [rbp+57h+pSid]; Buf1
0x180054433  call    memcmp_0
0x180054438  test    eax, eax
0x18005443a  jz      loc_180054351
0x180054440  jmp     loc_180054339
```
