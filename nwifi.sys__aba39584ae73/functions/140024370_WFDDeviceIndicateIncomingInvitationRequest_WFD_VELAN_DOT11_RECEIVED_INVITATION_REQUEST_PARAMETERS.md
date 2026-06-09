# WFDDeviceIndicateIncomingInvitationRequest(_WFD_VELAN *,_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *)

- ea: `0x140024370`
- end: `0x1400245c2`
- name: `?WFDDeviceIndicateIncomingInvitationRequest@@YAJPEAU_WFD_VELAN@@PEAU_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(struct _WFD_VELAN *, struct _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140086104`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x140024370`
- `0x140024808`
- `0x14008ccd4`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140024493`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140024493`
- `ntoskrnl!ExAllocatePool2` at `0x1400244ab`
- `ntoskrnl!ExAllocatePool2` at `0x1400244ab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024546`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024546`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002455a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002455a`

## pseudocode

```c
__int64 __fastcall WFDDeviceIndicateIncomingInvitationRequest(
        struct _WFD_VELAN *a1,
        struct _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *a2)
{
  __int64 v4; // r9
  unsigned int v5; // ebp
  unsigned int v7; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v10; // rdi
  char *v11; // rbx
  struct _WFD_ROLE *pRole; // rcx
  __int128 v13; // [rsp+40h] [rbp-68h] BYREF
  __int128 v14; // [rsp+50h] [rbp-58h]
  __int64 v15; // [rsp+60h] [rbp-48h]

  v13 = 0;
  v15 = 0;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 225, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF__MAC_DDD(
        WPP_GLOBAL_Control->AttachedDevice,
        226,
        *((unsigned __int8 *)a2 + 16),
        (char *)a2 + 4,
        *((unsigned __int8 *)a2 + 16),
        *((_DWORD *)a2 + 8),
        *((_DWORD *)a2 + 9));
    }
  }
  v4 = *((unsigned int *)a2 + 9);
  v5 = v4 + 48;
  if ( (unsigned int)v4 >= 0xFFFFFFD0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 227, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v4, -1);
    return 3221225621LL;
  }
  v7 = v4 + 64;
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
    *((_QWORD *)v11 + 5) = *((_QWORD *)a2 + 4);
    memmove(v11 + 48, (char *)a2 + *((unsigned int *)a2 + 8), *((unsigned int *)a2 + 9));
    *((_DWORD *)v11 + 10) = 40;
    *((_DWORD *)v11 + 11) = *((_DWORD *)a2 + 9);
    pRole = a1->pRole;
    LODWORD(v13) = 19;
    DWORD2(v13) = v5;
    *(_QWORD *)&v14 = v11;
    WFDRoleSendUpcallRequest(pRole, 1, (struct DOT11_AUTH_UPCALL_REQUEST *)&v13);
    if ( *v10 )
      ExFreeToNPagedLookasideList(*v10, v10);
    else
      ExFreePoolWithTag(v10, *((_DWORD *)v10 + 2));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 229, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    return 0;
  }
LABEL_28:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 228, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v5);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140024370  push    rbx
0x140024372  push    rbp
0x140024373  push    rsi
0x140024374  push    rdi
0x140024375  push    r14
0x140024377  push    r15
0x140024379  sub     rsp, 78h
0x14002437d  xorps   xmm0, xmm0
0x140024380  xor     eax, eax
0x140024382  movups  [rsp+0A8h+var_68], xmm0
0x140024387  mov     [rsp+0A8h+var_48], rax
0x14002438c  mov     rsi, rdx
0x14002438f  movups  [rsp+0A8h+var_58], xmm0
0x140024394  mov     r14, rcx
0x140024397  mov     rcx, cs:WPP_GLOBAL_Control
0x14002439e  lea     r15, WPP_GLOBAL_Control
0x1400243a5  cmp     rcx, r15
0x1400243a8  jz      short loc_140024404
0x1400243aa  mov     rcx, [rcx+18h]
0x1400243ae  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400243b5  mov     edx, 0E1h
0x1400243ba  call    WPP_SF_
0x1400243bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400243c6  cmp     rcx, r15
0x1400243c9  jz      short loc_140024404
0x1400243cb  cmp     byte ptr [rcx+29h], 3
0x1400243cf  jb      short loc_140024404
0x1400243d1  test    dword ptr [rcx+2Ch], 200000h
0x1400243d8  jz      short loc_140024404
0x1400243da  mov     eax, [rsi+24h]
0x1400243dd  lea     r9, [rsi+4]
0x1400243e1  movzx   r8d, byte ptr [rsi+10h]
0x1400243e6  mov     edx, 0E2h
0x1400243eb  mov     rcx, [rcx+18h]
0x1400243ef  mov     [rsp+0A8h+var_78], eax
0x1400243f3  mov     eax, [rsi+20h]
0x1400243f6  mov     [rsp+0A8h+var_80], eax
0x1400243fa  mov     [rsp+0A8h+var_88], r8d
0x1400243ff  call    WPP_SF__MAC_DDD
0x140024404  mov     r9d, [rsi+24h]
0x140024408  lea     ebp, [r9+30h]
0x14002440c  cmp     ebp, 30h ; '0'
0x14002440f  jnb     short loc_140024444
0x140024411  mov     rcx, cs:WPP_GLOBAL_Control
0x140024418  cmp     rcx, r15
0x14002441b  jz      short loc_14002443A
0x14002441d  mov     rcx, [rcx+18h]
0x140024421  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140024428  mov     edx, 0E3h
0x14002442d  mov     [rsp+0A8h+var_88], 0FFFFFFFFh
0x140024435  call    WPP_SF_Dd
0x14002443a  mov     eax, 0C0000095h
0x14002443f  jmp     loc_1400245B4
0x140024444  lea     eax, [rbp+10h]
0x140024447  cmp     eax, 10h
0x14002444a  jb      loc_14002458B
0x140024450  mov     ecx, 40h ; '@'
0x140024455  cmp     eax, ecx
0x140024457  ja      short loc_140024462
0x140024459  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140024460  jmp     short loc_140024490
0x140024462  cmp     eax, 100h
0x140024467  ja      short loc_140024472
0x140024469  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140024470  jmp     short loc_140024490
0x140024472  cmp     eax, 400h
0x140024477  ja      short loc_140024482
0x140024479  lea     rbx, Lookaside
0x140024480  jmp     short loc_140024490
0x140024482  cmp     eax, 800h
0x140024487  ja      short loc_1400244A1
0x140024489  lea     rbx, stru_1400B31C0
0x140024490  mov     rcx, rbx; Lookaside
0x140024493  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14002449a  nop     dword ptr [rax+rax+00h]
0x14002449f  jmp     short loc_1400244B7
0x1400244a1  xor     ebx, ebx
0x1400244a3  mov     edx, eax
0x1400244a5  mov     r8d, 30337776h
0x1400244ab  call    cs:__imp_ExAllocatePool2
0x1400244b2  nop     dword ptr [rax+rax+00h]
0x1400244b7  mov     rdi, rax
0x1400244ba  test    rax, rax
0x1400244bd  jz      loc_14002458B
0x1400244c3  mov     [rax], rbx
0x1400244c6  xor     edx, edx; Val
0x1400244c8  lea     rbx, [rax+10h]
0x1400244cc  mov     r8d, ebp; Size
0x1400244cf  mov     rcx, rbx; void *
0x1400244d2  mov     dword ptr [rax+8], 30337776h
0x1400244d9  call    memset
0x1400244de  movups  xmm0, xmmword ptr [rsi]
0x1400244e1  lea     rcx, [rbx+30h]; void *
0x1400244e5  movups  xmmword ptr [rbx+8], xmm0
0x1400244e9  movups  xmm1, xmmword ptr [rsi+10h]
0x1400244ed  movups  xmmword ptr [rbx+18h], xmm1
0x1400244f1  movsd   xmm0, qword ptr [rsi+20h]
0x1400244f6  movsd   qword ptr [rbx+28h], xmm0
0x1400244fb  mov     edx, [rsi+20h]
0x1400244fe  mov     r8d, [rsi+24h]; Size
0x140024502  add     rdx, rsi; Src
0x140024505  call    memmove
0x14002450a  mov     dword ptr [rbx+28h], 28h ; '('
0x140024511  lea     r8, [rsp+0A8h+var_68]; struct DOT11_AUTH_UPCALL_REQUEST *
0x140024516  mov     eax, [rsi+24h]
0x140024519  mov     edx, 1; int
0x14002451e  mov     [rbx+2Ch], eax
0x140024521  mov     rcx, [r14+38h]; struct _WFD_ROLE *
0x140024525  mov     dword ptr [rsp+0A8h+var_68], 13h
0x14002452d  mov     dword ptr [rsp+0A8h+var_68+8], ebp
0x140024531  mov     qword ptr [rsp+0A8h+var_58], rbx
0x140024536  call    ?WFDRoleSendUpcallRequest@@YAXPEAU_WFD_ROLE@@HPEAUDOT11_AUTH_UPCALL_REQUEST@@@Z; WFDRoleSendUpcallRequest(_WFD_ROLE *,int,DOT11_AUTH_UPCALL_REQUEST *)
0x14002453b  mov     rcx, [rdi]; Lookaside
0x14002453e  test    rcx, rcx
0x140024541  jz      short loc_140024554
0x140024543  mov     rdx, rdi; Entry
0x140024546  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002454d  nop     dword ptr [rax+rax+00h]
0x140024552  jmp     short loc_140024566
0x140024554  mov     edx, [rdi+8]; Tag
0x140024557  mov     rcx, rdi; P
0x14002455a  call    cs:__imp_ExFreePoolWithTag
0x140024561  nop     dword ptr [rax+rax+00h]
0x140024566  mov     rcx, cs:WPP_GLOBAL_Control
0x14002456d  cmp     rcx, r15
0x140024570  jz      short loc_140024587
0x140024572  mov     rcx, [rcx+18h]
0x140024576  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14002457d  mov     edx, 0E5h
0x140024582  call    WPP_SF_
0x140024587  xor     eax, eax
0x140024589  jmp     short loc_1400245B4
0x14002458b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024592  cmp     rcx, r15
0x140024595  jz      short loc_1400245AF
0x140024597  mov     rcx, [rcx+18h]
0x14002459b  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400245a2  mov     edx, 0E4h
0x1400245a7  mov     r9d, ebp
0x1400245aa  call    WPP_SF_d
0x1400245af  mov     eax, 0C000009Ah
0x1400245b4  add     rsp, 78h
0x1400245b8  pop     r15
0x1400245ba  pop     r14
0x1400245bc  pop     rdi
0x1400245bd  pop     rsi
0x1400245be  pop     rbp
0x1400245bf  pop     rbx
0x1400245c0  retn
```
