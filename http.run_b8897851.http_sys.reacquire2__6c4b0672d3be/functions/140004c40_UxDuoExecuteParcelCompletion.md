# UxDuoExecuteParcelCompletion

- ea: `0x140004c40`
- end: `0x1400053fc`
- name: `UxDuoExecuteParcelCompletion`
- size: `1980`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140003ac0`
- `0x140004c40`
- `0x140005410`
- `0x140005d10`
- `0x14000a350`
- `0x14003bf20`
- `0x140049d28`
- `0x140069330`
- `0x14006e50c`
- `0x140091ff0`
- `0x1400928e0`
- `0x140094f80`
- `0x140096e40`
- `0x1400d9280`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c4974`
- `0x1401ca800`
- `0x1401d9e44`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140004d3d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140004fe6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140004d3d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140004fe6`
- `ntoskrnl!IoFreeMdl` at `0x140004d93`
- `ntoskrnl!IoFreeMdl` at `0x140004d93`
- `ntoskrnl!IofCompleteRequest` at `0x14000539a`
- `ntoskrnl!IofCompleteRequest` at `0x14000539a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004dc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004de0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000537a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004dc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004de0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000537a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14016fdef`
- `ntoskrnl!KeReleaseSpinLock` at `0x14016fdef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14016fdbd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14016fdbd`

## pseudocode

```c
void __fastcall UxDuoExecuteParcelCompletion(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  int v3; // r10d
  __int64 v4; // r9
  __int64 v5; // r8
  int v6; // eax
  int v7; // ecx
  __int64 v8; // rdi
  _BYTE *v9; // rdi
  unsigned __int64 v10; // rsi
  ULONG_PTR v11; // rsi
  int v12; // eax
  struct _MDL *v13; // rcx
  struct _MDL *Next; // rdi
  __int64 v15; // rcx
  __int64 v16; // rcx
  ULONG_PTR v17; // rdx
  int v18; // eax
  volatile signed __int32 *v19; // rcx
  int v20; // ebp
  int v21; // ecx
  int v22; // ecx
  volatile signed __int32 *v23; // rcx
  int v24; // eax
  volatile signed __int32 *v25; // rdi
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rdx
  bool v29; // zf
  unsigned __int64 v30; // rsi
  __int64 v31; // rsi
  __int64 v32; // rax
  int v33; // ecx
  ULONG_PTR v34; // rcx
  void (__fastcall *v35)(_QWORD, __int64, __int64, __int64); // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rcx
  ULONG_PTR v39; // rdx
  int v40; // eax
  int v41; // eax
  IRP *v42; // rcx
  volatile signed __int32 *v43; // rcx
  KIRQL v44; // al
  __int64 v45; // r9
  KIRQL v46; // di
  _DWORD v47[24]; // [rsp+40h] [rbp-88h] BYREF

  v2 = *(_QWORD *)(a1 + 72);
  v3 = *(_DWORD *)(v2 + 16);
  v4 = *(_QWORD *)(v2 + 88);
  v5 = *(_QWORD *)(v2 + 80);
  *(_BYTE *)(v2 + 210) = 1;
  if ( v3 < 0 )
  {
    if ( v5 )
    {
      if ( (byte_1401A2C8B & 8) != 0 )
        WPP_SF_DDdD(a1, a2, v5, *(unsigned int *)(v4 + 17232), *(_DWORD *)(v5 + 88), v3, *(_DWORD *)(v2 + 176));
    }
    else if ( (byte_1401A2C8B & 8) != 0 )
    {
      WPP_SF_LLL(
        283,
        11,
        WPP_fc5e4f38a5b73b16c7731f2fb336856e_Traceguids,
        *(unsigned int *)(v4 + 17232),
        v3,
        *(_DWORD *)(v2 + 176));
    }
  }
  else if ( v5 )
  {
    if ( (BYTE11(xmmword_1401A2CA0) & 8) != 0 )
      WPP_SF_LLL(
        1307,
        12,
        WPP_fc5e4f38a5b73b16c7731f2fb336856e_Traceguids,
        *(unsigned int *)(v4 + 17232),
        *(_DWORD *)(v5 + 88),
        *(_DWORD *)(v2 + 176));
  }
  else if ( (BYTE11(xmmword_1401A2CA0) & 8) != 0 )
  {
    WPP_SF_Dd(
      1307,
      13,
      WPP_fc5e4f38a5b73b16c7731f2fb336856e_Traceguids,
      *(unsigned int *)(v4 + 17232),
      *(_DWORD *)(v2 + 176));
  }
  v6 = *(_DWORD *)(v2 + 232);
  if ( v6 )
  {
    if ( v6 == 2 )
    {
      UxDuoStreamEndComplete(v2, a2, v5, v4);
    }
    else if ( v6 == 10 )
    {
      UxDuoStreamEndComplete(v2, a2, v5, v4);
      UxDuoUpdateJobStatus(*(_QWORD *)(v2 + 264), *(unsigned int *)(v2 + 16));
    }
  }
  else
  {
    if ( *(_BYTE *)(v2 + 304) )
    {
      v31 = *(_QWORD *)(v2 + 80);
      if ( !*(_BYTE *)(v31 + 96) )
      {
        v29 = *(_BYTE *)(v31 + 399) == 0;
        *(_BYTE *)(v31 + 401) = 1;
        if ( v29 )
        {
          if ( (BYTE11(xmmword_1401A2CA0) & 8) != 0 )
            WPP_SF_Dd(
              1307,
              16,
              WPP_309922b680ce3405e88e422e035050e4_Traceguids,
              *(unsigned int *)(*(_QWORD *)(v31 + 48) + 17232LL),
              *(_DWORD *)(v31 + 88));
          v44 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(v31 + 48) + 16936LL));
          LOBYTE(v45) = 1;
          v46 = v44;
          UlSetBundleTimerEx(v31 + 104, 16, 0, v45);
          KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v31 + 48) + 16936LL), v46);
        }
        UxDuoRunStreamReceivePump(v31, a2, v5, v4);
      }
    }
    v32 = *(_QWORD *)(v2 + 264);
    if ( *(int *)(v32 + 32) >= 0 )
    {
      v33 = *(_DWORD *)(v2 + 16);
      if ( v33 < 0 )
        *(_DWORD *)(v32 + 32) = v33;
    }
  }
  v7 = *(_DWORD *)(v2 + 232);
  if ( v7 )
  {
    v21 = v7 - 1;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        if ( v22 == 8 )
        {
          v5 = *(_QWORD *)(v2 + 248);
          if ( v5 )
          {
            UxpFreeHeaderBufferBlock(26, 1112045653);
            *(_QWORD *)(v2 + 248) = 0;
          }
          v23 = *(volatile signed __int32 **)(v2 + 264);
          if ( v23 )
          {
            v24 = _InterlockedDecrement(v23);
            if ( UxDebugCheckRefcount && v24 <= -1 )
              UlBugCheckEx(3u, (ULONG_PTR)v23, 0x17u, v24);
            if ( !v24 )
              UxDuoFreeJob((PVOID)v23);
            goto LABEL_28;
          }
        }
      }
      else
      {
        v34 = *(_QWORD *)(v2 + 240);
        if ( v34 )
        {
          UxDuoDereferenceJob(v34, 0x19u);
          *(_QWORD *)(v2 + 240) = 0;
        }
      }
    }
    else
    {
      if ( *(_QWORD *)(v2 + 264) )
      {
        UxpFreeHeaderBufferBlock(26, 1112045653);
        *(_QWORD *)(v2 + 264) = 0;
      }
      v5 = *(_QWORD *)(v2 + 240);
      if ( v5 )
      {
        UxpFreeHeaderBufferBlock(27, 1346926677);
        *(_QWORD *)(v2 + 240) = 0;
      }
    }
  }
  else
  {
    v8 = *(_QWORD *)(v2 + 248);
    if ( v8 )
    {
      v9 = (_BYTE *)(v8 - 21);
      *((_DWORD *)v9 + 4) = 1651005557;
      if ( v9[20] )
      {
        if ( UxDebugDisableLookaside )
        {
          memset(v47, 0, sizeof(v47));
          v47[10] = dword_1401A0598;
          ((void (__fastcall *)(_BYTE *, _DWORD *))off_1401A05A8)(v9, v47);
        }
        else if ( UxCompactMode )
        {
          PnlFreeToLookasideList(qword_1401A0580, v9);
        }
        else
        {
          v10 = qword_1401A0580 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v9 + 1) << 7);
          if ( !*(_BYTE *)(v10 + 176) )
            PplpLazyInitializeLookasideList(qword_1401A0580, v10 + 64);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v10 + 64), v9);
        }
      }
      else
      {
        ExFreePoolWithTag(v9, 0);
      }
      *(_QWORD *)(v2 + 248) = 0;
    }
    v11 = *(_QWORD *)(v2 + 264);
    if ( v11 )
    {
      v12 = _InterlockedDecrement((volatile signed __int32 *)v11);
      if ( UxDebugCheckRefcount && v12 <= -1 )
        UlBugCheckEx(3u, v11, 0x24u, v12);
      if ( !v12 )
      {
        v13 = *(struct _MDL **)(v11 + 48);
        if ( v13 )
        {
          do
          {
            Next = v13->Next;
            IoFreeMdl(v13);
            v13 = Next;
          }
          while ( Next );
        }
        *(_QWORD *)(v11 + 48) = 0;
        *(_QWORD *)(v11 + 56) = 0;
        while ( 1 )
        {
          v15 = *(_QWORD *)(v11 + 72);
          if ( !v15 )
            break;
          *(_QWORD *)(v11 + 72) = *(_QWORD *)v15;
          ExFreePoolWithTag(*(PVOID *)(v15 + 8), 0);
        }
        v35 = *(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(v11 + 16);
        if ( v35 )
        {
          v36 = *(unsigned int *)(v11 + 32);
          if ( (int)v36 < 0 )
            v37 = 0;
          else
            v37 = *(_QWORD *)(v11 + 40);
          v35(*(_QWORD *)(v11 + 24), v36, v37, v4);
        }
        v38 = *(_QWORD *)(v11 + 8);
        if ( v38 )
        {
          v39 = v38 + 20;
          v40 = _InterlockedDecrement((volatile signed __int32 *)(v38 + 20));
          if ( UxDebugCheckRefcount && v40 <= -1 )
            UlBugCheckEx(3u, v39, 0x2Bu, v40);
          if ( !v40 )
            UxDuoFreeStream(v38, v39, v5, v4);
          *(_QWORD *)(v11 + 8) = 0;
        }
        ExFreePoolWithTag((PVOID)v11, 0);
      }
LABEL_28:
      *(_QWORD *)(v2 + 264) = 0;
    }
  }
  switch ( *(_DWORD *)(v2 + 96) )
  {
    case 9:
      v25 = *(volatile signed __int32 **)(v2 + 104);
      if ( !v25 )
        break;
      v26 = *(_QWORD *)(v2 + 88);
      v27 = _InterlockedDecrement(v25 + 5);
      if ( UxDebugCheckRefcount && v27 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v25 + 5), 1u, v27);
      if ( v27 )
        goto LABEL_64;
      v28 = *((_QWORD *)v25 + 3);
      if ( v28 )
      {
        (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(*(_QWORD *)(v26 + 16) + 128LL))(
          *(_QWORD *)(v26 + 8),
          v28,
          v5,
          v4);
        *((_QWORD *)v25 + 3) = 0;
      }
      v29 = UxDebugDisableLookaside == 0;
      *((_DWORD *)v25 + 4) = 2021218421;
      if ( !v29 )
      {
        memset(v47, 0, sizeof(v47));
        v47[10] = dword_1401A07D8;
        ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A07E8)(v25, v47);
        goto LABEL_64;
      }
      if ( !UxCompactMode )
      {
        v30 = qword_1401A07C0 + ((unsigned __int64)(unsigned int)(*v25 + 1) << 7);
        if ( !*(_BYTE *)(v30 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A07C0, v30 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v30 + 64), (PVOID)v25);
        goto LABEL_64;
      }
      PnlFreeToLookasideList(qword_1401A07C0, v25);
      *(_QWORD *)(v2 + 104) = 0;
      break;
    case 0xA:
      v43 = *(volatile signed __int32 **)(v2 + 104);
      if ( v43 )
      {
        v41 = _InterlockedDecrement(v43);
        if ( UxDebugCheckRefcount && v41 <= -1 )
          UlBugCheckEx(3u, (ULONG_PTR)v43, 0x3Au, v41);
        if ( !v41 )
          UxDuoFreeDeclarePushParameters((PVOID)v43);
        *(_QWORD *)(v2 + 112) = 0;
        *(_QWORD *)(v2 + 104) = 0;
      }
      break;
    case 0x11:
      v42 = *(IRP **)(v2 + 104);
      if ( v42 )
      {
        IofCompleteRequest(v42, 0);
LABEL_64:
        *(_QWORD *)(v2 + 104) = 0;
      }
      break;
  }
  v16 = *(_QWORD *)(v2 + 80);
  if ( v16 )
  {
    v17 = v16 + 20;
    v18 = _InterlockedDecrement((volatile signed __int32 *)(v16 + 20));
    if ( UxDebugCheckRefcount && v18 <= -1 )
      UlBugCheckEx(3u, v17, 0x2Cu, v18);
    if ( !v18 )
      UxDuoFreeStream(v16, v17, v5, v4);
    *(_QWORD *)(v2 + 80) = 0;
  }
  v19 = *(volatile signed __int32 **)(v2 + 88);
  if ( v19 )
  {
    v20 = _InterlockedDecrement(v19 + 1);
    if ( UxDebugCheckRefcount && v20 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v19 + 1), 0x2Cu, v20);
    if ( !v20 )
      UxDuoFreeConnection((PVOID)v19);
    *(_QWORD *)(v2 + 88) = 0;
  }
  ExFreePoolWithTag((PVOID)v2, 0);
}

```

## disassembly

```asm
0x140004c40  push    rbx
0x140004c42  push    rbp
0x140004c43  push    r14
0x140004c45  sub     rsp, 0B0h
0x140004c4c  mov     rax, cs:__security_cookie
0x140004c53  xor     rax, rsp
0x140004c56  mov     [rsp+0C8h+var_28], rax
0x140004c5e  mov     rbx, [rcx+48h]
0x140004c62  mov     r10d, [rbx+10h]
0x140004c66  mov     r9, [rbx+58h]
0x140004c6a  mov     r8, [rbx+50h]
0x140004c6e  mov     byte ptr [rbx+0D2h], 1
0x140004c75  test    r10d, r10d
0x140004c78  js      loc_1400050F0
0x140004c7e  test    r8, r8
0x140004c81  jnz     loc_140004EAB
0x140004c87  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 8
0x140004c8e  jnz     loc_14000526A
0x140004c94  mov     eax, [rbx+0E8h]
0x140004c9a  mov     [rsp+0C8h+arg_8], rsi
0x140004ca2  mov     [rsp+0C8h+arg_10], rdi
0x140004caa  test    eax, eax
0x140004cac  jz      loc_140004FFB
0x140004cb2  cmp     eax, 2
0x140004cb5  jz      loc_1400052B2
0x140004cbb  cmp     eax, 0Ah
0x140004cbe  jz      loc_140005296
0x140004cc4  mov     ecx, [rbx+0E8h]
0x140004cca  xor     r14d, r14d
0x140004ccd  mov     ebp, 0FFFFFFFFh
0x140004cd2  test    ecx, ecx
0x140004cd4  jnz     loc_140004EEC
0x140004cda  mov     rdi, [rbx+0F8h]
0x140004ce1  test    rdi, rdi
0x140004ce4  jz      short loc_140004D50
0x140004ce6  add     rdi, 0FFFFFFFFFFFFFFEBh
0x140004cea  mov     dword ptr [rdi+10h], 62685875h
0x140004cf1  cmp     [rdi+14h], r14b
0x140004cf5  jz      loc_140005375
0x140004cfb  cmp     cs:UxDebugDisableLookaside, r14b
0x140004d02  jnz     loc_140005340
0x140004d08  cmp     cs:UxCompactMode, r14b
0x140004d0f  mov     rcx, cs:qword_1401A0580
0x140004d16  jnz     loc_1400050C7
0x140004d1c  mov     esi, [rdi]
0x140004d1e  inc     esi
0x140004d20  shl     rsi, 7
0x140004d24  add     rsi, rcx
0x140004d27  movzx   eax, byte ptr [rsi+0B0h]
0x140004d2e  test    al, al
0x140004d30  jz      loc_14000519F
0x140004d36  mov     rdx, rdi; Entry
0x140004d39  lea     rcx, [rsi+40h]; Lookaside
0x140004d3d  call    cs:__imp_ExFreeToLookasideListEx
0x140004d44  nop     dword ptr [rax+rax+00h]
0x140004d49  mov     [rbx+0F8h], r14
0x140004d50  mov     rsi, [rbx+108h]
0x140004d57  test    rsi, rsi
0x140004d5a  jz      loc_140004DF3
0x140004d60  mov     eax, ebp
0x140004d62  lock xadd [rsi], eax
0x140004d66  dec     eax
0x140004d68  cmp     cs:UxDebugCheckRefcount, r14b
0x140004d6f  jnz     loc_140005050
0x140004d75  test    eax, eax
0x140004d77  jnz     short loc_140004DEC
0x140004d79  mov     rcx, [rsi+30h]; Mdl
0x140004d7d  test    rcx, rcx
0x140004d80  jz      short loc_140004DA7
0x140004d82  nop     dword ptr [rax+00h]
0x140004d86  nop     word ptr [rax+rax+00000000h]
0x140004d90  mov     rdi, [rcx]
0x140004d93  call    cs:__imp_IoFreeMdl
0x140004d9a  nop     dword ptr [rax+rax+00h]
0x140004d9f  mov     rcx, rdi
0x140004da2  test    rdi, rdi
0x140004da5  jnz     short loc_140004D90
0x140004da7  mov     [rsi+30h], r14
0x140004dab  mov     [rsi+38h], r14
0x140004daf  mov     rcx, [rsi+48h]
0x140004db3  test    rcx, rcx
0x140004db6  jz      loc_1400051BB
0x140004dbc  mov     rax, [rcx]
0x140004dbf  xor     edx, edx; Tag
0x140004dc1  mov     [rsi+48h], rax
0x140004dc5  mov     rcx, [rcx+8]; P
0x140004dc9  call    cs:__imp_ExFreePoolWithTag
0x140004dd0  nop     dword ptr [rax+rax+00h]
0x140004dd5  jmp     short loc_140004DAF
0x140004dd7  mov     [rsi+8], r14
0x140004ddb  xor     edx, edx; Tag
0x140004ddd  mov     rcx, rsi; P
0x140004de0  call    cs:__imp_ExFreePoolWithTag
0x140004de7  nop     dword ptr [rax+rax+00h]
0x140004dec  mov     [rbx+108h], r14
0x140004df3  mov     ecx, [rbx+60h]
0x140004df6  sub     ecx, 9
0x140004df9  jz      loc_140004F4E
0x140004dff  sub     ecx, 1
0x140004e02  jz      loc_1400053AB
0x140004e08  cmp     ecx, 7
0x140004e0b  jz      loc_14000538B
0x140004e11  mov     rcx, [rbx+50h]
0x140004e15  test    rcx, rcx
0x140004e18  jz      short loc_140004E40
0x140004e1a  lea     rdx, [rcx+14h]; BugCheckParameter2
0x140004e1e  mov     eax, ebp
0x140004e20  lock xadd [rdx], eax
0x140004e24  dec     eax
0x140004e26  cmp     cs:UxDebugCheckRefcount, r14b
0x140004e2d  jnz     loc_14000508C
0x140004e33  test    eax, eax
0x140004e35  jnz     short loc_140004E3C
0x140004e37  call    UxDuoFreeStream
0x140004e3c  mov     [rbx+50h], r14
0x140004e40  mov     rcx, [rbx+58h]; P
0x140004e44  test    rcx, rcx
0x140004e47  jz      short loc_140004E6D
0x140004e49  lea     rdx, [rcx+4]; BugCheckParameter2
0x140004e4d  lock xadd [rdx], ebp
0x140004e51  dec     ebp
0x140004e53  cmp     cs:UxDebugCheckRefcount, r14b
0x140004e5a  jnz     loc_14000506F
0x140004e60  test    ebp, ebp
0x140004e62  jnz     short loc_140004E69
0x140004e64  call    UxDuoFreeConnection
0x140004e69  mov     [rbx+58h], r14
0x140004e6d  xor     edx, edx; Tag
0x140004e6f  mov     rcx, rbx; P
0x140004e72  call    cs:__imp_ExFreePoolWithTag
0x140004e79  nop     dword ptr [rax+rax+00h]
0x140004e7e  mov     rdi, [rsp+0C8h+arg_10]
0x140004e86  mov     rsi, [rsp+0C8h+arg_8]
0x140004e8e  mov     rcx, [rsp+0C8h+var_28]
0x140004e96  xor     rcx, rsp; StackCookie
0x140004e99  call    __security_check_cookie
0x140004e9e  add     rsp, 0B0h
0x140004ea5  pop     r14
0x140004ea7  pop     rbp
0x140004ea8  pop     rbx
0x140004ea9  retn
0x140004eab  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 8
0x140004eb2  jz      loc_140004C94
0x140004eb8  mov     eax, [rbx+0B0h]
0x140004ebe  mov     edx, 0Ch
0x140004ec3  mov     r9d, [r9+4350h]
0x140004eca  mov     ecx, 51Bh
0x140004ecf  mov     [rsp+0C8h+var_A0], eax
0x140004ed3  mov     eax, [r8+58h]
0x140004ed7  lea     r8, WPP_fc5e4f38a5b73b16c7731f2fb336856e_Traceguids
0x140004ede  mov     [rsp+0C8h+var_A8], eax
0x140004ee2  call    WPP_SF_LLL
0x140004ee7  jmp     loc_140004C94
0x140004eec  sub     ecx, 1
0x140004eef  jz      loc_140005315
0x140004ef5  sub     ecx, 1
0x140004ef8  jz      loc_140005179
0x140004efe  cmp     ecx, 8
0x140004f01  jnz     loc_140004DF3
0x140004f07  mov     r8, [rbx+0F8h]
0x140004f0e  test    r8, r8
0x140004f11  jnz     loc_1400052FA
0x140004f17  mov     rcx, [rbx+108h]; P
0x140004f1e  test    rcx, rcx
0x140004f21  jz      loc_140004DF3
0x140004f27  mov     eax, ebp
0x140004f29  lock xadd [rcx], eax
0x140004f2d  dec     eax
0x140004f2f  cmp     cs:UxDebugCheckRefcount, r14b
0x140004f36  jnz     loc_1400050A8
0x140004f3c  test    eax, eax
0x140004f3e  jnz     loc_140004DEC
0x140004f44  call    UxDuoFreeJob
0x140004f49  jmp     loc_140004DEC
0x140004f4e  mov     rdi, [rbx+68h]
0x140004f52  test    rdi, rdi
0x140004f55  jz      loc_140004E11
0x140004f5b  mov     rcx, [rbx+58h]
0x140004f5f  lea     rdx, [rdi+14h]; BugCheckParameter2
0x140004f63  mov     eax, ebp
0x140004f65  lock xadd [rdx], eax
0x140004f69  dec     eax
0x140004f6b  cmp     cs:UxDebugCheckRefcount, r14b
0x140004f72  jnz     loc_1400050D4
0x140004f78  test    eax, eax
0x140004f7a  jnz     short loc_140004FF2
0x140004f7c  mov     rdx, [rdi+18h]
0x140004f80  test    rdx, rdx
0x140004f83  jz      short loc_140004F9D
0x140004f85  mov     rax, [rcx+10h]
0x140004f89  mov     rcx, [rcx+8]
0x140004f8d  mov     rax, [rax+80h]
0x140004f94  call    _guard_dispatch_icall
0x140004f99  mov     [rdi+18h], r14
0x140004f9d  cmp     cs:UxDebugDisableLookaside, r14b
0x140004fa4  mov     dword ptr [rdi+10h], 78795875h
0x140004fab  jnz     loc_1400053C7
0x140004fb1  cmp     cs:UxCompactMode, r14b
0x140004fb8  mov     rcx, cs:qword_1401A07C0
0x140004fbf  jnz     loc_14000512A
0x140004fc5  mov     esi, [rdi]
0x140004fc7  inc     esi
0x140004fc9  shl     rsi, 7
0x140004fcd  add     rsi, rcx
0x140004fd0  movzx   eax, byte ptr [rsi+0B0h]
0x140004fd7  test    al, al
0x140004fd9  jz      loc_1400051AD
0x140004fdf  mov     rdx, rdi; Entry
0x140004fe2  lea     rcx, [rsi+40h]; Lookaside
0x140004fe6  call    cs:__imp_ExFreeToLookasideListEx
0x140004fed  nop     dword ptr [rax+rax+00h]
0x140004ff2  mov     [rbx+68h], r14
0x140004ff6  jmp     loc_140004E11
0x140004ffb  cmp     byte ptr [rbx+130h], 0
0x140005002  jz      short loc_14000500E
0x140005004  mov     rsi, [rbx+50h]
0x140005008  cmp     byte ptr [rsi+60h], 0
0x14000500c  jz      short loc_140005032
0x14000500e  mov     rax, [rbx+108h]
0x140005015  cmp     dword ptr [rax+20h], 0
0x140005019  jl      loc_140004CC4
0x14000501f  mov     ecx, [rbx+10h]
0x140005022  test    ecx, ecx
0x140005024  jns     loc_140004CC4
0x14000502a  mov     [rax+20h], ecx
0x14000502d  jmp     loc_140004CC4
0x140005032  cmp     byte ptr [rsi+18Fh], 0
0x140005039  mov     byte ptr [rsi+191h], 1
0x140005040  jz      loc_1400052BF
0x140005046  mov     rcx, rsi
0x140005049  call    UxDuoRunStreamReceivePump
0x14000504e  jmp     short loc_14000500E
0x140005050  cmp     eax, ebp
0x140005052  jg      loc_140004D75
0x140005058  movsxd  r9, eax; BugCheckParameter4
0x14000505b  mov     r8d, 24h ; '$'; BugCheckParameter3
0x140005061  mov     rdx, rsi; BugCheckParameter2
0x140005064  mov     ecx, 3; BugCheckParameter1
0x140005069  call    UlBugCheckEx
0x14000506f  cmp     ebp, 0FFFFFFFFh
0x140005072  jg      loc_140004E60
0x140005078  movsxd  r9, ebp; BugCheckParameter4
0x14000507b  mov     ecx, 3; BugCheckParameter1
0x140005080  mov     r8d, 2Ch ; ','; BugCheckParameter3
0x140005086  call    UlBugCheckEx
0x14000508c  cmp     eax, ebp
0x14000508e  jg      loc_140004E33
0x140005094  movsxd  r9, eax; BugCheckParameter4
0x140005097  mov     ecx, 3; BugCheckParameter1
0x14000509c  mov     r8d, 2Ch ; ','; BugCheckParameter3
0x1400050a2  call    UlBugCheckEx
0x1400050a8  cmp     eax, ebp
0x1400050aa  jg      loc_140004F3C
0x1400050b0  mov     rdx, rcx; BugCheckParameter2
0x1400050b3  movsxd  r9, eax; BugCheckParameter4
0x1400050b6  mov     ecx, 3; BugCheckParameter1
0x1400050bb  mov     r8d, 17h; BugCheckParameter3
0x1400050c1  call    UlBugCheckEx
0x1400050c7  mov     rdx, rdi
0x1400050ca  call    PnlFreeToLookasideList
0x1400050cf  jmp     loc_140004D49
0x1400050d4  cmp     eax, ebp
0x1400050d6  jg      loc_140004F78
0x1400050dc  movsxd  r9, eax; BugCheckParameter4
0x1400050df  mov     ecx, 3; BugCheckParameter1
0x1400050e4  mov     r8d, 1; BugCheckParameter3
0x1400050ea  call    UlBugCheckEx
0x1400050f0  test    r8, r8
0x1400050f3  jz      short loc_14000513B
0x1400050f5  test    cs:byte_1401A2C8B, 8
0x1400050fc  jz      loc_140004C94
0x140005102  mov     eax, [rbx+0B0h]
0x140005108  mov     r9d, [r9+4350h]
0x14000510f  mov     [rsp+0C8h+var_98], eax
0x140005113  mov     eax, [r8+58h]
0x140005117  mov     [rsp+0C8h+var_A0], r10d
0x14000511c  mov     [rsp+0C8h+var_A8], eax
0x140005120  call    WPP_SF_DDdD
0x140005125  jmp     loc_140004C94
0x14000512a  mov     rdx, rdi
0x14000512d  call    PnlFreeToLookasideList
0x140005132  mov     [rbx+68h], r14
0x140005136  jmp     loc_140004E11
0x14000513b  test    cs:byte_1401A2C8B, 8
0x140005142  jz      loc_140004C94
0x140005148  mov     eax, [rbx+0B0h]
0x14000514e  lea     r8, WPP_fc5e4f38a5b73b16c7731f2fb336856e_Traceguids
0x140005155  mov     r9d, [r9+4350h]
0x14000515c  mov     edx, 0Bh
0x140005161  mov     [rsp+0C8h+var_A0], eax
0x140005165  mov     ecx, 11Bh
0x14000516a  mov     [rsp+0C8h+var_A8], r10d
0x14000516f  call    WPP_SF_LLL
0x140005174  jmp     loc_140004C94
0x140005179  mov     rcx, [rbx+0F0h]; BugCheckParameter2
0x140005180  test    rcx, rcx
0x140005183  jz      loc_140004DF3
0x140005189  mov     edx, 19h; BugCheckParameter3
0x14000518e  call    UxDuoDereferenceJob
0x140005193  mov     [rbx+0F0h], r14
  ... truncated ...
```
