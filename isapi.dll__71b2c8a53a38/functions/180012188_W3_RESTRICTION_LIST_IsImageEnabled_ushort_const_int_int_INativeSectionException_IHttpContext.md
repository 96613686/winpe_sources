# W3_RESTRICTION_LIST::IsImageEnabled(ushort const *,int,int *,INativeSectionException * *,IHttpContext *)

- ea: `0x180012188`
- end: `0x180012270`
- name: `?IsImageEnabled@W3_RESTRICTION_LIST@@SAJPEBGHPEAHPEAPEAVINativeSectionException@@PEAVIHttpContext@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, int *, struct INativeSectionException **, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005224`

## callees

- `0x18000b360`
- `0x180012068`
- `0x180012150`
- `0x180012188`
- `0x180012278`
- `0x180013010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800121a2`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800121a2`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800121e3`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800121e3`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800121bb`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001220d`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800121bb`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001220d`

## pseudocode

```c
__int64 __fastcall W3_RESTRICTION_LIST::IsImageEnabled(
        const unsigned __int16 *a1,
        __int64 a2,
        int *a3,
        struct INativeSectionException **a4,
        struct IHttpContext *a5)
{
  __int64 result; // rax
  int v9; // ebx
  __int64 v10; // rax
  struct IHttpTraceContext *v11; // rax
  const struct _GUID *v12; // rdx
  W3_IMAGE_RECORD *v13; // [rsp+20h] [rbp-38h] BYREF

  while ( 1 )
  {
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
    if ( W3_RESTRICTION_LIST::sm_pRestrictionList )
      break;
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
    result = W3_RESTRICTION_LIST::CreateList(a4);
    if ( (int)result < 0 )
      return result;
  }
  v13 = 0;
  if ( (unsigned int)CLKRHashTable::FindKey(W3_RESTRICTION_LIST::sm_pRestrictionList, a1, &v13) )
  {
    v9 = *((_DWORD *)W3_RESTRICTION_LIST::sm_pRestrictionList + 19);
  }
  else
  {
    v9 = *((_DWORD *)v13 + 16);
    W3_IMAGE_RECORD::DereferenceImageRecord(v13);
  }
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
  if ( !v9 )
  {
    v10 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a5 + 272LL))(a5);
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v10, 4, 3) )
    {
      v11 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a5 + 272LL))(a5);
      IISSecurityEvents::SECURITY_DENIED_BY_ISAPI_RESTRICTION::RaiseEvent(v11, v12, a1);
    }
  }
  *a3 = v9;
  return 0;
}

```

## disassembly

```asm
0x180012188  push    rbx
0x18001218a  push    rsi
0x18001218b  push    rdi
0x18001218c  push    r14
0x18001218e  sub     rsp, 38h
0x180012192  mov     rbx, r9
0x180012195  mov     r14, r8
0x180012198  mov     rsi, rcx
0x18001219b  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x1800121a2  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800121a8  mov     rcx, cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x1800121af  test    rcx, rcx
0x1800121b2  jnz     short loc_1800121D2
0x1800121b4  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x1800121bb  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800121c1  mov     rcx, rbx; struct INativeSectionException **
0x1800121c4  call    ?CreateList@W3_RESTRICTION_LIST@@SAJPEAPEAVINativeSectionException@@@Z; W3_RESTRICTION_LIST::CreateList(INativeSectionException * *)
0x1800121c9  test    eax, eax
0x1800121cb  jns     short loc_18001219B
0x1800121cd  jmp     loc_180012266
0x1800121d2  lea     r8, [rsp+58h+var_38]
0x1800121d7  mov     [rsp+58h+var_38], 0
0x1800121e0  mov     rdx, rsi
0x1800121e3  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800121e9  test    eax, eax
0x1800121eb  jnz     short loc_1800121FC
0x1800121ed  mov     rcx, [rsp+58h+var_38]; this
0x1800121f2  mov     ebx, [rcx+40h]
0x1800121f5  call    ?DereferenceImageRecord@W3_IMAGE_RECORD@@QEAAXXZ; W3_IMAGE_RECORD::DereferenceImageRecord(void)
0x1800121fa  jmp     short loc_180012206
0x1800121fc  mov     rax, cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x180012203  mov     ebx, [rax+4Ch]
0x180012206  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x18001220d  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180012213  test    ebx, ebx
0x180012215  jnz     short loc_180012261
0x180012217  mov     rdi, [rsp+58h+arg_20]
0x18001221f  mov     rcx, rdi
0x180012222  mov     rax, [rdi]
0x180012225  mov     rax, [rax+110h]
0x18001222c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012231  lea     edx, [rbx+4]
0x180012234  mov     rcx, rax
0x180012237  lea     r8d, [rbx+3]
0x18001223b  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180012240  test    eax, eax
0x180012242  jz      short loc_180012261
0x180012244  mov     rax, [rdi]
0x180012247  mov     rcx, rdi
0x18001224a  mov     rax, [rax+110h]
0x180012251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012256  mov     rcx, rax; struct IHttpTraceContext *
0x180012259  mov     r8, rsi; unsigned __int16 *
0x18001225c  call    ?RaiseEvent@SECURITY_DENIED_BY_ISAPI_RESTRICTION@IISSecurityEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z; IISSecurityEvents::SECURITY_DENIED_BY_ISAPI_RESTRICTION::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)
0x180012261  mov     [r14], ebx
0x180012264  xor     eax, eax
0x180012266  add     rsp, 38h
0x18001226a  pop     r14
0x18001226c  pop     rdi
0x18001226d  pop     rsi
0x18001226e  pop     rbx
0x18001226f  retn
```
