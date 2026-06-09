# DhcpJetLoadConfig6

- ea: `0x180018d40`
- end: `0x180019429`
- name: `DhcpJetLoadConfig6`
- size: `1769`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013d60`
- `0x18003070c`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000e814`
- `0x1800179ec`
- `0x180018520`
- `0x180018d40`
- `0x18001a23c`
- `0x18001a314`
- `0x180094a7c`
- `0x180096254`
- `0x1800962b0`

## import_xrefs

- `ESENT!JetCloseTable` at `0x180018e0d`
- `ESENT!JetCloseTable` at `0x180018e0d`
- `ESENT!JetOpenTable` at `0x180018de7`
- `ESENT!JetOpenTable` at `0x180018de7`
- `ESENT!JetUpdate` at `0x1800190aa`
- `ESENT!JetUpdate` at `0x1800190aa`
- `ESENT!JetSetCurrentIndex` at `0x180018ec5`
- `ESENT!JetSetCurrentIndex` at `0x180018ec5`
- `ESENT!JetBeginTransaction` at `0x180018fe4`
- `ESENT!JetBeginTransaction` at `0x180018fe4`
- `ESENT!JetCommitTransaction` at `0x1800190d7`
- `ESENT!JetCommitTransaction` at `0x1800190d7`
- `ESENT!JetPrepareUpdate` at `0x18001901a`
- `ESENT!JetPrepareUpdate` at `0x18001901a`
- `ESENT!JetSetColumn` at `0x18001906d`
- `ESENT!JetSetColumn` at `0x18001906d`
- `ESENT!JetMove` at `0x180018f3f`
- `ESENT!JetMove` at `0x18001913b`
- `ESENT!JetMove` at `0x180018f3f`
- `ESENT!JetMove` at `0x18001913b`
- `KERNEL32!HeapAlloc` at `0x18001917b`
- `KERNEL32!HeapAlloc` at `0x18001917b`
- `KERNEL32!HeapFree` at `0x1800191c2`
- `KERNEL32!HeapFree` at `0x180019294`
- `KERNEL32!HeapFree` at `0x1800192b3`
- `KERNEL32!HeapFree` at `0x1800191c2`
- `KERNEL32!HeapFree` at `0x180019294`
- `KERNEL32!HeapFree` at `0x1800192b3`

## string_xrefs

- `0x180018f4d`: `JetMove`
- `0x180019149`: `JetMove`
- `0x180019028`: `JetPrepareUpdate Failed`
- `0x1800190b8`: `JetUpdate Failed`
- `0x1800190e5`: `JetCommitTransaction Failed`

## pseudocode

```c
__int64 __fastcall DhcpJetLoadConfig6(__int64 *a1)
{
  unsigned int v2; // r14d
  _QWORD *v3; // r15
  unsigned int v5; // edi
  __int64 v6; // rbx
  unsigned int v7; // eax
  unsigned int v8; // esi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // edi
  int DBEntry6; // edi
  unsigned int v14; // eax
  unsigned int v15; // eax
  _QWORD *v16; // rax
  void *v17; // rsi
  unsigned int v18; // esi
  void *v19; // rbx
  unsigned int v20; // esi
  __int128 *v21; // rdi
  __int64 v22; // rax
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  unsigned int v30; // eax
  unsigned int i; // edi
  unsigned int *v32; // rsi
  __int64 v33; // rax
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int64 v41; // [rsp+40h] [rbp-89h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-81h]
  __int64 v43; // [rsp+50h] [rbp-79h] BYREF
  _QWORD *v44; // [rsp+58h] [rbp-71h]
  __int128 v45; // [rsp+60h] [rbp-69h]
  __int128 v46; // [rsp+70h] [rbp-59h]
  __int128 v47; // [rsp+80h] [rbp-49h]
  __int128 v48; // [rsp+90h] [rbp-39h]
  __int128 v49; // [rsp+A0h] [rbp-29h]
  __int128 v50; // [rsp+B0h] [rbp-19h]
  __int128 v51; // [rsp+C0h] [rbp-9h]
  __int128 v52; // [rsp+D0h] [rbp+7h]
  __int64 v53; // [rsp+E0h] [rbp+17h]
  JET_TABLEID tableid; // [rsp+140h] [rbp+77h] BYREF

  v2 = 0;
  v3 = 0;
  v41 = 0;
  lpMem = 0;
  v43 = 0;
  v44 = 0;
  if ( !DhcpGlobalConfigTableV6 )
    return 1627;
  if ( !a1 || (v6 = *a1) == 0 && (v6 = MemAlloc(0x88u)) == 0 )
  {
    v5 = 87;
    goto LABEL_40;
  }
  tableid = 0;
  if ( (unsigned int)JetOpenTable(
                       DhcpGlobalJetServerSession,
                       DhcpGlobalDatabaseHandle,
                       "StatelessClients",
                       0,
                       0,
                       0,
                       &tableid) == -1305
    || (v7 = JetCloseTable(DhcpGlobalJetServerSession, tableid),
        (v5 = DhcpMapJetError(v7, "IsUpgradeFromPreWin8OS : JetCloseTable ")) == 0) )
  {
    if ( v6 )
    {
      if ( v6 != -80 )
      {
        *(_QWORD *)(v6 + 80) = 0;
        *(_QWORD *)(v6 + 88) = 0;
      }
      if ( v6 != -64 )
      {
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
      }
      if ( v6 != -48 )
      {
        *(_QWORD *)(v6 + 48) = 0;
        *(_QWORD *)(v6 + 56) = 0;
      }
      if ( v6 != -16 )
      {
        *(_QWORD *)(v6 + 16) = 0;
        *(_QWORD *)(v6 + 24) = 0;
      }
      if ( v6 != -32 )
      {
        *(_QWORD *)(v6 + 32) = 0;
        *(_QWORD *)(v6 + 40) = 0;
      }
      *(_QWORD *)(v6 + 8) = 0;
      *(_QWORD *)v6 = 0;
      *(_QWORD *)(v6 + 96) = 0;
      *(_DWORD *)(v6 + 104) = 48;
      *(_DWORD *)(v6 + 128) = -1;
      if ( v6 != -112 )
      {
        *(_QWORD *)(v6 + 112) = 0;
        *(_QWORD *)(v6 + 120) = 0;
      }
    }
    v8 = JetSetCurrentIndex(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 0);
    v5 = DhcpMapJetError(v8, "JetSetCurrentIndex");
    if ( v5 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        v10 = 27;
        v11 = v8;
LABEL_26:
        WPP_SF_D(v9[2], v10, &WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids, v11);
      }
      goto LABEL_40;
    }
    v12 = JetMove(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 0x80000000, 0);
    if ( (unsigned int)DhcpMapJetError(v12, "JetMove") )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids, v12);
    }
    else
    {
      while ( 1 )
      {
        v16 = HeapAlloc(gDhcpHeap, 8u, 0x88u);
        v17 = v16;
        if ( !v16 )
        {
          v5 = 8;
          goto LABEL_40;
        }
        v16[3] = 0;
        v16[4] = 0;
        v16[1] = 0;
        v16[11] = 0;
        v16[6] = 0;
        v16[7] = 0;
        DBEntry6 = ReadDBEntry6(v16);
        if ( DBEntry6 == 259 )
          break;
        if ( DBEntry6 )
        {
          v5 = 1627;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids);
          }
          goto LABEL_56;
        }
        v5 = MemArrayAddElement(&v41, v17);
        if ( v5 )
        {
          FreeDBEntry6(v17);
LABEL_56:
          HeapFree(gDhcpHeap, 0, v17);
          goto LABEL_40;
        }
        v14 = JetMove(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 1, 0);
        v15 = DhcpMapJetError(v14, "JetMove");
        v5 = v15;
        if ( v15 == 259 )
        {
          v5 = 0;
          goto LABEL_58;
        }
        if ( v15 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          {
            v10 = 30;
            v11 = v15;
            goto LABEL_26;
          }
          goto LABEL_40;
        }
      }
      v5 = 0;
      HeapFree(gDhcpHeap, 0, v17);
LABEL_58:
      if ( (_DWORD)v41 )
      {
        v20 = 0;
        do
        {
          v21 = (__int128 *)*((_QWORD *)lpMem + v20);
          v22 = *((_QWORD *)v21 + 16);
          v23 = v21[1];
          v45 = *v21;
          v24 = v21[2];
          v46 = v23;
          v25 = v21[3];
          v47 = v24;
          v26 = v21[4];
          v48 = v25;
          v27 = v21[5];
          v49 = v26;
          v28 = v21[6];
          v50 = v27;
          v29 = v21[7];
          v51 = v28;
          v52 = v29;
          v53 = v22;
          v30 = AddDBEntry6(v6);
          if ( v30 == 2 )
          {
            v5 = MemArrayAddElement(&v43, v21);
            if ( v5 )
            {
              v3 = v44;
              goto LABEL_40;
            }
          }
          else if ( v30
                 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids, v30);
          }
          ++v20;
        }
        while ( v20 < (unsigned int)v41 );
        v3 = v44;
        v5 = 0;
        v2 = v43;
      }
      if ( !v2 )
      {
LABEL_32:
        *a1 = v6;
        goto LABEL_40;
      }
      for ( i = 0; i < v2; ++i )
      {
        v32 = (unsigned int *)v3[i];
        v33 = *((_QWORD *)v32 + 16);
        v34 = *((_OWORD *)v32 + 1);
        v45 = *(_OWORD *)v32;
        v35 = *((_OWORD *)v32 + 2);
        v46 = v34;
        v36 = *((_OWORD *)v32 + 3);
        v47 = v35;
        v37 = *((_OWORD *)v32 + 4);
        v48 = v36;
        v38 = *((_OWORD *)v32 + 5);
        v49 = v37;
        v39 = *((_OWORD *)v32 + 6);
        v50 = v38;
        v40 = *((_OWORD *)v32 + 7);
        v51 = v39;
        v52 = v40;
        v53 = v33;
        if ( (unsigned int)AddDBEntry6(v6) )
          DeleteDBEntry6(*v32);
      }
    }
    v5 = 0;
    goto LABEL_32;
  }
LABEL_40:
  if ( (_DWORD)v41 )
  {
    v18 = 0;
    do
    {
      v19 = (void *)*((_QWORD *)lpMem + v18);
      FreeDBEntry6(v19);
      HeapFree(gDhcpHeap, 0, v19);
      ++v18;
    }
    while ( v18 < (unsigned int)v41 );
    if ( lpMem )
      MemFree(lpMem);
  }
  if ( v3 )
    MemFree(v3);
  return v5;
}

```

## disassembly

```asm
0x180018d40  mov     [rsp-8+arg_0], rbx
0x180018d45  push    rbp
0x180018d46  push    rsi
0x180018d47  push    rdi
0x180018d48  push    r12
0x180018d4a  push    r13
0x180018d4c  push    r14
0x180018d4e  push    r15
0x180018d50  lea     rbp, [rsp-27h]
0x180018d55  sub     rsp, 0F0h
0x180018d5c  xor     edi, edi
0x180018d5e  mov     r12, rcx
0x180018d61  cmp     cs:DhcpGlobalConfigTableV6, rdi
0x180018d68  mov     r14d, edi
0x180018d6b  mov     [rbp+57h+arg_8], edi
0x180018d6e  mov     r15d, edi
0x180018d71  mov     [rsp+120h+var_E0], rdi
0x180018d76  mov     [rsp+120h+lpMem], rdi
0x180018d7b  mov     [rbp+57h+var_D0], rdi
0x180018d7f  mov     [rbp+57h+var_C8], rdi
0x180018d83  jnz     short loc_180018D8F
0x180018d85  mov     eax, 65Bh
0x180018d8a  jmp     loc_1800191F7
0x180018d8f  test    r12, r12
0x180018d92  jnz     short loc_180018D9E
0x180018d94  mov     edi, 57h ; 'W'
0x180018d99  jmp     loc_18001919A
0x180018d9e  mov     rbx, [rcx]
0x180018da1  test    rbx, rbx
0x180018da4  jnz     short loc_180018DB8
0x180018da6  mov     ecx, 88h; dwBytes
0x180018dab  call    MemAlloc
0x180018db0  mov     rbx, rax
0x180018db3  test    rax, rax
0x180018db6  jz      short loc_180018D94
0x180018db8  mov     edx, cs:DhcpGlobalDatabaseHandle
0x180018dbe  lea     rax, [rbp+57h+tableid]
0x180018dc2  mov     rcx, cs:DhcpGlobalJetServerSession
0x180018dc9  lea     r8, aStatelessclien; "StatelessClients"
0x180018dd0  mov     [rsp+120h+psetinfo], rax
0x180018dd5  xor     r9d, r9d
0x180018dd8  mov     [rsp+120h+grbit], edi
0x180018ddc  mov     r13d, edi
0x180018ddf  mov     [rsp+120h+cbData], edi
0x180018de3  mov     [rbp+57h+tableid], rdi
0x180018de7  call    cs:__imp_JetOpenTable
0x180018dee  nop     dword ptr [rax+rax+00h]
0x180018df3  cmp     eax, 0FFFFFAE7h
0x180018df8  jnz     short loc_180018E02
0x180018dfa  mov     r13d, 1
0x180018e00  jmp     short loc_180018E33
0x180018e02  mov     rdx, [rbp+57h+tableid]; tableid
0x180018e06  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180018e0d  call    cs:__imp_JetCloseTable
0x180018e14  nop     dword ptr [rax+rax+00h]
0x180018e19  mov     ecx, eax
0x180018e1b  lea     rdx, aIsupgradefromp; "IsUpgradeFromPreWin8OS : JetCloseTable "
0x180018e22  call    DhcpMapJetError
0x180018e27  mov     edi, eax
0x180018e29  test    eax, eax
0x180018e2b  jnz     loc_18001919A
0x180018e31  xor     edi, edi
0x180018e33  test    rbx, rbx
0x180018e36  jz      short loc_180018EB4
0x180018e38  lea     rax, [rbx+50h]
0x180018e3c  test    rax, rax
0x180018e3f  jz      short loc_180018E48
0x180018e41  mov     [rax], r14
0x180018e44  mov     [rax+8], rdi
0x180018e48  lea     rax, [rbx+40h]
0x180018e4c  test    rax, rax
0x180018e4f  jz      short loc_180018E58
0x180018e51  mov     [rax], r14
0x180018e54  mov     [rax+8], rdi
0x180018e58  lea     rax, [rbx+30h]
0x180018e5c  test    rax, rax
0x180018e5f  jz      short loc_180018E68
0x180018e61  mov     [rax], r14
0x180018e64  mov     [rax+8], rdi
0x180018e68  lea     rax, [rbx+10h]
0x180018e6c  test    rax, rax
0x180018e6f  jz      short loc_180018E78
0x180018e71  mov     [rax], r14
0x180018e74  mov     [rax+8], rdi
0x180018e78  lea     rax, [rbx+20h]
0x180018e7c  test    rax, rax
0x180018e7f  jz      short loc_180018E88
0x180018e81  mov     [rax], r14
0x180018e84  mov     [rax+8], rdi
0x180018e88  mov     [rbx+8], rdi
0x180018e8c  mov     [rbx], rdi
0x180018e8f  lea     rax, [rbx+70h]
0x180018e93  mov     [rbx+60h], r14
0x180018e97  mov     dword ptr [rbx+68h], 30h ; '0'
0x180018e9e  mov     dword ptr [rbx+80h], 0FFFFFFFFh
0x180018ea8  test    rax, rax
0x180018eab  jz      short loc_180018EB4
0x180018ead  mov     [rax], r14
0x180018eb0  mov     [rax+8], rdi
0x180018eb4  mov     rdx, cs:DhcpGlobalConfigTableV6Handle
0x180018ebb  xor     r8d, r8d
0x180018ebe  mov     rcx, cs:DhcpGlobalJetServerSession
0x180018ec5  call    cs:__imp_JetSetCurrentIndex
0x180018ecc  nop     dword ptr [rax+rax+00h]
0x180018ed1  mov     ecx, eax
0x180018ed3  lea     rdx, aJetsetcurrenti; "JetSetCurrentIndex"
0x180018eda  mov     esi, eax
0x180018edc  call    DhcpMapJetError
0x180018ee1  mov     edi, eax
0x180018ee3  test    eax, eax
0x180018ee5  jz      short loc_180018F28
0x180018ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180018eee  lea     r14, WPP_GLOBAL_Control
0x180018ef5  cmp     rcx, r14
0x180018ef8  jz      loc_18001919A
0x180018efe  test    dword ptr [rcx+1Ch], 800h
0x180018f05  jz      loc_18001919A
0x180018f0b  mov     edx, 1Bh
0x180018f10  mov     r9d, esi
0x180018f13  mov     rcx, [rcx+10h]
0x180018f17  lea     r8, WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids
0x180018f1e  call    WPP_SF_D
0x180018f23  jmp     loc_18001919A
0x180018f28  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x180018f2f  xor     r9d, r9d; grbit
0x180018f32  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180018f39  mov     r8d, 80000000h; cRow
0x180018f3f  call    cs:__imp_JetMove
0x180018f46  nop     dword ptr [rax+rax+00h]
0x180018f4b  mov     ecx, eax
0x180018f4d  lea     rdx, aJetmove; "JetMove"
0x180018f54  mov     edi, eax
0x180018f56  call    DhcpMapJetError
0x180018f5b  test    eax, eax
0x180018f5d  jz      loc_18001916A
0x180018f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f6a  lea     r14, WPP_GLOBAL_Control
0x180018f71  cmp     rcx, r14
0x180018f74  jz      short loc_180018F97
0x180018f76  test    dword ptr [rcx+1Ch], 800h
0x180018f7d  jz      short loc_180018F97
0x180018f7f  mov     rcx, [rcx+10h]
0x180018f83  lea     r8, WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids
0x180018f8a  mov     edx, 1Ch
0x180018f8f  mov     r9d, edi
0x180018f92  call    WPP_SF_D
0x180018f97  xor     edi, edi
0x180018f99  mov     [r12], rbx
0x180018f9d  jmp     loc_18001919A
0x180018fa2  lea     r8, [rbp+57h+arg_8]
0x180018fa6  mov     [rsi+18h], rdi
0x180018faa  mov     edx, r13d
0x180018fad  mov     [rsi+20h], rdi
0x180018fb1  mov     rcx, rsi; pvData
0x180018fb4  mov     [rsi+8], rdi
0x180018fb8  mov     [rsi+58h], rdi
0x180018fbc  mov     [rsi+30h], rdi
0x180018fc0  mov     [rsi+38h], rdi
0x180018fc4  call    ReadDBEntry6
0x180018fc9  cmp     [rbp+57h+arg_8], 1
0x180018fcd  mov     edi, eax
0x180018fcf  jnz     loc_1800190FB
0x180018fd5  test    eax, eax
0x180018fd7  jnz     loc_1800190FB
0x180018fdd  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180018fe4  call    cs:__imp_JetBeginTransaction
0x180018feb  nop     dword ptr [rax+rax+00h]
0x180018ff0  mov     ecx, eax
0x180018ff2  lea     rdx, aJetbegintransa; "JetBeginTransaction Failed"
0x180018ff9  call    DhcpMapJetError
0x180018ffe  mov     edi, eax
0x180019000  test    eax, eax
0x180019002  jnz     loc_18001919A
0x180019008  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x18001900f  lea     r8d, [rax+2]; prep
0x180019013  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001901a  call    cs:__imp_JetPrepareUpdate
0x180019021  nop     dword ptr [rax+rax+00h]
0x180019026  mov     ecx, eax
0x180019028  lea     rdx, aJetprepareupda_0; "JetPrepareUpdate Failed"
0x18001902f  call    DhcpMapJetError
0x180019034  mov     edi, eax
0x180019036  test    eax, eax
0x180019038  jnz     loc_18001919A
0x18001903e  mov     r8, cs:DhcpGlobalConfigTableV6
0x180019045  lea     r9, [rsi+10h]; pvData
0x180019049  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x180019050  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180019057  mov     [rsp+120h+psetinfo], r14; psetinfo
0x18001905c  mov     r8d, [r8+48h]; columnid
0x180019060  mov     [rsp+120h+grbit], r14d; grbit
0x180019065  mov     [rsp+120h+cbData], 4; cbData
0x18001906d  call    cs:__imp_JetSetColumn
0x180019074  nop     dword ptr [rax+rax+00h]
0x180019079  mov     ecx, eax
0x18001907b  lea     rdx, aJetsetcolumnFa; "JetSetColumn Failed"
0x180019082  call    DhcpMapJetError
0x180019087  mov     edi, eax
0x180019089  test    eax, eax
0x18001908b  jnz     loc_18001919A
0x180019091  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x180019098  xor     r9d, r9d; cbBookmark
0x18001909b  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800190a2  xor     r8d, r8d; pvBookmark
0x1800190a5  mov     qword ptr [rsp+120h+cbData], r14; pcbActual
0x1800190aa  call    cs:__imp_JetUpdate
0x1800190b1  nop     dword ptr [rax+rax+00h]
0x1800190b6  mov     ecx, eax
0x1800190b8  lea     rdx, aJetupdateFaile; "JetUpdate Failed"
0x1800190bf  call    DhcpMapJetError
0x1800190c4  mov     edi, eax
0x1800190c6  test    eax, eax
0x1800190c8  jnz     loc_18001919A
0x1800190ce  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800190d5  xor     edx, edx; grbit
0x1800190d7  call    cs:__imp_JetCommitTransaction
0x1800190de  nop     dword ptr [rax+rax+00h]
0x1800190e3  mov     ecx, eax
0x1800190e5  lea     rdx, aJetcommittrans; "JetCommitTransaction Failed"
0x1800190ec  call    DhcpMapJetError
0x1800190f1  mov     edi, eax
0x1800190f3  test    eax, eax
0x1800190f5  jnz     loc_18001919A
0x1800190fb  cmp     edi, 103h
0x180019101  jz      loc_1800192A5
0x180019107  test    edi, edi
0x180019109  jnz     loc_180019252
0x18001910f  mov     rdx, rsi
0x180019112  lea     rcx, [rsp+120h+var_E0]
0x180019117  call    MemArrayAddElement
0x18001911c  mov     edi, eax
0x18001911e  test    eax, eax
0x180019120  jnz     loc_180019248
0x180019126  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x18001912d  lea     r8d, [rax+1]; cRow
0x180019131  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180019138  xor     r9d, r9d; grbit
0x18001913b  call    cs:__imp_JetMove
0x180019142  nop     dword ptr [rax+rax+00h]
0x180019147  mov     ecx, eax
0x180019149  lea     rdx, aJetmove; "JetMove"
0x180019150  call    DhcpMapJetError
0x180019155  mov     edi, eax
0x180019157  cmp     eax, 103h
0x18001915c  jz      loc_180019244
0x180019162  test    eax, eax
0x180019164  jnz     loc_180019213
0x18001916a  mov     rcx, cs:gDhcpHeap; hHeap
0x180019171  mov     r8d, 88h; dwBytes
0x180019177  lea     edx, [r8-80h]; dwFlags
0x18001917b  call    cs:__imp_HeapAlloc
0x180019182  nop     dword ptr [rax+rax+00h]
0x180019187  xor     edi, edi
0x180019189  mov     rsi, rax
0x18001918c  test    rax, rax
0x18001918f  jnz     loc_180018FA2
0x180019195  mov     edi, 8
0x18001919a  cmp     dword ptr [rsp+120h+var_E0], 0
0x18001919f  jbe     short loc_1800191E8
0x1800191a1  xor     esi, esi
0x1800191a3  mov     rax, [rsp+120h+lpMem]
0x1800191a8  mov     ecx, esi
0x1800191aa  mov     rbx, [rax+rcx*8]
0x1800191ae  mov     rcx, rbx
0x1800191b1  call    FreeDBEntry6
0x1800191b6  mov     rcx, cs:gDhcpHeap; hHeap
0x1800191bd  mov     r8, rbx; lpMem
0x1800191c0  xor     edx, edx; dwFlags
0x1800191c2  call    cs:__imp_HeapFree
0x1800191c9  nop     dword ptr [rax+rax+00h]
0x1800191ce  lea     eax, [rsi+1]
0x1800191d1  mov     esi, eax
0x1800191d3  cmp     eax, dword ptr [rsp+120h+var_E0]
0x1800191d7  jb      short loc_1800191A3
0x1800191d9  mov     rcx, [rsp+120h+lpMem]; lpMem
0x1800191de  test    rcx, rcx
0x1800191e1  jz      short loc_1800191E8
0x1800191e3  call    MemFree
0x1800191e8  test    r15, r15
0x1800191eb  jz      short loc_1800191F5
0x1800191ed  mov     rcx, r15; lpMem
0x1800191f0  call    MemFree
0x1800191f5  mov     eax, edi
0x1800191f7  mov     rbx, [rsp+120h+arg_0]
0x1800191ff  add     rsp, 0F0h
0x180019206  pop     r15
0x180019208  pop     r14
0x18001920a  pop     r13
0x18001920c  pop     r12
0x18001920e  pop     rdi
0x18001920f  pop     rsi
0x180019210  pop     rbp
0x180019211  retn
0x180019213  mov     rcx, cs:WPP_GLOBAL_Control
0x18001921a  lea     r14, WPP_GLOBAL_Control
0x180019221  cmp     rcx, r14
0x180019224  jz      loc_18001919A
0x18001922a  test    dword ptr [rcx+1Ch], 800h
0x180019231  jz      loc_18001919A
0x180019237  mov     edx, 1Eh
  ... truncated ...
```
