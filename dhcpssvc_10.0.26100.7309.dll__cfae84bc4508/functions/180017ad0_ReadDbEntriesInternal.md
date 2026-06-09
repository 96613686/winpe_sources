# ReadDbEntriesInternal

- ea: `0x180017ad0`
- end: `0x180017fb4`
- name: `ReadDbEntriesInternal`
- size: `1252`
- prototype: `__int64 __fastcall(JET_SESID sesid, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800174c0`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000f144`
- `0x180015e00`
- `0x180016ff0`
- `0x180017ad0`
- `0x180017fbc`
- `0x18008f124`
- `0x1800947e4`
- `0x1800948b0`
- `0x180096080`
- `0x1800cc99a`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x180017b1b`
- `ESENT!JetSetCurrentIndex` at `0x180017b1b`
- `ESENT!JetMove` at `0x180017b7d`
- `ESENT!JetMove` at `0x180017d8e`
- `ESENT!JetMove` at `0x180017b7d`
- `ESENT!JetMove` at `0x180017d8e`
- `KERNEL32!HeapAlloc` at `0x180017c13`
- `KERNEL32!HeapAlloc` at `0x180017cb4`
- `KERNEL32!HeapAlloc` at `0x180017c13`
- `KERNEL32!HeapAlloc` at `0x180017cb4`
- `KERNEL32!HeapFree` at `0x180017bf5`
- `KERNEL32!HeapFree` at `0x180017d71`
- `KERNEL32!HeapFree` at `0x180017e92`
- `KERNEL32!HeapFree` at `0x180017eef`
- `KERNEL32!HeapFree` at `0x180017f07`
- `KERNEL32!HeapFree` at `0x180017bf5`
- `KERNEL32!HeapFree` at `0x180017d71`
- `KERNEL32!HeapFree` at `0x180017e92`
- `KERNEL32!HeapFree` at `0x180017eef`
- `KERNEL32!HeapFree` at `0x180017f07`

## string_xrefs

- `0x180017b8b`: `C:JetMoveFirst2`
- `0x180017d9c`: `C:JetMove2`

## pseudocode

```c
__int64 __fastcall ReadDbEntriesInternal(JET_SESID sesid, __int64 a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // eax
  char *v9; // rdi
  unsigned int v10; // r12d
  char *v11; // rax
  unsigned int DbEntry; // eax
  _OWORD *v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // r13
  void *v17; // rcx
  unsigned int v18; // esi
  int v19; // r12d
  _QWORD *v20; // rdi
  unsigned int v21; // eax
  void *v22; // r8
  unsigned int v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v27; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v28[9]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 lpMem; // [rsp+F0h] [rbp-10h]
  __int64 v30; // [rsp+100h] [rbp+0h]
  int v32; // [rsp+160h] [rbp+60h]
  int v33; // [rsp+168h] [rbp+68h]

  memset_0(v28, 0, 0xA8u);
  v32 = 0;
  v27 = 0;
  v33 = 0;
  v3 = JetSetCurrentIndex(sesid, DbcfgTbl, 0);
  v4 = DhcpMapJetError(v3, "C:SetIndex2");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      return v4;
    v6 = 36;
    goto LABEL_65;
  }
  v7 = JetMove(sesid, DbcfgTbl, 0x80000000, 0);
  v8 = DhcpMapJetError(v7, "C:JetMoveFirst2");
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v8);
  v24[1] = 0;
  v24[0] = 0;
  v25 = 0;
  do
  {
    v9 = 0;
    v10 = 512;
    do
    {
      if ( v9 )
        HeapFree(gDhcpHeap, 0, v9);
      v10 *= 2;
      v11 = (char *)HeapAlloc(gDhcpHeap, 8u, v10);
      v9 = v11;
      if ( !v11 )
      {
        v4 = 8;
        goto LABEL_62;
      }
      DbEntry = ReadDbEntry(sesid, (char *)v28, v11, v10);
      v4 = DbEntry;
    }
    while ( DbEntry == 122 );
    if ( (v28[0] & 1) == 0 || (v28[0] & 2) == 0 )
    {
      if ( !DbEntry )
        v4 = 1359;
LABEL_44:
      HeapFree(gDhcpHeap, 0, v9);
      if ( v4 == 259 )
      {
LABEL_45:
        v16 = a2;
        v4 = 0;
        *(_DWORD *)(a2 + 152) = DWORD1(v28[0]);
        goto LABEL_30;
      }
LABEL_62:
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
        return v4;
      v6 = 38;
LABEL_65:
      WPP_SF_D(v5[2], v6, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v4);
      return v4;
    }
    if ( DbEntry )
      goto LABEL_44;
    *(_QWORD *)&lpMem = v9;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids);
    if ( (unsigned int)AddDbEntryEx(a2, v28) == 2 )
    {
      v4 = 8;
      v13 = HeapAlloc(gDhcpHeap, 8u, 0xA8u);
      v27 = v13;
      if ( !v13 )
        return v4;
      *v13 = v28[0];
      v13[1] = v28[1];
      v13[2] = v28[2];
      v13[3] = v28[3];
      v13[4] = v28[4];
      v13[5] = v28[5];
      v13[6] = v28[6];
      v13[7] = v28[7];
      v13[8] = v28[8];
      v13[9] = lpMem;
      *((_QWORD *)v13 + 20) = v30;
      v4 = MemArrayAddElement(v24, (__int64)v13);
      if ( v4 )
      {
LABEL_23:
        if ( v25 )
          MemFree(v25);
        return v4;
      }
    }
    else if ( (_QWORD)lpMem )
    {
      HeapFree(gDhcpHeap, 0, (LPVOID)lpMem);
    }
    v14 = JetMove(sesid, DbcfgTbl, 1, 0);
    v15 = DhcpMapJetError(v14, "C:JetMove2");
    v4 = v15;
  }
  while ( !v15 );
  if ( v15 == 259 )
    goto LABEL_45;
  v16 = a2;
LABEL_30:
  v17 = WPP_GLOBAL_Control;
  v18 = v24[0];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v24[0]);
LABEL_33:
  if ( v18 )
  {
    v26 = 0;
    v19 = v32;
    while ( 1 )
    {
      --v18;
      MemArrayDelElement(v24, &v26, &v27);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids);
      }
      v20 = v27;
      v21 = AddDbEntryEx(v16, v27);
      v4 = v21;
      if ( v21 == 2 )
      {
        if ( v32 != 4 )
        {
          v4 = MemArrayAddElement(v24, (__int64)v20);
          if ( v4 )
            goto LABEL_23;
          goto LABEL_52;
        }
      }
      else if ( !v21 )
      {
        goto LABEL_49;
      }
      v33 = 1;
      if ( v20 )
      {
        v4 = DeleteRecord(*((unsigned int *)v20 + 1));
LABEL_49:
        v22 = (void *)v20[18];
        if ( v22 )
          HeapFree(gDhcpHeap, 0, v22);
        HeapFree(gDhcpHeap, 0, v20);
      }
LABEL_52:
      if ( !v18 )
      {
        ++v32;
        if ( (unsigned int)(v19 + 1) < 5 )
        {
          v18 = v24[0];
          goto LABEL_33;
        }
        break;
      }
    }
  }
  if ( v33 )
    DhcpReportEventW(v17, 1065, 1);
  if ( v4 == 2 )
  {
    if ( v25 )
      MemFree(v25);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180017ad0  mov     [rsp-8+arg_8], rdx
0x180017ad5  push    rbp
0x180017ad6  push    rbx
0x180017ad7  push    rsi
0x180017ad8  push    rdi
0x180017ad9  push    r12
0x180017adb  push    r13
0x180017add  push    r14
0x180017adf  lea     rbp, [rsp-10h]
0x180017ae4  sub     rsp, 110h
0x180017aeb  mov     r13, rcx
0x180017aee  xor     edx, edx; Val
0x180017af0  lea     rcx, [rsp+140h+var_E0]; void *
0x180017af5  mov     r8d, 0A8h; Size
0x180017afb  call    memset_0
0x180017b00  mov     rdx, cs:DbcfgTbl
0x180017b07  xor     eax, eax
0x180017b09  and     [rbp+40h+arg_10], eax
0x180017b0c  xor     r8d, r8d
0x180017b0f  and     [rsp+140h+var_E8], 0
0x180017b15  mov     rcx, r13
0x180017b18  mov     [rbp+40h+arg_18], eax
0x180017b1b  call    cs:__imp_JetSetCurrentIndex
0x180017b22  nop     dword ptr [rax+rax+00h]
0x180017b27  mov     ecx, eax
0x180017b29  lea     rdx, aCSetindex2; "C:SetIndex2"
0x180017b30  call    DhcpMapJetError
0x180017b35  mov     ebx, eax
0x180017b37  test    eax, eax
0x180017b39  jz      short loc_180017B6A
0x180017b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b42  lea     r14, WPP_GLOBAL_Control
0x180017b49  cmp     rcx, r14
0x180017b4c  jz      loc_180017F9F
0x180017b52  mov     esi, 800h
0x180017b57  test    [rcx+1Ch], esi
0x180017b5a  jz      loc_180017F9F
0x180017b60  mov     edx, 24h ; '$'
0x180017b65  jmp     loc_180017F8C
0x180017b6a  mov     rdx, cs:DbcfgTbl; tableid
0x180017b71  xor     r9d, r9d; grbit
0x180017b74  mov     r8d, 80000000h; cRow
0x180017b7a  mov     rcx, r13; sesid
0x180017b7d  call    cs:__imp_JetMove
0x180017b84  nop     dword ptr [rax+rax+00h]
0x180017b89  mov     ecx, eax
0x180017b8b  lea     rdx, aCJetmovefirst2; "C:JetMoveFirst2"
0x180017b92  call    DhcpMapJetError
0x180017b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b9e  lea     r14, WPP_GLOBAL_Control
0x180017ba5  mov     esi, 800h
0x180017baa  cmp     rcx, r14
0x180017bad  jz      short loc_180017BCC
0x180017baf  test    [rcx+1Ch], esi
0x180017bb2  jz      short loc_180017BCC
0x180017bb4  mov     rcx, [rcx+10h]
0x180017bb8  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180017bbf  mov     edx, 25h ; '%'
0x180017bc4  mov     r9d, eax
0x180017bc7  call    WPP_SF_D
0x180017bcc  and     [rsp+140h+var_FC], 0
0x180017bd1  and     [rsp+140h+var_100], 0
0x180017bd6  and     [rsp+140h+var_F8], 0
0x180017bdc  xor     edi, edi
0x180017bde  mov     r12d, 200h
0x180017be4  test    rdi, rdi
0x180017be7  jz      short loc_180017C01
0x180017be9  mov     rcx, cs:gDhcpHeap; hHeap
0x180017bf0  mov     r8, rdi; lpMem
0x180017bf3  xor     edx, edx; dwFlags
0x180017bf5  call    cs:__imp_HeapFree
0x180017bfc  nop     dword ptr [rax+rax+00h]
0x180017c01  mov     rcx, cs:gDhcpHeap; hHeap
0x180017c08  add     r12d, r12d
0x180017c0b  mov     r8d, r12d; dwBytes
0x180017c0e  mov     edx, 8; dwFlags
0x180017c13  call    cs:__imp_HeapAlloc
0x180017c1a  nop     dword ptr [rax+rax+00h]
0x180017c1f  mov     rdi, rax
0x180017c22  test    rax, rax
0x180017c25  jz      loc_180017F71
0x180017c2b  mov     r9d, r12d; cbData
0x180017c2e  lea     rdx, [rsp+140h+var_E0]; void *
0x180017c33  mov     r8, rax; void *
0x180017c36  mov     rcx, r13; sesid
0x180017c39  call    ReadDbEntry
0x180017c3e  mov     ebx, eax
0x180017c40  cmp     eax, 7Ah ; 'z'
0x180017c43  jz      short loc_180017BE4
0x180017c45  test    [rsp+140h+var_E0], 1
0x180017c4a  jz      loc_180017E7C
0x180017c50  test    [rsp+140h+var_E0], 2
0x180017c55  jz      loc_180017E7C
0x180017c5b  test    eax, eax
0x180017c5d  jnz     loc_180017E86
0x180017c63  mov     qword ptr [rbp+40h+lpMem], rdi
0x180017c67  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c6e  cmp     rcx, r14
0x180017c71  jz      short loc_180017C8B
0x180017c73  test    [rcx+1Ch], esi
0x180017c76  jz      short loc_180017C8B
0x180017c78  mov     rcx, [rcx+10h]
0x180017c7c  lea     edx, [rax+20h]
0x180017c7f  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180017c86  call    WPP_SF_
0x180017c8b  mov     rcx, [rbp+40h+arg_8]
0x180017c8f  lea     rdx, [rsp+140h+var_E0]
0x180017c94  call    AddDbEntryEx
0x180017c99  cmp     eax, 2
0x180017c9c  jnz     loc_180017D5F
0x180017ca2  mov     rcx, cs:gDhcpHeap; hHeap
0x180017ca9  lea     ebx, [rax+6]
0x180017cac  mov     edx, ebx; dwFlags
0x180017cae  mov     r8d, 0A8h; dwBytes
0x180017cb4  call    cs:__imp_HeapAlloc
0x180017cbb  nop     dword ptr [rax+rax+00h]
0x180017cc0  mov     [rsp+140h+var_E8], rax
0x180017cc5  mov     rdx, rax
0x180017cc8  test    rax, rax
0x180017ccb  jz      loc_180017F9F
0x180017cd1  lea     rax, [rsp+140h+var_E0]
0x180017cd6  movups  xmm0, xmmword ptr [rax]
0x180017cd9  lea     r8d, [rbx+78h]
0x180017cdd  lea     rcx, [r8+rdx]
0x180017ce1  movups  xmmword ptr [rdx], xmm0
0x180017ce4  movups  xmm1, xmmword ptr [rax+10h]
0x180017ce8  movups  xmmword ptr [rdx+10h], xmm1
0x180017cec  movups  xmm0, xmmword ptr [rax+20h]
0x180017cf0  movups  xmmword ptr [rdx+20h], xmm0
0x180017cf4  movups  xmm1, xmmword ptr [rax+30h]
0x180017cf8  movups  xmmword ptr [rdx+30h], xmm1
0x180017cfc  movups  xmm0, xmmword ptr [rax+40h]
0x180017d00  movups  xmmword ptr [rdx+40h], xmm0
0x180017d04  movups  xmm1, xmmword ptr [rax+50h]
0x180017d08  movups  xmmword ptr [rdx+50h], xmm1
0x180017d0c  movups  xmm0, xmmword ptr [rax+60h]
0x180017d10  movups  xmmword ptr [rdx+60h], xmm0
0x180017d14  movups  xmm1, xmmword ptr [rax+70h]
0x180017d18  movups  xmmword ptr [rcx-10h], xmm1
0x180017d1c  movups  xmm0, xmmword ptr [rax+r8]
0x180017d21  movups  xmmword ptr [rcx], xmm0
0x180017d24  movups  xmm1, xmmword ptr [rax+r8+10h]
0x180017d2a  movups  xmmword ptr [rcx+10h], xmm1
0x180017d2e  mov     rax, [rax+r8+20h]
0x180017d33  mov     [rcx+20h], rax
0x180017d37  lea     rcx, [rsp+140h+var_100]
0x180017d3c  call    MemArrayAddElement
0x180017d41  mov     ebx, eax
0x180017d43  test    eax, eax
0x180017d45  jz      short loc_180017D7D
0x180017d47  mov     rcx, [rsp+140h+var_F8]; lpMem
0x180017d4c  test    rcx, rcx
0x180017d4f  jz      loc_180017F9F
0x180017d55  call    MemFree
0x180017d5a  jmp     loc_180017F9F
0x180017d5f  mov     r8, qword ptr [rbp+40h+lpMem]; lpMem
0x180017d63  test    r8, r8
0x180017d66  jz      short loc_180017D7D
0x180017d68  mov     rcx, cs:gDhcpHeap; hHeap
0x180017d6f  xor     edx, edx; dwFlags
0x180017d71  call    cs:__imp_HeapFree
0x180017d78  nop     dword ptr [rax+rax+00h]
0x180017d7d  mov     rdx, cs:DbcfgTbl; tableid
0x180017d84  xor     r9d, r9d; grbit
0x180017d87  mov     rcx, r13; sesid
0x180017d8a  lea     r8d, [r9+1]; cRow
0x180017d8e  call    cs:__imp_JetMove
0x180017d95  nop     dword ptr [rax+rax+00h]
0x180017d9a  mov     ecx, eax
0x180017d9c  lea     rdx, aCJetmove2; "C:JetMove2"
0x180017da3  call    DhcpMapJetError
0x180017da8  mov     ebx, eax
0x180017daa  test    eax, eax
0x180017dac  jz      loc_180017BDC
0x180017db2  cmp     eax, 103h
0x180017db7  jz      loc_180017EAA
0x180017dbd  mov     r13, [rbp+40h+arg_8]
0x180017dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180017dc8  mov     esi, [rsp+140h+var_100]
0x180017dcc  cmp     rcx, r14
0x180017dcf  jz      short loc_180017DF2
0x180017dd1  test    dword ptr [rcx+1Ch], 10000000h
0x180017dd8  jz      short loc_180017DF2
0x180017dda  mov     rcx, [rcx+10h]
0x180017dde  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180017de5  mov     edx, 27h ; '''
0x180017dea  mov     r9d, esi
0x180017ded  call    WPP_SF_D
0x180017df2  test    esi, esi
0x180017df4  jz      loc_180017F31
0x180017dfa  and     [rsp+140h+var_F0], 0
0x180017dff  mov     r12d, [rbp+40h+arg_10]
0x180017e03  dec     esi
0x180017e05  lea     r8, [rsp+140h+var_E8]
0x180017e0a  lea     rdx, [rsp+140h+var_F0]
0x180017e0f  lea     rcx, [rsp+140h+var_100]
0x180017e14  call    MemArrayDelElement
0x180017e19  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e20  cmp     rcx, r14
0x180017e23  jz      short loc_180017E43
0x180017e25  test    dword ptr [rcx+1Ch], 10000000h
0x180017e2c  jz      short loc_180017E43
0x180017e2e  mov     rcx, [rcx+10h]
0x180017e32  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180017e39  mov     edx, 28h ; '('
0x180017e3e  call    WPP_SF_
0x180017e43  mov     rdi, [rsp+140h+var_E8]
0x180017e48  mov     rcx, r13
0x180017e4b  mov     rdx, rdi
0x180017e4e  call    AddDbEntryEx
0x180017e53  mov     ebx, eax
0x180017e55  cmp     eax, 2
0x180017e58  jnz     short loc_180017EC0
0x180017e5a  cmp     r12d, 4
0x180017e5e  jz      short loc_180017EC4
0x180017e60  mov     rdx, rdi
0x180017e63  lea     rcx, [rsp+140h+var_100]
0x180017e68  call    MemArrayAddElement
0x180017e6d  mov     ebx, eax
0x180017e6f  test    eax, eax
0x180017e71  jnz     loc_180017D47
0x180017e77  jmp     loc_180017F13
0x180017e7c  test    ebx, ebx
0x180017e7e  mov     eax, 54Fh
0x180017e83  cmovz   ebx, eax
0x180017e86  mov     rcx, cs:gDhcpHeap; hHeap
0x180017e8d  mov     r8, rdi; lpMem
0x180017e90  xor     edx, edx; dwFlags
0x180017e92  call    cs:__imp_HeapFree
0x180017e99  nop     dword ptr [rax+rax+00h]
0x180017e9e  cmp     ebx, 103h
0x180017ea4  jnz     loc_180017F76
0x180017eaa  mov     r13, [rbp+40h+arg_8]
0x180017eae  xor     ebx, ebx
0x180017eb0  mov     eax, [rsp+140h+var_DC]
0x180017eb4  mov     [r13+98h], eax
0x180017ebb  jmp     loc_180017DC1
0x180017ec0  test    eax, eax
0x180017ec2  jz      short loc_180017EDA
0x180017ec4  mov     [rbp+40h+arg_18], 1
0x180017ecb  test    rdi, rdi
0x180017ece  jz      short loc_180017F13
0x180017ed0  mov     ecx, [rdi+4]
0x180017ed3  call    DeleteRecord
0x180017ed8  mov     ebx, eax
0x180017eda  mov     r8, [rdi+90h]; lpMem
0x180017ee1  test    r8, r8
0x180017ee4  jz      short loc_180017EFB
0x180017ee6  mov     rcx, cs:gDhcpHeap; hHeap
0x180017eed  xor     edx, edx; dwFlags
0x180017eef  call    cs:__imp_HeapFree
0x180017ef6  nop     dword ptr [rax+rax+00h]
0x180017efb  mov     rcx, cs:gDhcpHeap; hHeap
0x180017f02  mov     r8, rdi; lpMem
0x180017f05  xor     edx, edx; dwFlags
0x180017f07  call    cs:__imp_HeapFree
0x180017f0e  nop     dword ptr [rax+rax+00h]
0x180017f13  test    esi, esi
0x180017f15  jnz     loc_180017E03
0x180017f1b  mov     eax, r12d
0x180017f1e  inc     eax
0x180017f20  mov     [rbp+40h+arg_10], eax
0x180017f23  cmp     eax, 5
0x180017f26  jnb     short loc_180017F31
0x180017f28  mov     esi, [rsp+140h+var_100]
0x180017f2c  jmp     loc_180017DF2
0x180017f31  cmp     [rbp+40h+arg_18], 0
0x180017f35  jz      short loc_180017F59
0x180017f37  and     [rsp+140h+var_110], 0
0x180017f3d  xor     r9d, r9d
0x180017f40  and     [rsp+140h+var_118], 0
0x180017f46  mov     edx, 429h
0x180017f4b  and     [rsp+140h+var_120], 0
0x180017f50  lea     r8d, [r9+1]
0x180017f54  call    DhcpReportEventW
0x180017f59  cmp     ebx, 2
0x180017f5c  jnz     short loc_180017F9F
0x180017f5e  mov     rcx, [rsp+140h+var_F8]; lpMem
0x180017f63  test    rcx, rcx
0x180017f66  jz      short loc_180017F6D
0x180017f68  call    MemFree
0x180017f6d  xor     ebx, ebx
0x180017f6f  jmp     short loc_180017F9F
0x180017f71  mov     ebx, 8
0x180017f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f7d  cmp     rcx, r14
0x180017f80  jz      short loc_180017F9F
0x180017f82  test    [rcx+1Ch], esi
0x180017f85  jz      short loc_180017F9F
0x180017f87  mov     edx, 26h ; '&'
0x180017f8c  mov     rcx, [rcx+10h]
0x180017f90  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180017f97  mov     r9d, ebx
0x180017f9a  call    WPP_SF_D
0x180017f9f  mov     eax, ebx
0x180017fa1  add     rsp, 110h
0x180017fa8  pop     r14
0x180017faa  pop     r13
0x180017fac  pop     r12
0x180017fae  pop     rdi
  ... truncated ...
```
