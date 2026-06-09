# FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent

- ea: `0x180037ec0`
- end: `0x180038302`
- name: `FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent`
- size: `1090`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013d30`
- `0x180028c94`

## callees

- `0x18000438c`
- `0x180006e40`
- `0x180007e38`
- `0x180011060`
- `0x180011de0`
- `0x18001346a`
- `0x180020f44`
- `0x180037a70`
- `0x180037ec0`
- `0x180038308`
- `0x1800384ec`
- `0x18004703c`

## string_xrefs

- `0x1800381fb`: `FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent`
- `0x1800382d7`: `FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent`

## pseudocode

```c
__int64 __fastcall FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent(
        unsigned int a1,
        __int64 a2,
        int a3,
        unsigned int *a4,
        _QWORD *a5)
{
  int v5; // r13d
  _QWORD *v6; // rbx
  __int64 v10; // rsi
  unsigned int v11; // ebp
  int v12; // edi
  unsigned int i; // edi
  unsigned int j; // edi
  unsigned int k; // edi
  char *v16; // r15
  unsigned int v17; // r12d
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int m; // r11d
  unsigned int n; // r8d
  unsigned int ii; // r10d
  __int64 v22; // rdi
  unsigned __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int v26; // r12d
  unsigned int v27; // edx
  unsigned __int64 v28; // r15
  __int64 v29; // r8
  char *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // xmm1_8
  __int64 v33; // rcx
  unsigned int v34; // edi
  int v35; // eax
  unsigned int v36; // r15d
  __int64 v37; // rbp
  char *v38; // rbp
  unsigned int jj; // r15d
  unsigned int v41; // [rsp+20h] [rbp-58h]
  void *v42; // [rsp+28h] [rbp-50h] BYREF
  void *v43; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v44; // [rsp+80h] [rbp+8h]

  v5 = 0;
  *a4 = 0;
  v6 = 0;
  v43 = 0;
  *a5 = 0;
  v10 = 0;
  v42 = 0;
  if ( !a1 )
    goto LABEL_48;
  v10 = WfpPoolAllocNonPaged(16LL * a1);
  if ( v10 )
  {
    v6 = v43;
    goto LABEL_48;
  }
  v6 = v43;
  v11 = 0;
  memset_0(v43, 0, 16LL * a1);
  if ( a3 )
  {
    v12 = a3 - 1;
    if ( v12 )
    {
      if ( v12 == 1 )
      {
        for ( i = 0; i < a1; ++i )
        {
          v10 = FwppExpandIkeV2OutboundRootConfigToCriteria(a2 + 24LL * i, (char *)v43 + 16 * i);
          if ( v10 )
            goto LABEL_46;
          v11 += *((_DWORD *)v43 + 4 * i);
        }
      }
    }
    else
    {
      for ( j = 0; j < a1; ++j )
      {
        v10 = FwppExpandAuthIpOutboundRootConfigToCriteria(a2 + 24LL * j, (char *)v43 + 16 * j);
        if ( v10 )
          goto LABEL_46;
        v11 += *((_DWORD *)v43 + 4 * j);
      }
    }
  }
  else
  {
    for ( k = 0; k < a1; ++k )
    {
      v10 = FwppExpandIkeOutboundRootConfigToCriteria(a2 + 24LL * k, (char *)v43 + 16 * k);
      if ( v10 )
        goto LABEL_46;
      v11 += *((_DWORD *)v43 + 4 * k);
    }
  }
  v10 = WfpPoolAllocNonPaged(56LL * v11);
  if ( v10 )
  {
LABEL_48:
    v34 = 0;
    if ( a1 )
      goto LABEL_49;
    goto LABEL_62;
  }
  v16 = (char *)v42;
  v44 = 0;
  v17 = 0;
  memset_0(v42, 0, 56LL * v11);
  if ( (Feature_BugFix_BfeTvs__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BugFix_BfeTvs__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BugFix_BfeTvs__private_IsEnabledDeviceUsageNoInline();
  if ( !IsEnabledDeviceUsageNoInline )
  {
    for ( m = 0; m < 6; ++m )
    {
      for ( n = 0; n < a1; ++n )
      {
        for ( ii = 0; ii < LODWORD(v6[2 * n]); ++ii )
        {
          v22 = v6[2 * n + 1];
          v23 = (unsigned __int64)ii << 6;
          if ( *(unsigned __int16 *)(v23 + v22 + 56) == m )
          {
            v24 = 56LL * v17++;
            *(_OWORD *)&v16[v24] = *(_OWORD *)(v23 + v22);
            *(_OWORD *)&v16[v24 + 16] = *(_OWORD *)(v23 + v22 + 16);
            *(_OWORD *)&v16[v24 + 32] = *(_OWORD *)(v23 + v22 + 32);
            *(_QWORD *)&v16[v24 + 48] = *(_QWORD *)(v23 + v22 + 48);
          }
        }
      }
    }
LABEL_44:
    *a4 = v11;
    *a5 = v16;
    goto LABEL_48;
  }
  v25 = 6;
  while ( 1 )
  {
    v26 = 0;
    if ( a1 )
      break;
LABEL_43:
    if ( (unsigned int)++v5 >= 6 )
      goto LABEL_44;
  }
  while ( 1 )
  {
    if ( v6[2 * v26 + 1] )
    {
      v27 = 0;
      v41 = 0;
      if ( LODWORD(v6[2 * v26]) )
        break;
    }
LABEL_42:
    if ( ++v26 >= a1 )
      goto LABEL_43;
  }
  while ( 1 )
  {
    v28 = (unsigned __int64)v27 << 6;
    if ( *(_WORD *)(v28 + v6[2 * v26 + 1] + 56) >= 6u )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(6);
      v27 = v41;
    }
    v29 = v6[2 * v26 + 1];
    if ( *(unsigned __int16 *)(v28 + v29 + 56) != v5 )
    {
      v16 = (char *)v42;
      goto LABEL_41;
    }
    if ( v44 >= v11 )
      break;
    v30 = (char *)v42;
    v31 = 56LL * v44++;
    *(_OWORD *)((char *)v42 + v31) = *(_OWORD *)(v28 + v29);
    *(_OWORD *)&v30[v31 + 16] = *(_OWORD *)(v28 + v29 + 16);
    *(_OWORD *)&v30[v31 + 32] = *(_OWORD *)(v28 + v29 + 32);
    v32 = *(_QWORD *)(v28 + v29 + 48);
    v16 = v30;
    *(_QWORD *)&v30[v31 + 48] = v32;
LABEL_41:
    ++v27;
    v25 = 6;
    v41 = v27;
    if ( v27 >= LODWORD(v6[2 * v26]) )
      goto LABEL_42;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(v25);
  v10 = WfpReportSysErrorAsHResult(v33, "FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent", 2147942487LL);
LABEL_46:
  v34 = 0;
  do
  {
LABEL_49:
    if ( v10 )
    {
      if ( (Feature_BugFix_BfeTvs__private_featureState & 0x10) != 0 )
        v35 = Feature_BugFix_BfeTvs__private_featureState & 1;
      else
        v35 = Feature_BugFix_BfeTvs__private_IsEnabledDeviceUsageNoInline();
      if ( v35 )
      {
        if ( v6 )
        {
          v38 = (char *)&v6[2 * v34];
          if ( *((_QWORD *)v38 + 1) )
          {
            for ( jj = 0; jj < *(_DWORD *)v38; ++jj )
              FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0(*((_QWORD *)v38 + 1) + ((unsigned __int64)jj << 6));
          }
        }
      }
      else
      {
        v36 = 0;
        v37 = 2LL * v34;
        if ( LODWORD(v6[v37]) )
        {
          do
            FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0(v6[v37 + 1] + ((unsigned __int64)v36++ << 6));
          while ( v36 < LODWORD(v6[2 * v34]) );
        }
      }
    }
    WfpMemFree(&v6[2 * v34++ + 1]);
  }
  while ( v34 < a1 );
LABEL_62:
  WfpMemFree(&v43);
  if ( v10 )
  {
    WfpMemFree(&v42);
    WfpReportError(v10, "FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent");
  }
  return v10;
}

```

## disassembly

```asm
0x180037ec0  mov     r11, rsp
0x180037ec3  mov     [r11+10h], rbx
0x180037ec7  mov     [r11+20h], r9
0x180037ecb  push    rbp
0x180037ecc  push    rsi
0x180037ecd  push    rdi
0x180037ece  push    r12
0x180037ed0  push    r13
0x180037ed2  push    r14
0x180037ed4  push    r15
0x180037ed6  sub     rsp, 40h
0x180037eda  mov     rax, [rsp+78h+arg_20]
0x180037ee2  xor     r13d, r13d
0x180037ee5  mov     [r9], r13d
0x180037ee8  mov     ebx, r13d
0x180037eeb  mov     r14d, ecx
0x180037eee  mov     edi, r8d
0x180037ef1  mov     [r11-48h], rbx
0x180037ef5  mov     r12, rdx
0x180037ef8  mov     [rax], r13
0x180037efb  mov     esi, r13d
0x180037efe  mov     [r11-50h], r13
0x180037f02  test    ecx, ecx
0x180037f04  jz      loc_180038217
0x180037f0a  mov     ebx, r14d
0x180037f0d  lea     r8, [r11-48h]
0x180037f11  shl     rbx, 4
0x180037f15  mov     rcx, rbx; dwBytes
0x180037f18  call    WfpPoolAllocNonPaged
0x180037f1d  mov     rsi, rax
0x180037f20  test    rax, rax
0x180037f23  jnz     loc_180038212
0x180037f29  mov     r8, rbx; Size
0x180037f2c  xor     edx, edx; Val
0x180037f2e  mov     rbx, [rsp+78h+var_48]
0x180037f33  mov     ebp, r13d
0x180037f36  mov     rcx, rbx; void *
0x180037f39  call    memset_0
0x180037f3e  test    edi, edi
0x180037f40  jz      loc_180037FD0
0x180037f46  sub     edi, 1
0x180037f49  jz      short loc_180037F94
0x180037f4b  cmp     edi, 1
0x180037f4e  jnz     loc_18003800A
0x180037f54  mov     edi, r13d
0x180037f57  test    r14d, r14d
0x180037f5a  jz      loc_18003800A
0x180037f60  mov     ecx, edi
0x180037f62  mov     r15d, edi
0x180037f65  shl     r15, 4
0x180037f69  add     r15, rbx
0x180037f6c  lea     rax, [rcx+rcx*2]
0x180037f70  mov     rdx, r15
0x180037f73  lea     rcx, [r12+rax*8]
0x180037f77  call    FwppExpandIkeV2OutboundRootConfigToCriteria
0x180037f7c  mov     rsi, rax
0x180037f7f  test    rax, rax
0x180037f82  jnz     loc_18003820D
0x180037f88  add     ebp, [r15]
0x180037f8b  inc     edi
0x180037f8d  cmp     edi, r14d
0x180037f90  jb      short loc_180037F60
0x180037f92  jmp     short loc_18003800A
0x180037f94  mov     edi, r13d
0x180037f97  test    r14d, r14d
0x180037f9a  jz      short loc_18003800A
0x180037f9c  mov     ecx, edi
0x180037f9e  mov     r15d, edi
0x180037fa1  shl     r15, 4
0x180037fa5  add     r15, rbx
0x180037fa8  lea     rax, [rcx+rcx*2]
0x180037fac  mov     rdx, r15
0x180037faf  lea     rcx, [r12+rax*8]
0x180037fb3  call    FwppExpandAuthIpOutboundRootConfigToCriteria
0x180037fb8  mov     rsi, rax
0x180037fbb  test    rax, rax
0x180037fbe  jnz     loc_18003820D
0x180037fc4  add     ebp, [r15]
0x180037fc7  inc     edi
0x180037fc9  cmp     edi, r14d
0x180037fcc  jb      short loc_180037F9C
0x180037fce  jmp     short loc_18003800A
0x180037fd0  mov     edi, r13d
0x180037fd3  test    r14d, r14d
0x180037fd6  jz      short loc_18003800A
0x180037fd8  mov     ecx, edi
0x180037fda  mov     r15d, edi
0x180037fdd  shl     r15, 4
0x180037fe1  add     r15, rbx
0x180037fe4  lea     rax, [rcx+rcx*2]
0x180037fe8  mov     rdx, r15
0x180037feb  lea     rcx, [r12+rax*8]
0x180037fef  call    FwppExpandIkeOutboundRootConfigToCriteria
0x180037ff4  mov     rsi, rax
0x180037ff7  test    rax, rax
0x180037ffa  jnz     loc_18003820D
0x180038000  add     ebp, [r15]
0x180038003  inc     edi
0x180038005  cmp     edi, r14d
0x180038008  jb      short loc_180037FD8
0x18003800a  mov     eax, ebp
0x18003800c  lea     r8, [rsp+78h+var_50]
0x180038011  imul    rdi, rax, 38h ; '8'
0x180038015  mov     rcx, rdi; dwBytes
0x180038018  call    WfpPoolAllocNonPaged
0x18003801d  mov     rsi, rax
0x180038020  test    rax, rax
0x180038023  jnz     loc_180038217
0x180038029  mov     r15, [rsp+78h+var_50]
0x18003802e  mov     r8, rdi; Size
0x180038031  mov     rcx, r15; void *
0x180038034  mov     [rsp+78h+arg_0], r13d
0x18003803c  xor     edx, edx; Val
0x18003803e  mov     r12d, r13d
0x180038041  call    memset_0
0x180038046  mov     eax, cs:Feature_BugFix_BfeTvs__private_featureState
0x18003804c  test    al, 10h
0x18003804e  jz      short loc_180038055
0x180038050  and     eax, 1
0x180038053  jmp     short loc_18003805A
0x180038055  call    Feature_BugFix_BfeTvs__private_IsEnabledDeviceUsageNoInline
0x18003805a  test    eax, eax
0x18003805c  jnz     loc_1800380F0
0x180038062  mov     r11d, r13d
0x180038065  mov     r8d, r13d
0x180038068  test    r14d, r14d
0x18003806b  jz      short loc_1800380DE
0x18003806d  mov     edx, r8d
0x180038070  mov     r10d, r13d
0x180038073  add     rdx, rdx
0x180038076  cmp     [rbx+rdx*8], r13d
0x18003807a  jbe     short loc_1800380D6
0x18003807c  mov     rdi, [rbx+rdx*8+8]
0x180038081  mov     r9d, r10d
0x180038084  shl     r9, 6
0x180038088  movzx   eax, word ptr [r9+rdi+38h]
0x18003808e  cmp     eax, r11d
0x180038091  jnz     short loc_1800380CD
0x180038093  movups  xmm0, xmmword ptr [r9+rdi]
0x180038098  mov     eax, r12d
0x18003809b  imul    rcx, rax, 38h ; '8'
0x18003809f  inc     r12d
0x1800380a2  movups  xmmword ptr [rcx+r15], xmm0
0x1800380a7  movups  xmm1, xmmword ptr [r9+rdi+10h]
0x1800380ad  movups  xmmword ptr [rcx+r15+10h], xmm1
0x1800380b3  movups  xmm0, xmmword ptr [r9+rdi+20h]
0x1800380b9  movups  xmmword ptr [rcx+r15+20h], xmm0
0x1800380bf  movsd   xmm1, qword ptr [r9+rdi+30h]
0x1800380c6  movsd   qword ptr [rcx+r15+30h], xmm1
0x1800380cd  inc     r10d
0x1800380d0  cmp     r10d, [rbx+rdx*8]
0x1800380d4  jb      short loc_18003807C
0x1800380d6  inc     r8d
0x1800380d9  cmp     r8d, r14d
0x1800380dc  jb      short loc_18003806D
0x1800380de  inc     r11d
0x1800380e1  cmp     r11d, 6
0x1800380e5  jb      loc_180038065
0x1800380eb  jmp     loc_1800381D9
0x1800380f0  mov     ecx, 6
0x1800380f5  xor     r12d, r12d
0x1800380f8  test    r14d, r14d
0x1800380fb  jz      loc_1800381CA
0x180038101  mov     edi, r12d
0x180038104  add     rdi, rdi
0x180038107  cmp     qword ptr [rbx+rdi*8+8], 0
0x18003810d  jz      loc_1800381BE
0x180038113  xor     edx, edx
0x180038115  mov     [rsp+78h+var_58], edx
0x180038119  cmp     [rbx+rdi*8], edx
0x18003811c  jbe     loc_1800381BE
0x180038122  mov     rax, [rbx+rdi*8+8]
0x180038127  mov     r15d, edx
0x18003812a  shl     r15, 6
0x18003812e  cmp     [r15+rax+38h], cx
0x180038134  jb      short loc_18003813F
0x180038136  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003813b  mov     edx, [rsp+78h+var_58]
0x18003813f  mov     r8, [rbx+rdi*8+8]
0x180038144  movzx   eax, word ptr [r15+r8+38h]
0x18003814a  cmp     eax, r13d
0x18003814d  jnz     short loc_1800381A5
0x18003814f  mov     r9d, [rsp+78h+arg_0]
0x180038157  cmp     r9d, ebp
0x18003815a  jnb     loc_1800381F0
0x180038160  movups  xmm0, xmmword ptr [r15+r8]
0x180038165  mov     rax, [rsp+78h+var_50]
0x18003816a  imul    rcx, r9, 38h ; '8'
0x18003816e  inc     r9d
0x180038171  mov     [rsp+78h+arg_0], r9d
0x180038179  movups  xmmword ptr [rcx+rax], xmm0
0x18003817d  movups  xmm1, xmmword ptr [r15+r8+10h]
0x180038183  movups  xmmword ptr [rcx+rax+10h], xmm1
0x180038188  movups  xmm0, xmmword ptr [r15+r8+20h]
0x18003818e  movups  xmmword ptr [rcx+rax+20h], xmm0
0x180038193  movsd   xmm1, qword ptr [r15+r8+30h]
0x18003819a  mov     r15, rax
0x18003819d  movsd   qword ptr [rcx+rax+30h], xmm1
0x1800381a3  jmp     short loc_1800381AA
0x1800381a5  mov     r15, [rsp+78h+var_50]
0x1800381aa  inc     edx
0x1800381ac  mov     ecx, 6
0x1800381b1  mov     [rsp+78h+var_58], edx
0x1800381b5  cmp     edx, [rbx+rdi*8]
0x1800381b8  jb      loc_180038122
0x1800381be  inc     r12d
0x1800381c1  cmp     r12d, r14d
0x1800381c4  jb      loc_180038101
0x1800381ca  inc     r13d
0x1800381cd  cmp     r13d, ecx
0x1800381d0  jb      loc_1800380F5
0x1800381d6  xor     r13d, r13d
0x1800381d9  mov     rax, [rsp+78h+arg_18]
0x1800381e1  mov     [rax], ebp
0x1800381e3  mov     rax, [rsp+78h+arg_20]
0x1800381eb  mov     [rax], r15
0x1800381ee  jmp     short loc_180038217
0x1800381f0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800381f5  mov     r8d, 80070057h
0x1800381fb  lea     rdx, aFwppexpandcert_0; "FwppExpandCertAuthRootConfig0ArrayOutTo"...
0x180038202  call    WfpReportSysErrorAsHResult
0x180038207  mov     rsi, rax
0x18003820a  xor     r13d, r13d
0x18003820d  mov     edi, r13d
0x180038210  jmp     short loc_180038223
0x180038212  mov     rbx, [rsp+78h+var_48]
0x180038217  mov     edi, r13d
0x18003821a  test    r14d, r14d
0x18003821d  jz      loc_1800382BE
0x180038223  test    rsi, rsi
0x180038226  jz      short loc_1800382A1
0x180038228  mov     eax, cs:Feature_BugFix_BfeTvs__private_featureState
0x18003822e  test    al, 10h
0x180038230  jz      short loc_180038237
0x180038232  and     eax, 1
0x180038235  jmp     short loc_18003823C
0x180038237  call    Feature_BugFix_BfeTvs__private_IsEnabledDeviceUsageNoInline
0x18003823c  test    eax, eax
0x18003823e  jnz     short loc_18003826B
0x180038240  mov     ebp, edi
0x180038242  mov     r15d, r13d
0x180038245  shl     rbp, 4
0x180038249  cmp     [rbx+rbp], r13d
0x18003824d  jbe     short loc_1800382A1
0x18003824f  mov     ecx, r15d
0x180038252  shl     rcx, 6
0x180038256  add     rcx, [rbx+rbp+8]
0x18003825b  call    FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0
0x180038260  inc     r15d
0x180038263  cmp     r15d, [rbx+rbp]
0x180038267  jb      short loc_18003824F
0x180038269  jmp     short loc_1800382A1
0x18003826b  test    rbx, rbx
0x18003826e  jz      short loc_1800382A1
0x180038270  mov     ebp, edi
0x180038272  shl     rbp, 4
0x180038276  add     rbp, rbx
0x180038279  cmp     [rbp+8], r13
0x18003827d  jz      short loc_1800382A1
0x18003827f  mov     r15d, r13d
0x180038282  cmp     [rbp+0], r13d
0x180038286  jbe     short loc_1800382A1
0x180038288  mov     ecx, r15d
0x18003828b  shl     rcx, 6
0x18003828f  add     rcx, [rbp+8]
0x180038293  call    FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0
0x180038298  inc     r15d
0x18003829b  cmp     r15d, [rbp+0]
0x18003829f  jb      short loc_180038288
0x1800382a1  mov     ecx, edi
0x1800382a3  shl     rcx, 4
0x1800382a7  add     rcx, 8
0x1800382ab  add     rcx, rbx
0x1800382ae  call    WfpMemFree
0x1800382b3  inc     edi
0x1800382b5  cmp     edi, r14d
0x1800382b8  jb      loc_180038223
0x1800382be  lea     rcx, [rsp+78h+var_48]
0x1800382c3  call    WfpMemFree
0x1800382c8  test    rsi, rsi
0x1800382cb  jz      short loc_1800382E6
0x1800382cd  lea     rcx, [rsp+78h+var_50]
0x1800382d2  call    WfpMemFree
0x1800382d7  lea     rdx, aFwppexpandcert_0; "FwppExpandCertAuthRootConfig0ArrayOutTo"...
0x1800382de  mov     rcx, rsi
0x1800382e1  call    WfpReportError
0x1800382e6  mov     rbx, [rsp+78h+arg_8]
0x1800382ee  mov     rax, rsi
0x1800382f1  add     rsp, 40h
0x1800382f5  pop     r15
0x1800382f7  pop     r14
0x1800382f9  pop     r13
0x1800382fb  pop     r12
0x1800382fd  pop     rdi
0x1800382fe  pop     rsi
0x1800382ff  pop     rbp
0x180038300  retn
```
