# GetPreviousCredentialHistory(_CREDENTIAL_HISTORY_MAP *,_CREDENTIAL_HISTORY *)

- ea: `0x1800033a8`
- end: `0x1800034fd`
- name: `?GetPreviousCredentialHistory@@YAPEAU_CREDENTIAL_HISTORY@@PEAU_CREDENTIAL_HISTORY_MAP@@PEAU1@@Z`
- size: `341`
- prototype: `struct _CREDENTIAL_HISTORY *__fastcall(struct _CREDENTIAL_HISTORY_MAP *, struct _CREDENTIAL_HISTORY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003510`
- `0x180004e60`

## callees

- `0x1800033a8`
- `0x180013f2c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000346d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000346d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180003456`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180003456`

## pseudocode

```c
struct _CREDENTIAL_HISTORY *__fastcall GetPreviousCredentialHistory(
        struct _CREDENTIAL_HISTORY_MAP *a1,
        struct _CREDENTIAL_HISTORY *a2)
{
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rax
  unsigned int *v5; // rdi
  unsigned __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // ebx

  if ( !a1 )
    return 0;
  v3 = *((_QWORD *)a1 + 67);
  if ( !v3 )
    return 0;
  v4 = *((unsigned int *)a1 + 136);
  if ( (unsigned int)v4 < 0x18 )
    return 0;
  if ( a2 )
  {
    if ( (unsigned __int64)a2 < v3 )
      return 0;
    if ( (unsigned __int64)a2 - v3 + 24 > v4 )
      return 0;
    v6 = *((unsigned int *)a2 + 5);
    if ( (unsigned __int64)a2 - v3 < v6 )
      return 0;
    v5 = (unsigned int *)((char *)a2 - v6);
    if ( (unsigned int)v6 < 0x44 )
      return 0;
    v7 = v6 - 68;
    if ( v7 < v5[9] )
      return 0;
    v8 = v7 - v5[9];
    if ( (v8 & 7) != 0 )
      return 0;
    if ( v8 < v5[11] )
      return 0;
    if ( v8 - v5[11] < v5[12] )
      return 0;
    if ( !IsValidSid(v5 + 17) )
      return 0;
    v9 = v5[9];
    if ( GetLengthSid(v5 + 17) != v9 )
      return 0;
  }
  else
  {
    v5 = (unsigned int *)(v3 + v4 - 24);
  }
  if ( *v5 != 1
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 32, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids, *v5);
  }
  return (struct _CREDENTIAL_HISTORY *)v5;
}

```

## disassembly

```asm
0x1800033a8  mov     [rsp+arg_0], rbx
0x1800033ad  mov     [rsp+arg_8], rsi
0x1800033b2  push    rdi
0x1800033b3  sub     rsp, 30h
0x1800033b7  mov     rdi, rdx
0x1800033ba  test    rcx, rcx
0x1800033bd  jz      loc_1800034F9
0x1800033c3  mov     rdx, [rcx+218h]
0x1800033ca  test    rdx, rdx
0x1800033cd  jz      loc_1800034F9
0x1800033d3  mov     eax, [rcx+220h]
0x1800033d9  cmp     eax, 18h
0x1800033dc  jb      loc_1800034F9
0x1800033e2  test    rdi, rdi
0x1800033e5  jnz     short loc_180003401
0x1800033e7  lea     rdi, [rax-18h]
0x1800033eb  add     rdi, rdx
0x1800033ee  mov     [rsp+38h+var_18], rdi
0x1800033f3  cmp     dword ptr [rdi], 1
0x1800033f6  jnz     loc_18000349F
0x1800033fc  jmp     loc_1800034E5
0x180003401  cmp     rdi, rdx
0x180003404  jb      loc_1800034DD
0x18000340a  mov     r8, rdi
0x18000340d  sub     r8, rdx
0x180003410  lea     rcx, [r8+18h]
0x180003414  cmp     rcx, rax
0x180003417  ja      loc_1800034DD
0x18000341d  mov     eax, [rdi+14h]
0x180003420  cmp     r8, rax
0x180003423  jb      loc_1800034DD
0x180003429  sub     rdi, rax
0x18000342c  mov     [rsp+38h+var_18], rdi
0x180003431  cmp     eax, 44h ; 'D'
0x180003434  jb      short loc_180003483
0x180003436  add     eax, 0FFFFFFBCh
0x180003439  cmp     eax, [rdi+24h]
0x18000343c  jb      short loc_180003487
0x18000343e  sub     eax, [rdi+24h]
0x180003441  test    al, 7
0x180003443  jnz     short loc_18000348B
0x180003445  cmp     eax, [rdi+2Ch]
0x180003448  jb      short loc_18000348F
0x18000344a  sub     eax, [rdi+2Ch]
0x18000344d  cmp     eax, [rdi+30h]
0x180003450  jb      short loc_180003493
0x180003452  lea     rcx, [rdi+44h]; pSid
0x180003456  call    cs:__imp_IsValidSid
0x18000345d  nop     dword ptr [rax+rax+00h]
0x180003462  test    eax, eax
0x180003464  jz      short loc_180003497
0x180003466  mov     ebx, [rdi+24h]
0x180003469  lea     rcx, [rdi+44h]; pSid
0x18000346d  call    cs:__imp_GetLengthSid
0x180003474  nop     dword ptr [rax+rax+00h]
0x180003479  cmp     eax, ebx
0x18000347b  jz      loc_1800033F3
0x180003481  jmp     short loc_18000349B
0x180003483  xor     eax, eax
0x180003485  jmp     short loc_1800034E8
0x180003487  xor     eax, eax
0x180003489  jmp     short loc_1800034E8
0x18000348b  xor     eax, eax
0x18000348d  jmp     short loc_1800034E8
0x18000348f  xor     eax, eax
0x180003491  jmp     short loc_1800034E8
0x180003493  xor     eax, eax
0x180003495  jmp     short loc_1800034E8
0x180003497  xor     eax, eax
0x180003499  jmp     short loc_1800034E8
0x18000349b  xor     eax, eax
0x18000349d  jmp     short loc_1800034E8
0x18000349f  lea     rax, WPP_GLOBAL_Control
0x1800034a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034ad  cmp     rcx, rax
0x1800034b0  jz      loc_1800033FC
0x1800034b6  test    byte ptr [rcx+1Ch], 4
0x1800034ba  jz      loc_1800033FC
0x1800034c0  mov     edx, 20h ; ' '
0x1800034c5  mov     r9d, [rdi]
0x1800034c8  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x1800034cf  mov     rcx, [rcx+10h]
0x1800034d3  call    WPP_SF_d
0x1800034d8  jmp     loc_1800033FC
0x1800034dd  xor     eax, eax
0x1800034df  jmp     short loc_1800034E8
0x1800034e1  xor     eax, eax
0x1800034e3  jmp     short loc_1800034E8
0x1800034e5  mov     rax, rdi
0x1800034e8  mov     rbx, [rsp+38h+arg_0]
0x1800034ed  mov     rsi, [rsp+38h+arg_8]
0x1800034f2  add     rsp, 30h
0x1800034f6  pop     rdi
0x1800034f7  retn
0x1800034f9  xor     eax, eax
0x1800034fb  jmp     short loc_1800034E8
0x18003c6f4  push    rbp
0x18003c6f6  sub     rsp, 20h
0x18003c6fa  mov     rbp, rdx
0x18003c6fd  mov     rax, [rcx]
0x18003c700  cmp     dword ptr [rax], 0C0000006h
0x18003c706  jz      short loc_18003C714
0x18003c708  cmp     dword ptr [rax], 80000002h
0x18003c70e  jz      short loc_18003C714
0x18003c710  xor     eax, eax
0x18003c712  jmp     short loc_18003C719
0x18003c714  mov     eax, 1
0x18003c719  add     rsp, 20h
0x18003c71d  pop     rbp
0x18003c71e  retn
```
