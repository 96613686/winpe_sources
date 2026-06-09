# DiscpEstablishTxFilter

- ea: `0x180015384`
- end: `0x1800156d8`
- name: `DiscpEstablishTxFilter`
- size: `852`
- prototype: `__int64 __fastcall(__int64, __int64, __int16, char, unsigned int *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010fc8`

## callees

- `0x18000bdb0`
- `0x180015384`
- `0x1800161c8`
- `0x180016230`
- `0x180016400`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x1800153db`
- `ISCSIUM!DiscpAllocMemory` at `0x180015561`
- `ISCSIUM!DiscpAllocMemory` at `0x1800153db`
- `ISCSIUM!DiscpAllocMemory` at `0x180015561`
- `ISCSIUM!DiscpFreeMemory` at `0x180015698`
- `ISCSIUM!DiscpFreeMemory` at `0x1800156b5`
- `ISCSIUM!DiscpFreeMemory` at `0x180015698`
- `ISCSIUM!DiscpFreeMemory` at `0x1800156b5`
- `WS2_32!__imp_htonl` at `0x18001542c`
- `WS2_32!__imp_htonl` at `0x18001542c`
- `WS2_32!__imp_htons` at `0x180015464`
- `WS2_32!__imp_htons` at `0x180015472`
- `WS2_32!__imp_htons` at `0x180015480`
- `WS2_32!__imp_htons` at `0x18001548e`
- `WS2_32!__imp_htons` at `0x18001549c`
- `WS2_32!__imp_htons` at `0x1800154a9`
- `WS2_32!__imp_htons` at `0x1800154b6`
- `WS2_32!__imp_htons` at `0x1800154c7`
- `WS2_32!__imp_htons` at `0x180015464`
- `WS2_32!__imp_htons` at `0x180015472`
- `WS2_32!__imp_htons` at `0x180015480`
- `WS2_32!__imp_htons` at `0x18001548e`
- `WS2_32!__imp_htons` at `0x18001549c`
- `WS2_32!__imp_htons` at `0x1800154a9`
- `WS2_32!__imp_htons` at `0x1800154b6`
- `WS2_32!__imp_htons` at `0x1800154c7`
- `fwpuclnt!FwpmFilterAdd0` at `0x18001565b`
- `fwpuclnt!FwpmFilterAdd0` at `0x18001565b`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180015674`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180015674`
- `fwpuclnt!FwpmTransactionBegin0` at `0x180015637`
- `fwpuclnt!FwpmTransactionBegin0` at `0x180015637`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18001568f`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18001568f`

## pseudocode

```c
__int64 __fastcall DiscpEstablishTxFilter(__int64 a1, __int64 a2, __int16 a3, char a4, unsigned int *a5, __int64 *a6)
{
  __int64 *v7; // rdi
  __int16 v8; // si
  wchar_t *v9; // rax
  STRSAFE_LPWSTR v10; // r15
  u_long v11; // eax
  int v12; // edx
  int v13; // ecx
  int v14; // r8d
  DWORD v15; // eax
  int v16; // r14d
  int v17; // edi
  int v18; // ebx
  u_short v19; // ax
  int v20; // ecx
  int v21; // r8d
  DWORD v22; // ebx
  unsigned int v23; // edi
  __int64 v24; // r14
  __int64 v25; // r12
  __int64 i; // rdx
  _OWORD **v27; // r10
  _OWORD *v28; // rcx
  __int64 v29; // r11
  __int64 v30; // r9
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rsi
  DWORD v34; // eax
  int v36; // [rsp+28h] [rbp-69h]
  int v37; // [rsp+30h] [rbp-61h]
  __int64 v38; // [rsp+68h] [rbp-29h]
  __int128 v39; // [rsp+70h] [rbp-21h] BYREF
  __int128 v40; // [rsp+80h] [rbp-11h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+100h] [rbp+6Fh] BYREF

  v7 = DiscpTxPolicyPFSGuid;
  if ( (a4 & 0x10) == 0 )
    v7 = DiscpTxPolicyNoPFSGuid;
  v38 = (__int64)v7;
  v8 = a3;
  v39 = 0;
  v9 = (wchar_t *)DiscpAllocMemory(136);
  pszDest = v9;
  v10 = v9;
  if ( !v9 )
    return 8;
  if ( *(_DWORD *)a1 )
  {
    htons(*(_WORD *)(a1 + 26));
    htons(*(_WORD *)(a1 + 24));
    htons(*(_WORD *)(a1 + 22));
    v16 = htons(*(_WORD *)(a1 + 20));
    htons(*(_WORD *)(a1 + 18));
    v17 = htons(*(_WORD *)(a1 + 16));
    v18 = htons(*(_WORD *)(a1 + 14));
    v19 = htons(*(_WORD *)(a1 + 12));
    v10 = pszDest;
    StringCchPrintfW(pszDest, 0x44u, L"iSCSI_Transport_filter_to_%04x:%04x:%04x:%04x:%04x:%04x:%04x:%04x", v19);
    v8 = a3;
    v40 = 0;
    v15 = DiscpFilterListIpsecTransportV6Create(
            v20,
            (unsigned int)&v40,
            v21,
            (int)a1 + 12,
            v18,
            v17,
            a3,
            v16,
            a2,
            v38,
            (__int64)&v39,
            (__int64)&v39 + 8);
  }
  else
  {
    v37 = *(unsigned __int8 *)(a1 + 6);
    v36 = *(unsigned __int8 *)(a1 + 5);
    StringCchPrintfW(v9, 0x44u, L"iSCSI_Transport_filter_to_%d.%d.%d.%d", *(unsigned __int8 *)(a1 + 4));
    v11 = htonl(*(_DWORD *)(a1 + 4));
    v15 = DiscpFilterListIpsecTransportV4Create(v13, v12, v14, v11, v36, v37, v8);
  }
  v22 = v15;
  if ( !v15 )
  {
    v23 = DWORD2(v39);
    v24 = DiscpAllocMemory((unsigned int)(16 * DWORD2(v39)));
    if ( !v24 )
    {
      v22 = 8;
      goto LABEL_31;
    }
    v25 = v39;
    for ( i = 0; (unsigned int)i < v23; i = (unsigned int)(i + 1) )
    {
      v27 = (_OWORD **)(v25 + 8 * i);
      *((_QWORD *)*v27 + 2) = v10;
      *((_QWORD *)*v27 + 3) = v10;
      *(_OWORD *)(v24 + 16LL * (unsigned int)i) = **v27;
      v28 = *v27;
      if ( *((_QWORD *)*v27 + 8) == *(_QWORD *)&FWPM_LAYER_IPSEC_V4.Data1
        && *((_QWORD *)v28 + 9) == *(_QWORD *)FWPM_LAYER_IPSEC_V4.Data4
        && *((_DWORD *)v28 + 28) )
      {
        v29 = *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4;
        v30 = 0;
        v31 = *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1;
        do
        {
          v32 = *((_QWORD *)v28 + 15);
          if ( *(_QWORD *)(v32 + 40 * v30) == v31
            && *(_QWORD *)(v32 + 40 * v30 + 8) == v29
            && *(_WORD *)(v32 + 40 * v30 + 32) == v8 )
          {
            *(GUID *)(v32 + 40 * v30) = FWPM_CONDITION_IP_REMOTE_PORT;
            v29 = *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4;
            v31 = *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1;
          }
          v28 = *v27;
          v30 = (unsigned int)(v30 + 1);
        }
        while ( (unsigned int)v30 < *((_DWORD *)*v27 + 28) );
      }
    }
    pszDest = 0;
    v22 = FwpmTransactionBegin0(DiscpEngineHandle, 0);
    if ( !v22 )
    {
      v33 = 0;
      do
      {
        if ( (unsigned int)v33 >= v23 )
          break;
        v34 = FwpmFilterAdd0(DiscpEngineHandle, *(const FWPM_FILTER0 **)(v25 + 8 * v33), 0, (UINT64 *)&pszDest);
        v33 = (unsigned int)(v33 + 1);
        v22 = v34;
      }
      while ( !v34 );
      if ( v22 )
      {
        FwpmTransactionAbort0(DiscpEngineHandle);
        goto LABEL_29;
      }
      v22 = FwpmTransactionCommit0(DiscpEngineHandle);
    }
    if ( !v22 )
    {
      *a5 = v23;
      *a6 = v24;
LABEL_31:
      DiscpFilterListDestroy(&v39, (char *)&v39 + 8);
      goto LABEL_32;
    }
LABEL_29:
    DiscpFreeMemory(v24);
    goto LABEL_31;
  }
LABEL_32:
  DiscpFreeMemory(v10);
  return v22;
}

```

## disassembly

```asm
0x180015384  mov     rax, rsp
0x180015387  mov     [rax+18h], r8w
0x18001538c  mov     [rax+10h], rdx
0x180015390  mov     [rax+8], rcx
0x180015394  push    rbp
0x180015395  push    rbx
0x180015396  push    rsi
0x180015397  push    rdi
0x180015398  push    r12
0x18001539a  push    r13
0x18001539c  push    r14
0x18001539e  push    r15
0x1800153a0  lea     rbp, [rax-4Fh]
0x1800153a4  sub     rsp, 98h
0x1800153ab  test    r9b, 10h
0x1800153af  lea     rax, DiscpTxPolicyNoPFSGuid
0x1800153b6  mov     rbx, rcx
0x1800153b9  lea     rdi, DiscpTxPolicyPFSGuid
0x1800153c0  cmovz   rdi, rax
0x1800153c4  xorps   xmm0, xmm0
0x1800153c7  mov     ecx, 88h
0x1800153cc  mov     [rbp+47h+var_70], rdi
0x1800153d0  movzx   esi, r8w
0x1800153d4  mov     r14, rdx
0x1800153d7  movups  [rbp+47h+var_68], xmm0
0x1800153db  call    cs:__imp_DiscpAllocMemory
0x1800153e1  mov     [rbp+47h+pszDest], rax
0x1800153e5  mov     r15, rax
0x1800153e8  test    rax, rax
0x1800153eb  jz      loc_1800156BD
0x1800153f1  cmp     dword ptr [rbx], 0
0x1800153f4  jnz     short loc_180015460
0x1800153f6  movzx   ecx, byte ptr [rbx+7]
0x1800153fa  movzx   edx, byte ptr [rbx+6]
0x1800153fe  movzx   r8d, byte ptr [rbx+5]
0x180015403  movzx   r9d, byte ptr [rbx+4]
0x180015408  mov     [rsp+0D0h+var_A0], ecx
0x18001540c  mov     rcx, rax; pszDest
0x18001540f  mov     [rsp+0D0h+var_A8], edx
0x180015413  mov     edx, 44h ; 'D'; cchDest
0x180015418  mov     [rsp+0D0h+var_B0], r8d
0x18001541d  lea     r8, aIscsiTransport; "iSCSI_Transport_filter_to_%d.%d.%d.%d"
0x180015424  call    StringCchPrintfW
0x180015429  mov     ecx, [rbx+4]; hostlong
0x18001542c  call    cs:__imp_htonl
0x180015432  mov     r9d, eax
0x180015435  lea     rax, [rbp+47h+var_68+8]
0x180015439  mov     [rsp+58h], rax
0x18001543e  lea     rax, [rbp+47h+var_68]
0x180015442  mov     [rsp+0D0h+var_80], rax
0x180015447  mov     [rsp+0D0h+var_88], rdi
0x18001544c  mov     [rsp+0D0h+var_90], r14
0x180015451  mov     word ptr [rsp+0D0h+var_A0], si
0x180015456  call    DiscpFilterListIpsecTransportV4Create
0x18001545b  jmp     loc_18001554E
0x180015460  movzx   ecx, word ptr [rbx+1Ah]; hostshort
0x180015464  call    cs:__imp_htons
0x18001546a  movzx   ecx, word ptr [rbx+18h]; hostshort
0x18001546e  movzx   r13d, ax
0x180015472  call    cs:__imp_htons
0x180015478  movzx   ecx, word ptr [rbx+16h]; hostshort
0x18001547c  movzx   r12d, ax
0x180015480  call    cs:__imp_htons
0x180015486  movzx   ecx, word ptr [rbx+14h]; hostshort
0x18001548a  movzx   r15d, ax
0x18001548e  call    cs:__imp_htons
0x180015494  movzx   ecx, word ptr [rbx+12h]; hostshort
0x180015498  movzx   r14d, ax
0x18001549c  call    cs:__imp_htons
0x1800154a2  movzx   ecx, word ptr [rbx+10h]; hostshort
0x1800154a6  movzx   esi, ax
0x1800154a9  call    cs:__imp_htons
0x1800154af  movzx   ecx, word ptr [rbx+0Eh]; hostshort
0x1800154b3  movzx   edi, ax
0x1800154b6  call    cs:__imp_htons
0x1800154bc  movzx   ebx, ax
0x1800154bf  mov     rax, [rbp+47h+arg_0]
0x1800154c3  movzx   ecx, word ptr [rax+0Ch]; hostshort
0x1800154c7  call    cs:__imp_htons
0x1800154cd  mov     dword ptr [rsp+0D0h+var_80], r13d
0x1800154d2  lea     r8, aIscsiTransport_0; "iSCSI_Transport_filter_to_%04x:%04x:%04"...
0x1800154d9  mov     dword ptr [rsp+0D0h+var_88], r12d
0x1800154de  mov     edx, 44h ; 'D'; cchDest
0x1800154e3  mov     dword ptr [rsp+0D0h+var_90], r15d
0x1800154e8  mov     r15, [rbp+47h+pszDest]
0x1800154ec  mov     dword ptr [rsp+0D0h+var_98], r14d
0x1800154f1  mov     rcx, r15; pszDest
0x1800154f4  mov     [rsp+0D0h+var_A0], esi
0x1800154f8  mov     [rsp+0D0h+var_A8], edi
0x1800154fc  movzx   r9d, ax
0x180015500  mov     [rsp+0D0h+var_B0], ebx
0x180015504  call    StringCchPrintfW
0x180015509  mov     r9, [rbp+47h+arg_0]
0x18001550d  lea     rax, [rbp+47h+var_68+8]
0x180015511  movzx   esi, [rbp+47h+arg_10]
0x180015515  lea     rdx, [rbp+47h+var_58]
0x180015519  mov     [rsp+58h], rax
0x18001551e  xorps   xmm0, xmm0
0x180015521  lea     rax, [rbp+47h+var_68]
0x180015525  add     r9, 0Ch
0x180015529  mov     [rsp+0D0h+var_80], rax
0x18001552e  mov     rax, [rbp+47h+var_70]
0x180015532  mov     [rsp+0D0h+var_88], rax
0x180015537  mov     rax, [rbp+47h+arg_8]
0x18001553b  mov     [rsp+0D0h+var_90], rax
0x180015540  mov     word ptr [rsp+0D0h+var_A0], si
0x180015545  movups  [rbp+47h+var_58], xmm0
0x180015549  call    DiscpFilterListIpsecTransportV6Create
0x18001554e  mov     ebx, eax
0x180015550  test    eax, eax
0x180015552  jnz     loc_1800156B2
0x180015558  mov     rdi, qword ptr [rbp+47h+var_68+8]
0x18001555c  mov     ecx, edi
0x18001555e  shl     ecx, 4
0x180015561  call    cs:__imp_DiscpAllocMemory
0x180015567  mov     r14, rax
0x18001556a  test    rax, rax
0x18001556d  jz      loc_1800156A0
0x180015573  mov     r12, qword ptr [rbp+47h+var_68]
0x180015577  xor     edx, edx
0x180015579  test    edi, edi
0x18001557b  jz      loc_180015626
0x180015581  lea     r10, [r12+rdx*8]
0x180015585  mov     ecx, edx
0x180015587  mov     rax, [r10]
0x18001558a  add     rcx, rcx
0x18001558d  mov     [rax+10h], r15
0x180015591  mov     rax, [r10]
0x180015594  mov     [rax+18h], r15
0x180015598  mov     rax, [r10]
0x18001559b  movups  xmm0, xmmword ptr [rax]
0x18001559e  movdqu  xmmword ptr [r14+rcx*8], xmm0
0x1800155a4  mov     rcx, [r10]
0x1800155a7  mov     rax, [rcx+40h]
0x1800155ab  cmp     rax, qword ptr cs:FWPM_LAYER_IPSEC_V4.Data1
0x1800155b2  jnz     short loc_18001561C
0x1800155b4  mov     rax, [rcx+48h]
0x1800155b8  cmp     rax, qword ptr cs:FWPM_LAYER_IPSEC_V4.Data4
0x1800155bf  jnz     short loc_18001561C
0x1800155c1  cmp     dword ptr [rcx+70h], 0
0x1800155c5  jbe     short loc_18001561C
0x1800155c7  mov     r11, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x1800155ce  xor     r9d, r9d
0x1800155d1  mov     rbx, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x1800155d8  mov     rax, [rcx+78h]
0x1800155dc  lea     r8, [r9+r9*4]
0x1800155e0  cmp     [rax+r8*8], rbx
0x1800155e4  jnz     short loc_180015610
0x1800155e6  cmp     [rax+r8*8+8], r11
0x1800155eb  jnz     short loc_180015610
0x1800155ed  cmp     [rax+r8*8+20h], si
0x1800155f3  jnz     short loc_180015610
0x1800155f5  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x1800155fc  movdqu  xmmword ptr [rax+r8*8], xmm0
0x180015602  mov     r11, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x180015609  mov     rbx, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x180015610  mov     rcx, [r10]
0x180015613  inc     r9d
0x180015616  cmp     r9d, [rcx+70h]
0x18001561a  jb      short loc_1800155D8
0x18001561c  inc     edx
0x18001561e  cmp     edx, edi
0x180015620  jb      loc_180015581
0x180015626  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x18001562d  xor     edx, edx; flags
0x18001562f  mov     [rbp+47h+pszDest], 0
0x180015637  call    cs:__imp_FwpmTransactionBegin0
0x18001563d  mov     ebx, eax
0x18001563f  test    eax, eax
0x180015641  jnz     short loc_18001567C
0x180015643  xor     esi, esi
0x180015645  cmp     esi, edi
0x180015647  jnb     short loc_180015669
0x180015649  mov     rdx, [r12+rsi*8]; filter
0x18001564d  lea     r9, [rbp+47h+pszDest]; id
0x180015651  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x180015658  xor     r8d, r8d; sd
0x18001565b  call    cs:__imp_FwpmFilterAdd0
0x180015661  inc     esi
0x180015663  mov     ebx, eax
0x180015665  test    eax, eax
0x180015667  jz      short loc_180015645
0x180015669  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x180015670  test    ebx, ebx
0x180015672  jnz     short loc_18001568F
0x180015674  call    cs:__imp_FwpmTransactionCommit0
0x18001567a  mov     ebx, eax
0x18001567c  test    ebx, ebx
0x18001567e  jnz     short loc_180015695
0x180015680  mov     rax, [rbp+47h+arg_20]
0x180015684  mov     [rax], edi
0x180015686  mov     rax, [rbp+47h+arg_28]
0x18001568a  mov     [rax], r14
0x18001568d  jmp     short loc_1800156A5
0x18001568f  call    cs:__imp_FwpmTransactionAbort0
0x180015695  mov     rcx, r14
0x180015698  call    cs:__imp_DiscpFreeMemory
0x18001569e  jmp     short loc_1800156A5
0x1800156a0  mov     ebx, 8
0x1800156a5  lea     rdx, [rbp+47h+var_68+8]
0x1800156a9  lea     rcx, [rbp+47h+var_68]
0x1800156ad  call    DiscpFilterListDestroy
0x1800156b2  mov     rcx, r15
0x1800156b5  call    cs:__imp_DiscpFreeMemory
0x1800156bb  jmp     short loc_1800156C2
0x1800156bd  mov     ebx, 8
0x1800156c2  mov     eax, ebx
0x1800156c4  add     rsp, 98h
0x1800156cb  pop     r15
0x1800156cd  pop     r14
0x1800156cf  pop     r13
0x1800156d1  pop     r12
0x1800156d3  pop     rdi
0x1800156d4  pop     rsi
0x1800156d5  pop     rbx
0x1800156d6  pop     rbp
0x1800156d7  retn
```
