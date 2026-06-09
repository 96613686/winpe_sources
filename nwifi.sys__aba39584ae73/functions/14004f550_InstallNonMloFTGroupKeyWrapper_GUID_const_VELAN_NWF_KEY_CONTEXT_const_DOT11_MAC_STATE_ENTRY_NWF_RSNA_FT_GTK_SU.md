# InstallNonMloFTGroupKeyWrapper(_GUID const *,_VELAN *,_NWF_KEY_CONTEXT const *,DOT11_MAC_STATE_ENTRY *,NWF_RSNA_FT_GTK_SUB_ELEMENT const *,NWF_RSNA_FT_IGTK_SUB_ELEMENT const *,NWF_RSNA_FT_BIGTK_SUB_ELEMENT const *)

- ea: `0x14004f550`
- end: `0x14004fa2e`
- name: `?InstallNonMloFTGroupKeyWrapper@@YAJPEBU_GUID@@PEAU_VELAN@@PEBU_NWF_KEY_CONTEXT@@PEAUDOT11_MAC_STATE_ENTRY@@PEBUNWF_RSNA_FT_GTK_SUB_ELEMENT@@PEBUNWF_RSNA_FT_IGTK_SUB_ELEMENT@@PEBUNWF_RSNA_FT_BIGTK_SUB_ELEMENT@@@Z`
- size: `1246`
- prototype: `__int64 __fastcall(const struct _GUID *, struct _VELAN *, const struct _NWF_KEY_CONTEXT *, struct DOT11_MAC_STATE_ENTRY *, const struct NWF_RSNA_FT_GTK_SUB_ELEMENT *, const struct NWF_RSNA_FT_IGTK_SUB_ELEMENT *, const struct NWF_RSNA_FT_BIGTK_SUB_ELEMENT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140047e48`

## callees

- `0x14000a898`
- `0x1400208f0`
- `0x140020dc0`
- `0x140030244`
- `0x14004dde0`
- `0x14004f550`
- `0x14008f5e4`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004f63f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004f63f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004f9f6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004f9f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fa07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fa07`

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
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 477, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, a6);
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 478, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v12);
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
      v21 = 480;
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
      v24 = 481;
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
      v21 = 482;
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
        v24 = 483;
        v25 = *((unsigned __int8 *)a7 + 1);
LABEL_30:
        WPP_SF_lll(
          v22->AttachedDevice,
          v24,
          WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
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
      v21 = 484;
    }
LABEL_25:
    WPP_SF_d(v20->AttachedDevice, v21, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, (unsigned int)v17);
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_lll(
      WPP_GLOBAL_Control->AttachedDevice,
      479,
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
        485,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
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
0x14004f550  mov     [rsp+arg_10], rbx
0x14004f555  mov     [rsp+arg_8], rdx
0x14004f55a  mov     [rsp+arg_0], rcx
0x14004f55f  push    rbp
0x14004f560  push    rsi
0x14004f561  push    rdi
0x14004f562  push    r12
0x14004f564  push    r13
0x14004f566  push    r14
0x14004f568  push    r15
0x14004f56a  sub     rsp, 40h
0x14004f56e  mov     r14, [rsp+78h+arg_20]
0x14004f576  lea     r15, WPP_GLOBAL_Control
0x14004f57d  mov     rbp, [rsp+78h+arg_30]
0x14004f585  mov     r12, r9
0x14004f588  mov     r13, r8
0x14004f58b  test    r14, r14
0x14004f58e  jnz     short loc_14004F5CF
0x14004f590  mov     edi, 0C000000Dh
0x14004f595  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f59c  cmp     rcx, r15
0x14004f59f  jz      loc_14004FA13
0x14004f5a5  mov     rsi, [rsp+78h+arg_28]
0x14004f5ad  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004f5b4  mov     rcx, [rcx+18h]
0x14004f5b8  mov     r9, rsi
0x14004f5bb  xor     r15d, r15d
0x14004f5be  xor     ebx, ebx
0x14004f5c0  mov     edx, 1DDh
0x14004f5c5  call    WPP_SF_q
0x14004f5ca  jmp     loc_14004F979
0x14004f5cf  movzx   eax, byte ptr [r14+4]
0x14004f5d4  mov     ebx, 18h
0x14004f5d9  mov     rsi, [rsp+78h+arg_28]
0x14004f5e1  add     eax, 8
0x14004f5e4  cmp     eax, ebx
0x14004f5e6  cmovnb  ebx, eax
0x14004f5e9  test    rsi, rsi
0x14004f5ec  jz      short loc_14004F5FA
0x14004f5ee  movzx   eax, byte ptr [rsi+0Ah]
0x14004f5f2  add     eax, 8
0x14004f5f5  cmp     ebx, eax
0x14004f5f7  cmovbe  ebx, eax
0x14004f5fa  test    rbp, rbp
0x14004f5fd  jz      short loc_14004F60B
0x14004f5ff  movzx   eax, byte ptr [rbp+0Ah]
0x14004f603  add     eax, 8
0x14004f606  cmp     ebx, eax
0x14004f608  cmovbe  ebx, eax
0x14004f60b  lea     eax, [rbx+10h]
0x14004f60e  cmp     eax, 10h
0x14004f611  jb      loc_14004F949
0x14004f617  cmp     eax, 40h ; '@'
0x14004f61a  ja      short loc_14004F625
0x14004f61c  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14004f623  jmp     short loc_14004F63C
0x14004f625  cmp     eax, 100h
0x14004f62a  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004f631  lea     rcx, Lookaside
0x14004f638  cmova   rdi, rcx
0x14004f63c  mov     rcx, rdi; Lookaside
0x14004f63f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004f646  nop     dword ptr [rax+rax+00h]
0x14004f64b  test    rax, rax
0x14004f64e  jz      loc_14004F949
0x14004f654  lea     r15, [rax+10h]
0x14004f658  mov     r8d, ebx; Size
0x14004f65b  mov     rcx, r15; void *
0x14004f65e  mov     [rax], rdi
0x14004f661  xor     edx, edx; Val
0x14004f663  mov     dword ptr [rax+8], 7A697377h
0x14004f66a  call    memset
0x14004f66f  mov     ecx, [r13+408h]
0x14004f676  lea     r8, [r14+0Dh]
0x14004f67a  movzx   r9d, byte ptr [r14+1]
0x14004f67f  add     rcx, 414h
0x14004f686  mov     edx, [r13+40Ch]
0x14004f68d  add     rcx, r13
0x14004f690  sub     r9d, 0Bh
0x14004f694  mov     [rsp+78h+var_58], r15
0x14004f699  call    AES_UNWRAP
0x14004f69e  mov     edi, eax
0x14004f6a0  test    eax, eax
0x14004f6a2  jns     short loc_14004F6EC
0x14004f6a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f6ab  lea     r12, WPP_GLOBAL_Control
0x14004f6b2  cmp     rcx, r12
0x14004f6b5  jz      loc_14004F9D2
0x14004f6bb  movzx   r8d, byte ptr [r14+4]
0x14004f6c0  mov     edx, 1DFh
0x14004f6c5  movzx   r9d, byte ptr [r14+1]
0x14004f6ca  mov     dword ptr [rsp+78h+var_50], eax
0x14004f6ce  sub     r9d, 0Bh
0x14004f6d2  mov     dword ptr [rsp+78h+var_58], r8d
0x14004f6d7  mov     rcx, [rcx+18h]
0x14004f6db  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004f6e2  call    WPP_SF_lll
0x14004f6e7  jmp     loc_14004F980
0x14004f6ec  movzx   eax, byte ptr [r14+4]
0x14004f6f1  lea     rcx, [r14+5]
0x14004f6f5  movzx   r9d, byte ptr [r14+2]
0x14004f6fa  mov     rdx, r12; struct DOT11_MAC_STATE_ENTRY *
0x14004f6fd  mov     r8d, [r13+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004f701  and     r9d, 3; unsigned int
0x14004f705  mov     [rsp+78h+var_40], r15; unsigned __int8 *
0x14004f70a  mov     [rsp+78h+var_48], eax; unsigned int
0x14004f70e  mov     [rsp+78h+var_50], 0; unsigned __int8 *
0x14004f717  mov     [rsp+78h+var_58], rcx; unsigned __int8 *
0x14004f71c  mov     rcx, [rsp+78h+arg_8]; struct _VELAN *
0x14004f724  call    ?InstallGroupKey@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_CIPHER_ALGORITHM@@KPEBE3K3@Z; InstallGroupKey(_VELAN *,DOT11_MAC_STATE_ENTRY *,_DOT11_CIPHER_ALGORITHM,ulong,uchar const *,uchar const *,ulong,uchar const *)
0x14004f729  mov     edi, eax
0x14004f72b  test    eax, eax
0x14004f72d  jns     short loc_14004F763
0x14004f72f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f736  lea     r12, WPP_GLOBAL_Control
0x14004f73d  cmp     rcx, r12
0x14004f740  jz      loc_14004F9D2
0x14004f746  mov     edx, 1E0h
0x14004f74b  mov     rcx, [rcx+18h]
0x14004f74f  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004f756  mov     r9d, eax
0x14004f759  call    WPP_SF_d
0x14004f75e  jmp     loc_14004F980
0x14004f763  test    rsi, rsi
0x14004f766  jz      loc_14004F843
0x14004f76c  mov     r8d, ebx; Size
0x14004f76f  xor     edx, edx; Val
0x14004f771  mov     rcx, r15; void *
0x14004f774  call    memset
0x14004f779  mov     ecx, [r13+408h]
0x14004f780  lea     r8, [rsi+0Bh]
0x14004f784  movzx   r9d, byte ptr [rsi+1]
0x14004f789  add     rcx, 414h
0x14004f790  mov     edx, [r13+40Ch]
0x14004f797  add     rcx, r13
0x14004f79a  sub     r9d, 9
0x14004f79e  mov     [rsp+78h+var_58], r15
0x14004f7a3  call    AES_UNWRAP
0x14004f7a8  mov     edi, eax
0x14004f7aa  test    eax, eax
0x14004f7ac  jns     short loc_14004F7E4
0x14004f7ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f7b5  lea     r12, WPP_GLOBAL_Control
0x14004f7bc  cmp     rcx, r12
0x14004f7bf  jz      loc_14004F9D2
0x14004f7c5  movzx   eax, byte ptr [rsi+0Ah]
0x14004f7c9  mov     edx, 1E1h
0x14004f7ce  movzx   r9d, byte ptr [rsi+1]
0x14004f7d3  mov     dword ptr [rsp+78h+var_50], edi
0x14004f7d7  sub     r9d, 9
0x14004f7db  mov     dword ptr [rsp+78h+var_58], eax
0x14004f7df  jmp     loc_14004F6D7
0x14004f7e4  movzx   eax, byte ptr [rsi+0Ah]
0x14004f7e8  lea     rcx, [rsi+4]
0x14004f7ec  movzx   r9d, byte ptr [rsi+2]; unsigned int
0x14004f7f1  mov     rdx, r12; struct DOT11_MAC_STATE_ENTRY *
0x14004f7f4  mov     r8d, [r13+18h]; enum _DOT11_CIPHER_ALGORITHM
0x14004f7f8  mov     [rsp+78h+var_40], r15; unsigned __int8 *
0x14004f7fd  mov     [rsp+78h+var_48], eax; unsigned int
0x14004f801  mov     [rsp+78h+var_50], rcx; unsigned __int8 *
0x14004f806  mov     rcx, [rsp+78h+arg_8]; struct _VELAN *
0x14004f80e  mov     [rsp+78h+var_58], 0; unsigned __int8 *
0x14004f817  call    ?InstallGroupKey@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_CIPHER_ALGORITHM@@KPEBE3K3@Z; InstallGroupKey(_VELAN *,DOT11_MAC_STATE_ENTRY *,_DOT11_CIPHER_ALGORITHM,ulong,uchar const *,uchar const *,ulong,uchar const *)
0x14004f81c  mov     edi, eax
0x14004f81e  test    eax, eax
0x14004f820  jns     short loc_14004F843
0x14004f822  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f829  lea     r12, WPP_GLOBAL_Control
0x14004f830  cmp     rcx, r12
0x14004f833  jz      loc_14004F9D2
0x14004f839  mov     edx, 1E2h
0x14004f83e  jmp     loc_14004F74B
0x14004f843  test    rbp, rbp
0x14004f846  jz      loc_14004F917
0x14004f84c  mov     r8d, ebx; Size
0x14004f84f  xor     edx, edx; Val
0x14004f851  mov     rcx, r15; void *
0x14004f854  call    memset
0x14004f859  mov     ecx, [r13+408h]
0x14004f860  lea     r8, [rbp+0Bh]
0x14004f864  movzx   r9d, byte ptr [rbp+1]
0x14004f869  add     rcx, 414h
0x14004f870  mov     edx, [r13+40Ch]
0x14004f877  add     rcx, r13
0x14004f87a  sub     r9d, 9
0x14004f87e  mov     [rsp+78h+var_58], r15
0x14004f883  call    AES_UNWRAP
0x14004f888  mov     edi, eax
0x14004f88a  test    eax, eax
0x14004f88c  jns     short loc_14004F8B8
0x14004f88e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f895  lea     r12, WPP_GLOBAL_Control
0x14004f89c  cmp     rcx, r12
0x14004f89f  jz      loc_14004F9D2
0x14004f8a5  movzx   eax, byte ptr [rbp+0Ah]
0x14004f8a9  mov     edx, 1E3h
0x14004f8ae  movzx   r9d, byte ptr [rbp+1]
0x14004f8b3  jmp     loc_14004F7D3
0x14004f8b8  movzx   eax, byte ptr [rbp+0Ah]
0x14004f8bc  lea     rcx, [rbp+4]
0x14004f8c0  movzx   r9d, byte ptr [rbp+2]; unsigned int
0x14004f8c5  mov     rdx, r12; struct DOT11_MAC_STATE_ENTRY *
0x14004f8c8  mov     r8d, [r13+18h]; enum _DOT11_CIPHER_ALGORITHM
0x14004f8cc  mov     [rsp+78h+var_40], r15; unsigned __int8 *
0x14004f8d1  mov     [rsp+78h+var_48], eax; unsigned int
0x14004f8d5  mov     [rsp+78h+var_50], rcx; unsigned __int8 *
0x14004f8da  mov     rcx, [rsp+78h+arg_8]; struct _VELAN *
0x14004f8e2  mov     [rsp+78h+var_58], 0; unsigned __int8 *
0x14004f8eb  call    ?InstallGroupKey@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_CIPHER_ALGORITHM@@KPEBE3K3@Z; InstallGroupKey(_VELAN *,DOT11_MAC_STATE_ENTRY *,_DOT11_CIPHER_ALGORITHM,ulong,uchar const *,uchar const *,ulong,uchar const *)
0x14004f8f0  mov     edi, eax
0x14004f8f2  test    eax, eax
0x14004f8f4  jns     short loc_14004F917
0x14004f8f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f8fd  lea     r12, WPP_GLOBAL_Control
0x14004f904  cmp     rcx, r12
0x14004f907  jz      loc_14004F9D2
0x14004f90d  mov     edx, 1E4h
0x14004f912  jmp     loc_14004F74B
0x14004f917  test    cs:byte_1400B2804, 8
0x14004f91e  jz      short loc_14004F979
0x14004f920  movzx   eax, byte ptr [r14+4]
0x14004f925  movzx   r9d, byte ptr [r14+2]
0x14004f92a  mov     r8, [rsp+78h+arg_0]
0x14004f932  and     r9d, 3
0x14004f936  mov     [rsp+78h+var_48], eax
0x14004f93a  mov     eax, [r13+14h]
0x14004f93e  mov     dword ptr [rsp+78h+var_58], eax
0x14004f942  call    McTemplateK0qquq_EtwWriteTransfer
0x14004f947  jmp     short loc_14004F979
0x14004f949  mov     edi, 0C000009Ah
0x14004f94e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f955  cmp     rcx, r15
0x14004f958  jz      loc_14004FA13
0x14004f95e  mov     rcx, [rcx+18h]
0x14004f962  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004f969  xor     r15d, r15d
0x14004f96c  mov     edx, 1DEh
0x14004f971  mov     r9d, ebx
0x14004f974  call    WPP_SF_d
0x14004f979  lea     r12, WPP_GLOBAL_Control
0x14004f980  mov     r10, cs:WPP_GLOBAL_Control
0x14004f987  cmp     r10, r12
0x14004f98a  jz      short loc_14004F9D2
0x14004f98c  test    rbp, rbp
0x14004f98f  jz      short loc_14004F997
0x14004f991  movzx   ecx, byte ptr [rbp+0Ah]
0x14004f995  jmp     short loc_14004F999
0x14004f997  xor     ecx, ecx
0x14004f999  test    rsi, rsi
0x14004f99c  jz      short loc_14004F9A4
0x14004f99e  movzx   eax, byte ptr [rsi+0Ah]
0x14004f9a2  jmp     short loc_14004F9A6
0x14004f9a4  xor     eax, eax
0x14004f9a6  test    r14, r14
0x14004f9a9  jz      short loc_14004F9B2
0x14004f9ab  movzx   r9d, byte ptr [r14+4]
0x14004f9b0  jmp     short loc_14004F9B5
0x14004f9b2  xor     r9d, r9d
0x14004f9b5  mov     dword ptr [rsp+78h+var_50], ecx
0x14004f9b9  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004f9c0  mov     rcx, [r10+18h]
0x14004f9c4  mov     edx, 1E5h
0x14004f9c9  mov     dword ptr [rsp+78h+var_58], eax
0x14004f9cd  call    WPP_SF_lll
0x14004f9d2  test    r15, r15
0x14004f9d5  jz      short loc_14004FA13
0x14004f9d7  mov     r8d, ebx; Size
0x14004f9da  xor     edx, edx; Val
0x14004f9dc  mov     rcx, r15; void *
0x14004f9df  call    memset
0x14004f9e4  lea     rcx, [r15-10h]; P
0x14004f9e8  mov     rax, [rcx]
0x14004f9eb  test    rax, rax
0x14004f9ee  jz      short loc_14004FA04
0x14004f9f0  mov     rdx, rcx; Entry
0x14004f9f3  mov     rcx, rax; Lookaside
0x14004f9f6  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004f9fd  nop     dword ptr [rax+rax+00h]
0x14004fa02  jmp     short loc_14004FA13
0x14004fa04  mov     edx, [rcx+8]; Tag
0x14004fa07  call    cs:__imp_ExFreePoolWithTag
0x14004fa0e  nop     dword ptr [rax+rax+00h]
0x14004fa13  mov     rbx, [rsp+78h+arg_10]
0x14004fa1b  mov     eax, edi
0x14004fa1d  add     rsp, 40h
0x14004fa21  pop     r15
0x14004fa23  pop     r14
0x14004fa25  pop     r13
0x14004fa27  pop     r12
0x14004fa29  pop     rdi
0x14004fa2a  pop     rsi
0x14004fa2b  pop     rbp
0x14004fa2c  retn
```
