# InstallPairwiseKey(_VELAN *,_NWF_KEY_CONTEXT *,DOT11_MAC_STATE_ENTRY *,uchar *,ulong)

- ea: `0x14004fe84`
- end: `0x140050126`
- name: `?InstallPairwiseKey@@YAJPEAU_VELAN@@PEAU_NWF_KEY_CONTEXT@@PEAUDOT11_MAC_STATE_ENTRY@@PEAEK@Z`
- size: `674`
- prototype: `int(struct _VELAN *, struct _NWF_KEY_CONTEXT *, struct DOT11_MAC_STATE_ENTRY *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14005012c`

## callees

- `0x1400160d0`
- `0x1400165b4`
- `0x14001a320`
- `0x14004fe84`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ff21`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ff21`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400500ee`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400500ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400500ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400500ff`

## pseudocode

```c
__int64 __fastcall InstallPairwiseKey(
        struct _VELAN *a1,
        struct _NWF_KEY_CONTEXT *a2,
        struct DOT11_MAC_STATE_ENTRY *a3,
        unsigned __int8 *a4,
        size_t a5)
{
  unsigned int v8; // ebx
  unsigned int v9; // edi
  unsigned int v10; // ebp
  __int16 v11; // r14
  char *v12; // rsi
  _DWORD *v13; // rax
  _DWORD *v14; // rbx
  void *v15; // rcx
  struct _NDIS_OID_REQUEST *v16; // r8
  size_t Size; // [rsp+88h] [rbp+10h] BYREF

  switch ( a2->UcastCipher )
  {
    case DOT11_CIPHER_ALGO_TKIP:
      v9 = a5;
      if ( (_DWORD)a5 != 32 )
        return (unsigned int)-1073741823;
      v10 = 80;
      v11 = 48;
      break;
    case DOT11_CIPHER_ALGO_CCMP:
    case DOT11_CIPHER_ALGO_GCMP:
      v9 = a5;
      if ( (_DWORD)a5 != 16 )
        return (unsigned int)-1073741823;
      v10 = 60;
      v11 = 28;
      break;
    case DOT11_CIPHER_ALGO_GCMP_256:
      v9 = a5;
      if ( (_DWORD)a5 != 32 )
        return (unsigned int)-1073741823;
      v10 = 76;
      v11 = 44;
      break;
    default:
      return (unsigned int)-1073741595;
  }
  v12 = 0;
  v13 = ExAllocateFromNPagedLookasideList(&Lookaside);
  if ( v13 )
  {
    v12 = (char *)(v13 + 4);
    *(_QWORD *)v13 = &Lookaside;
    v13[2] = 2053731191;
    v14 = v13 + 90;
    Size = v10;
    memset(v13 + 90, 0, v10);
    *((_QWORD *)v12 + 40) = a1;
    *((_QWORD *)v12 + 38) = v14;
    *((_DWORD *)v12 + 78) = v10;
    *((_DWORD *)v12 + 84) = 1;
    v14[1] = v10 - 12;
    v14[2] = v10 - 12;
    *v14 = 1048960;
    v14[3] = *(_DWORD *)a3->MacHashEntry.MacKey;
    *((_WORD *)v14 + 8) = *(_WORD *)&a3->MacHashEntry.MacKey[4];
    *((_BYTE *)v14 + 28) = 0;
    v14[5] = a2->UcastCipher;
    v14[6] = 3;
    *((_BYTE *)v14 + 29) = 0;
    *((_WORD *)v14 + 15) = v11;
    switch ( a2->UcastCipher )
    {
      case DOT11_CIPHER_ALGO_TKIP:
        v15 = v14 + 12;
        v14[8] = 0;
        *((_WORD *)v14 + 18) = 0;
        v14[11] = 16;
        break;
      case DOT11_CIPHER_ALGO_CCMP:
      case DOT11_CIPHER_ALGO_GCMP:
        v15 = v14 + 11;
        v14[8] = 0;
        *((_WORD *)v14 + 18) = 0;
        break;
      case DOT11_CIPHER_ALGO_GCMP_256:
        v15 = v14 + 11;
        v14[8] = 0;
        *((_WORD *)v14 + 18) = 0;
        v14[10] = 32;
LABEL_25:
        memmove(v15, a4, v9);
        Dot11BuildNdisRequest(
          (struct DOT11_NDIS_REQUEST *)v12,
          1u,
          0xE01018Cu,
          v10,
          v14,
          (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))FreeOidRequestBuffer,
          v12 + 304,
          0);
        _InterlockedIncrement((volatile signed __int32 *)&a3->uRefCnt);
        *((_QWORD *)v12 + 41) = a3;
        v16 = (struct _NDIS_OID_REQUEST *)*((_QWORD *)v12 + 1);
        LODWORD(Size) = 0;
        Dot11Request((int *)&Size, a1->pAdapt, v16);
        v8 = Size;
        if ( (_DWORD)Size == 259 )
          return 0;
        else
          Dot11RequestComplete(a1->pAdapt, *((struct _NDIS_OID_REQUEST **)v12 + 1), Size);
        return v8;
      default:
        if ( v14 )
          memset(v14, 0, Size);
        v8 = -1073741595;
        goto LABEL_29;
    }
    v14[10] = 16;
    goto LABEL_25;
  }
  v8 = -1073741670;
LABEL_29:
  if ( v12 )
  {
    if ( *((_QWORD *)v12 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), v12 - 16);
    else
      ExFreePoolWithTag(v12 - 16, *((_DWORD *)v12 - 2));
  }
  return v8;
}

```

## disassembly

```asm
0x14004fe84  mov     [rsp+arg_10], rbx
0x14004fe89  mov     [rsp+arg_0], rcx
0x14004fe8e  push    rbp
0x14004fe8f  push    rsi
0x14004fe90  push    rdi
0x14004fe91  push    r12
0x14004fe93  push    r13
0x14004fe95  push    r14
0x14004fe97  push    r15
0x14004fe99  sub     rsp, 40h
0x14004fe9d  mov     r10d, [rdx+10h]
0x14004fea1  mov     r15, r9
0x14004fea4  mov     r12, r8
0x14004fea7  mov     r13, rdx
0x14004feaa  sub     r10d, 2
0x14004feae  jz      short loc_14004FF02
0x14004feb0  sub     r10d, 2
0x14004feb4  jz      short loc_14004FEED
0x14004feb6  sub     r10d, 4
0x14004feba  jz      short loc_14004FEED
0x14004febc  cmp     r10d, 1
0x14004fec0  jz      short loc_14004FECC
0x14004fec2  mov     ebx, 0C00000E5h
0x14004fec7  jmp     loc_14005010B
0x14004fecc  mov     edi, dword ptr [rsp+78h+arg_20]
0x14004fed3  cmp     edi, 20h ; ' '
0x14004fed6  jz      short loc_14004FEE2
0x14004fed8  mov     ebx, 0C0000001h
0x14004fedd  jmp     loc_14005010B
0x14004fee2  mov     ebp, 4Ch ; 'L'
0x14004fee7  lea     r14d, [rbp-20h]
0x14004feeb  jmp     short loc_14004FF15
0x14004feed  mov     edi, dword ptr [rsp+78h+arg_20]
0x14004fef4  cmp     edi, 10h
0x14004fef7  jnz     short loc_14004FED8
0x14004fef9  lea     ebp, [rdi+2Ch]
0x14004fefc  lea     r14d, [rdi+0Ch]
0x14004ff00  jmp     short loc_14004FF15
0x14004ff02  mov     edi, dword ptr [rsp+78h+arg_20]
0x14004ff09  cmp     edi, 20h ; ' '
0x14004ff0c  jnz     short loc_14004FED8
0x14004ff0e  lea     ebp, [rdi+30h]
0x14004ff11  lea     r14d, [rdi+10h]
0x14004ff15  lea     rbx, Lookaside
0x14004ff1c  xor     esi, esi
0x14004ff1e  mov     rcx, rbx; Lookaside
0x14004ff21  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004ff28  nop     dword ptr [rax+rax+00h]
0x14004ff2d  test    rax, rax
0x14004ff30  jz      loc_1400500D2
0x14004ff36  lea     rsi, [rax+10h]
0x14004ff3a  mov     [rax], rbx
0x14004ff3d  mov     dword ptr [rax+8], 7A697377h
0x14004ff44  lea     rbx, [rsi+158h]
0x14004ff4b  mov     eax, ebp
0x14004ff4d  mov     rcx, rbx; void *
0x14004ff50  mov     r8d, ebp; Size
0x14004ff53  xor     edx, edx; Val
0x14004ff55  mov     [rsp+78h+Size], rax
0x14004ff5d  call    memset
0x14004ff62  mov     rcx, [rsp+78h+arg_0]
0x14004ff6a  lea     rax, [rsi+130h]
0x14004ff71  mov     [rax+10h], rcx
0x14004ff75  mov     edx, 10h
0x14004ff7a  mov     [rax], rbx
0x14004ff7d  mov     [rax+8], ebp
0x14004ff80  mov     dword ptr [rax+20h], 1
0x14004ff87  lea     eax, [rbp-0Ch]
0x14004ff8a  mov     [rbx+4], eax
0x14004ff8d  mov     [rbx+8], eax
0x14004ff90  mov     dword ptr [rbx], 100180h
0x14004ff96  mov     eax, [r12+10h]
0x14004ff9b  mov     [rbx+0Ch], eax
0x14004ff9e  movzx   eax, word ptr [r12+14h]
0x14004ffa4  mov     [rbx+10h], ax
0x14004ffa8  mov     byte ptr [rbx+1Ch], 0
0x14004ffac  mov     eax, [r13+10h]
0x14004ffb0  mov     [rbx+14h], eax
0x14004ffb3  mov     dword ptr [rbx+18h], 3
0x14004ffba  mov     byte ptr [rbx+1Dh], 0
0x14004ffbe  mov     [rbx+1Eh], r14w
0x14004ffc3  mov     ecx, [r13+10h]
0x14004ffc7  sub     ecx, 2
0x14004ffca  jz      short loc_140050021
0x14004ffcc  sub     ecx, 2
0x14004ffcf  jz      short loc_140050012
0x14004ffd1  sub     ecx, 4
0x14004ffd4  jz      short loc_140050012
0x14004ffd6  cmp     ecx, 1
0x14004ffd9  jz      short loc_14004FFFC
0x14004ffdb  test    rbx, rbx
0x14004ffde  jz      short loc_14004FFF2
0x14004ffe0  mov     r8, [rsp+78h+Size]; Size
0x14004ffe8  xor     edx, edx; Val
0x14004ffea  mov     rcx, rbx; void *
0x14004ffed  call    memset
0x14004fff2  mov     ebx, 0C00000E5h
0x14004fff7  jmp     loc_1400500D7
0x14004fffc  xor     eax, eax
0x14004fffe  lea     rcx, [rbx+2Ch]
0x140050002  mov     [rbx+20h], eax
0x140050005  mov     [rbx+24h], ax
0x140050009  mov     dword ptr [rbx+28h], 20h ; ' '
0x140050010  jmp     short loc_140050034
0x140050012  xor     eax, eax
0x140050014  lea     rcx, [rbx+2Ch]
0x140050018  mov     [rbx+20h], eax
0x14005001b  mov     [rbx+24h], ax
0x14005001f  jmp     short loc_140050031
0x140050021  xor     eax, eax
0x140050023  lea     rcx, [rbx+30h]; void *
0x140050027  mov     [rbx+20h], eax
0x14005002a  mov     [rbx+24h], ax
0x14005002e  mov     [rbx+2Ch], edx
0x140050031  mov     [rbx+28h], edx
0x140050034  mov     r8d, edi; Size
0x140050037  mov     rdx, r15; Src
0x14005003a  call    memmove
0x14005003f  mov     [rsp+78h+var_40], 0; void *
0x140050048  lea     rax, ?FreeOidRequestBuffer@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; FreeOidRequestBuffer(_ADAPT *,DOT11_NDIS_REQUEST *)
0x14005004f  lea     rdi, [rsi+130h]
0x140050056  mov     r9d, ebp; unsigned int
0x140050059  mov     [rsp+78h+var_48], rdi; void *
0x14005005e  mov     edx, 1; unsigned int
0x140050063  mov     [rsp+78h+var_50], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x140050068  mov     r8d, 0E01018Ch; unsigned int
0x14005006e  mov     rcx, rsi; struct DOT11_NDIS_REQUEST *
0x140050071  mov     [rsp+78h+var_58], rbx; void *
0x140050076  call    ?Dot11BuildNdisRequest@@YAXPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@0@Z11@Z; Dot11BuildNdisRequest(DOT11_NDIS_REQUEST *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x14005007b  lock inc dword ptr [r12+24h]
0x140050081  mov     [rdi+18h], r12
0x140050085  lea     rcx, [rsp+78h+Size]; int *
0x14005008d  mov     rdi, [rsp+78h+arg_0]
0x140050095  mov     r8, [rsi+8]; struct _NDIS_OID_REQUEST *
0x140050099  mov     dword ptr [rsp+78h+Size], 0
0x1400500a4  mov     rdx, [rdi+10h]; struct _ADAPT *
0x1400500a8  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x1400500ad  mov     ebx, dword ptr [rsp+78h+Size]
0x1400500b4  cmp     ebx, 103h
0x1400500ba  jz      short loc_1400500CE
0x1400500bc  mov     rdx, [rsi+8]; struct _NDIS_OID_REQUEST *
0x1400500c0  mov     r8d, ebx; int
0x1400500c3  mov     rcx, [rdi+10h]; struct _ADAPT *
0x1400500c7  call    ?Dot11RequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z; Dot11RequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)
0x1400500cc  jmp     short loc_14005010B
0x1400500ce  xor     ebx, ebx
0x1400500d0  jmp     short loc_14005010B
0x1400500d2  mov     ebx, 0C000009Ah
0x1400500d7  test    rsi, rsi
0x1400500da  jz      short loc_14005010B
0x1400500dc  lea     rcx, [rsi-10h]; P
0x1400500e0  mov     rax, [rcx]
0x1400500e3  test    rax, rax
0x1400500e6  jz      short loc_1400500FC
0x1400500e8  mov     rdx, rcx; Entry
0x1400500eb  mov     rcx, rax; Lookaside
0x1400500ee  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400500f5  nop     dword ptr [rax+rax+00h]
0x1400500fa  jmp     short loc_14005010B
0x1400500fc  mov     edx, [rcx+8]; Tag
0x1400500ff  call    cs:__imp_ExFreePoolWithTag
0x140050106  nop     dword ptr [rax+rax+00h]
0x14005010b  mov     eax, ebx
0x14005010d  mov     rbx, [rsp+78h+arg_10]
0x140050115  add     rsp, 40h
0x140050119  pop     r15
0x14005011b  pop     r14
0x14005011d  pop     r13
0x14005011f  pop     r12
0x140050121  pop     rdi
0x140050122  pop     rsi
0x140050123  pop     rbp
0x140050124  retn
```
