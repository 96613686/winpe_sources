# ReceiveData

- ea: `0x14001ded0`
- end: `0x14001e1d0`
- name: `ReceiveData`
- size: `768`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14001cde0`
- `0x14001dea0`

## callees

- `0x1400076d0`
- `0x140007710`
- `0x14001ded0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e018`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e139`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e018`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e139`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001dfae`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001dfae`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x14001e080`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x14001e080`
- `NDIS!NdisAllocateNetBufferList` at `0x14001e055`
- `NDIS!NdisAllocateNetBufferList` at `0x14001e055`
- `NDIS!NdisFreeNetBufferList` at `0x14001e123`
- `NDIS!NdisFreeNetBufferList` at `0x14001e123`
- `NETIO!RtlCopyMdlToMdl` at `0x14001e0be`
- `NETIO!RtlCopyMdlToMdl` at `0x14001e0be`

## pseudocode

```c
__int64 __fastcall ReceiveData(__int64 a1, __int64 a2, int a3, __int64 *a4, _QWORD *a5)
{
  __int64 v6; // r13
  _QWORD *v7; // rcx
  __int64 *v8; // rbx
  int v9; // edi
  _QWORD *v11; // rax
  _QWORD *v12; // r14
  _WORD *v13; // rax
  _DWORD *v14; // rdx
  unsigned int v15; // r12d
  ULONG i; // esi
  __int64 v17; // rcx
  ULONG v18; // r15d
  ULONG v19; // eax
  USHORT v20; // dx
  void *v21; // rcx
  struct _NET_BUFFER_LIST *NetBufferList; // rax
  struct _NET_BUFFER_LIST *v23; // r13
  PNET_BUFFER FirstNetBuffer; // r8
  __int64 v25; // rcx
  __int64 v26; // rax
  __int128 v27; // xmm0
  int v28; // eax
  _DWORD *v29; // rdx
  __int64 v31; // [rsp+38h] [rbp-90h] BYREF
  __int64 v32; // [rsp+40h] [rbp-88h]
  __int64 v33; // [rsp+48h] [rbp-80h]
  __int128 v34; // [rsp+50h] [rbp-78h] BYREF
  _WORD v35[16]; // [rsp+60h] [rbp-68h] BYREF

  v6 = 0;
  v7 = a5;
  v8 = a4;
  v33 = (__int64)a5;
  v9 = a3;
  v32 = 0;
  memset(v35, 0, 28);
  v34 = 0;
  if ( !a1 )
  {
LABEL_2:
    if ( v7 )
      *v7 = v6;
    return 0;
  }
  if ( (*(_DWORD *)(a1 + 392) & 0x20) == 0 || !a4 )
    return 0;
  while ( 1 )
  {
    if ( !v8 )
    {
      v7 = (_QWORD *)v33;
      goto LABEL_2;
    }
    if ( v9 == 2 )
    {
      v26 = v8[4];
      if ( v26 )
      {
        if ( *(_DWORD *)(v26 + 12) != 19 )
          return 0;
      }
    }
    if ( v8[3] <= (unsigned __int64)*(unsigned int *)(*(_QWORD *)(a1 + 72) + 8LL) || v9 == 1 )
      break;
LABEL_18:
    v8 = (__int64 *)*v8;
  }
  v11 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 128));
  v12 = v11;
  if ( !v11 )
    return 0;
  *v11 = a1;
  if ( v9 == 2 )
  {
    v13 = (_WORD *)v8[6];
    v14 = (_DWORD *)v8[4];
    v12[1] = v13;
    if ( *v13 == 23 )
    {
      if ( v14 && v14[3] == 19 && v14 != (_DWORD *)-16LL )
      {
        v27 = *((_OWORD *)v14 + 1);
        v35[0] = 23;
        *(_OWORD *)&v35[4] = v27;
        v12[3] = v35;
        v28 = v14[8];
LABEL_40:
        *((_DWORD *)v12 + 4) = v28;
      }
    }
    else if ( *v13 == 2 )
    {
      if ( v14 )
      {
        if ( v14[3] == 19 )
        {
          v29 = v14 + 4;
          if ( v29 )
          {
            DWORD1(v34) = *v29;
            LOWORD(v34) = 2;
            v12[3] = &v34;
            v28 = v29[1];
            goto LABEL_40;
          }
        }
      }
    }
  }
  v15 = *((_DWORD *)v8 + 4);
  for ( i = *((_DWORD *)v8 + 6); ; i -= v18 )
  {
    if ( !i )
    {
      v6 = v8[3] + v32;
      v32 = v6;
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 128), v12);
      v9 = a3;
      goto LABEL_18;
    }
    v17 = *(_QWORD *)(a1 + 72);
    v18 = i;
    v19 = *(_DWORD *)(v17 + 8);
    v20 = *(_WORD *)(v17 + 12);
    v21 = *(void **)v17;
    if ( i >= v19 )
      v18 = v19;
    NetBufferList = NdisAllocateNetBufferList(v21, v20, 0);
    v23 = NetBufferList;
    if ( !NetBufferList )
      break;
    if ( NdisRetreatNetBufferListDataStart(NetBufferList, v18, 0, 0, 0) < 0
      || (FirstNetBuffer = v23->FirstNetBuffer,
          v25 = v8[1],
          v31 = 0,
          RtlCopyMdlToMdl(v25, v15, FirstNetBuffer->Link.Region, FirstNetBuffer->CurrentMdlOffset, v18, &v31),
          v31 != v18) )
    {
      NdisFreeNetBufferList(v23);
      break;
    }
    v15 += v18;
    v12[4] = v23;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 512));
    (*(void (__fastcall **)(__int64, _QWORD *, struct _NET_BUFFER_LIST *))(a1 + 16))(a1 + 8, v12, v23);
  }
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 128), v12);
  return 0;
}

```

## disassembly

```asm
0x14001ded0  mov     [rsp+arg_8], rbx
0x14001ded5  push    rbp
0x14001ded6  push    rsi
0x14001ded7  push    rdi
0x14001ded8  push    r12
0x14001deda  push    r13
0x14001dedc  push    r14
0x14001dede  push    r15
0x14001dee0  sub     rsp, 90h
0x14001dee7  mov     rax, cs:__security_cookie
0x14001deee  xor     rax, rsp
0x14001def1  mov     [rsp+0C8h+var_48], rax
0x14001def9  xorps   xmm0, xmm0
0x14001defc  mov     [rsp+0C8h+var_98], r8d
0x14001df01  mov     rbp, rcx
0x14001df04  xor     r13d, r13d
0x14001df07  mov     rcx, [rsp+0C8h+arg_20]
0x14001df0f  mov     rbx, r9
0x14001df12  mov     [rsp+0C8h+var_80], rcx
0x14001df17  mov     edi, r8d
0x14001df1a  mov     [rsp+0C8h+var_88], r13
0x14001df1f  movups  xmmword ptr [rsp+0C8h+var_68], xmm0
0x14001df24  movups  xmmword ptr [rsp+0C8h+var_68+0Ch], xmm0
0x14001df29  movups  [rsp+0C8h+var_78], xmm0
0x14001df2e  test    rbp, rbp
0x14001df31  jnz     short loc_14001DF6A
0x14001df33  test    rcx, rcx
0x14001df36  jnz     loc_14001E1C8
0x14001df3c  xor     eax, eax
0x14001df3e  mov     rcx, [rsp+0C8h+var_48]
0x14001df46  xor     rcx, rsp; StackCookie
0x14001df49  call    __security_check_cookie
0x14001df4e  mov     rbx, [rsp+0C8h+arg_8]
0x14001df56  add     rsp, 90h
0x14001df5d  pop     r15
0x14001df5f  pop     r14
0x14001df61  pop     r13
0x14001df63  pop     r12
0x14001df65  pop     rdi
0x14001df66  pop     rsi
0x14001df67  pop     rbp
0x14001df68  retn
0x14001df6a  mov     eax, [rbp+188h]
0x14001df70  test    al, 20h
0x14001df72  jz      short loc_14001DF3C
0x14001df74  test    rbx, rbx
0x14001df77  jz      short loc_14001DF3C
0x14001df79  mov     esi, 2
0x14001df7e  mov     r12d, 17h
0x14001df84  test    rbx, rbx
0x14001df87  jz      loc_14001E116
0x14001df8d  cmp     edi, 2
0x14001df90  jz      loc_14001E0FA
0x14001df96  mov     rax, [rbp+48h]
0x14001df9a  mov     ecx, [rax+8]
0x14001df9d  cmp     [rbx+18h], rcx
0x14001dfa1  ja      loc_14001E14A
0x14001dfa7  lea     rcx, [rbp+80h]; Lookaside
0x14001dfae  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001dfb5  nop     dword ptr [rax+rax+00h]
0x14001dfba  mov     r14, rax
0x14001dfbd  test    rax, rax
0x14001dfc0  jz      loc_14001DF3C
0x14001dfc6  mov     [rax], rbp
0x14001dfc9  cmp     edi, 2
0x14001dfcc  jnz     short loc_14001DFF5
0x14001dfce  mov     rax, [rbx+30h]
0x14001dfd2  mov     rdx, [rbx+20h]
0x14001dfd6  mov     [r14+8], rax
0x14001dfda  movzx   ecx, word ptr [rax]
0x14001dfdd  cmp     cx, 17h
0x14001dfe1  jz      loc_14001E158
0x14001dfe7  cmp     cx, di
0x14001dfea  jnz     short loc_14001DFF5
0x14001dfec  test    rdx, rdx
0x14001dfef  jnz     loc_14001E194
0x14001dff5  mov     r12d, [rbx+10h]
0x14001dff9  mov     esi, [rbx+18h]
0x14001dffc  test    esi, esi
0x14001dffe  jnz     short loc_14001E03B
0x14001e000  mov     r13, [rsp+0C8h+var_88]
0x14001e005  lea     rcx, [rbp+80h]; Lookaside
0x14001e00c  add     r13, [rbx+18h]
0x14001e010  mov     rdx, r14; Entry
0x14001e013  mov     [rsp+0C8h+var_88], r13
0x14001e018  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001e01f  nop     dword ptr [rax+rax+00h]
0x14001e024  mov     edi, [rsp+0C8h+var_98]
0x14001e028  mov     esi, 2
0x14001e02d  mov     r12d, 17h
0x14001e033  mov     rbx, [rbx]
0x14001e036  jmp     loc_14001DF84
0x14001e03b  mov     rcx, [rbp+48h]
0x14001e03f  mov     r15d, esi
0x14001e042  mov     eax, [rcx+8]
0x14001e045  cmp     esi, eax
0x14001e047  movzx   edx, word ptr [rcx+0Ch]; ContextSize
0x14001e04b  mov     rcx, [rcx]; PoolHandle
0x14001e04e  cmovnb  r15d, eax
0x14001e052  xor     r8d, r8d; ContextBackFill
0x14001e055  call    cs:__imp_NdisAllocateNetBufferList
0x14001e05c  nop     dword ptr [rax+rax+00h]
0x14001e061  mov     r13, rax
0x14001e064  test    rax, rax
0x14001e067  jz      loc_14001E12F
0x14001e06d  xor     edi, edi
0x14001e06f  xor     r9d, r9d; AllocateMdlHandler
0x14001e072  xor     r8d, r8d; DataBackFill
0x14001e075  mov     [rsp+0C8h+FreeMdlHandler], rdi; FreeMdlHandler
0x14001e07a  mov     edx, r15d; DataOffsetDelta
0x14001e07d  mov     rcx, rax; NetBufferList
0x14001e080  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x14001e087  nop     dword ptr [rax+rax+00h]
0x14001e08c  test    eax, eax
0x14001e08e  js      loc_14001E120
0x14001e094  mov     r8, [r13+8]
0x14001e098  lea     rax, [rsp+0C8h+var_90]
0x14001e09d  mov     rcx, [rbx+8]
0x14001e0a1  mov     [rsp+0C8h+var_90], rdi
0x14001e0a6  mov     [rsp+0C8h+var_A0], rax
0x14001e0ab  mov     r9d, [r8+10h]
0x14001e0af  mov     r8, [r8+8]
0x14001e0b3  mov     edi, r15d
0x14001e0b6  mov     edx, r12d
0x14001e0b9  mov     [rsp+0C8h+FreeMdlHandler], rdi
0x14001e0be  call    cs:__imp_RtlCopyMdlToMdl
0x14001e0c5  nop     dword ptr [rax+rax+00h]
0x14001e0ca  cmp     [rsp+0C8h+var_90], rdi
0x14001e0cf  jnz     short loc_14001E120
0x14001e0d1  add     r12d, r15d
0x14001e0d4  mov     [r14+20h], r13
0x14001e0d8  lock inc dword ptr [rbp+200h]
0x14001e0df  mov     rax, [rbp+10h]
0x14001e0e3  lea     rcx, [rbp+8]
0x14001e0e7  mov     r8, r13
0x14001e0ea  mov     rdx, r14
0x14001e0ed  call    _guard_dispatch_icall
0x14001e0f2  sub     esi, r15d
0x14001e0f5  jmp     loc_14001DFFC
0x14001e0fa  mov     rax, [rbx+20h]
0x14001e0fe  test    rax, rax
0x14001e101  jz      loc_14001DF96
0x14001e107  cmp     dword ptr [rax+0Ch], 13h
0x14001e10b  jnz     loc_14001DF3C
0x14001e111  jmp     loc_14001DF96
0x14001e116  mov     rcx, [rsp+0C8h+var_80]
0x14001e11b  jmp     loc_14001DF33
0x14001e120  mov     rcx, r13; NetBufferList
0x14001e123  call    cs:__imp_NdisFreeNetBufferList
0x14001e12a  nop     dword ptr [rax+rax+00h]
0x14001e12f  lea     rcx, [rbp+80h]; Lookaside
0x14001e136  mov     rdx, r14; Entry
0x14001e139  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001e140  nop     dword ptr [rax+rax+00h]
0x14001e145  jmp     loc_14001DF3C
0x14001e14a  cmp     edi, 1
0x14001e14d  jnz     loc_14001E033
0x14001e153  jmp     loc_14001DFA7
0x14001e158  test    rdx, rdx
0x14001e15b  jz      loc_14001DFF5
0x14001e161  cmp     dword ptr [rdx+0Ch], 13h
0x14001e165  jnz     loc_14001DFF5
0x14001e16b  lea     rax, [rdx+10h]
0x14001e16f  test    rax, rax
0x14001e172  jz      loc_14001DFF5
0x14001e178  movups  xmm0, xmmword ptr [rax]
0x14001e17b  lea     rax, [rsp+0C8h+var_68]
0x14001e180  mov     [rsp+0C8h+var_68], r12w
0x14001e186  movups  xmmword ptr [rsp+0C8h+var_68+8], xmm0
0x14001e18b  mov     [r14+18h], rax
0x14001e18f  mov     eax, [rdx+20h]
0x14001e192  jmp     short loc_14001E1BF
0x14001e194  cmp     dword ptr [rdx+0Ch], 13h
0x14001e198  jnz     loc_14001DFF5
0x14001e19e  add     rdx, 10h
0x14001e1a2  jz      loc_14001DFF5
0x14001e1a8  mov     eax, [rdx]
0x14001e1aa  mov     dword ptr [rsp+0C8h+var_78+4], eax
0x14001e1ae  lea     rax, [rsp+0C8h+var_78]
0x14001e1b3  mov     word ptr [rsp+0C8h+var_78], si
0x14001e1b8  mov     [r14+18h], rax
0x14001e1bc  mov     eax, [rdx+4]
0x14001e1bf  mov     [r14+10h], eax
0x14001e1c3  jmp     loc_14001DFF5
0x14001e1c8  mov     [rcx], r13
0x14001e1cb  jmp     loc_14001DF3C
```
