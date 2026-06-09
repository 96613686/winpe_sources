# Dhcpv6QueryLeaseInfoArray

- ea: `0x1800016f0`
- end: `0x180001d1e`
- name: `Dhcpv6QueryLeaseInfoArray`
- size: `1582`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800016f0`
- `0x180001e30`
- `0x180001e70`
- `0x180001eb0`
- `0x180001ff0`
- `0x180002130`
- `0x1800072fc`
- `0x1800081c0`
- `0x180008220`
- `0x1800082b0`
- `0x1800082d0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800017a8`
- `RPCRT4!NdrClientCall3` at `0x1800017a8`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000794e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000794e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001871`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000191b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001946`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001871`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000191b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001946`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bc9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bc9`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800017d7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180001c1d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180001c3c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800017d7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180001c1d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180001c3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001be1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001cb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001ccb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001cec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001be1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001cb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001ccb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001cec`

## pseudocode

```c
__int64 __fastcall Dhcpv6QueryLeaseInfoArray(__int64 a1, unsigned int a2, _QWORD *a3)
{
  char *v5; // rax
  char *v6; // r15
  char *v7; // rcx
  unsigned int i; // r14d
  unsigned int Pointer; // ebx
  NET_LUID *v11; // rax
  LPVOID v12; // rax
  LPVOID v13; // rax
  LPVOID v14; // rax
  LPVOID v15; // rax
  void *v16; // rax
  __int64 v17; // r15
  char *v18; // r13
  void *v19; // rbx
  __int64 v20; // r14
  unsigned int **v21; // rsi
  char *v22; // rbx
  __int64 v23; // rax
  __int64 v24; // r14
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  void *v28; // rcx
  __int64 v29; // rax
  void *v30; // rcx
  LPWSTR CommandLineW; // rax
  __int64 v32; // rcx
  LPWSTR v33; // rax
  unsigned int v34; // r13d
  __int64 v35; // rsi
  void *v36; // rcx
  LPVOID v37; // [rsp+38h] [rbp-60h] BYREF
  char *v38; // [rsp+40h] [rbp-58h]
  char *v39; // [rsp+48h] [rbp-50h]
  __int128 v40; // [rsp+50h] [rbp-48h] BYREF
  char *v41; // [rsp+A0h] [rbp+8h]
  unsigned int v42; // [rsp+A0h] [rbp+8h]
  __int64 v43; // [rsp+A0h] [rbp+8h]
  unsigned int v45; // [rsp+B0h] [rbp+18h]
  unsigned int v46; // [rsp+B8h] [rbp+20h]

  v40 = 0;
  v37 = 0;
  *a3 = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_(a1, 57, WPP_cb48999f8e5838f952918348529d50de_Traceguids);
  if ( !a1 || !a2 )
  {
    v6 = 0;
    Pointer = 87;
    goto LABEL_43;
  }
  v5 = (char *)DhcpAlloc(56 * a2);
  v6 = v5;
  v39 = v5;
  if ( !v5 )
  {
LABEL_42:
    Pointer = 8;
    goto LABEL_43;
  }
  v7 = v5;
  v38 = v5;
  for ( i = 0; i < a2; ++i )
  {
    v41 = &v7[56 * i];
    *v41 = 0;
    v11 = (NET_LUID *)HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, 8u);
    *((_QWORD *)v41 + 1) = v11;
    if ( !v11 )
      goto LABEL_42;
    Pointer = Dhcpv6AdapterNameToIfId(*(const WCHAR **)(a1 + 8LL * i), v11);
    v46 = Pointer;
    if ( Pointer )
      goto LABEL_13;
    v12 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, 0x90u);
    *((_QWORD *)v41 + 2) = v12;
    if ( !v12 )
      goto LABEL_42;
    v13 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
    *((_QWORD *)v41 + 3) = v13;
    if ( !v13 )
      goto LABEL_42;
    v14 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
    *((_QWORD *)v41 + 4) = v14;
    if ( !v14 )
      goto LABEL_42;
    v15 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
    *((_QWORD *)v41 + 5) = v15;
    if ( !v15 )
      goto LABEL_42;
    v7 = v6;
  }
  LODWORD(v40) = a2;
  *((_QWORD *)&v40 + 1) = v6;
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(v32, 58, WPP_cb48999f8e5838f952918348529d50de_Traceguids, CommandLineW);
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xAu, 0, 0, &v40).Pointer;
  v46 = Pointer;
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    v33 = GetCommandLineW();
    WPP_SF_DS(1028, 59, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, Pointer, (__int64)v33);
  }
  if ( !Pointer )
  {
    v16 = DhcpAlloc(304LL * a2);
    v37 = v16;
    if ( v16 )
    {
      v46 = 0;
      v42 = 0;
      v17 = 0;
      v18 = v38;
      v19 = v16;
      do
      {
        v20 = (__int64)v19 + 304 * v17;
        v21 = (unsigned int **)&v18[56 * v17];
        Dhcpv6ConvertRpcLeaseInfoToLeaseInfo(v20, v21[2]);
        *(_WORD *)(v20 + 208) = *(_WORD *)v21[4];
        *(_QWORD *)(v20 + 200) = *((_QWORD *)v21[4] + 1);
        *((_QWORD *)v21[4] + 1) = 0;
        *(_WORD *)(v20 + 224) = *(_WORD *)v21[3];
        *(_QWORD *)(v20 + 216) = *((_QWORD *)v21[3] + 1);
        *((_QWORD *)v21[3] + 1) = 0;
        *(_DWORD *)(v20 + 240) = v21[5][2];
        *(_DWORD *)(v20 + 236) = v21[5][1];
        *(_BYTE *)(v20 + 235) = *((_BYTE *)v21[5] + 3);
        *(_DWORD *)(v20 + 280) = v21[5][12];
        *(_QWORD *)(v20 + 288) = *((_QWORD *)v21[5] + 7);
        *((_QWORD *)v21[5] + 7) = 0;
        *(_DWORD *)(v20 + 264) = v21[5][8];
        *(_BYTE *)(v20 + 234) = *((_BYTE *)v21[5] + 2);
        *(_QWORD *)(v20 + 272) = *((_QWORD *)v21[5] + 5);
        *((_QWORD *)v21[5] + 5) = 0;
        *(_DWORD *)(v20 + 296) = *((_DWORD *)v21 + 12);
        ++v42;
        ++v17;
      }
      while ( v42 < a2 );
      Pointer = 0;
      v6 = v18;
      *a3 = v37;
      v37 = 0;
      goto LABEL_13;
    }
    Pointer = 8;
LABEL_43:
    v46 = Pointer;
  }
LABEL_13:
  Dhcpv6FreeLeaseInfoArray(a2, &v37);
  if ( v6 )
  {
    v45 = 0;
    if ( a2 )
    {
      v22 = v6 + 40;
      v23 = 0;
      v43 = 0;
      do
      {
        v24 = 56 * v23;
        v25 = *(_QWORD *)&v22[56 * v23];
        if ( v25 )
        {
          v30 = *(void **)(v25 + 56);
          if ( v30 )
          {
            LocalFree(v30);
            *(_QWORD *)(*(_QWORD *)&v6[v24 + 40] + 56LL) = 0;
          }
        }
        v26 = *(_QWORD *)&v6[v24 + 40];
        if ( v26 && *(_QWORD *)(v26 + 40) )
        {
          if ( *(_DWORD *)(v26 + 32) )
          {
            v34 = 0;
            do
            {
              v35 = 8LL * v34;
              LocalFree(*(HLOCAL *)(*(_QWORD *)(v26 + 40) + v35));
              *(_QWORD *)(v35 + *(_QWORD *)(*(_QWORD *)&v6[v24 + 40] + 40LL)) = 0;
              ++v34;
              v26 = *(_QWORD *)&v6[v24 + 40];
            }
            while ( v34 < *(_DWORD *)(v26 + 32) );
          }
          LocalFree(*(HLOCAL *)(v26 + 40));
          *(_QWORD *)(*(_QWORD *)&v6[v24 + 40] + 40LL) = 0;
        }
        v27 = *(_QWORD *)&v6[v24 + 24];
        if ( v27 )
        {
          v28 = *(void **)(v27 + 8);
          if ( v28 )
          {
            LocalFree(v28);
            *(_QWORD *)(*(_QWORD *)&v6[v24 + 24] + 8LL) = 0;
          }
        }
        v29 = *(_QWORD *)&v6[v24 + 32];
        if ( v29 )
        {
          v36 = *(void **)(v29 + 8);
          if ( v36 )
          {
            LocalFree(v36);
            *(_QWORD *)(*(_QWORD *)&v6[v24 + 32] + 8LL) = 0;
          }
        }
        DhcpFree((LPVOID *)&v6[v24 + 8]);
        DhcpFree((LPVOID *)&v6[v24 + 16]);
        DhcpFree((LPVOID *)&v6[v24 + 24]);
        DhcpFree((LPVOID *)&v6[v24 + 32]);
        DhcpFree((LPVOID *)&v22[v24]);
        ++v45;
        v23 = ++v43;
      }
      while ( v45 < a2 );
      Pointer = v46;
    }
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v6);
  }
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_D(1028, 60, WPP_cb48999f8e5838f952918348529d50de_Traceguids, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x1800016f0  mov     [rsp+arg_10], r8
0x1800016f5  mov     [rsp+arg_8], edx
0x1800016f9  push    rbx
0x1800016fa  push    rsi
0x1800016fb  push    rdi
0x1800016fc  push    r12
0x1800016fe  push    r13
0x180001700  push    r14
0x180001702  push    r15
0x180001704  sub     rsp, 60h
0x180001708  mov     r13, r8
0x18000170b  mov     edi, edx
0x18000170d  mov     rsi, rcx
0x180001710  xorps   xmm0, xmm0
0x180001713  movups  [rsp+98h+var_48], xmm0
0x180001718  xor     r12d, r12d
0x18000171b  mov     [rsp+98h+var_60], r12
0x180001720  mov     [r8], r12
0x180001723  test    byte ptr cs:xmmword_18000F160, 10h
0x18000172a  jnz     loc_180001C07
0x180001730  test    rsi, rsi
0x180001733  jz      loc_180001C6C
0x180001739  test    edi, edi
0x18000173b  jz      loc_180001C6C
0x180001741  imul    ecx, edi, 38h ; '8'
0x180001744  call    DhcpAlloc
0x180001749  mov     r15, rax
0x18000174c  mov     [rsp+98h+var_50], rax
0x180001751  test    rax, rax
0x180001754  jz      loc_180001BF5
0x18000175a  mov     rcx, rax
0x18000175d  mov     [rsp+98h+var_58], rax
0x180001762  mov     r14d, r12d
0x180001765  cmp     r14d, edi
0x180001768  jb      loc_180001847
0x18000176e  mov     dword ptr [rsp+98h+var_48], edi
0x180001772  mov     qword ptr [rsp+98h+var_48+8], r15
0x180001777  test    byte ptr cs:xmmword_18000F160, 10h
0x18000177e  jnz     loc_180001C1D
0x180001784  mov     [rsp+98h+arg_0], r12
0x18000178c  lea     rax, [rsp+98h+var_48]
0x180001791  mov     [rsp+98h+var_78], rax
0x180001796  xor     r9d, r9d
0x180001799  xor     r8d, r8d; pReturnValue
0x18000179c  mov     edx, 0Ah; nProcNum
0x1800017a1  lea     rcx, pProxyInfo; pProxyInfo
0x1800017a8  call    cs:__imp_NdrClientCall3
0x1800017ae  mov     rbx, rax
0x1800017b1  mov     [rsp+98h+arg_18], rax
0x1800017b9  mov     [rsp+98h+arg_0], rax
0x1800017c1  mov     [rsp+98h+var_68], eax
0x1800017c5  jmp     short loc_1800017FE
0x1800017c7  mov     edi, eax
0x1800017c9  mov     ebx, eax
0x1800017cb  mov     [rsp+98h+arg_18], rbx
0x1800017d3  mov     [rsp+98h+var_68], eax
0x1800017d7  call    cs:__imp_GetCommandLineW
0x1800017dd  mov     rdx, rax
0x1800017e0  mov     ecx, ebx
0x1800017e2  call    TraceRpcException
0x1800017e7  xor     r12d, r12d
0x1800017ea  mov     r13, [rsp+98h+arg_10]
0x1800017f2  mov     edi, [rsp+98h+arg_8]
0x1800017f9  mov     r15, [rsp+98h+var_50]
0x1800017fe  test    byte ptr cs:xmmword_18000F160, 10h
0x180001805  jnz     loc_180001C3C
0x18000180b  test    ebx, ebx
0x18000180d  jz      loc_180001964
0x180001813  lea     rdx, [rsp+98h+var_60]
0x180001818  mov     ecx, edi
0x18000181a  call    Dhcpv6FreeLeaseInfoArray
0x18000181f  test    r15, r15
0x180001822  jnz     loc_180001ADE
0x180001828  test    byte ptr cs:xmmword_18000F160, 10h
0x18000182f  jnz     loc_180001D00
0x180001835  mov     eax, ebx
0x180001837  add     rsp, 60h
0x18000183b  pop     r15
0x18000183d  pop     r14
0x18000183f  pop     r13
0x180001841  pop     r12
0x180001843  pop     rdi
0x180001844  pop     rsi
0x180001845  pop     rbx
0x180001846  retn
0x180001847  mov     eax, r14d
0x18000184a  imul    rbx, rax, 38h ; '8'
0x18000184e  add     rbx, rcx
0x180001851  mov     [rsp+98h+arg_0], rbx
0x180001859  mov     [rbx], r12b
0x18000185c  mov     rcx, gs:60h
0x180001865  mov     edx, 8; dwFlags
0x18000186a  mov     r8d, edx; dwBytes
0x18000186d  mov     rcx, [rcx+30h]; hHeap
0x180001871  call    cs:__imp_HeapAlloc
0x180001877  mov     [rbx+8], rax
0x18000187b  test    rax, rax
0x18000187e  jz      loc_180001BF5
0x180001884  mov     rdx, rax
0x180001887  mov     ecx, r14d
0x18000188a  mov     rcx, [rsi+rcx*8]
0x18000188e  call    Dhcpv6AdapterNameToIfId
0x180001893  mov     ebx, eax
0x180001895  mov     [rsp+98h+arg_18], rbx
0x18000189d  test    eax, eax
0x18000189f  jnz     loc_180001813
0x1800018a5  mov     rcx, gs:60h
0x1800018ae  mov     edx, 8; dwFlags
0x1800018b3  mov     r8d, 90h; dwBytes
0x1800018b9  mov     rcx, [rcx+30h]; hHeap
0x1800018bd  call    cs:__imp_HeapAlloc
0x1800018c3  mov     rbx, [rsp+98h+arg_0]
0x1800018cb  mov     [rbx+10h], rax
0x1800018cf  test    rax, rax
0x1800018d2  jz      loc_180001BF5
0x1800018d8  mov     rcx, gs:60h
0x1800018e1  mov     edx, 8; dwFlags
0x1800018e6  mov     r8d, 10h; dwBytes
0x1800018ec  mov     rcx, [rcx+30h]; hHeap
0x1800018f0  call    cs:__imp_HeapAlloc
0x1800018f6  mov     [rbx+18h], rax
0x1800018fa  test    rax, rax
0x1800018fd  jz      loc_180001BF5
0x180001903  mov     rcx, gs:60h
0x18000190c  mov     edx, 8; dwFlags
0x180001911  mov     r8d, 10h; dwBytes
0x180001917  mov     rcx, [rcx+30h]; hHeap
0x18000191b  call    cs:__imp_HeapAlloc
0x180001921  mov     [rbx+20h], rax
0x180001925  test    rax, rax
0x180001928  jz      loc_180001BF5
0x18000192e  mov     rcx, gs:60h
0x180001937  mov     edx, 8; dwFlags
0x18000193c  mov     r8d, 40h ; '@'; dwBytes
0x180001942  mov     rcx, [rcx+30h]; hHeap
0x180001946  call    cs:__imp_HeapAlloc
0x18000194c  mov     [rbx+28h], rax
0x180001950  test    rax, rax
0x180001953  jz      loc_180001BF5
0x180001959  inc     r14d
0x18000195c  mov     rcx, r15
0x18000195f  jmp     loc_180001765
0x180001964  mov     eax, edi
0x180001966  imul    rcx, rax, 130h
0x18000196d  call    DhcpAlloc
0x180001972  mov     [rsp+98h+var_60], rax
0x180001977  test    rax, rax
0x18000197a  jz      loc_180001C65
0x180001980  mov     ebx, r12d
0x180001983  mov     [rsp+98h+arg_18], rbx
0x18000198b  mov     dword ptr [rsp+98h+arg_0], r12d
0x180001993  test    edi, edi
0x180001995  jz      loc_180001AD0
0x18000199b  mov     r15, r12
0x18000199e  mov     r13, [rsp+98h+var_58]
0x1800019a3  mov     rbx, rax
0x1800019a6  imul    r14, r15, 130h
0x1800019ad  add     r14, rbx
0x1800019b0  imul    rsi, r15, 38h ; '8'
0x1800019b4  add     rsi, r13
0x1800019b7  mov     rdx, [rsi+10h]
0x1800019bb  mov     rcx, r14
0x1800019be  call    Dhcpv6ConvertRpcLeaseInfoToLeaseInfo
0x1800019c3  mov     rax, [rsi+20h]
0x1800019c7  movzx   ecx, word ptr [rax]
0x1800019ca  mov     [r14+0D0h], cx
0x1800019d2  mov     rax, [rsi+20h]
0x1800019d6  mov     rcx, [rax+8]
0x1800019da  mov     [r14+0C8h], rcx
0x1800019e1  mov     rax, [rsi+20h]
0x1800019e5  mov     [rax+8], r12
0x1800019e9  mov     rax, [rsi+18h]
0x1800019ed  movzx   ecx, word ptr [rax]
0x1800019f0  mov     [r14+0E0h], cx
0x1800019f8  mov     rax, [rsi+18h]
0x1800019fc  mov     rcx, [rax+8]
0x180001a00  mov     [r14+0D8h], rcx
0x180001a07  mov     rax, [rsi+18h]
0x180001a0b  mov     [rax+8], r12
0x180001a0f  mov     rax, [rsi+28h]
0x180001a13  mov     ecx, [rax+8]
0x180001a16  mov     [r14+0F0h], ecx
0x180001a1d  mov     rax, [rsi+28h]
0x180001a21  mov     ecx, [rax+4]
0x180001a24  mov     [r14+0ECh], ecx
0x180001a2b  mov     rax, [rsi+28h]
0x180001a2f  movzx   ecx, byte ptr [rax+3]
0x180001a33  mov     [r14+0EBh], cl
0x180001a3a  mov     rax, [rsi+28h]
0x180001a3e  mov     ecx, [rax+30h]
0x180001a41  mov     [r14+118h], ecx
0x180001a48  mov     rax, [rsi+28h]
0x180001a4c  mov     rcx, [rax+38h]
0x180001a50  mov     [r14+120h], rcx
0x180001a57  mov     rax, [rsi+28h]
0x180001a5b  mov     [rax+38h], r12
0x180001a5f  mov     rax, [rsi+28h]
0x180001a63  mov     ecx, [rax+20h]
0x180001a66  mov     [r14+108h], ecx
0x180001a6d  mov     rax, [rsi+28h]
0x180001a71  movzx   ecx, byte ptr [rax+2]
0x180001a75  mov     [r14+0EAh], cl
0x180001a7c  mov     rax, [rsi+28h]
0x180001a80  mov     rcx, [rax+28h]
0x180001a84  mov     [r14+110h], rcx
0x180001a8b  mov     rax, [rsi+28h]
0x180001a8f  mov     [rax+28h], r12
0x180001a93  mov     eax, [rsi+30h]
0x180001a96  mov     [r14+128h], eax
0x180001a9d  mov     eax, dword ptr [rsp+98h+arg_0]
0x180001aa4  inc     eax
0x180001aa6  mov     dword ptr [rsp+98h+arg_0], eax
0x180001aad  inc     r15
0x180001ab0  cmp     eax, edi
0x180001ab2  jb      loc_1800019A6
0x180001ab8  mov     rbx, [rsp+98h+arg_18]
0x180001ac0  mov     r15, r13
0x180001ac3  mov     r13, [rsp+98h+arg_10]
0x180001acb  mov     rax, [rsp+98h+var_60]
0x180001ad0  mov     [r13+0], rax
0x180001ad4  mov     [rsp+98h+var_60], r12
0x180001ad9  jmp     loc_180001813
0x180001ade  mov     dword ptr [rsp+98h+arg_10], r12d
0x180001ae6  test    edi, edi
0x180001ae8  jz      loc_180001BB7
0x180001aee  lea     rbx, [r15+28h]
0x180001af2  mov     rax, r12
0x180001af5  mov     [rsp+98h+arg_0], rax
0x180001afd  nop     dword ptr [rax]
0x180001b00  imul    r14, rax, 38h ; '8'
0x180001b04  mov     rax, [rbx+r14]
0x180001b08  test    rax, rax
0x180001b0b  jnz     loc_180001BD4
0x180001b11  mov     rcx, [r15+r14+28h]
0x180001b16  test    rcx, rcx
0x180001b19  jz      short loc_180001B26
0x180001b1b  cmp     qword ptr [rcx+28h], 0
0x180001b20  jnz     loc_180001C76
0x180001b26  lea     r13, [r14+r15]
0x180001b2a  mov     rax, [r13+18h]
0x180001b2e  test    rax, rax
0x180001b31  jz      short loc_180001B40
0x180001b33  mov     rcx, [rax+8]; hMem
0x180001b37  test    rcx, rcx
0x180001b3a  jnz     loc_180001CCB
0x180001b40  lea     rsi, [r14+r15]
0x180001b44  mov     rax, [rsi+20h]
0x180001b48  test    rax, rax
0x180001b4b  jnz     loc_180001CDF
0x180001b51  lea     rcx, [r14+8]
0x180001b55  add     rcx, r15
0x180001b58  call    DhcpFree
0x180001b5d  lea     rcx, [r14+10h]
0x180001b61  add     rcx, r15
0x180001b64  call    DhcpFree
0x180001b69  lea     rcx, [r13+18h]
0x180001b6d  call    DhcpFree
0x180001b72  lea     rcx, [rsi+20h]
0x180001b76  call    DhcpFree
0x180001b7b  lea     rcx, [rbx+r14]
0x180001b7f  call    DhcpFree
0x180001b84  mov     ecx, dword ptr [rsp+98h+arg_10]
0x180001b8b  inc     ecx
0x180001b8d  mov     dword ptr [rsp+98h+arg_10], ecx
0x180001b94  mov     rax, [rsp+98h+arg_0]
0x180001b9c  inc     rax
0x180001b9f  mov     [rsp+98h+arg_0], rax
0x180001ba7  cmp     ecx, edi
0x180001ba9  jb      loc_180001B00
0x180001baf  mov     rbx, [rsp+98h+arg_18]
0x180001bb7  mov     rcx, gs:60h
0x180001bc0  mov     r8, r15; lpMem
0x180001bc3  xor     edx, edx; dwFlags
0x180001bc5  mov     rcx, [rcx+30h]; hHeap
0x180001bc9  call    cs:__imp_HeapFree
0x180001bcf  jmp     loc_180001828
0x180001bd4  mov     rcx, [rax+38h]; hMem
0x180001bd8  test    rcx, rcx
0x180001bdb  jz      loc_180001B11
0x180001be1  call    cs:__imp_LocalFree
0x180001be7  mov     rax, [r15+r14+28h]
0x180001bec  mov     [rax+38h], r12
0x180001bf0  jmp     loc_180001B11
0x180001bf5  mov     ebx, 8
0x180001bfa  mov     [rsp+98h+arg_18], rbx
0x180001c02  jmp     loc_180001813
0x180001c07  mov     edx, 39h ; '9'
0x180001c0c  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180001c13  call    WPP_SF_
0x180001c18  jmp     loc_180001730
0x180001c1d  call    cs:__imp_GetCommandLineW
0x180001c23  mov     r9, rax
0x180001c26  mov     edx, 3Ah ; ':'
0x180001c2b  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180001c32  call    WPP_SF_S
0x180001c37  jmp     loc_180001784
0x180001c3c  call    cs:__imp_GetCommandLineW
0x180001c42  mov     edx, 3Bh ; ';'
0x180001c47  mov     ecx, 404h
0x180001c4c  mov     [rsp+98h+var_78], rax
  ... truncated ...
```
