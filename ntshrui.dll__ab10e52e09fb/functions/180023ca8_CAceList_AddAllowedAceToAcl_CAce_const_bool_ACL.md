# CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)

- ea: `0x180023ca8`
- end: `0x180023e02`
- name: `?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z`
- size: `346`
- prototype: `int(CAceList *__hidden this, struct CAce *const, bool, struct _ACL *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023adc`

## callees

- `0x1800098dc`
- `0x180023ca8`
- `0x18002637c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023dde`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180023dd4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180023dd4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180023d33`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180023d33`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180023d91`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180023d91`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023d24`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023d5f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023d24`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023d5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023ce9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023ce9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023db3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023db3`

## pseudocode

```c
__int64 __fastcall CAceList::_AddAllowedAceToAcl(CAceList *this, struct CAce *const a2, char a3, struct _ACL *a4)
{
  unsigned __int8 v6; // bl
  char *v7; // rax
  char *v8; // r15
  unsigned int Error; // esi
  void *v10; // rbx
  DWORD LengthSid; // eax
  const void *v12; // rdi
  unsigned int v13; // ebx
  DWORD v14; // eax
  signed int LastError; // eax
  signed int v16; // eax

  if ( !a3 || *((_DWORD *)this + 6) || *((_DWORD *)this + 7) )
    v6 = *((_BYTE *)a2 + 1);
  else
    v6 = *((_BYTE *)a2 + 1) & 0xEF;
  if ( *(_BYTE *)a2 == 9 )
  {
    v7 = (char *)LocalAlloc(0x40u, *((unsigned __int16 *)a2 + 1));
    v8 = v7;
    if ( !v7 )
      return (unsigned int)-2147024882;
    *v7 = *(_BYTE *)a2;
    v7[1] = v6;
    *((_WORD *)v7 + 1) = *((_WORD *)a2 + 1);
    *((_DWORD *)v7 + 1) = *((_DWORD *)a2 + 1);
    v10 = (void *)*((_QWORD *)a2 + 1);
    LengthSid = GetLengthSid(v10);
    if ( CopySid(LengthSid, v8 + 8, v10) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( (Error & 0x80000000) != 0 )
      {
LABEL_17:
        LocalFree(v8);
        return Error;
      }
    }
    if ( *((_DWORD *)a2 + 6) )
    {
      v12 = (const void *)*((_QWORD *)a2 + 2);
      v13 = *((_DWORD *)a2 + 6);
      v14 = GetLengthSid(*((PSID *)a2 + 1));
      memcpy_0(&v8[v14 + 8], v12, v13);
    }
    if ( !AddAce(a4, 2u, 0xFFFFFFFF, v8, *((unsigned __int16 *)a2 + 1)) )
    {
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
    }
    goto LABEL_17;
  }
  Error = 0;
  if ( !AddAccessAllowedAceEx(a4, 2u, v6, *((_DWORD *)a2 + 1), *((PSID *)a2 + 1)) )
  {
    v16 = GetLastError();
    Error = v16;
    if ( v16 > 0 )
      return (unsigned __int16)v16 | 0x80070000;
  }
  return Error;
}

```

## disassembly

```asm
0x180023ca8  push    rbx
0x180023caa  push    rbp
0x180023cab  push    rsi
0x180023cac  push    rdi
0x180023cad  push    r14
0x180023caf  push    r15
0x180023cb1  sub     rsp, 38h
0x180023cb5  mov     rbp, r9
0x180023cb8  mov     r14, rdx
0x180023cbb  test    r8b, r8b
0x180023cbe  jz      short loc_180023CD4
0x180023cc0  cmp     dword ptr [rcx+18h], 0
0x180023cc4  jnz     short loc_180023CD4
0x180023cc6  cmp     dword ptr [rcx+1Ch], 0
0x180023cca  jnz     short loc_180023CD4
0x180023ccc  mov     bl, [rdx+1]
0x180023ccf  and     bl, 0EFh
0x180023cd2  jmp     short loc_180023CD7
0x180023cd4  mov     bl, [rdx+1]
0x180023cd7  cmp     byte ptr [rdx], 9
0x180023cda  jnz     loc_180023DBB
0x180023ce0  movzx   edx, word ptr [rdx+2]; uBytes
0x180023ce4  mov     ecx, 40h ; '@'; uFlags
0x180023ce9  call    cs:__imp_LocalAlloc
0x180023cef  mov     r15, rax
0x180023cf2  test    rax, rax
0x180023cf5  jnz     short loc_180023D01
0x180023cf7  mov     esi, 8007000Eh
0x180023cfc  jmp     loc_180023DF3
0x180023d01  mov     al, [r14]
0x180023d04  mov     [r15], al
0x180023d07  mov     [r15+1], bl
0x180023d0b  movzx   eax, word ptr [r14+2]
0x180023d10  mov     [r15+2], ax
0x180023d15  mov     eax, [r14+4]
0x180023d19  mov     [r15+4], eax
0x180023d1d  mov     rbx, [r14+8]
0x180023d21  mov     rcx, rbx; pSid
0x180023d24  call    cs:__imp_GetLengthSid
0x180023d2a  lea     rdx, [r15+8]; pDestinationSid
0x180023d2e  mov     r8, rbx; pSourceSid
0x180023d31  mov     ecx, eax; nDestinationSidLength
0x180023d33  call    cs:__imp_CopySid
0x180023d39  test    eax, eax
0x180023d3b  jz      short loc_180023D41
0x180023d3d  xor     esi, esi
0x180023d3f  jmp     short loc_180023D4C
0x180023d41  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180023d46  mov     esi, eax
0x180023d48  test    eax, eax
0x180023d4a  js      short loc_180023DB0
0x180023d4c  cmp     dword ptr [r14+18h], 0
0x180023d51  jz      short loc_180023D79
0x180023d53  mov     rcx, [r14+8]; pSid
0x180023d57  mov     rdi, [r14+10h]
0x180023d5b  mov     ebx, [r14+18h]
0x180023d5f  call    cs:__imp_GetLengthSid
0x180023d65  mov     ecx, eax
0x180023d67  mov     r8d, ebx; Size
0x180023d6a  add     rcx, 8
0x180023d6e  mov     rdx, rdi; Src
0x180023d71  add     rcx, r15; void *
0x180023d74  call    memcpy_0
0x180023d79  movzx   eax, word ptr [r14+2]
0x180023d7e  mov     r9, r15; pAceList
0x180023d81  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180023d85  mov     [rsp+68h+nAceListLength], eax; nAceListLength
0x180023d89  mov     edx, 2; dwAceRevision
0x180023d8e  mov     rcx, rbp; pAcl
0x180023d91  call    cs:__imp_AddAce
0x180023d97  test    eax, eax
0x180023d99  jnz     short loc_180023DB0
0x180023d9b  call    cs:__imp_GetLastError
0x180023da1  mov     esi, eax
0x180023da3  test    eax, eax
0x180023da5  jle     short loc_180023DB0
0x180023da7  movzx   esi, ax
0x180023daa  or      esi, 80070000h
0x180023db0  mov     rcx, r15; hMem
0x180023db3  call    cs:__imp_LocalFree
0x180023db9  jmp     short loc_180023DF3
0x180023dbb  mov     rax, [rdx+8]
0x180023dbf  xor     esi, esi
0x180023dc1  mov     r9d, [rdx+4]; AccessMask
0x180023dc5  mov     rcx, rbp; pAcl
0x180023dc8  movzx   r8d, bl; AceFlags
0x180023dcc  mov     qword ptr [rsp+68h+nAceListLength], rax; pSid
0x180023dd1  lea     edx, [rsi+2]; dwAceRevision
0x180023dd4  call    cs:__imp_AddAccessAllowedAceEx
0x180023dda  test    eax, eax
0x180023ddc  jnz     short loc_180023DF3
0x180023dde  call    cs:__imp_GetLastError
0x180023de4  mov     esi, eax
0x180023de6  test    eax, eax
0x180023de8  jle     short loc_180023DF3
0x180023dea  movzx   esi, ax
0x180023ded  or      esi, 80070000h
0x180023df3  mov     eax, esi
0x180023df5  add     rsp, 38h
0x180023df9  pop     r15
0x180023dfb  pop     r14
0x180023dfd  pop     rdi
0x180023dfe  pop     rsi
0x180023dff  pop     rbp
0x180023e00  pop     rbx
0x180023e01  retn
```
