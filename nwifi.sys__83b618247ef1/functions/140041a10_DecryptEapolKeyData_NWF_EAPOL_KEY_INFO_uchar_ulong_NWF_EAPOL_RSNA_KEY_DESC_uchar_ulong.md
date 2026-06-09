# DecryptEapolKeyData(NWF_EAPOL_KEY_INFO *,uchar *,ulong,NWF_EAPOL_RSNA_KEY_DESC *,uchar * *,ulong *)

- ea: `0x140041a10`
- end: `0x140041f5d`
- name: `?DecryptEapolKeyData@@YAJPEAUNWF_EAPOL_KEY_INFO@@PEAEKPEAUNWF_EAPOL_RSNA_KEY_DESC@@PEAPEAEPEAK@Z`
- size: `1357`
- prototype: `__int64 __fastcall(struct NWF_EAPOL_KEY_INFO *, unsigned __int8 *, unsigned int, struct NWF_EAPOL_RSNA_KEY_DESC *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400437a0`
- `0x140044a48`

## callees

- `0x140020cd0`
- `0x140020dc0`
- `0x140041a10`
- `0x14008ddb4`
- `0x14008de04`
- `0x14008e744`
- `0x14009a3d0`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140041b5f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140041bda`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140041d5c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140041b5f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140041bda`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140041d5c`
- `ntoskrnl!ExAllocatePool2` at `0x140041b77`
- `ntoskrnl!ExAllocatePool2` at `0x140041bf5`
- `ntoskrnl!ExAllocatePool2` at `0x140041d74`
- `ntoskrnl!ExAllocatePool2` at `0x140041b77`
- `ntoskrnl!ExAllocatePool2` at `0x140041bf5`
- `ntoskrnl!ExAllocatePool2` at `0x140041d74`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041e78`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041f1d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041e78`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041f1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041e9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041e9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f2e`
- `ksecdd!BCryptDestroyKey` at `0x140041efa`
- `ksecdd!BCryptDestroyKey` at `0x140041efa`

## pseudocode

```c
__int64 __fastcall DecryptEapolKeyData(
        struct NWF_EAPOL_KEY_INFO *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        struct NWF_EAPOL_RSNA_KEY_DESC *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  _OWORD *v6; // r13
  __int64 KeyMaterialLengthOffset; // rax
  __int16 v8; // si
  char *v9; // rax
  unsigned int v10; // esi
  __int64 v11; // r9
  int Rc4Key; // ebx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v17; // rdi
  char *v18; // rax
  __int64 v19; // r9
  unsigned int v20; // eax
  _DWORD *v21; // rax
  const void *v22; // rdx
  unsigned __int8 *v23; // rdi
  unsigned int v24; // ebx
  __int64 v25; // rcx
  struct NWF_EAPOL_RSNA_KEY_DESC *v26; // r12
  unsigned int i; // r15d
  unsigned int v28; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  int v31; // r9d
  int v32; // r8d
  int v33; // edx
  int v34; // ecx
  __int64 v35; // rdx
  bool v36; // cf
  struct NWF_EAPOL_RSNA_KEY_DESC *v38; // [rsp+30h] [rbp-59h] BYREF
  size_t Size; // [rsp+38h] [rbp-51h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+40h] [rbp-49h]
  char *v41; // [rsp+48h] [rbp-41h]
  void *Src[2]; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int8 **v43; // [rsp+60h] [rbp-29h]
  unsigned int *v44; // [rsp+68h] [rbp-21h]
  __int128 v45; // [rsp+70h] [rbp-19h] BYREF

  v6 = 0;
  v43 = a5;
  v44 = a6;
  KeyMaterialLengthOffset = a1->KeyMaterialLengthOffset;
  v38 = a4;
  v45 = 0;
  LODWORD(Size) = a3;
  v8 = *(_WORD *)((char *)a4 + KeyMaterialLengthOffset);
  v9 = (char *)a4 + a1->KeyMaterialOffset;
  LOWORD(v10) = __ROR2__(v8, 8);
  v11 = HIBYTE(*(unsigned __int16 *)((char *)a4 + 1)) & 7;
  Src[0] = a2;
  hKey = 0;
  v41 = v9;
  if ( !(_DWORD)v11 )
    goto LABEL_44;
  if ( (_DWORD)v11 != 1 )
  {
    if ( (unsigned int)(v11 - 2) >= 2 )
    {
      Rc4Key = -1073741811;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v14 = 19;
LABEL_80:
        WPP_SF_d(v13->AttachedDevice, v14, WPP_e90d411d816e312466897e39e745b158_Traceguids, v11);
        goto LABEL_81;
      }
      goto LABEL_81;
    }
LABEL_44:
    if ( (unsigned __int16)v10 < 0x10u || (v10 & 7) != 0 )
    {
      Rc4Key = -1073741811;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v11 = (unsigned __int16)v10;
        v14 = 16;
        goto LABEL_80;
      }
      goto LABEL_81;
    }
    LODWORD(v38) = (unsigned __int16)v10;
    v10 = (unsigned __int16)v10 - 8;
    v28 = v10 + 16;
    if ( v10 + 16 < 0x10 )
      goto LABEL_43;
    if ( v28 > 0x40 )
    {
      if ( v28 > 0x100 )
      {
        if ( v28 > 0x400 )
        {
          if ( v28 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v28, 2053731191, v11);
LABEL_57:
            if ( Pool2 )
            {
              v31 = (int)v38;
              v32 = (int)v41;
              v33 = Size;
              v34 = (int)Src[0];
              Pool2[2] = 2053731191;
              v23 = (unsigned __int8 *)(Pool2 + 4);
              *(_QWORD *)Pool2 = p_WaitListHead;
              Rc4Key = AES_UNWRAP(v34, v33, v32, v31, (__int64)(Pool2 + 4));
              if ( Rc4Key < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    17,
                    WPP_e90d411d816e312466897e39e745b158_Traceguids,
                    (unsigned int)Rc4Key);
LABEL_72:
                if ( v23 )
                {
                  if ( *((_QWORD *)v23 - 2) )
                    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v23 - 2), v23 - 16);
                  else
                    ExFreePoolWithTag(v23 - 16, *((_DWORD *)v23 - 2));
                }
                goto LABEL_81;
              }
              v26 = 0;
LABEL_62:
              v35 = 0;
              v36 = v10 != 0;
              do
              {
                if ( !v36 )
                  goto LABEL_76;
                if ( v23[v35] == 0xDD
                  && (v10 - (_DWORD)v35 == 1 || v10 - (unsigned int)v35 > 1 && !v23[(unsigned int)(v35 + 1)]) )
                {
                  v10 = v35;
LABEL_76:
                  Rc4Key = 0;
                  *v43 = v23;
                  *v44 = v10;
                  goto LABEL_82;
                }
                if ( (int)v35 + 2 > v10 )
                  break;
                v35 = (unsigned int)v23[(unsigned int)(v35 + 1)] + (_DWORD)v35 + 2;
                v36 = (unsigned int)v35 < v10;
              }
              while ( (unsigned int)v35 <= v10 );
              Rc4Key = -1073741823;
              hKey = v26;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  20,
                  WPP_e90d411d816e312466897e39e745b158_Traceguids,
                  3221225473LL);
              goto LABEL_72;
            }
            goto LABEL_43;
          }
          p_WaitListHead = &stru_1400B0180;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_57;
  }
  if ( a3 + 16 >= a3 )
  {
    v15 = a3 + 32;
    if ( a3 + 32 < 0x10 )
      goto LABEL_42;
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    if ( v15 > 0x40 )
    {
      if ( v15 > 0x100 )
      {
        if ( v15 > 0x400 )
        {
          if ( v15 > 0x800 )
          {
            v17 = 0;
            v18 = (char *)ExAllocatePool2(64, v15, 2053731191, v11);
LABEL_20:
            if ( v18 )
            {
              *((_DWORD *)v18 + 2) = 2053731191;
              v6 = v18 + 16;
              v10 = (unsigned __int16)v10;
              *(_QWORD *)v18 = v17;
              v20 = (unsigned __int16)v10 + 16;
              if ( v20 < 0x10 )
                goto LABEL_43;
              if ( v20 > 0x40 )
              {
                if ( v20 > 0x100 )
                {
                  if ( v20 > 0x400 )
                  {
                    if ( v20 > 0x800 )
                    {
                      p_DeviceQueue = 0;
                      v21 = (_DWORD *)ExAllocatePool2(64, v20, 2053731191, v19);
LABEL_31:
                      if ( v21 )
                      {
                        v22 = Src[0];
                        v23 = (unsigned __int8 *)(v21 + 4);
                        *(_QWORD *)v21 = p_DeviceQueue;
                        v24 = Size;
                        v21[2] = 2053731191;
                        *v6 = *(_OWORD *)((char *)v38 + 45);
                        memmove(v6 + 1, v22, v24);
                        v38 = 0;
                        Src[1] = (void *)(v24 + 16);
                        Src[0] = v6;
                        Rc4Key = wlansecurity::crypto::impl::GetRc4KeyHandle<OwnedAlgoStore>(v25, Src, &v38);
                        if ( Rc4Key >= 0 )
                        {
                          v26 = v38;
                          Rc4Key = 0;
                          v38 = 0;
                        }
                        else
                        {
                          v26 = 0;
                        }
                        hKey = v26;
                        wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
                        if ( Rc4Key < 0 )
                          goto LABEL_72;
                        for ( i = 0; i < 0x10; ++i )
                        {
                          Rc4Key = Decrypt((_DWORD)v26, (unsigned int)&v45, 16, (unsigned int)&v45, 16);
                          if ( Rc4Key < 0 )
                            goto LABEL_72;
                        }
                        Rc4Key = Decrypt(
                                   (_DWORD)v26,
                                   (_DWORD)v41,
                                   (unsigned __int16)v10,
                                   (_DWORD)v23,
                                   (unsigned __int16)v10);
                        if ( Rc4Key < 0 )
                          goto LABEL_72;
                        goto LABEL_62;
                      }
LABEL_43:
                      Rc4Key = -1073741670;
                      goto LABEL_81;
                    }
                    p_DeviceQueue = &stru_1400B0180;
                  }
                  else
                  {
                    p_DeviceQueue = &Lookaside;
                  }
                }
                else
                {
                  p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
                }
              }
              v21 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
              goto LABEL_31;
            }
LABEL_42:
            v6 = 0;
            goto LABEL_43;
          }
          v17 = &stru_1400B0180;
        }
        else
        {
          v17 = &Lookaside;
        }
      }
      else
      {
        v17 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v17 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v18 = (char *)ExAllocateFromNPagedLookasideList(v17);
    goto LABEL_20;
  }
  Rc4Key = -1073741811;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v14 = 18;
    v11 = a3;
    goto LABEL_80;
  }
LABEL_81:
  *v43 = 0;
  *v44 = 0;
LABEL_82:
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v6 )
  {
    if ( *((_QWORD *)v6 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v6 - 2), v6 - 1);
    else
      ExFreePoolWithTag(v6 - 1, *((_DWORD *)v6 - 2));
  }
  return (unsigned int)Rc4Key;
}

```

## disassembly

```asm
0x140041a10  push    rbp
0x140041a12  push    rbx
0x140041a13  push    rsi
0x140041a14  push    rdi
0x140041a15  push    r12
0x140041a17  push    r13
0x140041a19  push    r14
0x140041a1b  push    r15
0x140041a1d  lea     rbp, [rsp-0Fh]
0x140041a22  sub     rsp, 98h
0x140041a29  mov     rax, cs:__security_cookie
0x140041a30  xor     rax, rsp
0x140041a33  mov     [rbp+47h+var_50], rax
0x140041a37  mov     rax, [rbp+47h+arg_20]
0x140041a3b  xor     r13d, r13d
0x140041a3e  mov     [rbp+47h+var_70], rax
0x140041a42  xorps   xmm0, xmm0
0x140041a45  mov     rax, [rbp+47h+arg_28]
0x140041a49  mov     [rbp+47h+var_68], rax
0x140041a4d  movzx   eax, word ptr [rcx+18h]
0x140041a51  mov     [rbp+47h+var_A0], r9
0x140041a55  movups  [rbp+47h+var_60], xmm0
0x140041a59  mov     dword ptr [rbp+47h+Size], r8d
0x140041a5d  movzx   esi, word ptr [rax+r9]
0x140041a62  movzx   eax, word ptr [rcx+1Ah]
0x140041a66  add     rax, r9
0x140041a69  ror     si, 8
0x140041a6d  movzx   r9d, word ptr [r9+1]
0x140041a72  shr     r9d, 8
0x140041a76  and     r9d, 7
0x140041a7a  mov     [rbp+47h+Src], rdx
0x140041a7e  mov     ecx, r9d
0x140041a81  mov     [rbp+47h+hKey], r13
0x140041a85  mov     [rbp+47h+var_88], rax
0x140041a89  jz      loc_140041CE5
0x140041a8f  sub     ecx, 1
0x140041a92  jz      short loc_140041ACB
0x140041a94  sub     ecx, 1
0x140041a97  jz      loc_140041CE5
0x140041a9d  cmp     ecx, 1
0x140041aa0  jz      loc_140041CE5
0x140041aa6  mov     ebx, 0C000000Dh
0x140041aab  mov     rcx, cs:WPP_GLOBAL_Control
0x140041ab2  lea     rax, WPP_GLOBAL_Control
0x140041ab9  cmp     rcx, rax
0x140041abc  jz      loc_140041ED9
0x140041ac2  lea     edx, [r13+13h]
0x140041ac6  jmp     loc_140041EC9
0x140041acb  lea     eax, [r8+10h]
0x140041acf  cmp     eax, r8d
0x140041ad2  jnb     short loc_140041AFD
0x140041ad4  mov     ebx, 0C000000Dh
0x140041ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x140041ae0  lea     rax, WPP_GLOBAL_Control
0x140041ae7  cmp     rcx, rax
0x140041aea  jz      loc_140041ED9
0x140041af0  mov     edx, 12h
0x140041af5  mov     r9d, r8d
0x140041af8  jmp     loc_140041EC9
0x140041afd  add     eax, 10h
0x140041b00  mov     r14d, 10h
0x140041b06  cmp     eax, r14d
0x140041b09  jb      loc_140041CD8
0x140041b0f  lea     r15d, [r14+30h]
0x140041b13  mov     r13d, 7A697377h
0x140041b19  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140041b20  mov     r12d, 100h
0x140041b26  cmp     eax, r15d
0x140041b29  ja      short loc_140041B30
0x140041b2b  mov     rdi, rbx
0x140041b2e  jmp     short loc_140041B5C
0x140041b30  cmp     eax, r12d
0x140041b33  ja      short loc_140041B3E
0x140041b35  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140041b3c  jmp     short loc_140041B5C
0x140041b3e  cmp     eax, 400h
0x140041b43  ja      short loc_140041B4E
0x140041b45  lea     rdi, Lookaside
0x140041b4c  jmp     short loc_140041B5C
0x140041b4e  cmp     eax, 800h
0x140041b53  ja      short loc_140041B6D
0x140041b55  lea     rdi, stru_1400B0180
0x140041b5c  mov     rcx, rdi; Lookaside
0x140041b5f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140041b66  nop     dword ptr [rax+rax+00h]
0x140041b6b  jmp     short loc_140041B83
0x140041b6d  xor     edi, edi
0x140041b6f  mov     edx, eax
0x140041b71  mov     r8d, r13d
0x140041b74  mov     rcx, r15
0x140041b77  call    cs:__imp_ExAllocatePool2
0x140041b7e  nop     dword ptr [rax+rax+00h]
0x140041b83  test    rax, rax
0x140041b86  jz      loc_140041CD8
0x140041b8c  mov     [rax+8], r13d
0x140041b90  lea     r13, [rax+10h]
0x140041b94  movzx   esi, si
0x140041b97  mov     [rax], rdi
0x140041b9a  lea     eax, [rsi+10h]
0x140041b9d  cmp     eax, r14d
0x140041ba0  jb      loc_140041CDB
0x140041ba6  cmp     eax, r15d
0x140041ba9  jbe     short loc_140041BD7
0x140041bab  cmp     eax, r12d
0x140041bae  ja      short loc_140041BB9
0x140041bb0  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140041bb7  jmp     short loc_140041BD7
0x140041bb9  cmp     eax, 400h
0x140041bbe  ja      short loc_140041BC9
0x140041bc0  lea     rbx, Lookaside
0x140041bc7  jmp     short loc_140041BD7
0x140041bc9  cmp     eax, 800h
0x140041bce  ja      short loc_140041BE8
0x140041bd0  lea     rbx, stru_1400B0180
0x140041bd7  mov     rcx, rbx; Lookaside
0x140041bda  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140041be1  nop     dword ptr [rax+rax+00h]
0x140041be6  jmp     short loc_140041C01
0x140041be8  xor     ebx, ebx
0x140041bea  mov     edx, eax
0x140041bec  mov     r8d, 7A697377h
0x140041bf2  mov     rcx, r15
0x140041bf5  call    cs:__imp_ExAllocatePool2
0x140041bfc  nop     dword ptr [rax+rax+00h]
0x140041c01  test    rax, rax
0x140041c04  jz      loc_140041CDB
0x140041c0a  mov     rdx, [rbp+47h+Src]; Src
0x140041c0e  lea     rdi, [rax+10h]
0x140041c12  mov     [rax], rbx
0x140041c15  lea     rcx, [r13+10h]; void *
0x140041c19  mov     ebx, dword ptr [rbp+47h+Size]
0x140041c1c  mov     dword ptr [rax+8], 7A697377h
0x140041c23  mov     r8d, ebx; Size
0x140041c26  mov     rax, [rbp+47h+var_A0]
0x140041c2a  movups  xmm0, xmmword ptr [rax+2Dh]
0x140041c2e  movdqu  xmmword ptr [r13+0], xmm0
0x140041c34  call    memmove
0x140041c39  lea     eax, [rbx+10h]
0x140041c3c  mov     [rbp+47h+var_A0], 0
0x140041c44  lea     r8, [rbp+47h+var_A0]
0x140041c48  mov     [rbp+47h+var_78], rax
0x140041c4c  lea     rdx, [rbp+47h+Src]
0x140041c50  mov     [rbp+47h+Src], r13
0x140041c54  call    ??$GetRc4KeyHandle@VOwnedAlgoStore@@@impl@crypto@wlansecurity@@YAJAEBVOwnedAlgoStore@@V?$span@$$CBE$0?0@utl@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; wlansecurity::crypto::impl::GetRc4KeyHandle<OwnedAlgoStore>(OwnedAlgoStore const &,utl::span<uchar const,-1>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x140041c59  mov     ebx, eax
0x140041c5b  test    eax, eax
0x140041c5d  jns     short loc_140041C64
0x140041c5f  xor     r12d, r12d
0x140041c62  jmp     short loc_140041C72
0x140041c64  mov     r12, [rbp+47h+var_A0]
0x140041c68  xor     ebx, ebx
0x140041c6a  mov     [rbp+47h+var_A0], 0
0x140041c72  lea     rcx, [rbp+47h+var_A0]
0x140041c76  mov     [rbp+47h+hKey], r12
0x140041c7a  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140041c7f  test    ebx, ebx
0x140041c81  js      loc_140041E61
0x140041c87  xor     r15d, r15d
0x140041c8a  mov     rcx, r12
0x140041c8d  cmp     r15d, r14d
0x140041c90  jnb     short loc_140041CB6
0x140041c92  lea     r9, [rbp+47h+var_60]
0x140041c96  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x140041c9b  mov     r8d, r14d
0x140041c9e  lea     rdx, [rbp+47h+var_60]
0x140041ca2  call    Decrypt
0x140041ca7  mov     ebx, eax
0x140041ca9  test    eax, eax
0x140041cab  js      loc_140041E61
0x140041cb1  inc     r15d
0x140041cb4  jmp     short loc_140041C8A
0x140041cb6  mov     rdx, [rbp+47h+var_88]
0x140041cba  mov     r9, rdi
0x140041cbd  mov     r8d, esi
0x140041cc0  mov     dword ptr [rsp+0D0h+var_B0], esi
0x140041cc4  call    Decrypt
0x140041cc9  mov     ebx, eax
0x140041ccb  test    eax, eax
0x140041ccd  js      loc_140041E61
0x140041cd3  jmp     loc_140041DE6
0x140041cd8  xor     r13d, r13d
0x140041cdb  mov     ebx, 0C000009Ah
0x140041ce0  jmp     loc_140041ED9
0x140041ce5  mov     r14d, 10h
0x140041ceb  cmp     si, r14w
0x140041cef  jb      loc_140041EAA
0x140041cf5  test    sil, 7
0x140041cf9  jnz     loc_140041EAA
0x140041cff  movzx   eax, si
0x140041d02  mov     dword ptr [rbp+47h+var_A0], eax
0x140041d05  lea     esi, [rax-8]
0x140041d08  lea     eax, [rsi+10h]
0x140041d0b  cmp     eax, r14d
0x140041d0e  jb      short loc_140041CDB
0x140041d10  lea     r15d, [r14+30h]
0x140041d14  mov     edi, 7A697377h
0x140041d19  cmp     eax, r15d
0x140041d1c  ja      short loc_140041D27
0x140041d1e  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140041d25  jmp     short loc_140041D59
0x140041d27  mov     r12d, 100h
0x140041d2d  cmp     eax, r12d
0x140041d30  ja      short loc_140041D3B
0x140041d32  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140041d39  jmp     short loc_140041D59
0x140041d3b  cmp     eax, 400h
0x140041d40  ja      short loc_140041D4B
0x140041d42  lea     rbx, Lookaside
0x140041d49  jmp     short loc_140041D59
0x140041d4b  cmp     eax, 800h
0x140041d50  ja      short loc_140041D6A
0x140041d52  lea     rbx, stru_1400B0180
0x140041d59  mov     rcx, rbx; Lookaside
0x140041d5c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140041d63  nop     dword ptr [rax+rax+00h]
0x140041d68  jmp     short loc_140041D80
0x140041d6a  xor     ebx, ebx
0x140041d6c  mov     edx, eax
0x140041d6e  mov     r8d, edi
0x140041d71  mov     rcx, r15
0x140041d74  call    cs:__imp_ExAllocatePool2
0x140041d7b  nop     dword ptr [rax+rax+00h]
0x140041d80  test    rax, rax
0x140041d83  jz      loc_140041CDB
0x140041d89  mov     r9d, dword ptr [rbp+47h+var_A0]
0x140041d8d  mov     r8, [rbp+47h+var_88]
0x140041d91  mov     edx, dword ptr [rbp+47h+Size]
0x140041d94  mov     rcx, [rbp+47h+Src]
0x140041d98  mov     [rax+8], edi
0x140041d9b  lea     rdi, [rax+10h]
0x140041d9f  mov     [rsp+0D0h+var_B0], rdi
0x140041da4  mov     [rax], rbx
0x140041da7  call    AES_UNWRAP
0x140041dac  mov     ebx, eax
0x140041dae  test    eax, eax
0x140041db0  jns     short loc_140041DE3
0x140041db2  mov     rcx, cs:WPP_GLOBAL_Control
0x140041db9  lea     rax, WPP_GLOBAL_Control
0x140041dc0  cmp     rcx, rax
0x140041dc3  jz      loc_140041E61
0x140041dc9  mov     rcx, [rcx+18h]
0x140041dcd  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140041dd4  mov     edx, 11h
0x140041dd9  mov     r9d, ebx
0x140041ddc  call    WPP_SF_d
0x140041de1  jmp     short loc_140041E61
0x140041de3  mov     r12, r13
0x140041de6  xor     edx, edx
0x140041de8  cmp     edx, esi
0x140041dea  jnb     loc_140041E88
0x140041df0  cmp     byte ptr [rdx+rdi], 0DDh
0x140041df4  jnz     short loc_140041E0E
0x140041df6  mov     eax, esi
0x140041df8  sub     eax, edx
0x140041dfa  cmp     eax, 1
0x140041dfd  jz      loc_140041E86
0x140041e03  jbe     short loc_140041E0E
0x140041e05  lea     eax, [rdx+1]
0x140041e08  cmp     byte ptr [rax+rdi], 0
0x140041e0c  jz      short loc_140041E86
0x140041e0e  lea     eax, [rdx+2]
0x140041e11  cmp     eax, esi
0x140041e13  ja      short loc_140041E25
0x140041e15  lea     eax, [rdx+1]
0x140041e18  add     edx, 2
0x140041e1b  movzx   eax, byte ptr [rax+rdi]
0x140041e1f  add     edx, eax
0x140041e21  cmp     edx, esi
0x140041e23  jbe     short loc_140041DEA
0x140041e25  mov     ebx, 0C0000001h
0x140041e2a  mov     [rbp+47h+hKey], r12
0x140041e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140041e35  lea     rax, WPP_GLOBAL_Control
0x140041e3c  cmp     rcx, rax
0x140041e3f  jz      short loc_140041E59
0x140041e41  mov     rcx, [rcx+18h]
0x140041e45  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140041e4c  mov     edx, 14h
0x140041e51  mov     r9d, ebx
0x140041e54  call    WPP_SF_d
0x140041e59  test    ebx, ebx
0x140041e5b  jns     loc_140041EEE
0x140041e61  test    rdi, rdi
0x140041e64  jz      short loc_140041ED9
0x140041e66  lea     rcx, [rdi-10h]; P
0x140041e6a  mov     rax, [rcx]
0x140041e6d  test    rax, rax
0x140041e70  jz      short loc_140041E99
0x140041e72  mov     rdx, rcx; Entry
0x140041e75  mov     rcx, rax; Lookaside
0x140041e78  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041e7f  nop     dword ptr [rax+rax+00h]
0x140041e84  jmp     short loc_140041ED9
0x140041e86  mov     esi, edx
0x140041e88  mov     rax, [rbp+47h+var_70]
0x140041e8c  xor     ebx, ebx
0x140041e8e  mov     [rax], rdi
0x140041e91  mov     rax, [rbp+47h+var_68]
0x140041e95  mov     [rax], esi
0x140041e97  jmp     short loc_140041EEE
  ... truncated ...
```
