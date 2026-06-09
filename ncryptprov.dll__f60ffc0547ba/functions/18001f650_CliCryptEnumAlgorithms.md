# CliCryptEnumAlgorithms

- ea: `0x18001f650`
- end: `0x18001fac1`
- name: `CliCryptEnumAlgorithms`
- size: `1137`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`
- `0x18001f650`
- `0x180060f5c`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180062880`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062880`
- `RPCRT4!NdrClientCall3` at `0x18001f6d5`
- `RPCRT4!NdrClientCall3` at `0x18001f6d5`

## string_xrefs

- `0x18001f714`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18001f753`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18001f896`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18001fa68`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptEnumAlgorithms(__int64 *a1, int a2, unsigned int *a3, __int64 *a4, int a5)
{
  __int64 *v5; // r12
  _WORD **v8; // r15
  __int64 v9; // rdx
  int Pointer; // eax
  int v11; // edx
  int v12; // r8d
  unsigned int v13; // ebx
  _WORD **v15; // r11
  unsigned __int64 v16; // rsi
  unsigned int i; // r9d
  _WORD *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rax
  unsigned __int64 v21; // r8
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // r8d
  __int64 v28; // r10
  _WORD **v29; // r13
  __int64 v30; // r9
  __int64 v31; // rcx
  _WORD *v32; // rdx
  unsigned __int64 v33; // rsi
  unsigned int v34; // r11d
  _WORD *v35; // rax
  _WORD *v36; // rcx
  signed int v37; // r8d
  __int64 v38; // rcx
  unsigned __int64 v39; // r8
  _WORD *v40; // r11
  __int64 v41; // rcx
  _WORD *v42; // rax
  unsigned __int64 v43; // r11
  _QWORD *v44; // rsi
  unsigned int j; // r12d
  __int64 v46; // r9
  int v47; // [rsp+50h] [rbp-48h]
  __int64 v48; // [rsp+58h] [rbp-40h]

  v5 = a4;
  v8 = 0;
  *a4 = 0;
  *a3 = 0;
  if ( a1 )
    v9 = *a1;
  else
    v9 = 0;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            4u,
                            0,
                            g_RpcBindingContext,
                            qword_18007A5E0,
                            v9,
                            a2,
                            a3,
                            a4,
                            a5).Pointer;
  v13 = Pointer;
  if ( Pointer < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        v12,
        (unsigned int)"Status",
        Pointer,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        26);
    goto LABEL_10;
  }
  v8 = (_WORD **)*v5;
  *v5 = 0;
  v15 = v8;
  v16 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *a3 )
    {
      v26 = SafeAllocaAllocateFromHeap(v16);
      v28 = v26;
      if ( !v26 )
      {
        v13 = 14;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            v27,
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
            80);
        goto LABEL_10;
      }
      v29 = v8;
      v30 = v26;
      v31 = *a3;
      v32 = (_WORD *)(v26 + 24 * v31);
      v33 = (v16 - 24 * v31) >> 1;
      v34 = 0;
      v47 = 0;
      if ( !(_DWORD)v31 )
      {
LABEL_51:
        *v5 = v28;
        goto LABEL_10;
      }
      while ( 1 )
      {
        *(_OWORD *)v30 = *(_OWORD *)v29;
        *(_QWORD *)(v30 + 16) = v29[2];
        *(_QWORD *)v30 = 0;
        v35 = *v29;
        if ( *v29 )
        {
          v36 = 0;
          if ( !v33 || (v37 = 0, v33 > 0x7FFFFFFF) )
            v37 = -2147024809;
          if ( v37 < 0 )
          {
            if ( v33 )
              *v32 = 0;
            goto LABEL_47;
          }
          if ( v33 )
          {
            v38 = 2147483646;
            v39 = v33;
            v40 = v32;
            v48 = 0;
            do
            {
              if ( !v38 )
                break;
              if ( !*v35 )
                break;
              *v40++ = *v35++;
              --v38;
              ++v48;
              --v39;
            }
            while ( v39 );
            v41 = v48 - 1;
            if ( v39 )
              v41 = v48;
            v42 = v40 - 1;
            if ( v39 )
              v42 = v40;
            *v42 = 0;
            v37 = v39 == 0 ? 0x8007007A : 0;
            v43 = v33 - v41;
            v36 = &v32[v41];
LABEL_43:
            v5 = a4;
            if ( (int)(v37 + 0x80000000) < 0 || v37 == -2147024774 )
              v33 = v43;
            else
              v36 = 0;
            v34 = v47;
LABEL_47:
            if ( v37 >= 0 )
            {
              *(_QWORD *)v30 = v32;
              v32 = v36;
              if ( v36 )
              {
                v32 = v36 + 1;
                --v33;
              }
            }
            goto LABEL_50;
          }
          v36 = v32;
          v43 = 0;
          v37 = 0;
          if ( !*v35 )
            goto LABEL_43;
          if ( v32 )
          {
            v37 = -2147024774;
            goto LABEL_43;
          }
          v34 = v47;
        }
LABEL_50:
        v47 = ++v34;
        v29 += 3;
        v30 += 24;
        if ( v34 >= *a3 )
          goto LABEL_51;
      }
    }
    v16 += 24LL;
    v18 = *v15;
    if ( !*v15 )
      goto LABEL_23;
    v19 = 512;
    do
    {
      if ( !*v18 )
        break;
      ++v18;
      --v19;
    }
    while ( v19 );
    v20 = 2 * ((512 - v19) & -(__int64)(v19 != 0));
    if ( !v19 )
      v20 = 0;
    v13 = v19 == 0 ? 0x80070057 : 0;
    if ( !v19 )
      break;
    v21 = v16;
    v22 = v16;
    v23 = v16 + v20 + 2;
    v24 = -1;
    if ( v23 >= v16 )
      v24 = v23;
    v16 = v24;
    v25 = v23 < v22 ? 0x80070216 : 0;
    v13 = v25;
    if ( v23 < v21 )
    {
      v46 = 1347;
      goto LABEL_60;
    }
LABEL_23:
    v15 += 3;
  }
  v46 = 1340;
  v25 = 2147942487LL;
LABEL_60:
  DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", v46);
LABEL_10:
  if ( v8 )
  {
    v44 = v8;
    for ( j = 0; j < *a3; ++j )
    {
      if ( *v44 )
      {
        MSCryptFree(*v44);
        *v44 = 0;
      }
      v44 += 3;
    }
    MSCryptFree(v8);
  }
  return v13;
}

```

## disassembly

```asm
0x18001f650  mov     rax, rsp
0x18001f653  mov     [rax+8], rbx
0x18001f657  mov     [rax+10h], rsi
0x18001f65b  mov     [rax+20h], r9
0x18001f65f  mov     [rax+18h], r8
0x18001f663  push    rdi
0x18001f664  push    r12
0x18001f666  push    r13
0x18001f668  push    r14
0x18001f66a  push    r15
0x18001f66c  sub     rsp, 70h
0x18001f670  mov     r12, r9
0x18001f673  mov     r14, r8
0x18001f676  mov     r8d, edx
0x18001f679  xor     edi, edi
0x18001f67b  mov     r15d, edi
0x18001f67e  mov     [r9], rdi
0x18001f681  mov     [r14], edi
0x18001f684  test    rcx, rcx
0x18001f687  jz      loc_18001F736
0x18001f68d  mov     rdx, [rcx]
0x18001f690  mov     rcx, cs:qword_18007A5E0
0x18001f697  mov     [rsp+98h+var_40], rdi
0x18001f69c  mov     eax, [rsp+98h+arg_20]
0x18001f6a3  mov     [rsp+98h+var_50], eax
0x18001f6a7  mov     [rsp+98h+var_58], r12
0x18001f6ac  mov     [rsp+98h+var_60], r14
0x18001f6b1  mov     [rsp+98h+var_68], r8d
0x18001f6b6  mov     [rsp+98h+var_70], rdx
0x18001f6bb  mov     [rsp+98h+var_78], rcx
0x18001f6c0  mov     r9, cs:g_RpcBindingContext
0x18001f6c7  xor     r8d, r8d; pReturnValue
0x18001f6ca  lea     edx, [r8+4]; nProcNum
0x18001f6ce  lea     rcx, pProxyInfo; pProxyInfo
0x18001f6d5  call    cs:__imp_NdrClientCall3
0x18001f6dc  nop     dword ptr [rax+rax+00h]
0x18001f6e1  mov     rbx, rax
0x18001f6e4  mov     [rsp+98h+var_40], rax
0x18001f6e9  mov     [rsp+98h+var_44], ebx
0x18001f6ed  test    eax, eax
0x18001f6ef  jns     short loc_18001F73E
0x18001f6f1  lea     rax, WPP_GLOBAL_Control
0x18001f6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6ff  cmp     rcx, rax
0x18001f702  jz      short loc_18001F70A
0x18001f704  test    byte ptr [rcx+1Ch], 1
0x18001f708  jnz     short loc_18001F70C
0x18001f70a  jmp     short loc_18001F775
0x18001f70c  mov     [rsp+98h+var_68], 51Ah
0x18001f714  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f71b  mov     [rsp+98h+var_70], rax
0x18001f720  mov     dword ptr [rsp+98h+var_78], ebx
0x18001f724  lea     r9, aStatus; "Status"
0x18001f72b  mov     rcx, [rcx+10h]
0x18001f72f  call    WPP_SF_sDsd
0x18001f734  jmp     short loc_18001F70A
0x18001f736  mov     rdx, rdi
0x18001f739  jmp     loc_18001F690
0x18001f73e  jmp     short loc_18001F79B
0x18001f740  mov     ecx, eax
0x18001f742  call    HResultFromRpcException
0x18001f747  mov     ebx, eax
0x18001f749  mov     [rsp+98h+var_44], eax
0x18001f74d  mov     r9d, 51Fh
0x18001f753  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f75a  lea     rdx, aStatus; "Status"
0x18001f761  mov     ecx, eax
0x18001f763  call    DebugTraceError
0x18001f768  xor     edi, edi
0x18001f76a  mov     r14, [rsp+98h+arg_10]
0x18001f772  mov     r15d, edi
0x18001f775  test    r15, r15
0x18001f778  jnz     loc_18001FA14
0x18001f77e  mov     eax, ebx
0x18001f780  lea     r11, [rsp+98h+var_28]
0x18001f785  mov     rbx, [r11+30h]
0x18001f789  mov     rsi, [r11+38h]
0x18001f78d  mov     rsp, r11
0x18001f790  pop     r15
0x18001f792  pop     r14
0x18001f794  pop     r13
0x18001f796  pop     r12
0x18001f798  pop     rdi
0x18001f799  retn
0x18001f79b  mov     r15, [r12]
0x18001f79f  mov     [r12], rdi
0x18001f7a3  mov     r11, r15
0x18001f7a6  mov     rsi, rdi
0x18001f7a9  mov     r9d, edi
0x18001f7ac  mov     r13d, 200h
0x18001f7b2  cmp     r9d, [r14]
0x18001f7b5  jnb     loc_18001F858
0x18001f7bb  add     rsi, 18h
0x18001f7bf  mov     rax, [r11]
0x18001f7c2  test    rax, rax
0x18001f7c5  jz      loc_18001F84C
0x18001f7cb  mov     rdx, r13
0x18001f7ce  cmp     [rax], di
0x18001f7d1  jz      short loc_18001F7DD
0x18001f7d3  add     rax, 2
0x18001f7d7  sub     rdx, 1
0x18001f7db  jnz     short loc_18001F7CE
0x18001f7dd  mov     rax, rdx
0x18001f7e0  neg     rax
0x18001f7e3  sbb     r10d, r10d
0x18001f7e6  not     r10d
0x18001f7e9  and     r10d, 80070057h
0x18001f7f0  mov     rax, rdx
0x18001f7f3  mov     rcx, r13
0x18001f7f6  sub     rcx, rdx
0x18001f7f9  neg     rax
0x18001f7fc  sbb     r8, r8
0x18001f7ff  and     r8, rcx
0x18001f802  test    rdx, rdx
0x18001f805  lea     rax, [r8+r8]
0x18001f809  jz      loc_18001FA48
0x18001f80f  mov     ebx, r10d
0x18001f812  test    rdx, rdx
0x18001f815  jz      loc_18001FA58
0x18001f81b  mov     r8, rsi
0x18001f81e  mov     rcx, rsi
0x18001f821  lea     rdx, [rax+2]
0x18001f825  add     rdx, rsi
0x18001f828  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f82c  cmp     rdx, rsi
0x18001f82f  cmovnb  rax, rdx
0x18001f833  mov     rsi, rax
0x18001f836  cmp     rdx, rcx
0x18001f839  sbb     ecx, ecx
0x18001f83b  and     ecx, 80070216h
0x18001f841  mov     ebx, ecx
0x18001f843  cmp     rdx, r8
0x18001f846  jb      loc_18001FA50
0x18001f84c  inc     r9d
0x18001f84f  add     r11, 18h
0x18001f853  jmp     loc_18001F7B2
0x18001f858  mov     rcx, rsi
0x18001f85b  call    SafeAllocaAllocateFromHeap
0x18001f860  mov     r10, rax
0x18001f863  test    rax, rax
0x18001f866  jnz     short loc_18001F8BB
0x18001f868  lea     edx, [rax+0Eh]
0x18001f86b  mov     ebx, edx
0x18001f86d  lea     rax, WPP_GLOBAL_Control
0x18001f874  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f87b  cmp     rcx, rax
0x18001f87e  jz      loc_18001F775
0x18001f884  test    byte ptr [rcx+1Ch], 1
0x18001f888  jz      loc_18001F775
0x18001f88e  mov     [rsp+98h+var_68], 550h
0x18001f896  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f89d  mov     [rsp+98h+var_70], rax
0x18001f8a2  mov     dword ptr [rsp+98h+var_78], edx
0x18001f8a6  lea     r9, aStatus; "Status"
0x18001f8ad  mov     rcx, [rcx+10h]
0x18001f8b1  call    WPP_SF_sDsd
0x18001f8b6  jmp     loc_18001F775
0x18001f8bb  mov     r13, r15
0x18001f8be  mov     r9, r10
0x18001f8c1  mov     ecx, [r14]
0x18001f8c4  lea     rax, [rcx+rcx*2]
0x18001f8c8  lea     rdx, [r10+rax*8]
0x18001f8cc  sub     rsi, rdx
0x18001f8cf  add     rsi, r10
0x18001f8d2  shr     rsi, 1
0x18001f8d5  mov     r11d, edi
0x18001f8d8  mov     [rsp+98h+var_48], edi
0x18001f8dc  test    ecx, ecx
0x18001f8de  jz      loc_18001FA06
0x18001f8e4  movups  xmm0, xmmword ptr [r13+0]
0x18001f8e9  movups  xmmword ptr [r9], xmm0
0x18001f8ed  movsd   xmm1, qword ptr [r13+10h]
0x18001f8f3  movsd   qword ptr [r9+10h], xmm1
0x18001f8f9  mov     [r9], rdi
0x18001f8fc  mov     rax, [r13+0]
0x18001f900  test    rax, rax
0x18001f903  jz      loc_18001F9ED
0x18001f909  mov     rcx, rdi
0x18001f90c  mov     [rsp+98h+var_30], rcx
0x18001f911  test    rsi, rsi
0x18001f914  jz      loc_18001FA79
0x18001f91a  mov     r8d, edi
0x18001f91d  cmp     rsi, 7FFFFFFFh
0x18001f924  ja      loc_18001FA79
0x18001f92a  test    r8d, r8d
0x18001f92d  js      loc_18001FAA6
0x18001f933  test    rsi, rsi
0x18001f936  jz      loc_18001FA84
0x18001f93c  mov     ecx, 7FFFFFFEh
0x18001f941  mov     r8, rsi
0x18001f944  mov     r11, rdx
0x18001f947  mov     [rsp+98h+var_40], rdi
0x18001f94c  test    rcx, rcx
0x18001f94f  jz      short loc_18001F975
0x18001f951  movzx   r12d, word ptr [rax]
0x18001f955  test    r12w, r12w
0x18001f959  jz      short loc_18001F975
0x18001f95b  mov     [r11], r12w
0x18001f95f  add     r11, 2
0x18001f963  add     rax, 2
0x18001f967  dec     rcx
0x18001f96a  inc     [rsp+98h+var_40]
0x18001f96f  sub     r8, 1
0x18001f973  jnz     short loc_18001F94C
0x18001f975  mov     rax, [rsp+98h+var_40]
0x18001f97a  lea     rcx, [rax-1]
0x18001f97e  test    r8, r8
0x18001f981  cmovnz  rcx, rax
0x18001f985  lea     rax, [r11-2]
0x18001f989  cmovnz  rax, r11
0x18001f98d  mov     [rax], di
0x18001f990  neg     r8
0x18001f993  sbb     r8d, r8d
0x18001f996  not     r8d
0x18001f999  and     r8d, 8007007Ah
0x18001f9a0  lea     rax, [rdx+rcx*2]
0x18001f9a4  mov     r11, rsi
0x18001f9a7  sub     r11, rcx
0x18001f9aa  mov     rcx, rax
0x18001f9ad  mov     eax, 80000000h
0x18001f9b2  add     eax, r8d
0x18001f9b5  bt      eax, 1Fh
0x18001f9b9  mov     r12, [rsp+98h+arg_18]
0x18001f9c1  jb      short loc_18001FA0F
0x18001f9c3  cmp     r8d, 8007007Ah
0x18001f9ca  jz      short loc_18001FA0F
0x18001f9cc  mov     rcx, [rsp+98h+var_30]
0x18001f9d1  mov     r11d, [rsp+98h+var_48]
0x18001f9d6  test    r8d, r8d
0x18001f9d9  js      short loc_18001F9ED
0x18001f9db  mov     [r9], rdx
0x18001f9de  mov     rdx, rcx
0x18001f9e1  test    rcx, rcx
0x18001f9e4  jz      short loc_18001F9ED
0x18001f9e6  add     rdx, 2
0x18001f9ea  dec     rsi
0x18001f9ed  inc     r11d
0x18001f9f0  mov     [rsp+98h+var_48], r11d
0x18001f9f5  add     r13, 18h
0x18001f9f9  add     r9, 18h
0x18001f9fd  cmp     r11d, [r14]
0x18001fa00  jb      loc_18001F8E4
0x18001fa06  mov     [r12], r10
0x18001fa0a  jmp     loc_18001F775
0x18001fa0f  mov     rsi, r11
0x18001fa12  jmp     short loc_18001F9D1
0x18001fa14  mov     rsi, r15
0x18001fa17  mov     r12d, edi
0x18001fa1a  cmp     [r14], edi
0x18001fa1d  jbe     short loc_18001FA3B
0x18001fa1f  cmp     [rsi], rdi
0x18001fa22  jz      short loc_18001FA2F
0x18001fa24  mov     rcx, [rsi]
0x18001fa27  call    MSCryptFree
0x18001fa2c  mov     [rsi], rdi
0x18001fa2f  add     rsi, 18h
0x18001fa33  inc     r12d
0x18001fa36  cmp     r12d, [r14]
0x18001fa39  jb      short loc_18001FA1F
0x18001fa3b  mov     rcx, r15
0x18001fa3e  call    MSCryptFree
0x18001fa43  jmp     loc_18001F77E
0x18001fa48  mov     rax, rdi
0x18001fa4b  jmp     loc_18001F80F
0x18001fa50  mov     r9d, 543h
0x18001fa56  jmp     short loc_18001FA61
0x18001fa58  mov     r9d, 53Ch
0x18001fa5e  mov     ecx, r10d
0x18001fa61  lea     rdx, aStatus; "Status"
0x18001fa68  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001fa6f  call    DebugTraceError
0x18001fa74  jmp     loc_18001F775
0x18001fa79  mov     r8d, 80070057h
0x18001fa7f  jmp     loc_18001F92A
0x18001fa84  mov     rcx, rdx
0x18001fa87  mov     r11, rsi
0x18001fa8a  mov     r8d, edi
0x18001fa8d  cmp     [rax], di
0x18001fa90  jz      loc_18001F9AD
0x18001fa96  test    rdx, rdx
0x18001fa99  jz      short loc_18001FAB7
0x18001fa9b  mov     r8d, 8007007Ah
0x18001faa1  jmp     loc_18001F9AD
0x18001faa6  test    rsi, rsi
0x18001faa9  jz      loc_18001F9D6
0x18001faaf  mov     [rdx], di
0x18001fab2  jmp     loc_18001F9D6
0x18001fab7  mov     r11d, [rsp+98h+var_48]
0x18001fabc  jmp     loc_18001F9ED
0x180062872  push    rbp
0x180062874  sub     rsp, 50h
0x180062878  mov     rbp, rdx
0x18006287b  mov     rcx, [rcx]
0x18006287e  mov     ecx, [rcx]; ExceptionCode
0x180062880  call    cs:__imp_I_RpcExceptionFilter
0x180062887  nop     dword ptr [rax+rax+00h]
0x18006288c  nop
0x18006288d  add     rsp, 50h
0x180062891  pop     rbp
0x180062892  retn
  ... truncated ...
```
