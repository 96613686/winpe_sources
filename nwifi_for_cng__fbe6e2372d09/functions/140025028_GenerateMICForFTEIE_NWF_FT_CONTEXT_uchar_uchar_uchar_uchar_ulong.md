# GenerateMICForFTEIE(NWF_FT_CONTEXT *,uchar,uchar *,uchar *,uchar *,ulong)

- ea: `0x140025028`
- end: `0x140025254`
- name: `?GenerateMICForFTEIE@@YAJPEAUNWF_FT_CONTEXT@@EPEAE11K@Z`
- size: `556`
- prototype: `__int64 __fastcall(struct NWF_FT_CONTEXT *, unsigned __int8, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140042a1c`
- `0x140047794`

## callees

- `0x14000d21c`
- `0x140020f20`
- `0x140025028`
- `0x14002525c`
- `0x14009bbb0`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400250d1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400250d1`
- `ntoskrnl!ExAllocatePool2` at `0x1400250e6`
- `ntoskrnl!ExAllocatePool2` at `0x1400250e6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025213`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025213`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025227`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025227`

## pseudocode

```c
__int64 __fastcall GenerateMICForFTEIE(
        struct NWF_FT_CONTEXT *a1,
        char a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        unsigned int a6)
{
  unsigned __int8 *pFTE_MIC; // rax
  unsigned int v9; // r14d
  unsigned int v10; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v13; // rdi
  unsigned int v14; // ebp
  char *v15; // r15
  unsigned int v16; // ebx
  __int128 v20; // [rsp+40h] [rbp-68h] BYREF

  pFTE_MIC = a1->pFTE_MIC;
  v20 = 0;
  *(_OWORD *)pFTE_MIC = 0;
  v9 = a1->FTEIELength + a1->MDDIELength + a1->RSNIELength;
  v10 = v9 + 29;
  if ( v9 + 29 < 0x10 )
  {
LABEL_13:
    v14 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        459,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        v9 + 13,
        -1073741670);
    return v14;
  }
  if ( v10 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_10:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_12;
  }
  if ( v10 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_10;
  }
  if ( v10 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_10;
  }
  if ( v10 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_10;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v10, 2053731191);
LABEL_12:
  v13 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( !Pool2 )
    goto LABEL_13;
  v15 = (char *)(Pool2 + 4);
  Pool2[2] = 2053731191;
  v14 = 0;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  Pool2[4] = *(_DWORD *)a3;
  *((_WORD *)Pool2 + 10) = *((_WORD *)a3 + 2);
  *(_DWORD *)((char *)Pool2 + 22) = *(_DWORD *)a4;
  *((_WORD *)Pool2 + 13) = *((_WORD *)a4 + 2);
  *((_BYTE *)Pool2 + 28) = a2;
  memmove((char *)Pool2 + 29, a1->pRSNIE, a1->RSNIELength);
  v16 = a1->RSNIELength + 13;
  memmove(&v15[v16], a1->pMDDIE, a1->MDDIELength);
  memmove(&v15[v16 + a1->MDDIELength], a1->pFTEIE, a1->FTEIELength);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 460, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
  WL_CMAC_128((_DWORD)v13 + 16, v9 + 13, (_DWORD)a5, a6, (__int64)&v20);
  *(_OWORD *)a1->pFTE_MIC = v20;
  if ( *v13 )
    ExFreeToNPagedLookasideList(*v13, v13);
  else
    ExFreePoolWithTag(v13, *((_DWORD *)v13 + 2));
  return v14;
}

```

## disassembly

```asm
0x140025028  push    rbx
0x14002502a  push    rbp
0x14002502b  push    rsi
0x14002502c  push    rdi
0x14002502d  push    r12
0x14002502f  push    r13
0x140025031  push    r14
0x140025033  push    r15
0x140025035  sub     rsp, 68h
0x140025039  mov     rax, cs:__security_cookie
0x140025040  xor     rax, rsp
0x140025043  mov     [rsp+0A8h+var_58], rax
0x140025048  mov     rax, [rcx+98h]
0x14002504f  xorps   xmm0, xmm0
0x140025052  mov     r12, [rsp+0A8h+arg_20]
0x14002505a  xorps   xmm1, xmm1
0x14002505d  movups  [rsp+0A8h+var_68], xmm0
0x140025062  mov     r13, r9
0x140025065  mov     [rsp+0A8h+var_70], r8
0x14002506a  movups  xmmword ptr [rax], xmm1
0x14002506d  mov     r14d, [rcx+3Ch]
0x140025071  mov     rsi, rcx
0x140025074  add     r14d, [rcx+34h]
0x140025078  add     r14d, [rcx+38h]
0x14002507c  mov     [rsp+0A8h+var_78], dl
0x140025080  lea     eax, [r14+1Dh]
0x140025084  cmp     eax, 10h
0x140025087  jb      short loc_1400250FA
0x140025089  mov     ecx, 40h ; '@'
0x14002508e  mov     ebp, 7A697377h
0x140025093  cmp     eax, ecx
0x140025095  ja      short loc_1400250A0
0x140025097  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14002509e  jmp     short loc_1400250CE
0x1400250a0  cmp     eax, 100h
0x1400250a5  ja      short loc_1400250B0
0x1400250a7  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400250ae  jmp     short loc_1400250CE
0x1400250b0  cmp     eax, 400h
0x1400250b5  ja      short loc_1400250C0
0x1400250b7  lea     rbx, Lookaside
0x1400250be  jmp     short loc_1400250CE
0x1400250c0  cmp     eax, 800h
0x1400250c5  ja      short loc_1400250DF
0x1400250c7  lea     rbx, stru_1400B31C0
0x1400250ce  mov     rcx, rbx; Lookaside
0x1400250d1  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400250d8  nop     dword ptr [rax+rax+00h]
0x1400250dd  jmp     short loc_1400250F2
0x1400250df  xor     ebx, ebx
0x1400250e1  mov     edx, eax
0x1400250e3  mov     r8d, ebp
0x1400250e6  call    cs:__imp_ExAllocatePool2
0x1400250ed  nop     dword ptr [rax+rax+00h]
0x1400250f2  mov     rdi, rax
0x1400250f5  test    rax, rax
0x1400250f8  jnz     short loc_140025138
0x1400250fa  mov     ebp, 0C000009Ah
0x1400250ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140025106  lea     rax, WPP_GLOBAL_Control
0x14002510d  cmp     rcx, rax
0x140025110  jz      loc_140025233
0x140025116  mov     rcx, [rcx+18h]
0x14002511a  lea     r9d, [r14+0Dh]
0x14002511e  mov     edx, 1CBh
0x140025123  mov     dword ptr [rsp+0A8h+var_88], ebp
0x140025127  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14002512e  call    WPP_SF_Dd
0x140025133  jmp     loc_140025233
0x140025138  mov     rcx, [rsp+0A8h+var_70]
0x14002513d  lea     r15, [rdi+10h]
0x140025141  mov     [rdi+8], ebp
0x140025144  xor     ebp, ebp
0x140025146  mov     [rdi], rbx
0x140025149  mov     eax, [rcx]
0x14002514b  mov     [r15], eax
0x14002514e  movzx   eax, word ptr [rcx+4]
0x140025152  lea     rcx, [r15+0Dh]; void *
0x140025156  mov     [r15+4], ax
0x14002515b  mov     eax, [r13+0]
0x14002515f  mov     [r15+6], eax
0x140025163  movzx   eax, word ptr [r13+4]
0x140025168  mov     [r15+0Ah], ax
0x14002516d  mov     al, [rsp+0A8h+var_78]
0x140025171  mov     [r15+0Ch], al
0x140025175  mov     r8d, [rsi+3Ch]; Size
0x140025179  mov     rdx, [rsi+50h]; Src
0x14002517d  call    memmove
0x140025182  mov     ebx, [rsi+3Ch]
0x140025185  mov     r8d, [rsi+34h]; Size
0x140025189  add     ebx, 0Dh
0x14002518c  mov     rdx, [rsi+40h]; Src
0x140025190  mov     ecx, ebx
0x140025192  add     rcx, r15; void *
0x140025195  call    memmove
0x14002519a  mov     ecx, [rsi+34h]
0x14002519d  mov     r8d, [rsi+38h]; Size
0x1400251a1  add     ecx, ebx
0x1400251a3  mov     rdx, [rsi+48h]; Src
0x1400251a7  add     rcx, r15; void *
0x1400251aa  call    memmove
0x1400251af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400251b6  lea     rax, WPP_GLOBAL_Control
0x1400251bd  cmp     rcx, rax
0x1400251c0  jz      short loc_1400251D7
0x1400251c2  mov     rcx, [rcx+18h]
0x1400251c6  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400251cd  mov     edx, 1CCh
0x1400251d2  call    WPP_SF_
0x1400251d7  mov     r9d, [rsp+0A8h+arg_28]
0x1400251df  lea     rax, [rsp+0A8h+var_68]
0x1400251e4  mov     r8, r12
0x1400251e7  mov     [rsp+0A8h+var_88], rax
0x1400251ec  lea     edx, [r14+0Dh]
0x1400251f0  mov     rcx, r15
0x1400251f3  call    WL_CMAC_128
0x1400251f8  mov     rax, [rsi+98h]
0x1400251ff  movups  xmm0, [rsp+0A8h+var_68]
0x140025204  movdqu  xmmword ptr [rax], xmm0
0x140025208  mov     rcx, [rdi]; Lookaside
0x14002520b  test    rcx, rcx
0x14002520e  jz      short loc_140025221
0x140025210  mov     rdx, rdi; Entry
0x140025213  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002521a  nop     dword ptr [rax+rax+00h]
0x14002521f  jmp     short loc_140025233
0x140025221  mov     edx, [rdi+8]; Tag
0x140025224  mov     rcx, rdi; P
0x140025227  call    cs:__imp_ExFreePoolWithTag
0x14002522e  nop     dword ptr [rax+rax+00h]
0x140025233  mov     eax, ebp
0x140025235  mov     rcx, [rsp+0A8h+var_58]
0x14002523a  xor     rcx, rsp; StackCookie
0x14002523d  call    __security_check_cookie
0x140025242  add     rsp, 68h
0x140025246  pop     r15
0x140025248  pop     r14
0x14002524a  pop     r13
0x14002524c  pop     r12
0x14002524e  pop     rdi
0x14002524f  pop     rsi
0x140025250  pop     rbp
0x140025251  pop     rbx
0x140025252  retn
```
