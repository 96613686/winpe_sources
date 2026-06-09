# FTP_ENDPOINT_MANAGER::GetEndpoint(sockaddr_storage *,ulong,FTP_ENDPOINT * *)

- ea: `0x180031f80`
- end: `0x1800320fb`
- name: `?GetEndpoint@FTP_ENDPOINT_MANAGER@@QEAAJPEAUsockaddr_storage@@KPEAPEAVFTP_ENDPOINT@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(FTP_ENDPOINT_MANAGER *__hidden this, struct sockaddr_storage *, unsigned int, struct FTP_ENDPOINT **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18000a730`

## callees

- `0x180001210`
- `0x18003192c`
- `0x180031d44`
- `0x180031df8`
- `0x180031f80`
- `0x1800321fc`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180032037`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180032037`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180032080`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180032080`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180032046`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180032046`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180031ff3`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18003206f`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180031ff3`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18003206f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180031fd4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180031fd4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800320a5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800320a5`

## pseudocode

```c
__int64 __fastcall FTP_ENDPOINT_MANAGER::GetEndpoint(
        FTP_ENDPOINT_MANAGER *this,
        struct sockaddr_storage *a2,
        unsigned int a3,
        struct FTP_ENDPOINT **a4)
{
  FTP_ENDPOINT *v8; // rax
  volatile signed __int32 *v9; // rbx
  int inserted; // edi
  int updated; // edi
  FTP_ENDPOINT *v13; // [rsp+20h] [rbp-118h] BYREF
  _BYTE v14[56]; // [rsp+28h] [rbp-110h] BYREF
  unsigned __int16 v15[64]; // [rsp+60h] [rbp-D8h] BYREF

  memset_0(v15, 0, sizeof(v15));
  STRU::STRU((STRU *)v14, v15, 0x40u);
  v13 = 0;
  if ( !(unsigned int)CLKRHashTable::FindKey((char *)this + 8, a2, &v13) )
  {
    v9 = (volatile signed __int32 *)v13;
LABEL_13:
    _InterlockedIncrement(v9 + 2);
    updated = FTP_ENDPOINT::ListenAndUpdateSettings((FTP_ENDPOINT *)v9, a3);
    if ( updated >= 0 )
    {
      updated = 0;
      *a4 = (struct FTP_ENDPOINT *)v9;
      goto LABEL_10;
    }
    goto LABEL_8;
  }
  v8 = (FTP_ENDPOINT *)operator new(0x3F8u);
  v13 = v8;
  if ( !v8 || (v9 = (volatile signed __int32 *)FTP_ENDPOINT::FTP_ENDPOINT(v8, this, a2)) == 0 )
  {
    updated = -2147024888;
    goto LABEL_10;
  }
  CReaderWriterLock3::WriteLock((FTP_ENDPOINT_MANAGER *)((char *)this + 80));
  inserted = CLKRHashTable::InsertRecord((char *)this + 8, v9, 0);
  if ( inserted == 1 )
  {
    FTP_ENDPOINT::DereferenceFtpEndpoint((FTP_ENDPOINT *)v9);
    v13 = 0;
    inserted = CLKRHashTable::FindKey((char *)this + 8, a2, &v13);
    v9 = (volatile signed __int32 *)v13;
  }
  CReaderWriterLock3::WriteUnlock((FTP_ENDPOINT_MANAGER *)((char *)this + 80));
  if ( !inserted )
    goto LABEL_13;
  updated = -2147467259;
LABEL_8:
  if ( v9 )
    FTP_ENDPOINT_MANAGER::ReleaseEndpoint(this, (struct FTP_ENDPOINT *)v9);
LABEL_10:
  STRU::~STRU(v14);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180031f80  push    rbx
0x180031f82  push    rbp
0x180031f83  push    rsi
0x180031f84  push    rdi
0x180031f85  push    r12
0x180031f87  push    r13
0x180031f89  push    r14
0x180031f8b  push    r15
0x180031f8d  sub     rsp, 0F8h
0x180031f94  mov     rax, cs:__security_cookie
0x180031f9b  xor     rax, rsp
0x180031f9e  mov     [rsp+138h+var_58], rax
0x180031fa6  mov     r12, r9
0x180031fa9  mov     r13d, r8d
0x180031fac  mov     r14, rdx
0x180031faf  mov     rsi, rcx
0x180031fb2  xor     edx, edx; Val
0x180031fb4  mov     r8d, 80h; Size
0x180031fba  lea     rcx, [rsp+138h+var_D8]; void *
0x180031fbf  call    memset_0
0x180031fc4  mov     r8d, 40h ; '@'
0x180031fca  lea     rdx, [rsp+138h+var_D8]
0x180031fcf  lea     rcx, [rsp+138h+var_110]
0x180031fd4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180031fda  nop
0x180031fdb  lea     r15, [rsi+8]
0x180031fdf  mov     [rsp+138h+var_118], 0
0x180031fe8  lea     r8, [rsp+138h+var_118]
0x180031fed  mov     rdx, r14
0x180031ff0  mov     rcx, r15
0x180031ff3  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180031ff9  test    eax, eax
0x180031ffb  jz      loc_1800320D8
0x180032001  mov     ecx, 3F8h; Size
0x180032006  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003200b  mov     [rsp+138h+var_118], rax
0x180032010  test    rax, rax
0x180032013  jz      loc_1800320D1
0x180032019  mov     r8, r14; struct sockaddr_storage *
0x18003201c  mov     rdx, rsi; struct FTP_ENDPOINT_MANAGER *
0x18003201f  mov     rcx, rax; this
0x180032022  call    ??0FTP_ENDPOINT@@QEAA@PEAVFTP_ENDPOINT_MANAGER@@PEAUsockaddr_storage@@@Z; FTP_ENDPOINT::FTP_ENDPOINT(FTP_ENDPOINT_MANAGER *,sockaddr_storage *)
0x180032027  mov     rbx, rax
0x18003202a  test    rax, rax
0x18003202d  jz      loc_1800320D1
0x180032033  lea     rcx, [rsi+50h]
0x180032037  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18003203d  xor     r8d, r8d
0x180032040  mov     rdx, rbx
0x180032043  mov     rcx, r15
0x180032046  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18003204c  mov     edi, eax
0x18003204e  cmp     eax, 1
0x180032051  jnz     short loc_18003207C
0x180032053  mov     rcx, rbx; this
0x180032056  call    ?DereferenceFtpEndpoint@FTP_ENDPOINT@@QEAAXXZ; FTP_ENDPOINT::DereferenceFtpEndpoint(void)
0x18003205b  mov     [rsp+138h+var_118], 0
0x180032064  lea     r8, [rsp+138h+var_118]
0x180032069  mov     rdx, r14
0x18003206c  mov     rcx, r15
0x18003206f  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180032075  mov     edi, eax
0x180032077  mov     rbx, [rsp+138h+var_118]
0x18003207c  lea     rcx, [rsi+50h]
0x180032080  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180032086  test    edi, edi
0x180032088  jz      short loc_1800320DD
0x18003208a  mov     edi, 80004005h
0x18003208f  test    rbx, rbx
0x180032092  jz      short loc_1800320A0
0x180032094  mov     rdx, rbx; struct FTP_ENDPOINT *
0x180032097  mov     rcx, rsi; this
0x18003209a  call    ?ReleaseEndpoint@FTP_ENDPOINT_MANAGER@@QEAAXPEAVFTP_ENDPOINT@@@Z; FTP_ENDPOINT_MANAGER::ReleaseEndpoint(FTP_ENDPOINT *)
0x18003209f  nop
0x1800320a0  lea     rcx, [rsp+138h+var_110]
0x1800320a5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800320ab  mov     eax, edi
0x1800320ad  mov     rcx, [rsp+138h+var_58]
0x1800320b5  xor     rcx, rsp; StackCookie
0x1800320b8  call    __security_check_cookie
0x1800320bd  add     rsp, 0F8h
0x1800320c4  pop     r15
0x1800320c6  pop     r14
0x1800320c8  pop     r13
0x1800320ca  pop     r12
0x1800320cc  pop     rdi
0x1800320cd  pop     rsi
0x1800320ce  pop     rbp
0x1800320cf  pop     rbx
0x1800320d0  retn
0x1800320d1  mov     edi, 80070008h
0x1800320d6  jmp     short loc_1800320A0
0x1800320d8  mov     rbx, [rsp+138h+var_118]
0x1800320dd  lock inc dword ptr [rbx+8]
0x1800320e1  mov     edx, r13d; unsigned int
0x1800320e4  mov     rcx, rbx; this
0x1800320e7  call    ?ListenAndUpdateSettings@FTP_ENDPOINT@@QEAAJK@Z; FTP_ENDPOINT::ListenAndUpdateSettings(ulong)
0x1800320ec  mov     edi, eax
0x1800320ee  test    eax, eax
0x1800320f0  js      short loc_18003208F
0x1800320f2  xor     edi, edi
0x1800320f4  mov     [r12], rbx
0x1800320f8  jmp     short loc_1800320A0
```
