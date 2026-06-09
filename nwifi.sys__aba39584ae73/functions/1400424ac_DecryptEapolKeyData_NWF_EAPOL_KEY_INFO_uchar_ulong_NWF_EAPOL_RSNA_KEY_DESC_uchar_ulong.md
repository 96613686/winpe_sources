# DecryptEapolKeyData(NWF_EAPOL_KEY_INFO *,uchar *,ulong,NWF_EAPOL_RSNA_KEY_DESC *,uchar * *,ulong *)

- ea: `0x1400424ac`
- end: `0x1400429f9`
- name: `?DecryptEapolKeyData@@YAJPEAUNWF_EAPOL_KEY_INFO@@PEAEKPEAUNWF_EAPOL_RSNA_KEY_DESC@@PEAPEAEPEAK@Z`
- size: `1357`
- prototype: `__int64 __fastcall(struct NWF_EAPOL_KEY_INFO *, unsigned __int8 *, unsigned int, struct NWF_EAPOL_RSNA_KEY_DESC *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140044320`
- `0x1400455c8`

## callees

- `0x140020cd0`
- `0x140020dc0`
- `0x1400424ac`
- `0x14008f5e4`
- `0x14008f634`
- `0x14008ff24`
- `0x14009bbb0`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400425fb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140042676`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400427f8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400425fb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140042676`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400427f8`
- `ntoskrnl!ExAllocatePool2` at `0x140042613`
- `ntoskrnl!ExAllocatePool2` at `0x140042691`
- `ntoskrnl!ExAllocatePool2` at `0x140042810`
- `ntoskrnl!ExAllocatePool2` at `0x140042613`
- `ntoskrnl!ExAllocatePool2` at `0x140042691`
- `ntoskrnl!ExAllocatePool2` at `0x140042810`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140042914`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400429b9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140042914`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400429b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042938`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400429ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042938`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400429ca`
- `ksecdd!BCryptDestroyKey` at `0x140042996`
- `ksecdd!BCryptDestroyKey` at `0x140042996`

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
  unsigned int v19; // eax
  _DWORD *v20; // rax
  const void *v21; // rdx
  unsigned __int8 *v22; // rdi
  unsigned int v23; // ebx
  __int64 v24; // rcx
  struct NWF_EAPOL_RSNA_KEY_DESC *v25; // r12
  unsigned int i; // r15d
  unsigned int v27; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  int v30; // r9d
  int v31; // r8d
  int v32; // edx
  int v33; // ecx
  __int64 v34; // rdx
  bool v35; // cf
  struct NWF_EAPOL_RSNA_KEY_DESC *v37; // [rsp+30h] [rbp-59h] BYREF
  size_t Size; // [rsp+38h] [rbp-51h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+40h] [rbp-49h]
  char *v40; // [rsp+48h] [rbp-41h]
  void *Src[2]; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int8 **v42; // [rsp+60h] [rbp-29h]
  unsigned int *v43; // [rsp+68h] [rbp-21h]
  __int128 v44; // [rsp+70h] [rbp-19h] BYREF

  v6 = 0;
  v42 = a5;
  v43 = a6;
  KeyMaterialLengthOffset = a1->KeyMaterialLengthOffset;
  v37 = a4;
  v44 = 0;
  LODWORD(Size) = a3;
  v8 = *(_WORD *)((char *)a4 + KeyMaterialLengthOffset);
  v9 = (char *)a4 + a1->KeyMaterialOffset;
  LOWORD(v10) = __ROR2__(v8, 8);
  v11 = HIBYTE(*(unsigned __int16 *)((char *)a4 + 1)) & 7;
  Src[0] = a2;
  hKey = 0;
  v40 = v9;
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
        WPP_SF_d(v13->AttachedDevice, v14, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v11);
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
    LODWORD(v37) = (unsigned __int16)v10;
    v10 = (unsigned __int16)v10 - 8;
    v27 = v10 + 16;
    if ( v10 + 16 < 0x10 )
      goto LABEL_43;
    if ( v27 > 0x40 )
    {
      if ( v27 > 0x100 )
      {
        if ( v27 > 0x400 )
        {
          if ( v27 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v27, 2053731191);
LABEL_57:
            if ( Pool2 )
            {
              v30 = (int)v37;
              v31 = (int)v40;
              v32 = Size;
              v33 = (int)Src[0];
              Pool2[2] = 2053731191;
              v22 = (unsigned __int8 *)(Pool2 + 4);
              *(_QWORD *)Pool2 = p_WaitListHead;
              Rc4Key = AES_UNWRAP(v33, v32, v31, v30, (__int64)(Pool2 + 4));
              if ( Rc4Key < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    17,
                    WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                    (unsigned int)Rc4Key);
LABEL_72:
                if ( v22 )
                {
                  if ( *((_QWORD *)v22 - 2) )
                    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v22 - 2), v22 - 16);
                  else
                    ExFreePoolWithTag(v22 - 16, *((_DWORD *)v22 - 2));
                }
                goto LABEL_81;
              }
              v25 = 0;
LABEL_62:
              v34 = 0;
              v35 = v10 != 0;
              do
              {
                if ( !v35 )
                  goto LABEL_76;
                if ( v22[v34] == 0xDD
                  && (v10 - (_DWORD)v34 == 1 || v10 - (unsigned int)v34 > 1 && !v22[(unsigned int)(v34 + 1)]) )
                {
                  v10 = v34;
LABEL_76:
                  Rc4Key = 0;
                  *v42 = v22;
                  *v43 = v10;
                  goto LABEL_82;
                }
                if ( (int)v34 + 2 > v10 )
                  break;
                v34 = (unsigned int)v22[(unsigned int)(v34 + 1)] + (_DWORD)v34 + 2;
                v35 = (unsigned int)v34 < v10;
              }
              while ( (unsigned int)v34 <= v10 );
              Rc4Key = -1073741823;
              hKey = v25;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  20,
                  WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                  3221225473LL);
              goto LABEL_72;
            }
            goto LABEL_43;
          }
          p_WaitListHead = &stru_1400B31C0;
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
            v18 = (char *)ExAllocatePool2(64, v15, 2053731191);
LABEL_20:
            if ( v18 )
            {
              *((_DWORD *)v18 + 2) = 2053731191;
              v6 = v18 + 16;
              v10 = (unsigned __int16)v10;
              *(_QWORD *)v18 = v17;
              v19 = (unsigned __int16)v10 + 16;
              if ( v19 < 0x10 )
                goto LABEL_43;
              if ( v19 > 0x40 )
              {
                if ( v19 > 0x100 )
                {
                  if ( v19 > 0x400 )
                  {
                    if ( v19 > 0x800 )
                    {
                      p_DeviceQueue = 0;
                      v20 = (_DWORD *)ExAllocatePool2(64, v19, 2053731191);
LABEL_31:
                      if ( v20 )
                      {
                        v21 = Src[0];
                        v22 = (unsigned __int8 *)(v20 + 4);
                        *(_QWORD *)v20 = p_DeviceQueue;
                        v23 = Size;
                        v20[2] = 2053731191;
                        *v6 = *(_OWORD *)((char *)v37 + 45);
                        memmove(v6 + 1, v21, v23);
                        v37 = 0;
                        Src[1] = (void *)(v23 + 16);
                        Src[0] = v6;
                        Rc4Key = wlansecurity::crypto::impl::GetRc4KeyHandle<OwnedAlgoStore>(v24, Src, &v37);
                        if ( Rc4Key >= 0 )
                        {
                          v25 = v37;
                          Rc4Key = 0;
                          v37 = 0;
                        }
                        else
                        {
                          v25 = 0;
                        }
                        hKey = v25;
                        wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
                        if ( Rc4Key < 0 )
                          goto LABEL_72;
                        for ( i = 0; i < 0x10; ++i )
                        {
                          Rc4Key = Decrypt((_DWORD)v25, (unsigned int)&v44, 16, (unsigned int)&v44, 16);
                          if ( Rc4Key < 0 )
                            goto LABEL_72;
                        }
                        Rc4Key = Decrypt(
                                   (_DWORD)v25,
                                   (_DWORD)v40,
                                   (unsigned __int16)v10,
                                   (_DWORD)v22,
                                   (unsigned __int16)v10);
                        if ( Rc4Key < 0 )
                          goto LABEL_72;
                        goto LABEL_62;
                      }
LABEL_43:
                      Rc4Key = -1073741670;
                      goto LABEL_81;
                    }
                    p_DeviceQueue = &stru_1400B31C0;
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
              v20 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
              goto LABEL_31;
            }
LABEL_42:
            v6 = 0;
            goto LABEL_43;
          }
          v17 = &stru_1400B31C0;
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
  *v42 = 0;
  *v43 = 0;
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
0x1400424ac  push    rbp
0x1400424ae  push    rbx
0x1400424af  push    rsi
0x1400424b0  push    rdi
0x1400424b1  push    r12
0x1400424b3  push    r13
0x1400424b5  push    r14
0x1400424b7  push    r15
0x1400424b9  lea     rbp, [rsp-0Fh]
0x1400424be  sub     rsp, 98h
0x1400424c5  mov     rax, cs:__security_cookie
0x1400424cc  xor     rax, rsp
0x1400424cf  mov     [rbp+47h+var_50], rax
0x1400424d3  mov     rax, [rbp+47h+arg_20]
0x1400424d7  xor     r13d, r13d
0x1400424da  mov     [rbp+47h+var_70], rax
0x1400424de  xorps   xmm0, xmm0
0x1400424e1  mov     rax, [rbp+47h+arg_28]
0x1400424e5  mov     [rbp+47h+var_68], rax
0x1400424e9  movzx   eax, word ptr [rcx+18h]
0x1400424ed  mov     [rbp+47h+var_A0], r9
0x1400424f1  movups  [rbp+47h+var_60], xmm0
0x1400424f5  mov     dword ptr [rbp+47h+Size], r8d
0x1400424f9  movzx   esi, word ptr [rax+r9]
0x1400424fe  movzx   eax, word ptr [rcx+1Ah]
0x140042502  add     rax, r9
0x140042505  ror     si, 8
0x140042509  movzx   r9d, word ptr [r9+1]
0x14004250e  shr     r9d, 8
0x140042512  and     r9d, 7
0x140042516  mov     [rbp+47h+Src], rdx
0x14004251a  mov     ecx, r9d
0x14004251d  mov     [rbp+47h+hKey], r13
0x140042521  mov     [rbp+47h+var_88], rax
0x140042525  jz      loc_140042781
0x14004252b  sub     ecx, 1
0x14004252e  jz      short loc_140042567
0x140042530  sub     ecx, 1
0x140042533  jz      loc_140042781
0x140042539  cmp     ecx, 1
0x14004253c  jz      loc_140042781
0x140042542  mov     ebx, 0C000000Dh
0x140042547  mov     rcx, cs:WPP_GLOBAL_Control
0x14004254e  lea     rax, WPP_GLOBAL_Control
0x140042555  cmp     rcx, rax
0x140042558  jz      loc_140042975
0x14004255e  lea     edx, [r13+13h]
0x140042562  jmp     loc_140042965
0x140042567  lea     eax, [r8+10h]
0x14004256b  cmp     eax, r8d
0x14004256e  jnb     short loc_140042599
0x140042570  mov     ebx, 0C000000Dh
0x140042575  mov     rcx, cs:WPP_GLOBAL_Control
0x14004257c  lea     rax, WPP_GLOBAL_Control
0x140042583  cmp     rcx, rax
0x140042586  jz      loc_140042975
0x14004258c  mov     edx, 12h
0x140042591  mov     r9d, r8d
0x140042594  jmp     loc_140042965
0x140042599  add     eax, 10h
0x14004259c  mov     r14d, 10h
0x1400425a2  cmp     eax, r14d
0x1400425a5  jb      loc_140042774
0x1400425ab  lea     r15d, [r14+30h]
0x1400425af  mov     r13d, 7A697377h
0x1400425b5  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400425bc  mov     r12d, 100h
0x1400425c2  cmp     eax, r15d
0x1400425c5  ja      short loc_1400425CC
0x1400425c7  mov     rdi, rbx
0x1400425ca  jmp     short loc_1400425F8
0x1400425cc  cmp     eax, r12d
0x1400425cf  ja      short loc_1400425DA
0x1400425d1  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400425d8  jmp     short loc_1400425F8
0x1400425da  cmp     eax, 400h
0x1400425df  ja      short loc_1400425EA
0x1400425e1  lea     rdi, Lookaside
0x1400425e8  jmp     short loc_1400425F8
0x1400425ea  cmp     eax, 800h
0x1400425ef  ja      short loc_140042609
0x1400425f1  lea     rdi, stru_1400B31C0
0x1400425f8  mov     rcx, rdi; Lookaside
0x1400425fb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140042602  nop     dword ptr [rax+rax+00h]
0x140042607  jmp     short loc_14004261F
0x140042609  xor     edi, edi
0x14004260b  mov     edx, eax
0x14004260d  mov     r8d, r13d
0x140042610  mov     rcx, r15
0x140042613  call    cs:__imp_ExAllocatePool2
0x14004261a  nop     dword ptr [rax+rax+00h]
0x14004261f  test    rax, rax
0x140042622  jz      loc_140042774
0x140042628  mov     [rax+8], r13d
0x14004262c  lea     r13, [rax+10h]
0x140042630  movzx   esi, si
0x140042633  mov     [rax], rdi
0x140042636  lea     eax, [rsi+10h]
0x140042639  cmp     eax, r14d
0x14004263c  jb      loc_140042777
0x140042642  cmp     eax, r15d
0x140042645  jbe     short loc_140042673
0x140042647  cmp     eax, r12d
0x14004264a  ja      short loc_140042655
0x14004264c  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140042653  jmp     short loc_140042673
0x140042655  cmp     eax, 400h
0x14004265a  ja      short loc_140042665
0x14004265c  lea     rbx, Lookaside
0x140042663  jmp     short loc_140042673
0x140042665  cmp     eax, 800h
0x14004266a  ja      short loc_140042684
0x14004266c  lea     rbx, stru_1400B31C0
0x140042673  mov     rcx, rbx; Lookaside
0x140042676  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004267d  nop     dword ptr [rax+rax+00h]
0x140042682  jmp     short loc_14004269D
0x140042684  xor     ebx, ebx
0x140042686  mov     edx, eax
0x140042688  mov     r8d, 7A697377h
0x14004268e  mov     rcx, r15
0x140042691  call    cs:__imp_ExAllocatePool2
0x140042698  nop     dword ptr [rax+rax+00h]
0x14004269d  test    rax, rax
0x1400426a0  jz      loc_140042777
0x1400426a6  mov     rdx, [rbp+47h+Src]; Src
0x1400426aa  lea     rdi, [rax+10h]
0x1400426ae  mov     [rax], rbx
0x1400426b1  lea     rcx, [r13+10h]; void *
0x1400426b5  mov     ebx, dword ptr [rbp+47h+Size]
0x1400426b8  mov     dword ptr [rax+8], 7A697377h
0x1400426bf  mov     r8d, ebx; Size
0x1400426c2  mov     rax, [rbp+47h+var_A0]
0x1400426c6  movups  xmm0, xmmword ptr [rax+2Dh]
0x1400426ca  movdqu  xmmword ptr [r13+0], xmm0
0x1400426d0  call    memmove
0x1400426d5  lea     eax, [rbx+10h]
0x1400426d8  mov     [rbp+47h+var_A0], 0
0x1400426e0  lea     r8, [rbp+47h+var_A0]
0x1400426e4  mov     [rbp+47h+var_78], rax
0x1400426e8  lea     rdx, [rbp+47h+Src]
0x1400426ec  mov     [rbp+47h+Src], r13
0x1400426f0  call    ??$GetRc4KeyHandle@VOwnedAlgoStore@@@impl@crypto@wlansecurity@@YAJAEBVOwnedAlgoStore@@V?$span@$$CBE$0?0@utl@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; wlansecurity::crypto::impl::GetRc4KeyHandle<OwnedAlgoStore>(OwnedAlgoStore const &,utl::span<uchar const,-1>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x1400426f5  mov     ebx, eax
0x1400426f7  test    eax, eax
0x1400426f9  jns     short loc_140042700
0x1400426fb  xor     r12d, r12d
0x1400426fe  jmp     short loc_14004270E
0x140042700  mov     r12, [rbp+47h+var_A0]
0x140042704  xor     ebx, ebx
0x140042706  mov     [rbp+47h+var_A0], 0
0x14004270e  lea     rcx, [rbp+47h+var_A0]
0x140042712  mov     [rbp+47h+hKey], r12
0x140042716  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14004271b  test    ebx, ebx
0x14004271d  js      loc_1400428FD
0x140042723  xor     r15d, r15d
0x140042726  mov     rcx, r12
0x140042729  cmp     r15d, r14d
0x14004272c  jnb     short loc_140042752
0x14004272e  lea     r9, [rbp+47h+var_60]
0x140042732  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x140042737  mov     r8d, r14d
0x14004273a  lea     rdx, [rbp+47h+var_60]
0x14004273e  call    Decrypt
0x140042743  mov     ebx, eax
0x140042745  test    eax, eax
0x140042747  js      loc_1400428FD
0x14004274d  inc     r15d
0x140042750  jmp     short loc_140042726
0x140042752  mov     rdx, [rbp+47h+var_88]
0x140042756  mov     r9, rdi
0x140042759  mov     r8d, esi
0x14004275c  mov     dword ptr [rsp+0D0h+var_B0], esi
0x140042760  call    Decrypt
0x140042765  mov     ebx, eax
0x140042767  test    eax, eax
0x140042769  js      loc_1400428FD
0x14004276f  jmp     loc_140042882
0x140042774  xor     r13d, r13d
0x140042777  mov     ebx, 0C000009Ah
0x14004277c  jmp     loc_140042975
0x140042781  mov     r14d, 10h
0x140042787  cmp     si, r14w
0x14004278b  jb      loc_140042946
0x140042791  test    sil, 7
0x140042795  jnz     loc_140042946
0x14004279b  movzx   eax, si
0x14004279e  mov     dword ptr [rbp+47h+var_A0], eax
0x1400427a1  lea     esi, [rax-8]
0x1400427a4  lea     eax, [rsi+10h]
0x1400427a7  cmp     eax, r14d
0x1400427aa  jb      short loc_140042777
0x1400427ac  lea     r15d, [r14+30h]
0x1400427b0  mov     edi, 7A697377h
0x1400427b5  cmp     eax, r15d
0x1400427b8  ja      short loc_1400427C3
0x1400427ba  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400427c1  jmp     short loc_1400427F5
0x1400427c3  mov     r12d, 100h
0x1400427c9  cmp     eax, r12d
0x1400427cc  ja      short loc_1400427D7
0x1400427ce  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400427d5  jmp     short loc_1400427F5
0x1400427d7  cmp     eax, 400h
0x1400427dc  ja      short loc_1400427E7
0x1400427de  lea     rbx, Lookaside
0x1400427e5  jmp     short loc_1400427F5
0x1400427e7  cmp     eax, 800h
0x1400427ec  ja      short loc_140042806
0x1400427ee  lea     rbx, stru_1400B31C0
0x1400427f5  mov     rcx, rbx; Lookaside
0x1400427f8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400427ff  nop     dword ptr [rax+rax+00h]
0x140042804  jmp     short loc_14004281C
0x140042806  xor     ebx, ebx
0x140042808  mov     edx, eax
0x14004280a  mov     r8d, edi
0x14004280d  mov     rcx, r15
0x140042810  call    cs:__imp_ExAllocatePool2
0x140042817  nop     dword ptr [rax+rax+00h]
0x14004281c  test    rax, rax
0x14004281f  jz      loc_140042777
0x140042825  mov     r9d, dword ptr [rbp+47h+var_A0]
0x140042829  mov     r8, [rbp+47h+var_88]
0x14004282d  mov     edx, dword ptr [rbp+47h+Size]
0x140042830  mov     rcx, [rbp+47h+Src]
0x140042834  mov     [rax+8], edi
0x140042837  lea     rdi, [rax+10h]
0x14004283b  mov     [rsp+0D0h+var_B0], rdi
0x140042840  mov     [rax], rbx
0x140042843  call    AES_UNWRAP
0x140042848  mov     ebx, eax
0x14004284a  test    eax, eax
0x14004284c  jns     short loc_14004287F
0x14004284e  mov     rcx, cs:WPP_GLOBAL_Control
0x140042855  lea     rax, WPP_GLOBAL_Control
0x14004285c  cmp     rcx, rax
0x14004285f  jz      loc_1400428FD
0x140042865  mov     rcx, [rcx+18h]
0x140042869  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140042870  mov     edx, 11h
0x140042875  mov     r9d, ebx
0x140042878  call    WPP_SF_d
0x14004287d  jmp     short loc_1400428FD
0x14004287f  mov     r12, r13
0x140042882  xor     edx, edx
0x140042884  cmp     edx, esi
0x140042886  jnb     loc_140042924
0x14004288c  cmp     byte ptr [rdx+rdi], 0DDh
0x140042890  jnz     short loc_1400428AA
0x140042892  mov     eax, esi
0x140042894  sub     eax, edx
0x140042896  cmp     eax, 1
0x140042899  jz      loc_140042922
0x14004289f  jbe     short loc_1400428AA
0x1400428a1  lea     eax, [rdx+1]
0x1400428a4  cmp     byte ptr [rax+rdi], 0
0x1400428a8  jz      short loc_140042922
0x1400428aa  lea     eax, [rdx+2]
0x1400428ad  cmp     eax, esi
0x1400428af  ja      short loc_1400428C1
0x1400428b1  lea     eax, [rdx+1]
0x1400428b4  add     edx, 2
0x1400428b7  movzx   eax, byte ptr [rax+rdi]
0x1400428bb  add     edx, eax
0x1400428bd  cmp     edx, esi
0x1400428bf  jbe     short loc_140042886
0x1400428c1  mov     ebx, 0C0000001h
0x1400428c6  mov     [rbp+47h+hKey], r12
0x1400428ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400428d1  lea     rax, WPP_GLOBAL_Control
0x1400428d8  cmp     rcx, rax
0x1400428db  jz      short loc_1400428F5
0x1400428dd  mov     rcx, [rcx+18h]
0x1400428e1  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400428e8  mov     edx, 14h
0x1400428ed  mov     r9d, ebx
0x1400428f0  call    WPP_SF_d
0x1400428f5  test    ebx, ebx
0x1400428f7  jns     loc_14004298A
0x1400428fd  test    rdi, rdi
0x140042900  jz      short loc_140042975
0x140042902  lea     rcx, [rdi-10h]; P
0x140042906  mov     rax, [rcx]
0x140042909  test    rax, rax
0x14004290c  jz      short loc_140042935
0x14004290e  mov     rdx, rcx; Entry
0x140042911  mov     rcx, rax; Lookaside
0x140042914  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004291b  nop     dword ptr [rax+rax+00h]
0x140042920  jmp     short loc_140042975
0x140042922  mov     esi, edx
0x140042924  mov     rax, [rbp+47h+var_70]
0x140042928  xor     ebx, ebx
0x14004292a  mov     [rax], rdi
0x14004292d  mov     rax, [rbp+47h+var_68]
0x140042931  mov     [rax], esi
0x140042933  jmp     short loc_14004298A
  ... truncated ...
```
