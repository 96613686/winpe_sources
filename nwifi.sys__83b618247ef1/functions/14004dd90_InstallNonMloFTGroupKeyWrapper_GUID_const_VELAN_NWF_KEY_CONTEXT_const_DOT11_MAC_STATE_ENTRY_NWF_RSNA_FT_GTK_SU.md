# InstallNonMloFTGroupKeyWrapper(_GUID const *,_VELAN *,_NWF_KEY_CONTEXT const *,DOT11_MAC_STATE_ENTRY *,NWF_RSNA_FT_GTK_SUB_ELEMENT const *,NWF_RSNA_FT_IGTK_SUB_ELEMENT const *,NWF_RSNA_FT_BIGTK_SUB_ELEMENT const *)

- ea: `0x14004dd90`
- end: `0x14004e26e`
- name: `?InstallNonMloFTGroupKeyWrapper@@YAJPEBU_GUID@@PEAU_VELAN@@PEBU_NWF_KEY_CONTEXT@@PEAUDOT11_MAC_STATE_ENTRY@@PEBUNWF_RSNA_FT_GTK_SUB_ELEMENT@@PEBUNWF_RSNA_FT_IGTK_SUB_ELEMENT@@PEBUNWF_RSNA_FT_BIGTK_SUB_ELEMENT@@@Z`
- size: `1246`
- prototype: `int(const struct _GUID *, struct _VELAN *, const struct _NWF_KEY_CONTEXT *, struct DOT11_MAC_STATE_ENTRY *, const struct NWF_RSNA_FT_GTK_SUB_ELEMENT *, const struct NWF_RSNA_FT_IGTK_SUB_ELEMENT *, const struct NWF_RSNA_FT_BIGTK_SUB_ELEMENT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140046bf0`

## callees

- `0x14000a8a8`
- `0x1400208f0`
- `0x140020dc0`
- `0x14002ffb4`
- `0x14004c674`
- `0x14004dd90`
- `0x14008ddb4`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004de7f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004de7f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e236`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e236`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e247`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e247`

## pseudocode

```c
__int64 __fastcall InstallNonMloFTGroupKeyWrapper(
        const struct _GUID *a1,
        struct _VELAN *a2,
        const struct _NWF_KEY_CONTEXT *a3,
        struct DOT11_MAC_STATE_ENTRY *a4,
        const struct NWF_RSNA_FT_GTK_SUB_ELEMENT *a5,
        const struct NWF_RSNA_FT_IGTK_SUB_ELEMENT *a6,
        const struct NWF_RSNA_FT_BIGTK_SUB_ELEMENT *a7)
{
  int v9; // edi
  const struct NWF_RSNA_FT_IGTK_SUB_ELEMENT *v10; // rsi
  unsigned __int8 *v11; // r15
  unsigned int v12; // ebx
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
  if ( !a5 )
  {
    v9 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)v9;
    v10 = a6;
    v11 = 0;
    v12 = 0;
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 458, WPP_e90d411d816e312466897e39e745b158_Traceguids, a6);
    goto LABEL_45;
  }
  v12 = 24;
  v10 = a6;
  if ( (unsigned int)*((unsigned __int8 *)a5 + 4) + 8 >= 0x18 )
    v12 = *((unsigned __int8 *)a5 + 4) + 8;
  if ( a6 && v12 <= (unsigned int)*((unsigned __int8 *)a6 + 10) + 8 )
    v12 = *((unsigned __int8 *)a6 + 10) + 8;
  if ( a7 && v12 <= (unsigned int)*((unsigned __int8 *)a7 + 10) + 8 )
    v12 = *((unsigned __int8 *)a7 + 10) + 8;
  v13 = v12 + 16;
  if ( v12 >= 0xFFFFFFF0 )
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
    v9 = -1073741670;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)v9;
    v11 = 0;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 459, WPP_e90d411d816e312466897e39e745b158_Traceguids, v12);
    goto LABEL_45;
  }
  v11 = (unsigned __int8 *)(v15 + 16);
  *(_QWORD *)v15 = p_WaitListHead;
  *((_DWORD *)v15 + 2) = 2053731191;
  memset(v15 + 16, 0, v12);
  v16 = AES_UNWRAP(
          (int)a3 + a3->TempPTK.KCKLength + 1044,
          a3->TempPTK.KEKLength,
          (int)a5 + 13,
          (unsigned int)*((unsigned __int8 *)a5 + 1) - 11,
          (__int64)v11);
  v9 = v16;
  if ( v16 >= 0 )
  {
    v17 = InstallGroupKey(
            a2,
            a4,
            a3->McastCipher,
            *((_BYTE *)a5 + 2) & 3,
            (const unsigned __int8 *)a5 + 5,
            0,
            *((unsigned __int8 *)a5 + 4),
            v11);
    v9 = v17;
    if ( v17 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_56;
      v21 = 461;
      goto LABEL_25;
    }
    if ( !a6 )
      goto LABEL_63;
    memset(v11, 0, v12);
    v9 = AES_UNWRAP(
           (int)a3 + a3->TempPTK.KCKLength + 1044,
           a3->TempPTK.KEKLength,
           (int)a6 + 11,
           (unsigned int)*((unsigned __int8 *)a6 + 1) - 9,
           (__int64)v11);
    if ( v9 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_56;
      v23 = *((unsigned __int8 *)a6 + 10);
      v24 = 462;
      v25 = *((unsigned __int8 *)a6 + 1);
      goto LABEL_30;
    }
    v17 = InstallGroupKey(
            a2,
            a4,
            a3->McastMgmtCipher,
            *((unsigned __int8 *)a6 + 2),
            0,
            (const unsigned __int8 *)a6 + 4,
            *((unsigned __int8 *)a6 + 10),
            v11);
    v9 = v17;
    if ( v17 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_56;
      v21 = 463;
    }
    else
    {
LABEL_63:
      if ( !a7 )
        goto LABEL_41;
      memset(v11, 0, v12);
      v9 = AES_UNWRAP(
             (int)a3 + a3->TempPTK.KCKLength + 1044,
             a3->TempPTK.KEKLength,
             (int)a7 + 11,
             (unsigned int)*((unsigned __int8 *)a7 + 1) - 9,
             (__int64)v11);
      if ( v9 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_56;
        v23 = *((unsigned __int8 *)a7 + 10);
        v24 = 464;
        v25 = *((unsigned __int8 *)a7 + 1);
LABEL_30:
        WPP_SF_lll(
          v22->AttachedDevice,
          v24,
          WPP_e90d411d816e312466897e39e745b158_Traceguids,
          (unsigned int)(v25 - 9),
          v23,
          v9);
        goto LABEL_45;
      }
      v17 = InstallGroupKey(
              a2,
              a4,
              a3->McastMgmtCipher,
              *((unsigned __int8 *)a7 + 2),
              0,
              (const unsigned __int8 *)a7 + 4,
              *((unsigned __int8 *)a7 + 10),
              v11);
      v9 = v17;
      if ( v17 >= 0 )
      {
LABEL_41:
        if ( (byte_1400AF804 & 8) != 0 )
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
      v21 = 465;
    }
LABEL_25:
    WPP_SF_d(v20->AttachedDevice, v21, WPP_e90d411d816e312466897e39e745b158_Traceguids, (unsigned int)v17);
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_lll(
      WPP_GLOBAL_Control->AttachedDevice,
      460,
      WPP_e90d411d816e312466897e39e745b158_Traceguids,
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
      if ( v10 )
        v27 = *((unsigned __int8 *)v10 + 10);
      else
        v27 = 0;
      if ( a5 )
        v28 = *((unsigned __int8 *)a5 + 4);
      else
        v28 = 0;
      WPP_SF_lll(
        WPP_GLOBAL_Control->AttachedDevice,
        466,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        v28,
        v27,
        v26);
    }
  }
LABEL_56:
  if ( v11 )
  {
    memset(v11, 0, v12);
    if ( *((_QWORD *)v11 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v11 - 2), v11 - 16);
    else
      ExFreePoolWithTag(v11 - 16, *((_DWORD *)v11 - 2));
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14004dd90  mov     [rsp+arg_10], rbx
0x14004dd95  mov     [rsp+arg_8], rdx
0x14004dd9a  mov     [rsp+arg_0], rcx
0x14004dd9f  push    rbp
0x14004dda0  push    rsi
0x14004dda1  push    rdi
0x14004dda2  push    r12
0x14004dda4  push    r13
0x14004dda6  push    r14
0x14004dda8  push    r15
0x14004ddaa  sub     rsp, 40h
0x14004ddae  mov     r14, [rsp+78h+arg_20]
0x14004ddb6  lea     r15, WPP_GLOBAL_Control
0x14004ddbd  mov     rbp, [rsp+78h+arg_30]
0x14004ddc5  mov     r12, r9
0x14004ddc8  mov     r13, r8
0x14004ddcb  test    r14, r14
0x14004ddce  jnz     short loc_14004DE0F
0x14004ddd0  mov     edi, 0C000000Dh
0x14004ddd5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dddc  cmp     rcx, r15
0x14004dddf  jz      loc_14004E253
0x14004dde5  mov     rsi, [rsp+78h+arg_28]
0x14004dded  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004ddf4  mov     rcx, [rcx+18h]
0x14004ddf8  mov     r9, rsi
0x14004ddfb  xor     r15d, r15d
0x14004ddfe  xor     ebx, ebx
0x14004de00  mov     edx, 1CAh
0x14004de05  call    WPP_SF_q
0x14004de0a  jmp     loc_14004E1B9
0x14004de0f  movzx   eax, byte ptr [r14+4]
0x14004de14  mov     ebx, 18h
0x14004de19  mov     rsi, [rsp+78h+arg_28]
0x14004de21  add     eax, 8
0x14004de24  cmp     eax, ebx
0x14004de26  cmovnb  ebx, eax
0x14004de29  test    rsi, rsi
0x14004de2c  jz      short loc_14004DE3A
0x14004de2e  movzx   eax, byte ptr [rsi+0Ah]
0x14004de32  add     eax, 8
0x14004de35  cmp     ebx, eax
0x14004de37  cmovbe  ebx, eax
0x14004de3a  test    rbp, rbp
0x14004de3d  jz      short loc_14004DE4B
0x14004de3f  movzx   eax, byte ptr [rbp+0Ah]
0x14004de43  add     eax, 8
0x14004de46  cmp     ebx, eax
0x14004de48  cmovbe  ebx, eax
0x14004de4b  lea     eax, [rbx+10h]
0x14004de4e  cmp     eax, 10h
0x14004de51  jb      loc_14004E189
0x14004de57  cmp     eax, 40h ; '@'
0x14004de5a  ja      short loc_14004DE65
0x14004de5c  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14004de63  jmp     short loc_14004DE7C
0x14004de65  cmp     eax, 100h
0x14004de6a  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004de71  lea     rcx, Lookaside
0x14004de78  cmova   rdi, rcx
0x14004de7c  mov     rcx, rdi; Lookaside
0x14004de7f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004de86  nop     dword ptr [rax+rax+00h]
0x14004de8b  test    rax, rax
0x14004de8e  jz      loc_14004E189
0x14004de94  lea     r15, [rax+10h]
0x14004de98  mov     r8d, ebx; Size
0x14004de9b  mov     rcx, r15; void *
0x14004de9e  mov     [rax], rdi
0x14004dea1  xor     edx, edx; Val
0x14004dea3  mov     dword ptr [rax+8], 7A697377h
0x14004deaa  call    memset
0x14004deaf  mov     ecx, [r13+408h]
0x14004deb6  lea     r8, [r14+0Dh]
0x14004deba  movzx   r9d, byte ptr [r14+1]
0x14004debf  add     rcx, 414h
0x14004dec6  mov     edx, [r13+40Ch]
0x14004decd  add     rcx, r13
0x14004ded0  sub     r9d, 0Bh
0x14004ded4  mov     [rsp+78h+var_58], r15
0x14004ded9  call    AES_UNWRAP
0x14004dede  mov     edi, eax
0x14004dee0  test    eax, eax
0x14004dee2  jns     short loc_14004DF2C
0x14004dee4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004deeb  lea     r12, WPP_GLOBAL_Control
0x14004def2  cmp     rcx, r12
0x14004def5  jz      loc_14004E212
0x14004defb  movzx   r8d, byte ptr [r14+4]
0x14004df00  mov     edx, 1CCh
0x14004df05  movzx   r9d, byte ptr [r14+1]
0x14004df0a  mov     dword ptr [rsp+78h+var_50], eax
0x14004df0e  sub     r9d, 0Bh
0x14004df12  mov     dword ptr [rsp+78h+var_58], r8d
0x14004df17  mov     rcx, [rcx+18h]
0x14004df1b  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004df22  call    WPP_SF_lll
0x14004df27  jmp     loc_14004E1C0
0x14004df2c  movzx   eax, byte ptr [r14+4]
0x14004df31  lea     rcx, [r14+5]
0x14004df35  movzx   r9d, byte ptr [r14+2]
0x14004df3a  mov     rdx, r12; struct DOT11_MAC_STATE_ENTRY *
0x14004df3d  mov     r8d, [r13+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004df41  and     r9d, 3; unsigned int
0x14004df45  mov     [rsp+78h+var_40], r15; unsigned __int8 *
0x14004df4a  mov     [rsp+78h+var_48], eax; unsigned int
0x14004df4e  mov     [rsp+78h+var_50], 0; unsigned __int8 *
0x14004df57  mov     [rsp+78h+var_58], rcx; unsigned __int8 *
0x14004df5c  mov     rcx, [rsp+78h+arg_8]; struct _VELAN *
0x14004df64  call    ?InstallGroupKey@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_CIPHER_ALGORITHM@@KPEBE3K3@Z; InstallGroupKey(_VELAN *,DOT11_MAC_STATE_ENTRY *,_DOT11_CIPHER_ALGORITHM,ulong,uchar const *,uchar const *,ulong,uchar const *)
0x14004df69  mov     edi, eax
0x14004df6b  test    eax, eax
0x14004df6d  jns     short loc_14004DFA3
0x14004df6f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004df76  lea     r12, WPP_GLOBAL_Control
0x14004df7d  cmp     rcx, r12
0x14004df80  jz      loc_14004E212
0x14004df86  mov     edx, 1CDh
0x14004df8b  mov     rcx, [rcx+18h]
0x14004df8f  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004df96  mov     r9d, eax
0x14004df99  call    WPP_SF_d
0x14004df9e  jmp     loc_14004E1C0
0x14004dfa3  test    rsi, rsi
0x14004dfa6  jz      loc_14004E083
0x14004dfac  mov     r8d, ebx; Size
0x14004dfaf  xor     edx, edx; Val
0x14004dfb1  mov     rcx, r15; void *
0x14004dfb4  call    memset
0x14004dfb9  mov     ecx, [r13+408h]
0x14004dfc0  lea     r8, [rsi+0Bh]
0x14004dfc4  movzx   r9d, byte ptr [rsi+1]
0x14004dfc9  add     rcx, 414h
0x14004dfd0  mov     edx, [r13+40Ch]
0x14004dfd7  add     rcx, r13
0x14004dfda  sub     r9d, 9
0x14004dfde  mov     [rsp+78h+var_58], r15
0x14004dfe3  call    AES_UNWRAP
0x14004dfe8  mov     edi, eax
0x14004dfea  test    eax, eax
0x14004dfec  jns     short loc_14004E024
0x14004dfee  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dff5  lea     r12, WPP_GLOBAL_Control
0x14004dffc  cmp     rcx, r12
0x14004dfff  jz      loc_14004E212
0x14004e005  movzx   eax, byte ptr [rsi+0Ah]
0x14004e009  mov     edx, 1CEh
0x14004e00e  movzx   r9d, byte ptr [rsi+1]
0x14004e013  mov     dword ptr [rsp+78h+var_50], edi
0x14004e017  sub     r9d, 9
0x14004e01b  mov     dword ptr [rsp+78h+var_58], eax
0x14004e01f  jmp     loc_14004DF17
0x14004e024  movzx   eax, byte ptr [rsi+0Ah]
0x14004e028  lea     rcx, [rsi+4]
0x14004e02c  movzx   r9d, byte ptr [rsi+2]; unsigned int
0x14004e031  mov     rdx, r12; struct DOT11_MAC_STATE_ENTRY *
0x14004e034  mov     r8d, [r13+18h]; enum _DOT11_CIPHER_ALGORITHM
0x14004e038  mov     [rsp+78h+var_40], r15; unsigned __int8 *
0x14004e03d  mov     [rsp+78h+var_48], eax; unsigned int
0x14004e041  mov     [rsp+78h+var_50], rcx; unsigned __int8 *
0x14004e046  mov     rcx, [rsp+78h+arg_8]; struct _VELAN *
0x14004e04e  mov     [rsp+78h+var_58], 0; unsigned __int8 *
0x14004e057  call    ?InstallGroupKey@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_CIPHER_ALGORITHM@@KPEBE3K3@Z; InstallGroupKey(_VELAN *,DOT11_MAC_STATE_ENTRY *,_DOT11_CIPHER_ALGORITHM,ulong,uchar const *,uchar const *,ulong,uchar const *)
0x14004e05c  mov     edi, eax
0x14004e05e  test    eax, eax
0x14004e060  jns     short loc_14004E083
0x14004e062  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e069  lea     r12, WPP_GLOBAL_Control
0x14004e070  cmp     rcx, r12
0x14004e073  jz      loc_14004E212
0x14004e079  mov     edx, 1CFh
0x14004e07e  jmp     loc_14004DF8B
0x14004e083  test    rbp, rbp
0x14004e086  jz      loc_14004E157
0x14004e08c  mov     r8d, ebx; Size
0x14004e08f  xor     edx, edx; Val
0x14004e091  mov     rcx, r15; void *
0x14004e094  call    memset
0x14004e099  mov     ecx, [r13+408h]
0x14004e0a0  lea     r8, [rbp+0Bh]
0x14004e0a4  movzx   r9d, byte ptr [rbp+1]
0x14004e0a9  add     rcx, 414h
0x14004e0b0  mov     edx, [r13+40Ch]
0x14004e0b7  add     rcx, r13
0x14004e0ba  sub     r9d, 9
0x14004e0be  mov     [rsp+78h+var_58], r15
0x14004e0c3  call    AES_UNWRAP
0x14004e0c8  mov     edi, eax
0x14004e0ca  test    eax, eax
0x14004e0cc  jns     short loc_14004E0F8
0x14004e0ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e0d5  lea     r12, WPP_GLOBAL_Control
0x14004e0dc  cmp     rcx, r12
0x14004e0df  jz      loc_14004E212
0x14004e0e5  movzx   eax, byte ptr [rbp+0Ah]
0x14004e0e9  mov     edx, 1D0h
0x14004e0ee  movzx   r9d, byte ptr [rbp+1]
0x14004e0f3  jmp     loc_14004E013
0x14004e0f8  movzx   eax, byte ptr [rbp+0Ah]
0x14004e0fc  lea     rcx, [rbp+4]
0x14004e100  movzx   r9d, byte ptr [rbp+2]; unsigned int
0x14004e105  mov     rdx, r12; struct DOT11_MAC_STATE_ENTRY *
0x14004e108  mov     r8d, [r13+18h]; enum _DOT11_CIPHER_ALGORITHM
0x14004e10c  mov     [rsp+78h+var_40], r15; unsigned __int8 *
0x14004e111  mov     [rsp+78h+var_48], eax; unsigned int
0x14004e115  mov     [rsp+78h+var_50], rcx; unsigned __int8 *
0x14004e11a  mov     rcx, [rsp+78h+arg_8]; struct _VELAN *
0x14004e122  mov     [rsp+78h+var_58], 0; unsigned __int8 *
0x14004e12b  call    ?InstallGroupKey@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_CIPHER_ALGORITHM@@KPEBE3K3@Z; InstallGroupKey(_VELAN *,DOT11_MAC_STATE_ENTRY *,_DOT11_CIPHER_ALGORITHM,ulong,uchar const *,uchar const *,ulong,uchar const *)
0x14004e130  mov     edi, eax
0x14004e132  test    eax, eax
0x14004e134  jns     short loc_14004E157
0x14004e136  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e13d  lea     r12, WPP_GLOBAL_Control
0x14004e144  cmp     rcx, r12
0x14004e147  jz      loc_14004E212
0x14004e14d  mov     edx, 1D1h
0x14004e152  jmp     loc_14004DF8B
0x14004e157  test    cs:byte_1400AF804, 8
0x14004e15e  jz      short loc_14004E1B9
0x14004e160  movzx   eax, byte ptr [r14+4]
0x14004e165  movzx   r9d, byte ptr [r14+2]
0x14004e16a  mov     r8, [rsp+78h+arg_0]
0x14004e172  and     r9d, 3
0x14004e176  mov     [rsp+78h+var_48], eax
0x14004e17a  mov     eax, [r13+14h]
0x14004e17e  mov     dword ptr [rsp+78h+var_58], eax
0x14004e182  call    McTemplateK0qquq_EtwWriteTransfer
0x14004e187  jmp     short loc_14004E1B9
0x14004e189  mov     edi, 0C000009Ah
0x14004e18e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e195  cmp     rcx, r15
0x14004e198  jz      loc_14004E253
0x14004e19e  mov     rcx, [rcx+18h]
0x14004e1a2  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004e1a9  xor     r15d, r15d
0x14004e1ac  mov     edx, 1CBh
0x14004e1b1  mov     r9d, ebx
0x14004e1b4  call    WPP_SF_d
0x14004e1b9  lea     r12, WPP_GLOBAL_Control
0x14004e1c0  mov     r10, cs:WPP_GLOBAL_Control
0x14004e1c7  cmp     r10, r12
0x14004e1ca  jz      short loc_14004E212
0x14004e1cc  test    rbp, rbp
0x14004e1cf  jz      short loc_14004E1D7
0x14004e1d1  movzx   ecx, byte ptr [rbp+0Ah]
0x14004e1d5  jmp     short loc_14004E1D9
0x14004e1d7  xor     ecx, ecx
0x14004e1d9  test    rsi, rsi
0x14004e1dc  jz      short loc_14004E1E4
0x14004e1de  movzx   eax, byte ptr [rsi+0Ah]
0x14004e1e2  jmp     short loc_14004E1E6
0x14004e1e4  xor     eax, eax
0x14004e1e6  test    r14, r14
0x14004e1e9  jz      short loc_14004E1F2
0x14004e1eb  movzx   r9d, byte ptr [r14+4]
0x14004e1f0  jmp     short loc_14004E1F5
0x14004e1f2  xor     r9d, r9d
0x14004e1f5  mov     dword ptr [rsp+78h+var_50], ecx
0x14004e1f9  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004e200  mov     rcx, [r10+18h]
0x14004e204  mov     edx, 1D2h
0x14004e209  mov     dword ptr [rsp+78h+var_58], eax
0x14004e20d  call    WPP_SF_lll
0x14004e212  test    r15, r15
0x14004e215  jz      short loc_14004E253
0x14004e217  mov     r8d, ebx; Size
0x14004e21a  xor     edx, edx; Val
0x14004e21c  mov     rcx, r15; void *
0x14004e21f  call    memset
0x14004e224  lea     rcx, [r15-10h]; P
0x14004e228  mov     rax, [rcx]
0x14004e22b  test    rax, rax
0x14004e22e  jz      short loc_14004E244
0x14004e230  mov     rdx, rcx; Entry
0x14004e233  mov     rcx, rax; Lookaside
0x14004e236  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004e23d  nop     dword ptr [rax+rax+00h]
0x14004e242  jmp     short loc_14004E253
0x14004e244  mov     edx, [rcx+8]; Tag
0x14004e247  call    cs:__imp_ExFreePoolWithTag
0x14004e24e  nop     dword ptr [rax+rax+00h]
0x14004e253  mov     rbx, [rsp+78h+arg_10]
0x14004e25b  mov     eax, edi
0x14004e25d  add     rsp, 40h
0x14004e261  pop     r15
0x14004e263  pop     r14
0x14004e265  pop     r13
0x14004e267  pop     r12
0x14004e269  pop     rdi
0x14004e26a  pop     rsi
0x14004e26b  pop     rbp
0x14004e26c  retn
```
