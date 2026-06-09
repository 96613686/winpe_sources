# GetRootDomEntitySid

- ea: `0x18002ffbc`
- end: `0x1800300f2`
- name: `GetRootDomEntitySid`
- size: `310`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030ec0`
- `0x180033314`
- `0x180033b78`

## callees

- `0x180008400`
- `0x180012450`
- `0x18002a290`
- `0x18002ffbc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030035`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030035`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300dc`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180030054`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180030054`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003008e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003009c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800300b1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003008e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003009c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800300b1`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180030063`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180030063`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180030028`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180030028`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180030017`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180030017`

## pseudocode

```c
__int64 __fastcall GetRootDomEntitySid(_QWORD *a1, DWORD a2)
{
  int SidFromDomain; // eax
  unsigned int v5; // ebx
  HLOCAL v6; // rdi
  unsigned int v7; // ecx
  int v8; // edx
  DWORD v9; // ebx
  DWORD SidLengthRequired; // eax
  struct _SID_IDENTIFIER_AUTHORITY *SidIdentifierAuthority; // rax
  DWORD v12; // r14d
  DWORD v13; // ebp
  DWORD v14; // ebx
  PDWORD SidSubAuthority; // rax
  PDWORD v16; // rax
  PSID pSid; // [rsp+60h] [rbp+8h] BYREF

  *a1 = 0;
  pSid = 0;
  SidFromDomain = myGetSidFromDomain(0, &pSid);
  v5 = SidFromDomain;
  if ( SidFromDomain )
  {
    v6 = 0;
    if ( SidFromDomain > 0 )
      v5 = (unsigned __int16)SidFromDomain | 0x80070000;
    v7 = 459014952;
    goto LABEL_5;
  }
  v9 = *GetSidSubAuthorityCount(pSid);
  SidLengthRequired = GetSidLengthRequired(v9 + 1);
  v6 = LocalAlloc(0x40u, SidLengthRequired);
  if ( !v6 )
  {
    v5 = -2147024882;
    v7 = 459801384;
LABEL_5:
    v8 = v5;
LABEL_6:
    CSPrintErrorLineFile(v7, v8);
    goto LABEL_14;
  }
  SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
  if ( !InitializeSid(v6, SidIdentifierAuthority, v9 + 1) )
  {
    v5 = myHLastError();
    v8 = v5;
    v7 = 460391208;
    goto LABEL_6;
  }
  v12 = 0;
  v13 = v9;
  if ( (_BYTE)v9 )
  {
    do
    {
      v14 = *GetSidSubAuthority(pSid, v12);
      SidSubAuthority = GetSidSubAuthority(v6, v12++);
      *SidSubAuthority = v14;
    }
    while ( v12 < v13 );
  }
  v16 = GetSidSubAuthority(v6, v13);
  *a1 = v6;
  v6 = 0;
  v5 = 0;
  *v16 = a2;
LABEL_14:
  if ( pSid )
    LocalFree(pSid);
  if ( v6 )
    LocalFree(v6);
  return v5;
}

```

## disassembly

```asm
0x18002ffbc  push    rbx
0x18002ffbe  push    rbp
0x18002ffbf  push    rdi
0x18002ffc0  push    r12
0x18002ffc2  push    r14
0x18002ffc4  push    r15
0x18002ffc6  sub     rsp, 28h
0x18002ffca  mov     r12d, edx
0x18002ffcd  mov     qword ptr [rcx], 0
0x18002ffd4  mov     r15, rcx
0x18002ffd7  mov     [rsp+58h+pSid], 0
0x18002ffe0  lea     rdx, [rsp+58h+pSid]; void **
0x18002ffe5  xor     ecx, ecx; unsigned __int16 *
0x18002ffe7  call    ?myGetSidFromDomain@@YAKPEAGPEAPEAX@Z; myGetSidFromDomain(ushort *,void * *)
0x18002ffec  mov     ebx, eax
0x18002ffee  test    eax, eax
0x18002fff0  jz      short loc_180030012
0x18002fff2  xor     edi, edi
0x18002fff4  test    eax, eax
0x18002fff6  jle     short loc_180030001
0x18002fff8  movzx   ebx, ax
0x18002fffb  or      ebx, 80070000h
0x180030001  mov     ecx, 1B5C0328h; unsigned int
0x180030006  mov     edx, ebx; int
0x180030008  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003000d  jmp     loc_1800300C1
0x180030012  mov     rcx, [rsp+58h+pSid]; pSid
0x180030017  call    cs:__imp_GetSidSubAuthorityCount
0x18003001d  movzx   ebx, byte ptr [rax]
0x180030020  lea     eax, [rbx+1]
0x180030023  mov     cl, al; nSubAuthorityCount
0x180030025  mov     bpl, al
0x180030028  call    cs:__imp_GetSidLengthRequired
0x18003002e  mov     edx, eax; uBytes
0x180030030  mov     ecx, 40h ; '@'; uFlags
0x180030035  call    cs:__imp_LocalAlloc
0x18003003b  mov     rdi, rax
0x18003003e  test    rax, rax
0x180030041  jnz     short loc_18003004F
0x180030043  mov     ebx, 8007000Eh
0x180030048  mov     ecx, 1B680328h
0x18003004d  jmp     short loc_180030006
0x18003004f  mov     rcx, [rsp+58h+pSid]; pSid
0x180030054  call    cs:__imp_GetSidIdentifierAuthority
0x18003005a  mov     r8b, bpl; nSubAuthorityCount
0x18003005d  mov     rcx, rdi; Sid
0x180030060  mov     rdx, rax; pIdentifierAuthority
0x180030063  call    cs:__imp_InitializeSid
0x180030069  test    eax, eax
0x18003006b  jnz     short loc_18003007D
0x18003006d  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180030072  mov     ebx, eax
0x180030074  mov     edx, eax
0x180030076  mov     ecx, 1B710328h
0x18003007b  jmp     short loc_180030008
0x18003007d  xor     r14d, r14d
0x180030080  mov     ebp, ebx
0x180030082  test    bl, bl
0x180030084  jz      short loc_1800300AC
0x180030086  mov     rcx, [rsp+58h+pSid]; pSid
0x18003008b  mov     edx, r14d; nSubAuthority
0x18003008e  call    cs:__imp_GetSidSubAuthority
0x180030094  mov     edx, r14d; nSubAuthority
0x180030097  mov     rcx, rdi; pSid
0x18003009a  mov     ebx, [rax]
0x18003009c  call    cs:__imp_GetSidSubAuthority
0x1800300a2  inc     r14d
0x1800300a5  mov     [rax], ebx
0x1800300a7  cmp     r14d, ebp
0x1800300aa  jb      short loc_180030086
0x1800300ac  mov     edx, ebp; nSubAuthority
0x1800300ae  mov     rcx, rdi; pSid
0x1800300b1  call    cs:__imp_GetSidSubAuthority
0x1800300b7  mov     [r15], rdi
0x1800300ba  xor     edi, edi
0x1800300bc  xor     ebx, ebx
0x1800300be  mov     [rax], r12d
0x1800300c1  cmp     [rsp+58h+pSid], 0
0x1800300c7  jz      short loc_1800300D4
0x1800300c9  mov     rcx, [rsp+58h+pSid]; hMem
0x1800300ce  call    cs:__imp_LocalFree
0x1800300d4  test    rdi, rdi
0x1800300d7  jz      short loc_1800300E2
0x1800300d9  mov     rcx, rdi; hMem
0x1800300dc  call    cs:__imp_LocalFree
0x1800300e2  mov     eax, ebx
0x1800300e4  add     rsp, 28h
0x1800300e8  pop     r15
0x1800300ea  pop     r14
0x1800300ec  pop     r12
0x1800300ee  pop     rdi
0x1800300ef  pop     rbp
0x1800300f0  pop     rbx
0x1800300f1  retn
```
