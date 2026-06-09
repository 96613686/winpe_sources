# SecLookupWellKnownSid

- ea: `0x180004190`
- end: `0x1800044dc`
- name: `SecLookupWellKnownSid`
- size: `844`
- prototype: `NTSTATUS __stdcall(WELL_KNOWN_SID_TYPE SidType, PSID Sid, ULONG SidBufferSize, PULONG SidSize)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x180004190`
- `0x180010a00`
- `0x180027f0c`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1800041ee`
- `ntoskrnl!SeExports` at `0x180004289`
- `ntoskrnl!SeExports` at `0x18000429f`
- `ntoskrnl!SeExports` at `0x1800042b5`
- `ntoskrnl!SeExports` at `0x1800042cb`
- `ntoskrnl!SeExports` at `0x1800042e1`
- `ntoskrnl!SeExports` at `0x1800042f7`
- `ntoskrnl!SeExports` at `0x18000430d`
- `ntoskrnl!SeExports` at `0x180004340`
- `ntoskrnl!SeExports` at `0x180004356`
- `ntoskrnl!SeExports` at `0x18000436c`
- `ntoskrnl!SeExports` at `0x180004382`
- `ntoskrnl!SeExports` at `0x180004398`
- `ntoskrnl!SeExports` at `0x1800043ae`
- `ntoskrnl!SeExports` at `0x1800043cd`
- `ntoskrnl!SeExports` at `0x1800043e3`
- `ntoskrnl!SeExports` at `0x1800043f9`
- `ntoskrnl!SeExports` at `0x18000440f`
- `ntoskrnl!SeExports` at `0x180004425`
- `ntoskrnl!SeExports` at `0x180004458`
- `ntoskrnl!SeExports` at `0x18000446e`
- `ntoskrnl!SeExports` at `0x180004484`
- `ntoskrnl!SeExports` at `0x18000449a`
- `ntoskrnl!SeExports` at `0x1800044b0`
- `ntoskrnl!SeExports` at `0x1800044c6`
- `ntoskrnl!RtlLengthSid` at `0x180004207`
- `ntoskrnl!RtlLengthSid` at `0x180004207`

## pseudocode

```c
NTSTATUS __stdcall SecLookupWellKnownSid(WELL_KNOWN_SID_TYPE SidType, PSID Sid, ULONG SidBufferSize, PULONG SidSize)
{
  __int32 v8; // ecx
  __int32 v9; // ecx
  __int32 v10; // ecx
  __int32 v11; // ecx
  PSID SeRestrictedSid; // rbx
  ULONG v13; // eax
  ULONG v14; // edi
  NTSTATUS result; // eax
  __int32 v16; // ecx
  __int32 v17; // ecx
  __int32 v18; // ecx
  __int32 v19; // ecx
  __int32 v20; // ecx
  __int32 v21; // ecx
  __int32 v22; // ecx
  __int32 v23; // ecx
  __int32 v24; // ecx
  __int32 v25; // ecx
  __int32 v26; // ecx
  __int32 v27; // ecx

  if ( SidType <= WinRestrictedCodeSid )
  {
    if ( SidType == WinRestrictedCodeSid )
    {
      SeRestrictedSid = SeExports->SeRestrictedSid;
    }
    else if ( SidType > WinDialupSid )
    {
      v20 = SidType - 9;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( v22 )
          {
            v23 = v22 - 2;
            if ( v23 )
            {
              if ( v23 != 4 )
                return SecpLookupWellKnownSid(SidType, Sid, SidBufferSize, SidSize);
              SeRestrictedSid = SeExports->SeAuthenticatedUsersSid;
            }
            else
            {
              SeRestrictedSid = SeExports->SeAnonymousLogonSid;
            }
          }
          else
          {
            SeRestrictedSid = SeExports->SeInteractiveSid;
          }
        }
        else
        {
          SeRestrictedSid = SeExports->SeBatchSid;
        }
      }
      else
      {
        SeRestrictedSid = SeExports->SeNetworkSid;
      }
    }
    else if ( SidType == WinDialupSid )
    {
      SeRestrictedSid = SeExports->SeDialupSid;
    }
    else if ( SidType )
    {
      v16 = SidType - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            v19 = v18 - 1;
            if ( v19 )
            {
              if ( v19 != 3 )
                return SecpLookupWellKnownSid(SidType, Sid, SidBufferSize, SidSize);
              SeRestrictedSid = SeExports->SeNtAuthoritySid;
            }
            else
            {
              SeRestrictedSid = SeExports->SeCreatorGroupSid;
            }
          }
          else
          {
            SeRestrictedSid = SeExports->SeCreatorOwnerSid;
          }
        }
        else
        {
          SeRestrictedSid = SeExports->SeLocalSid;
        }
      }
      else
      {
        SeRestrictedSid = SeExports->SeWorldSid;
      }
    }
    else
    {
      SeRestrictedSid = SeExports->SeNullSid;
    }
  }
  else
  {
    if ( SidType > WinIUserSid )
      return SecpLookupWellKnownSid(SidType, Sid, SidBufferSize, SidSize);
    if ( SidType == WinIUserSid )
    {
      SeRestrictedSid = SeExports->SeIUserSid;
    }
    else if ( SidType > WinBuiltinGuestsSid )
    {
      v24 = SidType - 29;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( v26 )
          {
            v27 = v26 - 1;
            if ( v27 )
            {
              if ( v27 != 1 )
                return SecpLookupWellKnownSid(SidType, Sid, SidBufferSize, SidSize);
              SeRestrictedSid = SeExports->SeAliasBackupOpsSid;
            }
            else
            {
              SeRestrictedSid = SeExports->SeAliasPrintOpsSid;
            }
          }
          else
          {
            SeRestrictedSid = SeExports->SeAliasSystemOpsSid;
          }
        }
        else
        {
          SeRestrictedSid = SeExports->SeAliasAccountOpsSid;
        }
      }
      else
      {
        SeRestrictedSid = SeExports->SeAliasPowerUsersSid;
      }
    }
    else if ( SidType == WinBuiltinGuestsSid )
    {
      SeRestrictedSid = SeExports->SeAliasGuestsSid;
    }
    else
    {
      v8 = SidType - 22;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 2;
            if ( v11 )
            {
              if ( v11 != 1 )
                return SecpLookupWellKnownSid(SidType, Sid, SidBufferSize, SidSize);
              SeRestrictedSid = SeExports->SeAliasUsersSid;
            }
            else
            {
              SeRestrictedSid = SeExports->SeAliasAdminsSid;
            }
          }
          else
          {
            SeRestrictedSid = SeExports->SeNetworkServiceSid;
          }
        }
        else
        {
          SeRestrictedSid = SeExports->SeLocalServiceSid;
        }
      }
      else
      {
        SeRestrictedSid = SeExports->SeLocalSystemSid;
      }
    }
  }
  if ( !SeRestrictedSid )
    return SecpLookupWellKnownSid(SidType, Sid, SidBufferSize, SidSize);
  v13 = RtlLengthSid(SeRestrictedSid);
  v14 = v13;
  if ( v13 <= SidBufferSize )
  {
    memmove(Sid, SeRestrictedSid, v13);
    result = 0;
  }
  else
  {
    result = -1073741789;
  }
  if ( SidSize )
    *SidSize = v14;
  return result;
}

```

## disassembly

```asm
0x180004190  push    rbx
0x180004192  push    rbp
0x180004193  push    rsi
0x180004194  push    rdi
0x180004195  push    r14
0x180004197  sub     rsp, 20h
0x18000419b  mov     rsi, r9
0x18000419e  mov     ebp, r8d
0x1800041a1  mov     r14, rdx
0x1800041a4  mov     r10d, ecx
0x1800041a7  cmp     ecx, 12h
0x1800041aa  jle     short loc_180004227
0x1800041ac  cmp     ecx, 3Fh ; '?'
0x1800041af  jg      loc_180004263
0x1800041b5  jz      loc_1800044C6
0x1800041bb  cmp     ecx, 1Ch
0x1800041be  jg      loc_18000443B
0x1800041c4  jz      loc_180004425
0x1800041ca  sub     ecx, 16h
0x1800041cd  jz      loc_18000440F
0x1800041d3  sub     ecx, 1
0x1800041d6  jz      loc_1800043F9
0x1800041dc  sub     ecx, 1
0x1800041df  jz      loc_1800043E3
0x1800041e5  sub     ecx, 2
0x1800041e8  jnz     loc_1800043C4
0x1800041ee  mov     rax, cs:__imp_SeExports
0x1800041f5  mov     rcx, [rax]
0x1800041f8  mov     rbx, [rcx+110h]
0x1800041ff  test    rbx, rbx
0x180004202  jz      short loc_180004263
0x180004204  mov     rcx, rbx; Sid
0x180004207  call    cs:__imp_RtlLengthSid
0x18000420e  nop     dword ptr [rax+rax+00h]
0x180004213  mov     edi, eax
0x180004215  cmp     eax, ebp
0x180004217  jbe     short loc_180004277
0x180004219  mov     eax, 0C0000023h
0x18000421e  test    rsi, rsi
0x180004221  jz      short loc_18000426B
0x180004223  mov     [rsi], edi
0x180004225  jmp     short loc_18000426B
0x180004227  jz      loc_1800043AE
0x18000422d  cmp     r10d, 8
0x180004231  jg      loc_180004323
0x180004237  jz      loc_18000430D
0x18000423d  test    r10d, r10d
0x180004240  jz      loc_1800042F7
0x180004246  sub     ecx, 1
0x180004249  jz      loc_1800042E1
0x18000424f  sub     ecx, 1
0x180004252  jz      short loc_1800042CB
0x180004254  sub     ecx, 1
0x180004257  jz      short loc_1800042B5
0x180004259  sub     ecx, 1
0x18000425c  jz      short loc_18000429F
0x18000425e  cmp     ecx, 3
0x180004261  jz      short loc_180004289
0x180004263  mov     ecx, r10d
0x180004266  call    SecpLookupWellKnownSid
0x18000426b  add     rsp, 20h
0x18000426f  pop     r14
0x180004271  pop     rdi
0x180004272  pop     rsi
0x180004273  pop     rbp
0x180004274  pop     rbx
0x180004275  retn
0x180004277  mov     r8, rdi; Size
0x18000427a  mov     rdx, rbx; Src
0x18000427d  mov     rcx, r14; void *
0x180004280  call    memmove
0x180004285  xor     eax, eax
0x180004287  jmp     short loc_18000421E
0x180004289  mov     rax, cs:__imp_SeExports
0x180004290  mov     rcx, [rax]
0x180004293  mov     rbx, [rcx+0E0h]
0x18000429a  jmp     loc_1800041FF
0x18000429f  mov     rax, cs:__imp_SeExports
0x1800042a6  mov     rcx, [rax]
0x1800042a9  mov     rbx, [rcx+0D8h]
0x1800042b0  jmp     loc_1800041FF
0x1800042b5  mov     rax, cs:__imp_SeExports
0x1800042bc  mov     rcx, [rax]
0x1800042bf  mov     rbx, [rcx+0D0h]
0x1800042c6  jmp     loc_1800041FF
0x1800042cb  mov     rax, cs:__imp_SeExports
0x1800042d2  mov     rcx, [rax]
0x1800042d5  mov     rbx, [rcx+0C8h]
0x1800042dc  jmp     loc_1800041FF
0x1800042e1  mov     rax, cs:__imp_SeExports
0x1800042e8  mov     rcx, [rax]
0x1800042eb  mov     rbx, [rcx+0C0h]
0x1800042f2  jmp     loc_1800041FF
0x1800042f7  mov     rax, cs:__imp_SeExports
0x1800042fe  mov     rcx, [rax]
0x180004301  mov     rbx, [rcx+0B8h]
0x180004308  jmp     loc_1800041FF
0x18000430d  mov     rax, cs:__imp_SeExports
0x180004314  mov     rcx, [rax]
0x180004317  mov     rbx, [rcx+0E8h]
0x18000431e  jmp     loc_1800041FF
0x180004323  sub     ecx, 9
0x180004326  jz      short loc_180004398
0x180004328  sub     ecx, 1
0x18000432b  jz      short loc_180004382
0x18000432d  sub     ecx, 1
0x180004330  jz      short loc_18000436C
0x180004332  sub     ecx, 2
0x180004335  jz      short loc_180004356
0x180004337  cmp     ecx, 4
0x18000433a  jnz     loc_180004263
0x180004340  mov     rax, cs:__imp_SeExports
0x180004347  mov     rcx, [rax]
0x18000434a  mov     rbx, [rcx+150h]
0x180004351  jmp     loc_1800041FF
0x180004356  mov     rax, cs:__imp_SeExports
0x18000435d  mov     rcx, [rax]
0x180004360  mov     rbx, [rcx+160h]
0x180004367  jmp     loc_1800041FF
0x18000436c  mov     rax, cs:__imp_SeExports
0x180004373  mov     rcx, [rax]
0x180004376  mov     rbx, [rcx+100h]
0x18000437d  jmp     loc_1800041FF
0x180004382  mov     rax, cs:__imp_SeExports
0x180004389  mov     rcx, [rax]
0x18000438c  mov     rbx, [rcx+0F8h]
0x180004393  jmp     loc_1800041FF
0x180004398  mov     rax, cs:__imp_SeExports
0x18000439f  mov     rcx, [rax]
0x1800043a2  mov     rbx, [rcx+0F0h]
0x1800043a9  jmp     loc_1800041FF
0x1800043ae  mov     rax, cs:__imp_SeExports
0x1800043b5  mov     rcx, [rax]
0x1800043b8  mov     rbx, [rcx+158h]
0x1800043bf  jmp     loc_1800041FF
0x1800043c4  cmp     ecx, 1
0x1800043c7  jnz     loc_180004263
0x1800043cd  mov     rax, cs:__imp_SeExports
0x1800043d4  mov     rcx, [rax]
0x1800043d7  mov     rbx, [rcx+118h]
0x1800043de  jmp     loc_1800041FF
0x1800043e3  mov     rax, cs:__imp_SeExports
0x1800043ea  mov     rcx, [rax]
0x1800043ed  mov     rbx, [rcx+188h]
0x1800043f4  jmp     loc_1800041FF
0x1800043f9  mov     rax, cs:__imp_SeExports
0x180004400  mov     rcx, [rax]
0x180004403  mov     rbx, [rcx+180h]
0x18000440a  jmp     loc_1800041FF
0x18000440f  mov     rax, cs:__imp_SeExports
0x180004416  mov     rcx, [rax]
0x180004419  mov     rbx, [rcx+108h]
0x180004420  jmp     loc_1800041FF
0x180004425  mov     rax, cs:__imp_SeExports
0x18000442c  mov     rcx, [rax]
0x18000442f  mov     rbx, [rcx+120h]
0x180004436  jmp     loc_1800041FF
0x18000443b  sub     ecx, 1Dh
0x18000443e  jz      short loc_1800044B0
0x180004440  sub     ecx, 1
0x180004443  jz      short loc_18000449A
0x180004445  sub     ecx, 1
0x180004448  jz      short loc_180004484
0x18000444a  sub     ecx, 1
0x18000444d  jz      short loc_18000446E
0x18000444f  cmp     ecx, 1
0x180004452  jnz     loc_180004263
0x180004458  mov     rax, cs:__imp_SeExports
0x18000445f  mov     rcx, [rax]
0x180004462  mov     rbx, [rcx+148h]
0x180004469  jmp     loc_1800041FF
0x18000446e  mov     rax, cs:__imp_SeExports
0x180004475  mov     rcx, [rax]
0x180004478  mov     rbx, [rcx+140h]
0x18000447f  jmp     loc_1800041FF
0x180004484  mov     rax, cs:__imp_SeExports
0x18000448b  mov     rcx, [rax]
0x18000448e  mov     rbx, [rcx+138h]
0x180004495  jmp     loc_1800041FF
0x18000449a  mov     rax, cs:__imp_SeExports
0x1800044a1  mov     rcx, [rax]
0x1800044a4  mov     rbx, [rcx+130h]
0x1800044ab  jmp     loc_1800041FF
0x1800044b0  mov     rax, cs:__imp_SeExports
0x1800044b7  mov     rcx, [rax]
0x1800044ba  mov     rbx, [rcx+128h]
0x1800044c1  jmp     loc_1800041FF
0x1800044c6  mov     rax, cs:__imp_SeExports
0x1800044cd  mov     rcx, [rax]
0x1800044d0  mov     rbx, [rcx+1D0h]
0x1800044d7  jmp     loc_1800041FF
```
