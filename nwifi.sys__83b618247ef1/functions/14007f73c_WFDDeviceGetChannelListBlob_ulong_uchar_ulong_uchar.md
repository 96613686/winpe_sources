# WFDDeviceGetChannelListBlob(ulong,uchar *,ulong *,uchar * *)

- ea: `0x14007f73c`
- end: `0x14007f9a3`
- name: `?WFDDeviceGetChannelListBlob@@YAJKPEAEPEAKPEAPEAE@Z`
- size: `615`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int8 *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14008055c`
- `0x14008332c`

## callees

- `0x14000d22c`
- `0x14007f73c`
- `0x140096508`
- `0x140096614`
- `0x1400966b0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007f88f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007f88f`
- `ntoskrnl!ExAllocatePool2` at `0x14007f8a4`
- `ntoskrnl!ExAllocatePool2` at `0x14007f8a4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f932`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f932`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f943`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f943`

## pseudocode

```c
__int64 __fastcall WFDDeviceGetChannelListBlob(
        unsigned int a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  unsigned int FirstP2PIE; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int v10; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  char *Pool2; // rax
  size_t v13; // r8
  unsigned __int8 *v14; // rdi
  unsigned int v15; // eax
  __int128 v17; // [rsp+30h] [rbp-20h] BYREF
  __int64 v18; // [rsp+40h] [rbp-10h]
  unsigned int v19; // [rsp+70h] [rbp+20h] BYREF
  unsigned __int8 *v20; // [rsp+78h] [rbp+28h] BYREF

  v20 = a2;
  v19 = a1;
  v18 = 0;
  v17 = 0;
  if ( !a3 )
  {
    FirstP2PIE = -1073741811;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v8 = 395;
LABEL_34:
      WPP_SF_(v7->AttachedDevice, v8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      return FirstP2PIE;
    }
    return FirstP2PIE;
  }
  FirstP2PIE = FindFirstP2PIE(&v20, &v19);
  if ( !FirstP2PIE )
  {
    FirstP2PIE = FindAttributeInFragmentedP2PIEs(v20, v19, 0xBu, (struct _WFD_ATTRIBUTE_INFO *)&v17);
    if ( FirstP2PIE )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v8 = 397;
        goto LABEL_34;
      }
      return FirstP2PIE;
    }
    if ( WORD1(v17) < 5u )
    {
      FirstP2PIE = -1071448043;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v8 = 398;
        goto LABEL_34;
      }
      return FirstP2PIE;
    }
    v10 = WORD1(v17) + 16;
    if ( v10 > 0x40 )
    {
      if ( v10 > 0x100 )
      {
        if ( v10 > 0x400 )
        {
          if ( v10 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (char *)ExAllocatePool2(64, v10, 808679286, v9);
LABEL_23:
            if ( Pool2 )
            {
              v13 = WORD1(v17);
              *((_DWORD *)Pool2 + 2) = 808679286;
              v14 = (unsigned __int8 *)(Pool2 + 16);
              *(_QWORD *)Pool2 = p_WaitListHead;
              memset(Pool2 + 16, 0, v13);
              FirstP2PIE = GetAttributeBytes((struct _WFD_ATTRIBUTE_INFO *)&v17, v14, 0, WORD1(v17), 0);
              if ( FirstP2PIE )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 400, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                if ( v14 )
                {
                  if ( *((_QWORD *)v14 - 2) )
                    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 - 2), v14 - 16);
                  else
                    ExFreePoolWithTag(v14 - 16, *((_DWORD *)v14 - 2));
                }
              }
              else
              {
                v15 = WORD1(v17);
                *a4 = v14;
                *a3 = v15;
              }
            }
            else
            {
              FirstP2PIE = -1073741670;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                v8 = 399;
                goto LABEL_34;
              }
            }
            return FirstP2PIE;
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
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_23;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v8 = 396;
    goto LABEL_34;
  }
  return FirstP2PIE;
}

```

## disassembly

```asm
0x14007f73c  mov     rax, rsp
0x14007f73f  mov     [rax+18h], rbx
0x14007f743  mov     [rax+20h], rdi
0x14007f747  mov     [rax+10h], rdx
0x14007f74b  mov     [rax+8], ecx
0x14007f74e  push    rbp
0x14007f74f  push    r14
0x14007f751  push    r15
0x14007f753  mov     rbp, rsp
0x14007f756  sub     rsp, 50h
0x14007f75a  xor     eax, eax
0x14007f75c  xorps   xmm0, xmm0
0x14007f75f  mov     [rbp+var_10], rax
0x14007f763  mov     r15, r9
0x14007f766  mov     r14, r8
0x14007f769  movups  [rbp+var_20], xmm0
0x14007f76d  test    r8, r8
0x14007f770  jnz     short loc_14007F798
0x14007f772  mov     ebx, 0C000000Dh
0x14007f777  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f77e  lea     rax, WPP_GLOBAL_Control
0x14007f785  cmp     rcx, rax
0x14007f788  jz      loc_14007F98A
0x14007f78e  mov     edx, 18Bh
0x14007f793  jmp     loc_14007F97A
0x14007f798  lea     rdx, [rbp+arg_0]; unsigned int *
0x14007f79c  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x14007f7a0  call    ?FindFirstP2PIE@@YAJPEAPEAEPEAK@Z; FindFirstP2PIE(uchar * *,ulong *)
0x14007f7a5  mov     ebx, eax
0x14007f7a7  test    eax, eax
0x14007f7a9  jz      short loc_14007F7CC
0x14007f7ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f7b2  lea     rax, WPP_GLOBAL_Control
0x14007f7b9  cmp     rcx, rax
0x14007f7bc  jz      loc_14007F98A
0x14007f7c2  mov     edx, 18Ch
0x14007f7c7  jmp     loc_14007F97A
0x14007f7cc  mov     edx, [rbp+arg_0]; unsigned int
0x14007f7cf  lea     r9, [rbp+var_20]; struct _WFD_ATTRIBUTE_INFO *
0x14007f7d3  mov     rcx, [rbp+arg_8]; unsigned __int8 *
0x14007f7d7  mov     r8b, 0Bh; unsigned __int8
0x14007f7da  call    ?FindAttributeInFragmentedP2PIEs@@YAJPEAEKEPEAU_WFD_ATTRIBUTE_INFO@@@Z; FindAttributeInFragmentedP2PIEs(uchar *,ulong,uchar,_WFD_ATTRIBUTE_INFO *)
0x14007f7df  mov     ebx, eax
0x14007f7e1  test    eax, eax
0x14007f7e3  jz      short loc_14007F806
0x14007f7e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f7ec  lea     rax, WPP_GLOBAL_Control
0x14007f7f3  cmp     rcx, rax
0x14007f7f6  jz      loc_14007F98A
0x14007f7fc  mov     edx, 18Dh
0x14007f801  jmp     loc_14007F97A
0x14007f806  mov     eax, 5
0x14007f80b  cmp     ax, word ptr [rbp+var_20+2]
0x14007f80f  jbe     short loc_14007F837
0x14007f811  mov     ebx, 0C0230015h
0x14007f816  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f81d  lea     rax, WPP_GLOBAL_Control
0x14007f824  cmp     rcx, rax
0x14007f827  jz      loc_14007F98A
0x14007f82d  mov     edx, 18Eh
0x14007f832  jmp     loc_14007F97A
0x14007f837  movzx   eax, word ptr [rbp+var_20+2]
0x14007f83b  add     eax, 10h
0x14007f83e  cmp     eax, 10h
0x14007f841  jb      loc_14007F95D
0x14007f847  mov     ecx, 40h ; '@'
0x14007f84c  mov     edi, 30337776h
0x14007f851  cmp     eax, ecx
0x14007f853  ja      short loc_14007F85E
0x14007f855  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14007f85c  jmp     short loc_14007F88C
0x14007f85e  cmp     eax, 100h
0x14007f863  ja      short loc_14007F86E
0x14007f865  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007f86c  jmp     short loc_14007F88C
0x14007f86e  cmp     eax, 400h
0x14007f873  ja      short loc_14007F87E
0x14007f875  lea     rbx, Lookaside
0x14007f87c  jmp     short loc_14007F88C
0x14007f87e  cmp     eax, 800h
0x14007f883  ja      short loc_14007F89D
0x14007f885  lea     rbx, stru_1400B0180
0x14007f88c  mov     rcx, rbx; Lookaside
0x14007f88f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007f896  nop     dword ptr [rax+rax+00h]
0x14007f89b  jmp     short loc_14007F8B0
0x14007f89d  xor     ebx, ebx
0x14007f89f  mov     edx, eax
0x14007f8a1  mov     r8d, edi
0x14007f8a4  call    cs:__imp_ExAllocatePool2
0x14007f8ab  nop     dword ptr [rax+rax+00h]
0x14007f8b0  test    rax, rax
0x14007f8b3  jz      loc_14007F95D
0x14007f8b9  movzx   r8d, word ptr [rbp+var_20+2]; Size
0x14007f8be  xor     edx, edx; Val
0x14007f8c0  mov     [rax+8], edi
0x14007f8c3  lea     rdi, [rax+10h]
0x14007f8c7  mov     rcx, rdi; void *
0x14007f8ca  mov     [rax], rbx
0x14007f8cd  call    memset
0x14007f8d2  movzx   r9d, word ptr [rbp+var_20+2]; unsigned __int16
0x14007f8d7  lea     rcx, [rbp+var_20]; struct _WFD_ATTRIBUTE_INFO *
0x14007f8db  xor     eax, eax
0x14007f8dd  xor     r8d, r8d; unsigned __int8
0x14007f8e0  mov     rdx, rdi; unsigned __int8 *
0x14007f8e3  mov     [rsp+50h+var_30], ax; unsigned __int16
0x14007f8e8  call    ?GetAttributeBytes@@YAJPEAU_WFD_ATTRIBUTE_INFO@@PEAEEGG@Z; GetAttributeBytes(_WFD_ATTRIBUTE_INFO *,uchar *,uchar,ushort,ushort)
0x14007f8ed  mov     ebx, eax
0x14007f8ef  test    eax, eax
0x14007f8f1  jz      short loc_14007F951
0x14007f8f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f8fa  lea     rax, WPP_GLOBAL_Control
0x14007f901  cmp     rcx, rax
0x14007f904  jz      short loc_14007F91B
0x14007f906  mov     rcx, [rcx+18h]
0x14007f90a  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007f911  mov     edx, 190h
0x14007f916  call    WPP_SF_
0x14007f91b  test    rdi, rdi
0x14007f91e  jz      short loc_14007F98A
0x14007f920  lea     rcx, [rdi-10h]; P
0x14007f924  mov     rax, [rcx]
0x14007f927  test    rax, rax
0x14007f92a  jz      short loc_14007F940
0x14007f92c  mov     rdx, rcx; Entry
0x14007f92f  mov     rcx, rax; Lookaside
0x14007f932  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007f939  nop     dword ptr [rax+rax+00h]
0x14007f93e  jmp     short loc_14007F98A
0x14007f940  mov     edx, [rcx+8]; Tag
0x14007f943  call    cs:__imp_ExFreePoolWithTag
0x14007f94a  nop     dword ptr [rax+rax+00h]
0x14007f94f  jmp     short loc_14007F98A
0x14007f951  movzx   eax, word ptr [rbp+var_20+2]
0x14007f955  mov     [r15], rdi
0x14007f958  mov     [r14], eax
0x14007f95b  jmp     short loc_14007F98A
0x14007f95d  mov     ebx, 0C000009Ah
0x14007f962  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f969  lea     rax, WPP_GLOBAL_Control
0x14007f970  cmp     rcx, rax
0x14007f973  jz      short loc_14007F98A
0x14007f975  mov     edx, 18Fh
0x14007f97a  mov     rcx, [rcx+18h]
0x14007f97e  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007f985  call    WPP_SF_
0x14007f98a  lea     r11, [rsp+50h+var_s0]
0x14007f98f  mov     eax, ebx
0x14007f991  mov     rbx, [r11+30h]
0x14007f995  mov     rdi, [r11+38h]
0x14007f999  mov     rsp, r11
0x14007f99c  pop     r15
0x14007f99e  pop     r14
0x14007f9a0  pop     rbp
0x14007f9a1  retn
```
