# InstallGroupKey(_VELAN *,DOT11_MAC_STATE_ENTRY *,_DOT11_CIPHER_ALGORITHM,ulong,uchar const *,uchar const *,ulong,uchar const *)

- ea: `0x14004c674`
- end: `0x14004c975`
- name: `?InstallGroupKey@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_CIPHER_ALGORITHM@@KPEBE3K3@Z`
- size: `769`
- prototype: `int(struct _VELAN *, struct DOT11_MAC_STATE_ENTRY *, enum _DOT11_CIPHER_ALGORITHM, unsigned int, const unsigned __int8 *, const unsigned __int8 *, unsigned int, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004dd90`
- `0x14004e274`

## callees

- `0x1400160e0`
- `0x1400165c4`
- `0x14001a320`
- `0x140020dc0`
- `0x140020f20`
- `0x140047858`
- `0x14004c674`
- `0x1400500b0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c757`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c757`
- `ntoskrnl!ExAllocatePool2` at `0x14004c76d`
- `ntoskrnl!ExAllocatePool2` at `0x14004c76d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004c884`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004c884`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c898`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c898`

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
  __int64 v10; // r9
  int v11; // r12d
  unsigned int v12; // ebx
  unsigned int v13; // r13d
  unsigned int v14; // esi
  unsigned int v15; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  char *v18; // rdi
  struct _NDIS_OID_REQUEST *v19; // r8
  size_t v21; // [rsp+30h] [rbp-68h]
  unsigned int v22; // [rsp+40h] [rbp-58h]
  size_t Size[9]; // [rsp+50h] [rbp-48h] BYREF

  CipherKeyStructLength = ValidateAndGetCipherKeyStructLength(a3, a7);
  v11 = CipherKeyStructLength;
  if ( !CipherKeyStructLength )
  {
    v12 = -1073741595;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        257,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        (unsigned int)a3,
        a7);
    return v12;
  }
  v13 = CipherKeyStructLength + 24;
  v14 = CipherKeyStructLength + 368;
  v15 = CipherKeyStructLength + 384;
  if ( (unsigned int)(v11 + 384) < 0x10 )
    goto LABEL_28;
  if ( v15 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_13:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_15;
  }
  if ( v15 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_13;
  }
  if ( v15 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_13;
  }
  if ( v15 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_13;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v15, 2053731191, v10);
LABEL_15:
  if ( Pool2 )
  {
    v18 = (char *)(Pool2 + 4);
    *(_QWORD *)Pool2 = p_DeviceQueue;
    Pool2[2] = 2053731191;
    memset(Pool2 + 4, 0, v14);
    *((_QWORD *)v18 + 40) = a1;
    Size[0] = v13;
    *((_QWORD *)v18 + 38) = v18 + 344;
    *((_DWORD *)v18 + 78) = v13;
    *((_DWORD *)v18 + 84) = 0;
    memset(v18 + 344, 0, v13);
    LODWORD(v21) = a7;
    v12 = FillCipherDefaultKeyValues(
            a3,
            (const unsigned __int8 (*)[6])a2->MacHashEntry.MacKey,
            a4,
            a5,
            a6,
            v11,
            v21,
            Src,
            v22,
            (struct DOT11_CIPHER_DEFAULT_KEY_VALUE *)(v18 + 344));
    if ( (v12 & 0x80000000) == 0 )
    {
      Dot11BuildNdisRequest(
        (struct DOT11_NDIS_REQUEST *)v18,
        1u,
        0xE01018Bu,
        v13,
        v18 + 344,
        (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))FreeOidRequestBuffer,
        v18 + 304,
        0);
      _InterlockedIncrement((volatile signed __int32 *)&a2->uRefCnt);
      *((_QWORD *)v18 + 41) = a2;
      v19 = (struct _NDIS_OID_REQUEST *)*((_QWORD *)v18 + 1);
      LODWORD(Size[0]) = 0;
      Dot11Request((int *)Size, a1->pAdapt, v19);
      v12 = Size[0];
      if ( LODWORD(Size[0]) == 259 )
        return 0;
      else
        Dot11RequestComplete(a1->pAdapt, *((struct _NDIS_OID_REQUEST **)v18 + 1), Size[0]);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 259, WPP_e90d411d816e312466897e39e745b158_Traceguids, v12);
      if ( v18 != (char *)-344LL )
        memset(v18 + 344, 0, Size[0]);
      if ( v18 )
      {
        if ( *((_QWORD *)v18 - 2) )
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v18 - 2), v18 - 16);
        else
          ExFreePoolWithTag(v18 - 16, *((_DWORD *)v18 - 2));
      }
    }
    return v12;
  }
LABEL_28:
  v12 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 258, WPP_e90d411d816e312466897e39e745b158_Traceguids, v14);
  return v12;
}

```

## disassembly

```asm
0x14004c674  mov     rax, rsp
0x14004c677  mov     [rax+18h], rbx
0x14004c67b  mov     [rax+20h], r9d
0x14004c67f  mov     [rax+10h], rdx
0x14004c683  mov     [rax+8], rcx
0x14004c687  push    rbp
0x14004c688  push    rsi
0x14004c689  push    rdi
0x14004c68a  push    r12
0x14004c68c  push    r13
0x14004c68e  push    r14
0x14004c690  push    r15
0x14004c692  sub     rsp, 60h
0x14004c696  mov     r15d, dword ptr [rsp+98h+arg_30]
0x14004c69e  mov     ecx, r8d; enum _DOT11_CIPHER_ALGORITHM
0x14004c6a1  mov     edx, r15d; unsigned int
0x14004c6a4  mov     ebp, r8d
0x14004c6a7  call    ?ValidateAndGetCipherKeyStructLength@@YAGW4_DOT11_CIPHER_ALGORITHM@@K@Z; ValidateAndGetCipherKeyStructLength(_DOT11_CIPHER_ALGORITHM,ulong)
0x14004c6ac  movzx   r12d, ax
0x14004c6b0  xor     edi, edi
0x14004c6b2  test    r12w, r12w
0x14004c6b6  jnz     short loc_14004C6F6
0x14004c6b8  mov     ebx, 0C00000E5h
0x14004c6bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c6c4  lea     rax, WPP_GLOBAL_Control
0x14004c6cb  cmp     rcx, rax
0x14004c6ce  jz      loc_14004C95A
0x14004c6d4  mov     rcx, [rcx+18h]
0x14004c6d8  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004c6df  mov     edx, 101h
0x14004c6e4  mov     dword ptr [rsp+98h+var_78], r15d
0x14004c6e9  mov     r9d, ebp
0x14004c6ec  call    WPP_SF_Dd
0x14004c6f1  jmp     loc_14004C95A
0x14004c6f6  lea     r13d, [r12+18h]
0x14004c6fb  lea     esi, [r13+158h]
0x14004c702  lea     eax, [rsi+10h]
0x14004c705  cmp     eax, 10h
0x14004c708  jb      loc_14004C92A
0x14004c70e  mov     ecx, 40h ; '@'
0x14004c713  mov     r14d, 7A697377h
0x14004c719  cmp     eax, ecx
0x14004c71b  ja      short loc_14004C726
0x14004c71d  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004c724  jmp     short loc_14004C754
0x14004c726  cmp     eax, 100h
0x14004c72b  ja      short loc_14004C736
0x14004c72d  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004c734  jmp     short loc_14004C754
0x14004c736  cmp     eax, 400h
0x14004c73b  ja      short loc_14004C746
0x14004c73d  lea     rbx, Lookaside
0x14004c744  jmp     short loc_14004C754
0x14004c746  cmp     eax, 800h
0x14004c74b  ja      short loc_14004C765
0x14004c74d  lea     rbx, stru_1400B0180
0x14004c754  mov     rcx, rbx; Lookaside
0x14004c757  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004c75e  nop     dword ptr [rax+rax+00h]
0x14004c763  jmp     short loc_14004C779
0x14004c765  mov     edx, eax
0x14004c767  mov     r8d, r14d
0x14004c76a  mov     rbx, rdi
0x14004c76d  call    cs:__imp_ExAllocatePool2
0x14004c774  nop     dword ptr [rax+rax+00h]
0x14004c779  test    rax, rax
0x14004c77c  jz      loc_14004C92A
0x14004c782  lea     rdi, [rax+10h]
0x14004c786  mov     r8d, esi; Size
0x14004c789  mov     rcx, rdi; void *
0x14004c78c  mov     [rax], rbx
0x14004c78f  xor     edx, edx; Val
0x14004c791  mov     [rax+8], r14d
0x14004c795  call    memset
0x14004c79a  mov     rax, [rsp+98h+arg_0]
0x14004c7a2  lea     r14, [rdi+130h]
0x14004c7a9  mov     [r14+10h], rax
0x14004c7ad  lea     rsi, [r14+28h]
0x14004c7b1  mov     eax, r13d
0x14004c7b4  xor     edx, edx; Val
0x14004c7b6  mov     r8d, r13d; Size
0x14004c7b9  mov     rcx, rsi; void *
0x14004c7bc  mov     [rsp+98h+Size], rax
0x14004c7c1  mov     [r14], rsi
0x14004c7c4  mov     [r14+8], r13d
0x14004c7c8  mov     dword ptr [r14+20h], 0
0x14004c7d0  call    memset
0x14004c7d5  mov     rax, [rsp+98h+arg_38]
0x14004c7dd  mov     ecx, ebp; enum _DOT11_CIPHER_ALGORITHM
0x14004c7df  mov     rdx, [rsp+98h+arg_8]
0x14004c7e7  mov     r9, [rsp+98h+arg_20]; unsigned __int8 *
0x14004c7ef  add     rdx, 10h; unsigned __int8 (*)[6]
0x14004c7f3  mov     r8d, [rsp+98h+arg_18]; unsigned int
0x14004c7fb  mov     [rsp+98h+var_50], rsi; struct DOT11_CIPHER_DEFAULT_KEY_VALUE *
0x14004c800  mov     [rsp+98h+Src], rax; Src
0x14004c805  mov     rax, [rsp+98h+arg_28]
0x14004c80d  mov     dword ptr [rsp+98h+var_68], r15d; Size
0x14004c812  mov     word ptr [rsp+98h+var_70], r12w; unsigned __int16
0x14004c818  mov     [rsp+98h+var_78], rax; unsigned __int8 *
0x14004c81d  call    ?FillCipherDefaultKeyValues@@YAHW4_DOT11_CIPHER_ALGORITHM@@PEAY05$$CBEKPEBE2GK2KPEAUDOT11_CIPHER_DEFAULT_KEY_VALUE@@@Z; FillCipherDefaultKeyValues(_DOT11_CIPHER_ALGORITHM,uchar const (*)[6],ulong,uchar const *,uchar const *,ushort,ulong,uchar const *,ulong,DOT11_CIPHER_DEFAULT_KEY_VALUE *)
0x14004c822  xor     ebp, ebp
0x14004c824  mov     ebx, eax
0x14004c826  test    eax, eax
0x14004c828  jns     short loc_14004C8A9
0x14004c82a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c831  lea     rax, WPP_GLOBAL_Control
0x14004c838  cmp     rcx, rax
0x14004c83b  jz      short loc_14004C855
0x14004c83d  mov     rcx, [rcx+18h]
0x14004c841  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004c848  mov     edx, 103h
0x14004c84d  mov     r9d, ebx
0x14004c850  call    WPP_SF_d
0x14004c855  test    rsi, rsi
0x14004c858  jz      short loc_14004C869
0x14004c85a  mov     r8, [rsp+98h+Size]; Size
0x14004c85f  xor     edx, edx; Val
0x14004c861  mov     rcx, rsi; void *
0x14004c864  call    memset
0x14004c869  test    rdi, rdi
0x14004c86c  jz      loc_14004C95A
0x14004c872  lea     rcx, [rdi-10h]; P
0x14004c876  mov     rax, [rcx]
0x14004c879  test    rax, rax
0x14004c87c  jz      short loc_14004C895
0x14004c87e  mov     rdx, rcx; Entry
0x14004c881  mov     rcx, rax; Lookaside
0x14004c884  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004c88b  nop     dword ptr [rax+rax+00h]
0x14004c890  jmp     loc_14004C95A
0x14004c895  mov     edx, [rcx+8]; Tag
0x14004c898  call    cs:__imp_ExFreePoolWithTag
0x14004c89f  nop     dword ptr [rax+rax+00h]
0x14004c8a4  jmp     loc_14004C95A
0x14004c8a9  mov     [rsp+98h+Src], rbp; void *
0x14004c8ae  lea     rax, ?FreeOidRequestBuffer@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; FreeOidRequestBuffer(_ADAPT *,DOT11_NDIS_REQUEST *)
0x14004c8b5  mov     [rsp+98h+var_68], r14; void *
0x14004c8ba  mov     r9d, r13d; unsigned int
0x14004c8bd  mov     [rsp+98h+var_70], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x14004c8c2  mov     edx, 1; unsigned int
0x14004c8c7  mov     r8d, 0E01018Bh; unsigned int
0x14004c8cd  mov     [rsp+98h+var_78], rsi; void *
0x14004c8d2  mov     rcx, rdi; struct DOT11_NDIS_REQUEST *
0x14004c8d5  call    ?Dot11BuildNdisRequest@@YAXPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@0@Z11@Z; Dot11BuildNdisRequest(DOT11_NDIS_REQUEST *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x14004c8da  mov     rax, [rsp+98h+arg_8]
0x14004c8e2  lock inc dword ptr [rax+24h]
0x14004c8e6  mov     rsi, [rsp+98h+arg_0]
0x14004c8ee  lea     rcx, [rsp+98h+Size]; int *
0x14004c8f3  mov     [r14+18h], rax
0x14004c8f7  mov     r8, [rdi+8]; struct _NDIS_OID_REQUEST *
0x14004c8fb  mov     dword ptr [rsp+98h+Size], ebp
0x14004c8ff  mov     rdx, [rsi+10h]; struct _ADAPT *
0x14004c903  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x14004c908  mov     ebx, dword ptr [rsp+98h+Size]
0x14004c90c  cmp     ebx, 103h
0x14004c912  jz      short loc_14004C926
0x14004c914  mov     rdx, [rdi+8]; struct _NDIS_OID_REQUEST *
0x14004c918  mov     r8d, ebx; int
0x14004c91b  mov     rcx, [rsi+10h]; struct _ADAPT *
0x14004c91f  call    ?Dot11RequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z; Dot11RequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)
0x14004c924  jmp     short loc_14004C95A
0x14004c926  mov     ebx, ebp
0x14004c928  jmp     short loc_14004C95A
0x14004c92a  mov     ebx, 0C000009Ah
0x14004c92f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c936  lea     rax, WPP_GLOBAL_Control
0x14004c93d  cmp     rcx, rax
0x14004c940  jz      short loc_14004C95A
0x14004c942  mov     rcx, [rcx+18h]
0x14004c946  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004c94d  mov     edx, 102h
0x14004c952  mov     r9d, esi
0x14004c955  call    WPP_SF_d
0x14004c95a  mov     eax, ebx
0x14004c95c  mov     rbx, [rsp+98h+arg_10]
0x14004c964  add     rsp, 60h
0x14004c968  pop     r15
0x14004c96a  pop     r14
0x14004c96c  pop     r13
0x14004c96e  pop     r12
0x14004c970  pop     rdi
0x14004c971  pop     rsi
0x14004c972  pop     rbp
0x14004c973  retn
```
