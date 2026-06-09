# VerifyMIC(_DOT11_AUTH_ALGORITHM,RSNA_AKM_SUITE,uchar *,ulong,ulong,NWF_EAPOL_HEADER *)

- ea: `0x140051f94`
- end: `0x140052179`
- name: `?VerifyMIC@@YAJW4_DOT11_AUTH_ALGORITHM@@W4RSNA_AKM_SUITE@@PEAEKKPEFAUNWF_EAPOL_HEADER@@@Z`
- size: `485`
- prototype: `int(enum _DOT11_AUTH_ALGORITHM, enum RSNA_AKM_SUITE, unsigned __int8 *, unsigned int, unsigned int, struct NWF_EAPOL_HEADER *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400437a0`
- `0x140044a48`
- `0x14004f690`

## callees

- `0x14000d22c`
- `0x140040af4`
- `0x140051f94`
- `0x14009a3d0`
- `0x14009a4c0`
- `0x14009a7c0`
- `0x14009ace0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005202c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005202c`
- `ntoskrnl!ExAllocatePool2` at `0x140052044`
- `ntoskrnl!ExAllocatePool2` at `0x140052044`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140052127`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140052127`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052138`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052138`

## pseudocode

```c
__int64 __fastcall VerifyMIC(
        enum _DOT11_AUTH_ALGORITHM a1,
        enum RSNA_AKM_SUITE a2,
        unsigned __int8 *a3,
        __int64 a4,
        unsigned int Size,
        struct NWF_EAPOL_HEADER *Src)
{
  unsigned int v6; // r13d
  unsigned __int16 v9; // ax
  unsigned int v10; // ebp
  unsigned int v11; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  unsigned __int8 *v14; // rdi
  enum _DOT11_AUTH_ALGORITHM v15; // edx
  int v16; // ebx
  size_t v18; // [rsp+38h] [rbp-A0h]
  unsigned __int8 Buf1[64]; // [rsp+50h] [rbp-88h] BYREF

  v6 = a4;
  v9 = __ROR2__(*((_WORD *)Src + 1), 8);
  v10 = v9 + 4;
  v11 = v9 + 20;
  if ( v11 < 0x10 )
    return (unsigned int)-1073741670;
  if ( v11 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_10:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_12;
  }
  if ( v11 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_10;
  }
  if ( v11 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_10;
  }
  if ( v11 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_10;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v11, 2053731191, a4);
LABEL_12:
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  *((_DWORD *)Pool2 + 2) = 2053731191;
  v14 = (unsigned __int8 *)(Pool2 + 16);
  *(_QWORD *)Pool2 = p_DeviceQueue;
  memmove(Pool2 + 16, Src, v10);
  memset(v14 + 81, 0, Size);
  memset(Buf1, 0, sizeof(Buf1));
  LODWORD(v18) = Size;
  v16 = CalculateMIC(*((_BYTE *)Src + 6) & 7, v15, a2, v6, a3, v10, v14, v18, Buf1);
  if ( v16 >= 0 )
  {
    if ( memcmp(Buf1, (char *)Src + 81, Size) )
    {
      v16 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_e90d411d816e312466897e39e745b158_Traceguids);
    }
  }
  if ( v14 )
  {
    if ( *((_QWORD *)v14 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 - 2), v14 - 16);
    else
      ExFreePoolWithTag(v14 - 16, *((_DWORD *)v14 - 2));
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140051f94  mov     [rsp+arg_0], rbx
0x140051f99  push    rbp
0x140051f9a  push    rsi
0x140051f9b  push    rdi
0x140051f9c  push    r12
0x140051f9e  push    r13
0x140051fa0  push    r14
0x140051fa2  push    r15
0x140051fa4  sub     rsp, 0A0h
0x140051fab  mov     rax, cs:__security_cookie
0x140051fb2  xor     rax, rsp
0x140051fb5  mov     [rsp+0D8h+var_48], rax
0x140051fbd  mov     rsi, [rsp+0D8h+Src]
0x140051fc5  mov     r13d, r9d
0x140051fc8  mov     r12, r8
0x140051fcb  mov     r15d, edx
0x140051fce  movzx   eax, word ptr [rsi+2]
0x140051fd2  ror     ax, 8
0x140051fd6  movzx   ebp, ax
0x140051fd9  add     ebp, 4
0x140051fdc  lea     eax, [rbp+10h]
0x140051fdf  cmp     eax, 10h
0x140051fe2  jb      loc_140052146
0x140051fe8  mov     edi, 7A697377h
0x140051fed  cmp     eax, 40h ; '@'
0x140051ff0  ja      short loc_140051FFB
0x140051ff2  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140051ff9  jmp     short loc_140052029
0x140051ffb  cmp     eax, 100h
0x140052000  ja      short loc_14005200B
0x140052002  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140052009  jmp     short loc_140052029
0x14005200b  cmp     eax, 400h
0x140052010  ja      short loc_14005201B
0x140052012  lea     rbx, Lookaside
0x140052019  jmp     short loc_140052029
0x14005201b  cmp     eax, 800h
0x140052020  ja      short loc_14005203A
0x140052022  lea     rbx, stru_1400B0180
0x140052029  mov     rcx, rbx; Lookaside
0x14005202c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140052033  nop     dword ptr [rax+rax+00h]
0x140052038  jmp     short loc_140052050
0x14005203a  xor     ebx, ebx
0x14005203c  mov     edx, eax
0x14005203e  mov     r8d, edi
0x140052041  lea     ecx, [rbx+40h]
0x140052044  call    cs:__imp_ExAllocatePool2
0x14005204b  nop     dword ptr [rax+rax+00h]
0x140052050  test    rax, rax
0x140052053  jz      loc_140052146
0x140052059  mov     [rax+8], edi
0x14005205c  mov     rdx, rsi; Src
0x14005205f  lea     rdi, [rax+10h]
0x140052063  mov     r8d, ebp; Size
0x140052066  mov     rcx, rdi; void *
0x140052069  mov     [rax], rbx
0x14005206c  call    memmove
0x140052071  mov     ebx, dword ptr [rsp+0D8h+Size]
0x140052078  lea     rcx, [rdi+51h]; void *
0x14005207c  mov     r8d, ebx; Size
0x14005207f  xor     edx, edx; Val
0x140052081  mov     r14d, ebx
0x140052084  call    memset
0x140052089  xor     edx, edx; Val
0x14005208b  lea     rcx, [rsp+0D8h+Buf1]; void *
0x140052090  lea     r8d, [rdx+40h]; Size
0x140052094  call    memset
0x140052099  mov     al, [rsi+6]
0x14005209c  mov     r9d, r13d; unsigned int
0x14005209f  and     al, 7
0x1400520a1  mov     r8d, r15d; enum RSNA_AKM_SUITE
0x1400520a4  movzx   ecx, al; unsigned __int16
0x1400520a7  lea     rax, [rsp+0D8h+Buf1]
0x1400520ac  mov     [rsp+0D8h+var_98], rax; unsigned __int8 *
0x1400520b1  mov     dword ptr [rsp+0D8h+var_A0], ebx; Size
0x1400520b5  mov     [rsp+0D8h+var_A8], rdi; unsigned __int8 *
0x1400520ba  mov     [rsp+0D8h+var_B0], ebp; unsigned int
0x1400520be  mov     [rsp+0D8h+var_B8], r12; unsigned __int8 *
0x1400520c3  call    ?CalculateMIC@@YAJGW4_DOT11_AUTH_ALGORITHM@@W4RSNA_AKM_SUITE@@KPEAEK2K2@Z; CalculateMIC(ushort,_DOT11_AUTH_ALGORITHM,RSNA_AKM_SUITE,ulong,uchar *,ulong,uchar *,ulong,uchar *)
0x1400520c8  mov     ebx, eax
0x1400520ca  test    eax, eax
0x1400520cc  js      short loc_140052110
0x1400520ce  lea     rdx, [rsi+51h]; Buf2
0x1400520d2  mov     r8d, r14d; Size
0x1400520d5  lea     rcx, [rsp+0D8h+Buf1]; Buf1
0x1400520da  call    memcmp
0x1400520df  test    eax, eax
0x1400520e1  jz      short loc_140052110
0x1400520e3  mov     ebx, 0C0000001h
0x1400520e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400520ef  lea     rax, WPP_GLOBAL_Control
0x1400520f6  cmp     rcx, rax
0x1400520f9  jz      short loc_140052110
0x1400520fb  mov     rcx, [rcx+18h]
0x1400520ff  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140052106  mov     edx, 34h ; '4'
0x14005210b  call    WPP_SF_
0x140052110  test    rdi, rdi
0x140052113  jz      short loc_14005214B
0x140052115  lea     rcx, [rdi-10h]; P
0x140052119  mov     rax, [rcx]
0x14005211c  test    rax, rax
0x14005211f  jz      short loc_140052135
0x140052121  mov     rdx, rcx; Entry
0x140052124  mov     rcx, rax; Lookaside
0x140052127  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005212e  nop     dword ptr [rax+rax+00h]
0x140052133  jmp     short loc_14005214B
0x140052135  mov     edx, [rcx+8]; Tag
0x140052138  call    cs:__imp_ExFreePoolWithTag
0x14005213f  nop     dword ptr [rax+rax+00h]
0x140052144  jmp     short loc_14005214B
0x140052146  mov     ebx, 0C000009Ah
0x14005214b  mov     eax, ebx
0x14005214d  mov     rcx, [rsp+0D8h+var_48]
0x140052155  xor     rcx, rsp; StackCookie
0x140052158  call    __security_check_cookie
0x14005215d  mov     rbx, [rsp+0D8h+arg_0]
0x140052165  add     rsp, 0A0h
0x14005216c  pop     r15
0x14005216e  pop     r14
0x140052170  pop     r13
0x140052172  pop     r12
0x140052174  pop     rdi
0x140052175  pop     rsi
0x140052176  pop     rbp
0x140052177  retn
```
