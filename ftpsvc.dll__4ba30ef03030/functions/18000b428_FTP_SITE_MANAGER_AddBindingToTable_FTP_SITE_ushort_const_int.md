# FTP_SITE_MANAGER::AddBindingToTable(FTP_SITE *,ushort const *,int *)

- ea: `0x18000b428`
- end: `0x18000b5f1`
- name: `?AddBindingToTable@FTP_SITE_MANAGER@@QEAAJPEAVFTP_SITE@@PEBGPEAH@Z`
- size: `457`
- prototype: `__int64 __fastcall(FTP_SITE_MANAGER *__hidden this, struct FTP_SITE *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a730`

## callees

- `0x180001210`
- `0x180001250`
- `0x18000b428`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000b5d0`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000b5d0`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000b541`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000b541`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b4b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b4b5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000b480`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000b480`
- `iisutil!PuDbgPrintError` at `0x18000b4fe`
- `iisutil!PuDbgPrintError` at `0x18000b592`
- `iisutil!PuDbgPrintError` at `0x18000b4fe`
- `iisutil!PuDbgPrintError` at `0x18000b592`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b5c6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b5c6`

## pseudocode

```c
__int64 __fastcall FTP_SITE_MANAGER::AddBindingToTable(
        FTP_SITE_MANAGER *this,
        struct FTP_SITE *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  char *v8; // rax
  volatile signed __int32 *v9; // rbx
  int v10; // edi
  int v11; // r14d
  __int64 v12; // rax
  int inserted; // eax

  *a4 = 0;
  v8 = (char *)operator new(0xD0u);
  v9 = (volatile signed __int32 *)v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 1) = 1;
    *((_DWORD *)v8 + 2) = 0;
    *((_DWORD *)v8 + 3) = 0;
    STRU::STRU((STRU *)(v8 + 16), (unsigned __int16 *)v8 + 36, 0x40u);
    *((_QWORD *)v9 + 25) = 0;
    *v9 = 1145197638;
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 25) = a2;
    v10 = STRU::Copy((STRU *)(v9 + 4), a3);
    if ( v10 >= 0 )
    {
      v11 = 0;
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      if ( (unsigned int)v12 > 1 && a3[(unsigned int)v12 - 1] != 58 )
      {
        v11 = 1;
        ++*((_DWORD *)this + 41);
      }
      inserted = CLKRHashTable::InsertRecord((char *)this + 88, v9, 0);
      if ( inserted )
      {
        if ( inserted == 1 )
        {
          *a4 = 1;
          v10 = -2147024713;
        }
        else
        {
          v10 = -2147467259;
        }
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
            1465,
            "FTP_SITE_MANAGER::AddBindingToTable",
            v10,
            "Failed to add new \"binding to site\" entry to the hash table\n");
        if ( v11 )
          --*((_DWORD *)this + 41);
      }
      else
      {
        v10 = 0;
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
        1422,
        "FTP_SITE_MANAGER::AddBindingToTable",
        v10,
        "Failed to initialize hash table entry for binding %S",
        a3);
    }
    if ( _InterlockedExchangeAdd(v9 + 1, 0xFFFFFFFF) == 1 )
    {
      *v9 = 1684173926;
      *((_QWORD *)v9 + 25) = 0;
      STRU::~STRU((void *)(v9 + 4));
      CReaderWriterLock3::~CReaderWriterLock3((CReaderWriterLock3 *)(v9 + 2));
      operator delete((void *)v9);
    }
  }
  else
  {
    return (unsigned int)-2147024888;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000b428  push    rbx
0x18000b42a  push    rbp
0x18000b42b  push    rsi
0x18000b42c  push    rdi
0x18000b42d  push    r12
0x18000b42f  push    r13
0x18000b431  push    r14
0x18000b433  push    r15
0x18000b435  sub     rsp, 48h
0x18000b439  mov     r15, r9
0x18000b43c  mov     rbp, r8
0x18000b43f  mov     rdi, rdx
0x18000b442  mov     rsi, rcx
0x18000b445  xor     r13d, r13d
0x18000b448  mov     [r9], r13d
0x18000b44b  mov     ecx, 0D0h; Size
0x18000b450  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b455  mov     rbx, rax
0x18000b458  mov     [rsp+88h+arg_18], rax
0x18000b460  test    rax, rax
0x18000b463  jz      short loc_18000B495
0x18000b465  mov     dword ptr [rax+4], 1
0x18000b46c  mov     [rax+8], r13d
0x18000b470  mov     [rax+0Ch], r13d
0x18000b474  lea     rdx, [rax+48h]
0x18000b478  lea     rcx, [rax+10h]
0x18000b47c  lea     r8d, [r13+40h]
0x18000b480  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000b486  mov     [rbx+0C8h], r13
0x18000b48d  mov     dword ptr [rbx], 44425446h
0x18000b493  jmp     short loc_18000B498
0x18000b495  mov     rbx, r13
0x18000b498  test    rbx, rbx
0x18000b49b  jnz     short loc_18000B4A7
0x18000b49d  mov     edi, 80070008h
0x18000b4a2  jmp     loc_18000B5DE
0x18000b4a7  mov     [rbx+0C8h], rdi
0x18000b4ae  mov     rdx, rbp
0x18000b4b1  lea     rcx, [rbx+10h]
0x18000b4b5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b4bb  mov     edi, eax
0x18000b4bd  test    eax, eax
0x18000b4bf  jns     short loc_18000B509
0x18000b4c1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b4c8  jz      loc_18000B5A8
0x18000b4ce  mov     [rsp+88h+var_58], rbp
0x18000b4d3  lea     rax, aFailedToInitia; "Failed to initialize hash table entry f"...
0x18000b4da  mov     [rsp+88h+var_60], rax
0x18000b4df  mov     [rsp+88h+var_68], edi
0x18000b4e3  lea     r9, aFtpSiteManager_4; "FTP_SITE_MANAGER::AddBindingToTable"
0x18000b4ea  mov     r8d, 58Eh
0x18000b4f0  lea     rdx, aInetsrvIisIisr_18; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000b4f7  mov     rcx, cs:g_pDebug
0x18000b4fe  call    cs:__imp_PuDbgPrintError
0x18000b504  jmp     loc_18000B5A8
0x18000b509  mov     r14d, r13d
0x18000b50c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b510  inc     rax
0x18000b513  cmp     [rbp+rax*2+0], r13w
0x18000b519  jnz     short loc_18000B510
0x18000b51b  mov     edi, 1
0x18000b520  cmp     eax, edi
0x18000b522  jbe     short loc_18000B537
0x18000b524  mov     eax, eax
0x18000b526  cmp     word ptr [rbp+rax*2-2], 3Ah ; ':'
0x18000b52c  jz      short loc_18000B537
0x18000b52e  mov     r14d, edi
0x18000b531  add     [rsi+0A4h], edi
0x18000b537  lea     rcx, [rsi+58h]
0x18000b53b  xor     r8d, r8d
0x18000b53e  mov     rdx, rbx
0x18000b541  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000b547  test    eax, eax
0x18000b549  jz      short loc_18000B5A5
0x18000b54b  cmp     eax, edi
0x18000b54d  jnz     short loc_18000B559
0x18000b54f  mov     [r15], edi
0x18000b552  mov     edi, 800700B7h
0x18000b557  jmp     short loc_18000B55E
0x18000b559  mov     edi, 80004005h
0x18000b55e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b565  jz      short loc_18000B598
0x18000b567  lea     rax, aFailedToAddNew; "Failed to add new \"binding to site\" e"...
0x18000b56e  mov     [rsp+88h+var_60], rax
0x18000b573  mov     [rsp+88h+var_68], edi
0x18000b577  lea     r9, aFtpSiteManager_4; "FTP_SITE_MANAGER::AddBindingToTable"
0x18000b57e  mov     r8d, 5B9h
0x18000b584  lea     rdx, aInetsrvIisIisr_18; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000b58b  mov     rcx, cs:g_pDebug
0x18000b592  call    cs:__imp_PuDbgPrintError
0x18000b598  test    r14d, r14d
0x18000b59b  jz      short loc_18000B5A8
0x18000b59d  dec     dword ptr [rsi+0A4h]
0x18000b5a3  jmp     short loc_18000B5A8
0x18000b5a5  mov     edi, r13d
0x18000b5a8  or      eax, 0FFFFFFFFh
0x18000b5ab  lock xadd [rbx+4], eax
0x18000b5b0  cmp     eax, 1
0x18000b5b3  jnz     short loc_18000B5DE
0x18000b5b5  mov     dword ptr [rbx], 64627466h
0x18000b5bb  mov     [rbx+0C8h], r13
0x18000b5c2  lea     rcx, [rbx+10h]
0x18000b5c6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000b5cc  lea     rcx, [rbx+8]
0x18000b5d0  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000b5d6  mov     rcx, rbx; Block
0x18000b5d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b5de  mov     eax, edi
0x18000b5e0  add     rsp, 48h
0x18000b5e4  pop     r15
0x18000b5e6  pop     r14
0x18000b5e8  pop     r13
0x18000b5ea  pop     r12
0x18000b5ec  pop     rdi
0x18000b5ed  pop     rsi
0x18000b5ee  pop     rbp
0x18000b5ef  pop     rbx
0x18000b5f0  retn
```
