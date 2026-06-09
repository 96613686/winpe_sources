# KerbUnpackErrorData(KERB_ERROR *,KERB_EXT_ERROR * *)

- ea: `0x180014380`
- end: `0x180014b30`
- name: `?KerbUnpackErrorData@@YAJPEAUKERB_ERROR@@PEAPEAUKERB_EXT_ERROR@@@Z`
- size: `1968`
- prototype: `__int64 __fastcall(struct KERB_ERROR *, struct KERB_EXT_ERROR **)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180019678`
- `0x180042a40`

## callees

- `0x1800069a0`
- `0x18000efd0`
- `0x180011150`
- `0x1800113f0`
- `0x180014380`
- `0x18006b9c8`
- `0x18006ccec`
- `0x18006d73c`
- `0x180077804`
- `0x1800dffbc`

## import_xrefs

- `MSASN1!ASN1_CreateModule` at `0x18001444f`
- `MSASN1!ASN1_CreateModule` at `0x18001457c`
- `MSASN1!ASN1_CreateModule` at `0x18001444f`
- `MSASN1!ASN1_CreateModule` at `0x18001457c`
- `MSASN1!ASN1_CloseDecoder` at `0x1800144cb`
- `MSASN1!ASN1_CloseDecoder` at `0x1800145f0`
- `MSASN1!ASN1_CloseDecoder` at `0x1800144cb`
- `MSASN1!ASN1_CloseDecoder` at `0x1800145f0`
- `MSASN1!ASN1_CreateDecoder` at `0x18001446e`
- `MSASN1!ASN1_CreateDecoder` at `0x18001459b`
- `MSASN1!ASN1_CreateDecoder` at `0x18001446e`
- `MSASN1!ASN1_CreateDecoder` at `0x18001459b`
- `MSASN1!ASN1_Decode` at `0x1800144a0`
- `MSASN1!ASN1_Decode` at `0x1800145cf`
- `MSASN1!ASN1_Decode` at `0x1800144a0`
- `MSASN1!ASN1_Decode` at `0x1800145cf`

## pseudocode

```c
__int64 __fastcall KerbUnpackErrorData(struct KERB_ERROR *a1, struct KERB_EXT_ERROR **a2)
{
  bool v4; // zf
  __int64 v5; // rsi
  unsigned int v6; // r14d
  int v7; // r12d
  unsigned int v8; // ebx
  __int64 v9; // r13
  __int64 v10; // rax
  unsigned int v11; // eax
  int v12; // eax
  unsigned int v13; // r12d
  PVOID *v14; // r10
  int v15; // r12d
  int v16; // r12d
  __int64 Module; // rax
  unsigned int v18; // eax
  int v19; // eax
  unsigned int v20; // r12d
  PVOID *v21; // r10
  __int64 v23; // r12
  struct TYPED_DATA_s *v24; // rax
  PVOID *v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // [rsp+58h] [rbp-9h] BYREF
  __int64 v28; // [rsp+60h] [rbp-1h] BYREF
  __int64 v29; // [rsp+68h] [rbp+7h]
  unsigned int v30; // [rsp+C8h] [rbp+67h] BYREF
  __int64 v31; // [rsp+D0h] [rbp+6Fh] BYREF
  struct TYPED_DATA_s *v32; // [rsp+D8h] [rbp+77h] BYREF
  __int64 v33; // [rsp+E0h] [rbp+7Fh] BYREF

  *a2 = 0;
  v4 = (*(_BYTE *)a1 & 4) == 0;
  v5 = 0;
  v32 = 0;
  v6 = 0;
  v33 = 0;
  v28 = 0;
  v30 = 0;
  if ( v4 )
    return 60;
  v7 = *((_DWORD *)a1 + 30);
  v8 = 60;
  v27 = 0;
  if ( !v7 || (v9 = *((_QWORD *)a1 + 16)) == 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_12:
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
      {
        WPP_SF_(v14[2], 10, WPP_e952c4c2f30a34722b906e2d71434858_Traceguids);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_15:
      v16 = *((_DWORD *)a1 + 30);
      v31 = 0;
      if ( !v16 || (v29 = *((_QWORD *)a1 + 16)) == 0 )
      {
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
          WPP_SF_(v14[2], 38, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids);
        goto LABEL_25;
      }
      if ( fKRB5ModuleStarted )
      {
        Module = KRB5_Module;
      }
      else
      {
        fKRB5ModuleStarted = 1;
        Module = ASN1_CreateModule(
                   0x10000,
                   1024,
                   4096,
                   81,
                   off_1800F62D0,
                   off_1800F6040,
                   off_1800F6560,
                   qword_1800FE8B0,
                   895644267);
        KRB5_Module = Module;
      }
      v18 = ASN1_CreateDecoder(Module, &v31, 0, 0, 0);
      if ( v18 )
      {
        v25 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v18);
            v25 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
            WPP_SF_D(v25[2], 39, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, 60);
        }
        goto LABEL_25;
      }
      v33 = 0;
      v19 = ASN1_Decode(v31, &v33, 30, 8, v29, v16);
      v20 = v19;
      if ( v19 >= 0 )
      {
        v21 = (PVOID *)WPP_GLOBAL_Control;
LABEL_22:
        if ( v31 )
        {
          ASN1_CloseDecoder();
          v21 = (PVOID *)WPP_GLOBAL_Control;
        }
        v8 = v6;
        if ( v6 )
          goto LABEL_25;
        if ( *(char *)v33 >= 0 || *(_DWORD *)(v33 + 4) != 3 || *(_DWORD *)(v33 + 8) < 0xCu )
          goto LABEL_102;
        v26 = KerbPackData(*(_QWORD *)(v33 + 16), 0x1Fu, &v30, &v28);
        v5 = v28;
        v8 = v26;
        if ( v26 )
          goto LABEL_25;
        v6 = v30;
        v23 = v28;
        goto LABEL_97;
      }
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          &WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
          (unsigned int)v19);
        v21 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v20 != -1009 )
      {
        if ( v20 == -1011 )
        {
LABEL_51:
          v6 = 60;
LABEL_52:
          v33 = 0;
          goto LABEL_22;
        }
        if ( v20 != -1002 )
        {
          if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
          {
            WPP_SF_d(v21[2], 42, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v20);
            v21 = (PVOID *)WPP_GLOBAL_Control;
          }
          goto LABEL_51;
        }
      }
      if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 )
      {
        WPP_SF_d(v21[2], 41, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, 30);
        v21 = (PVOID *)WPP_GLOBAL_Control;
      }
      v6 = -2147483647;
      goto LABEL_52;
    }
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids);
LABEL_35:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  if ( fKRB5ModuleStarted )
  {
    v10 = KRB5_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    v10 = ASN1_CreateModule(
            0x10000,
            1024,
            4096,
            81,
            off_1800F62D0,
            off_1800F6040,
            off_1800F6560,
            qword_1800FE8B0,
            895644267);
    KRB5_Module = v10;
  }
  v11 = ASN1_CreateDecoder(v10, &v27, 0, 0, 0);
  if ( v11 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_12;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v11);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 1) == 0 )
      goto LABEL_12;
    WPP_SF_D(v14[2], 39, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, 60);
    goto LABEL_35;
  }
  v32 = 0;
  v12 = ASN1_Decode(v27, &v32, 32, 8, v9, v7);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    v15 = 0;
    goto LABEL_9;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      &WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
      (unsigned int)v12);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 == -1009 )
    goto LABEL_44;
  if ( v13 != -1011 )
  {
    if ( v13 == -1002 )
    {
LABEL_44:
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 )
      {
        WPP_SF_d(v14[2], 41, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, 32);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      v15 = -2147483647;
      goto LABEL_55;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
    {
      WPP_SF_d(v14[2], 42, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v13);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v15 = 60;
LABEL_55:
  v32 = 0;
LABEL_9:
  if ( v27 )
  {
    ASN1_CloseDecoder();
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 )
    goto LABEL_12;
  v23 = 0;
  v8 = 0;
  v24 = KerbTypedDataListFind(v32, -129);
  if ( v24 )
  {
    v6 = *((_DWORD *)v24 + 4);
    v23 = *((_QWORD *)v24 + 3);
  }
  if ( *((_DWORD *)a1 + 13) != 7 || !KerbTypedDataListFind(v32, -128) )
    goto LABEL_98;
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
    WPP_SF_(v21[2], 11, WPP_e952c4c2f30a34722b906e2d71434858_Traceguids);
  *((_DWORD *)a1 + 13) = 27;
LABEL_97:
  v21 = (PVOID *)WPP_GLOBAL_Control;
LABEL_98:
  if ( !v23 || !v6 )
  {
LABEL_102:
    if ( *a2 && v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
      WPP_SF_DDD(
        v21[2],
        12,
        WPP_e952c4c2f30a34722b906e2d71434858_Traceguids,
        *((unsigned int *)a1 + 13),
        *((_DWORD *)*a2 + 1),
        *(_DWORD *)*a2);
    goto LABEL_25;
  }
  v8 = KerbUnpackData(v23, v6, 31, a2);
  if ( !v8 )
  {
    v21 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_102;
  }
LABEL_25:
  if ( v33 )
    KerbFreeData(30);
  if ( v32 )
    KerbFreeData(32);
  if ( v5 )
    KerbFree(v5);
  return v8;
}

```

## disassembly

```asm
0x180014380  mov     r11, rsp
0x180014383  push    rbp
0x180014384  push    rbx
0x180014385  push    rsi
0x180014386  push    rdi
0x180014387  push    r14
0x180014389  push    r15
0x18001438b  lea     rbp, [r11-5Fh]
0x18001438f  sub     rsp, 88h
0x180014396  xor     eax, eax
0x180014398  mov     r15, rdx
0x18001439b  mov     [rdx], rax
0x18001439e  mov     rdi, rcx
0x1800143a1  test    byte ptr [rcx], 4
0x1800143a4  mov     esi, eax
0x1800143a6  mov     [rbp+57h+arg_10], rax
0x1800143aa  mov     r14d, eax
0x1800143ad  mov     [rbp+57h+arg_18], rax
0x1800143b1  mov     [rbp+57h+var_58], rax
0x1800143b5  mov     [rbp+57h+arg_0], eax
0x1800143b8  jz      loc_1800146BC
0x1800143be  mov     [r11-38h], r12
0x1800143c2  lea     rdx, off_1800F6560
0x1800143c9  mov     r12d, [rcx+78h]
0x1800143cd  lea     r8, off_1800F6040
0x1800143d4  mov     [r11-40h], r13
0x1800143d8  mov     ebx, 3Ch ; '<'
0x1800143dd  mov     [rbp+57h+var_60], rax
0x1800143e1  lea     rcx, qword_1800FE8B0
0x1800143e8  lea     r9, off_1800F62D0
0x1800143ef  test    r12d, r12d
0x1800143f2  jz      loc_18001464B
0x1800143f8  mov     r13, [rdi+80h]
0x1800143ff  test    r13, r13
0x180014402  jz      loc_18001464B
0x180014408  cmp     cs:?fKRB5ModuleStarted@@3HA, eax; int fKRB5ModuleStarted
0x18001440e  jnz     loc_180014765
0x180014414  mov     dword ptr [rsp+40h], 3562726Bh
0x18001441c  mov     [r11-80h], rcx
0x180014420  mov     ecx, 10000h
0x180014425  mov     [rsp+0B0h+var_80], rdx
0x18001442a  mov     edx, 400h
0x18001442f  mov     [rsp+0B0h+var_88], r8
0x180014434  mov     r8d, 1000h
0x18001443a  mov     [rsp+0B0h+var_90], r9
0x18001443f  mov     r9d, 51h ; 'Q'
0x180014445  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x18001444f  call    cs:__imp_ASN1_CreateModule
0x180014455  mov     cs:KRB5_Module, rax
0x18001445c  xor     r9d, r9d
0x18001445f  mov     [rsp+0B0h+var_90], rsi
0x180014464  xor     r8d, r8d
0x180014467  lea     rdx, [rbp+57h+var_60]
0x18001446b  mov     rcx, rax
0x18001446e  call    cs:__imp_ASN1_CreateDecoder
0x180014474  test    eax, eax
0x180014476  jnz     loc_1800147DE
0x18001447c  mov     rcx, [rbp+57h+var_60]
0x180014480  lea     rdx, [rbp+57h+arg_10]
0x180014484  xor     eax, eax
0x180014486  mov     dword ptr [rsp+0B0h+var_88], r12d
0x18001448b  mov     r9d, 8
0x180014491  mov     [rbp+57h+arg_10], rax
0x180014495  mov     r8d, 20h ; ' '
0x18001449b  mov     [rsp+0B0h+var_90], r13
0x1800144a0  call    cs:__imp_ASN1_Decode
0x1800144a6  lea     r13, WPP_GLOBAL_Control
0x1800144ad  mov     r12d, eax
0x1800144b0  test    eax, eax
0x1800144b2  js      loc_1800146D1
0x1800144b8  mov     r10, cs:WPP_GLOBAL_Control
0x1800144bf  mov     r12d, esi
0x1800144c2  mov     rcx, [rbp+57h+var_60]
0x1800144c6  test    rcx, rcx
0x1800144c9  jz      short loc_1800144D8
0x1800144cb  call    cs:__imp_ASN1_CloseDecoder
0x1800144d1  mov     r10, cs:WPP_GLOBAL_Control
0x1800144d8  test    r12d, r12d
0x1800144db  jz      loc_1800148BB
0x1800144e1  lea     r9, off_1800F62D0
0x1800144e8  xor     eax, eax
0x1800144ea  lea     r8, off_1800F6040
0x1800144f1  lea     rdx, off_1800F6560
0x1800144f8  lea     rcx, qword_1800FE8B0
0x1800144ff  cmp     r10, r13
0x180014502  jz      short loc_18001450F
0x180014504  test    byte ptr [r10+1Ch], 2
0x180014509  jnz     loc_180014929
0x18001450f  mov     r12d, [rdi+78h]
0x180014513  mov     [rbp+57h+arg_8], rax
0x180014517  test    r12d, r12d
0x18001451a  jz      loc_18001468E
0x180014520  mov     rax, [rdi+80h]
0x180014527  mov     [rbp+57h+var_50], rax
0x18001452b  test    rax, rax
0x18001452e  jz      loc_18001468E
0x180014534  cmp     cs:?fKRB5ModuleStarted@@3HA, esi; int fKRB5ModuleStarted
0x18001453a  jnz     loc_180014771
0x180014540  mov     dword ptr [rsp+40h], 3562726Bh
0x180014548  mov     qword ptr [rsp+0B0h+var_78], rcx
0x18001454d  mov     ecx, 10000h
0x180014552  mov     [rsp+0B0h+var_80], rdx
0x180014557  mov     edx, 400h
0x18001455c  mov     [rsp+0B0h+var_88], r8
0x180014561  mov     r8d, 1000h
0x180014567  mov     [rsp+0B0h+var_90], r9
0x18001456c  mov     r9d, 51h ; 'Q'
0x180014572  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x18001457c  call    cs:__imp_ASN1_CreateModule
0x180014582  mov     cs:KRB5_Module, rax
0x180014589  xor     r9d, r9d
0x18001458c  mov     [rsp+0B0h+var_90], rsi
0x180014591  xor     r8d, r8d
0x180014594  lea     rdx, [rbp+57h+arg_8]
0x180014598  mov     rcx, rax
0x18001459b  call    cs:__imp_ASN1_CreateDecoder
0x1800145a1  test    eax, eax
0x1800145a3  jnz     loc_180014968
0x1800145a9  mov     rax, [rbp+57h+var_50]
0x1800145ad  lea     rdx, [rbp+57h+arg_18]
0x1800145b1  mov     rcx, [rbp+57h+arg_8]
0x1800145b5  mov     r9d, 8
0x1800145bb  mov     dword ptr [rsp+0B0h+var_88], r12d
0x1800145c0  mov     r8d, 1Eh
0x1800145c6  mov     [rsp+0B0h+var_90], rax
0x1800145cb  mov     [rbp+57h+arg_18], rsi
0x1800145cf  call    cs:__imp_ASN1_Decode
0x1800145d5  mov     r12d, eax
0x1800145d8  test    eax, eax
0x1800145da  js      loc_180014702
0x1800145e0  mov     r10, cs:WPP_GLOBAL_Control
0x1800145e7  mov     rcx, [rbp+57h+arg_8]
0x1800145eb  test    rcx, rcx
0x1800145ee  jz      short loc_1800145FD
0x1800145f0  call    cs:__imp_ASN1_CloseDecoder
0x1800145f6  mov     r10, cs:WPP_GLOBAL_Control
0x1800145fd  mov     ebx, r14d
0x180014600  test    r14d, r14d
0x180014603  jz      loc_180014A41
0x180014609  mov     rax, [rbp+57h+arg_18]
0x18001460d  mov     r13, [rsp+0B0h+var_38]
0x180014612  mov     r12, [rsp+80h]
0x18001461a  test    rax, rax
0x18001461d  jnz     loc_180014B02
0x180014623  mov     rdx, [rbp+57h+arg_10]
0x180014627  test    rdx, rdx
0x18001462a  jnz     loc_180014B14
0x180014630  test    rsi, rsi
0x180014633  jnz     loc_180014B23
0x180014639  mov     eax, ebx
0x18001463b  add     rsp, 88h
0x180014642  pop     r15
0x180014644  pop     r14
0x180014646  pop     rdi
0x180014647  pop     rsi
0x180014648  pop     rbx
0x180014649  pop     rbp
0x18001464a  retn
0x18001464b  mov     r10, cs:WPP_GLOBAL_Control
0x180014652  lea     r13, WPP_GLOBAL_Control
0x180014659  cmp     r10, r13
0x18001465c  jz      loc_18001450F
0x180014662  test    byte ptr [r10+1Ch], 1
0x180014667  jz      loc_1800144FF
0x18001466d  mov     rcx, [r10+10h]
0x180014671  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180014678  mov     edx, 26h ; '&'
0x18001467d  call    WPP_SF_
0x180014682  mov     r10, cs:WPP_GLOBAL_Control
0x180014689  jmp     loc_1800144E1
0x18001468e  cmp     r10, r13
0x180014691  jz      loc_180014609
0x180014697  test    byte ptr [r10+1Ch], 1
0x18001469c  jz      loc_180014609
0x1800146a2  mov     rcx, [r10+10h]
0x1800146a6  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x1800146ad  mov     edx, 26h ; '&'
0x1800146b2  call    WPP_SF_
0x1800146b7  jmp     loc_180014609
0x1800146bc  mov     eax, 3Ch ; '<'
0x1800146c1  add     rsp, 88h
0x1800146c8  pop     r15
0x1800146ca  pop     r14
0x1800146cc  pop     rdi
0x1800146cd  pop     rsi
0x1800146ce  pop     rbx
0x1800146cf  pop     rbp
0x1800146d0  retn
0x1800146d1  mov     r10, cs:WPP_GLOBAL_Control
0x1800146d8  cmp     r10, r13
0x1800146db  jz      short loc_1800146E8
0x1800146dd  test    byte ptr [r10+1Ch], 4
0x1800146e2  jnz     loc_180014820
0x1800146e8  cmp     r12d, 0FFFFFC0Fh
0x1800146ef  jnz     short loc_18001473B
0x1800146f1  cmp     r10, r13
0x1800146f4  jnz     loc_180014889
0x1800146fa  mov     r12d, 80000001h
0x180014700  jmp     short loc_18001474B
0x180014702  mov     r10, cs:WPP_GLOBAL_Control
0x180014709  cmp     r10, r13
0x18001470c  jz      short loc_180014719
0x18001470e  test    byte ptr [r10+1Ch], 4
0x180014713  jnz     loc_1800149A6
0x180014719  cmp     r12d, 0FFFFFC0Fh
0x180014720  jz      short loc_180014754
0x180014722  cmp     r12d, 0FFFFFC0Dh
0x180014729  jnz     loc_1800149CA
0x18001472f  mov     r14d, ebx
0x180014732  mov     [rbp+57h+arg_18], rsi
0x180014736  jmp     loc_1800145E7
0x18001473b  cmp     r12d, 0FFFFFC0Dh
0x180014742  jnz     loc_180014844
0x180014748  mov     r12d, ebx
0x18001474b  mov     [rbp+57h+arg_10], rsi
0x18001474f  jmp     loc_1800144C2
0x180014754  cmp     r10, r13
0x180014757  jnz     loc_180014A0F
0x18001475d  mov     r14d, 80000001h
0x180014763  jmp     short loc_180014732
0x180014765  mov     rax, cs:KRB5_Module
0x18001476c  jmp     loc_18001445C
0x180014771  mov     rax, cs:KRB5_Module
0x180014778  jmp     loc_180014589
0x18001477d  cmp     r10, r13
0x180014780  jz      loc_1800144E1
0x180014786  test    byte ptr [r10+1Ch], 1
0x18001478b  jz      loc_1800144E1
0x180014791  mov     rcx, [r10+10h]
0x180014795  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18001479c  mov     edx, 27h ; '''
0x1800147a1  mov     r9d, ebx
0x1800147a4  call    WPP_SF_D
0x1800147a9  jmp     loc_180014682
0x1800147ae  cmp     rcx, r13
0x1800147b1  jz      loc_180014609
0x1800147b7  test    byte ptr [rcx+1Ch], 1
0x1800147bb  jz      loc_180014609
0x1800147c1  mov     rcx, [rcx+10h]
0x1800147c5  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x1800147cc  mov     edx, 27h ; '''
0x1800147d1  mov     r9d, ebx
0x1800147d4  call    WPP_SF_D
0x1800147d9  jmp     loc_180014609
0x1800147de  mov     r10, cs:WPP_GLOBAL_Control
0x1800147e5  lea     r13, WPP_GLOBAL_Control
0x1800147ec  cmp     r10, r13
0x1800147ef  jz      loc_1800144E1
0x1800147f5  test    byte ptr [r10+1Ch], 1
0x1800147fa  jz      short loc_18001477D
0x1800147fc  mov     rcx, [r10+10h]
0x180014800  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180014807  mov     edx, 24h ; '$'
0x18001480c  mov     r9d, eax
0x18001480f  call    WPP_SF_D
0x180014814  mov     r10, cs:WPP_GLOBAL_Control
0x18001481b  jmp     loc_18001477D
0x180014820  mov     rcx, [r10+10h]
0x180014824  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18001482b  mov     edx, 28h ; '('
0x180014830  mov     r9d, r12d
0x180014833  call    WPP_SF_D
0x180014838  mov     r10, cs:WPP_GLOBAL_Control
0x18001483f  jmp     loc_1800146E8
0x180014844  cmp     r12d, 0FFFFFC16h
0x18001484b  jz      loc_1800146F1
0x180014851  cmp     r10, r13
0x180014854  jz      loc_180014748
0x18001485a  test    byte ptr [r10+1Ch], 1
0x18001485f  jz      loc_180014748
0x180014865  mov     rcx, [r10+10h]
0x180014869  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180014870  mov     edx, 2Ah ; '*'
0x180014875  mov     r9d, r12d
0x180014878  call    WPP_SF_d
0x18001487d  mov     r10, cs:WPP_GLOBAL_Control
0x180014884  jmp     loc_180014748
0x180014889  test    byte ptr [r10+1Ch], 4
0x18001488e  jz      loc_1800146FA
0x180014894  mov     rcx, [r10+10h]
0x180014898  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18001489f  mov     edx, 29h ; ')'
0x1800148a4  mov     r9d, 20h ; ' '
0x1800148aa  call    WPP_SF_d
0x1800148af  mov     r10, cs:WPP_GLOBAL_Control
0x1800148b6  jmp     loc_1800146FA
0x1800148bb  mov     rcx, [rbp+57h+arg_10]; struct TYPED_DATA_s *
0x1800148bf  mov     edx, 0FFFFFF7Fh; int
0x1800148c4  xor     r12d, r12d
0x1800148c7  xor     ebx, ebx
0x1800148c9  call    ?KerbTypedDataListFind@@YAPEAUTYPED_DATA_s@@PEAU1@J@Z; KerbTypedDataListFind(TYPED_DATA_s *,long)
0x1800148ce  test    rax, rax
0x1800148d1  jz      short loc_1800148DB
0x1800148d3  mov     r14d, [rax+10h]
0x1800148d7  mov     r12, [rax+18h]
0x1800148db  cmp     dword ptr [rdi+34h], 7
0x1800148df  jnz     loc_180014A88
0x1800148e5  mov     rcx, [rbp+57h+arg_10]; struct TYPED_DATA_s *
0x1800148e9  mov     edx, 0FFFFFF80h; int
0x1800148ee  call    ?KerbTypedDataListFind@@YAPEAUTYPED_DATA_s@@PEAU1@J@Z; KerbTypedDataListFind(TYPED_DATA_s *,long)
  ... truncated ...
```
