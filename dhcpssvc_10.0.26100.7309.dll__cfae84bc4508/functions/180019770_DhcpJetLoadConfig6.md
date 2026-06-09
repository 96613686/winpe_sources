# DhcpJetLoadConfig6

- ea: `0x180019770`
- end: `0x180019ea3`
- name: `DhcpJetLoadConfig6`
- size: `1843`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180014600`
- `0x18003116c`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000f144`
- `0x180018414`
- `0x180018f50`
- `0x180019770`
- `0x18001ac8c`
- `0x18001ad64`
- `0x1800947e4`
- `0x18009602c`
- `0x180096080`

## import_xrefs

- `ESENT!JetOpenTable` at `0x18001981b`
- `ESENT!JetOpenTable` at `0x18001981b`
- `ESENT!JetCloseTable` at `0x180019842`
- `ESENT!JetCloseTable` at `0x180019842`
- `ESENT!JetUpdate` at `0x180019b0c`
- `ESENT!JetUpdate` at `0x180019b0c`
- `ESENT!JetSetCurrentIndex` at `0x1800198fa`
- `ESENT!JetSetCurrentIndex` at `0x1800198fa`
- `ESENT!JetBeginTransaction` at `0x180019a47`
- `ESENT!JetBeginTransaction` at `0x180019a47`
- `ESENT!JetCommitTransaction` at `0x180019b39`
- `ESENT!JetCommitTransaction` at `0x180019b39`
- `ESENT!JetPrepareUpdate` at `0x180019a7d`
- `ESENT!JetPrepareUpdate` at `0x180019a7d`
- `ESENT!JetSetColumn` at `0x180019acf`
- `ESENT!JetSetColumn` at `0x180019acf`
- `ESENT!JetMove` at `0x180019975`
- `ESENT!JetMove` at `0x180019b9d`
- `ESENT!JetMove` at `0x180019975`
- `ESENT!JetMove` at `0x180019b9d`
- `KERNEL32!HeapAlloc` at `0x1800199e8`
- `KERNEL32!HeapAlloc` at `0x180019bd4`
- `KERNEL32!HeapAlloc` at `0x1800199e8`
- `KERNEL32!HeapAlloc` at `0x180019bd4`
- `KERNEL32!HeapFree` at `0x180019c80`
- `KERNEL32!HeapFree` at `0x180019ca4`
- `KERNEL32!HeapFree` at `0x180019e55`
- `KERNEL32!HeapFree` at `0x180019c80`
- `KERNEL32!HeapFree` at `0x180019ca4`
- `KERNEL32!HeapFree` at `0x180019e55`

## string_xrefs

- `0x180019983`: `JetMove`
- `0x180019bab`: `JetMove`
- `0x180019a8b`: `JetPrepareUpdate Failed`
- `0x180019b1a`: `JetUpdate Failed`
- `0x180019b47`: `JetCommitTransaction Failed`

## pseudocode

```c
__int64 __fastcall DhcpJetLoadConfig6(__int64 *a1)
{
  unsigned int v2; // esi
  unsigned int v3; // r14d
  _QWORD *v4; // r12
  unsigned int v6; // edi
  __int64 v7; // rbx
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // r15
  unsigned int v11; // edi
  int v12; // r13d
  int *v13; // rax
  int *v14; // r15
  int v15; // edx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // r15
  __int64 v25; // rdi
  __int64 v26; // rax
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  unsigned int v34; // eax
  __int64 v35; // rdi
  unsigned int *v36; // r15
  __int64 v37; // rax
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int64 v45; // r14
  void *v46; // rbx
  __int64 v47; // [rsp+40h] [rbp-89h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-81h]
  __int64 v49; // [rsp+50h] [rbp-79h] BYREF
  _QWORD *v50; // [rsp+58h] [rbp-71h]
  __int128 v51; // [rsp+60h] [rbp-69h]
  __int128 v52; // [rsp+70h] [rbp-59h]
  __int128 v53; // [rsp+80h] [rbp-49h]
  __int128 v54; // [rsp+90h] [rbp-39h]
  __int128 v55; // [rsp+A0h] [rbp-29h]
  __int128 v56; // [rsp+B0h] [rbp-19h]
  __int128 v57; // [rsp+C0h] [rbp-9h]
  __int128 v58; // [rsp+D0h] [rbp+7h]
  __int64 v59; // [rsp+E0h] [rbp+17h]
  JET_TABLEID tableid; // [rsp+138h] [rbp+6Fh] BYREF
  int v62; // [rsp+140h] [rbp+77h] BYREF

  v2 = 0;
  v62 = 0;
  v3 = 0;
  v47 = 0;
  v4 = 0;
  lpMem = 0;
  v49 = 0;
  v50 = 0;
  if ( !DhcpGlobalConfigTableV6 )
    return 1627;
  if ( a1 && ((v7 = *a1) != 0 || (v7 = MemAlloc(0x88u)) != 0) )
  {
    tableid = 0;
    if ( (unsigned int)JetOpenTable(
                         DhcpGlobalJetServerSession,
                         DhcpGlobalDatabaseHandle,
                         "StatelessClients",
                         0,
                         0,
                         0,
                         &tableid) == -1305 )
    {
      LODWORD(tableid) = 1;
      goto LABEL_10;
    }
    v8 = JetCloseTable(DhcpGlobalJetServerSession, tableid);
    v9 = DhcpMapJetError(v8, "IsUpgradeFromPreWin8OS : JetCloseTable ");
    LODWORD(tableid) = 0;
    v6 = v9;
    if ( !v9 )
    {
LABEL_10:
      if ( v7 )
      {
        if ( v7 != -80 )
        {
          *(_QWORD *)(v7 + 80) = 0;
          *(_QWORD *)(v7 + 88) = 0;
        }
        if ( v7 != -64 )
        {
          *(_QWORD *)(v7 + 64) = 0;
          *(_QWORD *)(v7 + 72) = 0;
        }
        if ( v7 != -48 )
        {
          *(_QWORD *)(v7 + 48) = 0;
          *(_QWORD *)(v7 + 56) = 0;
        }
        if ( v7 != -16 )
        {
          *(_QWORD *)(v7 + 16) = 0;
          *(_QWORD *)(v7 + 24) = 0;
        }
        if ( v7 != -32 )
        {
          *(_QWORD *)(v7 + 32) = 0;
          *(_QWORD *)(v7 + 40) = 0;
        }
        *(_QWORD *)(v7 + 8) = 0;
        *(_QWORD *)v7 = 0;
        *(_DWORD *)(v7 + 128) = -1;
        *(_QWORD *)(v7 + 96) = 0;
        *(_DWORD *)(v7 + 104) = 48;
        if ( v7 != -112 )
        {
          *(_QWORD *)(v7 + 112) = 0;
          *(_QWORD *)(v7 + 120) = 0;
        }
      }
      v10 = (unsigned int)JetSetCurrentIndex(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 0);
      v6 = DhcpMapJetError(v10, "JetSetCurrentIndex");
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            &WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids,
            (unsigned int)v10);
      }
      else
      {
        v11 = JetMove(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 0x80000000, 0);
        if ( (unsigned int)DhcpMapJetError(v11, "JetMove") )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids, v11);
          }
          v6 = 0;
          *a1 = v7;
        }
        else
        {
          v12 = 8;
          v13 = (int *)HeapAlloc(gDhcpHeap, 8u, 0x88u);
          v14 = v13;
          if ( v13 )
          {
            while ( 1 )
            {
              v15 = tableid;
              *((_QWORD *)v13 + 3) = 0;
              *((_QWORD *)v13 + 4) = 0;
              *((_QWORD *)v13 + 1) = 0;
              *((_QWORD *)v13 + 11) = 0;
              *((_QWORD *)v13 + 6) = 0;
              *((_QWORD *)v13 + 7) = 0;
              v16 = ReadDBEntry6(v14, v15, &v62);
              v6 = v16;
              if ( v62 == 1 && !v16 )
              {
                v17 = JetBeginTransaction(DhcpGlobalJetServerSession);
                v6 = DhcpMapJetError(v17, "JetBeginTransaction Failed");
                if ( v6 )
                  goto LABEL_56;
                v18 = JetPrepareUpdate(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 2u);
                v6 = DhcpMapJetError(v18, "JetPrepareUpdate Failed");
                if ( v6 )
                  goto LABEL_56;
                v19 = JetSetColumn(
                        DhcpGlobalJetServerSession,
                        DhcpGlobalConfigTableV6Handle,
                        *(_DWORD *)(DhcpGlobalConfigTableV6 + 72),
                        v14 + 4,
                        4u,
                        0,
                        0);
                v6 = DhcpMapJetError(v19, "JetSetColumn Failed");
                if ( v6 )
                  goto LABEL_56;
                v20 = JetUpdate(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 0, 0, 0);
                v6 = DhcpMapJetError(v20, "JetUpdate Failed");
                if ( v6 )
                  goto LABEL_56;
                v21 = JetCommitTransaction(DhcpGlobalJetServerSession, 0);
                v6 = DhcpMapJetError(v21, "JetCommitTransaction Failed");
                if ( v6 )
                  goto LABEL_56;
              }
              if ( v6 == 259 )
                break;
              if ( v6 )
              {
                v6 = 1627;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids);
                }
                goto LABEL_55;
              }
              v6 = MemArrayAddElement((unsigned int *)&v47, (__int64)v14);
              if ( v6 )
              {
                FreeDBEntry6(v14);
LABEL_55:
                HeapFree(gDhcpHeap, 0, v14);
LABEL_56:
                v2 = v47;
                goto LABEL_76;
              }
              v22 = JetMove(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 1, 0);
              v23 = DhcpMapJetError(v22, "JetMove");
              v6 = v23;
              if ( v23 == 259 )
              {
                v12 = 0;
                goto LABEL_58;
              }
              if ( v23 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    30,
                    &WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids,
                    v23);
                }
                goto LABEL_56;
              }
              v13 = (int *)HeapAlloc(gDhcpHeap, 8u, 0x88u);
              v14 = v13;
              if ( !v13 )
              {
                v2 = v47;
                goto LABEL_75;
              }
            }
            v12 = 0;
            HeapFree(gDhcpHeap, 0, v14);
LABEL_58:
            v2 = v47;
            if ( (_DWORD)v47 )
            {
              v24 = 0;
              do
              {
                v25 = *((_QWORD *)lpMem + v24);
                v26 = *(_QWORD *)(v25 + 128);
                v27 = *(_OWORD *)(v25 + 16);
                v51 = *(_OWORD *)v25;
                v28 = *(_OWORD *)(v25 + 32);
                v52 = v27;
                v29 = *(_OWORD *)(v25 + 48);
                v53 = v28;
                v30 = *(_OWORD *)(v25 + 64);
                v54 = v29;
                v31 = *(_OWORD *)(v25 + 80);
                v55 = v30;
                v32 = *(_OWORD *)(v25 + 96);
                v56 = v31;
                v33 = *(_OWORD *)(v25 + 112);
                v57 = v32;
                v58 = v33;
                v59 = v26;
                v34 = AddDBEntry6(v7);
                if ( v34 == 2 )
                {
                  v6 = MemArrayAddElement((unsigned int *)&v49, v25);
                  if ( v6 )
                  {
                    v4 = v50;
                    goto LABEL_76;
                  }
                }
                else if ( v34
                       && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                       && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    31,
                    &WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids,
                    v34);
                }
                v24 = (unsigned int)(v24 + 1);
              }
              while ( (unsigned int)v24 < v2 );
              v4 = v50;
              v3 = v49;
            }
            if ( v3 )
            {
              v35 = 0;
              do
              {
                v36 = (unsigned int *)v4[v35];
                v37 = *((_QWORD *)v36 + 16);
                v38 = *((_OWORD *)v36 + 1);
                v51 = *(_OWORD *)v36;
                v39 = *((_OWORD *)v36 + 2);
                v52 = v38;
                v40 = *((_OWORD *)v36 + 3);
                v53 = v39;
                v41 = *((_OWORD *)v36 + 4);
                v54 = v40;
                v42 = *((_OWORD *)v36 + 5);
                v55 = v41;
                v43 = *((_OWORD *)v36 + 6);
                v56 = v42;
                v44 = *((_OWORD *)v36 + 7);
                v57 = v43;
                v58 = v44;
                v59 = v37;
                if ( (unsigned int)AddDBEntry6(v7) )
                  DeleteDBEntry6(*v36);
                v35 = (unsigned int)(v35 + 1);
              }
              while ( (unsigned int)v35 < v3 );
            }
            *a1 = v7;
          }
LABEL_75:
          v6 = v12;
        }
      }
    }
  }
  else
  {
    v6 = 87;
  }
LABEL_76:
  if ( v2 )
  {
    v45 = 0;
    do
    {
      v46 = (void *)*((_QWORD *)lpMem + v45);
      FreeDBEntry6(v46);
      HeapFree(gDhcpHeap, 0, v46);
      v45 = (unsigned int)(v45 + 1);
    }
    while ( (unsigned int)v45 < v2 );
    if ( lpMem )
      MemFree(lpMem);
  }
  if ( v4 )
    MemFree(v4);
  return v6;
}

```

## disassembly

```asm
0x180019770  mov     [rsp-8+arg_18], rbx
0x180019775  mov     [rsp-8+arg_0], rcx
0x18001977a  push    rbp
0x18001977b  push    rsi
0x18001977c  push    rdi
0x18001977d  push    r12
0x18001977f  push    r13
0x180019781  push    r14
0x180019783  push    r15
0x180019785  lea     rbp, [rsp-27h]
0x18001978a  sub     rsp, 0F0h
0x180019791  xor     edi, edi
0x180019793  mov     r13, rcx
0x180019796  cmp     cs:DhcpGlobalConfigTableV6, rdi
0x18001979d  mov     esi, edi
0x18001979f  mov     [rbp+57h+arg_10], edi
0x1800197a2  mov     r14d, edi
0x1800197a5  mov     [rsp+120h+var_E0], rdi
0x1800197aa  mov     r12d, edi
0x1800197ad  mov     [rsp+120h+lpMem], rdi
0x1800197b2  mov     [rbp+57h+var_D0], rdi
0x1800197b6  mov     [rbp+57h+var_C8], rdi
0x1800197ba  jnz     short loc_1800197C6
0x1800197bc  mov     eax, 65Bh
0x1800197c1  jmp     loc_180019E87
0x1800197c6  test    r13, r13
0x1800197c9  jnz     short loc_1800197D5
0x1800197cb  mov     edi, 57h ; 'W'
0x1800197d0  jmp     loc_180019E2D
0x1800197d5  mov     rbx, [rcx]
0x1800197d8  test    rbx, rbx
0x1800197db  jnz     short loc_1800197EF
0x1800197dd  mov     ecx, 88h; dwBytes
0x1800197e2  call    MemAlloc
0x1800197e7  mov     rbx, rax
0x1800197ea  test    rax, rax
0x1800197ed  jz      short loc_1800197CB
0x1800197ef  mov     edx, cs:DhcpGlobalDatabaseHandle
0x1800197f5  lea     rax, [rbp+57h+tableid]
0x1800197f9  mov     rcx, cs:DhcpGlobalJetServerSession
0x180019800  lea     r8, aStatelessclien; "StatelessClients"
0x180019807  mov     [rsp+120h+psetinfo], rax
0x18001980c  xor     r9d, r9d
0x18001980f  mov     [rsp+120h+grbit], edi
0x180019813  mov     [rsp+120h+cbData], edi
0x180019817  mov     [rbp+57h+tableid], rdi
0x18001981b  call    cs:__imp_JetOpenTable
0x180019822  nop     dword ptr [rax+rax+00h]
0x180019827  cmp     eax, 0FFFFFAE7h
0x18001982c  jnz     short loc_180019837
0x18001982e  mov     dword ptr [rbp+57h+tableid], 1
0x180019835  jmp     short loc_18001986B
0x180019837  mov     rdx, [rbp+57h+tableid]; tableid
0x18001983b  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180019842  call    cs:__imp_JetCloseTable
0x180019849  nop     dword ptr [rax+rax+00h]
0x18001984e  mov     ecx, eax
0x180019850  lea     rdx, aIsupgradefromp; "IsUpgradeFromPreWin8OS : JetCloseTable "
0x180019857  call    DhcpMapJetError
0x18001985c  and     dword ptr [rbp+57h+tableid], esi
0x18001985f  mov     edi, eax
0x180019861  test    eax, eax
0x180019863  jnz     loc_180019E2D
0x180019869  xor     edi, edi
0x18001986b  test    rbx, rbx
0x18001986e  jz      short loc_1800198E9
0x180019870  lea     rax, [rbx+50h]
0x180019874  test    rax, rax
0x180019877  jz      short loc_180019880
0x180019879  mov     [rax], rsi
0x18001987c  mov     [rax+8], rdi
0x180019880  lea     rax, [rbx+40h]
0x180019884  test    rax, rax
0x180019887  jz      short loc_180019890
0x180019889  mov     [rax], rsi
0x18001988c  mov     [rax+8], rdi
0x180019890  lea     rax, [rbx+30h]
0x180019894  test    rax, rax
0x180019897  jz      short loc_1800198A0
0x180019899  mov     [rax], rsi
0x18001989c  mov     [rax+8], rdi
0x1800198a0  lea     rax, [rbx+10h]
0x1800198a4  test    rax, rax
0x1800198a7  jz      short loc_1800198B0
0x1800198a9  mov     [rax], rsi
0x1800198ac  mov     [rax+8], rdi
0x1800198b0  lea     rax, [rbx+20h]
0x1800198b4  test    rax, rax
0x1800198b7  jz      short loc_1800198C0
0x1800198b9  mov     [rax], rsi
0x1800198bc  mov     [rax+8], rdi
0x1800198c0  mov     [rbx+8], rdi
0x1800198c4  mov     [rbx], rdi
0x1800198c7  or      dword ptr [rbx+80h], 0FFFFFFFFh
0x1800198ce  lea     rax, [rbx+70h]
0x1800198d2  mov     [rbx+60h], rsi
0x1800198d6  mov     dword ptr [rbx+68h], 30h ; '0'
0x1800198dd  test    rax, rax
0x1800198e0  jz      short loc_1800198E9
0x1800198e2  mov     [rax], rsi
0x1800198e5  mov     [rax+8], rdi
0x1800198e9  mov     rdx, cs:DhcpGlobalConfigTableV6Handle
0x1800198f0  xor     r8d, r8d
0x1800198f3  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800198fa  call    cs:__imp_JetSetCurrentIndex
0x180019901  nop     dword ptr [rax+rax+00h]
0x180019906  mov     ecx, eax
0x180019908  lea     rdx, aJetsetcurrenti; "JetSetCurrentIndex"
0x18001990f  mov     r15d, eax
0x180019912  call    DhcpMapJetError
0x180019917  mov     edi, eax
0x180019919  test    eax, eax
0x18001991b  jz      short loc_18001995E
0x18001991d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019924  lea     r14, WPP_GLOBAL_Control
0x18001992b  cmp     rcx, r14
0x18001992e  jz      loc_180019E2D
0x180019934  test    dword ptr [rcx+1Ch], 800h
0x18001993b  jz      loc_180019E2D
0x180019941  mov     rcx, [rcx+10h]
0x180019945  lea     r8, WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids
0x18001994c  mov     edx, 1Bh
0x180019951  mov     r9d, r15d
0x180019954  call    WPP_SF_D
0x180019959  jmp     loc_180019E2D
0x18001995e  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x180019965  xor     r9d, r9d; grbit
0x180019968  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001996f  mov     r8d, 80000000h; cRow
0x180019975  call    cs:__imp_JetMove
0x18001997c  nop     dword ptr [rax+rax+00h]
0x180019981  mov     ecx, eax
0x180019983  lea     rdx, aJetmove; "JetMove"
0x18001998a  mov     edi, eax
0x18001998c  call    DhcpMapJetError
0x180019991  test    eax, eax
0x180019993  jz      short loc_1800199D4
0x180019995  mov     rcx, cs:WPP_GLOBAL_Control
0x18001999c  lea     r14, WPP_GLOBAL_Control
0x1800199a3  cmp     rcx, r14
0x1800199a6  jz      short loc_1800199C9
0x1800199a8  test    dword ptr [rcx+1Ch], 800h
0x1800199af  jz      short loc_1800199C9
0x1800199b1  mov     rcx, [rcx+10h]
0x1800199b5  lea     r8, WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids
0x1800199bc  mov     edx, 1Ch
0x1800199c1  mov     r9d, edi
0x1800199c4  call    WPP_SF_D
0x1800199c9  xor     edi, edi
0x1800199cb  mov     [r13+0], rbx
0x1800199cf  jmp     loc_180019E2D
0x1800199d4  mov     rcx, cs:gDhcpHeap; hHeap
0x1800199db  mov     r8d, 88h; dwBytes
0x1800199e1  lea     r13d, [r8-80h]
0x1800199e5  mov     edx, r13d; dwFlags
0x1800199e8  call    cs:__imp_HeapAlloc
0x1800199ef  nop     dword ptr [rax+rax+00h]
0x1800199f4  mov     r15, rax
0x1800199f7  test    rax, rax
0x1800199fa  jz      loc_180019E2A
0x180019a00  mov     ecx, dword ptr [rbp+57h+tableid]
0x180019a03  lea     r8, [rbp+57h+arg_10]
0x180019a07  mov     dword ptr [rbp+57h+tableid], ecx
0x180019a0a  mov     edx, ecx
0x180019a0c  mov     rcx, r15; pvData
0x180019a0f  mov     [rax+18h], rsi
0x180019a13  mov     [rax+20h], rsi
0x180019a17  mov     [rax+8], rsi
0x180019a1b  mov     [rax+58h], rsi
0x180019a1f  mov     [rax+30h], rsi
0x180019a23  mov     [rax+38h], rsi
0x180019a27  call    ReadDBEntry6
0x180019a2c  cmp     [rbp+57h+arg_10], 1
0x180019a30  mov     edi, eax
0x180019a32  jnz     loc_180019B5D
0x180019a38  test    eax, eax
0x180019a3a  jnz     loc_180019B5D
0x180019a40  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180019a47  call    cs:__imp_JetBeginTransaction
0x180019a4e  nop     dword ptr [rax+rax+00h]
0x180019a53  mov     ecx, eax
0x180019a55  lea     rdx, aJetbegintransa; "JetBeginTransaction Failed"
0x180019a5c  call    DhcpMapJetError
0x180019a61  mov     edi, eax
0x180019a63  test    eax, eax
0x180019a65  jnz     loc_180019C8C
0x180019a6b  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x180019a72  lea     r8d, [rax+2]; prep
0x180019a76  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180019a7d  call    cs:__imp_JetPrepareUpdate
0x180019a84  nop     dword ptr [rax+rax+00h]
0x180019a89  mov     ecx, eax
0x180019a8b  lea     rdx, aJetprepareupda_0; "JetPrepareUpdate Failed"
0x180019a92  call    DhcpMapJetError
0x180019a97  mov     edi, eax
0x180019a99  test    eax, eax
0x180019a9b  jnz     loc_180019C8C
0x180019aa1  mov     r8, cs:DhcpGlobalConfigTableV6
0x180019aa8  lea     r9, [r15+10h]; pvData
0x180019aac  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x180019ab3  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180019aba  mov     [rsp+120h+psetinfo], rsi; psetinfo
0x180019abf  mov     r8d, [r8+48h]; columnid
0x180019ac3  mov     [rsp+120h+grbit], esi; grbit
0x180019ac7  mov     [rsp+120h+cbData], 4; cbData
0x180019acf  call    cs:__imp_JetSetColumn
0x180019ad6  nop     dword ptr [rax+rax+00h]
0x180019adb  mov     ecx, eax
0x180019add  lea     rdx, aJetsetcolumnFa; "JetSetColumn Failed"
0x180019ae4  call    DhcpMapJetError
0x180019ae9  mov     edi, eax
0x180019aeb  test    eax, eax
0x180019aed  jnz     loc_180019C8C
0x180019af3  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x180019afa  xor     r9d, r9d; cbBookmark
0x180019afd  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180019b04  xor     r8d, r8d; pvBookmark
0x180019b07  mov     qword ptr [rsp+120h+cbData], rsi; pcbActual
0x180019b0c  call    cs:__imp_JetUpdate
0x180019b13  nop     dword ptr [rax+rax+00h]
0x180019b18  mov     ecx, eax
0x180019b1a  lea     rdx, aJetupdateFaile; "JetUpdate Failed"
0x180019b21  call    DhcpMapJetError
0x180019b26  mov     edi, eax
0x180019b28  test    eax, eax
0x180019b2a  jnz     loc_180019C8C
0x180019b30  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180019b37  xor     edx, edx; grbit
0x180019b39  call    cs:__imp_JetCommitTransaction
0x180019b40  nop     dword ptr [rax+rax+00h]
0x180019b45  mov     ecx, eax
0x180019b47  lea     rdx, aJetcommittrans; "JetCommitTransaction Failed"
0x180019b4e  call    DhcpMapJetError
0x180019b53  mov     edi, eax
0x180019b55  test    eax, eax
0x180019b57  jnz     loc_180019C8C
0x180019b5d  cmp     edi, 103h
0x180019b63  jz      loc_180019C95
0x180019b69  test    edi, edi
0x180019b6b  jnz     loc_180019C3E
0x180019b71  mov     rdx, r15
0x180019b74  lea     rcx, [rsp+120h+var_E0]
0x180019b79  call    MemArrayAddElement
0x180019b7e  mov     edi, eax
0x180019b80  test    eax, eax
0x180019b82  jnz     loc_180019C34
0x180019b88  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x180019b8f  lea     r8d, [rax+1]; cRow
0x180019b93  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180019b9a  xor     r9d, r9d; grbit
0x180019b9d  call    cs:__imp_JetMove
0x180019ba4  nop     dword ptr [rax+rax+00h]
0x180019ba9  mov     ecx, eax
0x180019bab  lea     rdx, aJetmove; "JetMove"
0x180019bb2  call    DhcpMapJetError
0x180019bb7  mov     edi, eax
0x180019bb9  cmp     eax, 103h
0x180019bbe  jz      short loc_180019C2F
0x180019bc0  test    eax, eax
0x180019bc2  jnz     short loc_180019BF5
0x180019bc4  mov     rcx, cs:gDhcpHeap; hHeap
0x180019bcb  mov     r8d, 88h; dwBytes
0x180019bd1  mov     edx, r13d; dwFlags
0x180019bd4  call    cs:__imp_HeapAlloc
0x180019bdb  nop     dword ptr [rax+rax+00h]
0x180019be0  mov     r15, rax
0x180019be3  test    rax, rax
0x180019be6  jnz     loc_180019A00
0x180019bec  mov     esi, dword ptr [rsp+120h+var_E0]
0x180019bf0  jmp     loc_180019E2A
0x180019bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bfc  lea     r14, WPP_GLOBAL_Control
0x180019c03  cmp     rcx, r14
0x180019c06  jz      loc_180019C8C
0x180019c0c  test    dword ptr [rcx+1Ch], 800h
0x180019c13  jz      short loc_180019C8C
0x180019c15  mov     rcx, [rcx+10h]
0x180019c19  lea     r8, WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids
0x180019c20  mov     edx, 1Eh
0x180019c25  mov     r9d, eax
0x180019c28  call    WPP_SF_D
0x180019c2d  jmp     short loc_180019C8C
0x180019c2f  mov     r13d, esi
0x180019c32  jmp     short loc_180019CB0
0x180019c34  mov     rcx, r15
0x180019c37  call    FreeDBEntry6
0x180019c3c  jmp     short loc_180019C74
0x180019c3e  mov     edi, 65Bh
0x180019c43  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c4a  lea     r14, WPP_GLOBAL_Control
0x180019c51  cmp     rcx, r14
0x180019c54  jz      short loc_180019C74
0x180019c56  test    dword ptr [rcx+1Ch], 800h
0x180019c5d  jz      short loc_180019C74
0x180019c5f  mov     rcx, [rcx+10h]
0x180019c63  lea     r8, WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids
0x180019c6a  mov     edx, 1Dh
0x180019c6f  call    WPP_SF_
0x180019c74  mov     rcx, cs:gDhcpHeap; hHeap
0x180019c7b  mov     r8, r15; lpMem
  ... truncated ...
```
