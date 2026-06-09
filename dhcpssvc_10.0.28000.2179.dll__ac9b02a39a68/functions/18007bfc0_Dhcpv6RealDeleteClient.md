# Dhcpv6RealDeleteClient

- ea: `0x18007bfc0`
- end: `0x18007c47b`
- name: `Dhcpv6RealDeleteClient`
- size: `1211`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007a290`
- `0x18007a9e8`

## callees

- `0x18000282c`
- `0x180003228`
- `0x1800058bc`
- `0x180005924`
- `0x18001120c`
- `0x180012f5c`
- `0x180012fc8`
- `0x180013134`
- `0x180013388`
- `0x180013bb0`
- `0x18007bfc0`
- `0x180091e2c`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetDelete` at `0x18007c335`
- `ESENT!JetDelete` at `0x18007c335`
- `KERNEL32!EnterCriticalSection` at `0x18007c10e`
- `KERNEL32!EnterCriticalSection` at `0x18007c10e`
- `KERNEL32!LeaveCriticalSection` at `0x18007c133`
- `KERNEL32!LeaveCriticalSection` at `0x18007c423`
- `KERNEL32!LeaveCriticalSection` at `0x18007c133`
- `KERNEL32!LeaveCriticalSection` at `0x18007c423`
- `KERNEL32!HeapFree` at `0x18007c441`
- `KERNEL32!HeapFree` at `0x18007c441`

## pseudocode

```c
void __fastcall Dhcpv6RealDeleteClient(__int128 *a1, const wchar_t *a2, char a3)
{
  __int128 v3; // xmm6
  const wchar_t *v5; // rdi
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

  v3 = *a1;
  v5 = a2;
  pcbActual = 0;
  lpMem = 0;
  pvData[0] = 0;
  v31 = 0;
  v7 = L"NULL";
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    LODWORD(v8) = (_DWORD)a2;
    if ( !a2 )
      v8 = L"NULL";
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      (unsigned int)&WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids,
      (_DWORD)v8,
      a3);
  }
  v32 = v3;
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
      WPP_SF_D(v10[2], v11, &WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids, v12);
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
          if ( !v5 )
            v5 = L"NULL";
          WPP_SF_S(v19, v18, &WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids, v5);
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
          WPP_SF_D(v17[2], 55, &WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids, ValueV6);
      }
LABEL_55:
      DhcpJetRollBackV6(DhcpGlobalJetServerSession);
      goto LABEL_70;
    }
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids, pvData[0]);
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
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids, v7);
        v21 = WPP_GLOBAL_Control;
      }
      if ( !v5 )
      {
        if ( lpMem )
          goto LABEL_69;
        goto LABEL_47;
      }
      v22 = &Annotation;
      if ( lpMem )
        v22 = (const size_t *)lpMem;
      v23 = (char *)v22 - (char *)v5;
      do
      {
        v24 = *(const wchar_t *)((char *)v5 + v23);
        v25 = *v5 - v24;
        if ( v25 )
          break;
        ++v5;
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
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids);
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
    WPP_SF_(v26, v27, &WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids);
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
0x18007bfc0  mov     rax, rsp
0x18007bfc3  mov     [rax+18h], rbx
0x18007bfc7  mov     [rax+20h], rsi
0x18007bfcb  push    rbp
0x18007bfcc  push    rdi
0x18007bfcd  push    r13
0x18007bfcf  push    r14
0x18007bfd1  push    r15
0x18007bfd3  lea     rbp, [rax-5Fh]
0x18007bfd7  sub     rsp, 90h
0x18007bfde  movaps  xmmword ptr [rax-38h], xmm6
0x18007bfe2  mov     rax, cs:__security_cookie
0x18007bfe9  xor     rax, rsp
0x18007bfec  mov     [rbp+57h+var_40], rax
0x18007bff0  movups  xmm6, xmmword ptr [rcx]
0x18007bff3  movzx   r15d, r8b
0x18007bff7  mov     rdi, rdx
0x18007bffa  mov     rbx, rcx
0x18007bffd  mov     [rbp+57h+pcbActual], 0
0x18007c004  mov     [rbp+57h+lpMem], 0
0x18007c00c  mov     [rbp+57h+pvData], 0
0x18007c010  mov     [rbp+57h+var_70], 0
0x18007c018  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c01f  lea     r13, WPP_GLOBAL_Control
0x18007c026  lea     r14, aNull_0; "NULL"
0x18007c02d  lea     rsi, WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids
0x18007c034  cmp     rcx, r13
0x18007c037  jz      short loc_18007C062
0x18007c039  test    dword ptr [rcx+1Ch], 40000h
0x18007c040  jz      short loc_18007C062
0x18007c042  mov     rcx, [rcx+10h]
0x18007c046  test    rdx, rdx
0x18007c049  mov     r9, rdx
0x18007c04c  mov     dword ptr [rsp+0B0h+sesid], r15d
0x18007c051  cmovz   r9, r14
0x18007c055  mov     edx, 2Bh ; '+'
0x18007c05a  mov     r8, rsi
0x18007c05d  call    WPP_SF_SD
0x18007c062  mov     rax, cs:DhcpGlobalThisServerV6
0x18007c069  lea     rdx, [rbp+57h+var_70]
0x18007c06d  xor     r9d, r9d
0x18007c070  mov     [rsp+0B0h+sesid], rax
0x18007c075  xor     r8d, r8d
0x18007c078  movdqa  [rbp+57h+var_60], xmm6
0x18007c07d  lea     rcx, [rbp+57h+var_60]
0x18007c081  call    MemServer6GetAddressInfo
0x18007c086  test    eax, eax
0x18007c088  jz      short loc_18007C0BE
0x18007c08a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c091  cmp     rcx, r13
0x18007c094  jz      loc_18007C44D
0x18007c09a  mov     bl, 10h
0x18007c09c  test    [rcx+1Ch], bl
0x18007c09f  jz      loc_18007C44D
0x18007c0a5  mov     edx, 2Ch ; ','
0x18007c0aa  mov     r9d, eax
0x18007c0ad  mov     r8, rsi
0x18007c0b0  mov     rcx, [rcx+10h]
0x18007c0b4  call    WPP_SF_D
0x18007c0b9  jmp     loc_18007C44D
0x18007c0be  mov     rdx, [rbp+57h+var_70]
0x18007c0c2  lea     r8, [rbp+57h+var_50]
0x18007c0c6  movups  xmm0, xmmword ptr [rbx]
0x18007c0c9  lea     rcx, [rbp+57h+var_60]
0x18007c0cd  mov     edx, [rdx+80F4h]
0x18007c0d3  movdqu  [rbp+57h+var_60], xmm0
0x18007c0d8  call    DhcpConvertAddressToDBFormat
0x18007c0dd  test    eax, eax
0x18007c0df  jz      short loc_18007C103
0x18007c0e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c0e8  cmp     rcx, r13
0x18007c0eb  jz      loc_18007C44D
0x18007c0f1  mov     bl, 10h
0x18007c0f3  test    [rcx+1Ch], bl
0x18007c0f6  jz      loc_18007C44D
0x18007c0fc  mov     edx, 2Dh ; '-'
0x18007c101  jmp     short loc_18007C0AA
0x18007c103  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18007c10a  and     r15b, 7
0x18007c10e  call    cs:__imp_EnterCriticalSection
0x18007c115  nop     dword ptr [rax+rax+00h]
0x18007c11a  mov     rcx, cs:DhcpGlobalJetServerSession
0x18007c121  call    DhcpJetBeginTransactionV6
0x18007c126  mov     esi, eax
0x18007c128  test    eax, eax
0x18007c12a  jz      short loc_18007C16E
0x18007c12c  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18007c133  call    cs:__imp_LeaveCriticalSection
0x18007c13a  nop     dword ptr [rax+rax+00h]
0x18007c13f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c146  cmp     rcx, r13
0x18007c149  jz      loc_18007C44D
0x18007c14f  mov     bl, 10h
0x18007c151  test    [rcx+1Ch], bl
0x18007c154  jz      loc_18007C44D
0x18007c15a  mov     edx, 2Eh ; '.'
0x18007c15f  lea     r8, WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids
0x18007c166  mov     r9d, esi
0x18007c169  jmp     loc_18007C0B0
0x18007c16e  mov     rcx, cs:DhcpGlobalClientTableV6
0x18007c175  lea     rdx, [rbp+57h+var_50]
0x18007c179  mov     rax, cs:DhcpGlobalJetServerSession
0x18007c180  mov     r8d, 0Bh
0x18007c186  mov     [rsp+0B0h+sesid], rax
0x18007c18b  mov     rcx, [rcx]
0x18007c18e  call    DhcpJetOpenKeyV6
0x18007c193  mov     esi, eax
0x18007c195  mov     bl, 10h
0x18007c197  test    eax, eax
0x18007c199  jz      short loc_18007C1D8
0x18007c19b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c1a2  cmp     rcx, r13
0x18007c1a5  jz      loc_18007C39A
0x18007c1ab  test    [rcx+1Ch], bl
0x18007c1ae  jz      loc_18007C378
0x18007c1b4  mov     edx, 2Fh ; '/'
0x18007c1b9  mov     rcx, [rcx+10h]
0x18007c1bd  lea     r8, WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids
0x18007c1c4  test    rdi, rdi
0x18007c1c7  cmovz   rdi, r14
0x18007c1cb  mov     r9, rdi
0x18007c1ce  call    WPP_SF_S
0x18007c1d3  jmp     loc_18007C371
0x18007c1d8  mov     rcx, cs:DhcpGlobalClientTableV6
0x18007c1df  lea     r8, [rbp+57h+pcbActual]; pcbActual
0x18007c1e3  mov     rax, cs:DhcpGlobalJetServerSession
0x18007c1ea  lea     rdx, [rbp+57h+pvData]; pvData
0x18007c1ee  mov     [rbp+57h+pcbActual], 1
0x18007c1f5  mov     [rsp+0B0h+sesid], rax; sesid
0x18007c1fa  mov     ecx, [rcx+68h]; columnid
0x18007c1fd  call    DhcpJetGetValueV6
0x18007c202  mov     esi, eax
0x18007c204  test    eax, eax
0x18007c206  jz      short loc_18007C228
0x18007c208  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c20f  cmp     rcx, r13
0x18007c212  jz      loc_18007C39A
0x18007c218  test    [rcx+1Ch], bl
0x18007c21b  jz      loc_18007C378
0x18007c221  mov     edx, 30h ; '0'
0x18007c226  jmp     short loc_18007C1B9
0x18007c228  mov     r10, cs:WPP_GLOBAL_Control
0x18007c22f  cmp     r10, r13
0x18007c232  jz      short loc_18007C25F
0x18007c234  test    dword ptr [r10+1Ch], 10000000h
0x18007c23c  jz      short loc_18007C25F
0x18007c23e  movzx   r9d, [rbp+57h+pvData]
0x18007c243  lea     r8, WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids
0x18007c24a  mov     rcx, [r10+10h]
0x18007c24e  mov     edx, 31h ; '1'
0x18007c253  call    WPP_SF_D
0x18007c258  mov     r10, cs:WPP_GLOBAL_Control
0x18007c25f  mov     al, [rbp+57h+pvData]
0x18007c262  and     al, 0C0h
0x18007c264  cmp     al, 0C0h
0x18007c266  jnz     loc_18007C3F0
0x18007c26c  movzx   ecx, [rbp+57h+pvData]
0x18007c270  and     ecx, 0FFFFF007h
0x18007c276  cmp     r15b, cl
0x18007c279  jnz     loc_18007C3F0
0x18007c27f  mov     rcx, cs:DhcpGlobalClientTableV6
0x18007c286  lea     r8, [rbp+57h+pcbActual]; pcbActual
0x18007c28a  mov     rax, cs:DhcpGlobalJetServerSession
0x18007c291  lea     rdx, [rbp+57h+lpMem]; pvData
0x18007c295  mov     [rbp+57h+pcbActual], 0
0x18007c29c  mov     [rsp+0B0h+sesid], rax; sesid
0x18007c2a1  mov     ecx, [rcx+0B8h]; columnid
0x18007c2a7  call    DhcpJetGetValueV6
0x18007c2ac  mov     esi, eax
0x18007c2ae  test    eax, eax
0x18007c2b0  jz      short loc_18007C2D5
0x18007c2b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c2b9  cmp     rcx, r13
0x18007c2bc  jz      loc_18007C39A
0x18007c2c2  test    [rcx+1Ch], bl
0x18007c2c5  jz      loc_18007C378
0x18007c2cb  mov     edx, 33h ; '3'
0x18007c2d0  jmp     loc_18007C1B9
0x18007c2d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c2dc  cmp     rcx, r13
0x18007c2df  jz      short loc_18007C314
0x18007c2e1  test    dword ptr [rcx+1Ch], 10000000h
0x18007c2e8  jz      short loc_18007C314
0x18007c2ea  mov     rax, [rbp+57h+lpMem]
0x18007c2ee  lea     r8, WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids
0x18007c2f5  mov     rcx, [rcx+10h]
0x18007c2f9  test    rax, rax
0x18007c2fc  mov     edx, 34h ; '4'
0x18007c301  cmovnz  r14, rax
0x18007c305  mov     r9, r14
0x18007c308  call    WPP_SF_S
0x18007c30d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c314  test    rdi, rdi
0x18007c317  jnz     loc_18007C3A8
0x18007c31d  cmp     [rbp+57h+lpMem], rdi
0x18007c321  jnz     loc_18007C410
0x18007c327  mov     rdx, cs:DhcpGlobalClientTableV6Handle; tableid
0x18007c32e  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18007c335  call    cs:__imp_JetDelete
0x18007c33c  nop     dword ptr [rax+rax+00h]
0x18007c341  mov     esi, eax
0x18007c343  test    eax, eax
0x18007c345  jz      loc_18007C410
0x18007c34b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c352  cmp     rcx, r13
0x18007c355  jz      short loc_18007C39A
0x18007c357  test    [rcx+1Ch], bl
0x18007c35a  jz      short loc_18007C378
0x18007c35c  mov     rcx, [rcx+10h]
0x18007c360  lea     r8, WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids
0x18007c367  mov     edx, 36h ; '6'
0x18007c36c  call    WPP_SF_
0x18007c371  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c378  cmp     rcx, r13
0x18007c37b  jz      short loc_18007C39A
0x18007c37d  test    [rcx+1Ch], bl
0x18007c380  jz      short loc_18007C39A
0x18007c382  mov     rcx, [rcx+10h]
0x18007c386  lea     r8, WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids
0x18007c38d  mov     edx, 37h ; '7'
0x18007c392  mov     r9d, esi
0x18007c395  call    WPP_SF_D
0x18007c39a  mov     rcx, cs:DhcpGlobalJetServerSession
0x18007c3a1  call    DhcpJetRollBackV6
0x18007c3a6  jmp     short loc_18007C41C
0x18007c3a8  mov     rax, [rbp+57h+lpMem]
0x18007c3ac  lea     rdx, Annotation
0x18007c3b3  test    rax, rax
0x18007c3b6  cmovnz  rdx, rax
0x18007c3ba  sub     rdx, rdi
0x18007c3bd  movzx   eax, word ptr [rdi]
0x18007c3c0  movzx   r8d, word ptr [rdi+rdx]
0x18007c3c5  sub     eax, r8d
0x18007c3c8  jnz     short loc_18007C3D3
0x18007c3ca  add     rdi, 2
0x18007c3ce  test    r8d, r8d
0x18007c3d1  jnz     short loc_18007C3BD
0x18007c3d3  test    eax, eax
0x18007c3d5  jz      loc_18007C327
0x18007c3db  cmp     rcx, r13
0x18007c3de  jz      short loc_18007C410
0x18007c3e0  test    [rcx+1Ch], bl
0x18007c3e3  jz      short loc_18007C410
0x18007c3e5  mov     rcx, [rcx+10h]
0x18007c3e9  mov     edx, 35h ; '5'
0x18007c3ee  jmp     short loc_18007C404
0x18007c3f0  cmp     r10, r13
0x18007c3f3  jz      short loc_18007C410
0x18007c3f5  test    [r10+1Ch], bl
0x18007c3f9  jz      short loc_18007C410
0x18007c3fb  mov     rcx, [r10+10h]
0x18007c3ff  mov     edx, 32h ; '2'
0x18007c404  lea     r8, WPP_cf21f7b16ab23d11150dbdb97e06e7c4_Traceguids
0x18007c40b  call    WPP_SF_
0x18007c410  mov     rcx, cs:DhcpGlobalJetServerSession
0x18007c417  call    DhcpJetCommitTransactionV6
0x18007c41c  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18007c423  call    cs:__imp_LeaveCriticalSection
0x18007c42a  nop     dword ptr [rax+rax+00h]
0x18007c42f  mov     r8, [rbp+57h+lpMem]; lpMem
0x18007c433  test    r8, r8
0x18007c436  jz      short loc_18007C44D
0x18007c438  mov     rcx, cs:gDhcpHeap; hHeap
0x18007c43f  xor     edx, edx; dwFlags
0x18007c441  call    cs:__imp_HeapFree
0x18007c448  nop     dword ptr [rax+rax+00h]
0x18007c44d  mov     rcx, [rbp+57h+var_40]
0x18007c451  xor     rcx, rsp; StackCookie
0x18007c454  call    __security_check_cookie
0x18007c459  lea     r11, [rsp+0B0h+var_20]
0x18007c461  mov     rbx, [r11+40h]
0x18007c465  mov     rsi, [r11+48h]
0x18007c469  movaps  xmm6, xmmword ptr [r11-10h]
0x18007c46e  mov     rsp, r11
0x18007c471  pop     r15
0x18007c473  pop     r14
0x18007c475  pop     r13
0x18007c477  pop     rdi
0x18007c478  pop     rbp
0x18007c479  retn
```
