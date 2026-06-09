# CFveApiBase::GetSecureBootValidationInfo(_FVE_DATUM_VALIDATION_INFO * *)

- ea: `0x18009c550`
- end: `0x18009c909`
- name: `?GetSecureBootValidationInfo@CFveApiBase@@QEAAJPEAPEAU_FVE_DATUM_VALIDATION_INFO@@@Z`
- size: `953`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this, struct _FVE_DATUM_VALIDATION_INFO **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18009e2f8`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x18001b260`
- `0x18001d0a0`
- `0x180044da4`
- `0x18004f700`
- `0x18009c550`
- `0x18009f3d0`
- `0x180119c58`
- `0x18011f010`

## import_xrefs

- `bcd!BcdQueryObject` at `0x18009c6d5`
- `bcd!BcdQueryObject` at `0x18009c6d5`
- `bcd!BcdCloseObject` at `0x18009c89b`
- `bcd!BcdCloseObject` at `0x18009c89b`
- `bcd!BcdOpenObject` at `0x18009c68b`
- `bcd!BcdOpenObject` at `0x18009c68b`
- `bcd!BcdCloseStore` at `0x18009c8ab`
- `bcd!BcdCloseStore` at `0x18009c8ab`
- `bcd!BcdOpenSystemStore` at `0x18009c63f`
- `bcd!BcdOpenSystemStore` at `0x18009c63f`

## pseudocode

```c
__int64 __fastcall CFveApiBase::GetSecureBootValidationInfo(CFveApiBase *this, struct _FVE_DATUM_VALIDATION_INFO **a2)
{
  int First; // eax
  int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  PVOID *v8; // r10
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // r8
  char v16; // di
  int v17; // eax
  __int64 v18; // rcx
  char v20; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v21[7]; // [rsp+41h] [rbp-28h] BYREF
  __int64 v22; // [rsp+48h] [rbp-21h] BYREF
  __int64 v23; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+58h] [rbp-11h] BYREF
  __int128 v25; // [rsp+60h] [rbp-9h] BYREF
  _OWORD v26[2]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v27; // [rsp+90h] [rbp+27h]

  v22 = 0;
  v23 = 0;
  v25 = 0;
  v27 = 0;
  memset(v26, 0, sizeof(v26));
  v24 = 0;
  v21[0] = 0;
  v20 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_1559182127783aab3882fe828952d989_Traceguids);
  First = FveDatasetGetFirst(*((_QWORD *)this + 146), 4, 7, &v22);
  v5 = FromNtStatus(First);
  v7 = v5;
  if ( v5 == -2147023728 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_1559182127783aab3882fe828952d989_Traceguids);
    goto LABEL_37;
  }
  if ( v5 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v9 = 22;
LABEL_41:
      WPP_SF_d(v8[2], v9, &WPP_1559182127783aab3882fe828952d989_Traceguids, (unsigned int)v5);
      goto LABEL_42;
    }
    goto LABEL_43;
  }
  v10 = BcdOpenSystemStore(&v23, v6);
  v5 = FromNtStatus(v10);
  v7 = v5;
  if ( v5 >= 0 )
  {
    v11 = BcdOpenObject(v23, &GUID_CURRENT_BOOT_ENTRY, &v24);
    v5 = FromNtStatus(v11);
    v7 = v5;
    if ( v5 < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 24;
        goto LABEL_41;
      }
      goto LABEL_43;
    }
    v12 = BcdQueryObject(v24, 0, 0, &v25);
    v5 = FromNtStatus(v12);
    v7 = v5;
    if ( v5 < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 25;
        goto LABEL_41;
      }
      goto LABEL_43;
    }
    v13 = FveDatumValidationInfoDataEntry(0, &v25, 16, v26);
    v5 = FromNtStatus(v13);
    v7 = v5;
    if ( v5 < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 26;
        goto LABEL_41;
      }
      goto LABEL_43;
    }
    LODWORD(v26[0]) = 131076;
    v14 = FveDatumCheckEntryInValidationInfo(v22, v26, v21, &v20);
    v5 = FromNtStatus(v14);
    v7 = v5;
    if ( v5 < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 27;
        goto LABEL_41;
      }
      goto LABEL_43;
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v16 = v20;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF__guid_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v15, &v25, v21[0] != 0, v20 != 0, 1);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !v16 )
      goto LABEL_43;
LABEL_37:
    v17 = FveDatumValidationInfoCreate(0, 0, 0, a2);
    v5 = FromNtStatus(v17);
    v7 = v5;
    if ( v5 >= 0 )
    {
LABEL_42:
      v8 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_43;
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v9 = 30;
      goto LABEL_41;
    }
    goto LABEL_43;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v9 = 23;
    goto LABEL_41;
  }
LABEL_43:
  if ( v22 )
  {
    FveDatumFree(v22);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v18 = v23;
  if ( v23 )
  {
    if ( v24 )
    {
      BcdCloseObject(v24);
      v18 = v23;
    }
    BcdCloseStore(v18, v6);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 )
    WPP_SF_d(v8[2], 31, &WPP_1559182127783aab3882fe828952d989_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18009c550  mov     [rsp-8+arg_10], rbx
0x18009c555  push    rbp
0x18009c556  push    rdi
0x18009c557  push    r12
0x18009c559  push    r13
0x18009c55b  push    r14
0x18009c55d  lea     rbp, [rsp-37h]
0x18009c562  sub     rsp, 0A0h
0x18009c569  mov     rax, cs:__security_cookie
0x18009c570  xor     rax, rsp
0x18009c573  mov     [rbp+57h+var_28], rax
0x18009c577  xorps   xmm0, xmm0
0x18009c57a  mov     [rbp+57h+var_78], 0
0x18009c582  xor     eax, eax
0x18009c584  mov     [rbp+57h+var_70], 0
0x18009c58c  movups  [rbp+57h+var_60], xmm0
0x18009c590  mov     [rbp+57h+var_30], rax
0x18009c594  mov     r14, rdx
0x18009c597  movups  [rbp+57h+var_50], xmm0
0x18009c59b  mov     rbx, rcx
0x18009c59e  mov     [rbp+57h+var_68], 0
0x18009c5a6  movups  [rbp+57h+var_40], xmm0
0x18009c5aa  mov     [rbp+57h+var_7F], 0
0x18009c5ae  mov     [rbp+57h+var_80], 0
0x18009c5b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c5b9  lea     r12, WPP_GLOBAL_Control
0x18009c5c0  lea     rdi, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009c5c7  cmp     rcx, r12
0x18009c5ca  jz      short loc_18009C5E1
0x18009c5cc  test    byte ptr [rcx+1Ch], 20h
0x18009c5d0  jz      short loc_18009C5E1
0x18009c5d2  mov     rcx, [rcx+10h]
0x18009c5d6  lea     edx, [rax+15h]
0x18009c5d9  mov     r8, rdi
0x18009c5dc  call    WPP_SF_
0x18009c5e1  mov     rcx, [rbx+490h]
0x18009c5e8  lea     r9, [rbp+57h+var_78]
0x18009c5ec  mov     edx, 4
0x18009c5f1  lea     r8d, [rdx+3]
0x18009c5f5  call    FveDatasetGetFirst
0x18009c5fa  mov     ecx, eax; int
0x18009c5fc  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009c601  mov     ebx, eax
0x18009c603  mov     r13d, 2
0x18009c609  cmp     eax, 80070490h
0x18009c60e  jz      loc_18009C803
0x18009c614  test    eax, eax
0x18009c616  jns     short loc_18009C63B
0x18009c618  mov     r10, cs:WPP_GLOBAL_Control
0x18009c61f  cmp     r10, r12
0x18009c622  jz      loc_18009C86F
0x18009c628  test    [r10+1Ch], r13b
0x18009c62c  jz      loc_18009C86F
0x18009c632  lea     edx, [r13+14h]
0x18009c636  jmp     loc_18009C859
0x18009c63b  lea     rcx, [rbp+57h+var_70]
0x18009c63f  call    cs:__imp_BcdOpenSystemStore
0x18009c646  nop     dword ptr [rax+rax+00h]
0x18009c64b  mov     ecx, eax; int
0x18009c64d  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009c652  mov     ebx, eax
0x18009c654  test    eax, eax
0x18009c656  jns     short loc_18009C67C
0x18009c658  mov     r10, cs:WPP_GLOBAL_Control
0x18009c65f  cmp     r10, r12
0x18009c662  jz      loc_18009C86F
0x18009c668  test    [r10+1Ch], r13b
0x18009c66c  jz      loc_18009C86F
0x18009c672  mov     edx, 17h
0x18009c677  jmp     loc_18009C859
0x18009c67c  mov     rcx, [rbp+57h+var_70]
0x18009c680  lea     r8, [rbp+57h+var_68]
0x18009c684  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x18009c68b  call    cs:__imp_BcdOpenObject
0x18009c692  nop     dword ptr [rax+rax+00h]
0x18009c697  mov     ecx, eax; int
0x18009c699  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009c69e  mov     ebx, eax
0x18009c6a0  test    eax, eax
0x18009c6a2  jns     short loc_18009C6C8
0x18009c6a4  mov     r10, cs:WPP_GLOBAL_Control
0x18009c6ab  cmp     r10, r12
0x18009c6ae  jz      loc_18009C86F
0x18009c6b4  test    [r10+1Ch], r13b
0x18009c6b8  jz      loc_18009C86F
0x18009c6be  mov     edx, 18h
0x18009c6c3  jmp     loc_18009C859
0x18009c6c8  mov     rcx, [rbp+57h+var_68]
0x18009c6cc  lea     r9, [rbp+57h+var_60]
0x18009c6d0  xor     r8d, r8d
0x18009c6d3  xor     edx, edx
0x18009c6d5  call    cs:__imp_BcdQueryObject
0x18009c6dc  nop     dword ptr [rax+rax+00h]
0x18009c6e1  mov     ecx, eax; int
0x18009c6e3  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009c6e8  mov     ebx, eax
0x18009c6ea  test    eax, eax
0x18009c6ec  jns     short loc_18009C712
0x18009c6ee  mov     r10, cs:WPP_GLOBAL_Control
0x18009c6f5  cmp     r10, r12
0x18009c6f8  jz      loc_18009C86F
0x18009c6fe  test    [r10+1Ch], r13b
0x18009c702  jz      loc_18009C86F
0x18009c708  mov     edx, 19h
0x18009c70d  jmp     loc_18009C859
0x18009c712  lea     r9, [rbp+57h+var_50]
0x18009c716  mov     r8d, 10h
0x18009c71c  lea     rdx, [rbp+57h+var_60]
0x18009c720  xor     ecx, ecx
0x18009c722  call    FveDatumValidationInfoDataEntry
0x18009c727  mov     ecx, eax; int
0x18009c729  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009c72e  mov     ebx, eax
0x18009c730  test    eax, eax
0x18009c732  jns     short loc_18009C758
0x18009c734  mov     r10, cs:WPP_GLOBAL_Control
0x18009c73b  cmp     r10, r12
0x18009c73e  jz      loc_18009C86F
0x18009c744  test    [r10+1Ch], r13b
0x18009c748  jz      loc_18009C86F
0x18009c74e  mov     edx, 1Ah
0x18009c753  jmp     loc_18009C859
0x18009c758  mov     rcx, [rbp+57h+var_78]
0x18009c75c  lea     r9, [rbp+57h+var_80]
0x18009c760  lea     r8, [rbp+57h+var_7F]
0x18009c764  mov     dword ptr [rbp+57h+var_50], 20004h
0x18009c76b  lea     rdx, [rbp+57h+var_50]
0x18009c76f  call    FveDatumCheckEntryInValidationInfo
0x18009c774  mov     ecx, eax; int
0x18009c776  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009c77b  mov     ebx, eax
0x18009c77d  test    eax, eax
0x18009c77f  jns     short loc_18009C7A5
0x18009c781  mov     r10, cs:WPP_GLOBAL_Control
0x18009c788  cmp     r10, r12
0x18009c78b  jz      loc_18009C86F
0x18009c791  test    [r10+1Ch], r13b
0x18009c795  jz      loc_18009C86F
0x18009c79b  mov     edx, 1Bh
0x18009c7a0  jmp     loc_18009C859
0x18009c7a5  mov     r10, cs:WPP_GLOBAL_Control
0x18009c7ac  mov     dil, [rbp+57h+var_80]
0x18009c7b0  cmp     r10, r12
0x18009c7b3  jz      short loc_18009C7F5
0x18009c7b5  test    byte ptr [r10+1Ch], 8
0x18009c7ba  jz      short loc_18009C7F5
0x18009c7bc  xor     ecx, ecx
0x18009c7be  mov     [rsp+0C0h+var_90], 1
0x18009c7c6  test    dil, dil
0x18009c7c9  lea     r9, [rbp+57h+var_60]
0x18009c7cd  mov     edx, 1Ch
0x18009c7d2  setnz   cl
0x18009c7d5  xor     eax, eax
0x18009c7d7  cmp     [rbp+57h+var_7F], al
0x18009c7da  mov     [rsp+0C0h+var_98], ecx
0x18009c7de  mov     rcx, [r10+10h]
0x18009c7e2  setnz   al
0x18009c7e5  mov     [rsp+0C0h+var_A0], eax
0x18009c7e9  call    WPP_SF__guid_ddd
0x18009c7ee  mov     r10, cs:WPP_GLOBAL_Control
0x18009c7f5  test    dil, dil
0x18009c7f8  jz      short loc_18009C86F
0x18009c7fa  lea     rdi, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009c801  jmp     short loc_18009C826
0x18009c803  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c80a  cmp     rcx, r12
0x18009c80d  jz      short loc_18009C826
0x18009c80f  test    byte ptr [rcx+1Ch], 8
0x18009c813  jz      short loc_18009C826
0x18009c815  mov     rcx, [rcx+10h]
0x18009c819  mov     edx, 1Dh
0x18009c81e  mov     r8, rdi
0x18009c821  call    WPP_SF_
0x18009c826  xor     r8d, r8d
0x18009c829  xor     edx, edx
0x18009c82b  mov     r9, r14
0x18009c82e  xor     ecx, ecx
0x18009c830  call    FveDatumValidationInfoCreate
0x18009c835  mov     ecx, eax; int
0x18009c837  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009c83c  mov     ebx, eax
0x18009c83e  test    eax, eax
0x18009c840  jns     short loc_18009C868
0x18009c842  mov     r10, cs:WPP_GLOBAL_Control
0x18009c849  cmp     r10, r12
0x18009c84c  jz      short loc_18009C86F
0x18009c84e  test    [r10+1Ch], r13b
0x18009c852  jz      short loc_18009C86F
0x18009c854  mov     edx, 1Eh
0x18009c859  mov     rcx, [r10+10h]
0x18009c85d  mov     r9d, eax
0x18009c860  mov     r8, rdi
0x18009c863  call    WPP_SF_d
0x18009c868  mov     r10, cs:WPP_GLOBAL_Control
0x18009c86f  cmp     [rbp+57h+var_78], 0
0x18009c874  jz      short loc_18009C886
0x18009c876  mov     rcx, [rbp+57h+var_78]
0x18009c87a  call    FveDatumFree
0x18009c87f  mov     r10, cs:WPP_GLOBAL_Control
0x18009c886  mov     rcx, [rbp+57h+var_70]
0x18009c88a  test    rcx, rcx
0x18009c88d  jz      short loc_18009C8BE
0x18009c88f  mov     rax, [rbp+57h+var_68]
0x18009c893  test    rax, rax
0x18009c896  jz      short loc_18009C8AB
0x18009c898  mov     rcx, rax
0x18009c89b  call    cs:__imp_BcdCloseObject
0x18009c8a2  nop     dword ptr [rax+rax+00h]
0x18009c8a7  mov     rcx, [rbp+57h+var_70]
0x18009c8ab  call    cs:__imp_BcdCloseStore
0x18009c8b2  nop     dword ptr [rax+rax+00h]
0x18009c8b7  mov     r10, cs:WPP_GLOBAL_Control
0x18009c8be  cmp     r10, r12
0x18009c8c1  jz      short loc_18009C8E2
0x18009c8c3  test    byte ptr [r10+1Ch], 20h
0x18009c8c8  jz      short loc_18009C8E2
0x18009c8ca  mov     rcx, [r10+10h]
0x18009c8ce  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009c8d5  mov     edx, 1Fh
0x18009c8da  mov     r9d, ebx
0x18009c8dd  call    WPP_SF_d
0x18009c8e2  mov     eax, ebx
0x18009c8e4  mov     rcx, [rbp+57h+var_28]
0x18009c8e8  xor     rcx, rsp; StackCookie
0x18009c8eb  call    __security_check_cookie
0x18009c8f0  mov     rbx, [rsp+0C0h+arg_10]
0x18009c8f8  add     rsp, 0A0h
0x18009c8ff  pop     r14
0x18009c901  pop     r13
0x18009c903  pop     r12
0x18009c905  pop     rdi
0x18009c906  pop     rbp
0x18009c907  retn
```
