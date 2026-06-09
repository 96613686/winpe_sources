# GetSecurityAttributesForSid(void *,_SECURITY_ATTRIBUTES * *)

- ea: `0x180017f40`
- end: `0x18001819c`
- name: `?GetSecurityAttributesForSid@@YAKPEAXPEAPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(void *, struct _SECURITY_ATTRIBUTES **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180017f40`
- `0x180018ec0`
- `0x180019230`
- `0x180019270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018103`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f9f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800180f3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800180f3`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001809b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001809b`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180018009`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180018009`

## string_xrefs

- `0x180018046`: `GetSecurityAttributesForSid`
- `0x180018054`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180018126`: `Setting the DACL on the security descriptor failed\n`
- `0x180018034`: `Setting ACE's into ACL failed.\n`
- `0x1800180d2`: `Initializing the security descriptor failed\n`

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
0x180017f40  mov     [rsp+arg_0], rbx
0x180017f45  mov     [rsp+arg_10], rsi
0x180017f4a  push    rdi
0x180017f4b  push    r14
0x180017f4d  push    r15; char
0x180017f4f  sub     rsp, 30h
0x180017f53  mov     [rsp+48h+hMem], 0
0x180017f5c  mov     r15, rdx
0x180017f5f  mov     rbx, rcx
0x180017f62  test    rdx, rdx
0x180017f65  jz      loc_180018182
0x180017f6b  cmp     qword ptr [rdx], 0
0x180017f6f  jnz     loc_180018182
0x180017f75  xor     edi, edi
0x180017f77  test    rbx, rbx
0x180017f7a  jz      loc_18001817A
0x180017f80  xor     esi, esi
0x180017f82  lea     ecx, [rsi+30h]; Size
0x180017f85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017f8a  mov     r14, rax
0x180017f8d  test    rax, rax
0x180017f90  jnz     short loc_180017FD5
0x180017f92  lea     ebx, [rsi+0Eh]
0x180017f95  mov     rcx, [rsp+48h+hMem]; hMem
0x180017f9a  test    rcx, rcx
0x180017f9d  jz      short loc_180017FB4
0x180017f9f  call    cs:__imp_LocalFree
0x180017fa6  nop     dword ptr [rax+rax+00h]
0x180017fab  mov     [rsp+48h+hMem], 0
0x180017fb4  test    rsi, rsi
0x180017fb7  jz      short loc_180017FC1
0x180017fb9  mov     rcx, rsi; Block
0x180017fbc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017fc1  test    rdi, rdi
0x180017fc4  jz      short loc_180017FCE
0x180017fc6  mov     rcx, rdi; Block
0x180017fc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017fce  mov     eax, ebx
0x180017fd0  jmp     loc_180018187
0x180017fd5  mov     [rax+0Ch], rsi
0x180017fd9  lea     r9, [rsp+48h+hMem]; NewAcl
0x180017fde  mov     [rax+14h], rsi
0x180017fe2  xor     r8d, r8d; OldAcl
0x180017fe5  mov     rdx, r14; pListOfExplicitEntries
0x180017fe8  mov     qword ptr [rax+20h], 5
0x180017ff0  mov     qword ptr [rax+4], 1
0x180017ff8  mov     [rax+1Ch], esi
0x180017ffb  lea     ecx, [r8+1]; cCountOfExplicitEntries
0x180017fff  mov     dword ptr [rax], 0C0000000h
0x180018005  mov     [rax+28h], rbx
0x180018009  call    cs:__imp_SetEntriesInAclW
0x180018010  nop     dword ptr [rax+rax+00h]
0x180018015  mov     ebx, eax
0x180018017  test    eax, eax
0x180018019  jz      short loc_180018069
0x18001801b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018022  jz      loc_18001816A
0x180018028  test    eax, eax
0x18001802a  jle     short loc_180018034
0x18001802c  movzx   eax, ax
0x18001802f  or      eax, 80070000h
0x180018034  lea     rcx, aSettingAceSInt; "Setting ACE's into ACL failed.\n"
0x18001803b  mov     r8d, 4AFh; unsigned int
0x180018041  mov     [rsp+48h+var_20], rcx; char *
0x180018046  lea     r9, aGetsecurityatt_0; "GetSecurityAttributesForSid"
0x18001804d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180018054  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001805b  mov     [rsp+48h+dwMessageId], eax; dwMessageId
0x18001805f  call    PuDbgPrintError
0x180018064  jmp     loc_18001816A
0x180018069  mov     ecx, 28h ; '('; Size
0x18001806e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018073  mov     rsi, rax
0x180018076  test    rax, rax
0x180018079  jnz     short loc_180018085
0x18001807b  mov     ebx, 0Eh
0x180018080  jmp     loc_18001816A
0x180018085  xor     eax, eax
0x180018087  xorps   xmm0, xmm0
0x18001808a  movups  xmmword ptr [rsi], xmm0
0x18001808d  mov     rcx, rsi; pSecurityDescriptor
0x180018090  movups  xmmword ptr [rsi+10h], xmm0
0x180018094  lea     edx, [rax+1]; dwRevision
0x180018097  mov     [rsi+20h], rax
0x18001809b  call    cs:__imp_InitializeSecurityDescriptor
0x1800180a2  nop     dword ptr [rax+rax+00h]
0x1800180a7  test    eax, eax
0x1800180a9  jnz     short loc_1800180E4
0x1800180ab  call    cs:__imp_GetLastError
0x1800180b2  nop     dword ptr [rax+rax+00h]
0x1800180b7  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800180be  mov     ebx, eax
0x1800180c0  jz      loc_18001816A
0x1800180c6  test    eax, eax
0x1800180c8  jle     short loc_1800180D2
0x1800180ca  movzx   eax, ax
0x1800180cd  or      eax, 80070000h
0x1800180d2  lea     rcx, aInitializingTh; "Initializing the security descriptor fa"...
0x1800180d9  mov     r8d, 4C4h
0x1800180df  jmp     loc_180018041
0x1800180e4  mov     r8, [rsp+48h+hMem]; pDacl
0x1800180e9  xor     r9d, r9d; bDaclDefaulted
0x1800180ec  mov     rcx, rsi; pSecurityDescriptor
0x1800180ef  lea     edx, [r9+1]; bDaclPresent
0x1800180f3  call    cs:__imp_SetSecurityDescriptorDacl
0x1800180fa  nop     dword ptr [rax+rax+00h]
0x1800180ff  test    eax, eax
0x180018101  jnz     short loc_180018138
0x180018103  call    cs:__imp_GetLastError
0x18001810a  nop     dword ptr [rax+rax+00h]
0x18001810f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018116  mov     ebx, eax
0x180018118  jz      short loc_18001816A
0x18001811a  test    eax, eax
0x18001811c  jle     short loc_180018126
0x18001811e  movzx   eax, ax
0x180018121  or      eax, 80070000h
0x180018126  lea     rcx, aSettingTheDacl; "Setting the DACL on the security descri"...
0x18001812d  mov     r8d, 4D3h
0x180018133  jmp     loc_180018041
0x180018138  mov     ecx, 20h ; ' '; Size
0x18001813d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018142  mov     rdi, rax
0x180018145  test    rax, rax
0x180018148  jz      loc_18001807B
0x18001814e  mov     qword ptr [rax], 18h
0x180018155  mov     qword ptr [rax+10h], 0
0x18001815d  mov     [rax+8], rsi
0x180018161  mov     rax, [rsp+48h+hMem]
0x180018166  mov     [rdi+18h], rax
0x18001816a  mov     rcx, r14; Block
0x18001816d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018172  test    ebx, ebx
0x180018174  jnz     loc_180017F95
0x18001817a  mov     [r15], rdi
0x18001817d  jmp     loc_180017FCE
0x180018182  mov     eax, 57h ; 'W'
0x180018187  mov     rbx, [rsp+48h+arg_0]
0x18001818c  mov     rsi, [rsp+48h+arg_10]
0x180018191  add     rsp, 30h
0x180018195  pop     r15
0x180018197  pop     r14
0x180018199  pop     rdi
0x18001819a  retn
```
