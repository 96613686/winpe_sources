# FatOpenVolume

- ea: `0x14002c234`
- end: `0x14002c58f`
- name: `FatOpenVolume`
- size: `859`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400268c0`

## callees

- `0x140002b30`
- `0x140006dbc`
- `0x1400202a0`
- `0x14002c234`
- `0x14003dae0`
- `0x14003db44`
- `0x14003e4b4`
- `0x14003e94c`
- `0x1400475e8`
- `0x14004814c`
- `0x140048e2c`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14002c3bb`
- `ntoskrnl!KeCancelTimer` at `0x14002c3bb`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14002c3ce`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14002c3ce`
- `ntoskrnl!IoRemoveShareAccess` at `0x14002c55f`
- `ntoskrnl!IoRemoveShareAccess` at `0x14005cabe`
- `ntoskrnl!IoRemoveShareAccess` at `0x14002c55f`
- `ntoskrnl!IoRemoveShareAccess` at `0x14005cabe`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x14002c2c2`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x14002c2c2`
- `ntoskrnl!CcIsThereDirtyData` at `0x14002c3a4`
- `ntoskrnl!CcIsThereDirtyData` at `0x14002c3a4`
- `ntoskrnl!IoCheckShareAccess` at `0x14002c449`
- `ntoskrnl!IoCheckShareAccess` at `0x14002c449`
- `ntoskrnl!IoSetShareAccess` at `0x14002c462`
- `ntoskrnl!IoSetShareAccess` at `0x14002c462`

## pseudocode

```c
_QWORD *__fastcall FatOpenVolume(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        ACCESS_MASK *a5,
        unsigned __int16 a6,
        int a7)
{
  struct _FILE_OBJECT *v8; // r14
  __int64 v9; // r9
  bool v11; // r15
  char v12; // di
  __int64 Ccb; // r13
  char v14; // r12
  NTSTATUS v15; // eax
  ACCESS_MASK v16; // eax
  unsigned __int16 v17; // r12
  int v18; // eax
  __int64 v20; // r15
  __int64 v21; // rcx
  struct _SHARE_ACCESS *v22; // r9
  ACCESS_MASK v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 v28; // r8
  char v30; // [rsp+30h] [rbp-48h]
  char v31; // [rsp+32h] [rbp-46h]
  __int64 v32[8]; // [rsp+38h] [rbp-40h] BYREF

  v8 = (struct _FILE_OBJECT *)a3;
  v9 = a2;
  *a1 = 0;
  a1[1] = 0;
  v11 = 0;
  v12 = 0;
  v30 = 0;
  Ccb = 0;
  v32[0] = 0;
  v14 = 0;
  v31 = 0;
  if ( ((a7 - 1) & 0xFFFFFFFD) != 0 )
  {
    v15 = -1073741790;
    *(_DWORD *)a1 = -1073741790;
    goto LABEL_39;
  }
  v16 = *a5;
  v17 = a6;
  if ( (a6 & 6) != 0 )
  {
    if ( (v16 & 7) != 0 )
      v11 = (int)FatFlushVolume(a2, a4, 1) >= 0;
    if ( !v11 )
      goto LABEL_25;
    goto LABEL_19;
  }
  if ( (v16 & 6) != 0 && FsRtlAreVolumeStartupApplicationsComplete() )
    v17 = a6 & 0xFFFE;
  if ( (v17 & 1) != 0 || (unsigned __int8)FatIsHandleCountZero(a1, a4, a3, v9) )
  {
    FatFlushFat(a2, a4);
    FatPurgeReferencedFileObjects(a2, *(_QWORD *)(a4 + 208), 1);
    v18 = *(_DWORD *)(a4 + 272);
    if ( (v17 & 1) != 0 ? *(_DWORD *)(a4 + 276) == v18 : v18 == 0 )
    {
      _InterlockedOr((volatile signed __int32 *)(a4 + 200), 1u);
      *(_QWORD *)(a4 + 792) = v8;
      v31 = 1;
LABEL_19:
      if ( (*(_DWORD *)(a4 + 200) & 4) != 0
        && (*(_DWORD *)(a4 + 200) & 0x10) == 0
        && !CcIsThereDirtyData(*(PVPB *)(a4 + 192)) )
      {
        KeCancelTimer((PKTIMER)(a4 + 952));
        KeRemoveQueueDpc((PRKDPC)(a4 + 888));
        v20 = a2;
        FatMarkVolume(a2, a4, 0);
        _InterlockedAnd((volatile signed __int32 *)(a4 + 200), 0xFFFFFFFB);
        if ( (*(_DWORD *)(a4 + 200) & 2) != 0 && (*(_DWORD *)(a4 + 200) & 0x800) == 0 )
          FatToggleMediaEjectDisable(v21, a4, 0);
LABEL_26:
        v22 = (struct _SHARE_ACCESS *)(a4 + 244);
        v23 = *a5;
        if ( *(_DWORD *)(a4 + 240) )
        {
          v15 = IoCheckShareAccess(v23, v17, v8, v22, 1u);
          *(_DWORD *)a1 = v15;
          v24 = 0;
          if ( v15 < 0 )
            goto LABEL_10;
        }
        else
        {
          IoSetShareAccess(v23, v17, v8, v22);
        }
        v30 = 1;
        Ccb = FatCreateCcb(a1, v24);
        v32[0] = Ccb;
        FatSetFileObject(v8, v25, a4, Ccb);
        v8->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)(a4 + 736);
        ++*(_DWORD *)(a4 + 240);
        ++*(_DWORD *)(a4 + 272);
        LOBYTE(v26) = v8->WriteAccess | v8->DeleteAccess;
        if ( !*(_WORD *)&v8->WriteAccess )
          ++*(_DWORD *)(a4 + 276);
        v14 = 1;
        v8->Flags |= 8u;
        v27 = *(_QWORD *)(v20 + 40);
        v28 = *(_QWORD *)(v27 + 184);
        if ( (*(_BYTE *)(v28 + 2) & 1) != 0 )
          LOBYTE(v27) = 1;
        else
          LOBYTE(v27) = *(_BYTE *)(v27 + 64);
        if ( (int)FatExplicitDeviceAccessGranted(
                    v26,
                    *(_QWORD *)(*(_QWORD *)(a4 + 192) + 16LL),
                    *(_QWORD *)(*(_QWORD *)(v28 + 8) + 8LL),
                    v27) >= 0 )
          *(_DWORD *)(Ccb + 4) |= 0x20000u;
        *(_DWORD *)a1 = 0;
        a1[1] = 1;
        v15 = 0;
        goto LABEL_38;
      }
LABEL_25:
      v20 = a2;
      goto LABEL_26;
    }
  }
  v15 = -1073741757;
  *(_DWORD *)a1 = -1073741757;
LABEL_10:
  v14 = 0;
LABEL_38:
  v12 = v30;
LABEL_39:
  if ( v15 < 0 )
  {
    if ( v14 )
    {
      a3 = 0xFFFFFFFFLL;
      --*(_DWORD *)(a4 + 240);
      --*(_DWORD *)(a4 + 272);
      if ( !*(_WORD *)&v8->WriteAccess )
        --*(_DWORD *)(a4 + 276);
    }
    if ( Ccb )
      FatDeleteCcb(a1, v32, a3, v9);
    if ( v12 )
      IoRemoveShareAccess(v8, (PSHARE_ACCESS)(a4 + 244));
    if ( v31 )
      _InterlockedAnd((volatile signed __int32 *)(a4 + 200), 0xFFFFFFFE);
  }
  return a1;
}

```

## disassembly

```asm
0x14002c234  mov     rax, rsp
0x14002c237  mov     [rax+20h], r9
0x14002c23b  mov     [rax+18h], r8
0x14002c23f  mov     [rax+10h], rdx
0x14002c243  mov     [rax+8], rcx
0x14002c247  push    rbx
0x14002c248  push    rsi
0x14002c249  push    rdi
0x14002c24a  push    r12
0x14002c24c  push    r13
0x14002c24e  push    r14
0x14002c250  push    r15
0x14002c252  sub     rsp, 40h
0x14002c256  mov     rbx, r9
0x14002c259  mov     r14, r8
0x14002c25c  mov     r9, rdx
0x14002c25f  mov     rsi, rcx
0x14002c262  xor     edx, edx
0x14002c264  mov     [rcx], rdx
0x14002c267  mov     [rcx+8], rdx
0x14002c26b  movzx   r15d, dl
0x14002c26f  mov     dil, dl
0x14002c272  mov     [rax-48h], dl
0x14002c275  mov     r13d, edx
0x14002c278  mov     [rax-40h], rdx
0x14002c27c  mov     r12b, dl
0x14002c27f  mov     [rax-47h], dl
0x14002c282  mov     [rax-46h], dl
0x14002c285  mov     eax, [rsp+78h+arg_30]
0x14002c28c  dec     eax
0x14002c28e  test    eax, 0FFFFFFFDh
0x14002c293  jz      short loc_14002C2A1
0x14002c295  mov     eax, 0C0000022h
0x14002c29a  mov     [rcx], eax
0x14002c29c  jmp     loc_14002C513
0x14002c2a1  mov     rax, [rsp+78h+arg_20]
0x14002c2a9  mov     eax, [rax]
0x14002c2ab  movzx   r12d, [rsp+78h+arg_28]
0x14002c2b4  test    r12b, 6
0x14002c2b8  jnz     loc_14002C35F
0x14002c2be  test    al, 6
0x14002c2c0  jz      short loc_14002C2DB
0x14002c2c2  call    cs:__imp_FsRtlAreVolumeStartupApplicationsComplete
0x14002c2c9  nop     dword ptr [rax+rax+00h]
0x14002c2ce  test    al, al
0x14002c2d0  jz      short loc_14002C2DB
0x14002c2d2  mov     eax, 0FFFEh
0x14002c2d7  and     r12w, ax
0x14002c2db  movzx   r15d, r12w
0x14002c2df  mov     edi, 1
0x14002c2e4  and     r15w, di
0x14002c2e8  jnz     short loc_14002C309
0x14002c2ea  mov     rdx, rbx
0x14002c2ed  call    FatIsHandleCountZero
0x14002c2f2  xor     edx, edx
0x14002c2f4  test    al, al
0x14002c2f6  jnz     short loc_14002C309
0x14002c2f8  mov     eax, 0C0000043h
0x14002c2fd  mov     [rsi], eax
0x14002c2ff  mov     r12b, [rsp+78h+var_47]
0x14002c304  jmp     loc_14002C50E
0x14002c309  mov     rdx, rbx
0x14002c30c  mov     rcx, [rsp+78h+arg_8]
0x14002c314  call    FatFlushFat
0x14002c319  mov     r8d, edi
0x14002c31c  mov     rdx, [rbx+0D0h]
0x14002c323  mov     rcx, [rsp+78h+arg_8]
0x14002c32b  call    FatPurgeReferencedFileObjects
0x14002c330  mov     eax, [rbx+110h]
0x14002c336  xor     edx, edx
0x14002c338  test    r15w, r15w
0x14002c33c  jnz     short loc_14002C357
0x14002c33e  test    eax, eax
0x14002c340  jnz     short loc_14002C2F8
0x14002c342  lock or [rbx+0C8h], edi
0x14002c349  mov     [rbx+318h], r14
0x14002c350  mov     [rsp+78h+var_46], dil
0x14002c355  jmp     short loc_14002C385
0x14002c357  cmp     [rbx+114h], eax
0x14002c35d  jmp     short loc_14002C340
0x14002c35f  mov     edi, 1
0x14002c364  test    al, 7
0x14002c366  jz      short loc_14002C37C
0x14002c368  mov     r8d, edi
0x14002c36b  mov     rdx, rbx
0x14002c36e  mov     rcx, r9
0x14002c371  call    FatFlushVolume
0x14002c376  test    eax, eax
0x14002c378  cmovns  r15d, edi
0x14002c37c  test    r15b, r15b
0x14002c37f  jz      loc_14002C41B
0x14002c385  mov     eax, [rbx+0C8h]
0x14002c38b  test    al, 4
0x14002c38d  jz      loc_14002C41B
0x14002c393  mov     eax, [rbx+0C8h]
0x14002c399  test    al, 10h
0x14002c39b  jnz     short loc_14002C41B
0x14002c39d  mov     rcx, [rbx+0C0h]; Vpb
0x14002c3a4  call    cs:__imp_CcIsThereDirtyData
0x14002c3ab  nop     dword ptr [rax+rax+00h]
0x14002c3b0  test    al, al
0x14002c3b2  jnz     short loc_14002C41B
0x14002c3b4  lea     rcx, [rbx+3B8h]; PKTIMER
0x14002c3bb  call    cs:__imp_KeCancelTimer
0x14002c3c2  nop     dword ptr [rax+rax+00h]
0x14002c3c7  lea     rcx, [rbx+378h]; Dpc
0x14002c3ce  call    cs:__imp_KeRemoveQueueDpc
0x14002c3d5  nop     dword ptr [rax+rax+00h]
0x14002c3da  xor     r8d, r8d
0x14002c3dd  mov     rdx, rbx
0x14002c3e0  mov     r15, [rsp+78h+arg_8]
0x14002c3e8  mov     rcx, r15
0x14002c3eb  call    FatMarkVolume
0x14002c3f0  lock and dword ptr [rbx+0C8h], 0FFFFFFFBh
0x14002c3f8  mov     eax, [rbx+0C8h]
0x14002c3fe  test    al, 2
0x14002c400  jz      short loc_14002C423
0x14002c402  mov     eax, [rbx+0C8h]
0x14002c408  bt      eax, 0Bh
0x14002c40c  jb      short loc_14002C423
0x14002c40e  xor     r8d, r8d
0x14002c411  mov     rdx, rbx
0x14002c414  call    FatToggleMediaEjectDisable
0x14002c419  jmp     short loc_14002C423
0x14002c41b  mov     r15, [rsp+78h+arg_8]
0x14002c423  lea     r9, [rbx+0F4h]; ShareAccess
0x14002c42a  movzx   edx, r12w; DesiredShareAccess
0x14002c42e  mov     rax, [rsp+78h+arg_20]
0x14002c436  mov     ecx, [rax]; DesiredAccess
0x14002c438  mov     r8, r14; FileObject
0x14002c43b  cmp     dword ptr [rbx+0F0h], 0
0x14002c442  jbe     short loc_14002C462
0x14002c444  mov     [rsp+78h+Update], dil; Update
0x14002c449  call    cs:__imp_IoCheckShareAccess
0x14002c450  nop     dword ptr [rax+rax+00h]
0x14002c455  mov     [rsi], eax
0x14002c457  xor     edx, edx
0x14002c459  test    eax, eax
0x14002c45b  jns     short loc_14002C46E
0x14002c45d  jmp     loc_14002C2FF
0x14002c462  call    cs:__imp_IoSetShareAccess
0x14002c469  nop     dword ptr [rax+rax+00h]
0x14002c46e  mov     [rsp+78h+var_48], dil
0x14002c473  call    FatCreateCcb
0x14002c478  mov     r13, rax
0x14002c47b  mov     [rsp+78h+var_40], rax
0x14002c480  mov     r9, rax
0x14002c483  mov     r8, rbx
0x14002c486  mov     rcx, r14
0x14002c489  call    FatSetFileObject
0x14002c48e  lea     r8, [rbx+2E0h]
0x14002c495  mov     [r14+28h], r8
0x14002c499  add     [rbx+0F0h], edi
0x14002c49f  add     [rbx+110h], edi
0x14002c4a5  mov     cl, [r14+4Ch]
0x14002c4a9  or      cl, [r14+4Bh]
0x14002c4ad  jnz     short loc_14002C4B5
0x14002c4af  add     [rbx+114h], edi
0x14002c4b5  mov     r12b, dil
0x14002c4b8  mov     [rsp+78h+var_47], dil
0x14002c4bd  mov     eax, [r14+50h]
0x14002c4c1  or      eax, 8
0x14002c4c4  mov     [r14+50h], eax
0x14002c4c8  mov     r9, [r15+28h]
0x14002c4cc  mov     r8, [r9+0B8h]
0x14002c4d3  test    [r8+2], dil
0x14002c4d7  jz      short loc_14002C4DE
0x14002c4d9  mov     r9b, dil
0x14002c4dc  jmp     short loc_14002C4E2
0x14002c4de  mov     r9b, [r9+40h]
0x14002c4e2  mov     r8, [r8+8]
0x14002c4e6  mov     rdx, [rbx+0C0h]
0x14002c4ed  mov     r8, [r8+8]
0x14002c4f1  mov     rdx, [rdx+10h]
0x14002c4f5  call    FatExplicitDeviceAccessGranted
0x14002c4fa  xor     edx, edx
0x14002c4fc  test    eax, eax
0x14002c4fe  js      short loc_14002C506
0x14002c500  bts     dword ptr [r13+4], 11h
0x14002c506  mov     [rsi], edx
0x14002c508  mov     [rsi+8], rdi
0x14002c50c  mov     eax, edx
0x14002c50e  mov     dil, [rsp+78h+var_48]
0x14002c513  test    eax, eax
0x14002c515  jns     short loc_14002C57B
0x14002c517  test    r12b, r12b
0x14002c51a  jz      short loc_14002C53F
0x14002c51c  or      r8d, 0FFFFFFFFh
0x14002c520  add     [rbx+0F0h], r8d
0x14002c527  add     [rbx+110h], r8d
0x14002c52e  mov     al, [r14+4Ch]
0x14002c532  or      al, [r14+4Bh]
0x14002c536  jnz     short loc_14002C53F
0x14002c538  add     [rbx+114h], r8d
0x14002c53f  test    r13, r13
0x14002c542  jz      short loc_14002C550
0x14002c544  lea     rdx, [rsp+78h+var_40]
0x14002c549  call    FatDeleteCcb
0x14002c54e  xor     edx, edx
0x14002c550  test    dil, dil
0x14002c553  jz      short loc_14002C56D
0x14002c555  lea     rdx, [rbx+0F4h]; ShareAccess
0x14002c55c  mov     rcx, r14; FileObject
0x14002c55f  call    cs:__imp_IoRemoveShareAccess
0x14002c566  nop     dword ptr [rax+rax+00h]
0x14002c56b  xor     edx, edx
0x14002c56d  cmp     [rsp+78h+var_46], dl
0x14002c571  jz      short loc_14002C57B
0x14002c573  lock and dword ptr [rbx+0C8h], 0FFFFFFFEh
0x14002c57b  mov     rax, rsi
0x14002c57e  add     rsp, 40h
0x14002c582  pop     r15
0x14002c584  pop     r14
0x14002c586  pop     r13
0x14002c588  pop     r12
0x14002c58a  pop     rdi
0x14002c58b  pop     rsi
0x14002c58c  pop     rbx
0x14002c58d  retn
0x14005ca44  push    rbx
0x14005ca46  push    rbp
0x14005ca47  sub     rsp, 38h
0x14005ca4b  mov     rbp, rdx
0x14005ca4e  movzx   eax, cl
0x14005ca51  test    cl, cl
0x14005ca53  jnz     short loc_14005CA61
0x14005ca55  mov     rax, [rbp+80h]
0x14005ca5c  cmp     dword ptr [rax], 0
0x14005ca5f  jge     short loc_14005CAD9
0x14005ca61  mov     rbx, [rbp+98h]
0x14005ca68  cmp     byte ptr [rbp+31h], 0
0x14005ca6c  jz      short loc_14005CA99
0x14005ca6e  dec     dword ptr [rbx+0F0h]
0x14005ca74  dec     dword ptr [rbx+110h]
0x14005ca7a  mov     rax, [rbp+90h]
0x14005ca81  mov     cl, [rax+4Bh]
0x14005ca84  mov     al, [rax+4Ch]
0x14005ca87  or      al, cl
0x14005ca89  jnz     short loc_14005CA99
0x14005ca8b  mov     eax, [rbx+114h]
0x14005ca91  dec     eax
0x14005ca93  mov     [rbx+114h], eax
0x14005ca99  cmp     qword ptr [rbp+38h], 0
0x14005ca9e  jz      short loc_14005CAAA
0x14005caa0  lea     rdx, [rbp+38h]
0x14005caa4  call    FatDeleteCcb
0x14005caa9  nop
0x14005caaa  cmp     byte ptr [rbp+30h], 0
0x14005caae  jz      short loc_14005CACB
0x14005cab0  lea     rdx, [rbx+0F4h]; ShareAccess
0x14005cab7  mov     rcx, [rbp+90h]; FileObject
0x14005cabe  call    cs:__imp_IoRemoveShareAccess
0x14005cac5  nop     dword ptr [rax+rax+00h]
0x14005caca  nop
0x14005cacb  cmp     byte ptr [rbp+32h], 0
0x14005cacf  jz      short loc_14005CAD9
0x14005cad1  lock and dword ptr [rbx+0C8h], 0FFFFFFFEh
0x14005cad9  add     rsp, 38h
0x14005cadd  pop     rbp
0x14005cade  pop     rbx
0x14005cadf  retn
```
