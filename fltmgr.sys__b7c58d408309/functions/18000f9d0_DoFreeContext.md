# DoFreeContext

- ea: `0x18000f9d0`
- end: `0x18000fc6a`
- name: `DoFreeContext`
- size: `666`
- prototype: `void __fastcall(void ***P)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e5e0`
- `0x18000f680`

## callees

- `0x18000f9d0`
- `0x180010400`
- `0x18001bb10`
- `0x180024880`
- `0x180024c00`
- `0x18005dcc0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000facc`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000facc`
- `ntoskrnl!ObfDereferenceObject` at `0x18000fb1c`
- `ntoskrnl!ObfDereferenceObject` at `0x18000fc37`
- `ntoskrnl!ObfDereferenceObject` at `0x18000fb1c`
- `ntoskrnl!ObfDereferenceObject` at `0x18000fc37`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000fab3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000fb50`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000fc04`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000fab3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000fb50`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000fc04`
- `ntoskrnl!ZwClose` at `0x18000fc49`
- `ntoskrnl!ZwClose` at `0x18000fc49`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18000fa51`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18000fa51`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18000fa64`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18000fa64`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000fbd3`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000fbd3`

## pseudocode

```c
void __fastcall DoFreeContext(void ***P)
{
  void **v1; // rdi
  int v3; // r14d
  __int16 v4; // ax
  void (__fastcall *v5)(void ***, _QWORD); // rax
  void **v6; // rsi
  __int16 v7; // ax
  int v8; // ecx
  int v9; // eax
  void *v10; // rdi
  int v11; // ecx
  ULONG v12; // edx
  void **v13; // rax
  void *v14; // rcx
  void *v15; // rsi
  volatile signed __int32 *v16; // rcx
  unsigned __int64 v17; // rbx
  void *v18; // rcx
  signed __int64 v19; // rax

  v1 = P[1];
  v3 = (_DWORD)P[9] & 2;
  v4 = *((_WORD *)v1 + 12);
  if ( v4 == 32 )
  {
    v18 = (*P)[1];
    if ( v18 != (void *)-1LL )
    {
      ObfDereferenceObject(v18);
      ZwClose(**P);
    }
    if ( ((_DWORD)P[9] & 4) != 0 )
    {
      v19 = _InterlockedCompareExchange64((volatile signed __int64 *)P + 2, 0, (signed __int64)P[2]);
      if ( v19 )
        FltpObjectPointerDereference(v19);
    }
  }
  else if ( v4 == 64 )
  {
    v13 = *P;
    v14 = **P;
    v15 = v13[1];
    if ( v14 )
      FltObjectDereference(v14);
    if ( v15 )
      ObfDereferenceObject(v15);
    memset(*P, 0, 0x58u);
  }
  v5 = (void (__fastcall *)(void ***, _QWORD))v1[1];
  if ( v5 )
    v5(P + 12, *((unsigned __int16 *)v1 + 12));
  v6 = P[1];
  v7 = *((_WORD *)v6 + 12);
  if ( v7 == 32 )
  {
    if ( *P )
      ExFreeToNPagedLookasideList(&stru_18003F040, *P);
  }
  else if ( v7 == 64 && *P )
  {
    ExFreeToNPagedLookasideList(&stru_18003F240, *P);
  }
  v8 = *((unsigned __int8 *)v6 + 27);
  if ( v8 == 1 )
  {
    v9 = *((_DWORD *)P + 18);
    if ( (v9 & 1) != 0 )
    {
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v6 + 24), P);
      goto LABEL_10;
    }
    if ( (v9 & 8) == 0 )
    {
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v6 + 8), P);
      goto LABEL_10;
    }
    v12 = *((_DWORD *)v6 + 58);
    goto LABEL_19;
  }
  v11 = v8 - 2;
  if ( !v11 )
  {
    v12 = *((_DWORD *)v6 + 8);
LABEL_19:
    ExFreePoolWithTag(P, v12);
    goto LABEL_10;
  }
  if ( v11 == 1 )
    ((void (__fastcall *)(void ***, _QWORD))v6[5])(P, *((unsigned __int16 *)v6 + 12));
LABEL_10:
  v10 = *v1;
  ExReleaseRundownProtection((PEX_RUNDOWN_REF)v10 + 1);
  if ( (FltGlobals & 0x2000) != 0 && (*(_DWORD *)v10 & 0x2000000) != 0
    || (FltGlobals & 0x4000) != 0 && (*(_DWORD *)v10 & 0x4000000) != 0
    || (FltGlobals & 0x8000) != 0 && (*(_DWORD *)v10 & 0x1000000) != 0 )
  {
    v16 = (volatile signed __int32 *)*((_QWORD *)v10 + 4);
    if ( v16 )
    {
      v17 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(v16, 1u) + 1) & 0x3FF) << 7;
      *(_DWORD *)(v17 + *((_QWORD *)v10 + 4) + 8) = -1;
      *(_QWORD *)(v17 + *((_QWORD *)v10 + 4) + 16) = *((_QWORD *)v10 + 1);
      memset((void *)(v17 + *((_QWORD *)v10 + 4) + 24LL), 0, 0x70u);
      RtlWalkFrameChain((PVOID *)(v17 + *((_QWORD *)v10 + 4) + 24LL), 0xEu, 0);
    }
  }
  if ( v3 )
    FltpDequeueThrottledWorkItem(1);
}

```

## disassembly

```asm
0x18000f9d0  push    rbx
0x18000f9d2  push    rsi
0x18000f9d3  push    rdi
0x18000f9d4  push    r14
0x18000f9d6  sub     rsp, 28h
0x18000f9da  mov     rdi, [rcx+8]
0x18000f9de  mov     rbx, rcx
0x18000f9e1  mov     r14d, [rcx+48h]
0x18000f9e5  and     r14d, 2
0x18000f9e9  movzx   eax, word ptr [rdi+18h]
0x18000f9ed  cmp     ax, 20h ; ' '
0x18000f9f1  jz      loc_18000FC26
0x18000f9f7  cmp     ax, 40h ; '@'
0x18000f9fb  jz      loc_18000FB00
0x18000fa01  mov     rax, [rdi+8]
0x18000fa05  test    rax, rax
0x18000fa08  jz      short loc_18000FA17
0x18000fa0a  movzx   edx, word ptr [rdi+18h]
0x18000fa0e  lea     rcx, [rbx+60h]
0x18000fa12  call    _guard_dispatch_icall
0x18000fa17  mov     rsi, [rbx+8]
0x18000fa1b  movzx   eax, word ptr [rsi+18h]
0x18000fa1f  cmp     ax, 20h ; ' '
0x18000fa23  jz      loc_18000FBF1
0x18000fa29  cmp     ax, 40h ; '@'
0x18000fa2d  jz      loc_18000FB3D
0x18000fa33  movzx   ecx, byte ptr [rsi+1Bh]
0x18000fa37  cmp     ecx, 1
0x18000fa3a  jnz     loc_18000FAC1
0x18000fa40  mov     eax, [rbx+48h]
0x18000fa43  test    cl, al
0x18000fa45  jz      short loc_18000FAA8
0x18000fa47  lea     rcx, [rsi+0C0h]; Lookaside
0x18000fa4e  mov     rdx, rbx; Entry
0x18000fa51  call    cs:__imp_ExFreeToPagedLookasideList
0x18000fa58  nop     dword ptr [rax+rax+00h]
0x18000fa5d  mov     rdi, [rdi]
0x18000fa60  lea     rcx, [rdi+8]; RunRef
0x18000fa64  call    cs:__imp_ExReleaseRundownProtection
0x18000fa6b  nop     dword ptr [rax+rax+00h]
0x18000fa70  mov     ecx, cs:FltGlobals
0x18000fa76  bt      ecx, 0Dh
0x18000fa7a  jb      loc_18000FBE4
0x18000fa80  bt      ecx, 0Eh
0x18000fa84  jb      loc_18000FB61
0x18000fa8a  bt      ecx, 0Fh
0x18000fa8e  jb      loc_18000FC15
0x18000fa94  test    r14d, r14d
0x18000fa97  jnz     loc_18000FC5B
0x18000fa9d  add     rsp, 28h
0x18000faa1  pop     r14
0x18000faa3  pop     rdi
0x18000faa4  pop     rsi
0x18000faa5  pop     rbx
0x18000faa6  retn
0x18000faa8  test    al, 8
0x18000faaa  jnz     short loc_18000FAF8
0x18000faac  lea     rcx, [rsi+40h]; Lookaside
0x18000fab0  mov     rdx, rbx; Entry
0x18000fab3  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000faba  nop     dword ptr [rax+rax+00h]
0x18000fabf  jmp     short loc_18000FA5D
0x18000fac1  sub     ecx, 2
0x18000fac4  jnz     short loc_18000FADA
0x18000fac6  mov     edx, [rsi+20h]; Tag
0x18000fac9  mov     rcx, rbx; P
0x18000facc  call    cs:__imp_ExFreePoolWithTag
0x18000fad3  nop     dword ptr [rax+rax+00h]
0x18000fad8  jmp     short loc_18000FA5D
0x18000fada  cmp     ecx, 1
0x18000fadd  jnz     loc_18000FA5D
0x18000fae3  mov     rax, [rsi+28h]
0x18000fae7  mov     rcx, rbx
0x18000faea  movzx   edx, word ptr [rsi+18h]
0x18000faee  call    _guard_dispatch_icall
0x18000faf3  jmp     loc_18000FA5D
0x18000faf8  mov     edx, [rsi+0E8h]
0x18000fafe  jmp     short loc_18000FAC9
0x18000fb00  mov     rax, [rcx]
0x18000fb03  mov     rcx, [rax]; FltObject
0x18000fb06  mov     rsi, [rax+8]
0x18000fb0a  test    rcx, rcx
0x18000fb0d  jz      short loc_18000FB14
0x18000fb0f  call    FltObjectDereference
0x18000fb14  test    rsi, rsi
0x18000fb17  jz      short loc_18000FB28
0x18000fb19  mov     rcx, rsi; Object
0x18000fb1c  call    cs:__imp_ObfDereferenceObject
0x18000fb23  nop     dword ptr [rax+rax+00h]
0x18000fb28  mov     rcx, [rbx]; void *
0x18000fb2b  xor     edx, edx; Val
0x18000fb2d  mov     r8d, 58h ; 'X'; Size
0x18000fb33  call    memset
0x18000fb38  jmp     loc_18000FA01
0x18000fb3d  mov     rdx, [rbx]; Entry
0x18000fb40  test    rdx, rdx
0x18000fb43  jz      loc_18000FA33
0x18000fb49  lea     rcx, stru_18003F240; Lookaside
0x18000fb50  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000fb57  nop     dword ptr [rax+rax+00h]
0x18000fb5c  jmp     loc_18000FA33
0x18000fb61  test    dword ptr [rdi], 4000000h
0x18000fb67  jz      loc_18000FA8A
0x18000fb6d  mov     rcx, [rdi+20h]
0x18000fb71  test    rcx, rcx
0x18000fb74  jz      loc_18000FA94
0x18000fb7a  mov     ebx, 1
0x18000fb7f  lock xadd [rcx], ebx
0x18000fb83  mov     rax, [rdi+20h]
0x18000fb87  inc     ebx
0x18000fb89  and     ebx, 3FFh
0x18000fb8f  xor     edx, edx; Val
0x18000fb91  shl     rbx, 7
0x18000fb95  mov     r8d, 70h ; 'p'; Size
0x18000fb9b  mov     dword ptr [rbx+rax+8], 0FFFFFFFFh
0x18000fba3  mov     rcx, [rdi+20h]
0x18000fba7  mov     rax, [rdi+8]
0x18000fbab  mov     [rbx+rcx+10h], rax
0x18000fbb0  mov     rcx, [rdi+20h]
0x18000fbb4  add     rcx, 18h
0x18000fbb8  add     rcx, rbx; void *
0x18000fbbb  call    memset
0x18000fbc0  mov     rcx, [rdi+20h]
0x18000fbc4  xor     r8d, r8d; Flags
0x18000fbc7  add     rcx, 18h
0x18000fbcb  mov     edx, 0Eh; Count
0x18000fbd0  add     rcx, rbx; Callers
0x18000fbd3  call    cs:__imp_RtlWalkFrameChain
0x18000fbda  nop     dword ptr [rax+rax+00h]
0x18000fbdf  jmp     loc_18000FA94
0x18000fbe4  test    dword ptr [rdi], 2000000h
0x18000fbea  jnz     short loc_18000FB6D
0x18000fbec  jmp     loc_18000FA80
0x18000fbf1  mov     rdx, [rbx]; Entry
0x18000fbf4  test    rdx, rdx
0x18000fbf7  jz      loc_18000FA33
0x18000fbfd  lea     rcx, stru_18003F040; Lookaside
0x18000fc04  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000fc0b  nop     dword ptr [rax+rax+00h]
0x18000fc10  jmp     loc_18000FA33
0x18000fc15  test    dword ptr [rdi], 1000000h
0x18000fc1b  jz      loc_18000FA94
0x18000fc21  jmp     loc_18000FB6D
0x18000fc26  mov     rax, [rcx]
0x18000fc29  mov     rcx, [rax+8]; Object
0x18000fc2d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fc31  jz      loc_180025CB8
0x18000fc37  call    cs:__imp_ObfDereferenceObject
0x18000fc3e  nop     dword ptr [rax+rax+00h]
0x18000fc43  mov     rcx, [rbx]
0x18000fc46  mov     rcx, [rcx]; Handle
0x18000fc49  call    cs:__imp_ZwClose
0x18000fc50  nop     dword ptr [rax+rax+00h]
0x18000fc55  nop
0x18000fc56  jmp     loc_180025CB8
0x18000fc5b  mov     ecx, 1
0x18000fc60  call    FltpDequeueThrottledWorkItem
0x18000fc65  jmp     loc_18000FA9D
0x180025cb8  mov     eax, [rbx+48h]
0x180025cbb  test    al, 4
0x180025cbd  jz      loc_18000FA01
0x180025cc3  mov     rax, [rbx+10h]
0x180025cc7  xor     ecx, ecx
0x180025cc9  lock cmpxchg [rbx+10h], rcx
0x180025ccf  test    rax, rax
0x180025cd2  jz      loc_18000FA01
0x180025cd8  mov     rcx, rax
0x180025cdb  call    FltpObjectPointerDereference
0x180025ce0  nop
0x180025ce1  jmp     loc_18000FA01
```
