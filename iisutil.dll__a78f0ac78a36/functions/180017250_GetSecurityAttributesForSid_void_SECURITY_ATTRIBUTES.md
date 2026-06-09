# GetSecurityAttributesForSid(void *,_SECURITY_ATTRIBUTES * *)

- ea: `0x180017250`
- end: `0x180017487`
- name: `?GetSecurityAttributesForSid@@YAKPEAXPEAPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(void *, struct _SECURITY_ATTRIBUTES **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180017250`
- `0x1800180c0`
- `0x1800183f8`
- `0x180018438`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800172af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800172af`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800173eb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800173eb`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001739f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001739f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180017313`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180017313`

## string_xrefs

- `0x18001734a`: `GetSecurityAttributesForSid`
- `0x180017358`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180017412`: `Setting the DACL on the security descriptor failed\n`
- `0x180017338`: `Setting ACE's into ACL failed.\n`
- `0x1800173ca`: `Initializing the security descriptor failed\n`

## pseudocode

```c
__int64 __fastcall GetSecurityAttributesForSid(void *a1, struct _SECURITY_ATTRIBUTES **a2)
{
  void *v3; // rbx
  struct _SECURITY_ATTRIBUTES *v4; // rdi
  _OWORD *v5; // rsi
  char *v6; // rax
  void *v7; // r14
  int dwMessageId; // eax
  char *v10; // rcx
  unsigned int v11; // r8d
  struct _SECURITY_ATTRIBUTES *v12; // rax
  char v13; // [rsp+30h] [rbp-18h]
  HLOCAL hMem; // [rsp+58h] [rbp+10h] BYREF

  hMem = 0;
  v3 = a1;
  if ( a2 && !*a2 )
  {
    v4 = 0;
    if ( !a1 )
      goto LABEL_34;
    v5 = 0;
    v6 = (char *)operator new(0x30u);
    v7 = v6;
    if ( !v6 )
    {
      LODWORD(v3) = 14;
LABEL_6:
      if ( hMem )
      {
        LocalFree(hMem);
        hMem = 0;
      }
      if ( v5 )
        operator delete(v5);
      if ( v4 )
        operator delete(v4);
      return (unsigned int)v3;
    }
    *(_QWORD *)(v6 + 12) = 0;
    *(_QWORD *)(v6 + 20) = 0;
    *((_QWORD *)v6 + 4) = 5;
    *(_QWORD *)(v6 + 4) = 1;
    *((_DWORD *)v6 + 7) = 0;
    *(_DWORD *)v6 = -1073741824;
    *((_QWORD *)v6 + 5) = v3;
    dwMessageId = SetEntriesInAclW(1u, (PEXPLICIT_ACCESS_W)v6, 0, (PACL *)&hMem);
    LODWORD(v3) = dwMessageId;
    if ( dwMessageId )
    {
      if ( (g_dwDebugFlagsIISUtil & 0xF) == 0 )
        goto LABEL_33;
      if ( dwMessageId > 0 )
        dwMessageId = (unsigned __int16)dwMessageId | 0x80070000;
      v10 = "Setting ACE's into ACL failed.\n";
      v11 = 1199;
      goto LABEL_18;
    }
    v5 = operator new(0x28u);
    if ( !v5 )
      goto LABEL_20;
    *v5 = 0;
    v5[1] = 0;
    *((_QWORD *)v5 + 4) = 0;
    if ( InitializeSecurityDescriptor(v5, 1u) )
    {
      if ( SetSecurityDescriptorDacl(v5, 1, (PACL)hMem, 0) )
      {
        v12 = (struct _SECURITY_ATTRIBUTES *)operator new(0x20u);
        v4 = v12;
        if ( !v12 )
        {
LABEL_20:
          LODWORD(v3) = 14;
          goto LABEL_33;
        }
        *(_QWORD *)&v12->nLength = 24;
        *(_QWORD *)&v12->bInheritHandle = 0;
        v12->lpSecurityDescriptor = v5;
        *(_QWORD *)&v12[1].nLength = hMem;
      }
      else
      {
        dwMessageId = GetLastError();
        LODWORD(v3) = dwMessageId;
        if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
        {
          if ( dwMessageId > 0 )
            dwMessageId = (unsigned __int16)dwMessageId | 0x80070000;
          v10 = "Setting the DACL on the security descriptor failed\n";
          v11 = 1235;
          goto LABEL_18;
        }
      }
    }
    else
    {
      dwMessageId = GetLastError();
      LODWORD(v3) = dwMessageId;
      if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      {
        if ( dwMessageId > 0 )
          dwMessageId = (unsigned __int16)dwMessageId | 0x80070000;
        v10 = "Initializing the security descriptor failed\n";
        v11 = 1220;
LABEL_18:
        PuDbgPrintError(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
          v11,
          "GetSecurityAttributesForSid",
          dwMessageId,
          v10,
          v13);
      }
    }
LABEL_33:
    operator delete(v7);
    if ( (_DWORD)v3 )
      goto LABEL_6;
LABEL_34:
    *a2 = v4;
    return (unsigned int)v3;
  }
  return 87;
}

```

## disassembly

```asm
0x180017250  mov     [rsp+arg_0], rbx
0x180017255  mov     [rsp+arg_10], rsi
0x18001725a  push    rdi
0x18001725b  push    r14
0x18001725d  push    r15; char
0x18001725f  sub     rsp, 30h
0x180017263  mov     [rsp+48h+hMem], 0
0x18001726c  mov     r15, rdx
0x18001726f  mov     rbx, rcx
0x180017272  test    rdx, rdx
0x180017275  jz      loc_18001746E
0x18001727b  cmp     qword ptr [rdx], 0
0x18001727f  jnz     loc_18001746E
0x180017285  xor     edi, edi
0x180017287  test    rbx, rbx
0x18001728a  jz      loc_180017466
0x180017290  xor     esi, esi
0x180017292  lea     ecx, [rsi+30h]; Size
0x180017295  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001729a  mov     r14, rax
0x18001729d  test    rax, rax
0x1800172a0  jnz     short loc_1800172DF
0x1800172a2  lea     ebx, [rsi+0Eh]
0x1800172a5  mov     rcx, [rsp+48h+hMem]; hMem
0x1800172aa  test    rcx, rcx
0x1800172ad  jz      short loc_1800172BE
0x1800172af  call    cs:__imp_LocalFree
0x1800172b5  mov     [rsp+48h+hMem], 0
0x1800172be  test    rsi, rsi
0x1800172c1  jz      short loc_1800172CB
0x1800172c3  mov     rcx, rsi; Block
0x1800172c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800172cb  test    rdi, rdi
0x1800172ce  jz      short loc_1800172D8
0x1800172d0  mov     rcx, rdi; Block
0x1800172d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800172d8  mov     eax, ebx
0x1800172da  jmp     loc_180017473
0x1800172df  mov     [rax+0Ch], rsi
0x1800172e3  lea     r9, [rsp+48h+hMem]; NewAcl
0x1800172e8  mov     [rax+14h], rsi
0x1800172ec  xor     r8d, r8d; OldAcl
0x1800172ef  mov     rdx, r14; pListOfExplicitEntries
0x1800172f2  mov     qword ptr [rax+20h], 5
0x1800172fa  mov     qword ptr [rax+4], 1
0x180017302  mov     [rax+1Ch], esi
0x180017305  lea     ecx, [r8+1]; cCountOfExplicitEntries
0x180017309  mov     dword ptr [rax], 0C0000000h
0x18001730f  mov     [rax+28h], rbx
0x180017313  call    cs:__imp_SetEntriesInAclW
0x180017319  mov     ebx, eax
0x18001731b  test    eax, eax
0x18001731d  jz      short loc_18001736D
0x18001731f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017326  jz      loc_180017456
0x18001732c  test    eax, eax
0x18001732e  jle     short loc_180017338
0x180017330  movzx   eax, ax
0x180017333  or      eax, 80070000h
0x180017338  lea     rcx, aSettingAceSInt; "Setting ACE's into ACL failed.\n"
0x18001733f  mov     r8d, 4AFh; unsigned int
0x180017345  mov     [rsp+48h+var_20], rcx; char *
0x18001734a  lea     r9, aGetsecurityatt_0; "GetSecurityAttributesForSid"
0x180017351  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017358  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001735f  mov     [rsp+48h+dwMessageId], eax; dwMessageId
0x180017363  call    PuDbgPrintError
0x180017368  jmp     loc_180017456
0x18001736d  mov     ecx, 28h ; '('; Size
0x180017372  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017377  mov     rsi, rax
0x18001737a  test    rax, rax
0x18001737d  jnz     short loc_180017389
0x18001737f  mov     ebx, 0Eh
0x180017384  jmp     loc_180017456
0x180017389  xor     eax, eax
0x18001738b  xorps   xmm0, xmm0
0x18001738e  movups  xmmword ptr [rsi], xmm0
0x180017391  mov     rcx, rsi; pSecurityDescriptor
0x180017394  movups  xmmword ptr [rsi+10h], xmm0
0x180017398  lea     edx, [rax+1]; dwRevision
0x18001739b  mov     [rsi+20h], rax
0x18001739f  call    cs:__imp_InitializeSecurityDescriptor
0x1800173a5  test    eax, eax
0x1800173a7  jnz     short loc_1800173DC
0x1800173a9  call    cs:__imp_GetLastError
0x1800173af  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800173b6  mov     ebx, eax
0x1800173b8  jz      loc_180017456
0x1800173be  test    eax, eax
0x1800173c0  jle     short loc_1800173CA
0x1800173c2  movzx   eax, ax
0x1800173c5  or      eax, 80070000h
0x1800173ca  lea     rcx, aInitializingTh; "Initializing the security descriptor fa"...
0x1800173d1  mov     r8d, 4C4h
0x1800173d7  jmp     loc_180017345
0x1800173dc  mov     r8, [rsp+48h+hMem]; pDacl
0x1800173e1  xor     r9d, r9d; bDaclDefaulted
0x1800173e4  mov     rcx, rsi; pSecurityDescriptor
0x1800173e7  lea     edx, [r9+1]; bDaclPresent
0x1800173eb  call    cs:__imp_SetSecurityDescriptorDacl
0x1800173f1  test    eax, eax
0x1800173f3  jnz     short loc_180017424
0x1800173f5  call    cs:__imp_GetLastError
0x1800173fb  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017402  mov     ebx, eax
0x180017404  jz      short loc_180017456
0x180017406  test    eax, eax
0x180017408  jle     short loc_180017412
0x18001740a  movzx   eax, ax
0x18001740d  or      eax, 80070000h
0x180017412  lea     rcx, aSettingTheDacl; "Setting the DACL on the security descri"...
0x180017419  mov     r8d, 4D3h
0x18001741f  jmp     loc_180017345
0x180017424  mov     ecx, 20h ; ' '; Size
0x180017429  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001742e  mov     rdi, rax
0x180017431  test    rax, rax
0x180017434  jz      loc_18001737F
0x18001743a  mov     qword ptr [rax], 18h
0x180017441  mov     qword ptr [rax+10h], 0
0x180017449  mov     [rax+8], rsi
0x18001744d  mov     rax, [rsp+48h+hMem]
0x180017452  mov     [rdi+18h], rax
0x180017456  mov     rcx, r14; Block
0x180017459  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001745e  test    ebx, ebx
0x180017460  jnz     loc_1800172A5
0x180017466  mov     [r15], rdi
0x180017469  jmp     loc_1800172D8
0x18001746e  mov     eax, 57h ; 'W'
0x180017473  mov     rbx, [rsp+48h+arg_0]
0x180017478  mov     rsi, [rsp+48h+arg_10]
0x18001747d  add     rsp, 30h
0x180017481  pop     r15
0x180017483  pop     r14
0x180017485  pop     rdi
0x180017486  retn
```
