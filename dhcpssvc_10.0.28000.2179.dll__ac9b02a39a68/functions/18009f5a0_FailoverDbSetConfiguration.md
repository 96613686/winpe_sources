# FailoverDbSetConfiguration

- ea: `0x18009f5a0`
- end: `0x18009fa2a`
- name: `FailoverDbSetConfiguration`
- size: `1162`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18009de98`

## callees

- `0x180003228`
- `0x18009f5a0`
- `0x1800a03f0`
- `0x1800a0448`
- `0x1800a0b3c`
- `0x1800a0b68`
- `0x1800a0bac`

## import_xrefs

- `msvcrt!time` at `0x18009f971`
- `msvcrt!time` at `0x18009f971`
- `ESENT!JetCommitTransaction` at `0x18009f9dd`
- `ESENT!JetCommitTransaction` at `0x18009f9dd`
- `KERNEL32!HeapAlloc` at `0x18009f8d4`
- `KERNEL32!HeapAlloc` at `0x18009f8d4`
- `KERNEL32!HeapFree` at `0x18009f9c4`
- `KERNEL32!HeapFree` at `0x18009f9c4`

## string_xrefs

- `0x18009f9eb`: `DhcpDALJetCommitTransaction`

## pseudocode

```c
__int64 __fastcall FailoverDbSetConfiguration(JET_SESID sesid, _QWORD *a2)
{
  _WORD *v4; // rax
  __int64 v6; // rbp
  __int64 v7; // rcx
  __int64 v8; // r14
  unsigned int v9; // ebx
  __int64 v10; // r9
  unsigned int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  _WORD *v14; // rax
  unsigned int v15; // eax
  __int64 v16; // r9
  _WORD *v17; // rax
  unsigned int v18; // eax
  _DWORD *v19; // rax
  unsigned __int64 v20; // rbp
  _DWORD *v21; // r14
  __int64 v22; // rax
  unsigned int i; // r8d
  __int64 v24; // rdx
  unsigned int v25; // eax
  int v26; // [rsp+70h] [rbp+18h] BYREF

  v26 = 0;
  v4 = (_WORD *)a2[4];
  if ( !v4 )
    return 87;
  v6 = 2147483646;
  v7 = 2147483646;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v7;
  }
  while ( v7 );
  if ( !v7 )
    return 87;
  v8 = (2 * (2147483646 - v7)) & -(__int64)(v7 != 0);
  v9 = DhcpDALJetBeginTransaction(sesid);
  if ( v9 )
    goto LABEL_45;
  v10 = a2[4];
  v11 = 0;
  if ( v10 )
    v11 = v8 + 2;
  v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9358, v10, v11);
  if ( v9 )
    goto LABEL_45;
  v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F93D0, (int)a2 + 12, 4u);
  if ( v9 )
    goto LABEL_45;
  v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9448, (int)a2 + 24, 4u);
  if ( v9 )
    goto LABEL_45;
  v12 = a2[5];
  if ( v12 )
  {
    v13 = 2147483646;
    v14 = (_WORD *)a2[5];
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v13;
    }
    while ( v13 );
    if ( !v13 )
      return 87;
    v15 = v13 != 0 ? -4 - 2 * v13 + 2 : 2;
  }
  else
  {
    v15 = 0;
  }
  v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9388, v12, v15);
  if ( v9 )
    goto LABEL_45;
  v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9370, (_DWORD)a2, 4u);
  if ( v9 )
    goto LABEL_45;
  v16 = a2[6];
  if ( !v16 )
  {
    v18 = 0;
    goto LABEL_31;
  }
  v17 = (_WORD *)a2[6];
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v6;
  }
  while ( v6 );
  if ( v6 )
  {
    v18 = v6 != 0 ? -4 - 2 * v6 + 2 : 2;
LABEL_31:
    v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F93B8, v16, v18);
    if ( !v9 )
    {
      v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F93A0, (int)a2 + 4, 4u);
      if ( !v9 )
      {
        v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9460, (int)a2 + 28, 4u);
        if ( !v9 )
        {
          v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F93E8, (int)a2 + 8, 4u);
          if ( !v9 )
          {
            v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9400, (int)a2 + 64, 1u);
            if ( !v9 )
            {
              v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9418, (int)a2 + 16, 4u);
              if ( !v9 )
              {
                v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9430, (int)a2 + 20, 4u);
                if ( !v9 )
                {
                  v19 = (_DWORD *)a2[7];
                  if ( !v19 || !*v19 )
                    goto LABEL_53;
                  v20 = 4LL * (unsigned int)*v19;
                  if ( v20 <= 0xFFFFFFFF )
                  {
                    v9 = 8;
                    v21 = HeapAlloc(gDhcpHeap, 8u, (unsigned int)v20);
                    if ( !v21 )
                    {
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
                      {
                        WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          11,
                          &WPP_69eab83df91b31eacaf8ec0f641a7f07_Traceguids);
                      }
                      goto LABEL_45;
                    }
                    v22 = a2[7];
                    for ( i = 0; i < *(_DWORD *)v22; v22 = a2[7] )
                    {
                      v24 = i++;
                      v21[v24] = *(_DWORD *)(*(_QWORD *)(v22 + 8) + 4 * v24);
                    }
                    v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9478, (_DWORD)v21, v20);
                    if ( !v9 )
                    {
                      v26 = time(0);
                      v9 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9490, (unsigned int)&v26, 4u);
                      if ( !v9 )
                        v9 = DhcpDALJetCommitUpdate(sesid, FailoverConfTableHandle);
                    }
                    HeapFree(gDhcpHeap, 0, v21);
                    if ( v9 )
                      goto LABEL_45;
LABEL_53:
                    v25 = JetCommitTransaction(sesid, 0);
                    return (unsigned int)DhcpDALMapJetError(v25, "DhcpDALJetCommitTransaction");
                  }
                  v9 = 534;
                }
              }
            }
          }
        }
      }
    }
LABEL_45:
    DhcpDALJetRollback(sesid);
    return v9;
  }
  return 87;
}

```

## disassembly

```asm
0x18009f5a0  mov     rax, rsp
0x18009f5a3  mov     [rax+8], rbx
0x18009f5a7  mov     [rax+10h], rbp
0x18009f5ab  mov     [rax+18h], r8d
0x18009f5af  push    rsi
0x18009f5b0  push    rdi
0x18009f5b1  push    r12
0x18009f5b3  push    r14
0x18009f5b5  push    r15
0x18009f5b7  sub     rsp, 30h
0x18009f5bb  xor     r15d, r15d
0x18009f5be  mov     rsi, rdx
0x18009f5c1  mov     [rax+18h], r15d
0x18009f5c5  mov     rdi, rcx
0x18009f5c8  mov     rax, [rdx+20h]
0x18009f5cc  test    rax, rax
0x18009f5cf  jnz     short loc_18009F5DA
0x18009f5d1  lea     eax, [r15+57h]
0x18009f5d5  jmp     loc_18009FA12
0x18009f5da  mov     ebp, 7FFFFFFEh
0x18009f5df  mov     ecx, ebp
0x18009f5e1  cmp     [rax], r15w
0x18009f5e5  jz      short loc_18009F5F1
0x18009f5e7  add     rax, 2
0x18009f5eb  sub     rcx, 1
0x18009f5ef  jnz     short loc_18009F5E1
0x18009f5f1  test    rcx, rcx
0x18009f5f4  jz      loc_18009FA08
0x18009f5fa  mov     rax, rbp
0x18009f5fd  sub     rax, rcx
0x18009f600  add     rax, rax
0x18009f603  neg     rcx
0x18009f606  mov     rcx, rdi
0x18009f609  sbb     r14, r14
0x18009f60c  and     r14, rax
0x18009f60f  call    DhcpDALJetBeginTransaction
0x18009f614  mov     ebx, eax
0x18009f616  test    eax, eax
0x18009f618  jnz     loc_18009F917
0x18009f61e  mov     r9, [rsi+20h]
0x18009f622  mov     eax, r15d
0x18009f625  test    r9, r9
0x18009f628  jz      short loc_18009F62E
0x18009f62a  lea     eax, [r14+2]
0x18009f62e  mov     r8d, cs:dword_1800F9358
0x18009f635  mov     rcx, rdi
0x18009f638  mov     rdx, cs:FailoverConfTableHandle
0x18009f63f  mov     [rsp+58h+var_38], eax
0x18009f643  call    DhcpDALJetSetValue
0x18009f648  mov     ebx, eax
0x18009f64a  test    eax, eax
0x18009f64c  jnz     loc_18009F917
0x18009f652  mov     r8d, cs:dword_1800F93D0
0x18009f659  lea     r12d, [rax+4]
0x18009f65d  mov     rdx, cs:FailoverConfTableHandle
0x18009f664  lea     r9, [rsi+0Ch]
0x18009f668  mov     rcx, rdi
0x18009f66b  mov     [rsp+58h+var_38], r12d
0x18009f670  call    DhcpDALJetSetValue
0x18009f675  mov     ebx, eax
0x18009f677  test    eax, eax
0x18009f679  jnz     loc_18009F917
0x18009f67f  mov     r8d, cs:dword_1800F9448
0x18009f686  lea     r9, [rsi+18h]
0x18009f68a  mov     rdx, cs:FailoverConfTableHandle
0x18009f691  mov     rcx, rdi
0x18009f694  mov     [rsp+58h+var_38], r12d
0x18009f699  call    DhcpDALJetSetValue
0x18009f69e  mov     ebx, eax
0x18009f6a0  test    eax, eax
0x18009f6a2  jnz     loc_18009F917
0x18009f6a8  mov     r9, [rsi+28h]
0x18009f6ac  mov     r14d, 0FFFFFFFCh
0x18009f6b2  test    r9, r9
0x18009f6b5  jz      short loc_18009F6EE
0x18009f6b7  mov     rdx, rbp
0x18009f6ba  mov     rax, r9
0x18009f6bd  cmp     [rax], r15w
0x18009f6c1  jz      short loc_18009F6CD
0x18009f6c3  add     rax, 2
0x18009f6c7  sub     rdx, 1
0x18009f6cb  jnz     short loc_18009F6BD
0x18009f6cd  test    rdx, rdx
0x18009f6d0  jz      short loc_18009F6E6
0x18009f6d2  lea     eax, [rdx+rdx]
0x18009f6d5  mov     ecx, r14d
0x18009f6d8  sub     ecx, eax
0x18009f6da  neg     rdx
0x18009f6dd  sbb     eax, eax
0x18009f6df  and     eax, ecx
0x18009f6e1  add     eax, 2
0x18009f6e4  jmp     short loc_18009F6F1
0x18009f6e6  neg     rdx
0x18009f6e9  jmp     loc_18009FA0B
0x18009f6ee  mov     eax, r15d
0x18009f6f1  mov     r8d, cs:dword_1800F9388
0x18009f6f8  mov     rcx, rdi
0x18009f6fb  mov     rdx, cs:FailoverConfTableHandle
0x18009f702  mov     [rsp+58h+var_38], eax
0x18009f706  call    DhcpDALJetSetValue
0x18009f70b  mov     ebx, eax
0x18009f70d  test    eax, eax
0x18009f70f  jnz     loc_18009F917
0x18009f715  mov     r8d, cs:dword_1800F9370
0x18009f71c  mov     r9, rsi
0x18009f71f  mov     rdx, cs:FailoverConfTableHandle
0x18009f726  mov     rcx, rdi
0x18009f729  mov     [rsp+58h+var_38], r12d
0x18009f72e  call    DhcpDALJetSetValue
0x18009f733  mov     ebx, eax
0x18009f735  test    eax, eax
0x18009f737  jnz     loc_18009F917
0x18009f73d  mov     r9, [rsi+30h]
0x18009f741  test    r9, r9
0x18009f744  jz      short loc_18009F77D
0x18009f746  mov     rax, r9
0x18009f749  cmp     [rax], r15w
0x18009f74d  jz      short loc_18009F759
0x18009f74f  add     rax, 2
0x18009f753  sub     rbp, 1
0x18009f757  jnz     short loc_18009F749
0x18009f759  test    rbp, rbp
0x18009f75c  jz      short loc_18009F775
0x18009f75e  lea     eax, ds:0[rbp*2]
0x18009f765  sub     r14d, eax
0x18009f768  neg     rbp
0x18009f76b  sbb     eax, eax
0x18009f76d  and     eax, r14d
0x18009f770  add     eax, 2
0x18009f773  jmp     short loc_18009F780
0x18009f775  neg     rbp
0x18009f778  jmp     loc_18009FA0B
0x18009f77d  mov     eax, r15d
0x18009f780  mov     r8d, cs:dword_1800F93B8
0x18009f787  mov     rcx, rdi
0x18009f78a  mov     rdx, cs:FailoverConfTableHandle
0x18009f791  mov     [rsp+58h+var_38], eax
0x18009f795  call    DhcpDALJetSetValue
0x18009f79a  mov     ebx, eax
0x18009f79c  test    eax, eax
0x18009f79e  jnz     loc_18009F917
0x18009f7a4  mov     r8d, cs:dword_1800F93A0
0x18009f7ab  lea     r9, [rsi+4]
0x18009f7af  mov     rdx, cs:FailoverConfTableHandle
0x18009f7b6  mov     rcx, rdi
0x18009f7b9  mov     [rsp+58h+var_38], r12d
0x18009f7be  call    DhcpDALJetSetValue
0x18009f7c3  mov     ebx, eax
0x18009f7c5  test    eax, eax
0x18009f7c7  jnz     loc_18009F917
0x18009f7cd  mov     r8d, cs:dword_1800F9460
0x18009f7d4  lea     r9, [rsi+1Ch]
0x18009f7d8  mov     rdx, cs:FailoverConfTableHandle
0x18009f7df  mov     rcx, rdi
0x18009f7e2  mov     [rsp+58h+var_38], r12d
0x18009f7e7  call    DhcpDALJetSetValue
0x18009f7ec  mov     ebx, eax
0x18009f7ee  test    eax, eax
0x18009f7f0  jnz     loc_18009F917
0x18009f7f6  mov     r8d, cs:dword_1800F93E8
0x18009f7fd  lea     r9, [rsi+8]
0x18009f801  mov     rdx, cs:FailoverConfTableHandle
0x18009f808  mov     rcx, rdi
0x18009f80b  mov     [rsp+58h+var_38], r12d
0x18009f810  call    DhcpDALJetSetValue
0x18009f815  mov     ebx, eax
0x18009f817  test    eax, eax
0x18009f819  jnz     loc_18009F917
0x18009f81f  mov     r8d, cs:dword_1800F9400
0x18009f826  lea     r9, [rsi+40h]
0x18009f82a  mov     rdx, cs:FailoverConfTableHandle
0x18009f831  mov     rcx, rdi
0x18009f834  mov     [rsp+58h+var_38], 1
0x18009f83c  call    DhcpDALJetSetValue
0x18009f841  mov     ebx, eax
0x18009f843  test    eax, eax
0x18009f845  jnz     loc_18009F917
0x18009f84b  mov     r8d, cs:dword_1800F9418
0x18009f852  lea     r9, [rsi+10h]
0x18009f856  mov     rdx, cs:FailoverConfTableHandle
0x18009f85d  mov     rcx, rdi
0x18009f860  mov     [rsp+58h+var_38], r12d
0x18009f865  call    DhcpDALJetSetValue
0x18009f86a  mov     ebx, eax
0x18009f86c  test    eax, eax
0x18009f86e  jnz     loc_18009F917
0x18009f874  mov     r8d, cs:dword_1800F9430
0x18009f87b  lea     r9, [rsi+14h]
0x18009f87f  mov     rdx, cs:FailoverConfTableHandle
0x18009f886  mov     rcx, rdi
0x18009f889  mov     [rsp+58h+var_38], r12d
0x18009f88e  call    DhcpDALJetSetValue
0x18009f893  mov     ebx, eax
0x18009f895  test    eax, eax
0x18009f897  jnz     short loc_18009F917
0x18009f899  mov     rax, [rsi+38h]
0x18009f89d  test    rax, rax
0x18009f8a0  jz      loc_18009F9D8
0x18009f8a6  cmp     [rax], r15d
0x18009f8a9  jz      loc_18009F9D8
0x18009f8af  mov     ebp, [rax]
0x18009f8b1  mov     eax, 0FFFFFFFFh
0x18009f8b6  shl     rbp, 2
0x18009f8ba  cmp     rbp, rax
0x18009f8bd  ja      loc_18009F9FE
0x18009f8c3  mov     rcx, cs:gDhcpHeap; hHeap
0x18009f8ca  mov     ebx, 8
0x18009f8cf  mov     edx, ebx; dwFlags
0x18009f8d1  mov     r8d, ebp; dwBytes
0x18009f8d4  call    cs:__imp_HeapAlloc
0x18009f8db  nop     dword ptr [rax+rax+00h]
0x18009f8e0  mov     r14, rax
0x18009f8e3  test    rax, rax
0x18009f8e6  jnz     short loc_18009F926
0x18009f8e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f8ef  lea     rax, WPP_GLOBAL_Control
0x18009f8f6  cmp     rcx, rax
0x18009f8f9  jz      short loc_18009F917
0x18009f8fb  test    dword ptr [rcx+1Ch], 800000h
0x18009f902  jz      short loc_18009F917
0x18009f904  mov     rcx, [rcx+10h]
0x18009f908  lea     edx, [rbx+3]
0x18009f90b  lea     r8, WPP_69eab83df91b31eacaf8ec0f641a7f07_Traceguids
0x18009f912  call    WPP_SF_
0x18009f917  mov     rcx, rdi
0x18009f91a  call    DhcpDALJetRollback
0x18009f91f  mov     eax, ebx
0x18009f921  jmp     loc_18009FA12
0x18009f926  mov     rax, [rsi+38h]
0x18009f92a  mov     r8d, r15d
0x18009f92d  cmp     [rax], r15d
0x18009f930  jbe     short loc_18009F94C
0x18009f932  mov     rax, [rax+8]
0x18009f936  mov     edx, r8d
0x18009f939  inc     r8d
0x18009f93c  mov     ecx, [rax+rdx*4]
0x18009f93f  mov     [r14+rdx*4], ecx
0x18009f943  mov     rax, [rsi+38h]
0x18009f947  cmp     r8d, [rax]
0x18009f94a  jb      short loc_18009F932
0x18009f94c  mov     r8d, cs:dword_1800F9478
0x18009f953  mov     r9, r14
0x18009f956  mov     rdx, cs:FailoverConfTableHandle
0x18009f95d  mov     rcx, rdi
0x18009f960  mov     [rsp+58h+var_38], ebp
0x18009f964  call    DhcpDALJetSetValue
0x18009f969  mov     ebx, eax
0x18009f96b  test    eax, eax
0x18009f96d  jnz     short loc_18009F9B8
0x18009f96f  xor     ecx, ecx; Time
0x18009f971  call    cs:__imp_time
0x18009f978  nop     dword ptr [rax+rax+00h]
0x18009f97d  mov     r8d, cs:dword_1800F9490
0x18009f984  lea     r9, [rsp+58h+arg_10]
0x18009f989  mov     rdx, cs:FailoverConfTableHandle
0x18009f990  mov     rcx, rdi
0x18009f993  mov     [rsp+58h+arg_10], eax
0x18009f997  mov     [rsp+58h+var_38], r12d
0x18009f99c  call    DhcpDALJetSetValue
0x18009f9a1  mov     ebx, eax
0x18009f9a3  test    eax, eax
0x18009f9a5  jnz     short loc_18009F9B8
0x18009f9a7  mov     rdx, cs:FailoverConfTableHandle
0x18009f9ae  mov     rcx, rdi
0x18009f9b1  call    DhcpDALJetCommitUpdate
0x18009f9b6  mov     ebx, eax
0x18009f9b8  mov     rcx, cs:gDhcpHeap; hHeap
0x18009f9bf  mov     r8, r14; lpMem
0x18009f9c2  xor     edx, edx; dwFlags
0x18009f9c4  call    cs:__imp_HeapFree
0x18009f9cb  nop     dword ptr [rax+rax+00h]
0x18009f9d0  test    ebx, ebx
0x18009f9d2  jnz     loc_18009F917
0x18009f9d8  xor     edx, edx; grbit
0x18009f9da  mov     rcx, rdi; sesid
0x18009f9dd  call    cs:__imp_JetCommitTransaction
0x18009f9e4  nop     dword ptr [rax+rax+00h]
0x18009f9e9  mov     ecx, eax
0x18009f9eb  lea     rdx, aDhcpdaljetcomm; "DhcpDALJetCommitTransaction"
0x18009f9f2  call    DhcpDALMapJetError
0x18009f9f7  mov     ebx, eax
0x18009f9f9  jmp     loc_18009F91F
0x18009f9fe  mov     ebx, 216h
0x18009fa03  jmp     loc_18009F917
0x18009fa08  neg     rcx
0x18009fa0b  sbb     eax, eax
0x18009fa0d  not     eax
0x18009fa0f  and     eax, 57h
0x18009fa12  mov     rbx, [rsp+58h+arg_0]
0x18009fa17  mov     rbp, [rsp+58h+arg_8]
0x18009fa1c  add     rsp, 30h
0x18009fa20  pop     r15
0x18009fa22  pop     r14
0x18009fa24  pop     r12
0x18009fa26  pop     rdi
0x18009fa27  pop     rsi
0x18009fa28  retn
```
