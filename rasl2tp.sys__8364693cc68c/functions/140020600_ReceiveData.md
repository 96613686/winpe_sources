# ReceiveData

- ea: `0x140020600`
- end: `0x1400208e0`
- name: `ReceiveData`
- size: `736`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14001f940`
- `0x1400205d0`

## callees

- `0x1400047f0`
- `0x140004830`
- `0x140020600`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400206c3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400206c3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020811`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020863`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020811`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020863`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140020782`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140020782`
- `NDIS!NdisAllocateNetBufferList` at `0x140020757`
- `NDIS!NdisAllocateNetBufferList` at `0x140020757`
- `NDIS!NdisFreeNetBufferList` at `0x1400207fb`
- `NDIS!NdisFreeNetBufferList` at `0x1400207fb`
- `NETIO!RtlCopyMdlToMdl` at `0x1400207bc`
- `NETIO!RtlCopyMdlToMdl` at `0x1400207bc`

## pseudocode

```c
__int64 __fastcall ReceiveData(__int64 a1, __int64 a2, int a3, __int64 *a4, _QWORD *a5)
{
  __int64 v6; // r15
  _QWORD *v7; // rcx
  __int64 *v8; // rbx
  int v9; // ebp
  __int64 v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // r14
  _WORD *v13; // rax
  _DWORD *v14; // rcx
  _DWORD *v15; // rcx
  int v16; // eax
  unsigned int v17; // r12d
  ULONG i; // ebp
  __int64 v19; // rcx
  ULONG v20; // r15d
  ULONG v21; // eax
  USHORT v22; // dx
  void *v23; // rcx
  struct _NET_BUFFER_LIST *NetBufferList; // rax
  struct _NET_BUFFER_LIST *v25; // r13
  PNET_BUFFER FirstNetBuffer; // r8
  __int64 v27; // rcx
  __int128 v29; // xmm0
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
    goto LABEL_32;
  if ( (*(_DWORD *)(a1 + 392) & 0x20) != 0 && a4 )
  {
    while ( 1 )
    {
      if ( !v8 )
      {
        v7 = (_QWORD *)v33;
LABEL_32:
        if ( v7 )
          *v7 = v6;
        return 0;
      }
      if ( v9 == 2 )
      {
        v10 = v8[4];
        if ( v10 )
        {
          if ( *(_DWORD *)(v10 + 12) != 19 )
            return 0;
        }
      }
      if ( v8[3] <= (unsigned __int64)*(unsigned int *)(*(_QWORD *)(a1 + 72) + 8LL) || v9 == 1 )
        break;
LABEL_30:
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
          v29 = *((_OWORD *)v14 + 1);
          v35[0] = 23;
          *(_OWORD *)&v35[4] = v29;
          v12[3] = v35;
          v16 = v14[8];
          goto LABEL_17;
        }
      }
      else if ( *v13 == 2 )
      {
        if ( v14 )
        {
          if ( v14[3] == 19 )
          {
            v15 = v14 + 4;
            if ( v15 )
            {
              DWORD1(v34) = *v15;
              LOWORD(v34) = 2;
              v12[3] = &v34;
              v16 = v15[1];
LABEL_17:
              *((_DWORD *)v12 + 4) = v16;
            }
          }
        }
      }
    }
    v17 = *((_DWORD *)v8 + 4);
    for ( i = *((_DWORD *)v8 + 6); i; i -= v20 )
    {
      v19 = *(_QWORD *)(a1 + 72);
      v20 = i;
      v21 = *(_DWORD *)(v19 + 8);
      v22 = *(_WORD *)(v19 + 12);
      v23 = *(void **)v19;
      if ( i >= v21 )
        v20 = v21;
      NetBufferList = NdisAllocateNetBufferList(v23, v22, 0);
      v25 = NetBufferList;
      if ( !NetBufferList )
        goto LABEL_27;
      if ( NdisRetreatNetBufferListDataStart(NetBufferList, v20, 0, 0, 0) < 0
        || (FirstNetBuffer = v25->FirstNetBuffer,
            v27 = v8[1],
            v31 = 0,
            RtlCopyMdlToMdl(v27, v17, FirstNetBuffer->Link.Region, FirstNetBuffer->CurrentMdlOffset, v20, &v31),
            v31 != v20) )
      {
        NdisFreeNetBufferList(v25);
LABEL_27:
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 128), v12);
        return 0;
      }
      v17 += v20;
      v12[4] = v25;
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 512));
      (*(void (__fastcall **)(__int64, _QWORD *, struct _NET_BUFFER_LIST *))(a1 + 16))(a1 + 8, v12, v25);
    }
    v6 = v8[3] + v32;
    v32 = v6;
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 128), v12);
    v9 = a3;
    goto LABEL_30;
  }
  return 0;
}

```

## disassembly

```asm
0x140020600  mov     [rsp+arg_8], rbx
0x140020605  push    rbp
0x140020606  push    rsi
0x140020607  push    rdi
0x140020608  push    r12
0x14002060a  push    r13
0x14002060c  push    r14
0x14002060e  push    r15
0x140020610  sub     rsp, 90h
0x140020617  mov     rax, cs:__security_cookie
0x14002061e  xor     rax, rsp
0x140020621  mov     [rsp+0C8h+var_48], rax
0x140020629  xorps   xmm0, xmm0
0x14002062c  mov     [rsp+0C8h+var_98], r8d
0x140020631  mov     rsi, rcx
0x140020634  xor     r15d, r15d
0x140020637  mov     rcx, [rsp+0C8h+arg_20]
0x14002063f  mov     rbx, r9
0x140020642  mov     [rsp+0C8h+var_80], rcx
0x140020647  mov     ebp, r8d
0x14002064a  mov     [rsp+0C8h+var_88], r15
0x14002064f  movups  xmmword ptr [rsp+0C8h+var_68], xmm0
0x140020654  movups  xmmword ptr [rsp+0C8h+var_68+0Ch], xmm0
0x140020659  movups  [rsp+0C8h+var_78], xmm0
0x14002065e  test    rsi, rsi
0x140020661  jz      loc_14002088C
0x140020667  mov     eax, [rsi+188h]
0x14002066d  test    al, 20h
0x14002066f  jz      loc_14002081D
0x140020675  test    rbx, rbx
0x140020678  jz      loc_14002081D
0x14002067e  mov     r13d, 17h
0x140020684  mov     r12d, 2
0x14002068a  test    rbx, rbx
0x14002068d  jz      loc_140020887
0x140020693  cmp     ebp, 2
0x140020696  jnz     short loc_1400206AB
0x140020698  mov     rax, [rbx+20h]
0x14002069c  test    rax, rax
0x14002069f  jz      short loc_1400206AB
0x1400206a1  cmp     dword ptr [rax+0Ch], 13h
0x1400206a5  jnz     loc_14002081D
0x1400206ab  mov     rax, [rsi+48h]
0x1400206af  mov     ecx, [rax+8]
0x1400206b2  cmp     [rbx+18h], rcx
0x1400206b6  ja      loc_140020896
0x1400206bc  lea     rcx, [rsi+80h]; Lookaside
0x1400206c3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400206ca  nop     dword ptr [rax+rax+00h]
0x1400206cf  mov     r14, rax
0x1400206d2  test    rax, rax
0x1400206d5  jz      loc_14002081D
0x1400206db  mov     [rax], rsi
0x1400206de  cmp     ebp, 2
0x1400206e1  jnz     short loc_14002072E
0x1400206e3  mov     rax, [rbx+30h]
0x1400206e7  mov     rcx, [rbx+20h]
0x1400206eb  mov     [r14+8], rax
0x1400206ef  movzx   edx, word ptr [rax]
0x1400206f2  cmp     dx, 17h
0x1400206f6  jz      loc_1400208A1
0x1400206fc  cmp     dx, bp
0x1400206ff  jnz     short loc_14002072E
0x140020701  test    rcx, rcx
0x140020704  jz      short loc_14002072E
0x140020706  cmp     dword ptr [rcx+0Ch], 13h
0x14002070a  jnz     short loc_14002072E
0x14002070c  add     rcx, 10h
0x140020710  jz      short loc_14002072E
0x140020712  mov     eax, [rcx]
0x140020714  mov     dword ptr [rsp+0C8h+var_78+4], eax
0x140020718  lea     rax, [rsp+0C8h+var_78]
0x14002071d  mov     word ptr [rsp+0C8h+var_78], r12w
0x140020723  mov     [r14+18h], rax
0x140020727  mov     eax, [rcx+4]
0x14002072a  mov     [r14+10h], eax
0x14002072e  mov     r12d, [rbx+10h]
0x140020732  mov     ebp, [rbx+18h]
0x140020735  test    ebp, ebp
0x140020737  jz      loc_14002084B
0x14002073d  mov     rcx, [rsi+48h]
0x140020741  mov     r15d, ebp
0x140020744  mov     eax, [rcx+8]
0x140020747  cmp     ebp, eax
0x140020749  movzx   edx, word ptr [rcx+0Ch]; ContextSize
0x14002074d  mov     rcx, [rcx]; PoolHandle
0x140020750  cmovnb  r15d, eax
0x140020754  xor     r8d, r8d; ContextBackFill
0x140020757  call    cs:__imp_NdisAllocateNetBufferList
0x14002075e  nop     dword ptr [rax+rax+00h]
0x140020763  mov     r13, rax
0x140020766  test    rax, rax
0x140020769  jz      loc_140020807
0x14002076f  xor     edi, edi
0x140020771  xor     r9d, r9d; AllocateMdlHandler
0x140020774  xor     r8d, r8d; DataBackFill
0x140020777  mov     [rsp+0C8h+FreeMdlHandler], rdi; FreeMdlHandler
0x14002077c  mov     edx, r15d; DataOffsetDelta
0x14002077f  mov     rcx, rax; NetBufferList
0x140020782  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x140020789  nop     dword ptr [rax+rax+00h]
0x14002078e  test    eax, eax
0x140020790  js      short loc_1400207F8
0x140020792  mov     r8, [r13+8]
0x140020796  lea     rax, [rsp+0C8h+var_90]
0x14002079b  mov     rcx, [rbx+8]
0x14002079f  mov     [rsp+0C8h+var_90], rdi
0x1400207a4  mov     [rsp+0C8h+var_A0], rax
0x1400207a9  mov     r9d, [r8+10h]
0x1400207ad  mov     r8, [r8+8]
0x1400207b1  mov     edi, r15d
0x1400207b4  mov     edx, r12d
0x1400207b7  mov     [rsp+0C8h+FreeMdlHandler], rdi
0x1400207bc  call    cs:__imp_RtlCopyMdlToMdl
0x1400207c3  nop     dword ptr [rax+rax+00h]
0x1400207c8  cmp     [rsp+0C8h+var_90], rdi
0x1400207cd  jnz     short loc_1400207F8
0x1400207cf  add     r12d, r15d
0x1400207d2  mov     [r14+20h], r13
0x1400207d6  lock inc dword ptr [rsi+200h]
0x1400207dd  mov     rax, [rsi+10h]
0x1400207e1  lea     rcx, [rsi+8]
0x1400207e5  mov     r8, r13
0x1400207e8  mov     rdx, r14
0x1400207eb  call    _guard_dispatch_icall
0x1400207f0  sub     ebp, r15d
0x1400207f3  jmp     loc_140020735
0x1400207f8  mov     rcx, r13; NetBufferList
0x1400207fb  call    cs:__imp_NdisFreeNetBufferList
0x140020802  nop     dword ptr [rax+rax+00h]
0x140020807  lea     rcx, [rsi+80h]; Lookaside
0x14002080e  mov     rdx, r14; Entry
0x140020811  call    cs:__imp_ExFreeToNPagedLookasideList
0x140020818  nop     dword ptr [rax+rax+00h]
0x14002081d  xor     eax, eax
0x14002081f  mov     rcx, [rsp+0C8h+var_48]
0x140020827  xor     rcx, rsp; StackCookie
0x14002082a  call    __security_check_cookie
0x14002082f  mov     rbx, [rsp+0C8h+arg_8]
0x140020837  add     rsp, 90h
0x14002083e  pop     r15
0x140020840  pop     r14
0x140020842  pop     r13
0x140020844  pop     r12
0x140020846  pop     rdi
0x140020847  pop     rsi
0x140020848  pop     rbp
0x140020849  retn
0x14002084b  mov     r15, [rsp+0C8h+var_88]
0x140020850  lea     rcx, [rsi+80h]; Lookaside
0x140020857  add     r15, [rbx+18h]
0x14002085b  mov     rdx, r14; Entry
0x14002085e  mov     [rsp+0C8h+var_88], r15
0x140020863  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002086a  nop     dword ptr [rax+rax+00h]
0x14002086f  mov     ebp, [rsp+0C8h+var_98]
0x140020873  mov     r12d, 2
0x140020879  mov     r13d, 17h
0x14002087f  mov     rbx, [rbx]
0x140020882  jmp     loc_14002068A
0x140020887  mov     rcx, [rsp+0C8h+var_80]
0x14002088c  test    rcx, rcx
0x14002088f  jz      short loc_14002081D
0x140020891  mov     [rcx], r15
0x140020894  jmp     short loc_14002081D
0x140020896  cmp     ebp, 1
0x140020899  jz      loc_1400206BC
0x14002089f  jmp     short loc_14002087F
0x1400208a1  test    rcx, rcx
0x1400208a4  jz      loc_14002072E
0x1400208aa  cmp     dword ptr [rcx+0Ch], 13h
0x1400208ae  jnz     loc_14002072E
0x1400208b4  lea     rax, [rcx+10h]
0x1400208b8  test    rax, rax
0x1400208bb  jz      loc_14002072E
0x1400208c1  movups  xmm0, xmmword ptr [rax]
0x1400208c4  lea     rax, [rsp+0C8h+var_68]
0x1400208c9  mov     [rsp+0C8h+var_68], r13w
0x1400208cf  movups  xmmword ptr [rsp+0C8h+var_68+8], xmm0
0x1400208d4  mov     [r14+18h], rax
0x1400208d8  mov     eax, [rcx+20h]
0x1400208db  jmp     loc_14002072A
```
