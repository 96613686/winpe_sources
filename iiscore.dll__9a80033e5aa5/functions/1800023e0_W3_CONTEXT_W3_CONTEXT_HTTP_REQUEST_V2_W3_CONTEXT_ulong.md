# W3_CONTEXT::W3_CONTEXT(_HTTP_REQUEST_V2 *,W3_CONTEXT *,ulong)

- ea: `0x1800023e0`
- end: `0x1800029ed`
- name: `??0W3_CONTEXT@@QEAA@PEAU_HTTP_REQUEST_V2@@PEAV0@K@Z`
- size: `1549`
- prototype: `W3_CONTEXT *__fastcall(W3_CONTEXT *__hidden this, struct _HTTP_REQUEST_V2 *, struct W3_CONTEXT *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800022c0`
- `0x1800037a4`
- `0x18001fa60`

## callees

- `0x1800023e0`
- `0x180002a00`
- `0x180018f38`
- `0x18002fb14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800029d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800029d5`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002667`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002720`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002667`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002720`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800024a2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800024a2`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800024b0`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800024bd`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800024b0`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800024bd`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800028dd`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800028dd`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000291a`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000291a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800025ee`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002608`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002622`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800025ee`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002608`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002622`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800027d0`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800027d0`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800027b0`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800027b0`

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
0x1800023e0  mov     [rsp+arg_8], rdx
0x1800023e5  push    rbx
0x1800023e6  push    rbp
0x1800023e7  push    rsi
0x1800023e8  push    rdi
0x1800023e9  push    r12
0x1800023eb  push    r13
0x1800023ed  push    r14
0x1800023ef  push    r15
0x1800023f1  sub     rsp, 28h
0x1800023f5  lea     rdi, [rcx+60h]
0x1800023f9  xor     r12d, r12d
0x1800023fc  mov     [rcx+30h], rdi
0x180002400  lea     r14, [rcx+198h]
0x180002407  lea     rax, ??_7REQUEST_CONTEXT@@6B@; const REQUEST_CONTEXT::`vftable'
0x18000240e  mov     rbx, rcx
0x180002411  mov     [rcx+28h], rax
0x180002415  mov     r15d, r9d
0x180002418  mov     [rcx+40h], r14
0x18000241c  lea     rax, ??_7RESPONSE_CONTEXT@@6B@; const RESPONSE_CONTEXT::`vftable'
0x180002423  mov     [rcx+38h], rax
0x180002427  mov     rsi, r8
0x18000242a  mov     dword ptr [rcx+48h], 58433357h
0x180002431  lea     rax, ??_7W3_CONTEXT@@6BIHttpContext4@@@; const W3_CONTEXT::`vftable'{for `IHttpContext4'}
0x180002438  mov     [rcx], rax
0x18000243b  mov     rbp, rdx
0x18000243e  mov     dword ptr [rcx+4Ch], 1
0x180002445  lea     rax, ??_7W3_CONTEXT@@6BIHttpTraceContext@@@; const W3_CONTEXT::`vftable'{for `IHttpTraceContext'}
0x18000244c  mov     [rcx+8], rax
0x180002450  lea     rax, ??_7W3_CONTEXT@@6BIMapHandlerProvider@@@; const W3_CONTEXT::`vftable'{for `IMapHandlerProvider'}
0x180002457  mov     [rcx+10h], rax
0x18000245b  lea     rax, ??_7W3_CONTEXT@@6BIModuleAllocator@@@; const W3_CONTEXT::`vftable'{for `IModuleAllocator'}
0x180002462  mov     [rcx+18h], rax
0x180002466  lea     rax, ??_7W3_CONTEXT@@6BIAuthenticationProvider@@@; const W3_CONTEXT::`vftable'{for `IAuthenticationProvider'}
0x18000246d  mov     [rcx+20h], rax
0x180002471  lea     rax, ??_7W3_REQUEST@@6B@; const W3_REQUEST::`vftable'
0x180002478  mov     [rcx+50h], r12
0x18000247c  mov     [rcx+58h], r12d
0x180002480  lea     rcx, [rdi+38h]
0x180002484  mov     [rdi], rax
0x180002487  mov     [rdi+8], r12
0x18000248b  mov     [rdi+10h], r12
0x18000248f  mov     [rdi+18h], r12
0x180002493  mov     [rdi+20h], r12
0x180002497  mov     [rdi+28h], rdx
0x18000249b  mov     dword ptr [rdi+30h], 1
0x1800024a2  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800024a8  lea     rcx, [rdi+78h]
0x1800024ac  mov     [rdi+70h], rbx
0x1800024b0  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800024b6  lea     rcx, [rdi+0A8h]
0x1800024bd  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800024c3  mov     [rdi+0D8h], r12d
0x1800024ca  mov     [rdi+0DCh], r12b
0x1800024d1  mov     [rdi+0E0h], r12
0x1800024d8  mov     [rdi+0E8h], r12
0x1800024df  mov     [rdi+0F0h], r12
0x1800024e6  mov     [rdi+0F8h], r12
0x1800024ed  mov     [rdi+100h], r12
0x1800024f4  mov     [rdi+108h], r12
0x1800024fb  test    rbp, rbp
0x1800024fe  jz      short loc_180002522
0x180002500  mov     rax, [rbp+48h]
0x180002504  mov     [rdi+0E0h], rax
0x18000250b  mov     rax, [rbp+58h]
0x18000250f  mov     [rdi+0E8h], rax
0x180002516  movzx   eax, word ptr [rbp+40h]
0x18000251a  shr     eax, 1
0x18000251c  mov     [rdi+0F0h], eax
0x180002522  mov     [rbx+170h], r12b
0x180002529  mov     [rbx+178h], r12
0x180002530  mov     [rbx+180h], r12
0x180002537  test    rsi, rsi
0x18000253a  jnz     loc_18000293C
0x180002540  mov     rax, rbx
0x180002543  mov     rdx, rbx; struct W3_CONTEXT *
0x180002546  mov     [rbx+188h], rax
0x18000254d  mov     rcx, r14; this
0x180002550  mov     [rbx+190h], rsi
0x180002557  call    ??0W3_RESPONSE@@QEAA@PEAVW3_CONTEXT@@@Z; W3_RESPONSE::W3_RESPONSE(W3_CONTEXT *)
0x18000255c  lea     rcx, [rbx+7F8h]
0x180002563  mov     [rbx+7C8h], r12
0x18000256a  mov     [rbx+7D0h], r12
0x180002571  mov     [rbx+7E8h], rcx
0x180002578  mov     dword ptr [rbx+7F0h], 1770h
0x180002582  test    rcx, rcx
0x180002585  jz      loc_180002948
0x18000258b  lea     rax, [rcx+27h]
0x18000258f  mov     qword ptr [rcx+8], 1770h
0x180002597  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000259b  mov     dword ptr [rcx+18h], 1770h
0x1800025a2  mov     [rcx+10h], rax
0x1800025a6  mov     [rcx], r12
0x1800025a9  mov     [rbx+7D8h], rcx
0x1800025b0  lea     rdx, [rbx+1FE0h]
0x1800025b7  mov     [rbx+7E0h], rcx
0x1800025be  mov     r8d, 80h
0x1800025c4  lea     rcx, [rbx+1FA8h]
0x1800025cb  mov     [rbx+1F88h], r12
0x1800025d2  mov     [rbx+1F90h], r15d
0x1800025d9  mov     [rbx+1F94h], r12d
0x1800025e0  mov     [rbx+1F98h], r12
0x1800025e7  mov     [rbx+1FA0h], r12
0x1800025ee  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800025f4  lea     rdx, [rbx+2118h]
0x1800025fb  mov     r8d, 80h
0x180002601  lea     rcx, [rbx+20E0h]
0x180002608  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000260e  lea     rdx, [rbx+2250h]
0x180002615  mov     r8d, 40h ; '@'
0x18000261b  lea     rcx, [rbx+2218h]
0x180002622  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002628  mov     [rbx+22D0h], r12
0x18000262f  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x180002636  mov     [rbx+22D8h], r12
0x18000263d  lea     rcx, [rbx+22F8h]
0x180002644  mov     [rbx+22E0h], rax
0x18000264b  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x180002652  mov     [rbx+22E8h], rax
0x180002659  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x180002660  mov     [rbx+22F0h], rax
0x180002667  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18000266d  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180002674  lea     r13, [rbx+23A0h]
0x18000267b  mov     [rbx+2300h], r12
0x180002682  xorps   xmm0, xmm0
0x180002685  mov     [rbx+2308h], r12
0x18000268c  mov     rcx, r13
0x18000268f  mov     [rbx+2310h], r12d
0x180002696  mov     [rbx+2314h], r12w
0x18000269e  mov     [rbx+2316h], r12b
0x1800026a5  mov     [rbx+2318h], r12
0x1800026ac  mov     [rbx+2320h], r12
0x1800026b3  mov     [rbx+2328h], r12
0x1800026ba  mov     [rbx+2340h], r12
0x1800026c1  mov     [rbx+2348h], r12
0x1800026c8  mov     [rbx+2350h], r12b
0x1800026cf  mov     [rbx+2358h], r12
0x1800026d6  mov     [rbx+2360h], r12
0x1800026dd  mov     [rbx+2368h], r12
0x1800026e4  mov     [rbx+2370h], r12d
0x1800026eb  mov     dword ptr [rbx+2374h], 1
0x1800026f5  movups  xmmword ptr [rbx+2378h], xmm0
0x1800026fc  mov     [rbx+2388h], r12w
0x180002704  mov     [rbx+238Ah], r12b
0x18000270b  mov     [rbx+2390h], r12
0x180002712  mov     [rbx+2398h], r12
0x180002719  mov     rsi, [rax+228h]
0x180002720  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180002726  mov     [r13+28h], r12d
0x18000272a  xorps   xmm0, xmm0
0x18000272d  mov     [r13+2Ch], r12w
0x180002732  xor     eax, eax
0x180002734  mov     [r13+2Eh], r12b
0x180002738  movups  xmmword ptr [r13+30h], xmm0
0x18000273d  mov     [r13+40h], r12
0x180002741  movups  xmmword ptr [r13+48h], xmm0
0x180002746  mov     [r13+58h], rax
0x18000274a  movups  xmmword ptr [r13+60h], xmm0
0x18000274f  mov     [r13+70h], al
0x180002753  movups  xmmword ptr [r13+78h], xmm0
0x180002758  mov     [r13+88h], r12
0x18000275f  movups  xmmword ptr [r13+90h], xmm0
0x180002767  mov     [r13+0A0h], rax
0x18000276e  movups  xmmword ptr [r13+0A8h], xmm0
0x180002776  mov     [r13+0B8h], al
0x18000277d  movups  xmmword ptr [r13+0C0h], xmm0
0x180002785  mov     [r13+0D0h], rax
0x18000278c  lea     rax, [r13+8]
0x180002790  mov     [rax+8], rax
0x180002794  mov     [rax], rax
0x180002797  lea     rax, [r13+18h]
0x18000279b  mov     [rax+8], rax
0x18000279f  mov     [rax], rax
0x1800027a2  test    rsi, rsi
0x1800027a5  jz      short loc_1800027D6
0x1800027a7  cmp     [rsi+2Ch], r12b
0x1800027ab  jz      short loc_1800027B6
0x1800027ad  mov     rcx, rsi
0x1800027b0  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800027b6  mov     rdi, [rsi+8]
0x1800027ba  lea     r14, [rsi+8]
0x1800027be  cmp     rdi, r14
0x1800027c1  jnz     loc_1800028C2
0x1800027c7  cmp     byte ptr [rsi+2Ch], 0
0x1800027cb  jz      short loc_1800027D6
0x1800027cd  mov     rcx, rsi
0x1800027d0  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800027d6  mov     eax, 0FFFFFFFFh
0x1800027db  mov     [rbx+2478h], rax
0x1800027e2  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800027e9  mov     ecx, [rax+260h]
0x1800027ef  shl     ecx, 4
0x1800027f2  mov     esi, ecx
0x1800027f4  cmp     ecx, 7FFFFFFFh
0x1800027fa  ja      loc_1800029D0
0x180002800  mov     rcx, [rbx+7E0h]; this
0x180002807  mov     rdi, r12
0x18000280a  test    rcx, rcx
0x18000280d  jz      loc_180002950
0x180002813  mov     rdx, [rcx+8]
0x180002817  mov     rdi, r12
0x18000281a  cmp     rsi, rdx
0x18000281d  ja      short loc_180002832
0x18000281f  mov     rdi, [rcx+10h]
0x180002823  sub     rdx, rsi
0x180002826  mov     [rcx+8], rdx
0x18000282a  lea     rax, [rdi+rsi]
0x18000282e  mov     [rcx+10h], rax
0x180002832  test    rdi, rdi
0x180002835  jnz     short loc_180002886
0x180002837  mov     rcx, [rcx]
0x18000283a  jmp     short loc_18000280A
0x18000283c  mov     edx, esi; unsigned int
0x18000283e  call    ?AllocateBuffer@CONTEXT_ALLOC_BASE@@AEAAPEAVCONTEXT_ALLOC_BUFFER@@K@Z; CONTEXT_ALLOC_BASE::AllocateBuffer(ulong)
0x180002843  mov     rdx, rax
0x180002846  test    rax, rax
0x180002849  jz      short loc_180002881
0x18000284b  mov     rax, [rbx+7D8h]
0x180002852  mov     rcx, [rax]
0x180002855  mov     [rdx], rcx
0x180002858  mov     rax, [rbx+7D8h]
0x18000285f  mov     [rax], rdx
0x180002862  mov     rcx, [rdx+8]
0x180002866  mov     rdi, r12
0x180002869  cmp     rsi, rcx
0x18000286c  ja      short loc_180002881
0x18000286e  mov     rdi, [rdx+10h]
0x180002872  sub     rcx, rsi
0x180002875  mov     [rdx+8], rcx
0x180002879  lea     rax, [rdi+rsi]
0x18000287d  mov     [rdx+10h], rax
0x180002881  test    rdi, rdi
0x180002884  jz      short loc_180002893
0x180002886  mov     [rbx+2300h], rdi
0x18000288d  mov     [rbx+2308h], esi
0x180002893  mov     rax, rbx
0x180002896  test    rbp, rbp
0x180002899  jz      short loc_1800028B1
0x18000289b  mov     rcx, [rbp+10h]
0x18000289f  mov     [rbx+2338h], rcx
0x1800028a6  mov     qword ptr [rbx+2330h], 0
0x1800028b1  add     rsp, 28h
0x1800028b5  pop     r15
0x1800028b7  pop     r14
0x1800028b9  pop     r13
0x1800028bb  pop     r12
0x1800028bd  pop     rdi
0x1800028be  pop     rsi
0x1800028bf  pop     rbp
0x1800028c0  pop     rbx
0x1800028c1  retn
0x1800028c2  lea     r15, [rdi+18h]
0x1800028c6  test    r15, r15
0x1800028c9  jz      loc_1800029E3
0x1800028cf  cmp     byte ptr [r13+2Ch], 0
0x1800028d4  mov     rbp, [rdi+10h]
0x1800028d8  jz      short loc_1800028E3
0x1800028da  mov     rcx, r13
0x1800028dd  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800028e3  mov     r14d, r12d
0x1800028e6  mov     eax, r14d
0x1800028e9  mov     rdx, rbp; void *
0x1800028ec  lea     rcx, [rax+rax*2]
0x1800028f0  lea     r8, [r15+rcx*8]; struct HTTP_TRACE_CONFIGURATION *
0x1800028f4  mov     rcx, r13; this
0x1800028f7  call    ?SetTraceConfigurationWorker@W3_TRACE_EVENT_MANAGER@@QEAAJPEAXPEAUHTTP_TRACE_CONFIGURATION@@@Z; W3_TRACE_EVENT_MANAGER::SetTraceConfigurationWorker(void *,HTTP_TRACE_CONFIGURATION *)
0x1800028fc  mov     r12d, eax
0x1800028ff  test    eax, eax
0x180002901  js      short loc_18000290C
0x180002903  inc     r14d
0x180002906  cmp     r14d, 1
0x18000290a  jb      short loc_1800028E6
0x18000290c  cmp     byte ptr [r13+2Ch], 0
0x180002911  lea     r14, [rsi+8]
0x180002915  jz      short loc_180002920
0x180002917  mov     rcx, r13
0x18000291a  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180002920  test    r12d, r12d
0x180002923  js      loc_1800029E0
0x180002929  mov     rdi, [rdi]
0x18000292c  mov     r12d, 0
0x180002932  cmp     rdi, r14
0x180002935  jnz     short loc_1800028C2
0x180002937  jmp     loc_1800029E3
0x18000293c  mov     rax, [rsi+188h]
0x180002943  jmp     loc_180002543
0x180002948  mov     rcx, r12
0x18000294b  jmp     loc_1800025A9
0x180002950  mov     edx, [rbx+7F0h]; unsigned int
0x180002956  lea     eax, [rsi+40h]
0x180002959  cmp     eax, edx
0x18000295b  jnb     loc_18000283C
0x180002961  call    ?AllocateBuffer@CONTEXT_ALLOC_BASE@@AEAAPEAVCONTEXT_ALLOC_BUFFER@@K@Z; CONTEXT_ALLOC_BASE::AllocateBuffer(ulong)
0x180002966  mov     rdx, rax
0x180002969  test    rax, rax
0x18000296c  jz      loc_180002881
0x180002972  mov     r8, [rbx+7D8h]
0x180002979  mov     rcx, [r8]
0x18000297c  test    rcx, rcx
  ... truncated ...
```
