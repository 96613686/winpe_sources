# FltpInternalCompletePendedPreOperation

- ea: `0x1800128f0`
- end: `0x180012d71`
- name: `FltpInternalCompletePendedPreOperation`
- size: `1153`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800126a0`

## callees

- `0x1800031e0`
- `0x180004710`
- `0x180009a00`
- `0x18000f5b0`
- `0x180011d10`
- `0x1800128f0`
- `0x1800143a0`
- `0x180017610`
- `0x180017a30`
- `0x180019690`
- `0x180060930`
- `0x18006ba60`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180012ab1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180012cb3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180012cca`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180012ab1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180012cb3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180012cca`
- `ntoskrnl!KeGetCurrentIrql` at `0x180012a2e`
- `ntoskrnl!KeGetCurrentIrql` at `0x180012a2e`

## pseudocode

```c
__int64 __fastcall FltpInternalCompletePendedPreOperation(__int64 a1, int a2, __int64 a3)
{
  __int64 v3; // rbx
  char v4; // r14
  int v6; // r10d
  __int64 v8; // rax
  __int64 v9; // r12
  __int64 v10; // r15
  __int64 v11; // rbp
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // r8
  __int64 v15; // rax
  char v16; // al
  __int64 v17; // r8
  ULONG v18; // esi
  int v19; // eax
  __int64 v20; // rax
  char v21; // al
  __int64 v22; // rdx
  int v23; // ecx
  _BYTE *v24; // rax
  _DWORD *v25; // rax
  char v26; // al
  char v27; // cl
  int v28; // edx
  unsigned __int64 v29; // r13
  int v30; // ecx
  int v31; // ecx
  char v32; // al
  __int64 v34; // rdx
  __int64 v35; // rcx
  unsigned __int64 v36; // [rsp+40h] [rbp-48h] BYREF
  char v37; // [rsp+90h] [rbp+8h] BYREF
  int v38; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v39; // [rsp+A8h] [rbp+20h] BYREF

  v38 = a2;
  v3 = *(_QWORD *)(a1 + 16);
  v4 = 0;
  v39 = 0;
  v37 = 0;
  v6 = a2;
  v8 = *(_QWORD *)(v3 + 80);
  v9 = 0;
  *(_QWORD *)(a1 + 24) = v8;
  v10 = *(_QWORD *)(v3 + 112);
  v11 = *(_QWORD *)(v8 + 16);
  if ( *(_QWORD *)(v8 + 32)
    || (*(_DWORD *)(*(_QWORD *)(v11 + 72) + 96LL) & 4) != 0
    && *(_BYTE *)(v3 + 12) == 6
    && (v12 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(v3 + 248) + 32LL) - 10), (unsigned int)v12 <= 0x3E)
    && (v13 = 0x4080000040000003LL, _bittest64(&v13, v12))
    || (*(_DWORD *)(v3 + 4) & 0x400) != 0 )
  {
    v14 = ((unsigned __int64)*(unsigned __int8 *)(v3 + 15) << 7) + *(_QWORD *)(v3 + 16) - 128LL;
  }
  else
  {
    v14 = 0;
  }
  v36 = v14;
  if ( *(int *)(v3 + 232) < 0 )
  {
    v15 = FltpProcessDirtyData(v3, v11, v14, (unsigned int)&v37, (__int64)&v38);
    v6 = v38;
    v9 = v15;
    v4 = v37;
  }
  v16 = FltpHandlePreCallbackReturnStatus(
          v3,
          *(_QWORD *)(*(_QWORD *)(a1 + 24) + 32LL),
          (unsigned int)&v36,
          (int)v3 + 128,
          v6,
          a3,
          (__int64)&v39);
  *(_DWORD *)(v3 + 232) &= ~0x80000000;
  if ( !v16 )
  {
    LOBYTE(v17) = 1;
    FltpTraceIOStatusOnFailure(v3, *(_QWORD *)(a1 + 24), v17);
    if ( *(_BYTE *)(v3 + 12) == 2 && KeGetCurrentIrql() < 2u && *(_QWORD *)(v3 + 160) )
    {
      FltpCleanupStreamListCtrlForFileObjectCloseWithStreamListCtrl(*(_QWORD *)(v11 + 64), *(_QWORD *)(v3 + 112));
      FltpReleaseStreamListCtrl(*(PVOID *)(v3 + 160));
      *(_QWORD *)(v3 + 160) = 0;
    }
    v18 = 2;
    if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(v3 + 12) + 22)) & 2) != 0 )
    {
      v19 = *(_DWORD *)(v3 + 256);
      if ( v19 >= 0 && v19 != 260 )
      {
        v20 = *(_QWORD *)(v3 + 160);
        if ( v20 )
        {
          *(_QWORD *)(v20 + 16) = v11;
          v18 = 1;
        }
      }
    }
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v11 + 56), v18);
    return v39;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 104) + 64LL) + 80LL) + 56LL) & 0x100) == 0 )
    goto LABEL_42;
  v21 = *(_BYTE *)(v3 + 12);
  if ( v21 == 6 )
  {
    v22 = *(_QWORD *)(v3 + 248);
    v23 = *(_DWORD *)(v22 + 32);
    if ( (unsigned int)(v23 - 19) <= 1 || v23 == 39 )
      goto LABEL_57;
    if ( v23 == 13 )
    {
      v24 = *(_BYTE **)(v22 + 56);
      if ( v24 && *v24 )
        goto LABEL_57;
    }
    else if ( v23 == 64 )
    {
      v25 = *(_DWORD **)(v22 + 56);
      if ( v25 )
      {
        if ( (*v25 & 1) != 0 )
          goto LABEL_57;
      }
    }
  }
  else if ( v21 == 4
         && ((**(_DWORD **)(v3 + 248) & 1) != 0
          || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 104) + 64LL) + 80LL) + 56LL) & 1) != 0
          || *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 104) + 64LL) + 80LL) + 60LL) == 27)
         && (**(_DWORD **)(v3 + 248) & 0x42) == 0 )
  {
    goto LABEL_57;
  }
  v26 = *(_BYTE *)(v3 + 12);
  if ( v26 )
  {
    if ( v26 == 13 )
    {
      v30 = *(_DWORD *)(*(_QWORD *)(v3 + 248) + 40LL);
      if ( v30 != 622792 && v30 != 623208 && v30 != 1327346 && v30 != 1343730 && v30 != 590047 )
        goto LABEL_42;
    }
    else
    {
      if ( v26 != 14 )
        goto LABEL_42;
      v31 = *(_DWORD *)(*(_QWORD *)(v3 + 248) + 40LL);
      if ( v31 != 1328152 && v31 != 1344540 )
        goto LABEL_42;
    }
  }
  else
  {
    v27 = *(_BYTE *)(*(_QWORD *)(v3 + 248) + 35LL);
    if ( (v27 & 0xFA) != 0 || v27 == 1 )
    {
LABEL_42:
      *(_DWORD *)(v3 + 4) &= ~0x400u;
      goto LABEL_43;
    }
  }
LABEL_57:
  v32 = *(_BYTE *)(v3 + 12);
  *(_DWORD *)(v3 + 4) |= 0x400u;
  v28 = *(_DWORD *)(v3 + 4);
  if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(v32 + 22)) & 2) == 0
    || v10 == *(_QWORD *)(v3 + 112) && !v4 && !*(_QWORD *)(*(_QWORD *)(v11 + 72) + 384LL) )
  {
    goto LABEL_44;
  }
  FltpSaveFileObjectFileName(v3);
LABEL_43:
  v28 = *(_DWORD *)(v3 + 4);
LABEL_44:
  v29 = v36;
  if ( (v28 & 0x10) != 0 )
  {
    if ( v10 == *(_QWORD *)(v3 + 112) )
    {
      FltpReinstateNameCachingAllFrames(*(PVOID *)(v11 + 64), v3);
    }
    else
    {
      *(_WORD *)(v36 + 120) |= 0x80u;
      *(_DWORD *)(v3 + 4) &= ~0x10u;
    }
  }
  if ( v29 )
    FltpLinkCompletionNodeToInstance(v11, v29);
  else
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v11 + 56), 1u);
  if ( v4 )
  {
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v11 + 56), 1u);
    *(_QWORD *)(a1 + 24) = FltpGetNextCallbackNodeForInstance(
                             v9,
                             (unsigned __int8)(*(_BYTE *)(*(_QWORD *)(v3 + 248) + 4LL) + 22),
                             0);
  }
  else
  {
    *(_DWORD *)(a1 + 40) |= 1u;
  }
  if ( *(_QWORD *)(a1 + 24) )
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 16) + 88LL) = a1;
    return FltpPerformPreCallbacks(a1);
  }
  if ( *(_BYTE *)(v3 + 12) == 2 )
  {
    v34 = *(_QWORD *)(v3 + 112);
    v35 = *(_QWORD *)(v11 + 64);
    if ( *(_QWORD *)(v3 + 160) )
    {
      FltpCleanupStreamListCtrlForFileObjectCloseWithStreamListCtrl(v35, v34);
      FltpReleaseStreamListCtrl(*(PVOID *)(v3 + 160));
      *(_QWORD *)(v3 + 160) = 0;
    }
    else
    {
      FltpCleanupStreamListCtrlForFileObjectClose(v35, v34);
    }
  }
  return v39;
}

```

## disassembly

```asm
0x1800128f0  mov     rax, rsp
0x1800128f3  mov     [rax+18h], rbx
0x1800128f7  mov     [rax+10h], edx
0x1800128fa  push    rbp
0x1800128fb  push    rsi
0x1800128fc  push    rdi
0x1800128fd  push    r12
0x1800128ff  push    r13
0x180012901  push    r14
0x180012903  push    r15
0x180012905  sub     rsp, 50h
0x180012909  mov     rbx, [rcx+10h]
0x18001290d  xor     r13d, r13d
0x180012910  xor     r14b, r14b
0x180012913  mov     [rax+20h], r13d
0x180012917  mov     [rax+8], r14b
0x18001291b  mov     rsi, r8
0x18001291e  mov     r10d, edx
0x180012921  mov     rdi, rcx
0x180012924  mov     rax, [rbx+50h]
0x180012928  mov     r12d, r13d
0x18001292b  mov     [rcx+18h], rax
0x18001292f  mov     r15, [rbx+70h]
0x180012933  mov     rbp, [rax+10h]
0x180012937  cmp     [rax+20h], r13
0x18001293b  jnz     short loc_18001297F
0x18001293d  mov     rax, [rbp+48h]
0x180012941  mov     ecx, [rax+60h]
0x180012944  test    cl, 4
0x180012947  jz      short loc_180012971
0x180012949  cmp     byte ptr [rbx+0Ch], 6
0x18001294d  jnz     short loc_180012971
0x18001294f  mov     rax, [rbx+0F8h]
0x180012956  mov     ecx, [rax+20h]
0x180012959  add     ecx, 0FFFFFFF6h
0x18001295c  cmp     ecx, 3Eh ; '>'
0x18001295f  ja      short loc_180012971
0x180012961  mov     rax, 4080000040000003h
0x18001296b  bt      rax, rcx
0x18001296f  jb      short loc_18001297F
0x180012971  test    dword ptr [rbx+4], 400h
0x180012978  jnz     short loc_18001297F
0x18001297a  mov     r8, r13
0x18001297d  jmp     short loc_180012992
0x18001297f  movzx   ecx, byte ptr [rbx+0Fh]
0x180012983  mov     r8, [rbx+10h]
0x180012987  shl     rcx, 7
0x18001298b  add     r8, 0FFFFFFFFFFFFFF80h
0x18001298f  add     r8, rcx
0x180012992  mov     [rsp+88h+var_48], r8
0x180012997  cmp     [rbx+0E8h], r12d
0x18001299e  jge     short loc_1800129D4
0x1800129a0  lea     rax, [rsp+88h+arg_8]
0x1800129a8  mov     rdx, rbp
0x1800129ab  lea     r9, [rsp+88h+arg_0]
0x1800129b3  mov     [rsp+88h+var_68], rax
0x1800129b8  mov     rcx, rbx
0x1800129bb  call    FltpProcessDirtyData
0x1800129c0  mov     r10d, [rsp+88h+arg_8]
0x1800129c8  mov     r12, rax
0x1800129cb  movzx   r14d, [rsp+88h+arg_0]
0x1800129d4  mov     rdx, [rdi+18h]
0x1800129d8  lea     rax, [rsp+88h+arg_18]
0x1800129e0  mov     [rsp+88h+var_58], rax
0x1800129e5  lea     r9, [rbx+80h]
0x1800129ec  mov     [rsp+88h+var_60], rsi
0x1800129f1  lea     r8, [rsp+88h+var_48]
0x1800129f6  mov     rcx, rbx
0x1800129f9  mov     dword ptr [rsp+88h+var_68], r10d
0x1800129fe  mov     rdx, [rdx+20h]
0x180012a02  call    FltpHandlePreCallbackReturnStatus
0x180012a07  and     dword ptr [rbx+0E8h], 7FFFFFFFh
0x180012a11  test    al, al
0x180012a13  jnz     loc_180012AC2
0x180012a19  mov     rdx, [rdi+18h]
0x180012a1d  mov     r8b, 1
0x180012a20  mov     rcx, rbx
0x180012a23  call    FltpTraceIOStatusOnFailure
0x180012a28  cmp     byte ptr [rbx+0Ch], 2
0x180012a2c  jnz     short loc_180012A6A
0x180012a2e  call    cs:__imp_KeGetCurrentIrql
0x180012a35  nop     dword ptr [rax+rax+00h]
0x180012a3a  cmp     al, 2
0x180012a3c  jnb     short loc_180012A6A
0x180012a3e  mov     r8, [rbx+0A0h]
0x180012a45  test    r8, r8
0x180012a48  jz      short loc_180012A6A
0x180012a4a  mov     rdx, [rbx+70h]
0x180012a4e  mov     rcx, [rbp+40h]
0x180012a52  call    FltpCleanupStreamListCtrlForFileObjectCloseWithStreamListCtrl
0x180012a57  mov     rcx, [rbx+0A0h]; Entry
0x180012a5e  call    FltpReleaseStreamListCtrl
0x180012a63  mov     [rbx+0A0h], r13
0x180012a6a  movzx   eax, byte ptr [rbx+0Ch]
0x180012a6e  lea     rcx, FltpOperationFlags
0x180012a75  add     al, 16h
0x180012a77  mov     esi, 2
0x180012a7c  movzx   eax, al
0x180012a7f  test    [rax+rcx], sil
0x180012a83  jz      short loc_180012AAB
0x180012a85  mov     eax, [rbx+100h]
0x180012a8b  test    eax, eax
0x180012a8d  js      short loc_180012AAB
0x180012a8f  cmp     eax, 104h
0x180012a94  jz      short loc_180012AAB
0x180012a96  mov     rax, [rbx+0A0h]
0x180012a9d  test    rax, rax
0x180012aa0  jz      short loc_180012AAB
0x180012aa2  mov     [rax+10h], rbp
0x180012aa6  mov     esi, 1
0x180012aab  mov     rcx, [rbp+38h]; RunRef
0x180012aaf  mov     edx, esi; Count
0x180012ab1  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x180012ab8  nop     dword ptr [rax+rax+00h]
0x180012abd  jmp     loc_180012D51
0x180012ac2  mov     rax, [rbx+68h]
0x180012ac6  mov     rcx, [rax+40h]
0x180012aca  mov     rax, [rcx+50h]
0x180012ace  mov     ecx, [rax+38h]
0x180012ad1  bt      ecx, 8
0x180012ad5  jnb     loc_180012B9F
0x180012adb  movzx   eax, byte ptr [rbx+0Ch]
0x180012adf  cmp     al, 6
0x180012ae1  jnz     short loc_180012B34
0x180012ae3  mov     rdx, [rbx+0F8h]
0x180012aea  mov     ecx, [rdx+20h]
0x180012aed  lea     eax, [rcx-13h]
0x180012af0  cmp     eax, 1
0x180012af3  jbe     loc_180012C3B
0x180012af9  cmp     ecx, 27h ; '''
0x180012afc  jz      loc_180012C3B
0x180012b02  cmp     ecx, 0Dh
0x180012b05  jnz     short loc_180012B1A
0x180012b07  mov     rax, [rdx+38h]
0x180012b0b  test    rax, rax
0x180012b0e  jz      short loc_180012B7E
0x180012b10  cmp     [rax], r13b
0x180012b13  jz      short loc_180012B7E
0x180012b15  jmp     loc_180012C3B
0x180012b1a  cmp     ecx, 40h ; '@'
0x180012b1d  jnz     short loc_180012B7E
0x180012b1f  mov     rax, [rdx+38h]
0x180012b23  test    rax, rax
0x180012b26  jz      short loc_180012B7E
0x180012b28  mov     eax, [rax]
0x180012b2a  test    al, 1
0x180012b2c  jnz     loc_180012C3B
0x180012b32  jmp     short loc_180012B7E
0x180012b34  cmp     al, 4
0x180012b36  jnz     short loc_180012B7E
0x180012b38  mov     rax, [rbx+0F8h]
0x180012b3f  mov     ecx, [rax]
0x180012b41  test    cl, 1
0x180012b44  jnz     short loc_180012B6C
0x180012b46  mov     rax, [rbx+68h]
0x180012b4a  mov     rcx, [rax+40h]
0x180012b4e  mov     rax, [rcx+50h]
0x180012b52  mov     ecx, [rax+38h]
0x180012b55  test    cl, 1
0x180012b58  jnz     short loc_180012B6C
0x180012b5a  mov     rax, [rbx+68h]
0x180012b5e  mov     rcx, [rax+40h]
0x180012b62  mov     rax, [rcx+50h]
0x180012b66  cmp     dword ptr [rax+3Ch], 1Bh
0x180012b6a  jnz     short loc_180012B7E
0x180012b6c  mov     rax, [rbx+0F8h]
0x180012b73  mov     ecx, [rax]
0x180012b75  test    cl, 42h
0x180012b78  jz      loc_180012C3B
0x180012b7e  movzx   eax, byte ptr [rbx+0Ch]
0x180012b82  test    al, al
0x180012b84  jnz     short loc_180012BE1
0x180012b86  mov     rax, [rbx+0F8h]
0x180012b8d  movzx   ecx, byte ptr [rax+23h]
0x180012b91  test    cl, 0FAh
0x180012b94  jnz     short loc_180012B9F
0x180012b96  cmp     cl, 1
0x180012b99  jnz     loc_180012C3B
0x180012b9f  and     dword ptr [rbx+4], 0FFFFFBFFh
0x180012ba6  mov     edx, [rbx+4]
0x180012ba9  mov     r13, [rsp+88h+var_48]
0x180012bae  test    dl, 10h
0x180012bb1  jz      loc_180012C96
0x180012bb7  cmp     r15, [rbx+70h]
0x180012bbb  jnz     loc_180012C88
0x180012bc1  mov     r9, [rdi+8]
0x180012bc5  mov     r8d, 0C0000120h
0x180012bcb  mov     rcx, [rbp+40h]; OwnerId
0x180012bcf  mov     rdx, r15
0x180012bd2  mov     [rsp+88h+var_68], rbx; __int64
0x180012bd7  call    FltpReinstateNameCachingAllFrames
0x180012bdc  jmp     loc_180012C96
0x180012be1  cmp     al, 0Dh
0x180012be3  jnz     short loc_180012C19
0x180012be5  mov     rax, [rbx+0F8h]
0x180012bec  mov     ecx, [rax+28h]
0x180012bef  cmp     ecx, 980C8h
0x180012bf5  jz      short loc_180012C3B
0x180012bf7  cmp     ecx, 98268h
0x180012bfd  jz      short loc_180012C3B
0x180012bff  cmp     ecx, 1440F2h
0x180012c05  jz      short loc_180012C3B
0x180012c07  cmp     ecx, 1480F2h
0x180012c0d  jz      short loc_180012C3B
0x180012c0f  cmp     ecx, 900DFh
0x180012c15  jnz     short loc_180012B9F
0x180012c17  jmp     short loc_180012C3B
0x180012c19  cmp     al, 0Eh
0x180012c1b  jnz     short loc_180012B9F
0x180012c1d  mov     rax, [rbx+0F8h]
0x180012c24  mov     ecx, [rax+28h]
0x180012c27  cmp     ecx, 144418h
0x180012c2d  jz      short loc_180012C3B
0x180012c2f  cmp     ecx, 14841Ch
0x180012c35  jnz     loc_180012B9F
0x180012c3b  movzx   eax, byte ptr [rbx+0Ch]
0x180012c3f  lea     rcx, FltpOperationFlags
0x180012c46  or      dword ptr [rbx+4], 400h
0x180012c4d  add     al, 16h
0x180012c4f  mov     edx, [rbx+4]
0x180012c52  movzx   eax, al
0x180012c55  test    byte ptr [rax+rcx], 2
0x180012c59  jz      loc_180012BA9
0x180012c5f  cmp     r15, [rbx+70h]
0x180012c63  jnz     short loc_180012C7B
0x180012c65  test    r14b, r14b
0x180012c68  jnz     short loc_180012C7B
0x180012c6a  mov     rax, [rbp+48h]
0x180012c6e  cmp     [rax+180h], r13
0x180012c75  jz      loc_180012BA9
0x180012c7b  mov     rcx, rbx
0x180012c7e  call    FltpSaveFileObjectFileName
0x180012c83  jmp     loc_180012BA6
0x180012c88  mov     eax, 80h
0x180012c8d  or      [r13+78h], ax
0x180012c92  and     dword ptr [rbx+4], 0FFFFFFEFh
0x180012c96  mov     esi, 1
0x180012c9b  test    r13, r13
0x180012c9e  jz      short loc_180012CAD
0x180012ca0  mov     rdx, r13
0x180012ca3  mov     rcx, rbp
0x180012ca6  call    FltpLinkCompletionNodeToInstance
0x180012cab  jmp     short loc_180012CBF
0x180012cad  mov     rcx, [rbp+38h]; RunRef
0x180012cb1  mov     edx, esi; Count
0x180012cb3  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x180012cba  nop     dword ptr [rax+rax+00h]
0x180012cbf  test    r14b, r14b
0x180012cc2  jz      short loc_180012CF8
0x180012cc4  mov     rcx, [rbp+38h]; RunRef
0x180012cc8  mov     edx, esi; Count
0x180012cca  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x180012cd1  nop     dword ptr [rax+rax+00h]
0x180012cd6  mov     rax, [rbx+0F8h]
0x180012cdd  xor     r8d, r8d
0x180012ce0  movzx   ecx, byte ptr [rax+4]
0x180012ce4  add     cl, 16h
0x180012ce7  movzx   edx, cl
0x180012cea  mov     rcx, r12
0x180012ced  call    FltpGetNextCallbackNodeForInstance
0x180012cf2  mov     [rdi+18h], rax
0x180012cf6  jmp     short loc_180012CFB
0x180012cf8  or      [rdi+28h], esi
0x180012cfb  cmp     qword ptr [rdi+18h], 0
0x180012d00  jz      short loc_180012D14
0x180012d02  mov     rax, [rdi+10h]
0x180012d06  mov     rcx, rdi
0x180012d09  mov     [rax+58h], rdi
0x180012d0d  call    FltpPerformPreCallbacks
0x180012d12  jmp     short loc_180012D58
0x180012d14  cmp     byte ptr [rbx+0Ch], 2
0x180012d18  jnz     short loc_180012D51
0x180012d1a  mov     r8, [rbx+0A0h]
0x180012d21  mov     rdx, [rbx+70h]
0x180012d25  mov     rcx, [rbp+40h]
0x180012d29  test    r8, r8
0x180012d2c  jz      short loc_180012D4C
0x180012d2e  call    FltpCleanupStreamListCtrlForFileObjectCloseWithStreamListCtrl
0x180012d33  mov     rcx, [rbx+0A0h]; Entry
0x180012d3a  call    FltpReleaseStreamListCtrl
0x180012d3f  mov     qword ptr [rbx+0A0h], 0
0x180012d4a  jmp     short loc_180012D51
0x180012d4c  call    FltpCleanupStreamListCtrlForFileObjectClose
0x180012d51  mov     eax, [rsp+88h+arg_18]
0x180012d58  mov     rbx, [rsp+88h+arg_10]
0x180012d60  add     rsp, 50h
0x180012d64  pop     r15
0x180012d66  pop     r14
0x180012d68  pop     r13
0x180012d6a  pop     r12
0x180012d6c  pop     rdi
0x180012d6d  pop     rsi
0x180012d6e  pop     rbp
0x180012d6f  retn
```
