# NwfQueryByteArray(_ADAPT *,ulong,ulong,DOT11_BYTE_ARRAY * *)

- ea: `0x140038930`
- end: `0x140038bdf`
- name: `?NwfQueryByteArray@@YAHPEAU_ADAPT@@KKPEAPEAUDOT11_BYTE_ARRAY@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(struct _ADAPT *, __int64, unsigned int, struct DOT11_BYTE_ARRAY **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14001a47c`

## callees

- `0x14000d21c`
- `0x140015b0c`
- `0x140030244`
- `0x140038930`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400389cc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400389cc`
- `ntoskrnl!ExAllocatePool2` at `0x1400389e7`
- `ntoskrnl!ExAllocatePool2` at `0x1400389e7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038a96`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038b98`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038a96`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038b98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038aad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038bac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038aad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038bac`

## pseudocode

```c
__int64 __fastcall NwfQueryByteArray(struct _ADAPT *a1, __int64 a2, unsigned int a3, struct DOT11_BYTE_ARRAY **a4)
{
  unsigned __int64 v4; // r14
  unsigned int v7; // ebp
  struct DOT11_BYTE_ARRAY *v8; // rsi
  unsigned int v9; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  ULONG *v13; // rdi
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  unsigned int *p_uNumOfBytes; // rdi
  unsigned int v18; // ecx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v22; // [rsp+70h] [rbp+18h] BYREF

  v4 = a3;
  v21 = 0;
  v22 = 0;
  if ( a3 == -1 )
  {
    v7 = 16;
    goto LABEL_3;
  }
  v7 = a3 + 16;
  if ( a3 + 16 < a3 )
    return 3221225473LL;
  while ( 1 )
  {
LABEL_3:
    v8 = 0;
    v9 = v7 + 16;
    if ( v7 >= 0xFFFFFFF0 )
    {
LABEL_49:
      v15 = -1073741670;
      goto LABEL_50;
    }
    if ( v9 <= 0x40 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_14:
      Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
      goto LABEL_16;
    }
    if ( v9 <= 0x100 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      goto LABEL_14;
    }
    if ( v9 <= 0x400 )
    {
      p_DeviceQueue = &Lookaside;
      goto LABEL_14;
    }
    if ( v9 <= 0x800 )
    {
      p_DeviceQueue = &stru_1400B31C0;
      goto LABEL_14;
    }
    p_DeviceQueue = 0;
    Pool2 = (char *)ExAllocatePool2(64, v9, 845771639);
LABEL_16:
    v13 = (ULONG *)Pool2;
    if ( !Pool2 )
      goto LABEL_49;
    v8 = (struct DOT11_BYTE_ARRAY *)(Pool2 + 16);
    *(_QWORD *)Pool2 = p_DeviceQueue;
    *((_DWORD *)Pool2 + 2) = 845771639;
    v14 = PtQueryAdapterSyncEx(a1, 0xE050106u, Pool2 + 16, v7, &v21, &v22);
    v15 = v14;
    if ( ((v14 + 1073676268) & 0xFFFFFFFD) != 0 && v14 != -2147483643 )
      break;
    if ( v21 < 0x10 )
      goto LABEL_23;
    if ( v8->Header.Type != 0x80 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v20 = 24;
LABEL_42:
        WPP_SF_(v19->AttachedDevice, v20, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids);
      }
LABEL_43:
      v15 = -1073741823;
LABEL_44:
      if ( v8 )
      {
        if ( *(_QWORD *)v13 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v13, v13);
        else
          ExFreePoolWithTag(v13, v13[2]);
        v8 = 0;
      }
      goto LABEL_50;
    }
    if ( !v8->Header.Revision )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v20 = 25;
        goto LABEL_42;
      }
      goto LABEL_43;
    }
    if ( (unsigned __int64)v7 - 16 >= v4 )
    {
      v15 = -2147483643;
      goto LABEL_50;
    }
LABEL_23:
    v16 = v7;
    v7 = v22;
    if ( v22 <= v16 )
      goto LABEL_43;
    if ( v8 )
    {
      if ( *(_QWORD *)v13 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v13, v13);
      else
        ExFreePoolWithTag(v13, v13[2]);
    }
  }
  if ( v14 )
    goto LABEL_44;
  p_uNumOfBytes = &v8->uNumOfBytes;
  if ( v21 < 0xC || (v18 = *p_uNumOfBytes, *p_uNumOfBytes > v21 - 12) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      p_uNumOfBytes = &v8->uNumOfBytes;
      WPP_SF_lll(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids,
        v21,
        v8->uNumOfBytes,
        v8->uTotalNumOfBytes);
    }
    *p_uNumOfBytes = 0;
    v18 = 0;
  }
  v8->uTotalNumOfBytes = v18;
LABEL_50:
  *a4 = v8;
  return v15;
}

```

## disassembly

```asm
0x140038930  mov     rax, rsp
0x140038933  mov     [rax+8], rbx
0x140038937  mov     [rax+20h], rbp
0x14003893b  mov     [rax+10h], edx
0x14003893e  push    rsi
0x14003893f  push    rdi
0x140038940  push    r12
0x140038942  push    r14
0x140038944  push    r15
0x140038946  sub     rsp, 30h
0x14003894a  mov     r14d, r8d
0x14003894d  mov     r12, r9
0x140038950  mov     dword ptr [rax+10h], 0
0x140038957  mov     r15, rcx
0x14003895a  mov     dword ptr [rax+18h], 0
0x140038961  cmp     r8d, 0FFFFFFFFh
0x140038965  jnz     short loc_140038988
0x140038967  mov     ebp, 10h
0x14003896c  xor     esi, esi
0x14003896e  lea     eax, [rbp+10h]
0x140038971  cmp     eax, 10h
0x140038974  jb      loc_140038BBC
0x14003897a  cmp     eax, 40h ; '@'
0x14003897d  ja      short loc_14003899B
0x14003897f  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140038986  jmp     short loc_1400389C9
0x140038988  lea     ebp, [r14+10h]
0x14003898c  cmp     ebp, r14d
0x14003898f  jnb     short loc_14003896C
0x140038991  mov     eax, 0C0000001h
0x140038996  jmp     loc_140038BC7
0x14003899b  cmp     eax, 100h
0x1400389a0  ja      short loc_1400389AB
0x1400389a2  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400389a9  jmp     short loc_1400389C9
0x1400389ab  cmp     eax, 400h
0x1400389b0  ja      short loc_1400389BB
0x1400389b2  lea     rbx, Lookaside
0x1400389b9  jmp     short loc_1400389C9
0x1400389bb  cmp     eax, 800h
0x1400389c0  ja      short loc_1400389DA
0x1400389c2  lea     rbx, stru_1400B31C0
0x1400389c9  mov     rcx, rbx; Lookaside
0x1400389cc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400389d3  nop     dword ptr [rax+rax+00h]
0x1400389d8  jmp     short loc_1400389F3
0x1400389da  xor     ebx, ebx
0x1400389dc  mov     edx, eax
0x1400389de  mov     r8d, 32697377h
0x1400389e4  lea     ecx, [rbx+40h]
0x1400389e7  call    cs:__imp_ExAllocatePool2
0x1400389ee  nop     dword ptr [rax+rax+00h]
0x1400389f3  mov     rdi, rax
0x1400389f6  test    rax, rax
0x1400389f9  jz      loc_140038BBC
0x1400389ff  lea     rsi, [rax+10h]
0x140038a03  mov     [rax], rbx
0x140038a06  mov     dword ptr [rax+8], 32697377h
0x140038a0d  mov     r9d, ebp; unsigned int
0x140038a10  lea     rax, [rsp+58h+arg_10]
0x140038a15  mov     r8, rsi; void *
0x140038a18  mov     [rsp+58h+var_30], rax; unsigned int *
0x140038a1d  mov     edx, 0E050106h; unsigned int
0x140038a22  lea     rax, [rsp+58h+arg_8]
0x140038a27  mov     rcx, r15; struct _ADAPT *
0x140038a2a  mov     [rsp+58h+var_38], rax; unsigned int *
0x140038a2f  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140038a34  mov     ebx, eax
0x140038a36  lea     ecx, [rax+3FFEFFECh]
0x140038a3c  test    ecx, 0FFFFFFFDh
0x140038a42  jz      short loc_140038A4B
0x140038a44  cmp     eax, 80000005h
0x140038a49  jnz     short loc_140038ABE
0x140038a4b  cmp     [rsp+58h+arg_8], 10h
0x140038a50  jb      short loc_140038A74
0x140038a52  cmp     byte ptr [rsi], 80h
0x140038a55  jnz     loc_140038B5B
0x140038a5b  cmp     byte ptr [rsi+1], 0
0x140038a5f  jz      loc_140038B41
0x140038a65  mov     ecx, ebp
0x140038a67  sub     rcx, 10h
0x140038a6b  cmp     rcx, r14
0x140038a6e  jnb     loc_140038B37
0x140038a74  mov     eax, ebp
0x140038a76  mov     ebp, [rsp+58h+arg_10]
0x140038a7a  cmp     ebp, eax
0x140038a7c  jbe     loc_140038B83
0x140038a82  test    rsi, rsi
0x140038a85  jz      loc_14003896C
0x140038a8b  mov     rcx, [rdi]; Lookaside
0x140038a8e  test    rcx, rcx
0x140038a91  jz      short loc_140038AA7
0x140038a93  mov     rdx, rdi; Entry
0x140038a96  call    cs:__imp_ExFreeToNPagedLookasideList
0x140038a9d  nop     dword ptr [rax+rax+00h]
0x140038aa2  jmp     loc_14003896C
0x140038aa7  mov     edx, [rdi+8]; Tag
0x140038aaa  mov     rcx, rdi; P
0x140038aad  call    cs:__imp_ExFreePoolWithTag
0x140038ab4  nop     dword ptr [rax+rax+00h]
0x140038ab9  jmp     loc_14003896C
0x140038abe  test    eax, eax
0x140038ac0  jnz     loc_140038B88
0x140038ac6  mov     r9d, [rsp+58h+arg_8]
0x140038acb  lea     rdi, [rsi+4]
0x140038acf  cmp     r9d, 0Ch
0x140038ad3  jb      short loc_140038ADF
0x140038ad5  mov     ecx, [rdi]
0x140038ad7  lea     eax, [r9-0Ch]
0x140038adb  cmp     ecx, eax
0x140038add  jbe     short loc_140038B2F
0x140038adf  mov     rcx, cs:WPP_GLOBAL_Control
0x140038ae6  lea     rax, WPP_GLOBAL_Control
0x140038aed  cmp     rcx, rax
0x140038af0  jz      short loc_140038B27
0x140038af2  cmp     byte ptr [rcx+29h], 2
0x140038af6  jb      short loc_140038B27
0x140038af8  test    dword ptr [rcx+2Ch], 100h
0x140038aff  jz      short loc_140038B27
0x140038b01  mov     eax, [rsi+8]
0x140038b04  lea     rdi, [rsi+4]
0x140038b08  mov     rcx, [rcx+18h]
0x140038b0c  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x140038b13  mov     dword ptr [rsp+58h+var_30], eax
0x140038b17  mov     edx, 17h
0x140038b1c  mov     eax, [rdi]
0x140038b1e  mov     dword ptr [rsp+58h+var_38], eax
0x140038b22  call    WPP_SF_lll
0x140038b27  mov     dword ptr [rdi], 0
0x140038b2d  xor     ecx, ecx
0x140038b2f  mov     [rsi+8], ecx
0x140038b32  jmp     loc_140038BC1
0x140038b37  mov     ebx, 80000005h
0x140038b3c  jmp     loc_140038BC1
0x140038b41  mov     rcx, cs:WPP_GLOBAL_Control
0x140038b48  lea     rax, WPP_GLOBAL_Control
0x140038b4f  cmp     rcx, rax
0x140038b52  jz      short loc_140038B83
0x140038b54  mov     edx, 19h
0x140038b59  jmp     short loc_140038B73
0x140038b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140038b62  lea     rax, WPP_GLOBAL_Control
0x140038b69  cmp     rcx, rax
0x140038b6c  jz      short loc_140038B83
0x140038b6e  mov     edx, 18h
0x140038b73  mov     rcx, [rcx+18h]
0x140038b77  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x140038b7e  call    WPP_SF_
0x140038b83  mov     ebx, 0C0000001h
0x140038b88  test    rsi, rsi
0x140038b8b  jz      short loc_140038BC1
0x140038b8d  mov     rcx, [rdi]; Lookaside
0x140038b90  test    rcx, rcx
0x140038b93  jz      short loc_140038BA6
0x140038b95  mov     rdx, rdi; Entry
0x140038b98  call    cs:__imp_ExFreeToNPagedLookasideList
0x140038b9f  nop     dword ptr [rax+rax+00h]
0x140038ba4  jmp     short loc_140038BB8
0x140038ba6  mov     edx, [rdi+8]; Tag
0x140038ba9  mov     rcx, rdi; P
0x140038bac  call    cs:__imp_ExFreePoolWithTag
0x140038bb3  nop     dword ptr [rax+rax+00h]
0x140038bb8  xor     esi, esi
0x140038bba  jmp     short loc_140038BC1
0x140038bbc  mov     ebx, 0C000009Ah
0x140038bc1  mov     [r12], rsi
0x140038bc5  mov     eax, ebx
0x140038bc7  mov     rbx, [rsp+58h+arg_0]
0x140038bcc  mov     rbp, [rsp+58h+arg_18]
0x140038bd1  add     rsp, 30h
0x140038bd5  pop     r15
0x140038bd7  pop     r14
0x140038bd9  pop     r12
0x140038bdb  pop     rdi
0x140038bdc  pop     rsi
0x140038bdd  retn
```
