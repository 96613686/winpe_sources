# InstallGroupKey(_VELAN *,DOT11_MAC_STATE_ENTRY *,_DOT11_CIPHER_ALGORITHM,ulong,uchar const *,uchar const *,ulong,uchar const *)

- ea: `0x14004dde0`
- end: `0x14004e136`
- name: `?InstallGroupKey@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_CIPHER_ALGORITHM@@KPEBE3K3@Z`
- size: `854`
- prototype: `int(struct _VELAN *, struct DOT11_MAC_STATE_ENTRY *, enum _DOT11_CIPHER_ALGORITHM, unsigned int, const unsigned __int8 *, const unsigned __int8 *, unsigned int, const unsigned __int8 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004d8fc`
- `0x14004f550`
- `0x14004fa34`

## callees

- `0x1400160d0`
- `0x1400165b4`
- `0x14001a320`
- `0x140020dc0`
- `0x140020f20`
- `0x140048ad0`
- `0x14004dde0`
- `0x140051878`
- `0x140053f88`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ded9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ded9`
- `ntoskrnl!ExAllocatePool2` at `0x14004deef`
- `ntoskrnl!ExAllocatePool2` at `0x14004deef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e06e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e06e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e10f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e10f`

## pseudocode

```c
__int64 __fastcall InstallGroupKey(
        struct _VELAN *a1,
        struct DOT11_MAC_STATE_ENTRY *a2,
        enum _DOT11_CIPHER_ALGORITHM a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *Src)
{
  unsigned __int16 CipherKeyStructLength; // ax
  int v10; // ebx
  char *v11; // rdi
  __int64 v12; // r14
  unsigned int v13; // esi
  unsigned int v14; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  size_t v17; // rsi
  struct _NDIS_OID_REQUEST *v18; // r8
  size_t Size; // [rsp+30h] [rbp-68h]
  unsigned int v21; // [rsp+40h] [rbp-58h]
  int v22[18]; // [rsp+50h] [rbp-48h] BYREF

  CipherKeyStructLength = ValidateAndGetCipherKeyStructLength(a3, a7);
  LOWORD(v22[0]) = CipherKeyStructLength;
  if ( !CipherKeyStructLength )
  {
    v10 = -1073741595;
    if ( (unsigned int)Feature_Bugfix_53850044__private_IsEnabledDeviceUsageNoInline()
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        257,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        (unsigned int)a3,
        a7);
    }
    return (unsigned int)v10;
  }
  v11 = 0;
  v12 = (unsigned int)CipherKeyStructLength + 24;
  v13 = CipherKeyStructLength + 368;
  v14 = CipherKeyStructLength + 384;
  if ( v14 < 0x10 )
    goto LABEL_6;
  if ( v14 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_15:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_17;
  }
  if ( v14 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_15;
  }
  if ( v14 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_15;
  }
  if ( v14 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_15;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v14, 2053731191);
LABEL_17:
  if ( !Pool2 )
  {
LABEL_6:
    v10 = -1073741670;
    goto LABEL_19;
  }
  *(_QWORD *)Pool2 = p_DeviceQueue;
  v11 = (char *)(Pool2 + 4);
  v10 = 0;
  Pool2[2] = 2053731191;
LABEL_19:
  if ( (unsigned int)Feature_Bugfix_53850044__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 258, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v13);
      goto LABEL_32;
    }
    memset(v11, 0, v13);
    v17 = (unsigned int)v12;
LABEL_26:
    *((_DWORD *)v11 + 78) = v12;
    *((_QWORD *)v11 + 38) = v11 + 344;
    *((_QWORD *)v11 + 40) = a1;
    *((_DWORD *)v11 + 84) = 0;
    memset(v11 + 344, 0, v17);
    LODWORD(Size) = a7;
    v10 = FillCipherDefaultKeyValues(
            a3,
            (const unsigned __int8 (*)[6])a2->MacHashEntry.MacKey,
            a4,
            a5,
            a6,
            v22[0],
            Size,
            Src,
            v21,
            (struct DOT11_CIPHER_DEFAULT_KEY_VALUE *)(v11 + 344));
    if ( (unsigned int)Feature_Bugfix_53850044__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            259,
            WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
            (unsigned int)v10);
        goto LABEL_30;
      }
    }
    else if ( v10 < 0 )
    {
LABEL_30:
      if ( v11 != (char *)-344LL )
        memset(v11 + 344, 0, v17);
      goto LABEL_32;
    }
    Dot11BuildNdisRequest(
      (struct DOT11_NDIS_REQUEST *)v11,
      1u,
      0xE01018Bu,
      v12,
      v11 + 344,
      (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))FreeOidRequestBuffer,
      v11 + 304,
      0);
    _InterlockedIncrement((volatile signed __int32 *)&a2->uRefCnt);
    *((_QWORD *)v11 + 41) = a2;
    v18 = (struct _NDIS_OID_REQUEST *)*((_QWORD *)v11 + 1);
    v22[0] = 0;
    Dot11Request(v22, a1->pAdapt, v18);
    v10 = v22[0];
    if ( v22[0] == 259 )
      return 0;
    else
      Dot11RequestComplete(a1->pAdapt, *((struct _NDIS_OID_REQUEST **)v11 + 1), v22[0]);
    return (unsigned int)v10;
  }
  if ( v10 >= 0 )
  {
    v17 = (unsigned int)v12;
    memset(v11, 0, v12 + 344);
    goto LABEL_26;
  }
LABEL_32:
  if ( v11 )
  {
    if ( *((_QWORD *)v11 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v11 - 2), v11 - 16);
    else
      ExFreePoolWithTag(v11 - 16, *((_DWORD *)v11 - 2));
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14004dde0  mov     rax, rsp
0x14004dde3  mov     [rax+18h], rbx
0x14004dde7  mov     [rax+20h], r9d
0x14004ddeb  mov     [rax+10h], rdx
0x14004ddef  mov     [rax+8], rcx
0x14004ddf3  push    rbp
0x14004ddf4  push    rsi
0x14004ddf5  push    rdi
0x14004ddf6  push    r12
0x14004ddf8  push    r13
0x14004ddfa  push    r14
0x14004ddfc  push    r15
0x14004ddfe  sub     rsp, 60h
0x14004de02  mov     r13d, dword ptr [rsp+98h+arg_30]
0x14004de0a  mov     ecx, r8d; enum _DOT11_CIPHER_ALGORITHM
0x14004de0d  mov     edx, r13d; unsigned int
0x14004de10  mov     r12d, r8d
0x14004de13  call    ?ValidateAndGetCipherKeyStructLength@@YAGW4_DOT11_CIPHER_ALGORITHM@@K@Z; ValidateAndGetCipherKeyStructLength(_DOT11_CIPHER_ALGORITHM,ulong)
0x14004de18  xor     ebp, ebp
0x14004de1a  mov     word ptr [rsp+98h+var_48], ax
0x14004de1f  test    ax, ax
0x14004de22  jnz     short loc_14004DE6F
0x14004de24  mov     ebx, 0C00000E5h
0x14004de29  call    Feature_Bugfix_53850044__private_IsEnabledDeviceUsageNoInline
0x14004de2e  test    eax, eax
0x14004de30  jz      loc_14004E11B
0x14004de36  mov     rcx, cs:WPP_GLOBAL_Control
0x14004de3d  lea     rax, WPP_GLOBAL_Control
0x14004de44  cmp     rcx, rax
0x14004de47  jz      loc_14004E11B
0x14004de4d  mov     rcx, [rcx+18h]
0x14004de51  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004de58  mov     edx, 101h
0x14004de5d  mov     dword ptr [rsp+98h+var_78], r13d
0x14004de62  mov     r9d, r12d
0x14004de65  call    WPP_SF_Dd
0x14004de6a  jmp     loc_14004E11B
0x14004de6f  movzx   r14d, ax
0x14004de73  mov     rdi, rbp
0x14004de76  add     r14d, 18h
0x14004de7a  lea     esi, [r14+158h]
0x14004de81  lea     eax, [rsi+10h]
0x14004de84  cmp     eax, 10h
0x14004de87  jnb     short loc_14004DE90
0x14004de89  mov     ebx, 0C000009Ah
0x14004de8e  jmp     short loc_14004DF0D
0x14004de90  mov     ecx, 40h ; '@'
0x14004de95  mov     r15d, 7A697377h
0x14004de9b  cmp     eax, ecx
0x14004de9d  ja      short loc_14004DEA8
0x14004de9f  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004dea6  jmp     short loc_14004DED6
0x14004dea8  cmp     eax, 100h
0x14004dead  ja      short loc_14004DEB8
0x14004deaf  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004deb6  jmp     short loc_14004DED6
0x14004deb8  cmp     eax, 400h
0x14004debd  ja      short loc_14004DEC8
0x14004debf  lea     rbx, Lookaside
0x14004dec6  jmp     short loc_14004DED6
0x14004dec8  cmp     eax, 800h
0x14004decd  ja      short loc_14004DEE7
0x14004decf  lea     rbx, stru_1400B31C0
0x14004ded6  mov     rcx, rbx; Lookaside
0x14004ded9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004dee0  nop     dword ptr [rax+rax+00h]
0x14004dee5  jmp     short loc_14004DEFB
0x14004dee7  mov     edx, eax
0x14004dee9  mov     r8d, r15d
0x14004deec  mov     rbx, rbp
0x14004deef  call    cs:__imp_ExAllocatePool2
0x14004def6  nop     dword ptr [rax+rax+00h]
0x14004defb  test    rax, rax
0x14004defe  jz      short loc_14004DE89
0x14004df00  mov     [rax], rbx
0x14004df03  lea     rdi, [rax+10h]
0x14004df07  mov     ebx, ebp
0x14004df09  mov     [rax+8], r15d
0x14004df0d  call    Feature_Bugfix_53850044__private_IsEnabledDeviceUsageNoInline
0x14004df12  test    eax, eax
0x14004df14  jz      short loc_14004DF60
0x14004df16  test    ebx, ebx
0x14004df18  jns     short loc_14004DF4E
0x14004df1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004df21  lea     rax, WPP_GLOBAL_Control
0x14004df28  cmp     rcx, rax
0x14004df2b  jz      loc_14004E04F
0x14004df31  mov     rcx, [rcx+18h]
0x14004df35  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004df3c  mov     edx, 102h
0x14004df41  mov     r9d, esi
0x14004df44  call    WPP_SF_d
0x14004df49  jmp     loc_14004E04F
0x14004df4e  mov     r8d, esi; Size
0x14004df51  xor     edx, edx; Val
0x14004df53  mov     rcx, rdi; void *
0x14004df56  call    memset
0x14004df5b  mov     esi, r14d
0x14004df5e  jmp     short loc_14004DF7C
0x14004df60  test    ebx, ebx
0x14004df62  js      loc_14004E04F
0x14004df68  lea     r8, [r14+158h]; Size
0x14004df6f  mov     esi, r14d
0x14004df72  xor     edx, edx; Val
0x14004df74  mov     rcx, rdi; void *
0x14004df77  call    memset
0x14004df7c  mov     rax, [rsp+98h+arg_0]
0x14004df84  lea     r15, [rdi+130h]
0x14004df8b  lea     rbp, [r15+28h]
0x14004df8f  mov     [r15+8], r14d
0x14004df93  mov     rcx, rbp; void *
0x14004df96  mov     [r15], rbp
0x14004df99  mov     r8, rsi; Size
0x14004df9c  mov     [r15+10h], rax
0x14004dfa0  xor     edx, edx; Val
0x14004dfa2  mov     dword ptr [r15+20h], 0
0x14004dfaa  call    memset
0x14004dfaf  mov     rax, [rsp+98h+arg_38]
0x14004dfb7  mov     ecx, r12d; enum _DOT11_CIPHER_ALGORITHM
0x14004dfba  mov     rdx, [rsp+98h+arg_8]
0x14004dfc2  mov     r9, [rsp+98h+arg_20]; unsigned __int8 *
0x14004dfca  add     rdx, 10h; unsigned __int8 (*)[6]
0x14004dfce  mov     r8d, [rsp+98h+arg_18]; unsigned int
0x14004dfd6  mov     [rsp+98h+var_50], rbp; struct DOT11_CIPHER_DEFAULT_KEY_VALUE *
0x14004dfdb  mov     [rsp+98h+Src], rax; Src
0x14004dfe0  movzx   eax, word ptr [rsp+98h+var_48]
0x14004dfe5  mov     dword ptr [rsp+98h+Size], r13d; Size
0x14004dfea  mov     word ptr [rsp+98h+var_70], ax; unsigned __int16
0x14004dfef  mov     rax, [rsp+98h+arg_28]
0x14004dff7  mov     [rsp+98h+var_78], rax; unsigned __int8 *
0x14004dffc  call    ?FillCipherDefaultKeyValues@@YAHW4_DOT11_CIPHER_ALGORITHM@@PEAY05$$CBEKPEBE2GK2KPEAUDOT11_CIPHER_DEFAULT_KEY_VALUE@@@Z; FillCipherDefaultKeyValues(_DOT11_CIPHER_ALGORITHM,uchar const (*)[6],ulong,uchar const *,uchar const *,ushort,ulong,uchar const *,ulong,DOT11_CIPHER_DEFAULT_KEY_VALUE *)
0x14004e001  mov     ebx, eax
0x14004e003  call    Feature_Bugfix_53850044__private_IsEnabledDeviceUsageNoInline
0x14004e008  test    eax, eax
0x14004e00a  jz      short loc_14004E07F
0x14004e00c  test    ebx, ebx
0x14004e00e  jns     short loc_14004E083
0x14004e010  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e017  lea     rax, WPP_GLOBAL_Control
0x14004e01e  cmp     rcx, rax
0x14004e021  jz      short loc_14004E03B
0x14004e023  mov     rcx, [rcx+18h]
0x14004e027  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004e02e  mov     edx, 103h
0x14004e033  mov     r9d, ebx
0x14004e036  call    WPP_SF_d
0x14004e03b  test    rbp, rbp
0x14004e03e  jz      short loc_14004E04D
0x14004e040  mov     r8, rsi; Size
0x14004e043  xor     edx, edx; Val
0x14004e045  mov     rcx, rbp; void *
0x14004e048  call    memset
0x14004e04d  xor     ebp, ebp
0x14004e04f  test    rdi, rdi
0x14004e052  jz      loc_14004E11B
0x14004e058  lea     rcx, [rdi-10h]; P
0x14004e05c  mov     rax, [rcx]
0x14004e05f  test    rax, rax
0x14004e062  jz      loc_14004E10C
0x14004e068  mov     rdx, rcx; Entry
0x14004e06b  mov     rcx, rax; Lookaside
0x14004e06e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004e075  nop     dword ptr [rax+rax+00h]
0x14004e07a  jmp     loc_14004E11B
0x14004e07f  test    ebx, ebx
0x14004e081  js      short loc_14004E03B
0x14004e083  mov     [rsp+98h+Src], 0; void *
0x14004e08c  lea     rax, ?FreeOidRequestBuffer@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; FreeOidRequestBuffer(_ADAPT *,DOT11_NDIS_REQUEST *)
0x14004e093  mov     [rsp+98h+Size], r15; void *
0x14004e098  mov     r9d, r14d; unsigned int
0x14004e09b  mov     [rsp+98h+var_70], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x14004e0a0  mov     edx, 1; unsigned int
0x14004e0a5  mov     r8d, 0E01018Bh; unsigned int
0x14004e0ab  mov     [rsp+98h+var_78], rbp; void *
0x14004e0b0  mov     rcx, rdi; struct DOT11_NDIS_REQUEST *
0x14004e0b3  call    ?Dot11BuildNdisRequest@@YAXPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@0@Z11@Z; Dot11BuildNdisRequest(DOT11_NDIS_REQUEST *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x14004e0b8  mov     rax, [rsp+98h+arg_8]
0x14004e0c0  lock inc dword ptr [rax+24h]
0x14004e0c4  mov     rsi, [rsp+98h+arg_0]
0x14004e0cc  lea     rcx, [rsp+98h+var_48]; int *
0x14004e0d1  mov     [r15+18h], rax
0x14004e0d5  mov     r8, [rdi+8]; struct _NDIS_OID_REQUEST *
0x14004e0d9  mov     [rsp+98h+var_48], 0
0x14004e0e1  mov     rdx, [rsi+10h]; struct _ADAPT *
0x14004e0e5  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x14004e0ea  mov     ebx, [rsp+98h+var_48]
0x14004e0ee  cmp     ebx, 103h
0x14004e0f4  jz      short loc_14004E108
0x14004e0f6  mov     rdx, [rdi+8]; struct _NDIS_OID_REQUEST *
0x14004e0fa  mov     r8d, ebx; int
0x14004e0fd  mov     rcx, [rsi+10h]; struct _ADAPT *
0x14004e101  call    ?Dot11RequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z; Dot11RequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)
0x14004e106  jmp     short loc_14004E11B
0x14004e108  xor     ebx, ebx
0x14004e10a  jmp     short loc_14004E11B
0x14004e10c  mov     edx, [rcx+8]; Tag
0x14004e10f  call    cs:__imp_ExFreePoolWithTag
0x14004e116  nop     dword ptr [rax+rax+00h]
0x14004e11b  mov     eax, ebx
0x14004e11d  mov     rbx, [rsp+98h+arg_10]
0x14004e125  add     rsp, 60h
0x14004e129  pop     r15
0x14004e12b  pop     r14
0x14004e12d  pop     r13
0x14004e12f  pop     r12
0x14004e131  pop     rdi
0x14004e132  pop     rsi
0x14004e133  pop     rbp
0x14004e134  retn
```
