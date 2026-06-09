# WFDDeviceIndicateIncomingGONegotiationRequest(_WFD_VELAN *,_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *)

- ea: `0x1400245c8`
- end: `0x140024802`
- name: `?WFDDeviceIndicateIncomingGONegotiationRequest@@YAJPEAU_WFD_VELAN@@PEAU_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(struct _WFD_VELAN *, struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140087c1c`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x1400245c8`
- `0x140024808`
- `0x14006f2bc`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400246e3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400246e3`
- `ntoskrnl!ExAllocatePool2` at `0x1400246fb`
- `ntoskrnl!ExAllocatePool2` at `0x1400246fb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002478c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002478c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400247a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400247a0`

## pseudocode

```c
__int64 __fastcall WFDDeviceIndicateIncomingGONegotiationRequest(
        struct _WFD_VELAN *a1,
        struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *a2)
{
  __int64 v4; // r9
  unsigned int v5; // ebp
  unsigned int v7; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v10; // rdi
  char *v11; // rbx
  struct _WFD_ROLE *pRole; // rcx
  int v13; // [rsp+28h] [rbp-70h]
  __int128 v14; // [rsp+30h] [rbp-68h] BYREF
  __int128 v15; // [rsp+40h] [rbp-58h]
  __int64 v16; // [rsp+50h] [rbp-48h]

  v14 = 0;
  v16 = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      v13 = *((_DWORD *)a2 + 7);
      WPP_SF__MAC_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        (unsigned int)WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        (_DWORD)a2 + 4,
        *((_DWORD *)a2 + 6),
        v13,
        v14,
        v15,
        v16);
    }
  }
  v4 = *((unsigned int *)a2 + 7);
  v5 = v4 + 40;
  if ( (unsigned int)v4 >= 0xFFFFFFD8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v4, -1);
    return 3221225621LL;
  }
  v7 = v4 + 56;
  if ( v5 >= 0xFFFFFFF0 )
    goto LABEL_28;
  if ( v7 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_19:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_21;
  }
  if ( v7 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_19;
  }
  if ( v7 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_19;
  }
  if ( v7 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_19;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v7, 808679286);
LABEL_21:
  v10 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = p_DeviceQueue;
    v11 = (char *)(Pool2 + 4);
    Pool2[2] = 808679286;
    memset(Pool2 + 4, 0, v5);
    *(_OWORD *)(v11 + 8) = *(_OWORD *)a2;
    *(_OWORD *)(v11 + 24) = *((_OWORD *)a2 + 1);
    memmove(v11 + 40, (char *)a2 + *((unsigned int *)a2 + 6), *((unsigned int *)a2 + 7));
    *((_DWORD *)v11 + 8) = 32;
    *((_DWORD *)v11 + 9) = *((_DWORD *)a2 + 7);
    pRole = a1->pRole;
    LODWORD(v14) = 18;
    DWORD2(v14) = v5;
    *(_QWORD *)&v15 = v11;
    WFDRoleSendUpcallRequest(pRole, 1, (struct DOT11_AUTH_UPCALL_REQUEST *)&v14);
    if ( *v10 )
      ExFreeToNPagedLookasideList(*v10, v10);
    else
      ExFreePoolWithTag(v10, *((_DWORD *)v10 + 2));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    return 0;
  }
LABEL_28:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v5);
  return 3221225626LL;
}

```

## disassembly

```asm
0x1400245c8  push    rbx
0x1400245ca  push    rbp
0x1400245cb  push    rsi
0x1400245cc  push    rdi
0x1400245cd  push    r12
0x1400245cf  push    r14
0x1400245d1  push    r15
0x1400245d3  sub     rsp, 60h
0x1400245d7  xorps   xmm0, xmm0
0x1400245da  xor     eax, eax
0x1400245dc  movups  [rsp+98h+var_68], xmm0
0x1400245e1  mov     [rsp+98h+var_48], rax
0x1400245e6  mov     rsi, rdx
0x1400245e9  movups  [rsp+98h+var_58], xmm0
0x1400245ee  mov     r14, rcx
0x1400245f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400245f8  lea     r15, WPP_GLOBAL_Control
0x1400245ff  lea     r12, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140024606  cmp     rcx, r15
0x140024609  jz      short loc_140024658
0x14002460b  mov     rcx, [rcx+18h]
0x14002460f  lea     edx, [rax+1Fh]
0x140024612  mov     r8, r12
0x140024615  call    WPP_SF_
0x14002461a  mov     rcx, cs:WPP_GLOBAL_Control
0x140024621  cmp     rcx, r15
0x140024624  jz      short loc_140024658
0x140024626  cmp     byte ptr [rcx+29h], 3
0x14002462a  jb      short loc_140024658
0x14002462c  test    dword ptr [rcx+2Ch], 200000h
0x140024633  jz      short loc_140024658
0x140024635  mov     eax, [rsi+1Ch]
0x140024638  lea     r9, [rsi+4]
0x14002463c  mov     rcx, [rcx+18h]
0x140024640  mov     edx, 20h ; ' '
0x140024645  mov     [rsp+98h+var_70], eax
0x140024649  mov     r8, r12
0x14002464c  mov     eax, [rsi+18h]
0x14002464f  mov     [rsp+98h+var_78], eax
0x140024653  call    WPP_SF__MAC_DD
0x140024658  mov     r9d, [rsi+1Ch]
0x14002465c  lea     ebp, [r9+28h]
0x140024660  cmp     ebp, 28h ; '('
0x140024663  jnb     short loc_140024694
0x140024665  mov     rcx, cs:WPP_GLOBAL_Control
0x14002466c  cmp     rcx, r15
0x14002466f  jz      short loc_14002468A
0x140024671  mov     rcx, [rcx+18h]
0x140024675  mov     edx, 21h ; '!'
0x14002467a  mov     r8, r12
0x14002467d  mov     [rsp+98h+var_78], 0FFFFFFFFh
0x140024685  call    WPP_SF_Dd
0x14002468a  mov     eax, 0C0000095h
0x14002468f  jmp     loc_1400247F2
0x140024694  lea     eax, [rbp+10h]
0x140024697  cmp     eax, 10h
0x14002469a  jb      loc_1400247CD
0x1400246a0  mov     ecx, 40h ; '@'
0x1400246a5  cmp     eax, ecx
0x1400246a7  ja      short loc_1400246B2
0x1400246a9  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400246b0  jmp     short loc_1400246E0
0x1400246b2  cmp     eax, 100h
0x1400246b7  ja      short loc_1400246C2
0x1400246b9  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400246c0  jmp     short loc_1400246E0
0x1400246c2  cmp     eax, 400h
0x1400246c7  ja      short loc_1400246D2
0x1400246c9  lea     rbx, Lookaside
0x1400246d0  jmp     short loc_1400246E0
0x1400246d2  cmp     eax, 800h
0x1400246d7  ja      short loc_1400246F1
0x1400246d9  lea     rbx, stru_1400B31C0
0x1400246e0  mov     rcx, rbx; Lookaside
0x1400246e3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400246ea  nop     dword ptr [rax+rax+00h]
0x1400246ef  jmp     short loc_140024707
0x1400246f1  xor     ebx, ebx
0x1400246f3  mov     edx, eax
0x1400246f5  mov     r8d, 30337776h
0x1400246fb  call    cs:__imp_ExAllocatePool2
0x140024702  nop     dword ptr [rax+rax+00h]
0x140024707  mov     rdi, rax
0x14002470a  test    rax, rax
0x14002470d  jz      loc_1400247CD
0x140024713  mov     [rax], rbx
0x140024716  xor     edx, edx; Val
0x140024718  lea     rbx, [rax+10h]
0x14002471c  mov     r8d, ebp; Size
0x14002471f  mov     rcx, rbx; void *
0x140024722  mov     dword ptr [rax+8], 30337776h
0x140024729  call    memset
0x14002472e  movups  xmm0, xmmword ptr [rsi]
0x140024731  lea     rcx, [rbx+28h]; void *
0x140024735  movups  xmmword ptr [rbx+8], xmm0
0x140024739  movups  xmm1, xmmword ptr [rsi+10h]
0x14002473d  movups  xmmword ptr [rbx+18h], xmm1
0x140024741  mov     edx, [rsi+18h]
0x140024744  mov     r8d, [rsi+1Ch]; Size
0x140024748  add     rdx, rsi; Src
0x14002474b  call    memmove
0x140024750  mov     dword ptr [rbx+20h], 20h ; ' '
0x140024757  lea     r8, [rsp+98h+var_68]; struct DOT11_AUTH_UPCALL_REQUEST *
0x14002475c  mov     eax, [rsi+1Ch]
0x14002475f  mov     edx, 1; int
0x140024764  mov     [rbx+24h], eax
0x140024767  mov     rcx, [r14+38h]; struct _WFD_ROLE *
0x14002476b  mov     dword ptr [rsp+98h+var_68], 12h
0x140024773  mov     dword ptr [rsp+98h+var_68+8], ebp
0x140024777  mov     qword ptr [rsp+98h+var_58], rbx
0x14002477c  call    ?WFDRoleSendUpcallRequest@@YAXPEAU_WFD_ROLE@@HPEAUDOT11_AUTH_UPCALL_REQUEST@@@Z; WFDRoleSendUpcallRequest(_WFD_ROLE *,int,DOT11_AUTH_UPCALL_REQUEST *)
0x140024781  mov     rcx, [rdi]; Lookaside
0x140024784  test    rcx, rcx
0x140024787  jz      short loc_14002479A
0x140024789  mov     rdx, rdi; Entry
0x14002478c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140024793  nop     dword ptr [rax+rax+00h]
0x140024798  jmp     short loc_1400247AC
0x14002479a  mov     edx, [rdi+8]; Tag
0x14002479d  mov     rcx, rdi; P
0x1400247a0  call    cs:__imp_ExFreePoolWithTag
0x1400247a7  nop     dword ptr [rax+rax+00h]
0x1400247ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400247b3  cmp     rcx, r15
0x1400247b6  jz      short loc_1400247C9
0x1400247b8  mov     rcx, [rcx+18h]
0x1400247bc  mov     edx, 23h ; '#'
0x1400247c1  mov     r8, r12
0x1400247c4  call    WPP_SF_
0x1400247c9  xor     eax, eax
0x1400247cb  jmp     short loc_1400247F2
0x1400247cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400247d4  cmp     rcx, r15
0x1400247d7  jz      short loc_1400247ED
0x1400247d9  mov     rcx, [rcx+18h]
0x1400247dd  mov     edx, 22h ; '"'
0x1400247e2  mov     r9d, ebp
0x1400247e5  mov     r8, r12
0x1400247e8  call    WPP_SF_d
0x1400247ed  mov     eax, 0C000009Ah
0x1400247f2  add     rsp, 60h
0x1400247f6  pop     r15
0x1400247f8  pop     r14
0x1400247fa  pop     r12
0x1400247fc  pop     rdi
0x1400247fd  pop     rsi
0x1400247fe  pop     rbp
0x1400247ff  pop     rbx
0x140024800  retn
```
