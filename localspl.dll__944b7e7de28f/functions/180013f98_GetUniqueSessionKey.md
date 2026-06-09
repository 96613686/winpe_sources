# GetUniqueSessionKey

- ea: `0x180013f98`
- end: `0x180014129`
- name: `GetUniqueSessionKey`
- size: `401`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001393c`
- `0x180013e60`
- `0x180040674`
- `0x1800c9fbc`

## callees

- `0x180013f98`
- `0x180034984`
- `0x1800ca63c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800140ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001410a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800140ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001410a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014016`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013fe0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013fe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140d0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014089`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014089`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014006`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014053`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014006`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014053`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800140aa`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800140aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800140ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800140ba`

## pseudocode

```c
__int64 __fastcall GetUniqueSessionKey(__int64 a1, LPWSTR *a2)
{
  void *v2; // rsi
  unsigned int *v4; // rdi
  unsigned int TokenInformation; // ebx
  unsigned int i; // ecx
  __int64 v7; // rbp
  DWORD LengthSid; // r14d
  void *v9; // rax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  int v12; // [rsp+64h] [rbp+Ch]
  HANDLE TokenHandle; // [rsp+70h] [rbp+18h] BYREF

  v12 = HIDWORD(a1);
  v2 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  v4 = 0;
  TokenInformation = GetTokenHandle(&TokenHandle);
  if ( TokenInformation )
  {
    if ( a2 )
    {
      TokenInformation = GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength);
      if ( !TokenInformation && GetLastError() == 122 )
      {
        v4 = (unsigned int *)ALLOCMEM(TokenInformationLength);
        if ( v4 )
        {
          TokenInformation = GetTokenInformation(
                               TokenHandle,
                               TokenGroups,
                               v4,
                               TokenInformationLength,
                               &TokenInformationLength);
          if ( TokenInformation )
          {
            TokenInformation = 0;
            for ( i = 0; i < *v4; ++i )
            {
              v7 = *(_QWORD *)&v4[4 * i + 2];
              if ( *(_BYTE *)(v7 + 1) == 3 && *(_DWORD *)(v7 + 8) == 5 )
              {
                LengthSid = GetLengthSid(*(PSID *)&v4[4 * i + 2]);
                v9 = (void *)ALLOCMEM(LengthSid);
                v2 = v9;
                if ( v9 && CopySid(LengthSid, v9, (PSID)v7) && ConvertSidToStringSidW(v2, a2) )
                  TokenInformation = 1;
                break;
              }
            }
          }
        }
      }
    }
    else
    {
      SetLastError(0x57u);
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( v4 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v4);
  return TokenInformation;
}

```

## disassembly

```asm
0x180013f98  mov     rax, rsp
0x180013f9b  mov     [rax+10h], rbx
0x180013f9f  mov     [rax+20h], rbp
0x180013fa3  mov     [rax+8], rcx
0x180013fa7  push    rsi
0x180013fa8  push    rdi
0x180013fa9  push    r12
0x180013fab  push    r14
0x180013fad  push    r15
0x180013faf  sub     rsp, 30h
0x180013fb3  xor     esi, esi
0x180013fb5  mov     qword ptr [rax+18h], 0
0x180013fbd  lea     rcx, [rax+18h]; TokenHandle
0x180013fc1  mov     [rax+8], esi
0x180013fc4  mov     r15, rdx
0x180013fc7  xor     edi, edi
0x180013fc9  call    GetTokenHandle
0x180013fce  mov     ebx, eax
0x180013fd0  test    eax, eax
0x180013fd2  jz      loc_1800140C6
0x180013fd8  test    r15, r15
0x180013fdb  jnz     short loc_180013FEB
0x180013fdd  lea     ecx, [rsi+57h]; dwErrCode
0x180013fe0  call    cs:__imp_SetLastError
0x180013fe6  jmp     loc_1800140C6
0x180013feb  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180013ff0  lea     rax, [rsp+58h+TokenInformationLength]
0x180013ff5  xor     r9d, r9d; TokenInformationLength
0x180013ff8  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180013ffd  xor     r8d, r8d; TokenInformation
0x180014000  lea     ebp, [r9+2]
0x180014004  mov     edx, ebp; TokenInformationClass
0x180014006  call    cs:__imp_GetTokenInformation
0x18001400c  mov     ebx, eax
0x18001400e  test    eax, eax
0x180014010  jnz     loc_1800140C6
0x180014016  call    cs:__imp_GetLastError
0x18001401c  cmp     eax, 7Ah ; 'z'
0x18001401f  jnz     loc_1800140C6
0x180014025  mov     ecx, [rsp+58h+TokenInformationLength]; dwBytes
0x180014029  call    ALLOCMEM
0x18001402e  mov     rdi, rax
0x180014031  test    rax, rax
0x180014034  jz      loc_1800140C6
0x18001403a  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18001403f  lea     rax, [rsp+58h+TokenInformationLength]
0x180014044  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180014049  mov     r8, rdi; TokenInformation
0x18001404c  mov     edx, ebp; TokenInformationClass
0x18001404e  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180014053  call    cs:__imp_GetTokenInformation
0x180014059  mov     ebx, eax
0x18001405b  test    eax, eax
0x18001405d  jz      short loc_1800140C6
0x18001405f  xor     ebx, ebx
0x180014061  lea     r12d, [rbp-1]
0x180014065  xor     ecx, ecx
0x180014067  cmp     ecx, [rdi]
0x180014069  jnb     short loc_1800140C6
0x18001406b  mov     eax, ecx
0x18001406d  add     rax, rax
0x180014070  mov     rbp, [rdi+rax*8+8]
0x180014075  cmp     byte ptr [rbp+1], 3
0x180014079  jnz     short loc_180014081
0x18001407b  cmp     dword ptr [rbp+8], 5
0x18001407f  jz      short loc_180014086
0x180014081  add     ecx, r12d
0x180014084  jmp     short loc_180014067
0x180014086  mov     rcx, rbp; pSid
0x180014089  call    cs:__imp_GetLengthSid
0x18001408f  mov     ecx, eax; dwBytes
0x180014091  mov     r14d, eax
0x180014094  call    ALLOCMEM
0x180014099  mov     rsi, rax
0x18001409c  test    rax, rax
0x18001409f  jz      short loc_1800140C6
0x1800140a1  mov     r8, rbp; pSourceSid
0x1800140a4  mov     rdx, rax; pDestinationSid
0x1800140a7  mov     ecx, r14d; nDestinationSidLength
0x1800140aa  call    cs:__imp_CopySid
0x1800140b0  test    eax, eax
0x1800140b2  jz      short loc_1800140C6
0x1800140b4  mov     rdx, r15; StringSid
0x1800140b7  mov     rcx, rsi; Sid
0x1800140ba  call    cs:__imp_ConvertSidToStringSidW
0x1800140c0  test    eax, eax
0x1800140c2  cmovnz  ebx, r12d
0x1800140c6  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1800140cb  test    rcx, rcx
0x1800140ce  jz      short loc_1800140D6
0x1800140d0  call    cs:__imp_CloseHandle
0x1800140d6  test    rsi, rsi
0x1800140d9  jz      short loc_1800140F3
0x1800140db  mov     rcx, gs:60h
0x1800140e4  mov     r8, rsi; lpMem
0x1800140e7  xor     edx, edx; dwFlags
0x1800140e9  mov     rcx, [rcx+30h]; hHeap
0x1800140ed  call    cs:__imp_HeapFree
0x1800140f3  test    rdi, rdi
0x1800140f6  jz      short loc_180014110
0x1800140f8  mov     rcx, gs:60h
0x180014101  mov     r8, rdi; lpMem
0x180014104  xor     edx, edx; dwFlags
0x180014106  mov     rcx, [rcx+30h]; hHeap
0x18001410a  call    cs:__imp_HeapFree
0x180014110  mov     rbp, [rsp+58h+arg_18]
0x180014115  mov     eax, ebx
0x180014117  mov     rbx, [rsp+58h+arg_8]
0x18001411c  add     rsp, 30h
0x180014120  pop     r15
0x180014122  pop     r14
0x180014124  pop     r12
0x180014126  pop     rdi
0x180014127  pop     rsi
0x180014128  retn
```
