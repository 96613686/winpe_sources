# LsaDbpDsFixupTrustedDomainObjectOnRestart(void)

- ea: `0x180014df0`
- end: `0x18001510e`
- name: `?LsaDbpDsFixupTrustedDomainObjectOnRestart@@YAJXZ`
- size: `798`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800117b0`
- `0x180015120`

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x18000fee8`
- `0x180014a40`
- `0x180014df0`
- `0x180015748`
- `0x180015790`
- `0x180019044`
- `0x18001f574`
- `0x18001fbcc`

## import_xrefs

- `LSASRV!LsapOpenSam` at `0x180014ee5`
- `LSASRV!LsapOpenSam` at `0x180014ee5`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180014f0c`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180014f59`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180014f0c`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180014f59`
- `LSASRV!LsaIRegisterNotification` at `0x1800150d8`
- `LSASRV!LsaIRegisterNotification` at `0x1800150d8`
- `SAMSRV!SamrEnumerateUsersInDomain` at `0x180014f81`
- `SAMSRV!SamrEnumerateUsersInDomain` at `0x180014f81`
- `SAMSRV!SamIQueryServerRole` at `0x180014f19`
- `SAMSRV!SamIQueryServerRole` at `0x180014f19`
- `SAMSRV!SamIFree_SAMPR_ENUMERATION_BUFFER` at `0x180015068`
- `SAMSRV!SamIFree_SAMPR_ENUMERATION_BUFFER` at `0x180015068`

## pseudocode

```c
__int64 LsaDbpDsFixupTrustedDomainObjectOnRestart(void)
{
  int inited; // eax
  unsigned int v1; // ecx
  unsigned int v2; // ebx
  char v4; // r15
  int ListOfSystemContainerItems; // eax
  __int64 v6; // r8
  int v7; // ebx
  unsigned int v8; // esi
  int v9; // eax
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 AccountDomainHandle; // rax
  int v14; // eax
  void *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdi
  struct _DSNAME **v19; // r14
  struct _SAMPR_RID_ENUMERATION *v20; // r9
  int v21; // eax
  int v22; // [rsp+40h] [rbp-28h] BYREF
  __int64 v23; // [rsp+48h] [rbp-20h] BYREF
  struct _DSNAME **v24; // [rsp+50h] [rbp-18h] BYREF
  char v25; // [rsp+A0h] [rbp+38h] BYREF
  unsigned int v26; // [rsp+A8h] [rbp+40h] BYREF
  unsigned int v27; // [rsp+B0h] [rbp+48h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+50h] BYREF

  v24 = 0;
  v28 = 0;
  v25 = 0;
  v22 = 0;
  v23 = 0;
  v27 = 0;
  v26 = 3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
  inited = LsaDbpDsInitAllocAsNeededEx(0x2000000, 2, &v25);
  v2 = inited;
  if ( inited < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
        (unsigned int)inited);
    return v2;
  }
  v4 = 0;
  ListOfSystemContainerItems = LsaDbpDsGetListOfSystemContainerItems(v1, &v28, &v24);
  v7 = ListOfSystemContainerItems;
  if ( ListOfSystemContainerItems == -1073741772 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
    v8 = 0;
LABEL_13:
    LsaDbpSaveDsThreadState();
    v9 = LsapOpenSam();
    v7 = v9;
    if ( v9 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v12 = 13;
LABEL_23:
        WPP_SF_d(v11[2], v12, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, (unsigned int)v9);
        goto LABEL_24;
      }
      goto LABEL_24;
    }
    AccountDomainHandle = LsapGetAccountDomainHandle(v10);
    v14 = SamIQueryServerRole(AccountDomainHandle, &v26);
    v7 = v14;
    v15 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v26, v14);
    if ( v7 < 0 || v26 != 3 )
      goto LABEL_29;
    v16 = LsapGetAccountDomainHandle(v15);
    v9 = SamrEnumerateUsersInDomain(v16, &v22, 64, &v23, -1, &v27);
    v7 = v9;
    if ( v9 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v12 = 15;
        goto LABEL_23;
      }
LABEL_24:
      LsaDbpRestoreDsThreadState();
      goto LABEL_25;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v27);
      LsaDbpRestoreDsThreadState();
    }
    else
    {
LABEL_29:
      LsaDbpRestoreDsThreadState();
      if ( v7 < 0 )
      {
LABEL_25:
        if ( v7 == -1073741772 )
          v7 = 0;
        goto LABEL_41;
      }
    }
    if ( v26 == 3 )
    {
      v18 = 0;
      if ( v8 )
      {
        v19 = v24;
        do
        {
          if ( v23 )
            v20 = *(struct _SAMPR_RID_ENUMERATION **)(v23 + 8);
          else
            v20 = 0;
          v21 = LsaDbpDsFixupTrustedDomainObject(v19[v18], v17, v27, v20);
          v7 = v21;
          if ( v21 < 0 )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
                (unsigned int)v21);
            v4 = 1;
          }
          v18 = (unsigned int)(v18 + 1);
        }
        while ( (unsigned int)v18 < v8 );
      }
    }
    goto LABEL_41;
  }
  if ( ListOfSystemContainerItems >= 0 )
  {
    v8 = v28;
    goto LABEL_13;
  }
LABEL_41:
  if ( v23 )
    SamIFree_SAMPR_ENUMERATION_BUFFER();
  LOBYTE(v6) = v25;
  LsaDbpDsDeleteAllocAsNeededEx2(0x2000000, 2, v6, (unsigned int)v7 >> 31);
  if ( v7 < 0 || v4 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
    LsaIRegisterNotification(LsaDbpDsFixupTrustedDomainOnRestartCallback, 0, 1);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180014df0  push    rbp
0x180014df2  push    rbx
0x180014df3  push    rsi
0x180014df4  push    rdi
0x180014df5  push    r14
0x180014df7  push    r15
0x180014df9  mov     rbp, rsp
0x180014dfc  sub     rsp, 68h
0x180014e00  mov     [rbp+var_18], 0
0x180014e08  mov     [rbp+arg_18], 0
0x180014e0f  mov     [rbp+arg_0], 0
0x180014e13  mov     [rbp+var_28], 0
0x180014e1a  mov     [rbp+var_20], 0
0x180014e22  mov     [rbp+arg_10], 0
0x180014e29  mov     [rbp+arg_8], 3
0x180014e30  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e37  lea     rdi, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180014e3e  test    byte ptr [rcx+1Ch], 4
0x180014e42  jz      short loc_180014E55
0x180014e44  mov     rcx, [rcx+10h]
0x180014e48  mov     edx, 0Ah
0x180014e4d  mov     r8, rdi
0x180014e50  call    WPP_SF_
0x180014e55  lea     r8, [rbp+arg_0]
0x180014e59  mov     edx, 2
0x180014e5e  mov     ecx, 2000000h
0x180014e63  call    ?LsaDbpDsInitAllocAsNeededEx@@YAJKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAE@Z; LsaDbpDsInitAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar *)
0x180014e68  mov     ebx, eax
0x180014e6a  test    eax, eax
0x180014e6c  jns     short loc_180014E96
0x180014e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e75  test    byte ptr [rcx+1Ch], 4
0x180014e79  jz      short loc_180014E8F
0x180014e7b  mov     rcx, [rcx+10h]
0x180014e7f  mov     edx, 0Bh
0x180014e84  mov     r9d, eax
0x180014e87  mov     r8, rdi
0x180014e8a  call    WPP_SF_d
0x180014e8f  mov     eax, ebx
0x180014e91  jmp     loc_180015101
0x180014e96  lea     r8, [rbp+var_18]; struct _DSNAME ***
0x180014e9a  xor     r15b, r15b
0x180014e9d  lea     rdx, [rbp+arg_18]; unsigned int *
0x180014ea1  call    ?LsaDbpDsGetListOfSystemContainerItems@@YAJKPEAKPEAPEAPEAU_DSNAME@@@Z; LsaDbpDsGetListOfSystemContainerItems(ulong,ulong *,_DSNAME * * *)
0x180014ea6  mov     r14d, 0C0000034h
0x180014eac  mov     ebx, eax
0x180014eae  cmp     eax, r14d
0x180014eb1  jnz     short loc_180014ED5
0x180014eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180014eba  test    byte ptr [rcx+1Ch], 4
0x180014ebe  jz      short loc_180014ED1
0x180014ec0  mov     rcx, [rcx+10h]
0x180014ec4  mov     edx, 0Ch
0x180014ec9  mov     r8, rdi
0x180014ecc  call    WPP_SF_
0x180014ed1  xor     esi, esi
0x180014ed3  jmp     short loc_180014EE0
0x180014ed5  test    eax, eax
0x180014ed7  js      loc_18001505F
0x180014edd  mov     esi, [rbp+arg_18]
0x180014ee0  call    ?LsaDbpSaveDsThreadState@@YAXXZ; LsaDbpSaveDsThreadState(void)
0x180014ee5  call    cs:__imp_LsapOpenSam
0x180014eeb  mov     ebx, eax
0x180014eed  test    eax, eax
0x180014eef  jns     short loc_180014F0C
0x180014ef1  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ef8  test    byte ptr [rcx+1Ch], 4
0x180014efc  jz      loc_180014FAE
0x180014f02  mov     edx, 0Dh
0x180014f07  jmp     loc_180014F9F
0x180014f0c  call    cs:__imp_LsapGetAccountDomainHandle
0x180014f12  mov     rcx, rax
0x180014f15  lea     rdx, [rbp+arg_8]
0x180014f19  call    cs:__imp_SamIQueryServerRole
0x180014f1f  mov     ebx, eax
0x180014f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f28  test    byte ptr [rcx+1Ch], 4
0x180014f2c  jz      short loc_180014F47
0x180014f2e  mov     r9d, [rbp+arg_8]
0x180014f32  mov     edx, 0Eh
0x180014f37  mov     rcx, [rcx+10h]
0x180014f3b  mov     r8, rdi
0x180014f3e  mov     [rsp+68h+var_48], eax
0x180014f42  call    WPP_SF_dd
0x180014f47  test    ebx, ebx
0x180014f49  js      loc_180014FEC
0x180014f4f  cmp     [rbp+arg_8], 3
0x180014f53  jnz     loc_180014FEC
0x180014f59  call    cs:__imp_LsapGetAccountDomainHandle
0x180014f5f  lea     r9, [rbp+var_20]
0x180014f63  mov     r8d, 40h ; '@'
0x180014f69  mov     rcx, rax
0x180014f6c  lea     rdx, [rbp+var_28]
0x180014f70  lea     rax, [rbp+arg_10]
0x180014f74  mov     [rsp+68h+var_40], rax
0x180014f79  mov     [rsp+68h+var_48], 0FFFFFFFFh
0x180014f81  call    cs:__imp_SamrEnumerateUsersInDomain
0x180014f87  mov     ebx, eax
0x180014f89  test    eax, eax
0x180014f8b  jns     short loc_180014FC3
0x180014f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f94  test    byte ptr [rcx+1Ch], 4
0x180014f98  jz      short loc_180014FAE
0x180014f9a  mov     edx, 0Fh
0x180014f9f  mov     rcx, [rcx+10h]
0x180014fa3  mov     r9d, eax
0x180014fa6  mov     r8, rdi
0x180014fa9  call    WPP_SF_d
0x180014fae  call    ?LsaDbpRestoreDsThreadState@@YAXXZ; LsaDbpRestoreDsThreadState(void)
0x180014fb3  cmp     ebx, r14d
0x180014fb6  jnz     loc_18001505F
0x180014fbc  xor     ebx, ebx
0x180014fbe  jmp     loc_18001505F
0x180014fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fca  test    byte ptr [rcx+1Ch], 4
0x180014fce  jz      short loc_180014FEC
0x180014fd0  mov     r9d, [rbp+arg_10]
0x180014fd4  mov     edx, 10h
0x180014fd9  mov     rcx, [rcx+10h]
0x180014fdd  mov     r8, rdi
0x180014fe0  call    WPP_SF_d
0x180014fe5  call    ?LsaDbpRestoreDsThreadState@@YAXXZ; LsaDbpRestoreDsThreadState(void)
0x180014fea  jmp     short loc_180014FF5
0x180014fec  call    ?LsaDbpRestoreDsThreadState@@YAXXZ; LsaDbpRestoreDsThreadState(void)
0x180014ff1  test    ebx, ebx
0x180014ff3  js      short loc_180014FB3
0x180014ff5  cmp     [rbp+arg_8], 3
0x180014ff9  jnz     short loc_18001505F
0x180014ffb  xor     edi, edi
0x180014ffd  test    esi, esi
0x180014fff  jz      short loc_180015058
0x180015001  mov     r14, [rbp+var_18]
0x180015005  mov     rax, [rbp+var_20]
0x180015009  test    rax, rax
0x18001500c  jz      short loc_180015014
0x18001500e  mov     r9, [rax+8]
0x180015012  jmp     short loc_180015017
0x180015014  xor     r9d, r9d; struct _SAMPR_RID_ENUMERATION *
0x180015017  mov     r8d, [rbp+arg_10]; unsigned int
0x18001501b  mov     rcx, [r14+rdi*8]; struct _DSNAME *
0x18001501f  call    ?LsaDbpDsFixupTrustedDomainObject@@YAJPEAU_DSNAME@@EKPEAU_SAMPR_RID_ENUMERATION@@@Z; LsaDbpDsFixupTrustedDomainObject(_DSNAME *,uchar,ulong,_SAMPR_RID_ENUMERATION *)
0x180015024  mov     ebx, eax
0x180015026  test    eax, eax
0x180015028  jns     short loc_180015052
0x18001502a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015031  test    byte ptr [rcx+1Ch], 4
0x180015035  jz      short loc_18001504F
0x180015037  mov     rcx, [rcx+10h]
0x18001503b  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180015042  mov     edx, 11h
0x180015047  mov     r9d, eax
0x18001504a  call    WPP_SF_d
0x18001504f  mov     r15b, 1
0x180015052  inc     edi
0x180015054  cmp     edi, esi
0x180015056  jb      short loc_180015005
0x180015058  lea     rdi, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x18001505f  mov     rcx, [rbp+var_20]
0x180015063  test    rcx, rcx
0x180015066  jz      short loc_18001506E
0x180015068  call    cs:__imp_SamIFree_SAMPR_ENUMERATION_BUFFER
0x18001506e  mov     r8b, [rbp+arg_0]
0x180015072  mov     r9d, ebx
0x180015075  shr     r9d, 1Fh
0x180015079  mov     edx, 2
0x18001507e  mov     ecx, 2000000h
0x180015083  call    ?LsaDbpDsDeleteAllocAsNeededEx2@@YAXKW4_LSAP_DB_OBJECT_TYPE_ID@@EE@Z; LsaDbpDsDeleteAllocAsNeededEx2(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar,uchar)
0x180015088  test    ebx, ebx
0x18001508a  js      short loc_180015091
0x18001508c  test    r15b, r15b
0x18001508f  jz      short loc_1800150DE
0x180015091  mov     rcx, cs:WPP_GLOBAL_Control
0x180015098  test    byte ptr [rcx+1Ch], 4
0x18001509c  jz      short loc_1800150AF
0x18001509e  mov     rcx, [rcx+10h]
0x1800150a2  mov     edx, 12h
0x1800150a7  mov     r8, rdi
0x1800150aa  call    WPP_SF_
0x1800150af  xor     r9d, r9d
0x1800150b2  mov     [rsp+68h+var_38], 0
0x1800150bb  mov     dword ptr [rsp+68h+var_40], 258h
0x1800150c3  lea     rcx, ?LsaDbpDsFixupTrustedDomainOnRestartCallback@@YAJPEAX@Z; LsaDbpDsFixupTrustedDomainOnRestartCallback(void *)
0x1800150ca  xor     edx, edx
0x1800150cc  mov     [rsp+68h+var_48], 2
0x1800150d4  lea     r8d, [r9+1]
0x1800150d8  call    cs:__imp_LsaIRegisterNotification
0x1800150de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150e5  test    byte ptr [rcx+1Ch], 4
0x1800150e9  jz      short loc_1800150FF
0x1800150eb  mov     rcx, [rcx+10h]
0x1800150ef  mov     edx, 13h
0x1800150f4  xor     r9d, r9d
0x1800150f7  mov     r8, rdi
0x1800150fa  call    WPP_SF_d
0x1800150ff  xor     eax, eax
0x180015101  add     rsp, 68h
0x180015105  pop     r15
0x180015107  pop     r14
0x180015109  pop     rdi
0x18001510a  pop     rsi
0x18001510b  pop     rbx
0x18001510c  pop     rbp
0x18001510d  retn
```
