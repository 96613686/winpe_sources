# WFDDeviceIndicateIncomingProvisionDiscoveryRequest(_WFD_VELAN *,_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *,void *,_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *)

- ea: `0x140024058`
- end: `0x140024369`
- name: `?WFDDeviceIndicateIncomingProvisionDiscoveryRequest@@YAJPEAU_WFD_VELAN@@PEAU_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS@@PEAXPEAU_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2@@@Z`
- size: `785`
- prototype: `__int64 __fastcall(struct _WFD_VELAN *, struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *, void *, struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140086bbc`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x140024058`
- `0x140024808`
- `0x14008d2cc`
- `0x140098be0`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140024189`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140024189`
- `ntoskrnl!ExAllocatePool2` at `0x14002419e`
- `ntoskrnl!ExAllocatePool2` at `0x14002419e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400242a4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400242a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400242ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400242ff`

## pseudocode

```c
__int64 __fastcall WFDDeviceIndicateIncomingProvisionDiscoveryRequest(
        struct _WFD_VELAN *a1,
        struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *a2,
        void *a3,
        struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *a4)
{
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // r15d
  unsigned int v11; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v14; // rdi
  char *v15; // rbx
  unsigned int v16; // r14d
  __int64 v17; // rcx
  struct _WFD_ROLE *pRole; // rcx
  int v19; // eax
  __int128 v20; // [rsp+40h] [rbp-78h] BYREF
  __int128 v21; // [rsp+50h] [rbp-68h]
  __int64 v22; // [rsp+60h] [rbp-58h]

  v20 = 0;
  v22 = 0;
  v21 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 313, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF__MAC_DDDq(
        WPP_GLOBAL_Control->AttachedDevice,
        *((unsigned __int8 *)a2 + 16),
        v7,
        (char *)a2 + 4,
        *((unsigned __int8 *)a2 + 16),
        *((_DWORD *)a2 + 8),
        *((_DWORD *)a2 + 9));
    }
  }
  v8 = *((unsigned int *)a2 + 9);
  v9 = v8 + 152;
  if ( (unsigned int)v8 >= 0xFFFFFF68 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 315, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v8, -1);
    return 3221225621LL;
  }
  v11 = v8 + 168;
  if ( v9 >= 0xFFFFFFF0 )
    goto LABEL_36;
  if ( v11 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_19:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_21;
  }
  if ( v11 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_19;
  }
  if ( v11 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_19;
  }
  if ( v11 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_19;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v11, 808679286);
LABEL_21:
  v14 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = p_DeviceQueue;
    v15 = (char *)(Pool2 + 4);
    Pool2[2] = 808679286;
    v16 = 0;
    memset(Pool2 + 4, 0, v9);
    *(_OWORD *)v15 = *(_OWORD *)a2;
    *((_OWORD *)v15 + 1) = *((_OWORD *)a2 + 1);
    *((_QWORD *)v15 + 4) = *((_QWORD *)a2 + 4);
    if ( a4 )
    {
      v15[40] = *((_BYTE *)a4 + 37);
      if ( *((_BYTE *)a4 + 44) )
      {
        *((_DWORD *)v15 + 25) = 1;
        *(_OWORD *)(v15 + 104) = *((_OWORD *)a4 + 3);
        *(_OWORD *)(v15 + 120) = *((_OWORD *)a4 + 4);
        *(_OWORD *)(v15 + 132) = *(_OWORD *)((char *)a4 + 76);
      }
      else
      {
        *((_DWORD *)v15 + 11) = 1;
        LOBYTE(v17) = *((_BYTE *)a4 + 92);
        v19 = WFDUtilConvertConnectionCapabilityFromUChar(v17, v15 + 48);
        v16 = v19;
        if ( v19 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              317,
              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              (unsigned int)v19);
          return v16;
        }
      }
      if ( *((_BYTE *)a4 + 269) )
      {
        *((_DWORD *)v15 + 13) = 1;
        *(_OWORD *)(v15 + 56) = *((_OWORD *)a4 + 17);
        *(_OWORD *)(v15 + 72) = *((_OWORD *)a4 + 18);
        *(_OWORD *)(v15 + 84) = *(_OWORD *)((char *)a4 + 300);
      }
    }
    memmove(v15 + 152, (char *)a2 + *((unsigned int *)a2 + 8), *((unsigned int *)a2 + 9));
    *((_DWORD *)v15 + 8) = 152;
    *((_DWORD *)v15 + 9) = *((_DWORD *)a2 + 9);
    pRole = a1->pRole;
    LODWORD(v20) = 26;
    DWORD2(v20) = v9;
    *(_QWORD *)&v21 = v15;
    WFDRoleSendUpcallRequest(pRole, 1, (struct DOT11_AUTH_UPCALL_REQUEST *)&v20);
    if ( *v14 )
      ExFreeToNPagedLookasideList(*v14, v14);
    else
      ExFreePoolWithTag(v14, *((_DWORD *)v14 + 2));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 318, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    return v16;
  }
LABEL_36:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 316, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v9);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140024058  push    rbx
0x14002405a  push    rbp
0x14002405b  push    rsi
0x14002405c  push    rdi
0x14002405d  push    r12
0x14002405f  push    r13
0x140024061  push    r14
0x140024063  push    r15
0x140024065  sub     rsp, 78h
0x140024069  xorps   xmm0, xmm0
0x14002406c  xor     eax, eax
0x14002406e  movups  [rsp+0B8h+var_78], xmm0
0x140024073  mov     [rsp+0B8h+var_58], rax
0x140024078  mov     rbp, r9
0x14002407b  movups  [rsp+0B8h+var_68], xmm0
0x140024080  mov     rsi, rdx
0x140024083  mov     r13, rcx
0x140024086  mov     rcx, cs:WPP_GLOBAL_Control
0x14002408d  lea     r12, WPP_GLOBAL_Control
0x140024094  cmp     rcx, r12
0x140024097  jz      short loc_1400240EC
0x140024099  mov     rcx, [rcx+18h]
0x14002409d  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400240a4  mov     edx, 139h
0x1400240a9  call    WPP_SF_
0x1400240ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400240b5  cmp     rcx, r12
0x1400240b8  jz      short loc_1400240EC
0x1400240ba  cmp     byte ptr [rcx+29h], 3
0x1400240be  jb      short loc_1400240EC
0x1400240c0  test    dword ptr [rcx+2Ch], 200000h
0x1400240c7  jz      short loc_1400240EC
0x1400240c9  mov     eax, [rsi+24h]
0x1400240cc  lea     r9, [rsi+4]
0x1400240d0  movzx   edx, byte ptr [rsi+10h]
0x1400240d4  mov     rcx, [rcx+18h]
0x1400240d8  mov     [rsp+0B8h+var_88], eax
0x1400240dc  mov     eax, [rsi+20h]
0x1400240df  mov     [rsp+0B8h+var_90], eax
0x1400240e3  mov     [rsp+0B8h+var_98], edx
0x1400240e7  call    WPP_SF__MAC_DDDq
0x1400240ec  mov     r9d, [rsi+24h]
0x1400240f0  lea     r15d, [r9+98h]
0x1400240f7  cmp     r15d, 98h
0x1400240fe  jnb     short loc_140024133
0x140024100  mov     rcx, cs:WPP_GLOBAL_Control
0x140024107  cmp     rcx, r12
0x14002410a  jz      short loc_140024129
0x14002410c  mov     rcx, [rcx+18h]
0x140024110  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140024117  mov     edx, 13Bh
0x14002411c  mov     [rsp+0B8h+var_98], 0FFFFFFFFh
0x140024124  call    WPP_SF_Dd
0x140024129  mov     eax, 0C0000095h
0x14002412e  jmp     loc_140024357
0x140024133  lea     eax, [r15+10h]
0x140024137  cmp     eax, 10h
0x14002413a  jb      loc_14002432E
0x140024140  mov     ecx, 40h ; '@'
0x140024145  mov     r14d, 30337776h
0x14002414b  cmp     eax, ecx
0x14002414d  ja      short loc_140024158
0x14002414f  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140024156  jmp     short loc_140024186
0x140024158  cmp     eax, 100h
0x14002415d  ja      short loc_140024168
0x14002415f  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140024166  jmp     short loc_140024186
0x140024168  cmp     eax, 400h
0x14002416d  ja      short loc_140024178
0x14002416f  lea     rbx, Lookaside
0x140024176  jmp     short loc_140024186
0x140024178  cmp     eax, 800h
0x14002417d  ja      short loc_140024197
0x14002417f  lea     rbx, stru_1400B31C0
0x140024186  mov     rcx, rbx; Lookaside
0x140024189  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140024190  nop     dword ptr [rax+rax+00h]
0x140024195  jmp     short loc_1400241AA
0x140024197  xor     ebx, ebx
0x140024199  mov     edx, eax
0x14002419b  mov     r8d, r14d
0x14002419e  call    cs:__imp_ExAllocatePool2
0x1400241a5  nop     dword ptr [rax+rax+00h]
0x1400241aa  mov     rdi, rax
0x1400241ad  test    rax, rax
0x1400241b0  jz      loc_14002432E
0x1400241b6  mov     [rax], rbx
0x1400241b9  xor     edx, edx; Val
0x1400241bb  lea     rbx, [rax+10h]
0x1400241bf  mov     [rax+8], r14d
0x1400241c3  mov     rcx, rbx; void *
0x1400241c6  mov     r8d, r15d; Size
0x1400241c9  xor     r14d, r14d
0x1400241cc  call    memset
0x1400241d1  movups  xmm0, xmmword ptr [rsi]
0x1400241d4  movups  xmmword ptr [rbx], xmm0
0x1400241d7  movups  xmm1, xmmword ptr [rsi+10h]
0x1400241db  movups  xmmword ptr [rbx+10h], xmm1
0x1400241df  movsd   xmm0, qword ptr [rsi+20h]
0x1400241e4  movsd   qword ptr [rbx+20h], xmm0
0x1400241e9  test    rbp, rbp
0x1400241ec  jz      short loc_140024251
0x1400241ee  mov     al, [rbp+25h]
0x1400241f1  mov     [rbx+28h], al
0x1400241f4  cmp     [rbp+2Ch], r14b
0x1400241f8  jz      loc_1400242B2
0x1400241fe  mov     dword ptr [rbx+64h], 1
0x140024205  movups  xmm0, xmmword ptr [rbp+30h]
0x140024209  movups  xmmword ptr [rbx+68h], xmm0
0x14002420d  movups  xmm1, xmmword ptr [rbp+40h]
0x140024211  movups  xmmword ptr [rbx+78h], xmm1
0x140024215  movups  xmm0, xmmword ptr [rbp+4Ch]
0x140024219  movups  xmmword ptr [rbx+84h], xmm0
0x140024220  cmp     byte ptr [rbp+10Dh], 0
0x140024227  jz      short loc_140024251
0x140024229  mov     dword ptr [rbx+34h], 1
0x140024230  movups  xmm0, xmmword ptr [rbp+110h]
0x140024237  movups  xmmword ptr [rbx+38h], xmm0
0x14002423b  movups  xmm1, xmmword ptr [rbp+120h]
0x140024242  movups  xmmword ptr [rbx+48h], xmm1
0x140024246  movups  xmm0, xmmword ptr [rbp+12Ch]
0x14002424d  movups  xmmword ptr [rbx+54h], xmm0
0x140024251  mov     edx, [rsi+20h]
0x140024254  lea     rcx, [rbx+98h]; void *
0x14002425b  mov     r8d, [rsi+24h]; Size
0x14002425f  add     rdx, rsi; Src
0x140024262  call    memmove
0x140024267  mov     dword ptr [rbx+20h], 98h
0x14002426e  lea     r8, [rsp+0B8h+var_78]; struct DOT11_AUTH_UPCALL_REQUEST *
0x140024273  mov     eax, [rsi+24h]
0x140024276  mov     edx, 1; int
0x14002427b  mov     [rbx+24h], eax
0x14002427e  mov     rcx, [r13+38h]; struct _WFD_ROLE *
0x140024282  mov     dword ptr [rsp+0B8h+var_78], 1Ah
0x14002428a  mov     dword ptr [rsp+0B8h+var_78+8], r15d
0x14002428f  mov     qword ptr [rsp+0B8h+var_68], rbx
0x140024294  call    ?WFDRoleSendUpcallRequest@@YAXPEAU_WFD_ROLE@@HPEAUDOT11_AUTH_UPCALL_REQUEST@@@Z; WFDRoleSendUpcallRequest(_WFD_ROLE *,int,DOT11_AUTH_UPCALL_REQUEST *)
0x140024299  mov     rcx, [rdi]; Lookaside
0x14002429c  test    rcx, rcx
0x14002429f  jz      short loc_1400242F9
0x1400242a1  mov     rdx, rdi; Entry
0x1400242a4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400242ab  nop     dword ptr [rax+rax+00h]
0x1400242b0  jmp     short loc_14002430B
0x1400242b2  mov     dword ptr [rbx+2Ch], 1
0x1400242b9  lea     rdx, [rbx+30h]
0x1400242bd  mov     cl, [rbp+5Ch]
0x1400242c0  call    WFDUtilConvertConnectionCapabilityFromUChar
0x1400242c5  mov     r14d, eax
0x1400242c8  test    eax, eax
0x1400242ca  jns     loc_140024220
0x1400242d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400242d7  cmp     rcx, r12
0x1400242da  jz      short loc_1400242F4
0x1400242dc  mov     rcx, [rcx+18h]
0x1400242e0  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400242e7  mov     edx, 13Dh
0x1400242ec  mov     r9d, eax
0x1400242ef  call    WPP_SF_d
0x1400242f4  mov     eax, r14d
0x1400242f7  jmp     short loc_140024357
0x1400242f9  mov     edx, [rdi+8]; Tag
0x1400242fc  mov     rcx, rdi; P
0x1400242ff  call    cs:__imp_ExFreePoolWithTag
0x140024306  nop     dword ptr [rax+rax+00h]
0x14002430b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024312  cmp     rcx, r12
0x140024315  jz      short loc_1400242F4
0x140024317  mov     rcx, [rcx+18h]
0x14002431b  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140024322  mov     edx, 13Eh
0x140024327  call    WPP_SF_
0x14002432c  jmp     short loc_1400242F4
0x14002432e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024335  cmp     rcx, r12
0x140024338  jz      short loc_140024352
0x14002433a  mov     rcx, [rcx+18h]
0x14002433e  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140024345  mov     edx, 13Ch
0x14002434a  mov     r9d, r15d
0x14002434d  call    WPP_SF_d
0x140024352  mov     eax, 0C000009Ah
0x140024357  add     rsp, 78h
0x14002435b  pop     r15
0x14002435d  pop     r14
0x14002435f  pop     r13
0x140024361  pop     r12
0x140024363  pop     rdi
0x140024364  pop     rsi
0x140024365  pop     rbp
0x140024366  pop     rbx
0x140024367  retn
```
