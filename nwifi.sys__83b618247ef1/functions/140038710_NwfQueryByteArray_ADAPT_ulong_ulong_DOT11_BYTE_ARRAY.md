# NwfQueryByteArray(_ADAPT *,ulong,ulong,DOT11_BYTE_ARRAY * *)

- ea: `0x140038710`
- end: `0x1400389bf`
- name: `?NwfQueryByteArray@@YAHPEAU_ADAPT@@KKPEAPEAUDOT11_BYTE_ARRAY@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(struct _ADAPT *, unsigned int, unsigned int, struct DOT11_BYTE_ARRAY **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14001a47c`

## callees

- `0x14000d22c`
- `0x140015b1c`
- `0x14002ffb4`
- `0x140038710`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400387ac`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400387ac`
- `ntoskrnl!ExAllocatePool2` at `0x1400387c7`
- `ntoskrnl!ExAllocatePool2` at `0x1400387c7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038876`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038978`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038876`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038978`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003888d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003898c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003888d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003898c`

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
      p_DeviceQueue = &stru_1400B0180;
      goto LABEL_14;
    }
    p_DeviceQueue = 0;
    Pool2 = (char *)ExAllocatePool2(64, v9, 845771639, a4);
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
0x140038710  mov     rax, rsp
0x140038713  mov     [rax+8], rbx
0x140038717  mov     [rax+20h], rbp
0x14003871b  mov     [rax+10h], edx
0x14003871e  push    rsi
0x14003871f  push    rdi
0x140038720  push    r12
0x140038722  push    r14
0x140038724  push    r15
0x140038726  sub     rsp, 30h
0x14003872a  mov     r14d, r8d
0x14003872d  mov     r12, r9
0x140038730  mov     dword ptr [rax+10h], 0
0x140038737  mov     r15, rcx
0x14003873a  mov     dword ptr [rax+18h], 0
0x140038741  cmp     r8d, 0FFFFFFFFh
0x140038745  jnz     short loc_140038768
0x140038747  mov     ebp, 10h
0x14003874c  xor     esi, esi
0x14003874e  lea     eax, [rbp+10h]
0x140038751  cmp     eax, 10h
0x140038754  jb      loc_14003899C
0x14003875a  cmp     eax, 40h ; '@'
0x14003875d  ja      short loc_14003877B
0x14003875f  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140038766  jmp     short loc_1400387A9
0x140038768  lea     ebp, [r14+10h]
0x14003876c  cmp     ebp, r14d
0x14003876f  jnb     short loc_14003874C
0x140038771  mov     eax, 0C0000001h
0x140038776  jmp     loc_1400389A7
0x14003877b  cmp     eax, 100h
0x140038780  ja      short loc_14003878B
0x140038782  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140038789  jmp     short loc_1400387A9
0x14003878b  cmp     eax, 400h
0x140038790  ja      short loc_14003879B
0x140038792  lea     rbx, Lookaside
0x140038799  jmp     short loc_1400387A9
0x14003879b  cmp     eax, 800h
0x1400387a0  ja      short loc_1400387BA
0x1400387a2  lea     rbx, stru_1400B0180
0x1400387a9  mov     rcx, rbx; Lookaside
0x1400387ac  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400387b3  nop     dword ptr [rax+rax+00h]
0x1400387b8  jmp     short loc_1400387D3
0x1400387ba  xor     ebx, ebx
0x1400387bc  mov     edx, eax
0x1400387be  mov     r8d, 32697377h
0x1400387c4  lea     ecx, [rbx+40h]
0x1400387c7  call    cs:__imp_ExAllocatePool2
0x1400387ce  nop     dword ptr [rax+rax+00h]
0x1400387d3  mov     rdi, rax
0x1400387d6  test    rax, rax
0x1400387d9  jz      loc_14003899C
0x1400387df  lea     rsi, [rax+10h]
0x1400387e3  mov     [rax], rbx
0x1400387e6  mov     dword ptr [rax+8], 32697377h
0x1400387ed  mov     r9d, ebp; unsigned int
0x1400387f0  lea     rax, [rsp+58h+arg_10]
0x1400387f5  mov     r8, rsi; void *
0x1400387f8  mov     [rsp+58h+var_30], rax; unsigned int *
0x1400387fd  mov     edx, 0E050106h; unsigned int
0x140038802  lea     rax, [rsp+58h+arg_8]
0x140038807  mov     rcx, r15; struct _ADAPT *
0x14003880a  mov     [rsp+58h+var_38], rax; unsigned int *
0x14003880f  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140038814  mov     ebx, eax
0x140038816  lea     ecx, [rax+3FFEFFECh]
0x14003881c  test    ecx, 0FFFFFFFDh
0x140038822  jz      short loc_14003882B
0x140038824  cmp     eax, 80000005h
0x140038829  jnz     short loc_14003889E
0x14003882b  cmp     [rsp+58h+arg_8], 10h
0x140038830  jb      short loc_140038854
0x140038832  cmp     byte ptr [rsi], 80h
0x140038835  jnz     loc_14003893B
0x14003883b  cmp     byte ptr [rsi+1], 0
0x14003883f  jz      loc_140038921
0x140038845  mov     ecx, ebp
0x140038847  sub     rcx, 10h
0x14003884b  cmp     rcx, r14
0x14003884e  jnb     loc_140038917
0x140038854  mov     eax, ebp
0x140038856  mov     ebp, [rsp+58h+arg_10]
0x14003885a  cmp     ebp, eax
0x14003885c  jbe     loc_140038963
0x140038862  test    rsi, rsi
0x140038865  jz      loc_14003874C
0x14003886b  mov     rcx, [rdi]; Lookaside
0x14003886e  test    rcx, rcx
0x140038871  jz      short loc_140038887
0x140038873  mov     rdx, rdi; Entry
0x140038876  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003887d  nop     dword ptr [rax+rax+00h]
0x140038882  jmp     loc_14003874C
0x140038887  mov     edx, [rdi+8]; Tag
0x14003888a  mov     rcx, rdi; P
0x14003888d  call    cs:__imp_ExFreePoolWithTag
0x140038894  nop     dword ptr [rax+rax+00h]
0x140038899  jmp     loc_14003874C
0x14003889e  test    eax, eax
0x1400388a0  jnz     loc_140038968
0x1400388a6  mov     r9d, [rsp+58h+arg_8]
0x1400388ab  lea     rdi, [rsi+4]
0x1400388af  cmp     r9d, 0Ch
0x1400388b3  jb      short loc_1400388BF
0x1400388b5  mov     ecx, [rdi]
0x1400388b7  lea     eax, [r9-0Ch]
0x1400388bb  cmp     ecx, eax
0x1400388bd  jbe     short loc_14003890F
0x1400388bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400388c6  lea     rax, WPP_GLOBAL_Control
0x1400388cd  cmp     rcx, rax
0x1400388d0  jz      short loc_140038907
0x1400388d2  cmp     byte ptr [rcx+29h], 2
0x1400388d6  jb      short loc_140038907
0x1400388d8  test    dword ptr [rcx+2Ch], 100h
0x1400388df  jz      short loc_140038907
0x1400388e1  mov     eax, [rsi+8]
0x1400388e4  lea     rdi, [rsi+4]
0x1400388e8  mov     rcx, [rcx+18h]
0x1400388ec  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x1400388f3  mov     dword ptr [rsp+58h+var_30], eax
0x1400388f7  mov     edx, 17h
0x1400388fc  mov     eax, [rdi]
0x1400388fe  mov     dword ptr [rsp+58h+var_38], eax
0x140038902  call    WPP_SF_lll
0x140038907  mov     dword ptr [rdi], 0
0x14003890d  xor     ecx, ecx
0x14003890f  mov     [rsi+8], ecx
0x140038912  jmp     loc_1400389A1
0x140038917  mov     ebx, 80000005h
0x14003891c  jmp     loc_1400389A1
0x140038921  mov     rcx, cs:WPP_GLOBAL_Control
0x140038928  lea     rax, WPP_GLOBAL_Control
0x14003892f  cmp     rcx, rax
0x140038932  jz      short loc_140038963
0x140038934  mov     edx, 19h
0x140038939  jmp     short loc_140038953
0x14003893b  mov     rcx, cs:WPP_GLOBAL_Control
0x140038942  lea     rax, WPP_GLOBAL_Control
0x140038949  cmp     rcx, rax
0x14003894c  jz      short loc_140038963
0x14003894e  mov     edx, 18h
0x140038953  mov     rcx, [rcx+18h]
0x140038957  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x14003895e  call    WPP_SF_
0x140038963  mov     ebx, 0C0000001h
0x140038968  test    rsi, rsi
0x14003896b  jz      short loc_1400389A1
0x14003896d  mov     rcx, [rdi]; Lookaside
0x140038970  test    rcx, rcx
0x140038973  jz      short loc_140038986
0x140038975  mov     rdx, rdi; Entry
0x140038978  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003897f  nop     dword ptr [rax+rax+00h]
0x140038984  jmp     short loc_140038998
0x140038986  mov     edx, [rdi+8]; Tag
0x140038989  mov     rcx, rdi; P
0x14003898c  call    cs:__imp_ExFreePoolWithTag
0x140038993  nop     dword ptr [rax+rax+00h]
0x140038998  xor     esi, esi
0x14003899a  jmp     short loc_1400389A1
0x14003899c  mov     ebx, 0C000009Ah
0x1400389a1  mov     [r12], rsi
0x1400389a5  mov     eax, ebx
0x1400389a7  mov     rbx, [rsp+58h+arg_0]
0x1400389ac  mov     rbp, [rsp+58h+arg_18]
0x1400389b1  add     rsp, 30h
0x1400389b5  pop     r15
0x1400389b7  pop     r14
0x1400389b9  pop     r12
0x1400389bb  pop     rdi
0x1400389bc  pop     rsi
0x1400389bd  retn
```
