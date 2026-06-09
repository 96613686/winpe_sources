# W3_RESTRICTION_LIST::IsImageEnabled(ushort const *,int,int *,INativeSectionException * *,IHttpContext *)

- ea: `0x1800069b4`
- end: `0x180006be8`
- name: `?IsImageEnabled@W3_RESTRICTION_LIST@@SAJPEBGHPEAHPEAPEAVINativeSectionException@@PEAVIHttpContext@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, int *, struct INativeSectionException **, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000337c`

## callees

- `0x180001008`
- `0x180001048`
- `0x1800066a8`
- `0x1800069b4`
- `0x180006bf0`
- `0x180008010`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006a0b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006a0b`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180006a79`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180006a79`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180006abf`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180006abf`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180006a9a`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180006a9a`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800069d7`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006ad0`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800069d7`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006ad0`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180006af7`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180006af7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006b19`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006b19`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800069fc`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180006b41`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800069fc`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180006b41`

## pseudocode

```c
__int64 __fastcall W3_RESTRICTION_LIST::IsImageEnabled(
        const unsigned __int16 *a1,
        __int64 a2,
        int *a3,
        struct INativeSectionException **a4,
        struct IHttpContext *a5)
{
  void *v8; // rcx
  int v9; // edi
  CLKRHashTable *v10; // rax
  W3_RESTRICTION_LIST *v11; // rbx
  char *v12; // rbx
  int v13; // edi
  int (__fastcall ***v15)(_QWORD, GUID **); // rax
  struct IHttpTraceContext *v16; // rax
  const struct _GUID *v17; // rdx
  void *Block; // [rsp+50h] [rbp-58h] BYREF
  GUID *v19; // [rsp+58h] [rbp-50h] BYREF
  __int128 v20; // [rsp+60h] [rbp-48h]

  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
  v8 = W3_RESTRICTION_LIST::sm_pRestrictionList;
  if ( W3_RESTRICTION_LIST::sm_pRestrictionList )
  {
LABEL_10:
    Block = 0;
    if ( (unsigned int)CLKRHashTable::FindKey(v8, a1, &Block) )
    {
      v13 = *((_DWORD *)W3_RESTRICTION_LIST::sm_pRestrictionList + 18);
    }
    else
    {
      v12 = (char *)Block;
      v13 = *((_DWORD *)Block + 16);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block, 0xFFFFFFFF) == 1 )
      {
        STRU::~STRU((STRU *)(v12 + 8));
        operator delete(v12);
      }
    }
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
    if ( !v13 )
    {
      v15 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a5 + 272LL))(a5);
      v19 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v20 = 0;
      if ( (**v15)(v15, &v19) >= 0 && DWORD2(v20) && DWORD1(v20) >= 3 && ((_DWORD)v20 == 4 || (v20 & 4) != 0) )
      {
        v16 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a5 + 272LL))(a5);
        IISSecurityEvents::SECURITY_DENIED_BY_CGI_RESTRICTION::RaiseEvent(v16, v17, a1);
      }
    }
    *a3 = v13;
    return 0;
  }
  else
  {
    while ( 1 )
    {
      CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
      v9 = 0;
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
      if ( !W3_RESTRICTION_LIST::sm_pRestrictionList )
      {
        v10 = (CLKRHashTable *)operator new(0x58u);
        v11 = v10;
        if ( v10 )
        {
          CLKRHashTable::CLKRHashTable(
            v10,
            "W3_RESTRICTION_LIST",
            (unsigned __int64 (*)(const void *))CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,unsigned short const *,CLKRHashTable>::_ExtractKey,
            (unsigned int (*)(unsigned __int64))CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
            (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,unsigned short const *,CLKRHashTable>::_EqualKeys,
            (void (*)(const void *, int))CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,unsigned short const *,CLKRHashTable>::_AddRefRecord,
            4.0,
            1u,
            0,
            0);
          *((_DWORD *)v11 + 20) = 1;
          v9 = W3_RESTRICTION_LIST::Create(v11, a4);
          if ( v9 >= 0 )
          {
            W3_RESTRICTION_LIST::sm_pRestrictionList = v11;
          }
          else
          {
            CLKRHashTable::~CLKRHashTable(v11);
            operator delete(v11);
          }
        }
        else
        {
          v9 = -2147024888;
        }
      }
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
      if ( v9 < 0 )
        return (unsigned int)v9;
      CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
      v8 = W3_RESTRICTION_LIST::sm_pRestrictionList;
      if ( W3_RESTRICTION_LIST::sm_pRestrictionList )
        goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x1800069b4  push    rbx
0x1800069b6  push    rbp
0x1800069b7  push    rsi
0x1800069b8  push    rdi
0x1800069b9  push    r14
0x1800069bb  sub     rsp, 80h
0x1800069c2  mov     rsi, rcx
0x1800069c5  movaps  [rsp+0A8h+var_38], xmm6
0x1800069ca  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x1800069d1  mov     rbp, r9
0x1800069d4  mov     r14, r8
0x1800069d7  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800069dd  mov     rcx, cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x1800069e4  test    rcx, rcx
0x1800069e7  jnz     loc_180006AE6
0x1800069ed  movsd   xmm6, cs:__real@4010000000000000
0x1800069f5  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x1800069fc  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180006a02  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180006a09  xor     edi, edi
0x180006a0b  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180006a11  cmp     cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA, rdi; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x180006a18  jnz     loc_180006AB8
0x180006a1e  lea     ecx, [rdi+58h]; Size
0x180006a21  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006a26  mov     rbx, rax
0x180006a29  test    rax, rax
0x180006a2c  jz      loc_180006AB3
0x180006a32  mov     [rsp+0A8h+var_60], dil
0x180006a37  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VW3_RESTRICTION_LIST@@VW3_IMAGE_RECORD@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180006a3e  mov     [rsp+0A8h+var_68], edi
0x180006a42  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VW3_RESTRICTION_LIST@@VW3_IMAGE_RECORD@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180006a49  mov     [rsp+0A8h+var_70], 1
0x180006a51  lea     r8, ?_ExtractKey@?$CTypedHashTable@VW3_RESTRICTION_LIST@@VW3_IMAGE_RECORD@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x180006a58  movsd   [rsp+0A8h+var_78], xmm6
0x180006a5e  lea     rdx, aW3RestrictionL; "W3_RESTRICTION_LIST"
0x180006a65  mov     [rsp+0A8h+var_80], rax
0x180006a6a  mov     rcx, rbx
0x180006a6d  lea     rax, ?_EqualKeys@?$CTypedHashTable@VW3_RESTRICTION_LIST@@VW3_IMAGE_RECORD@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180006a74  mov     [rsp+0A8h+var_88], rax
0x180006a79  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180006a7f  mov     rdx, rbp; struct INativeSectionException **
0x180006a82  mov     dword ptr [rbx+50h], 1
0x180006a89  mov     rcx, rbx; this
0x180006a8c  call    ?Create@W3_RESTRICTION_LIST@@AEAAJPEAPEAVINativeSectionException@@@Z; W3_RESTRICTION_LIST::Create(INativeSectionException * *)
0x180006a91  mov     edi, eax
0x180006a93  test    eax, eax
0x180006a95  jns     short loc_180006AAA
0x180006a97  mov     rcx, rbx
0x180006a9a  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180006aa0  mov     rcx, rbx; Block
0x180006aa3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006aa8  jmp     short loc_180006AB8
0x180006aaa  mov     cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA, rbx; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x180006ab1  jmp     short loc_180006AB8
0x180006ab3  mov     edi, 80070008h
0x180006ab8  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180006abf  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180006ac5  test    edi, edi
0x180006ac7  js      short loc_180006B29
0x180006ac9  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180006ad0  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180006ad6  mov     rcx, cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x180006add  test    rcx, rcx
0x180006ae0  jz      loc_1800069F5
0x180006ae6  lea     r8, [rsp+0A8h+Block]
0x180006aeb  mov     [rsp+0A8h+Block], 0
0x180006af4  mov     rdx, rsi
0x180006af7  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180006afd  test    eax, eax
0x180006aff  jnz     short loc_180006B30
0x180006b01  mov     rbx, [rsp+0A8h+Block]
0x180006b06  or      eax, 0FFFFFFFFh
0x180006b09  mov     edi, [rbx+40h]
0x180006b0c  lock xadd [rbx], eax
0x180006b10  cmp     eax, 1
0x180006b13  jnz     short loc_180006B3A
0x180006b15  lea     rcx, [rbx+8]
0x180006b19  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006b1f  mov     rcx, rbx; Block
0x180006b22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006b27  jmp     short loc_180006B3A
0x180006b29  mov     eax, edi
0x180006b2b  jmp     loc_180006BD5
0x180006b30  mov     rax, cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x180006b37  mov     edi, [rax+48h]
0x180006b3a  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180006b41  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180006b47  test    edi, edi
0x180006b49  jnz     loc_180006BD0
0x180006b4f  mov     rbx, [rsp+0A8h+arg_20]
0x180006b57  mov     rcx, rbx
0x180006b5a  mov     rax, [rbx]
0x180006b5d  mov     rax, [rax+110h]
0x180006b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b69  mov     r8, rax
0x180006b6c  lea     rdx, [rsp+0A8h+var_50]
0x180006b71  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180006b78  xorps   xmm0, xmm0
0x180006b7b  mov     [rsp+0A8h+var_50], rax
0x180006b80  movdqu  [rsp+0A8h+var_48], xmm0
0x180006b86  mov     rcx, [r8]
0x180006b89  mov     rax, [rcx]
0x180006b8c  mov     rcx, r8
0x180006b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b94  test    eax, eax
0x180006b96  js      short loc_180006BD0
0x180006b98  cmp     dword ptr [rsp+0A8h+var_48+8], edi
0x180006b9c  jz      short loc_180006BD0
0x180006b9e  cmp     dword ptr [rsp+0A8h+var_48+4], 3
0x180006ba3  jb      short loc_180006BD0
0x180006ba5  cmp     dword ptr [rsp+0A8h+var_48], 4
0x180006baa  jz      short loc_180006BB3
0x180006bac  test    byte ptr [rsp+0A8h+var_48], 4
0x180006bb1  jz      short loc_180006BD0
0x180006bb3  mov     rax, [rbx]
0x180006bb6  mov     rcx, rbx
0x180006bb9  mov     rax, [rax+110h]
0x180006bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bc5  mov     rcx, rax; struct IHttpTraceContext *
0x180006bc8  mov     r8, rsi; unsigned __int16 *
0x180006bcb  call    ?RaiseEvent@SECURITY_DENIED_BY_CGI_RESTRICTION@IISSecurityEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z; IISSecurityEvents::SECURITY_DENIED_BY_CGI_RESTRICTION::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)
0x180006bd0  mov     [r14], edi
0x180006bd3  xor     eax, eax
0x180006bd5  movaps  xmm6, [rsp+0A8h+var_38]
0x180006bda  add     rsp, 80h
0x180006be1  pop     r14
0x180006be3  pop     rdi
0x180006be4  pop     rsi
0x180006be5  pop     rbp
0x180006be6  pop     rbx
0x180006be7  retn
```
