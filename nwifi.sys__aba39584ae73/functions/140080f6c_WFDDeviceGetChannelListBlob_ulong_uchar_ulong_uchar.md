# WFDDeviceGetChannelListBlob(ulong,uchar *,ulong *,uchar * *)

- ea: `0x140080f6c`
- end: `0x1400811d3`
- name: `?WFDDeviceGetChannelListBlob@@YAJKPEAEPEAKPEAPEAE@Z`
- size: `615`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int8 *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140081d8c`
- `0x140084b5c`

## callees

- `0x14000d21c`
- `0x140080f6c`
- `0x140097ce8`
- `0x140097df4`
- `0x140097e90`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400810bf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400810bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400810d4`
- `ntoskrnl!ExAllocatePool2` at `0x1400810d4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140081162`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140081162`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081173`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081173`

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
  unsigned int v9; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  char *Pool2; // rax
  size_t v12; // r8
  unsigned __int8 *v13; // rdi
  unsigned int v14; // eax
  __int128 v16; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+40h] [rbp-10h]
  unsigned int v18; // [rsp+70h] [rbp+20h] BYREF
  unsigned __int8 *v19; // [rsp+78h] [rbp+28h] BYREF

  v19 = a2;
  v18 = a1;
  v17 = 0;
  v16 = 0;
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
  FirstP2PIE = FindFirstP2PIE(&v19, &v18);
  if ( !FirstP2PIE )
  {
    FirstP2PIE = FindAttributeInFragmentedP2PIEs(v19, v18, 0xBu, (struct _WFD_ATTRIBUTE_INFO *)&v16);
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
    if ( WORD1(v16) < 5u )
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
    v9 = WORD1(v16) + 16;
    if ( v9 > 0x40 )
    {
      if ( v9 > 0x100 )
      {
        if ( v9 > 0x400 )
        {
          if ( v9 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (char *)ExAllocatePool2(64, v9, 808679286);
LABEL_23:
            if ( Pool2 )
            {
              v12 = WORD1(v16);
              *((_DWORD *)Pool2 + 2) = 808679286;
              v13 = (unsigned __int8 *)(Pool2 + 16);
              *(_QWORD *)Pool2 = p_WaitListHead;
              memset(Pool2 + 16, 0, v12);
              FirstP2PIE = GetAttributeBytes((struct _WFD_ATTRIBUTE_INFO *)&v16, v13, 0, WORD1(v16), 0);
              if ( FirstP2PIE )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 400, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                if ( v13 )
                {
                  if ( *((_QWORD *)v13 - 2) )
                    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 - 2), v13 - 16);
                  else
                    ExFreePoolWithTag(v13 - 16, *((_DWORD *)v13 - 2));
                }
              }
              else
              {
                v14 = WORD1(v16);
                *a4 = v13;
                *a3 = v14;
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
0x140080f6c  mov     rax, rsp
0x140080f6f  mov     [rax+18h], rbx
0x140080f73  mov     [rax+20h], rdi
0x140080f77  mov     [rax+10h], rdx
0x140080f7b  mov     [rax+8], ecx
0x140080f7e  push    rbp
0x140080f7f  push    r14
0x140080f81  push    r15
0x140080f83  mov     rbp, rsp
0x140080f86  sub     rsp, 50h
0x140080f8a  xor     eax, eax
0x140080f8c  xorps   xmm0, xmm0
0x140080f8f  mov     [rbp+var_10], rax
0x140080f93  mov     r15, r9
0x140080f96  mov     r14, r8
0x140080f99  movups  [rbp+var_20], xmm0
0x140080f9d  test    r8, r8
0x140080fa0  jnz     short loc_140080FC8
0x140080fa2  mov     ebx, 0C000000Dh
0x140080fa7  mov     rcx, cs:WPP_GLOBAL_Control
0x140080fae  lea     rax, WPP_GLOBAL_Control
0x140080fb5  cmp     rcx, rax
0x140080fb8  jz      loc_1400811BA
0x140080fbe  mov     edx, 18Bh
0x140080fc3  jmp     loc_1400811AA
0x140080fc8  lea     rdx, [rbp+arg_0]; unsigned int *
0x140080fcc  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x140080fd0  call    ?FindFirstP2PIE@@YAJPEAPEAEPEAK@Z; FindFirstP2PIE(uchar * *,ulong *)
0x140080fd5  mov     ebx, eax
0x140080fd7  test    eax, eax
0x140080fd9  jz      short loc_140080FFC
0x140080fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x140080fe2  lea     rax, WPP_GLOBAL_Control
0x140080fe9  cmp     rcx, rax
0x140080fec  jz      loc_1400811BA
0x140080ff2  mov     edx, 18Ch
0x140080ff7  jmp     loc_1400811AA
0x140080ffc  mov     edx, [rbp+arg_0]; unsigned int
0x140080fff  lea     r9, [rbp+var_20]; struct _WFD_ATTRIBUTE_INFO *
0x140081003  mov     rcx, [rbp+arg_8]; unsigned __int8 *
0x140081007  mov     r8b, 0Bh; unsigned __int8
0x14008100a  call    ?FindAttributeInFragmentedP2PIEs@@YAJPEAEKEPEAU_WFD_ATTRIBUTE_INFO@@@Z; FindAttributeInFragmentedP2PIEs(uchar *,ulong,uchar,_WFD_ATTRIBUTE_INFO *)
0x14008100f  mov     ebx, eax
0x140081011  test    eax, eax
0x140081013  jz      short loc_140081036
0x140081015  mov     rcx, cs:WPP_GLOBAL_Control
0x14008101c  lea     rax, WPP_GLOBAL_Control
0x140081023  cmp     rcx, rax
0x140081026  jz      loc_1400811BA
0x14008102c  mov     edx, 18Dh
0x140081031  jmp     loc_1400811AA
0x140081036  mov     eax, 5
0x14008103b  cmp     ax, word ptr [rbp+var_20+2]
0x14008103f  jbe     short loc_140081067
0x140081041  mov     ebx, 0C0230015h
0x140081046  mov     rcx, cs:WPP_GLOBAL_Control
0x14008104d  lea     rax, WPP_GLOBAL_Control
0x140081054  cmp     rcx, rax
0x140081057  jz      loc_1400811BA
0x14008105d  mov     edx, 18Eh
0x140081062  jmp     loc_1400811AA
0x140081067  movzx   eax, word ptr [rbp+var_20+2]
0x14008106b  add     eax, 10h
0x14008106e  cmp     eax, 10h
0x140081071  jb      loc_14008118D
0x140081077  mov     ecx, 40h ; '@'
0x14008107c  mov     edi, 30337776h
0x140081081  cmp     eax, ecx
0x140081083  ja      short loc_14008108E
0x140081085  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14008108c  jmp     short loc_1400810BC
0x14008108e  cmp     eax, 100h
0x140081093  ja      short loc_14008109E
0x140081095  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14008109c  jmp     short loc_1400810BC
0x14008109e  cmp     eax, 400h
0x1400810a3  ja      short loc_1400810AE
0x1400810a5  lea     rbx, Lookaside
0x1400810ac  jmp     short loc_1400810BC
0x1400810ae  cmp     eax, 800h
0x1400810b3  ja      short loc_1400810CD
0x1400810b5  lea     rbx, stru_1400B31C0
0x1400810bc  mov     rcx, rbx; Lookaside
0x1400810bf  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400810c6  nop     dword ptr [rax+rax+00h]
0x1400810cb  jmp     short loc_1400810E0
0x1400810cd  xor     ebx, ebx
0x1400810cf  mov     edx, eax
0x1400810d1  mov     r8d, edi
0x1400810d4  call    cs:__imp_ExAllocatePool2
0x1400810db  nop     dword ptr [rax+rax+00h]
0x1400810e0  test    rax, rax
0x1400810e3  jz      loc_14008118D
0x1400810e9  movzx   r8d, word ptr [rbp+var_20+2]; Size
0x1400810ee  xor     edx, edx; Val
0x1400810f0  mov     [rax+8], edi
0x1400810f3  lea     rdi, [rax+10h]
0x1400810f7  mov     rcx, rdi; void *
0x1400810fa  mov     [rax], rbx
0x1400810fd  call    memset
0x140081102  movzx   r9d, word ptr [rbp+var_20+2]; unsigned __int16
0x140081107  lea     rcx, [rbp+var_20]; struct _WFD_ATTRIBUTE_INFO *
0x14008110b  xor     eax, eax
0x14008110d  xor     r8d, r8d; unsigned __int8
0x140081110  mov     rdx, rdi; unsigned __int8 *
0x140081113  mov     [rsp+50h+var_30], ax; unsigned __int16
0x140081118  call    ?GetAttributeBytes@@YAJPEAU_WFD_ATTRIBUTE_INFO@@PEAEEGG@Z; GetAttributeBytes(_WFD_ATTRIBUTE_INFO *,uchar *,uchar,ushort,ushort)
0x14008111d  mov     ebx, eax
0x14008111f  test    eax, eax
0x140081121  jz      short loc_140081181
0x140081123  mov     rcx, cs:WPP_GLOBAL_Control
0x14008112a  lea     rax, WPP_GLOBAL_Control
0x140081131  cmp     rcx, rax
0x140081134  jz      short loc_14008114B
0x140081136  mov     rcx, [rcx+18h]
0x14008113a  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140081141  mov     edx, 190h
0x140081146  call    WPP_SF_
0x14008114b  test    rdi, rdi
0x14008114e  jz      short loc_1400811BA
0x140081150  lea     rcx, [rdi-10h]; P
0x140081154  mov     rax, [rcx]
0x140081157  test    rax, rax
0x14008115a  jz      short loc_140081170
0x14008115c  mov     rdx, rcx; Entry
0x14008115f  mov     rcx, rax; Lookaside
0x140081162  call    cs:__imp_ExFreeToNPagedLookasideList
0x140081169  nop     dword ptr [rax+rax+00h]
0x14008116e  jmp     short loc_1400811BA
0x140081170  mov     edx, [rcx+8]; Tag
0x140081173  call    cs:__imp_ExFreePoolWithTag
0x14008117a  nop     dword ptr [rax+rax+00h]
0x14008117f  jmp     short loc_1400811BA
0x140081181  movzx   eax, word ptr [rbp+var_20+2]
0x140081185  mov     [r15], rdi
0x140081188  mov     [r14], eax
0x14008118b  jmp     short loc_1400811BA
0x14008118d  mov     ebx, 0C000009Ah
0x140081192  mov     rcx, cs:WPP_GLOBAL_Control
0x140081199  lea     rax, WPP_GLOBAL_Control
0x1400811a0  cmp     rcx, rax
0x1400811a3  jz      short loc_1400811BA
0x1400811a5  mov     edx, 18Fh
0x1400811aa  mov     rcx, [rcx+18h]
0x1400811ae  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400811b5  call    WPP_SF_
0x1400811ba  lea     r11, [rsp+50h+var_s0]
0x1400811bf  mov     eax, ebx
0x1400811c1  mov     rbx, [r11+30h]
0x1400811c5  mov     rdi, [r11+38h]
0x1400811c9  mov     rsp, r11
0x1400811cc  pop     r15
0x1400811ce  pop     r14
0x1400811d0  pop     rbp
0x1400811d1  retn
```
