# PATHMAP_ENTRY::GetConfigFileMapping(CONFIG_CACHE *,PARSE_ERROR_INFO *,STRU *,void * *,int *,int *,int *)

- ea: `0x1800444b0`
- end: `0x180044615`
- name: `?GetConfigFileMapping@PATHMAP_ENTRY@@QEAAJPEAVCONFIG_CACHE@@PEAVPARSE_ERROR_INFO@@PEAVSTRU@@PEAPEAXPEAH44@Z`
- size: `357`
- prototype: `__int64 __fastcall(PATHMAP_ENTRY *__hidden this, struct CONFIG_CACHE *, struct PARSE_ERROR_INFO *, struct STRU *, PHANDLE DuplicateTokenHandle, int *, int *, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008d00`
- `0x18004d910`
- `0x18004dde0`

## callees

- `0x1800444b0`
- `0x18004461c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044598`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18004458e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18004458e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180044560`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180044560`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18004450d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18004450d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180044530`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18004453c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180044530`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18004453c`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800444ef`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800444ef`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180044505`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800445fe`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180044505`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800445fe`

## pseudocode

```c
__int64 __fastcall PATHMAP_ENTRY::GetConfigFileMapping(
        PATHMAP_ENTRY *this,
        struct CONFIG_CACHE *a2,
        struct PARSE_ERROR_INFO *a3,
        struct STRU *a4,
        PHANDLE DuplicateTokenHandle,
        int *a6,
        int *a7,
        int *a8)
{
  signed int v12; // ebx
  int v13; // ebp
  CReaderWriterLock3 *v14; // rcx
  const unsigned __int16 *v15; // rdx
  void *v16; // rcx
  signed int LastError; // eax

  if ( a2 )
  {
    v13 = 0;
    v12 = 0;
    while ( !v13 )
    {
      v14 = (PATHMAP_ENTRY *)((char *)this + 48);
      if ( (*((_BYTE *)this + 32) & 8) != 0 )
      {
        CReaderWriterLock3::ReadLock(v14);
        if ( (*((_BYTE *)this + 32) & 8) != 0 )
          v13 = 1;
        else
          CReaderWriterLock3::ReadUnlock((PATHMAP_ENTRY *)((char *)this + 48));
      }
      else
      {
        CReaderWriterLock3::WriteLock(v14);
        if ( (*((_BYTE *)this + 32) & 8) == 0 )
        {
          v12 = PATHMAP_ENTRY::Initialize(this, a2, a3);
          if ( v12 < 0 )
          {
            CReaderWriterLock3::WriteUnlock((PATHMAP_ENTRY *)((char *)this + 48));
            return (unsigned int)v12;
          }
        }
        CReaderWriterLock3::WriteUnlock((PATHMAP_ENTRY *)((char *)this + 48));
      }
    }
    if ( a4 )
    {
      v15 = &szDomain;
      if ( *((_QWORD *)this + 3) )
        v15 = (const unsigned __int16 *)*((_QWORD *)this + 3);
      v12 = STRU::Copy(a4, v15);
      if ( v12 < 0 )
        goto LABEL_29;
    }
    if ( DuplicateTokenHandle )
    {
      v16 = (void *)*((_QWORD *)this + 5);
      if ( v16 )
      {
        if ( !DuplicateToken(v16, SecurityImpersonation, DuplicateTokenHandle) )
        {
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
LABEL_29:
          CReaderWriterLock3::ReadUnlock((PATHMAP_ENTRY *)((char *)this + 48));
          return (unsigned int)v12;
        }
      }
      else
      {
        *DuplicateTokenHandle = 0;
      }
    }
    if ( a6 )
      *a6 = -__CFSHR__(*((_DWORD *)this + 8), 3);
    if ( a7 )
      *a7 = -(*((_DWORD *)this + 8) & 1);
    if ( a8 )
      *a8 = -__CFSHR__(*((_DWORD *)this + 8), 5);
    goto LABEL_29;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x1800444b0  push    rbx
0x1800444b2  push    rbp
0x1800444b3  push    rsi
0x1800444b4  push    rdi
0x1800444b5  push    r12
0x1800444b7  push    r14
0x1800444b9  push    r15
0x1800444bb  sub     rsp, 20h
0x1800444bf  mov     r14, r9
0x1800444c2  mov     r12, r8
0x1800444c5  mov     r15, rdx
0x1800444c8  mov     rdi, rcx
0x1800444cb  test    rdx, rdx
0x1800444ce  jnz     short loc_1800444DA
0x1800444d0  mov     ebx, 80070057h
0x1800444d5  jmp     loc_180044604
0x1800444da  xor     ebp, ebp
0x1800444dc  xor     ebx, ebx
0x1800444de  test    ebp, ebp
0x1800444e0  jnz     short loc_180044547
0x1800444e2  test    byte ptr [rdi+20h], 8
0x1800444e6  lea     rsi, [rdi+30h]
0x1800444ea  mov     rcx, rsi
0x1800444ed  jz      short loc_18004450D
0x1800444ef  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800444f5  test    byte ptr [rdi+20h], 8
0x1800444f9  jz      short loc_180044502
0x1800444fb  mov     ebp, 1
0x180044500  jmp     short loc_1800444DE
0x180044502  mov     rcx, rsi
0x180044505  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18004450b  jmp     short loc_1800444DE
0x18004450d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180044513  test    byte ptr [rdi+20h], 8
0x180044517  jnz     short loc_18004452D
0x180044519  mov     r8, r12; struct PARSE_ERROR_INFO *
0x18004451c  mov     rdx, r15; struct CONFIG_CACHE *
0x18004451f  mov     rcx, rdi; this
0x180044522  call    ?Initialize@PATHMAP_ENTRY@@AEAAJPEAVCONFIG_CACHE@@PEAVPARSE_ERROR_INFO@@@Z; PATHMAP_ENTRY::Initialize(CONFIG_CACHE *,PARSE_ERROR_INFO *)
0x180044527  mov     ebx, eax
0x180044529  test    eax, eax
0x18004452b  js      short loc_180044538
0x18004452d  mov     rcx, rsi
0x180044530  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180044536  jmp     short loc_1800444DE
0x180044538  lea     rcx, [rdi+30h]
0x18004453c  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180044542  jmp     loc_180044604
0x180044547  test    r14, r14
0x18004454a  jz      short loc_180044570
0x18004454c  cmp     qword ptr [rdi+18h], 0
0x180044551  lea     rdx, szDomain
0x180044558  mov     rcx, r14
0x18004455b  cmovnz  rdx, [rdi+18h]
0x180044560  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180044566  mov     ebx, eax
0x180044568  test    eax, eax
0x18004456a  js      loc_1800445FA
0x180044570  mov     rax, [rsp+58h+DuplicateTokenHandle]
0x180044578  test    rax, rax
0x18004457b  jz      short loc_1800445B6
0x18004457d  mov     rcx, [rdi+28h]; ExistingTokenHandle
0x180044581  test    rcx, rcx
0x180044584  jz      short loc_1800445AF
0x180044586  mov     r8, rax; DuplicateTokenHandle
0x180044589  mov     edx, 2; ImpersonationLevel
0x18004458e  call    cs:__imp_DuplicateToken
0x180044594  test    eax, eax
0x180044596  jnz     short loc_1800445B6
0x180044598  call    cs:__imp_GetLastError
0x18004459e  mov     ebx, eax
0x1800445a0  test    eax, eax
0x1800445a2  jle     short loc_1800445FA
0x1800445a4  movzx   ebx, ax
0x1800445a7  or      ebx, 80070000h
0x1800445ad  jmp     short loc_1800445FA
0x1800445af  mov     qword ptr [rax], 0
0x1800445b6  mov     rcx, [rsp+58h+arg_28]
0x1800445be  test    rcx, rcx
0x1800445c1  jz      short loc_1800445CD
0x1800445c3  mov     eax, [rdi+20h]
0x1800445c6  shr     eax, 3
0x1800445c9  sbb     eax, eax
0x1800445cb  mov     [rcx], eax
0x1800445cd  mov     rcx, [rsp+58h+arg_30]
0x1800445d5  test    rcx, rcx
0x1800445d8  jz      short loc_1800445E3
0x1800445da  mov     eax, [rdi+20h]
0x1800445dd  shr     eax, 1
0x1800445df  sbb     eax, eax
0x1800445e1  mov     [rcx], eax
0x1800445e3  mov     rcx, [rsp+58h+arg_38]
0x1800445eb  test    rcx, rcx
0x1800445ee  jz      short loc_1800445FA
0x1800445f0  mov     eax, [rdi+20h]
0x1800445f3  shr     eax, 5
0x1800445f6  sbb     eax, eax
0x1800445f8  mov     [rcx], eax
0x1800445fa  lea     rcx, [rdi+30h]
0x1800445fe  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180044604  mov     eax, ebx
0x180044606  add     rsp, 20h
0x18004460a  pop     r15
0x18004460c  pop     r14
0x18004460e  pop     r12
0x180044610  pop     rdi
0x180044611  pop     rsi
0x180044612  pop     rbp
0x180044613  pop     rbx
0x180044614  retn
```
