# FTCache::MatchSid(_SID *,uchar *,_UNICODE_STRING *,void * *)

- ea: `0x18002970c`
- end: `0x180029921`
- name: `?MatchSid@FTCache@@AEAAJPEAU_SID@@PEAEPEAU_UNICODE_STRING@@PEAPEAX@Z`
- size: `533`
- prototype: `int(FTCache *__hidden this, struct _SID *, unsigned __int8 *, struct _UNICODE_STRING *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002901c`

## callees

- `0x180001670`
- `0x18000fd18`
- `0x18000fd40`
- `0x180021aa8`
- `0x180021ad4`
- `0x180022210`
- `0x180022278`
- `0x18002970c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002976a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002976a`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180029760`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180029760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029840`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029854`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029840`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029854`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800297d4`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800297d4`

## pseudocode

```c
__int64 __fastcall FTCache::MatchSid(
        FTCache *this,
        struct _SID *a2,
        unsigned __int8 *a3,
        struct _UNICODE_STRING *a4,
        void **a5)
{
  DWORD LastError; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rax
  char *v11; // r14
  char *i; // rbx
  __int64 v13; // rax
  FTCache::TLN_ENTRY *v14; // rcx
  __int64 v16; // rdx
  void *v17; // rbx
  DWORD cbDomainSid; // [rsp+20h] [rbp-448h] BYREF
  _BYTE *Buffer; // [rsp+28h] [rbp-440h] BYREF
  _BYTE pDomainSid[1024]; // [rsp+30h] [rbp-438h] BYREF

  cbDomainSid = 1024;
  Buffer = pDomainSid;
  if ( GetWindowsAccountDomainSid(a2, pDomainSid, &cbDomainSid) )
  {
    v10 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 216), &Buffer);
    if ( !v10 )
    {
LABEL_23:
      v9 = -1073741198;
      goto LABEL_24;
    }
    v11 = (char *)(v10 + 2);
    for ( i = (char *)v10[2]; ; i = *(char **)i )
    {
      if ( i == v11 )
        goto LABEL_23;
      v13 = *((_QWORD *)i + 10);
      if ( v13 && (i[112] & 3) == 0 && !*(_BYTE *)(v13 + 40) )
      {
        v14 = *(FTCache::TLN_ENTRY **)(v13 + 56);
        if ( v14 )
        {
          if ( !FTCache::TLN_ENTRY::Enabled(v14) )
            continue;
        }
        else if ( *(_WORD *)(v13 + 72) )
        {
          continue;
        }
        if ( !FTCache::TDO_ENTRY::Excludes(*((FTCache::TDO_ENTRY **)i + 9), *((const struct _UNICODE_STRING **)i + 12)) )
        {
          v16 = *((_QWORD *)i + 9);
          v17 = *(void **)(v16 + 16);
          *a3 = *(_BYTE *)(v16 + 92);
          if ( !v16 || !v17 )
            goto LABEL_23;
          if ( a4 && !FtcCopyUnicodeString(a4, (PCUNICODE_STRING)v16, 0) )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
            v9 = -1073741670;
            goto LABEL_25;
          }
          if ( !a5 || FtcCopySid(a5, v17) )
            return 0;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
          v9 = -1073741670;
          goto LABEL_24;
        }
      }
    }
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, LastError);
  switch ( v9 )
  {
    case 0x57u:
LABEL_8:
      v9 = -1073741811;
      break;
    case 0x7Au:
      v9 = -2147483643;
      break;
    case 0x4E9u:
      v9 = -1073741704;
      break;
    case 0x539u:
      goto LABEL_8;
    default:
      break;
  }
LABEL_24:
  if ( a4 )
  {
LABEL_25:
    LocalFree(a4->Buffer);
    *a4 = 0;
  }
  if ( a5 )
  {
    LocalFree(*a5);
    *a5 = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18002970c  push    rbx
0x18002970e  push    rsi
0x18002970f  push    rdi
0x180029710  push    r14
0x180029712  push    r15
0x180029714  sub     rsp, 440h
0x18002971b  mov     rax, cs:__security_cookie
0x180029722  xor     rax, rsp
0x180029725  mov     [rsp+468h+var_38], rax
0x18002972d  mov     rdi, [rsp+468h+arg_20]
0x180029735  mov     rbx, rcx
0x180029738  mov     rax, rdx
0x18002973b  mov     [rsp+468h+cbDomainSid], 400h
0x180029743  lea     rcx, [rsp+468h+pDomainSid]
0x180029748  mov     r15, r8
0x18002974b  mov     [rsp+468h+Buffer], rcx
0x180029750  lea     r8, [rsp+468h+cbDomainSid]; cbDomainSid
0x180029755  mov     rcx, rax; pSid
0x180029758  lea     rdx, [rsp+468h+pDomainSid]; pDomainSid
0x18002975d  mov     rsi, r9
0x180029760  call    cs:__imp_GetWindowsAccountDomainSid
0x180029766  test    eax, eax
0x180029768  jnz     short loc_1800297C8
0x18002976a  call    cs:__imp_GetLastError
0x180029770  mov     ebx, eax
0x180029772  mov     rcx, cs:WPP_GLOBAL_Control
0x180029779  test    byte ptr [rcx+1Ch], 8
0x18002977d  jz      short loc_180029797
0x18002977f  mov     rcx, [rcx+10h]
0x180029783  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002978a  mov     edx, 0DCh
0x18002978f  mov     r9d, eax
0x180029792  call    WPP_SF_d
0x180029797  mov     eax, ebx
0x180029799  sub     eax, 57h ; 'W'
0x18002979c  jz      short loc_1800297B3
0x18002979e  sub     eax, 23h ; '#'
0x1800297a1  jz      short loc_1800297C1
0x1800297a3  sub     eax, 46Fh
0x1800297a8  jz      short loc_1800297BA
0x1800297aa  cmp     eax, 50h ; 'P'
0x1800297ad  jnz     loc_180029837
0x1800297b3  mov     ebx, 0C000000Dh
0x1800297b8  jmp     short loc_180029837
0x1800297ba  mov     ebx, 0C0000078h
0x1800297bf  jmp     short loc_180029837
0x1800297c1  mov     ebx, 80000005h
0x1800297c6  jmp     short loc_180029837
0x1800297c8  lea     rcx, [rbx+0D8h]; Table
0x1800297cf  lea     rdx, [rsp+468h+Buffer]; Buffer
0x1800297d4  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1800297da  test    rax, rax
0x1800297dd  jz      short loc_180029832
0x1800297df  lea     r14, [rax+10h]
0x1800297e3  mov     rbx, [r14]
0x1800297e6  jmp     short loc_18002982D
0x1800297e8  mov     rax, [rbx+50h]
0x1800297ec  test    rax, rax
0x1800297ef  jz      short loc_18002982A
0x1800297f1  test    byte ptr [rbx+70h], 3
0x1800297f5  jnz     short loc_18002982A
0x1800297f7  cmp     byte ptr [rax+28h], 0
0x1800297fb  jnz     short loc_18002982A
0x1800297fd  mov     rcx, [rax+38h]; this
0x180029801  test    rcx, rcx
0x180029804  jz      short loc_180029811
0x180029806  call    ?Enabled@TLN_ENTRY@FTCache@@QEAAEXZ; FTCache::TLN_ENTRY::Enabled(void)
0x18002980b  test    al, al
0x18002980d  jz      short loc_18002982A
0x18002980f  jmp     short loc_180029819
0x180029811  movzx   eax, word ptr [rax+48h]
0x180029815  test    eax, eax
0x180029817  jnz     short loc_18002982A
0x180029819  mov     rdx, [rbx+60h]; struct _UNICODE_STRING *
0x18002981d  mov     rcx, [rbx+48h]; this
0x180029821  call    ?Excludes@TDO_ENTRY@FTCache@@QEAAEPEBU_UNICODE_STRING@@@Z; FTCache::TDO_ENTRY::Excludes(_UNICODE_STRING const *)
0x180029826  test    al, al
0x180029828  jz      short loc_180029882
0x18002982a  mov     rbx, [rbx]
0x18002982d  cmp     rbx, r14
0x180029830  jnz     short loc_1800297E8
0x180029832  mov     ebx, 0C0000272h
0x180029837  test    rsi, rsi
0x18002983a  jz      short loc_18002984C
0x18002983c  mov     rcx, [rsi+8]; hMem
0x180029840  call    cs:__imp_LocalFree
0x180029846  xorps   xmm0, xmm0
0x180029849  movups  xmmword ptr [rsi], xmm0
0x18002984c  test    rdi, rdi
0x18002984f  jz      short loc_180029861
0x180029851  mov     rcx, [rdi]; hMem
0x180029854  call    cs:__imp_LocalFree
0x18002985a  mov     qword ptr [rdi], 0
0x180029861  mov     eax, ebx
0x180029863  mov     rcx, [rsp+468h+var_38]
0x18002986b  xor     rcx, rsp; StackCookie
0x18002986e  call    __security_check_cookie
0x180029873  add     rsp, 440h
0x18002987a  pop     r15
0x18002987c  pop     r14
0x18002987e  pop     rdi
0x18002987f  pop     rsi
0x180029880  pop     rbx
0x180029881  retn
0x180029882  mov     rdx, [rbx+48h]; SourceString
0x180029886  mov     al, [rdx+5Ch]
0x180029889  mov     rbx, [rdx+10h]
0x18002988d  mov     [r15], al
0x180029890  test    rdx, rdx
0x180029893  jz      short loc_180029832
0x180029895  test    rbx, rbx
0x180029898  jz      short loc_180029832
0x18002989a  test    rsi, rsi
0x18002989d  jz      short loc_1800298DA
0x18002989f  xor     r8d, r8d; unsigned __int16 *
0x1800298a2  mov     rcx, rsi; DestinationString
0x1800298a5  call    ?FtcCopyUnicodeString@@YAEPEAU_UNICODE_STRING@@PEBU1@PEAG@Z; FtcCopyUnicodeString(_UNICODE_STRING *,_UNICODE_STRING const *,ushort *)
0x1800298aa  test    al, al
0x1800298ac  jnz     short loc_1800298DA
0x1800298ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800298b5  test    byte ptr [rcx+1Ch], 8
0x1800298b9  jz      short loc_1800298D0
0x1800298bb  mov     rcx, [rcx+10h]
0x1800298bf  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800298c6  mov     edx, 0DDh
0x1800298cb  call    WPP_SF_
0x1800298d0  mov     ebx, 0C000009Ah
0x1800298d5  jmp     loc_18002983C
0x1800298da  test    rdi, rdi
0x1800298dd  jz      short loc_18002991A
0x1800298df  mov     rdx, rbx; void *
0x1800298e2  mov     rcx, rdi; void **
0x1800298e5  call    ?FtcCopySid@@YAEPEAPEAXPEAX@Z; FtcCopySid(void * *,void *)
0x1800298ea  test    al, al
0x1800298ec  jnz     short loc_18002991A
0x1800298ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800298f5  test    byte ptr [rcx+1Ch], 8
0x1800298f9  jz      short loc_180029910
0x1800298fb  mov     rcx, [rcx+10h]
0x1800298ff  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180029906  mov     edx, 0DEh
0x18002990b  call    WPP_SF_
0x180029910  mov     ebx, 0C000009Ah
0x180029915  jmp     loc_180029837
0x18002991a  xor     ebx, ebx
0x18002991c  jmp     loc_180029861
```
