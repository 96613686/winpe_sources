# InstallFTGroupKeyWrapper(_GUID *,_VELAN *,_NWF_KEY_CONTEXT *,DOT11_MAC_STATE_ENTRY *,NWF_RSNA_FT_GTK_SUB_ELEMENT *,NWF_RSNA_FT_IGTK_SUB_ELEMENT *,NWF_RSNA_FT_BIGTK_SUB_ELEMENT *)

- ea: `0x14004d8fc`
- end: `0x14004ddd8`
- name: `?InstallFTGroupKeyWrapper@@YAJPEAU_GUID@@PEAU_VELAN@@PEAU_NWF_KEY_CONTEXT@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUNWF_RSNA_FT_GTK_SUB_ELEMENT@@PEAUNWF_RSNA_FT_IGTK_SUB_ELEMENT@@PEAUNWF_RSNA_FT_BIGTK_SUB_ELEMENT@@@Z`
- size: `1244`
- prototype: `__int64 __fastcall(struct _GUID *, struct _VELAN *, struct _NWF_KEY_CONTEXT *, struct DOT11_MAC_STATE_ENTRY *, struct NWF_RSNA_FT_GTK_SUB_ELEMENT *, struct NWF_RSNA_FT_IGTK_SUB_ELEMENT *, struct NWF_RSNA_FT_BIGTK_SUB_ELEMENT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140047794`

## callees

- `0x14000a898`
- `0x1400208f0`
- `0x140020dc0`
- `0x140030244`
- `0x14004d8fc`
- `0x14004dde0`
- `0x14008f5e4`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d9e9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d9e9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004dda0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004dda0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ddb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ddb1`

## pseudocode

```c
__int64 __fastcall InstallFTGroupKeyWrapper(
        struct _GUID *a1,
        struct _VELAN *a2,
        struct _NWF_KEY_CONTEXT *a3,
        struct DOT11_MAC_STATE_ENTRY *a4,
        struct NWF_RSNA_FT_GTK_SUB_ELEMENT *a5,
        struct NWF_RSNA_FT_IGTK_SUB_ELEMENT *a6,
        struct NWF_RSNA_FT_BIGTK_SUB_ELEMENT *a7)
{
  unsigned int v9; // ebx
  int v10; // edi
  struct NWF_RSNA_FT_IGTK_SUB_ELEMENT *v11; // rsi
  unsigned __int8 *v12; // r15
  unsigned int v13; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  char *v15; // rax
  int v16; // eax
  int v17; // eax
  int v18; // edx
  int v19; // ecx
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  PDEVICE_OBJECT v22; // rcx
  int v23; // eax
  __int64 v24; // rdx
  int v25; // r9d
  int v26; // ecx
  int v27; // eax
  __int64 v28; // r9
  int v30; // [rsp+28h] [rbp-50h]
  int v31; // [rsp+80h] [rbp+8h]

  v31 = (int)a1;
  v9 = 16;
  if ( !a5 )
  {
    v10 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)v10;
    v11 = a6;
    v12 = 0;
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 530, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, a6);
    goto LABEL_45;
  }
  v11 = a6;
  if ( (unsigned int)*((unsigned __int8 *)a5 + 4) + 8 >= 0x10 )
    v9 = *((unsigned __int8 *)a5 + 4) + 8;
  if ( a6 && v9 <= (unsigned int)*((unsigned __int8 *)a6 + 10) + 8 )
    v9 = *((unsigned __int8 *)a6 + 10) + 8;
  if ( a7 && v9 <= (unsigned int)*((unsigned __int8 *)a7 + 10) + 8 )
    v9 = *((unsigned __int8 *)a7 + 10) + 8;
  v13 = v9 + 16;
  if ( v9 >= 0xFFFFFFF0 )
    goto LABEL_43;
  if ( v13 > 0x40 )
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    if ( v13 > 0x100 )
      p_WaitListHead = &Lookaside;
  }
  else
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  }
  v15 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
  if ( !v15 )
  {
LABEL_43:
    v10 = -1073741670;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)v10;
    v12 = 0;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 531, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v9);
    goto LABEL_45;
  }
  v12 = (unsigned __int8 *)(v15 + 16);
  *(_QWORD *)v15 = p_WaitListHead;
  *((_DWORD *)v15 + 2) = 2053731191;
  memset(v15 + 16, 0, v9);
  v16 = AES_UNWRAP(
          (int)a3 + a3->TempPTK.KCKLength + 1044,
          a3->TempPTK.KEKLength,
          (int)a5 + 13,
          (unsigned int)*((unsigned __int8 *)a5 + 1) - 11,
          (__int64)v12);
  v10 = v16;
  if ( v16 >= 0 )
  {
    v17 = InstallGroupKey(
            a2,
            a4,
            a3->McastCipher,
            *((_BYTE *)a5 + 2) & 3,
            (unsigned __int8 *)a5 + 5,
            0,
            *((unsigned __int8 *)a5 + 4),
            v12);
    v10 = v17;
    if ( v17 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_56;
      v21 = 533;
      goto LABEL_25;
    }
    if ( !a6 )
      goto LABEL_63;
    memset(v12, 0, v9);
    v10 = AES_UNWRAP(
            (int)a3 + a3->TempPTK.KCKLength + 1044,
            a3->TempPTK.KEKLength,
            (int)a6 + 11,
            (unsigned int)*((unsigned __int8 *)a6 + 1) - 9,
            (__int64)v12);
    if ( v10 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_56;
      v23 = *((unsigned __int8 *)a6 + 10);
      v24 = 534;
      v25 = *((unsigned __int8 *)a6 + 1);
      goto LABEL_30;
    }
    v17 = InstallGroupKey(
            a2,
            a4,
            a3->McastMgmtCipher,
            *((unsigned __int8 *)a6 + 2),
            0,
            (unsigned __int8 *)a6 + 4,
            *((unsigned __int8 *)a6 + 10),
            v12);
    v10 = v17;
    if ( v17 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_56;
      v21 = 535;
    }
    else
    {
LABEL_63:
      if ( !a7 )
        goto LABEL_41;
      memset(v12, 0, v9);
      v10 = AES_UNWRAP(
              (int)a3 + a3->TempPTK.KCKLength + 1044,
              a3->TempPTK.KEKLength,
              (int)a7 + 11,
              (unsigned int)*((unsigned __int8 *)a7 + 1) - 9,
              (__int64)v12);
      if ( v10 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_56;
        v23 = *((unsigned __int8 *)a7 + 10);
        v24 = 536;
        v25 = *((unsigned __int8 *)a7 + 1);
LABEL_30:
        WPP_SF_lll(
          v22->AttachedDevice,
          v24,
          WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
          (unsigned int)(v25 - 9),
          v23,
          v10);
        goto LABEL_45;
      }
      v17 = InstallGroupKey(
              a2,
              a4,
              a3->McastMgmtCipher,
              *((unsigned __int8 *)a7 + 2),
              0,
              (unsigned __int8 *)a7 + 4,
              *((unsigned __int8 *)a7 + 10),
              v12);
      v10 = v17;
      if ( v17 >= 0 )
      {
LABEL_41:
        if ( (byte_1400B2804 & 8) != 0 )
          McTemplateK0qquq_EtwWriteTransfer(
            v19,
            v18,
            v31,
            *((_BYTE *)a5 + 2) & 3,
            a3->McastCipher,
            v30,
            *((_BYTE *)a5 + 4));
        goto LABEL_45;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_56;
      v21 = 537;
    }
LABEL_25:
    WPP_SF_d(v20->AttachedDevice, v21, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, (unsigned int)v17);
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_lll(
      WPP_GLOBAL_Control->AttachedDevice,
      532,
      WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
      (unsigned int)*((unsigned __int8 *)a5 + 1) - 11,
      *((unsigned __int8 *)a5 + 4),
      v16);
LABEL_45:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( a7 )
        v26 = *((unsigned __int8 *)a7 + 10);
      else
        v26 = 0;
      if ( v11 )
        v27 = *((unsigned __int8 *)v11 + 10);
      else
        v27 = 0;
      if ( a5 )
        v28 = *((unsigned __int8 *)a5 + 4);
      else
        v28 = 0;
      WPP_SF_lll(
        WPP_GLOBAL_Control->AttachedDevice,
        538,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        v28,
        v27,
        v26);
    }
  }
LABEL_56:
  if ( v12 )
  {
    memset(v12, 0, v9);
    if ( *((_QWORD *)v12 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), v12 - 16);
    else
      ExFreePoolWithTag(v12 - 16, *((_DWORD *)v12 - 2));
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14004d8fc  mov     [rsp+arg_10], rbx
0x14004d901  mov     [rsp+arg_8], rdx
0x14004d906  mov     [rsp+arg_0], rcx
0x14004d90b  push    rbp
0x14004d90c  push    rsi
0x14004d90d  push    rdi
0x14004d90e  push    r12
0x14004d910  push    r13
0x14004d912  push    r14
0x14004d914  push    r15
0x14004d916  sub     rsp, 40h
0x14004d91a  mov     r14, [rsp+78h+arg_20]
0x14004d922  lea     r15, WPP_GLOBAL_Control
0x14004d929  mov     rbp, [rsp+78h+arg_30]
0x14004d931  mov     r12, r9
0x14004d934  mov     r13, r8
0x14004d937  mov     ebx, 10h
0x14004d93c  test    r14, r14
0x14004d93f  jnz     short loc_14004D97E
0x14004d941  mov     edi, 0C000000Dh
0x14004d946  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d94d  cmp     rcx, r15
0x14004d950  jz      loc_14004DDBD
0x14004d956  mov     rsi, [rsp+78h+arg_28]
0x14004d95e  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004d965  mov     rcx, [rcx+18h]
0x14004d969  mov     r9, rsi
0x14004d96c  xor     r15d, r15d
0x14004d96f  mov     edx, 212h
0x14004d974  call    WPP_SF_q
0x14004d979  jmp     loc_14004DD23
0x14004d97e  movzx   eax, byte ptr [r14+4]
0x14004d983  mov     rsi, [rsp+78h+arg_28]
0x14004d98b  add     eax, 8
0x14004d98e  cmp     eax, ebx
0x14004d990  cmovnb  ebx, eax
0x14004d993  test    rsi, rsi
0x14004d996  jz      short loc_14004D9A4
0x14004d998  movzx   eax, byte ptr [rsi+0Ah]
0x14004d99c  add     eax, 8
0x14004d99f  cmp     ebx, eax
0x14004d9a1  cmovbe  ebx, eax
0x14004d9a4  test    rbp, rbp
0x14004d9a7  jz      short loc_14004D9B5
0x14004d9a9  movzx   eax, byte ptr [rbp+0Ah]
0x14004d9ad  add     eax, 8
0x14004d9b0  cmp     ebx, eax
0x14004d9b2  cmovbe  ebx, eax
0x14004d9b5  lea     eax, [rbx+10h]
0x14004d9b8  cmp     eax, 10h
0x14004d9bb  jb      loc_14004DCF3
0x14004d9c1  cmp     eax, 40h ; '@'
0x14004d9c4  ja      short loc_14004D9CF
0x14004d9c6  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14004d9cd  jmp     short loc_14004D9E6
0x14004d9cf  cmp     eax, 100h
0x14004d9d4  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004d9db  lea     rcx, Lookaside
0x14004d9e2  cmova   rdi, rcx
0x14004d9e6  mov     rcx, rdi; Lookaside
0x14004d9e9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004d9f0  nop     dword ptr [rax+rax+00h]
0x14004d9f5  test    rax, rax
0x14004d9f8  jz      loc_14004DCF3
0x14004d9fe  lea     r15, [rax+10h]
0x14004da02  mov     r8d, ebx; Size
0x14004da05  mov     rcx, r15; void *
0x14004da08  mov     [rax], rdi
0x14004da0b  xor     edx, edx; Val
0x14004da0d  mov     dword ptr [rax+8], 7A697377h
0x14004da14  call    memset
0x14004da19  mov     ecx, [r13+408h]
0x14004da20  lea     r8, [r14+0Dh]
0x14004da24  movzx   r9d, byte ptr [r14+1]
0x14004da29  add     rcx, 414h
0x14004da30  mov     edx, [r13+40Ch]
0x14004da37  add     rcx, r13
0x14004da3a  sub     r9d, 0Bh
0x14004da3e  mov     [rsp+78h+var_58], r15
0x14004da43  call    AES_UNWRAP
0x14004da48  mov     edi, eax
0x14004da4a  test    eax, eax
0x14004da4c  jns     short loc_14004DA96
0x14004da4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004da55  lea     r12, WPP_GLOBAL_Control
0x14004da5c  cmp     rcx, r12
0x14004da5f  jz      loc_14004DD7C
0x14004da65  movzx   r8d, byte ptr [r14+4]
0x14004da6a  mov     edx, 214h
0x14004da6f  movzx   r9d, byte ptr [r14+1]
0x14004da74  mov     dword ptr [rsp+78h+var_50], eax
0x14004da78  sub     r9d, 0Bh
0x14004da7c  mov     dword ptr [rsp+78h+var_58], r8d
0x14004da81  mov     rcx, [rcx+18h]
0x14004da85  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004da8c  call    WPP_SF_lll
0x14004da91  jmp     loc_14004DD2A
0x14004da96  movzx   eax, byte ptr [r14+4]
0x14004da9b  lea     rcx, [r14+5]
0x14004da9f  movzx   r9d, byte ptr [r14+2]
0x14004daa4  mov     rdx, r12; struct DOT11_MAC_STATE_ENTRY *
0x14004daa7  mov     r8d, [r13+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004daab  and     r9d, 3; unsigned int
0x14004daaf  mov     [rsp+78h+var_40], r15; unsigned __int8 *
0x14004dab4  mov     [rsp+78h+var_48], eax; unsigned int
0x14004dab8  mov     [rsp+78h+var_50], 0; unsigned __int8 *
0x14004dac1  mov     [rsp+78h+var_58], rcx; unsigned __int8 *
0x14004dac6  mov     rcx, [rsp+78h+arg_8]; struct _VELAN *
0x14004dace  call    ?InstallGroupKey@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_CIPHER_ALGORITHM@@KPEBE3K3@Z; InstallGroupKey(_VELAN *,DOT11_MAC_STATE_ENTRY *,_DOT11_CIPHER_ALGORITHM,ulong,uchar const *,uchar const *,ulong,uchar const *)
0x14004dad3  mov     edi, eax
0x14004dad5  test    eax, eax
0x14004dad7  jns     short loc_14004DB0D
0x14004dad9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dae0  lea     r12, WPP_GLOBAL_Control
0x14004dae7  cmp     rcx, r12
0x14004daea  jz      loc_14004DD7C
0x14004daf0  mov     edx, 215h
0x14004daf5  mov     rcx, [rcx+18h]
0x14004daf9  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004db00  mov     r9d, eax
0x14004db03  call    WPP_SF_d
0x14004db08  jmp     loc_14004DD2A
0x14004db0d  test    rsi, rsi
0x14004db10  jz      loc_14004DBED
0x14004db16  mov     r8d, ebx; Size
0x14004db19  xor     edx, edx; Val
0x14004db1b  mov     rcx, r15; void *
0x14004db1e  call    memset
0x14004db23  mov     ecx, [r13+408h]
0x14004db2a  lea     r8, [rsi+0Bh]
0x14004db2e  movzx   r9d, byte ptr [rsi+1]
0x14004db33  add     rcx, 414h
0x14004db3a  mov     edx, [r13+40Ch]
0x14004db41  add     rcx, r13
0x14004db44  sub     r9d, 9
0x14004db48  mov     [rsp+78h+var_58], r15
0x14004db4d  call    AES_UNWRAP
0x14004db52  mov     edi, eax
0x14004db54  test    eax, eax
0x14004db56  jns     short loc_14004DB8E
0x14004db58  mov     rcx, cs:WPP_GLOBAL_Control
0x14004db5f  lea     r12, WPP_GLOBAL_Control
0x14004db66  cmp     rcx, r12
0x14004db69  jz      loc_14004DD7C
0x14004db6f  movzx   eax, byte ptr [rsi+0Ah]
0x14004db73  mov     edx, 216h
0x14004db78  movzx   r9d, byte ptr [rsi+1]
0x14004db7d  mov     dword ptr [rsp+78h+var_50], edi
0x14004db81  sub     r9d, 9
0x14004db85  mov     dword ptr [rsp+78h+var_58], eax
0x14004db89  jmp     loc_14004DA81
0x14004db8e  movzx   eax, byte ptr [rsi+0Ah]
0x14004db92  lea     rcx, [rsi+4]
0x14004db96  movzx   r9d, byte ptr [rsi+2]; unsigned int
0x14004db9b  mov     rdx, r12; struct DOT11_MAC_STATE_ENTRY *
0x14004db9e  mov     r8d, [r13+18h]; enum _DOT11_CIPHER_ALGORITHM
0x14004dba2  mov     [rsp+78h+var_40], r15; unsigned __int8 *
0x14004dba7  mov     [rsp+78h+var_48], eax; unsigned int
0x14004dbab  mov     [rsp+78h+var_50], rcx; unsigned __int8 *
0x14004dbb0  mov     rcx, [rsp+78h+arg_8]; struct _VELAN *
0x14004dbb8  mov     [rsp+78h+var_58], 0; unsigned __int8 *
0x14004dbc1  call    ?InstallGroupKey@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_CIPHER_ALGORITHM@@KPEBE3K3@Z; InstallGroupKey(_VELAN *,DOT11_MAC_STATE_ENTRY *,_DOT11_CIPHER_ALGORITHM,ulong,uchar const *,uchar const *,ulong,uchar const *)
0x14004dbc6  mov     edi, eax
0x14004dbc8  test    eax, eax
0x14004dbca  jns     short loc_14004DBED
0x14004dbcc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dbd3  lea     r12, WPP_GLOBAL_Control
0x14004dbda  cmp     rcx, r12
0x14004dbdd  jz      loc_14004DD7C
0x14004dbe3  mov     edx, 217h
0x14004dbe8  jmp     loc_14004DAF5
0x14004dbed  test    rbp, rbp
0x14004dbf0  jz      loc_14004DCC1
0x14004dbf6  mov     r8d, ebx; Size
0x14004dbf9  xor     edx, edx; Val
0x14004dbfb  mov     rcx, r15; void *
0x14004dbfe  call    memset
0x14004dc03  mov     ecx, [r13+408h]
0x14004dc0a  lea     r8, [rbp+0Bh]
0x14004dc0e  movzx   r9d, byte ptr [rbp+1]
0x14004dc13  add     rcx, 414h
0x14004dc1a  mov     edx, [r13+40Ch]
0x14004dc21  add     rcx, r13
0x14004dc24  sub     r9d, 9
0x14004dc28  mov     [rsp+78h+var_58], r15
0x14004dc2d  call    AES_UNWRAP
0x14004dc32  mov     edi, eax
0x14004dc34  test    eax, eax
0x14004dc36  jns     short loc_14004DC62
0x14004dc38  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dc3f  lea     r12, WPP_GLOBAL_Control
0x14004dc46  cmp     rcx, r12
0x14004dc49  jz      loc_14004DD7C
0x14004dc4f  movzx   eax, byte ptr [rbp+0Ah]
0x14004dc53  mov     edx, 218h
0x14004dc58  movzx   r9d, byte ptr [rbp+1]
0x14004dc5d  jmp     loc_14004DB7D
0x14004dc62  movzx   eax, byte ptr [rbp+0Ah]
0x14004dc66  lea     rcx, [rbp+4]
0x14004dc6a  movzx   r9d, byte ptr [rbp+2]; unsigned int
0x14004dc6f  mov     rdx, r12; struct DOT11_MAC_STATE_ENTRY *
0x14004dc72  mov     r8d, [r13+18h]; enum _DOT11_CIPHER_ALGORITHM
0x14004dc76  mov     [rsp+78h+var_40], r15; unsigned __int8 *
0x14004dc7b  mov     [rsp+78h+var_48], eax; unsigned int
0x14004dc7f  mov     [rsp+78h+var_50], rcx; unsigned __int8 *
0x14004dc84  mov     rcx, [rsp+78h+arg_8]; struct _VELAN *
0x14004dc8c  mov     [rsp+78h+var_58], 0; unsigned __int8 *
0x14004dc95  call    ?InstallGroupKey@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_CIPHER_ALGORITHM@@KPEBE3K3@Z; InstallGroupKey(_VELAN *,DOT11_MAC_STATE_ENTRY *,_DOT11_CIPHER_ALGORITHM,ulong,uchar const *,uchar const *,ulong,uchar const *)
0x14004dc9a  mov     edi, eax
0x14004dc9c  test    eax, eax
0x14004dc9e  jns     short loc_14004DCC1
0x14004dca0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dca7  lea     r12, WPP_GLOBAL_Control
0x14004dcae  cmp     rcx, r12
0x14004dcb1  jz      loc_14004DD7C
0x14004dcb7  mov     edx, 219h
0x14004dcbc  jmp     loc_14004DAF5
0x14004dcc1  test    cs:byte_1400B2804, 8
0x14004dcc8  jz      short loc_14004DD23
0x14004dcca  movzx   eax, byte ptr [r14+4]
0x14004dccf  movzx   r9d, byte ptr [r14+2]
0x14004dcd4  mov     r8, [rsp+78h+arg_0]
0x14004dcdc  and     r9d, 3
0x14004dce0  mov     [rsp+78h+var_48], eax
0x14004dce4  mov     eax, [r13+14h]
0x14004dce8  mov     dword ptr [rsp+78h+var_58], eax
0x14004dcec  call    McTemplateK0qquq_EtwWriteTransfer
0x14004dcf1  jmp     short loc_14004DD23
0x14004dcf3  mov     edi, 0C000009Ah
0x14004dcf8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dcff  cmp     rcx, r15
0x14004dd02  jz      loc_14004DDBD
0x14004dd08  mov     rcx, [rcx+18h]
0x14004dd0c  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004dd13  xor     r15d, r15d
0x14004dd16  mov     edx, 213h
0x14004dd1b  mov     r9d, ebx
0x14004dd1e  call    WPP_SF_d
0x14004dd23  lea     r12, WPP_GLOBAL_Control
0x14004dd2a  mov     r10, cs:WPP_GLOBAL_Control
0x14004dd31  cmp     r10, r12
0x14004dd34  jz      short loc_14004DD7C
0x14004dd36  test    rbp, rbp
0x14004dd39  jz      short loc_14004DD41
0x14004dd3b  movzx   ecx, byte ptr [rbp+0Ah]
0x14004dd3f  jmp     short loc_14004DD43
0x14004dd41  xor     ecx, ecx
0x14004dd43  test    rsi, rsi
0x14004dd46  jz      short loc_14004DD4E
0x14004dd48  movzx   eax, byte ptr [rsi+0Ah]
0x14004dd4c  jmp     short loc_14004DD50
0x14004dd4e  xor     eax, eax
0x14004dd50  test    r14, r14
0x14004dd53  jz      short loc_14004DD5C
0x14004dd55  movzx   r9d, byte ptr [r14+4]
0x14004dd5a  jmp     short loc_14004DD5F
0x14004dd5c  xor     r9d, r9d
0x14004dd5f  mov     dword ptr [rsp+78h+var_50], ecx
0x14004dd63  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004dd6a  mov     rcx, [r10+18h]
0x14004dd6e  mov     edx, 21Ah
0x14004dd73  mov     dword ptr [rsp+78h+var_58], eax
0x14004dd77  call    WPP_SF_lll
0x14004dd7c  test    r15, r15
0x14004dd7f  jz      short loc_14004DDBD
0x14004dd81  mov     r8d, ebx; Size
0x14004dd84  xor     edx, edx; Val
0x14004dd86  mov     rcx, r15; void *
0x14004dd89  call    memset
0x14004dd8e  lea     rcx, [r15-10h]; P
0x14004dd92  mov     rax, [rcx]
0x14004dd95  test    rax, rax
0x14004dd98  jz      short loc_14004DDAE
0x14004dd9a  mov     rdx, rcx; Entry
0x14004dd9d  mov     rcx, rax; Lookaside
0x14004dda0  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004dda7  nop     dword ptr [rax+rax+00h]
0x14004ddac  jmp     short loc_14004DDBD
0x14004ddae  mov     edx, [rcx+8]; Tag
0x14004ddb1  call    cs:__imp_ExFreePoolWithTag
0x14004ddb8  nop     dword ptr [rax+rax+00h]
0x14004ddbd  mov     rbx, [rsp+78h+arg_10]
0x14004ddc5  mov     eax, edi
0x14004ddc7  add     rsp, 40h
0x14004ddcb  pop     r15
0x14004ddcd  pop     r14
0x14004ddcf  pop     r13
0x14004ddd1  pop     r12
0x14004ddd3  pop     rdi
0x14004ddd4  pop     rsi
0x14004ddd5  pop     rbp
0x14004ddd6  retn
```
