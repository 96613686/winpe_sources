# Dhcpv6RealDeleteClient

- ea: `0x18007c168`
- end: `0x18007c617`
- name: `Dhcpv6RealDeleteClient`
- size: `1199`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007a380`
- `0x18007abcc`

## callees

- `0x180002854`
- `0x18000323c`
- `0x1800058cc`
- `0x180005934`
- `0x180011adc`
- `0x180013824`
- `0x180013890`
- `0x1800139f8`
- `0x180013c34`
- `0x180014464`
- `0x18007c168`
- `0x180091c44`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetDelete` at `0x18007c4d1`
- `ESENT!JetDelete` at `0x18007c4d1`
- `KERNEL32!EnterCriticalSection` at `0x18007c2ad`
- `KERNEL32!EnterCriticalSection` at `0x18007c2ad`
- `KERNEL32!LeaveCriticalSection` at `0x18007c2d2`
- `KERNEL32!LeaveCriticalSection` at `0x18007c5bf`
- `KERNEL32!LeaveCriticalSection` at `0x18007c2d2`
- `KERNEL32!LeaveCriticalSection` at `0x18007c5bf`
- `KERNEL32!HeapFree` at `0x18007c5dd`
- `KERNEL32!HeapFree` at `0x18007c5dd`

## pseudocode

```c
void __fastcall Dhcpv6RealDeleteClient(__int128 *a1, const wchar_t *a2, char a3)
{
  const wchar_t *v3; // rdi
  __int128 v5; // xmm6
  const wchar_t *v7; // r14
  const wchar_t *v8; // r9
  unsigned int AddressInfo; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rdx
  char v14; // r15
  unsigned int v15; // esi
  unsigned int ValueV6; // esi
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  _BYTE *v20; // r10
  _BYTE *v21; // rcx
  const size_t *v22; // rdx
  signed __int64 v23; // rdx
  int v24; // r8d
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  _BYTE pvData[4]; // [rsp+38h] [rbp-29h] BYREF
  unsigned int pcbActual; // [rsp+3Ch] [rbp-25h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-21h] BYREF
  __int64 v31; // [rsp+48h] [rbp-19h] BYREF
  __int128 v32; // [rsp+58h] [rbp-9h] BYREF
  _BYTE v33[16]; // [rsp+68h] [rbp+7h] BYREF

  pcbActual = 0;
  v3 = a2;
  lpMem = 0;
  v31 = 0;
  v5 = *a1;
  pvData[0] = 0;
  v7 = L"NULL";
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    LODWORD(v8) = (_DWORD)a2;
    if ( !a2 )
      v8 = L"NULL";
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      (unsigned int)&WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids,
      (_DWORD)v8,
      a3);
  }
  v32 = v5;
  AddressInfo = MemServer6GetAddressInfo((unsigned int)&v32, (unsigned int)&v31, 0, 0, (__int64)DhcpGlobalThisServerV6);
  if ( AddressInfo )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v11 = 44;
LABEL_10:
      v12 = AddressInfo;
LABEL_11:
      WPP_SF_D(v10[2], v11, &WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids, v12);
      return;
    }
    return;
  }
  v13 = *(unsigned int *)(v31 + 33012);
  v32 = *a1;
  AddressInfo = DhcpConvertAddressToDBFormat(&v32, v13, v33);
  if ( !AddressInfo )
  {
    v14 = a3 & 7;
    EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    v15 = DhcpJetBeginTransactionV6(DhcpGlobalJetServerSession);
    if ( v15 )
    {
      LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v11 = 46;
        v12 = v15;
        goto LABEL_11;
      }
      return;
    }
    ValueV6 = DhcpJetOpenKeyV6(*(_QWORD *)DhcpGlobalClientTableV6, v33, 11);
    if ( ValueV6 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v18 = 47;
LABEL_24:
          v19 = v17[2];
          if ( !v3 )
            v3 = L"NULL";
          WPP_SF_S(v19, v18, &WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids, v3);
          goto LABEL_51;
        }
        goto LABEL_52;
      }
      goto LABEL_55;
    }
    pcbActual = 1;
    ValueV6 = DhcpJetGetValueV6(
                *(_DWORD *)(DhcpGlobalClientTableV6 + 104),
                pvData,
                &pcbActual,
                DhcpGlobalJetServerSession);
    if ( ValueV6 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v18 = 48;
          goto LABEL_24;
        }
LABEL_52:
        if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 0x10) != 0 )
          WPP_SF_D(v17[2], 55, &WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids, ValueV6);
      }
LABEL_55:
      DhcpJetRollBackV6(DhcpGlobalJetServerSession);
      goto LABEL_70;
    }
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids, pvData[0]);
      v20 = WPP_GLOBAL_Control;
    }
    if ( (pvData[0] & 0xC0) == 0xC0 && v14 == (pvData[0] & 7) )
    {
      pcbActual = 0;
      ValueV6 = DhcpJetGetValueV6(
                  *(_DWORD *)(DhcpGlobalClientTableV6 + 184),
                  &lpMem,
                  &pcbActual,
                  DhcpGlobalJetServerSession);
      if ( ValueV6 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v18 = 51;
            goto LABEL_24;
          }
          goto LABEL_52;
        }
        goto LABEL_55;
      }
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      {
        if ( lpMem )
          v7 = (const wchar_t *)lpMem;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids, v7);
        v21 = WPP_GLOBAL_Control;
      }
      if ( !v3 )
      {
        if ( lpMem )
          goto LABEL_69;
        goto LABEL_47;
      }
      v22 = &Annotation;
      if ( lpMem )
        v22 = (const size_t *)lpMem;
      v23 = (char *)v22 - (char *)v3;
      do
      {
        v24 = *(const wchar_t *)((char *)v3 + v23);
        v25 = *v3 - v24;
        if ( v25 )
          break;
        ++v3;
      }
      while ( v24 );
      if ( !v25 )
      {
LABEL_47:
        ValueV6 = JetDelete(DhcpGlobalJetServerSession, DhcpGlobalClientTableV6Handle);
        if ( ValueV6 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids);
LABEL_51:
              v17 = WPP_GLOBAL_Control;
              goto LABEL_52;
            }
            goto LABEL_52;
          }
          goto LABEL_55;
        }
LABEL_69:
        DhcpJetCommitTransactionV6(DhcpGlobalJetServerSession);
LABEL_70:
        LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
        if ( lpMem )
          HeapFree(gDhcpHeap, 0, lpMem);
        return;
      }
      if ( v21 == (_BYTE *)&WPP_GLOBAL_Control || (v21[28] & 0x10) == 0 )
        goto LABEL_69;
      v26 = *((_QWORD *)v21 + 2);
      v27 = 53;
    }
    else
    {
      if ( v20 == (_BYTE *)&WPP_GLOBAL_Control || (v20[28] & 0x10) == 0 )
        goto LABEL_69;
      v26 = *((_QWORD *)v20 + 2);
      v27 = 50;
    }
    WPP_SF_(v26, v27, &WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids);
    goto LABEL_69;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v11 = 45;
    goto LABEL_10;
  }
}

```

## disassembly

```asm
0x18007c168  mov     rax, rsp
0x18007c16b  mov     [rax+18h], rbx
0x18007c16f  mov     [rax+20h], rsi
0x18007c173  push    rbp
0x18007c174  push    rdi
0x18007c175  push    r13
0x18007c177  push    r14
0x18007c179  push    r15
0x18007c17b  lea     rbp, [rax-5Fh]
0x18007c17f  sub     rsp, 90h
0x18007c186  movaps  xmmword ptr [rax-38h], xmm6
0x18007c18a  mov     rax, cs:__security_cookie
0x18007c191  xor     rax, rsp
0x18007c194  mov     [rbp+57h+var_40], rax
0x18007c198  and     [rbp+57h+pcbActual], 0
0x18007c19c  mov     rdi, rdx
0x18007c19f  and     [rbp+57h+lpMem], 0
0x18007c1a4  mov     rbx, rcx
0x18007c1a7  and     [rbp+57h+var_70], 0
0x18007c1ac  movups  xmm6, xmmword ptr [rcx]
0x18007c1af  movzx   r15d, r8b
0x18007c1b3  mov     [rbp+57h+pvData], 0
0x18007c1b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c1be  lea     r13, WPP_GLOBAL_Control
0x18007c1c5  lea     r14, aNull_0; "NULL"
0x18007c1cc  lea     rsi, WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids
0x18007c1d3  cmp     rcx, r13
0x18007c1d6  jz      short loc_18007C201
0x18007c1d8  test    dword ptr [rcx+1Ch], 40000h
0x18007c1df  jz      short loc_18007C201
0x18007c1e1  mov     rcx, [rcx+10h]
0x18007c1e5  test    rdx, rdx
0x18007c1e8  mov     r9, rdx
0x18007c1eb  mov     dword ptr [rsp+0B0h+sesid], r15d
0x18007c1f0  cmovz   r9, r14
0x18007c1f4  mov     edx, 2Bh ; '+'
0x18007c1f9  mov     r8, rsi
0x18007c1fc  call    WPP_SF_SD
0x18007c201  mov     rax, cs:DhcpGlobalThisServerV6
0x18007c208  lea     rdx, [rbp+57h+var_70]
0x18007c20c  xor     r9d, r9d
0x18007c20f  mov     [rsp+0B0h+sesid], rax
0x18007c214  xor     r8d, r8d
0x18007c217  movdqa  [rbp+57h+var_60], xmm6
0x18007c21c  lea     rcx, [rbp+57h+var_60]
0x18007c220  call    MemServer6GetAddressInfo
0x18007c225  test    eax, eax
0x18007c227  jz      short loc_18007C25D
0x18007c229  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c230  cmp     rcx, r13
0x18007c233  jz      loc_18007C5E9
0x18007c239  mov     bl, 10h
0x18007c23b  test    [rcx+1Ch], bl
0x18007c23e  jz      loc_18007C5E9
0x18007c244  mov     edx, 2Ch ; ','
0x18007c249  mov     r9d, eax
0x18007c24c  mov     r8, rsi
0x18007c24f  mov     rcx, [rcx+10h]
0x18007c253  call    WPP_SF_D
0x18007c258  jmp     loc_18007C5E9
0x18007c25d  mov     rdx, [rbp+57h+var_70]
0x18007c261  lea     r8, [rbp+57h+var_50]
0x18007c265  movups  xmm0, xmmword ptr [rbx]
0x18007c268  lea     rcx, [rbp+57h+var_60]
0x18007c26c  mov     edx, [rdx+80F4h]
0x18007c272  movdqu  [rbp+57h+var_60], xmm0
0x18007c277  call    DhcpConvertAddressToDBFormat
0x18007c27c  test    eax, eax
0x18007c27e  jz      short loc_18007C2A2
0x18007c280  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c287  cmp     rcx, r13
0x18007c28a  jz      loc_18007C5E9
0x18007c290  mov     bl, 10h
0x18007c292  test    [rcx+1Ch], bl
0x18007c295  jz      loc_18007C5E9
0x18007c29b  mov     edx, 2Dh ; '-'
0x18007c2a0  jmp     short loc_18007C249
0x18007c2a2  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18007c2a9  and     r15b, 7
0x18007c2ad  call    cs:__imp_EnterCriticalSection
0x18007c2b4  nop     dword ptr [rax+rax+00h]
0x18007c2b9  mov     rcx, cs:DhcpGlobalJetServerSession
0x18007c2c0  call    DhcpJetBeginTransactionV6
0x18007c2c5  mov     esi, eax
0x18007c2c7  test    eax, eax
0x18007c2c9  jz      short loc_18007C30D
0x18007c2cb  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18007c2d2  call    cs:__imp_LeaveCriticalSection
0x18007c2d9  nop     dword ptr [rax+rax+00h]
0x18007c2de  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c2e5  cmp     rcx, r13
0x18007c2e8  jz      loc_18007C5E9
0x18007c2ee  mov     bl, 10h
0x18007c2f0  test    [rcx+1Ch], bl
0x18007c2f3  jz      loc_18007C5E9
0x18007c2f9  mov     edx, 2Eh ; '.'
0x18007c2fe  lea     r8, WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids
0x18007c305  mov     r9d, esi
0x18007c308  jmp     loc_18007C24F
0x18007c30d  mov     rcx, cs:DhcpGlobalClientTableV6
0x18007c314  lea     rdx, [rbp+57h+var_50]
0x18007c318  mov     rax, cs:DhcpGlobalJetServerSession
0x18007c31f  mov     r8d, 0Bh
0x18007c325  mov     [rsp+0B0h+sesid], rax
0x18007c32a  mov     rcx, [rcx]
0x18007c32d  call    DhcpJetOpenKeyV6
0x18007c332  mov     esi, eax
0x18007c334  mov     bl, 10h
0x18007c336  test    eax, eax
0x18007c338  jz      short loc_18007C377
0x18007c33a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c341  cmp     rcx, r13
0x18007c344  jz      loc_18007C536
0x18007c34a  test    [rcx+1Ch], bl
0x18007c34d  jz      loc_18007C514
0x18007c353  mov     edx, 2Fh ; '/'
0x18007c358  mov     rcx, [rcx+10h]
0x18007c35c  lea     r8, WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids
0x18007c363  test    rdi, rdi
0x18007c366  cmovz   rdi, r14
0x18007c36a  mov     r9, rdi
0x18007c36d  call    WPP_SF_S
0x18007c372  jmp     loc_18007C50D
0x18007c377  mov     rcx, cs:DhcpGlobalClientTableV6
0x18007c37e  lea     r8, [rbp+57h+pcbActual]; pcbActual
0x18007c382  mov     rax, cs:DhcpGlobalJetServerSession
0x18007c389  lea     rdx, [rbp+57h+pvData]; pvData
0x18007c38d  mov     [rbp+57h+pcbActual], 1
0x18007c394  mov     [rsp+0B0h+sesid], rax; sesid
0x18007c399  mov     ecx, [rcx+68h]; columnid
0x18007c39c  call    DhcpJetGetValueV6
0x18007c3a1  mov     esi, eax
0x18007c3a3  test    eax, eax
0x18007c3a5  jz      short loc_18007C3C7
0x18007c3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c3ae  cmp     rcx, r13
0x18007c3b1  jz      loc_18007C536
0x18007c3b7  test    [rcx+1Ch], bl
0x18007c3ba  jz      loc_18007C514
0x18007c3c0  mov     edx, 30h ; '0'
0x18007c3c5  jmp     short loc_18007C358
0x18007c3c7  mov     r10, cs:WPP_GLOBAL_Control
0x18007c3ce  cmp     r10, r13
0x18007c3d1  jz      short loc_18007C3FE
0x18007c3d3  test    dword ptr [r10+1Ch], 10000000h
0x18007c3db  jz      short loc_18007C3FE
0x18007c3dd  movzx   r9d, [rbp+57h+pvData]
0x18007c3e2  lea     r8, WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids
0x18007c3e9  mov     rcx, [r10+10h]
0x18007c3ed  mov     edx, 31h ; '1'
0x18007c3f2  call    WPP_SF_D
0x18007c3f7  mov     r10, cs:WPP_GLOBAL_Control
0x18007c3fe  mov     al, [rbp+57h+pvData]
0x18007c401  and     al, 0C0h
0x18007c403  cmp     al, 0C0h
0x18007c405  jnz     loc_18007C58C
0x18007c40b  movzx   ecx, [rbp+57h+pvData]
0x18007c40f  and     ecx, 0FFFFF007h
0x18007c415  cmp     r15b, cl
0x18007c418  jnz     loc_18007C58C
0x18007c41e  mov     rcx, cs:DhcpGlobalClientTableV6
0x18007c425  lea     r8, [rbp+57h+pcbActual]; pcbActual
0x18007c429  and     [rbp+57h+pcbActual], 0
0x18007c42d  lea     rdx, [rbp+57h+lpMem]; pvData
0x18007c431  mov     rax, cs:DhcpGlobalJetServerSession
0x18007c438  mov     [rsp+0B0h+sesid], rax; sesid
0x18007c43d  mov     ecx, [rcx+0B8h]; columnid
0x18007c443  call    DhcpJetGetValueV6
0x18007c448  mov     esi, eax
0x18007c44a  test    eax, eax
0x18007c44c  jz      short loc_18007C471
0x18007c44e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c455  cmp     rcx, r13
0x18007c458  jz      loc_18007C536
0x18007c45e  test    [rcx+1Ch], bl
0x18007c461  jz      loc_18007C514
0x18007c467  mov     edx, 33h ; '3'
0x18007c46c  jmp     loc_18007C358
0x18007c471  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c478  cmp     rcx, r13
0x18007c47b  jz      short loc_18007C4B0
0x18007c47d  test    dword ptr [rcx+1Ch], 10000000h
0x18007c484  jz      short loc_18007C4B0
0x18007c486  mov     rax, [rbp+57h+lpMem]
0x18007c48a  lea     r8, WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids
0x18007c491  mov     rcx, [rcx+10h]
0x18007c495  test    rax, rax
0x18007c498  mov     edx, 34h ; '4'
0x18007c49d  cmovnz  r14, rax
0x18007c4a1  mov     r9, r14
0x18007c4a4  call    WPP_SF_S
0x18007c4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c4b0  test    rdi, rdi
0x18007c4b3  jnz     loc_18007C544
0x18007c4b9  cmp     [rbp+57h+lpMem], rdi
0x18007c4bd  jnz     loc_18007C5AC
0x18007c4c3  mov     rdx, cs:DhcpGlobalClientTableV6Handle; tableid
0x18007c4ca  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18007c4d1  call    cs:__imp_JetDelete
0x18007c4d8  nop     dword ptr [rax+rax+00h]
0x18007c4dd  mov     esi, eax
0x18007c4df  test    eax, eax
0x18007c4e1  jz      loc_18007C5AC
0x18007c4e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c4ee  cmp     rcx, r13
0x18007c4f1  jz      short loc_18007C536
0x18007c4f3  test    [rcx+1Ch], bl
0x18007c4f6  jz      short loc_18007C514
0x18007c4f8  mov     rcx, [rcx+10h]
0x18007c4fc  lea     r8, WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids
0x18007c503  mov     edx, 36h ; '6'
0x18007c508  call    WPP_SF_
0x18007c50d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c514  cmp     rcx, r13
0x18007c517  jz      short loc_18007C536
0x18007c519  test    [rcx+1Ch], bl
0x18007c51c  jz      short loc_18007C536
0x18007c51e  mov     rcx, [rcx+10h]
0x18007c522  lea     r8, WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids
0x18007c529  mov     edx, 37h ; '7'
0x18007c52e  mov     r9d, esi
0x18007c531  call    WPP_SF_D
0x18007c536  mov     rcx, cs:DhcpGlobalJetServerSession
0x18007c53d  call    DhcpJetRollBackV6
0x18007c542  jmp     short loc_18007C5B8
0x18007c544  mov     rax, [rbp+57h+lpMem]
0x18007c548  lea     rdx, Annotation
0x18007c54f  test    rax, rax
0x18007c552  cmovnz  rdx, rax
0x18007c556  sub     rdx, rdi
0x18007c559  movzx   eax, word ptr [rdi]
0x18007c55c  movzx   r8d, word ptr [rdi+rdx]
0x18007c561  sub     eax, r8d
0x18007c564  jnz     short loc_18007C56F
0x18007c566  add     rdi, 2
0x18007c56a  test    r8d, r8d
0x18007c56d  jnz     short loc_18007C559
0x18007c56f  test    eax, eax
0x18007c571  jz      loc_18007C4C3
0x18007c577  cmp     rcx, r13
0x18007c57a  jz      short loc_18007C5AC
0x18007c57c  test    [rcx+1Ch], bl
0x18007c57f  jz      short loc_18007C5AC
0x18007c581  mov     rcx, [rcx+10h]
0x18007c585  mov     edx, 35h ; '5'
0x18007c58a  jmp     short loc_18007C5A0
0x18007c58c  cmp     r10, r13
0x18007c58f  jz      short loc_18007C5AC
0x18007c591  test    [r10+1Ch], bl
0x18007c595  jz      short loc_18007C5AC
0x18007c597  mov     rcx, [r10+10h]
0x18007c59b  mov     edx, 32h ; '2'
0x18007c5a0  lea     r8, WPP_557c1eb90a5d34dd8305787f84f7fc1b_Traceguids
0x18007c5a7  call    WPP_SF_
0x18007c5ac  mov     rcx, cs:DhcpGlobalJetServerSession
0x18007c5b3  call    DhcpJetCommitTransactionV6
0x18007c5b8  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18007c5bf  call    cs:__imp_LeaveCriticalSection
0x18007c5c6  nop     dword ptr [rax+rax+00h]
0x18007c5cb  mov     r8, [rbp+57h+lpMem]; lpMem
0x18007c5cf  test    r8, r8
0x18007c5d2  jz      short loc_18007C5E9
0x18007c5d4  mov     rcx, cs:gDhcpHeap; hHeap
0x18007c5db  xor     edx, edx; dwFlags
0x18007c5dd  call    cs:__imp_HeapFree
0x18007c5e4  nop     dword ptr [rax+rax+00h]
0x18007c5e9  mov     rcx, [rbp+57h+var_40]
0x18007c5ed  xor     rcx, rsp; StackCookie
0x18007c5f0  call    __security_check_cookie
0x18007c5f5  lea     r11, [rsp+0B0h+var_20]
0x18007c5fd  mov     rbx, [r11+40h]
0x18007c601  mov     rsi, [r11+48h]
0x18007c605  movaps  xmm6, xmmword ptr [r11-10h]
0x18007c60a  mov     rsp, r11
0x18007c60d  pop     r15
0x18007c60f  pop     r14
0x18007c611  pop     r13
0x18007c613  pop     rdi
0x18007c614  pop     rbp
0x18007c615  retn
```
