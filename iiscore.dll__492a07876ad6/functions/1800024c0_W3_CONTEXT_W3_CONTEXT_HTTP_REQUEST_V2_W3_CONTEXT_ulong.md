# W3_CONTEXT::W3_CONTEXT(_HTTP_REQUEST_V2 *,W3_CONTEXT *,ulong)

- ea: `0x1800024c0`
- end: `0x180002b23`
- name: `??0W3_CONTEXT@@QEAA@PEAU_HTTP_REQUEST_V2@@PEAV0@K@Z`
- size: `1635`
- prototype: `W3_CONTEXT *__fastcall(W3_CONTEXT *this, struct _HTTP_REQUEST_V2 *, struct W3_CONTEXT *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002380`
- `0x180003a78`
- `0x180021660`

## callees

- `0x1800024c0`
- `0x180002b30`
- `0x18001a4b0`
- `0x180032774`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002b05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002b05`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000276b`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000282a`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000276b`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000282a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002582`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002582`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180002596`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800025a9`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180002596`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800025a9`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800029fb`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800029fb`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002a3e`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002a3e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800026e0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002700`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002720`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800026e0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002700`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002720`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800028e6`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800028e6`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800028c0`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800028c0`

## pseudocode

```c
W3_CONTEXT *__fastcall W3_CONTEXT::W3_CONTEXT(
        W3_CONTEXT *this,
        struct _HTTP_REQUEST_V2 *a2,
        struct W3_CONTEXT *a3,
        int a4)
{
  char *v4; // rdi
  W3_RESPONSE *v5; // r14
  struct _HTTP_REQUEST_V2 *v9; // rbp
  W3_CONTEXT *v10; // rax
  _QWORD *v11; // rcx
  W3_SERVER *v12; // rax
  __int64 v13; // rsi
  _QWORD *v14; // rdi
  unsigned int v15; // ecx
  unsigned __int64 v16; // rsi
  _QWORD *v17; // rcx
  __int64 v18; // rdi
  unsigned __int64 v19; // rdx
  struct CONTEXT_ALLOC_BUFFER *Buffer; // rax
  struct CONTEXT_ALLOC_BUFFER *v21; // rdx
  unsigned __int64 v22; // rcx
  W3_CONTEXT *result; // rax
  void *v24; // rbp
  unsigned int v25; // r14d
  int v26; // r12d
  unsigned int v27; // edx
  struct CONTEXT_ALLOC_BUFFER **v28; // r8
  struct CONTEXT_ALLOC_BUFFER *i; // rcx
  _QWORD *j; // rax

  v4 = (char *)this + 96;
  *((_QWORD *)this + 6) = (char *)this + 96;
  v5 = (W3_CONTEXT *)((char *)this + 408);
  *((_QWORD *)this + 5) = &REQUEST_CONTEXT::`vftable';
  *((_QWORD *)this + 8) = (char *)this + 408;
  *((_QWORD *)this + 7) = &RESPONSE_CONTEXT::`vftable';
  *((_DWORD *)this + 18) = 1480799063;
  *(_QWORD *)this = &W3_CONTEXT::`vftable'{for `IHttpContext4'};
  v9 = a2;
  *((_DWORD *)this + 19) = 1;
  *((_QWORD *)this + 1) = &W3_CONTEXT::`vftable'{for `IHttpTraceContext'};
  *((_QWORD *)this + 2) = &W3_CONTEXT::`vftable'{for `IMapHandlerProvider'};
  *((_QWORD *)this + 3) = &W3_CONTEXT::`vftable'{for `IModuleAllocator'};
  *((_QWORD *)this + 4) = &W3_CONTEXT::`vftable'{for `IAuthenticationProvider'};
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 12) = &W3_REQUEST::`vftable';
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = a2;
  *((_DWORD *)this + 36) = 1;
  STRU::STRU((W3_CONTEXT *)((char *)this + 152));
  *((_QWORD *)v4 + 14) = this;
  BUFFER::BUFFER((BUFFER *)(v4 + 120));
  BUFFER::BUFFER((BUFFER *)(v4 + 168));
  *((_DWORD *)v4 + 54) = 0;
  v4[220] = 0;
  *((_QWORD *)v4 + 28) = 0;
  *((_QWORD *)v4 + 29) = 0;
  *((_QWORD *)v4 + 30) = 0;
  *((_QWORD *)v4 + 31) = 0;
  *((_QWORD *)v4 + 32) = 0;
  *((_QWORD *)v4 + 33) = 0;
  if ( v9 )
  {
    *((_QWORD *)v4 + 28) = v9->CookedUrl.pFullUrl;
    *((_QWORD *)v4 + 29) = v9->CookedUrl.pAbsPath;
    *((_DWORD *)v4 + 60) = v9->CookedUrl.FullUrlLength >> 1;
  }
  *((_BYTE *)this + 368) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  if ( a3 )
    v10 = (W3_CONTEXT *)*((_QWORD *)a3 + 49);
  else
    v10 = this;
  *((_QWORD *)this + 49) = v10;
  *((_QWORD *)this + 50) = a3;
  W3_RESPONSE::W3_RESPONSE(v5, this);
  v11 = (_QWORD *)((char *)this + 2040);
  *((_QWORD *)this + 249) = 0;
  *((_QWORD *)this + 250) = 0;
  *((_QWORD *)this + 253) = (char *)this + 2040;
  *((_DWORD *)this + 508) = 6000;
  if ( this == (W3_CONTEXT *)-2040LL )
  {
    v11 = 0;
  }
  else
  {
    *((_QWORD *)this + 256) = 6000;
    *((_DWORD *)this + 516) = 6000;
    *((_QWORD *)this + 257) = ((unsigned __int64)this + 2079) & 0xFFFFFFFFFFFFFFF8uLL;
    *v11 = 0;
  }
  *((_QWORD *)this + 251) = v11;
  *((_QWORD *)this + 252) = v11;
  *((_QWORD *)this + 1009) = 0;
  *((_DWORD *)this + 2020) = a4;
  *((_DWORD *)this + 2021) = 0;
  *((_QWORD *)this + 1011) = 0;
  *((_QWORD *)this + 1012) = 0;
  STRU::STRU((W3_CONTEXT *)((char *)this + 8104), (unsigned __int16 *)this + 4080, 0x80u);
  STRU::STRU((W3_CONTEXT *)((char *)this + 8416), (unsigned __int16 *)this + 4236, 0x80u);
  STRU::STRU((W3_CONTEXT *)((char *)this + 8728), (unsigned __int16 *)this + 4392, 0x40u);
  *((_QWORD *)this + 1114) = 0;
  *((_QWORD *)this + 1115) = 0;
  *((_QWORD *)this + 1116) = &CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'};
  *((_QWORD *)this + 1117) = &CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'};
  *((_QWORD *)this + 1118) = &CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'};
  CReaderWriterLock3::CReaderWriterLock3((W3_CONTEXT *)((char *)this + 8952));
  v12 = g_pW3Server;
  *((_QWORD *)this + 1120) = 0;
  *((_QWORD *)this + 1121) = 0;
  *((_DWORD *)this + 2244) = 0;
  *((_WORD *)this + 4490) = 0;
  *((_BYTE *)this + 8982) = 0;
  *((_QWORD *)this + 1123) = 0;
  *((_QWORD *)this + 1124) = 0;
  *((_QWORD *)this + 1125) = 0;
  *((_QWORD *)this + 1128) = 0;
  *((_QWORD *)this + 1129) = 0;
  *((_BYTE *)this + 9040) = 0;
  *((_QWORD *)this + 1131) = 0;
  *((_QWORD *)this + 1132) = 0;
  *((_QWORD *)this + 1133) = 0;
  *((_DWORD *)this + 2268) = 0;
  *((_DWORD *)this + 2269) = 1;
  *(_OWORD *)((char *)this + 9080) = 0;
  *((_WORD *)this + 4548) = 0;
  *((_BYTE *)this + 9098) = 0;
  *((_QWORD *)this + 1138) = 0;
  *((_QWORD *)this + 1139) = 0;
  v13 = *((_QWORD *)v12 + 69);
  CReaderWriterLock3::CReaderWriterLock3((W3_CONTEXT *)((char *)this + 9120));
  *((_DWORD *)this + 2290) = 0;
  *((_WORD *)this + 4582) = 0;
  *((_BYTE *)this + 9166) = 0;
  *((_OWORD *)this + 573) = 0;
  *((_QWORD *)this + 1148) = 0;
  *(_OWORD *)((char *)this + 9192) = 0;
  *((_QWORD *)this + 1151) = 0;
  *((_OWORD *)this + 576) = 0;
  *((_BYTE *)this + 9232) = 0;
  *(_OWORD *)((char *)this + 9240) = 0;
  *((_QWORD *)this + 1157) = 0;
  *((_OWORD *)this + 579) = 0;
  *((_QWORD *)this + 1160) = 0;
  *(_OWORD *)((char *)this + 9288) = 0;
  *((_BYTE *)this + 9304) = 0;
  *((_OWORD *)this + 582) = 0;
  *((_QWORD *)this + 1166) = 0;
  *((_QWORD *)this + 1142) = (char *)this + 9128;
  *((_QWORD *)this + 1141) = (char *)this + 9128;
  *((_QWORD *)this + 1144) = (char *)this + 9144;
  *((_QWORD *)this + 1143) = (char *)this + 9144;
  if ( v13 )
  {
    if ( *(_BYTE *)(v13 + 44) )
      CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)v13);
    v14 = *(_QWORD **)(v13 + 8);
    if ( v14 != (_QWORD *)(v13 + 8) )
    {
      do
      {
        if ( v14 == (_QWORD *)-24LL )
          break;
        v24 = (void *)v14[2];
        if ( *((_BYTE *)this + 9164) )
          CReaderWriterLock3::WriteLock((W3_CONTEXT *)((char *)this + 9120));
        v25 = 0;
        do
        {
          v26 = W3_TRACE_EVENT_MANAGER::SetTraceConfigurationWorker(
                  (W3_CONTEXT *)((char *)this + 9120),
                  v24,
                  (struct HTTP_TRACE_CONFIGURATION *)&v14[3 * v25 + 3]);
          if ( v26 < 0 )
            break;
          ++v25;
        }
        while ( !v25 );
        if ( *((_BYTE *)this + 9164) )
          CReaderWriterLock3::WriteUnlock((W3_CONTEXT *)((char *)this + 9120));
        if ( v26 < 0 )
          break;
        v14 = (_QWORD *)*v14;
      }
      while ( v14 != (_QWORD *)(v13 + 8) );
      v9 = a2;
    }
    if ( *(_BYTE *)(v13 + 44) )
      CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)v13);
  }
  *((_QWORD *)this + 1167) = 0xFFFFFFFFLL;
  v15 = 16 * *((_DWORD *)g_pW3Server + 152);
  v16 = v15;
  if ( v15 > 0x7FFFFFFF )
  {
    SetLastError(8u);
    goto LABEL_26;
  }
  v17 = (_QWORD *)*((_QWORD *)this + 252);
  v18 = 0;
  while ( v17 )
  {
    v19 = v17[1];
    v18 = 0;
    if ( v16 <= v19 )
    {
      v18 = v17[2];
      v17[1] = v19 - v16;
      v17[2] = v18 + v16;
    }
    if ( v18 )
      goto LABEL_25;
    v17 = (_QWORD *)*v17;
  }
  v27 = *((_DWORD *)this + 508);
  if ( (int)v16 + 64 >= v27 )
  {
    Buffer = CONTEXT_ALLOC_BASE::AllocateBuffer(0, v16);
    v21 = Buffer;
    if ( Buffer )
    {
      *(_QWORD *)Buffer = **((_QWORD **)this + 251);
      **((_QWORD **)this + 251) = Buffer;
LABEL_22:
      v22 = *((_QWORD *)v21 + 1);
      v18 = 0;
      if ( v16 <= v22 )
      {
        v18 = *((_QWORD *)v21 + 2);
        *((_QWORD *)v21 + 1) = v22 - v16;
        *((_QWORD *)v21 + 2) = v18 + v16;
      }
    }
  }
  else
  {
    v21 = CONTEXT_ALLOC_BASE::AllocateBuffer(0, v27);
    if ( v21 )
    {
      v28 = (struct CONTEXT_ALLOC_BUFFER **)*((_QWORD *)this + 251);
      for ( i = *v28; i; i = *(struct CONTEXT_ALLOC_BUFFER **)i )
        v28 = (struct CONTEXT_ALLOC_BUFFER **)i;
      *v28 = v21;
      for ( j = (_QWORD *)*((_QWORD *)this + 252); *j; *((_QWORD *)this + 252) = j )
      {
        if ( j[1] >= 0x40u )
          break;
        j = (_QWORD *)*j;
      }
      goto LABEL_22;
    }
  }
  if ( !v18 )
    goto LABEL_26;
LABEL_25:
  *((_QWORD *)this + 1120) = v18;
  *((_DWORD *)this + 2242) = v16;
LABEL_26:
  result = this;
  if ( v9 )
  {
    *((_QWORD *)this + 1127) = v9->RequestId;
    *((_QWORD *)this + 1126) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800024c0  mov     [rsp+arg_8], rdx
0x1800024c5  push    rbx
0x1800024c6  push    rbp
0x1800024c7  push    rsi
0x1800024c8  push    rdi
0x1800024c9  push    r12
0x1800024cb  push    r13
0x1800024cd  push    r14
0x1800024cf  push    r15
0x1800024d1  sub     rsp, 28h
0x1800024d5  lea     rdi, [rcx+60h]
0x1800024d9  xor     r12d, r12d
0x1800024dc  mov     [rcx+30h], rdi
0x1800024e0  lea     r14, [rcx+198h]
0x1800024e7  lea     rax, ??_7REQUEST_CONTEXT@@6B@; const REQUEST_CONTEXT::`vftable'
0x1800024ee  mov     rbx, rcx
0x1800024f1  mov     [rcx+28h], rax
0x1800024f5  mov     r15d, r9d
0x1800024f8  mov     [rcx+40h], r14
0x1800024fc  lea     rax, ??_7RESPONSE_CONTEXT@@6B@; const RESPONSE_CONTEXT::`vftable'
0x180002503  mov     [rcx+38h], rax
0x180002507  mov     rsi, r8
0x18000250a  mov     dword ptr [rcx+48h], 58433357h
0x180002511  lea     rax, ??_7W3_CONTEXT@@6BIHttpContext4@@@; const W3_CONTEXT::`vftable'{for `IHttpContext4'}
0x180002518  mov     [rcx], rax
0x18000251b  mov     rbp, rdx
0x18000251e  mov     dword ptr [rcx+4Ch], 1
0x180002525  lea     rax, ??_7W3_CONTEXT@@6BIHttpTraceContext@@@; const W3_CONTEXT::`vftable'{for `IHttpTraceContext'}
0x18000252c  mov     [rcx+8], rax
0x180002530  lea     rax, ??_7W3_CONTEXT@@6BIMapHandlerProvider@@@; const W3_CONTEXT::`vftable'{for `IMapHandlerProvider'}
0x180002537  mov     [rcx+10h], rax
0x18000253b  lea     rax, ??_7W3_CONTEXT@@6BIModuleAllocator@@@; const W3_CONTEXT::`vftable'{for `IModuleAllocator'}
0x180002542  mov     [rcx+18h], rax
0x180002546  lea     rax, ??_7W3_CONTEXT@@6BIAuthenticationProvider@@@; const W3_CONTEXT::`vftable'{for `IAuthenticationProvider'}
0x18000254d  mov     [rcx+20h], rax
0x180002551  lea     rax, ??_7W3_REQUEST@@6B@; const W3_REQUEST::`vftable'
0x180002558  mov     [rcx+50h], r12
0x18000255c  mov     [rcx+58h], r12d
0x180002560  lea     rcx, [rdi+38h]
0x180002564  mov     [rdi], rax
0x180002567  mov     [rdi+8], r12
0x18000256b  mov     [rdi+10h], r12
0x18000256f  mov     [rdi+18h], r12
0x180002573  mov     [rdi+20h], r12
0x180002577  mov     [rdi+28h], rdx
0x18000257b  mov     dword ptr [rdi+30h], 1
0x180002582  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002589  nop     dword ptr [rax+rax+00h]
0x18000258e  lea     rcx, [rdi+78h]
0x180002592  mov     [rdi+70h], rbx
0x180002596  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000259d  nop     dword ptr [rax+rax+00h]
0x1800025a2  lea     rcx, [rdi+0A8h]
0x1800025a9  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800025b0  nop     dword ptr [rax+rax+00h]
0x1800025b5  mov     [rdi+0D8h], r12d
0x1800025bc  mov     [rdi+0DCh], r12b
0x1800025c3  mov     [rdi+0E0h], r12
0x1800025ca  mov     [rdi+0E8h], r12
0x1800025d1  mov     [rdi+0F0h], r12
0x1800025d8  mov     [rdi+0F8h], r12
0x1800025df  mov     [rdi+100h], r12
0x1800025e6  mov     [rdi+108h], r12
0x1800025ed  test    rbp, rbp
0x1800025f0  jz      short loc_180002614
0x1800025f2  mov     rax, [rbp+48h]
0x1800025f6  mov     [rdi+0E0h], rax
0x1800025fd  mov     rax, [rbp+58h]
0x180002601  mov     [rdi+0E8h], rax
0x180002608  movzx   eax, word ptr [rbp+40h]
0x18000260c  shr     eax, 1
0x18000260e  mov     [rdi+0F0h], eax
0x180002614  mov     [rbx+170h], r12b
0x18000261b  mov     [rbx+178h], r12
0x180002622  mov     [rbx+180h], r12
0x180002629  test    rsi, rsi
0x18000262c  jnz     loc_180002A6A
0x180002632  mov     rax, rbx
0x180002635  mov     rdx, rbx; struct W3_CONTEXT *
0x180002638  mov     [rbx+188h], rax
0x18000263f  mov     rcx, r14; this
0x180002642  mov     [rbx+190h], rsi
0x180002649  call    ??0W3_RESPONSE@@QEAA@PEAVW3_CONTEXT@@@Z; W3_RESPONSE::W3_RESPONSE(W3_CONTEXT *)
0x18000264e  lea     rcx, [rbx+7F8h]
0x180002655  mov     [rbx+7C8h], r12
0x18000265c  mov     [rbx+7D0h], r12
0x180002663  mov     [rbx+7E8h], rcx
0x18000266a  mov     dword ptr [rbx+7F0h], 1770h
0x180002674  test    rcx, rcx
0x180002677  jz      loc_180002A76
0x18000267d  lea     rax, [rcx+27h]
0x180002681  mov     qword ptr [rcx+8], 1770h
0x180002689  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000268d  mov     dword ptr [rcx+18h], 1770h
0x180002694  mov     [rcx+10h], rax
0x180002698  mov     [rcx], r12
0x18000269b  mov     [rbx+7D8h], rcx
0x1800026a2  lea     rdx, [rbx+1FE0h]
0x1800026a9  mov     [rbx+7E0h], rcx
0x1800026b0  mov     r8d, 80h
0x1800026b6  lea     rcx, [rbx+1FA8h]
0x1800026bd  mov     [rbx+1F88h], r12
0x1800026c4  mov     [rbx+1F90h], r15d
0x1800026cb  mov     [rbx+1F94h], r12d
0x1800026d2  mov     [rbx+1F98h], r12
0x1800026d9  mov     [rbx+1FA0h], r12
0x1800026e0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800026e7  nop     dword ptr [rax+rax+00h]
0x1800026ec  lea     rdx, [rbx+2118h]
0x1800026f3  mov     r8d, 80h
0x1800026f9  lea     rcx, [rbx+20E0h]
0x180002700  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002707  nop     dword ptr [rax+rax+00h]
0x18000270c  lea     rdx, [rbx+2250h]
0x180002713  mov     r8d, 40h ; '@'
0x180002719  lea     rcx, [rbx+2218h]
0x180002720  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002727  nop     dword ptr [rax+rax+00h]
0x18000272c  mov     [rbx+22D0h], r12
0x180002733  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x18000273a  mov     [rbx+22D8h], r12
0x180002741  lea     rcx, [rbx+22F8h]
0x180002748  mov     [rbx+22E0h], rax
0x18000274f  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x180002756  mov     [rbx+22E8h], rax
0x18000275d  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x180002764  mov     [rbx+22F0h], rax
0x18000276b  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180002772  nop     dword ptr [rax+rax+00h]
0x180002777  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18000277e  lea     r13, [rbx+23A0h]
0x180002785  mov     [rbx+2300h], r12
0x18000278c  xorps   xmm0, xmm0
0x18000278f  mov     [rbx+2308h], r12
0x180002796  mov     rcx, r13
0x180002799  mov     [rbx+2310h], r12d
0x1800027a0  mov     [rbx+2314h], r12w
0x1800027a8  mov     [rbx+2316h], r12b
0x1800027af  mov     [rbx+2318h], r12
0x1800027b6  mov     [rbx+2320h], r12
0x1800027bd  mov     [rbx+2328h], r12
0x1800027c4  mov     [rbx+2340h], r12
0x1800027cb  mov     [rbx+2348h], r12
0x1800027d2  mov     [rbx+2350h], r12b
0x1800027d9  mov     [rbx+2358h], r12
0x1800027e0  mov     [rbx+2360h], r12
0x1800027e7  mov     [rbx+2368h], r12
0x1800027ee  mov     [rbx+2370h], r12d
0x1800027f5  mov     dword ptr [rbx+2374h], 1
0x1800027ff  movups  xmmword ptr [rbx+2378h], xmm0
0x180002806  mov     [rbx+2388h], r12w
0x18000280e  mov     [rbx+238Ah], r12b
0x180002815  mov     [rbx+2390h], r12
0x18000281c  mov     [rbx+2398h], r12
0x180002823  mov     rsi, [rax+228h]
0x18000282a  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180002831  nop     dword ptr [rax+rax+00h]
0x180002836  mov     [r13+28h], r12d
0x18000283a  xorps   xmm0, xmm0
0x18000283d  mov     [r13+2Ch], r12w
0x180002842  xor     eax, eax
0x180002844  mov     [r13+2Eh], r12b
0x180002848  movups  xmmword ptr [r13+30h], xmm0
0x18000284d  mov     [r13+40h], r12
0x180002851  movups  xmmword ptr [r13+48h], xmm0
0x180002856  mov     [r13+58h], rax
0x18000285a  movups  xmmword ptr [r13+60h], xmm0
0x18000285f  mov     [r13+70h], al
0x180002863  movups  xmmword ptr [r13+78h], xmm0
0x180002868  mov     [r13+88h], r12
0x18000286f  movups  xmmword ptr [r13+90h], xmm0
0x180002877  mov     [r13+0A0h], rax
0x18000287e  movups  xmmword ptr [r13+0A8h], xmm0
0x180002886  mov     [r13+0B8h], al
0x18000288d  movups  xmmword ptr [r13+0C0h], xmm0
0x180002895  mov     [r13+0D0h], rax
0x18000289c  lea     rax, [r13+8]
0x1800028a0  mov     [rax+8], rax
0x1800028a4  mov     [rax], rax
0x1800028a7  lea     rax, [r13+18h]
0x1800028ab  mov     [rax+8], rax
0x1800028af  mov     [rax], rax
0x1800028b2  test    rsi, rsi
0x1800028b5  jz      short loc_1800028F2
0x1800028b7  cmp     [rsi+2Ch], r12b
0x1800028bb  jz      short loc_1800028CC
0x1800028bd  mov     rcx, rsi
0x1800028c0  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800028c7  nop     dword ptr [rax+rax+00h]
0x1800028cc  mov     rdi, [rsi+8]
0x1800028d0  lea     r14, [rsi+8]
0x1800028d4  cmp     rdi, r14
0x1800028d7  jnz     loc_1800029E0
0x1800028dd  cmp     byte ptr [rsi+2Ch], 0
0x1800028e1  jz      short loc_1800028F2
0x1800028e3  mov     rcx, rsi
0x1800028e6  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800028ed  nop     dword ptr [rax+rax+00h]
0x1800028f2  mov     eax, 0FFFFFFFFh
0x1800028f7  mov     [rbx+2478h], rax
0x1800028fe  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180002905  mov     ecx, [rax+260h]
0x18000290b  shl     ecx, 4
0x18000290e  mov     esi, ecx
0x180002910  cmp     ecx, 7FFFFFFFh
0x180002916  ja      loc_180002B00
0x18000291c  mov     rcx, [rbx+7E0h]; this
0x180002923  mov     rdi, r12
0x180002926  test    rcx, rcx
0x180002929  jz      loc_180002A7E
0x18000292f  mov     rdx, [rcx+8]
0x180002933  mov     rdi, r12
0x180002936  cmp     rsi, rdx
0x180002939  ja      short loc_18000294E
0x18000293b  mov     rdi, [rcx+10h]
0x18000293f  sub     rdx, rsi
0x180002942  mov     [rcx+8], rdx
0x180002946  lea     rax, [rdi+rsi]
0x18000294a  mov     [rcx+10h], rax
0x18000294e  test    rdi, rdi
0x180002951  jnz     short loc_1800029A2
0x180002953  mov     rcx, [rcx]
0x180002956  jmp     short loc_180002926
0x180002958  mov     edx, esi; unsigned int
0x18000295a  call    ?AllocateBuffer@CONTEXT_ALLOC_BASE@@AEAAPEAVCONTEXT_ALLOC_BUFFER@@K@Z; CONTEXT_ALLOC_BASE::AllocateBuffer(ulong)
0x18000295f  mov     rdx, rax
0x180002962  test    rax, rax
0x180002965  jz      short loc_18000299D
0x180002967  mov     rax, [rbx+7D8h]
0x18000296e  mov     rcx, [rax]
0x180002971  mov     [rdx], rcx
0x180002974  mov     rax, [rbx+7D8h]
0x18000297b  mov     [rax], rdx
0x18000297e  mov     rcx, [rdx+8]
0x180002982  mov     rdi, r12
0x180002985  cmp     rsi, rcx
0x180002988  ja      short loc_18000299D
0x18000298a  mov     rdi, [rdx+10h]
0x18000298e  sub     rcx, rsi
0x180002991  mov     [rdx+8], rcx
0x180002995  lea     rax, [rdi+rsi]
0x180002999  mov     [rdx+10h], rax
0x18000299d  test    rdi, rdi
0x1800029a0  jz      short loc_1800029AF
0x1800029a2  mov     [rbx+2300h], rdi
0x1800029a9  mov     [rbx+2308h], esi
0x1800029af  mov     rax, rbx
0x1800029b2  test    rbp, rbp
0x1800029b5  jz      short loc_1800029CD
0x1800029b7  mov     rcx, [rbp+10h]
0x1800029bb  mov     [rbx+2338h], rcx
0x1800029c2  mov     qword ptr [rbx+2330h], 0
0x1800029cd  add     rsp, 28h
0x1800029d1  pop     r15
0x1800029d3  pop     r14
0x1800029d5  pop     r13
0x1800029d7  pop     r12
0x1800029d9  pop     rdi
0x1800029da  pop     rsi
0x1800029db  pop     rbp
0x1800029dc  pop     rbx
0x1800029dd  retn
0x1800029e0  lea     r15, [rdi+18h]
0x1800029e4  test    r15, r15
0x1800029e7  jz      loc_180002B19
0x1800029ed  cmp     byte ptr [r13+2Ch], 0
0x1800029f2  mov     rbp, [rdi+10h]
0x1800029f6  jz      short loc_180002A07
0x1800029f8  mov     rcx, r13
0x1800029fb  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180002a02  nop     dword ptr [rax+rax+00h]
0x180002a07  mov     r14d, r12d
0x180002a0a  mov     eax, r14d
0x180002a0d  mov     rdx, rbp; void *
0x180002a10  lea     rcx, [rax+rax*2]
0x180002a14  lea     r8, [r15+rcx*8]; struct HTTP_TRACE_CONFIGURATION *
0x180002a18  mov     rcx, r13; this
0x180002a1b  call    ?SetTraceConfigurationWorker@W3_TRACE_EVENT_MANAGER@@QEAAJPEAXPEAUHTTP_TRACE_CONFIGURATION@@@Z; W3_TRACE_EVENT_MANAGER::SetTraceConfigurationWorker(void *,HTTP_TRACE_CONFIGURATION *)
0x180002a20  mov     r12d, eax
0x180002a23  test    eax, eax
0x180002a25  js      short loc_180002A30
0x180002a27  inc     r14d
0x180002a2a  cmp     r14d, 1
0x180002a2e  jb      short loc_180002A0A
0x180002a30  cmp     byte ptr [r13+2Ch], 0
0x180002a35  lea     r14, [rsi+8]
0x180002a39  jz      short loc_180002A4A
0x180002a3b  mov     rcx, r13
0x180002a3e  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180002a45  nop     dword ptr [rax+rax+00h]
0x180002a4a  test    r12d, r12d
0x180002a4d  js      loc_180002B16
0x180002a53  mov     rdi, [rdi]
0x180002a56  mov     r12d, 0
0x180002a5c  cmp     rdi, r14
0x180002a5f  jnz     loc_1800029E0
0x180002a65  jmp     loc_180002B19
0x180002a6a  mov     rax, [rsi+188h]
0x180002a71  jmp     loc_180002635
0x180002a76  mov     rcx, r12
  ... truncated ...
```
