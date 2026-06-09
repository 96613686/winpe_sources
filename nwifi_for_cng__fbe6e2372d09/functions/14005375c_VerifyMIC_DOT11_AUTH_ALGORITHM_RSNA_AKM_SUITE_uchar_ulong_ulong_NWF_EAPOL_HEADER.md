# VerifyMIC(_DOT11_AUTH_ALGORITHM,RSNA_AKM_SUITE,uchar *,ulong,ulong,NWF_EAPOL_HEADER *)

- ea: `0x14005375c`
- end: `0x140053941`
- name: `?VerifyMIC@@YAJW4_DOT11_AUTH_ALGORITHM@@W4RSNA_AKM_SUITE@@PEAEKKPEFAUNWF_EAPOL_HEADER@@@Z`
- size: `485`
- prototype: `int(enum _DOT11_AUTH_ALGORITHM, enum RSNA_AKM_SUITE, unsigned __int8 *, unsigned int, unsigned int, struct NWF_EAPOL_HEADER *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140044320`
- `0x1400455c8`
- `0x140050e58`

## callees

- `0x14000d21c`
- `0x140041590`
- `0x14005375c`
- `0x14009bbb0`
- `0x14009bcc0`
- `0x14009bfc0`
- `0x14009c4e0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400537f4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400537f4`
- `ntoskrnl!ExAllocatePool2` at `0x14005380c`
- `ntoskrnl!ExAllocatePool2` at `0x14005380c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400538ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400538ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053900`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053900`

## pseudocode

```c
__int64 __fastcall VerifyMIC(
        enum _DOT11_AUTH_ALGORITHM a1,
        enum RSNA_AKM_SUITE a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int Size,
        struct NWF_EAPOL_HEADER *Src)
{
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
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_10;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v11, 2053731191);
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
  v16 = CalculateMIC(*((_BYTE *)Src + 6) & 7, v15, a2, a4, a3, v10, v14, v18, Buf1);
  if ( v16 >= 0 )
  {
    if ( memcmp(Buf1, (char *)Src + 81, Size) )
    {
      v16 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
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
0x14005375c  mov     [rsp+arg_0], rbx
0x140053761  push    rbp
0x140053762  push    rsi
0x140053763  push    rdi
0x140053764  push    r12
0x140053766  push    r13
0x140053768  push    r14
0x14005376a  push    r15
0x14005376c  sub     rsp, 0A0h
0x140053773  mov     rax, cs:__security_cookie
0x14005377a  xor     rax, rsp
0x14005377d  mov     [rsp+0D8h+var_48], rax
0x140053785  mov     rsi, [rsp+0D8h+Src]
0x14005378d  mov     r13d, r9d
0x140053790  mov     r12, r8
0x140053793  mov     r15d, edx
0x140053796  movzx   eax, word ptr [rsi+2]
0x14005379a  ror     ax, 8
0x14005379e  movzx   ebp, ax
0x1400537a1  add     ebp, 4
0x1400537a4  lea     eax, [rbp+10h]
0x1400537a7  cmp     eax, 10h
0x1400537aa  jb      loc_14005390E
0x1400537b0  mov     edi, 7A697377h
0x1400537b5  cmp     eax, 40h ; '@'
0x1400537b8  ja      short loc_1400537C3
0x1400537ba  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400537c1  jmp     short loc_1400537F1
0x1400537c3  cmp     eax, 100h
0x1400537c8  ja      short loc_1400537D3
0x1400537ca  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400537d1  jmp     short loc_1400537F1
0x1400537d3  cmp     eax, 400h
0x1400537d8  ja      short loc_1400537E3
0x1400537da  lea     rbx, Lookaside
0x1400537e1  jmp     short loc_1400537F1
0x1400537e3  cmp     eax, 800h
0x1400537e8  ja      short loc_140053802
0x1400537ea  lea     rbx, stru_1400B31C0
0x1400537f1  mov     rcx, rbx; Lookaside
0x1400537f4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400537fb  nop     dword ptr [rax+rax+00h]
0x140053800  jmp     short loc_140053818
0x140053802  xor     ebx, ebx
0x140053804  mov     edx, eax
0x140053806  mov     r8d, edi
0x140053809  lea     ecx, [rbx+40h]
0x14005380c  call    cs:__imp_ExAllocatePool2
0x140053813  nop     dword ptr [rax+rax+00h]
0x140053818  test    rax, rax
0x14005381b  jz      loc_14005390E
0x140053821  mov     [rax+8], edi
0x140053824  mov     rdx, rsi; Src
0x140053827  lea     rdi, [rax+10h]
0x14005382b  mov     r8d, ebp; Size
0x14005382e  mov     rcx, rdi; void *
0x140053831  mov     [rax], rbx
0x140053834  call    memmove
0x140053839  mov     ebx, dword ptr [rsp+0D8h+Size]
0x140053840  lea     rcx, [rdi+51h]; void *
0x140053844  mov     r8d, ebx; Size
0x140053847  xor     edx, edx; Val
0x140053849  mov     r14d, ebx
0x14005384c  call    memset
0x140053851  xor     edx, edx; Val
0x140053853  lea     rcx, [rsp+0D8h+Buf1]; void *
0x140053858  lea     r8d, [rdx+40h]; Size
0x14005385c  call    memset
0x140053861  mov     al, [rsi+6]
0x140053864  mov     r9d, r13d; unsigned int
0x140053867  and     al, 7
0x140053869  mov     r8d, r15d; enum RSNA_AKM_SUITE
0x14005386c  movzx   ecx, al; unsigned __int16
0x14005386f  lea     rax, [rsp+0D8h+Buf1]
0x140053874  mov     [rsp+0D8h+var_98], rax; unsigned __int8 *
0x140053879  mov     dword ptr [rsp+0D8h+var_A0], ebx; Size
0x14005387d  mov     [rsp+0D8h+var_A8], rdi; unsigned __int8 *
0x140053882  mov     [rsp+0D8h+var_B0], ebp; unsigned int
0x140053886  mov     [rsp+0D8h+var_B8], r12; unsigned __int8 *
0x14005388b  call    ?CalculateMIC@@YAJGW4_DOT11_AUTH_ALGORITHM@@W4RSNA_AKM_SUITE@@KPEAEK2K2@Z; CalculateMIC(ushort,_DOT11_AUTH_ALGORITHM,RSNA_AKM_SUITE,ulong,uchar *,ulong,uchar *,ulong,uchar *)
0x140053890  mov     ebx, eax
0x140053892  test    eax, eax
0x140053894  js      short loc_1400538D8
0x140053896  lea     rdx, [rsi+51h]; Buf2
0x14005389a  mov     r8d, r14d; Size
0x14005389d  lea     rcx, [rsp+0D8h+Buf1]; Buf1
0x1400538a2  call    memcmp
0x1400538a7  test    eax, eax
0x1400538a9  jz      short loc_1400538D8
0x1400538ab  mov     ebx, 0C0000001h
0x1400538b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400538b7  lea     rax, WPP_GLOBAL_Control
0x1400538be  cmp     rcx, rax
0x1400538c1  jz      short loc_1400538D8
0x1400538c3  mov     rcx, [rcx+18h]
0x1400538c7  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400538ce  mov     edx, 34h ; '4'
0x1400538d3  call    WPP_SF_
0x1400538d8  test    rdi, rdi
0x1400538db  jz      short loc_140053913
0x1400538dd  lea     rcx, [rdi-10h]; P
0x1400538e1  mov     rax, [rcx]
0x1400538e4  test    rax, rax
0x1400538e7  jz      short loc_1400538FD
0x1400538e9  mov     rdx, rcx; Entry
0x1400538ec  mov     rcx, rax; Lookaside
0x1400538ef  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400538f6  nop     dword ptr [rax+rax+00h]
0x1400538fb  jmp     short loc_140053913
0x1400538fd  mov     edx, [rcx+8]; Tag
0x140053900  call    cs:__imp_ExFreePoolWithTag
0x140053907  nop     dword ptr [rax+rax+00h]
0x14005390c  jmp     short loc_140053913
0x14005390e  mov     ebx, 0C000009Ah
0x140053913  mov     eax, ebx
0x140053915  mov     rcx, [rsp+0D8h+var_48]
0x14005391d  xor     rcx, rsp; StackCookie
0x140053920  call    __security_check_cookie
0x140053925  mov     rbx, [rsp+0D8h+arg_0]
0x14005392d  add     rsp, 0A0h
0x140053934  pop     r15
0x140053936  pop     r14
0x140053938  pop     r13
0x14005393a  pop     r12
0x14005393c  pop     rdi
0x14005393d  pop     rsi
0x14005393e  pop     rbp
0x14005393f  retn
```
