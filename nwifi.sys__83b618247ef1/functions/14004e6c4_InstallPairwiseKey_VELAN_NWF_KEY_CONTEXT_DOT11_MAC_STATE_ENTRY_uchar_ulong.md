# InstallPairwiseKey(_VELAN *,_NWF_KEY_CONTEXT *,DOT11_MAC_STATE_ENTRY *,uchar *,ulong)

- ea: `0x14004e6c4`
- end: `0x14004e966`
- name: `?InstallPairwiseKey@@YAJPEAU_VELAN@@PEAU_NWF_KEY_CONTEXT@@PEAUDOT11_MAC_STATE_ENTRY@@PEAEK@Z`
- size: `674`
- prototype: `int(struct _VELAN *, struct _NWF_KEY_CONTEXT *, struct DOT11_MAC_STATE_ENTRY *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004e96c`

## callees

- `0x1400160e0`
- `0x1400165c4`
- `0x14001a320`
- `0x14004e6c4`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004e761`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004e761`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e92e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e92e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e93f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e93f`

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
0x14004e6c4  mov     [rsp+arg_10], rbx
0x14004e6c9  mov     [rsp+arg_0], rcx
0x14004e6ce  push    rbp
0x14004e6cf  push    rsi
0x14004e6d0  push    rdi
0x14004e6d1  push    r12
0x14004e6d3  push    r13
0x14004e6d5  push    r14
0x14004e6d7  push    r15
0x14004e6d9  sub     rsp, 40h
0x14004e6dd  mov     r10d, [rdx+10h]
0x14004e6e1  mov     r15, r9
0x14004e6e4  mov     r12, r8
0x14004e6e7  mov     r13, rdx
0x14004e6ea  sub     r10d, 2
0x14004e6ee  jz      short loc_14004E742
0x14004e6f0  sub     r10d, 2
0x14004e6f4  jz      short loc_14004E72D
0x14004e6f6  sub     r10d, 4
0x14004e6fa  jz      short loc_14004E72D
0x14004e6fc  cmp     r10d, 1
0x14004e700  jz      short loc_14004E70C
0x14004e702  mov     ebx, 0C00000E5h
0x14004e707  jmp     loc_14004E94B
0x14004e70c  mov     edi, dword ptr [rsp+78h+arg_20]
0x14004e713  cmp     edi, 20h ; ' '
0x14004e716  jz      short loc_14004E722
0x14004e718  mov     ebx, 0C0000001h
0x14004e71d  jmp     loc_14004E94B
0x14004e722  mov     ebp, 4Ch ; 'L'
0x14004e727  lea     r14d, [rbp-20h]
0x14004e72b  jmp     short loc_14004E755
0x14004e72d  mov     edi, dword ptr [rsp+78h+arg_20]
0x14004e734  cmp     edi, 10h
0x14004e737  jnz     short loc_14004E718
0x14004e739  lea     ebp, [rdi+2Ch]
0x14004e73c  lea     r14d, [rdi+0Ch]
0x14004e740  jmp     short loc_14004E755
0x14004e742  mov     edi, dword ptr [rsp+78h+arg_20]
0x14004e749  cmp     edi, 20h ; ' '
0x14004e74c  jnz     short loc_14004E718
0x14004e74e  lea     ebp, [rdi+30h]
0x14004e751  lea     r14d, [rdi+10h]
0x14004e755  lea     rbx, Lookaside
0x14004e75c  xor     esi, esi
0x14004e75e  mov     rcx, rbx; Lookaside
0x14004e761  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004e768  nop     dword ptr [rax+rax+00h]
0x14004e76d  test    rax, rax
0x14004e770  jz      loc_14004E912
0x14004e776  lea     rsi, [rax+10h]
0x14004e77a  mov     [rax], rbx
0x14004e77d  mov     dword ptr [rax+8], 7A697377h
0x14004e784  lea     rbx, [rsi+158h]
0x14004e78b  mov     eax, ebp
0x14004e78d  mov     rcx, rbx; void *
0x14004e790  mov     r8d, ebp; Size
0x14004e793  xor     edx, edx; Val
0x14004e795  mov     [rsp+78h+Size], rax
0x14004e79d  call    memset
0x14004e7a2  mov     rcx, [rsp+78h+arg_0]
0x14004e7aa  lea     rax, [rsi+130h]
0x14004e7b1  mov     [rax+10h], rcx
0x14004e7b5  mov     edx, 10h
0x14004e7ba  mov     [rax], rbx
0x14004e7bd  mov     [rax+8], ebp
0x14004e7c0  mov     dword ptr [rax+20h], 1
0x14004e7c7  lea     eax, [rbp-0Ch]
0x14004e7ca  mov     [rbx+4], eax
0x14004e7cd  mov     [rbx+8], eax
0x14004e7d0  mov     dword ptr [rbx], 100180h
0x14004e7d6  mov     eax, [r12+10h]
0x14004e7db  mov     [rbx+0Ch], eax
0x14004e7de  movzx   eax, word ptr [r12+14h]
0x14004e7e4  mov     [rbx+10h], ax
0x14004e7e8  mov     byte ptr [rbx+1Ch], 0
0x14004e7ec  mov     eax, [r13+10h]
0x14004e7f0  mov     [rbx+14h], eax
0x14004e7f3  mov     dword ptr [rbx+18h], 3
0x14004e7fa  mov     byte ptr [rbx+1Dh], 0
0x14004e7fe  mov     [rbx+1Eh], r14w
0x14004e803  mov     ecx, [r13+10h]
0x14004e807  sub     ecx, 2
0x14004e80a  jz      short loc_14004E861
0x14004e80c  sub     ecx, 2
0x14004e80f  jz      short loc_14004E852
0x14004e811  sub     ecx, 4
0x14004e814  jz      short loc_14004E852
0x14004e816  cmp     ecx, 1
0x14004e819  jz      short loc_14004E83C
0x14004e81b  test    rbx, rbx
0x14004e81e  jz      short loc_14004E832
0x14004e820  mov     r8, [rsp+78h+Size]; Size
0x14004e828  xor     edx, edx; Val
0x14004e82a  mov     rcx, rbx; void *
0x14004e82d  call    memset
0x14004e832  mov     ebx, 0C00000E5h
0x14004e837  jmp     loc_14004E917
0x14004e83c  xor     eax, eax
0x14004e83e  lea     rcx, [rbx+2Ch]
0x14004e842  mov     [rbx+20h], eax
0x14004e845  mov     [rbx+24h], ax
0x14004e849  mov     dword ptr [rbx+28h], 20h ; ' '
0x14004e850  jmp     short loc_14004E874
0x14004e852  xor     eax, eax
0x14004e854  lea     rcx, [rbx+2Ch]
0x14004e858  mov     [rbx+20h], eax
0x14004e85b  mov     [rbx+24h], ax
0x14004e85f  jmp     short loc_14004E871
0x14004e861  xor     eax, eax
0x14004e863  lea     rcx, [rbx+30h]; void *
0x14004e867  mov     [rbx+20h], eax
0x14004e86a  mov     [rbx+24h], ax
0x14004e86e  mov     [rbx+2Ch], edx
0x14004e871  mov     [rbx+28h], edx
0x14004e874  mov     r8d, edi; Size
0x14004e877  mov     rdx, r15; Src
0x14004e87a  call    memmove
0x14004e87f  mov     [rsp+78h+var_40], 0; void *
0x14004e888  lea     rax, ?FreeOidRequestBuffer@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; FreeOidRequestBuffer(_ADAPT *,DOT11_NDIS_REQUEST *)
0x14004e88f  lea     rdi, [rsi+130h]
0x14004e896  mov     r9d, ebp; unsigned int
0x14004e899  mov     [rsp+78h+var_48], rdi; void *
0x14004e89e  mov     edx, 1; unsigned int
0x14004e8a3  mov     [rsp+78h+var_50], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x14004e8a8  mov     r8d, 0E01018Ch; unsigned int
0x14004e8ae  mov     rcx, rsi; struct DOT11_NDIS_REQUEST *
0x14004e8b1  mov     [rsp+78h+var_58], rbx; void *
0x14004e8b6  call    ?Dot11BuildNdisRequest@@YAXPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@0@Z11@Z; Dot11BuildNdisRequest(DOT11_NDIS_REQUEST *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x14004e8bb  lock inc dword ptr [r12+24h]
0x14004e8c1  mov     [rdi+18h], r12
0x14004e8c5  lea     rcx, [rsp+78h+Size]; int *
0x14004e8cd  mov     rdi, [rsp+78h+arg_0]
0x14004e8d5  mov     r8, [rsi+8]; struct _NDIS_OID_REQUEST *
0x14004e8d9  mov     dword ptr [rsp+78h+Size], 0
0x14004e8e4  mov     rdx, [rdi+10h]; struct _ADAPT *
0x14004e8e8  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x14004e8ed  mov     ebx, dword ptr [rsp+78h+Size]
0x14004e8f4  cmp     ebx, 103h
0x14004e8fa  jz      short loc_14004E90E
0x14004e8fc  mov     rdx, [rsi+8]; struct _NDIS_OID_REQUEST *
0x14004e900  mov     r8d, ebx; int
0x14004e903  mov     rcx, [rdi+10h]; struct _ADAPT *
0x14004e907  call    ?Dot11RequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z; Dot11RequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)
0x14004e90c  jmp     short loc_14004E94B
0x14004e90e  xor     ebx, ebx
0x14004e910  jmp     short loc_14004E94B
0x14004e912  mov     ebx, 0C000009Ah
0x14004e917  test    rsi, rsi
0x14004e91a  jz      short loc_14004E94B
0x14004e91c  lea     rcx, [rsi-10h]; P
0x14004e920  mov     rax, [rcx]
0x14004e923  test    rax, rax
0x14004e926  jz      short loc_14004E93C
0x14004e928  mov     rdx, rcx; Entry
0x14004e92b  mov     rcx, rax; Lookaside
0x14004e92e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004e935  nop     dword ptr [rax+rax+00h]
0x14004e93a  jmp     short loc_14004E94B
0x14004e93c  mov     edx, [rcx+8]; Tag
0x14004e93f  call    cs:__imp_ExFreePoolWithTag
0x14004e946  nop     dword ptr [rax+rax+00h]
0x14004e94b  mov     eax, ebx
0x14004e94d  mov     rbx, [rsp+78h+arg_10]
0x14004e955  add     rsp, 40h
0x14004e959  pop     r15
0x14004e95b  pop     r14
0x14004e95d  pop     r13
0x14004e95f  pop     r12
0x14004e961  pop     rdi
0x14004e962  pop     rsi
0x14004e963  pop     rbp
0x14004e964  retn
```
