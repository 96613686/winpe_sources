# CLocationEnvironmentHelper::CLocationEnvironmentHelper(void)

- ea: `0x1800024d4`
- end: `0x180002b10`
- name: `??0CLocationEnvironmentHelper@@QEAA@XZ`
- size: `1596`
- prototype: `CLocationEnvironmentHelper *__fastcall(CLocationEnvironmentHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800018e0`

## callees

- `0x1800024d4`
- `0x1800058fc`
- `0x180005b48`

## string_xrefs

- `0x180002572`: `BreadcrumbingEnabled`

## pseudocode

```c
CLocationEnvironmentHelper *__fastcall CLocationEnvironmentHelper::CLocationEnvironmentHelper(
        CLocationEnvironmentHelper *this)
{
  __int64 v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int128 v18; // [rsp+20h] [rbp-30h] BYREF
  __int128 v19; // [rsp+30h] [rbp-20h]
  __int64 v20; // [rsp+40h] [rbp-10h]

  std::vector<CLocationEnvironmentHelper::BitMetadata>::vector<CLocationEnvironmentHelper::BitMetadata>();
  LODWORD(v18) = 0;
  *((_QWORD *)&v18 + 1) = "ActiveCollectionEnabled";
  *(_QWORD *)&v19 = 0;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  v2 = *((_QWORD *)&c_environmentHelper + 1);
  if ( *((_QWORD *)&c_environmentHelper + 1) == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      *((_QWORD *)&c_environmentHelper + 1),
      &v18);
    v3 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    **((_OWORD **)&c_environmentHelper + 1) = v18;
    *(_OWORD *)(v2 + 16) = v19;
    *(_QWORD *)(v2 + 32) = v20;
    v3 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 1;
  *((_QWORD *)&v18 + 1) = "BreadcrumbingEnabled";
  *(_QWORD *)&v19 = 2;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v3 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v3,
      &v18);
    v4 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v3 = v18;
    *(_OWORD *)(v3 + 16) = v19;
    *(_QWORD *)(v3 + 32) = v20;
    v4 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 2;
  *((_QWORD *)&v18 + 1) = "ConnectedToACPower";
  *(_QWORD *)&v19 = 4;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v4 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v4,
      &v18);
    v5 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v4 = v18;
    *(_OWORD *)(v4 + 16) = v19;
    *(_QWORD *)(v4 + 32) = v20;
    v5 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 3;
  *((_QWORD *)&v18 + 1) = "InternetPresent";
  *(_QWORD *)&v19 = 6;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v5 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v5,
      &v18);
    v6 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v5 = v18;
    *(_OWORD *)(v5 + 16) = v19;
    *(_QWORD *)(v5 + 32) = v20;
    v6 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 4;
  *((_QWORD *)&v18 + 1) = "OnFreeNetwork";
  *(_QWORD *)&v19 = 8;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v6 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v6,
      &v18);
    v7 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v6 = v18;
    *(_OWORD *)(v6 + 16) = v19;
    *(_QWORD *)(v6 + 32) = v20;
    v7 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 5;
  *((_QWORD *)&v18 + 1) = "UserActivityPresent";
  *(_QWORD *)&v19 = 10;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v7 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v7,
      &v18);
    v8 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v7 = v18;
    *(_OWORD *)(v7 + 16) = v19;
    *(_QWORD *)(v7 + 32) = v20;
    v8 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 6;
  *((_QWORD *)&v18 + 1) = "WiFiConnected";
  *(_QWORD *)&v19 = 12;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v8 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v8,
      &v18);
    v9 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v8 = v18;
    *(_OWORD *)(v8 + 16) = v19;
    *(_QWORD *)(v8 + 32) = v20;
    v9 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 7;
  *((_QWORD *)&v18 + 1) = "GnssHWAvailable";
  *(_QWORD *)&v19 = 14;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v9 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v9,
      &v18);
    v10 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v9 = v18;
    *(_OWORD *)(v9 + 16) = v19;
    *(_QWORD *)(v9 + 32) = v20;
    v10 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 8;
  *((_QWORD *)&v18 + 1) = "GnssHWGeofenceTrackingActive";
  *(_QWORD *)&v19 = 16;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v10 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v10,
      &v18);
    v11 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v10 = v18;
    *(_OWORD *)(v10 + 16) = v19;
    *(_QWORD *)(v10 + 32) = v20;
    v11 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 9;
  *((_QWORD *)&v18 + 1) = "TrackedGeofencesPresent";
  *(_QWORD *)&v19 = 18;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v11 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v11,
      &v18);
    v12 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v11 = v18;
    *(_OWORD *)(v11 + 16) = v19;
    *(_QWORD *)(v11 + 32) = v20;
    v12 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 10;
  *((_QWORD *)&v18 + 1) = "InternalTrackedGeofencesPresent";
  *(_QWORD *)&v19 = 20;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v12 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v12,
      &v18);
    v13 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v12 = v18;
    *(_OWORD *)(v12 + 16) = v19;
    *(_QWORD *)(v12 + 32) = v20;
    v13 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 11;
  *((_QWORD *)&v18 + 1) = "BatterySavingsOn";
  *(_QWORD *)&v19 = 22;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v13 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v13,
      &v18);
    v14 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v13 = v18;
    *(_OWORD *)(v13 + 16) = v19;
    *(_QWORD *)(v13 + 32) = v20;
    v14 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 12;
  *((_QWORD *)&v18 + 1) = "ClientOriginatedActivityExists";
  *(_QWORD *)&v19 = 24;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v14 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v14,
      &v18);
    v15 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v14 = v18;
    *(_OWORD *)(v14 + 16) = v19;
    *(_QWORD *)(v14 + 32) = v20;
    v15 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 13;
  *((_QWORD *)&v18 + 1) = "ModernStandbyActive";
  *(_QWORD *)&v19 = 26;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v15 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v15,
      &v18);
    v16 = *((_QWORD *)&c_environmentHelper + 1);
  }
  else
  {
    *(_OWORD *)v15 = v18;
    *(_OWORD *)(v15 + 16) = v19;
    *(_QWORD *)(v15 + 32) = v20;
    v16 = *((_QWORD *)&c_environmentHelper + 1) + 40LL;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  LODWORD(v18) = 14;
  *((_QWORD *)&v18 + 1) = "NetworkConnectedInStandby";
  *(_QWORD *)&v19 = 28;
  *((_QWORD *)&v19 + 1) = 1;
  LOBYTE(v20) = 1;
  if ( v16 == qword_180012550 )
  {
    std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(
      v1,
      v16,
      &v18);
  }
  else
  {
    *(_OWORD *)v16 = v18;
    *(_OWORD *)(v16 + 16) = v19;
    *(_QWORD *)(v16 + 32) = v20;
    *((_QWORD *)&c_environmentHelper + 1) += 40LL;
  }
  return (CLocationEnvironmentHelper *)&c_environmentHelper;
}

```

## disassembly

```asm
0x1800024d4  mov     [rsp-8+arg_8], rbx
0x1800024d9  mov     [rsp-8+arg_10], r13
0x1800024de  mov     [rsp-8+arg_0], rcx
0x1800024e3  push    rbp
0x1800024e4  mov     rbp, rsp
0x1800024e7  sub     rsp, 50h
0x1800024eb  lea     r13, ?c_environmentHelper@@3VCLocationEnvironmentHelper@@B; CLocationEnvironmentHelper const c_environmentHelper
0x1800024f2  mov     [rbp+arg_0], r13
0x1800024f6  call    ??0?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@QEAA@XZ; std::vector<CLocationEnvironmentHelper::BitMetadata>::vector<CLocationEnvironmentHelper::BitMetadata>(void)
0x1800024fb  nop
0x1800024fc  mov     dword ptr [rbp+var_30], 0
0x180002503  lea     rax, aActivecollecti; "ActiveCollectionEnabled"
0x18000250a  mov     qword ptr [rbp+var_30+8], rax
0x18000250e  mov     qword ptr [rbp+var_20], 0
0x180002516  mov     ebx, 1
0x18000251b  mov     qword ptr [rbp+var_20+8], rbx
0x18000251f  mov     byte ptr [rbp+var_10], bl
0x180002522  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x180002529  cmp     rdx, cs:qword_180012550
0x180002530  jz      short loc_18000255F
0x180002532  movups  xmm0, [rbp+var_30]
0x180002536  movups  xmmword ptr [rdx], xmm0
0x180002539  movups  xmm1, [rbp+var_20]
0x18000253d  movups  xmmword ptr [rdx+10h], xmm1
0x180002541  movsd   xmm0, [rbp+var_10]
0x180002546  movsd   qword ptr [rdx+20h], xmm0
0x18000254b  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x180002552  add     rdx, 28h ; '('
0x180002556  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x18000255d  jmp     short loc_18000256F
0x18000255f  lea     r8, [rbp+var_30]
0x180002563  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x180002568  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x18000256f  mov     dword ptr [rbp+var_30], ebx
0x180002572  lea     rax, aBreadcrumbinge; "BreadcrumbingEnabled"
0x180002579  mov     qword ptr [rbp+var_30+8], rax
0x18000257d  mov     qword ptr [rbp+var_20], 2
0x180002585  mov     qword ptr [rbp+var_20+8], rbx
0x180002589  mov     byte ptr [rbp+var_10], bl
0x18000258c  cmp     rdx, cs:qword_180012550
0x180002593  jz      short loc_1800025C2
0x180002595  movups  xmm0, [rbp+var_30]
0x180002599  movups  xmmword ptr [rdx], xmm0
0x18000259c  movups  xmm1, [rbp+var_20]
0x1800025a0  movups  xmmword ptr [rdx+10h], xmm1
0x1800025a4  movsd   xmm0, [rbp+var_10]
0x1800025a9  movsd   qword ptr [rdx+20h], xmm0
0x1800025ae  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x1800025b5  add     rdx, 28h ; '('
0x1800025b9  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x1800025c0  jmp     short loc_1800025D2
0x1800025c2  lea     r8, [rbp+var_30]
0x1800025c6  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x1800025cb  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x1800025d2  mov     dword ptr [rbp+var_30], 2
0x1800025d9  lea     rax, aConnectedtoacp; "ConnectedToACPower"
0x1800025e0  mov     qword ptr [rbp+var_30+8], rax
0x1800025e4  mov     qword ptr [rbp+var_20], 4
0x1800025ec  mov     qword ptr [rbp+var_20+8], rbx
0x1800025f0  mov     byte ptr [rbp+var_10], bl
0x1800025f3  cmp     rdx, cs:qword_180012550
0x1800025fa  jz      short loc_180002629
0x1800025fc  movups  xmm0, [rbp+var_30]
0x180002600  movups  xmmword ptr [rdx], xmm0
0x180002603  movups  xmm1, [rbp+var_20]
0x180002607  movups  xmmword ptr [rdx+10h], xmm1
0x18000260b  movsd   xmm0, [rbp+var_10]
0x180002610  movsd   qword ptr [rdx+20h], xmm0
0x180002615  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x18000261c  add     rdx, 28h ; '('
0x180002620  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x180002627  jmp     short loc_180002639
0x180002629  lea     r8, [rbp+var_30]
0x18000262d  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x180002632  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x180002639  mov     dword ptr [rbp+var_30], 3
0x180002640  lea     rax, aInternetpresen; "InternetPresent"
0x180002647  mov     qword ptr [rbp+var_30+8], rax
0x18000264b  mov     qword ptr [rbp+var_20], 6
0x180002653  mov     qword ptr [rbp+var_20+8], rbx
0x180002657  mov     byte ptr [rbp+var_10], bl
0x18000265a  cmp     rdx, cs:qword_180012550
0x180002661  jz      short loc_180002690
0x180002663  movups  xmm0, [rbp+var_30]
0x180002667  movups  xmmword ptr [rdx], xmm0
0x18000266a  movups  xmm1, [rbp+var_20]
0x18000266e  movups  xmmword ptr [rdx+10h], xmm1
0x180002672  movsd   xmm0, [rbp+var_10]
0x180002677  movsd   qword ptr [rdx+20h], xmm0
0x18000267c  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x180002683  add     rdx, 28h ; '('
0x180002687  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x18000268e  jmp     short loc_1800026A0
0x180002690  lea     r8, [rbp+var_30]
0x180002694  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x180002699  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x1800026a0  mov     dword ptr [rbp+var_30], 4
0x1800026a7  lea     rax, aOnfreenetwork; "OnFreeNetwork"
0x1800026ae  mov     qword ptr [rbp+var_30+8], rax
0x1800026b2  mov     qword ptr [rbp+var_20], 8
0x1800026ba  mov     qword ptr [rbp+var_20+8], rbx
0x1800026be  mov     byte ptr [rbp+var_10], bl
0x1800026c1  cmp     rdx, cs:qword_180012550
0x1800026c8  jz      short loc_1800026F7
0x1800026ca  movups  xmm0, [rbp+var_30]
0x1800026ce  movups  xmmword ptr [rdx], xmm0
0x1800026d1  movups  xmm1, [rbp+var_20]
0x1800026d5  movups  xmmword ptr [rdx+10h], xmm1
0x1800026d9  movsd   xmm0, [rbp+var_10]
0x1800026de  movsd   qword ptr [rdx+20h], xmm0
0x1800026e3  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x1800026ea  add     rdx, 28h ; '('
0x1800026ee  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x1800026f5  jmp     short loc_180002707
0x1800026f7  lea     r8, [rbp+var_30]
0x1800026fb  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x180002700  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x180002707  mov     dword ptr [rbp+var_30], 5
0x18000270e  lea     rax, aUseractivitypr; "UserActivityPresent"
0x180002715  mov     qword ptr [rbp+var_30+8], rax
0x180002719  mov     qword ptr [rbp+var_20], 0Ah
0x180002721  mov     qword ptr [rbp+var_20+8], rbx
0x180002725  mov     byte ptr [rbp+var_10], bl
0x180002728  cmp     rdx, cs:qword_180012550
0x18000272f  jz      short loc_18000275E
0x180002731  movups  xmm0, [rbp+var_30]
0x180002735  movups  xmmword ptr [rdx], xmm0
0x180002738  movups  xmm1, [rbp+var_20]
0x18000273c  movups  xmmword ptr [rdx+10h], xmm1
0x180002740  movsd   xmm0, [rbp+var_10]
0x180002745  movsd   qword ptr [rdx+20h], xmm0
0x18000274a  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x180002751  add     rdx, 28h ; '('
0x180002755  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x18000275c  jmp     short loc_18000276E
0x18000275e  lea     r8, [rbp+var_30]
0x180002762  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x180002767  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x18000276e  mov     dword ptr [rbp+var_30], 6
0x180002775  lea     rax, aWificonnected; "WiFiConnected"
0x18000277c  mov     qword ptr [rbp+var_30+8], rax
0x180002780  mov     qword ptr [rbp+var_20], 0Ch
0x180002788  mov     qword ptr [rbp+var_20+8], rbx
0x18000278c  mov     byte ptr [rbp+var_10], bl
0x18000278f  cmp     rdx, cs:qword_180012550
0x180002796  jz      short loc_1800027C5
0x180002798  movups  xmm0, [rbp+var_30]
0x18000279c  movups  xmmword ptr [rdx], xmm0
0x18000279f  movups  xmm1, [rbp+var_20]
0x1800027a3  movups  xmmword ptr [rdx+10h], xmm1
0x1800027a7  movsd   xmm0, [rbp+var_10]
0x1800027ac  movsd   qword ptr [rdx+20h], xmm0
0x1800027b1  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x1800027b8  add     rdx, 28h ; '('
0x1800027bc  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x1800027c3  jmp     short loc_1800027D5
0x1800027c5  lea     r8, [rbp+var_30]
0x1800027c9  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x1800027ce  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x1800027d5  mov     dword ptr [rbp+var_30], 7
0x1800027dc  lea     rax, aGnsshwavailabl; "GnssHWAvailable"
0x1800027e3  mov     qword ptr [rbp+var_30+8], rax
0x1800027e7  mov     qword ptr [rbp+var_20], 0Eh
0x1800027ef  mov     qword ptr [rbp+var_20+8], rbx
0x1800027f3  mov     byte ptr [rbp+var_10], bl
0x1800027f6  cmp     rdx, cs:qword_180012550
0x1800027fd  jz      short loc_18000282C
0x1800027ff  movups  xmm0, [rbp+var_30]
0x180002803  movups  xmmword ptr [rdx], xmm0
0x180002806  movups  xmm1, [rbp+var_20]
0x18000280a  movups  xmmword ptr [rdx+10h], xmm1
0x18000280e  movsd   xmm0, [rbp+var_10]
0x180002813  movsd   qword ptr [rdx+20h], xmm0
0x180002818  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x18000281f  add     rdx, 28h ; '('
0x180002823  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x18000282a  jmp     short loc_18000283C
0x18000282c  lea     r8, [rbp+var_30]
0x180002830  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x180002835  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x18000283c  mov     dword ptr [rbp+var_30], 8
0x180002843  lea     rax, aGnsshwgeofence; "GnssHWGeofenceTrackingActive"
0x18000284a  mov     qword ptr [rbp+var_30+8], rax
0x18000284e  mov     qword ptr [rbp+var_20], 10h
0x180002856  mov     qword ptr [rbp+var_20+8], rbx
0x18000285a  mov     byte ptr [rbp+var_10], bl
0x18000285d  cmp     rdx, cs:qword_180012550
0x180002864  jz      short loc_180002893
0x180002866  movups  xmm0, [rbp+var_30]
0x18000286a  movups  xmmword ptr [rdx], xmm0
0x18000286d  movups  xmm1, [rbp+var_20]
0x180002871  movups  xmmword ptr [rdx+10h], xmm1
0x180002875  movsd   xmm0, [rbp+var_10]
0x18000287a  movsd   qword ptr [rdx+20h], xmm0
0x18000287f  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x180002886  add     rdx, 28h ; '('
0x18000288a  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x180002891  jmp     short loc_1800028A3
0x180002893  lea     r8, [rbp+var_30]
0x180002897  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x18000289c  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x1800028a3  mov     dword ptr [rbp+var_30], 9
0x1800028aa  lea     rax, aTrackedgeofenc; "TrackedGeofencesPresent"
0x1800028b1  mov     qword ptr [rbp+var_30+8], rax
0x1800028b5  mov     qword ptr [rbp+var_20], 12h
0x1800028bd  mov     qword ptr [rbp+var_20+8], rbx
0x1800028c1  mov     byte ptr [rbp+var_10], bl
0x1800028c4  cmp     rdx, cs:qword_180012550
0x1800028cb  jz      short loc_1800028FA
0x1800028cd  movups  xmm0, [rbp+var_30]
0x1800028d1  movups  xmmword ptr [rdx], xmm0
0x1800028d4  movups  xmm1, [rbp+var_20]
0x1800028d8  movups  xmmword ptr [rdx+10h], xmm1
0x1800028dc  movsd   xmm0, [rbp+var_10]
0x1800028e1  movsd   qword ptr [rdx+20h], xmm0
0x1800028e6  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x1800028ed  add     rdx, 28h ; '('
0x1800028f1  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x1800028f8  jmp     short loc_18000290A
0x1800028fa  lea     r8, [rbp+var_30]
0x1800028fe  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x180002903  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x18000290a  mov     dword ptr [rbp+var_30], 0Ah
0x180002911  lea     rax, aInternaltracke; "InternalTrackedGeofencesPresent"
0x180002918  mov     qword ptr [rbp+var_30+8], rax
0x18000291c  mov     qword ptr [rbp+var_20], 14h
0x180002924  mov     qword ptr [rbp+var_20+8], rbx
0x180002928  mov     byte ptr [rbp+var_10], bl
0x18000292b  cmp     rdx, cs:qword_180012550
0x180002932  jz      short loc_180002961
0x180002934  movups  xmm0, [rbp+var_30]
0x180002938  movups  xmmword ptr [rdx], xmm0
0x18000293b  movups  xmm1, [rbp+var_20]
0x18000293f  movups  xmmword ptr [rdx+10h], xmm1
0x180002943  movsd   xmm0, [rbp+var_10]
0x180002948  movsd   qword ptr [rdx+20h], xmm0
0x18000294d  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x180002954  add     rdx, 28h ; '('
0x180002958  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x18000295f  jmp     short loc_180002971
0x180002961  lea     r8, [rbp+var_30]
0x180002965  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x18000296a  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x180002971  mov     dword ptr [rbp+var_30], 0Bh
0x180002978  lea     rax, aBatterysavings; "BatterySavingsOn"
0x18000297f  mov     qword ptr [rbp+var_30+8], rax
0x180002983  mov     qword ptr [rbp+var_20], 16h
0x18000298b  mov     qword ptr [rbp+var_20+8], rbx
0x18000298f  mov     byte ptr [rbp+var_10], bl
0x180002992  cmp     rdx, cs:qword_180012550
0x180002999  jz      short loc_1800029C8
0x18000299b  movups  xmm0, [rbp+var_30]
0x18000299f  movups  xmmword ptr [rdx], xmm0
0x1800029a2  movups  xmm1, [rbp+var_20]
0x1800029a6  movups  xmmword ptr [rdx+10h], xmm1
0x1800029aa  movsd   xmm0, [rbp+var_10]
0x1800029af  movsd   qword ptr [rdx+20h], xmm0
0x1800029b4  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x1800029bb  add     rdx, 28h ; '('
0x1800029bf  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x1800029c6  jmp     short loc_1800029D8
0x1800029c8  lea     r8, [rbp+var_30]
0x1800029cc  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x1800029d1  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x1800029d8  mov     dword ptr [rbp+var_30], 0Ch
0x1800029df  lea     rax, aClientoriginat; "ClientOriginatedActivityExists"
0x1800029e6  mov     qword ptr [rbp+var_30+8], rax
0x1800029ea  mov     qword ptr [rbp+var_20], 18h
0x1800029f2  mov     qword ptr [rbp+var_20+8], rbx
0x1800029f6  mov     byte ptr [rbp+var_10], bl
0x1800029f9  cmp     rdx, cs:qword_180012550
0x180002a00  jz      short loc_180002A2F
0x180002a02  movups  xmm0, [rbp+var_30]
0x180002a06  movups  xmmword ptr [rdx], xmm0
0x180002a09  movups  xmm1, [rbp+var_20]
0x180002a0d  movups  xmmword ptr [rdx+10h], xmm1
0x180002a11  movsd   xmm0, [rbp+var_10]
0x180002a16  movsd   qword ptr [rdx+20h], xmm0
0x180002a1b  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x180002a22  add     rdx, 28h ; '('
0x180002a26  mov     qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8, rdx; CLocationEnvironmentHelper const c_environmentHelper
0x180002a2d  jmp     short loc_180002A3F
0x180002a2f  lea     r8, [rbp+var_30]
0x180002a33  call    ??$_Emplace_reallocate@UBitMetadata@CLocationEnvironmentHelper@@@?$vector@UBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@AEAAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU23@$$QEAU23@@Z; std::vector<CLocationEnvironmentHelper::BitMetadata>::_Emplace_reallocate<CLocationEnvironmentHelper::BitMetadata>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata &&)
0x180002a38  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
0x180002a3f  mov     dword ptr [rbp+var_30], 0Dh
0x180002a46  lea     rax, aModernstandbya; "ModernStandbyActive"
0x180002a4d  mov     qword ptr [rbp+var_30+8], rax
0x180002a51  mov     qword ptr [rbp+var_20], 1Ah
0x180002a59  mov     qword ptr [rbp+var_20+8], rbx
0x180002a5d  mov     byte ptr [rbp+var_10], bl
0x180002a60  cmp     rdx, cs:qword_180012550
0x180002a67  jz      short loc_180002A96
0x180002a69  movups  xmm0, [rbp+var_30]
0x180002a6d  movups  xmmword ptr [rdx], xmm0
0x180002a70  movups  xmm1, [rbp+var_20]
0x180002a74  movups  xmmword ptr [rdx+10h], xmm1
0x180002a78  movsd   xmm0, [rbp+var_10]
0x180002a7d  movsd   qword ptr [rdx+20h], xmm0
0x180002a82  mov     rdx, qword ptr cs:?c_environmentHelper@@3VCLocationEnvironmentHelper@@B+8; CLocationEnvironmentHelper const c_environmentHelper
  ... truncated ...
```
