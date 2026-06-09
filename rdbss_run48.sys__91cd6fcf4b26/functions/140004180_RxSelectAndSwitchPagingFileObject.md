# RxSelectAndSwitchPagingFileObject

- ea: `0x140004180`
- end: `0x140004ab1`
- name: `RxSelectAndSwitchPagingFileObject`
- size: `2353`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `7`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x140004ac0`
- `0x14004bd80`
- `0x14005e810`
- `0x1400649a0`
- `0x140066390`
- `0x14006aa40`
- `0x14006c5c0`

## callees

- `0x1400031a0`
- `0x140004180`
- `0x140010490`
- `0x140010530`
- `0x1400111b0`
- `0x140015230`
- `0x140017370`
- `0x140017420`
- `0x1400249cc`
- `0x140071700`

## import_xrefs

- `ntoskrnl!MmIsFileSectionActive` at `0x140004287`
- `ntoskrnl!MmIsFileSectionActive` at `0x140004287`
- `ntoskrnl!ObReferenceObjectSafe` at `0x14000467c`
- `ntoskrnl!ObReferenceObjectSafe` at `0x1400046b2`
- `ntoskrnl!ObReferenceObjectSafe` at `0x14000467c`
- `ntoskrnl!ObReferenceObjectSafe` at `0x1400046b2`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140004a4a`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140004a5f`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140004a74`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140004a89`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140004a4a`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140004a5f`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140004a74`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140004a89`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1400042a7`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1400042a7`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x1400048df`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x140004915`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x14000495f`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x1400048df`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x140004915`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x14000495f`
- `ntoskrnl!KeBugCheckEx` at `0x140004a34`
- `ntoskrnl!KeBugCheckEx` at `0x140004a34`

## pseudocode

```c
void __fastcall RxSelectAndSwitchPagingFileObject(
        ULONG_PTR BugCheckParameter3,
        _QWORD *a2,
        ULONG_PTR a3,
        unsigned __int8 a4)
{
  ULONG_PTR v6; // rbx
  __int64 v7; // rdi
  int v8; // eax
  char v9; // r12
  char v10; // r13
  bool v11; // si
  __int64 v12; // rcx
  bool v13; // al
  unsigned __int8 v14; // si
  __int64 v15; // rcx
  __int64 v16; // r8
  _QWORD *v17; // r9
  ULONG_PTR v18; // rdx
  struct _FILE_OBJECT *v19; // rax
  _QWORD *v20; // rcx
  char v21; // r9
  char v22; // r10
  struct _FILE_OBJECT *v23; // rsi
  _QWORD *v24; // rax
  _DWORD *v25; // rbx
  int v26; // eax
  int v27; // eax
  _QWORD *v28; // rcx
  _QWORD *v29; // rax
  _QWORD *v30; // r9
  int v31; // r8d
  __int64 v32; // r10
  int v33; // eax
  __int64 v34; // r8
  PVOID *v35; // rcx
  _QWORD *v36; // rdx
  _QWORD *v37; // rax
  _QWORD *v38; // rax
  NTSTATUS v39; // eax
  NTSTATUS v40; // r8d
  NTSTATUS v41; // r9d
  unsigned int v42; // esi
  __int64 v43; // rax
  __int64 v44; // rax
  UCHAR IrpMajorCode; // [rsp+20h] [rbp-E0h]
  void *v46; // [rsp+28h] [rbp-D8h]
  char v47; // [rsp+80h] [rbp-80h]
  char v48; // [rsp+81h] [rbp-7Fh]
  char v49; // [rsp+82h] [rbp-7Eh]
  ULONG_PTR v50; // [rsp+88h] [rbp-78h]
  _QWORD *v51; // [rsp+90h] [rbp-70h]
  _QWORD *v52; // [rsp+90h] [rbp-70h]
  ULONG_PTR v53; // [rsp+98h] [rbp-68h]
  struct _FILE_OBJECT *v54; // [rsp+98h] [rbp-68h]
  int v55; // [rsp+A0h] [rbp-60h]
  int v56; // [rsp+A4h] [rbp-5Ch]
  __int64 v57; // [rsp+A8h] [rbp-58h]
  PVOID v58[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v59; // [rsp+C0h] [rbp-40h]
  PVOID v60[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v61; // [rsp+D8h] [rbp-28h]
  __int64 v62; // [rsp+E0h] [rbp-20h]
  PVOID Object[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v64; // [rsp+F8h] [rbp-8h]
  PVOID v65[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v66; // [rsp+110h] [rbp+10h]
  _QWORD v67[2]; // [rsp+118h] [rbp+18h] BYREF
  int v68; // [rsp+128h] [rbp+28h]
  int v69; // [rsp+12Ch] [rbp+2Ch]
  int v71; // [rsp+170h] [rbp+70h]
  int v73; // [rsp+180h] [rbp+80h] BYREF

  v64 = 0;
  v66 = 0;
  v59 = 0;
  v61 = 0;
  v6 = BugCheckParameter3;
  *(_OWORD *)Object = 0;
  *(_OWORD *)v65 = 0;
  *(_OWORD *)v58 = 0;
  *(_OWORD *)v60 = 0;
  if ( *(_WORD *)BugCheckParameter3 != 0xEC22 )
    goto LABEL_148;
  v7 = *(_QWORD *)(BugCheckParameter3 + 488);
  v55 = *(_DWORD *)(BugCheckParameter3 + 496);
  v56 = *(_DWORD *)(BugCheckParameter3 + 500);
  v62 = v7;
  if ( !v7 )
  {
    v10 = 88;
    v49 = 1;
    v9 = 88;
LABEL_10:
    v48 = 1;
    goto LABEL_11;
  }
  v8 = *(_DWORD *)(v7 + 72);
  v9 = 65;
  v10 = 67;
  v11 = (v8 & 0x400000) == 0;
  v49 = v11;
  if ( (v8 & 0x400000) != 0 )
    v9 = 68;
  if ( (*(_DWORD *)(*(_QWORD *)(v7 + 32) + 128LL) & 8) != 0 )
    v10 = 85;
  if ( (int)((__int64 (*)(void))RxReconnectSrvOpen)() < 0 )
    goto LABEL_10;
  v48 = 0;
  v49 = v11;
LABEL_11:
  v12 = *(_QWORD *)(v6 + 304) + 8LL;
  v73 = 0;
  MmIsFileSectionActive(v12, 7, &v73);
  v13 = v73 && MmDoesFileHaveUserWritableReferences((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v6 + 304) + 8LL));
  v14 = a4 | 1;
  if ( !v13 )
    v14 = a4;
  if ( a3 && (!v7 || a3 != v7 && a3 != *(_QWORD *)(v7 + 32)) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_4aafbbf870a73d89198003f1abc844b5_Traceguids, v6, a3);
    }
    goto LABEL_149;
  }
  LOBYTE(v73) = 88;
  v47 = 88;
  if ( !a2 || !v49 )
    goto LABEL_51;
  v15 = a2[4];
  if ( ((*(_BYTE *)(v15 + 120) | (unsigned __int8)v55) & 2) != 0 )
    v14 |= 1u;
  if ( *(int *)(v15 + 92) <= 0 || (int)((__int64 (*)(void))RxReconnectSrvOpen)() < 0 )
    goto LABEL_51;
  v17 = a2;
  v18 = a2[4];
  v50 = v18;
  if ( (*(_BYTE *)(v18 + 120) & 2) == 0 && (v14 & 1) != 0 )
  {
    if ( !v48 )
      goto LABEL_45;
LABEL_51:
    v18 = v6 + 264;
    v16 = 60330;
    v53 = v6 + 264;
    v24 = (_QWORD *)(v6 + 264);
    do
    {
      v24 = (_QWORD *)*v24;
      if ( v24 == (_QWORD *)v18 )
        goto LABEL_108;
    }
    while ( *((_WORD *)v24 - 68) == 0xEBAA );
    if ( v24 != (_QWORD *)136 )
    {
      v25 = v24 - 17;
LABEL_56:
      if ( v25 != (_DWORD *)a3 )
      {
        v26 = v25[30];
        if ( (v26 & 1) != 0 && ((v14 & 1) == 0 || (v26 & 2) != 0) && (v25[18] & 0x40C) == 0 && v25[23] )
        {
          v27 = RxReconnectSrvOpen(v25, v18, 60330);
          v16 = 60330;
          if ( v27 >= 0 )
          {
            v28 = v25 + 46;
            v29 = v25 + 46;
            do
            {
              v29 = (_QWORD *)*v29;
              if ( v29 == v28 )
                goto LABEL_102;
              v30 = v29 - 14;
              v52 = v29 - 14;
            }
            while ( *((_WORD *)v29 - 56) == 0xEBAA );
            if ( v29 == (_QWORD *)112 )
              goto LABEL_102;
LABEL_67:
            if ( v30 == (_QWORD *)a3 )
            {
LABEL_98:
              v37 = v30 + 14;
              while ( 1 )
              {
                v37 = (_QWORD *)*v37;
                if ( v37 == v28 )
                  goto LABEL_102;
                v30 = v37 - 14;
                v52 = v37 - 14;
                if ( *((_WORD *)v37 - 56) != 0xEBAA )
                {
                  if ( v37 != (_QWORD *)112 )
                    goto LABEL_67;
                  goto LABEL_102;
                }
              }
            }
            v31 = *((_DWORD *)v30 + 18);
            if ( (v31 & 0x1000002) != 0
              || (v32 = v30[6], (v57 = v32) == 0)
              || v30 != a2 && (*(_DWORD *)(v32 + 80) & 0x40000) == 0
              || (*(_DWORD *)(v32 + 80) & 0x200000) != 0 )
            {
LABEL_97:
              v16 = 60330;
              goto LABEL_98;
            }
            v33 = *(_DWORD *)(v32 + 80) & 8;
            if ( (v31 & 0x400000) != 0 )
            {
              if ( v33 )
              {
                if ( !v48 && !(unsigned __int8)IsBetterPagingFO(v30, v60, v14 & 1) )
                  goto LABEL_96;
                if ( !(unsigned __int8)ObReferenceObjectSafe(v32) )
                  goto LABEL_95;
                v35 = v60;
              }
              else
              {
                if ( !v48 && !(unsigned __int8)IsBetterPagingFO(v30, v58, v14 & 1) )
                  goto LABEL_96;
                if ( !(unsigned __int8)ObReferenceObjectSafe(v32) )
                  goto LABEL_95;
                v35 = v58;
              }
              v36 = v52;
              v34 = v57;
            }
            else if ( v33 )
            {
              if ( !v48 && !(unsigned __int8)IsBetterPagingFO(v30, v65, v14 & 1) )
                goto LABEL_96;
              v34 = 0;
              v35 = v65;
              v36 = v30;
            }
            else
            {
              if ( (v25[30] & 6) != 0 && *(_QWORD *)(v32 + 48) )
                v14 |= 1u;
              if ( !v48 && !(unsigned __int8)IsBetterPagingFO(v30, Object, v14 & 1) )
                goto LABEL_96;
              v34 = 0;
              v35 = Object;
              v36 = v30;
            }
            UpdatePagingObjectSelection(v35, v36, v34);
LABEL_95:
            v30 = v52;
LABEL_96:
            v28 = v25 + 46;
            goto LABEL_97;
          }
LABEL_102:
          v18 = v53;
        }
      }
      v38 = v25 + 34;
      while ( 1 )
      {
        v38 = (_QWORD *)*v38;
        if ( v38 == (_QWORD *)v18 )
          break;
        v25 = v38 - 17;
        if ( *((_WORD *)v38 - 68) != 0xEBAA )
        {
          if ( v38 != (_QWORD *)136 )
            goto LABEL_56;
          break;
        }
      }
      v6 = BugCheckParameter3;
      LOBYTE(v7) = v62;
    }
LABEL_108:
    v20 = Object[0];
    v51 = Object[0];
    if ( Object[0] )
    {
      v18 = *((_QWORD *)Object[0] + 4);
      v21 = 67;
      v19 = (struct _FILE_OBJECT *)*((_QWORD *)Object[0] + 6);
      v22 = 65;
      LOBYTE(v73) = 67;
      v16 = 0;
      v47 = 65;
      goto LABEL_118;
    }
    v20 = v58[0];
    v51 = v58[0];
    if ( v58[0] )
    {
      v18 = *((_QWORD *)v58[0] + 4);
      v21 = 67;
      v19 = (struct _FILE_OBJECT *)v58[1];
      v22 = 68;
      LOBYTE(v73) = 67;
      v16 = 0;
      v47 = 68;
      goto LABEL_118;
    }
    v20 = v65[0];
    v51 = v65[0];
    if ( v65[0] )
    {
      v19 = (struct _FILE_OBJECT *)*((_QWORD *)v65[0] + 6);
      v22 = 65;
    }
    else
    {
      v20 = v60[0];
      v51 = v60[0];
      if ( !v60[0] )
      {
        LODWORD(v23) = 0;
LABEL_142:
        RxClearPagingFileObject(v6, v18, v16);
        goto LABEL_143;
      }
      v19 = (struct _FILE_OBJECT *)v60[1];
      v22 = 68;
    }
    v18 = v20[4];
    v21 = 85;
    LOBYTE(v73) = 85;
    v47 = v22;
LABEL_117:
    v16 = 256;
    goto LABEL_118;
  }
  if ( (*(_DWORD *)(v18 + 128) & 8) != 0 )
  {
    if ( v7 && !v48 && ((v55 & 2) != 0 || (v14 & 1) == 0) )
      goto LABEL_45;
    v19 = (struct _FILE_OBJECT *)a2[6];
    v20 = a2;
    v21 = 88;
    v51 = a2;
    v22 = 88;
    goto LABEL_117;
  }
  if ( v7 && (*(_DWORD *)(*(_QWORD *)(v7 + 32) + 128LL) & 8) == 0 )
  {
    v68 = v55;
    v69 = (unsigned __int8)v56;
    v67[0] = v7;
    v67[1] = 0;
    if ( v48 )
    {
LABEL_38:
      v19 = (struct _FILE_OBJECT *)v17[6];
      v20 = v17;
      v21 = 88;
      v51 = v20;
      v22 = 88;
      v16 = 0;
      goto LABEL_119;
    }
    if ( (unsigned __int8)IsBetterPagingFO(a2, v67, v14 & 1) )
    {
      v18 = v50;
      goto LABEL_38;
    }
LABEL_45:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_4aafbbf870a73d89198003f1abc844b5_Traceguids, v7, v6);
    }
    if ( (v14 & 4) == 0 )
    {
LABEL_148:
      if ( !a3 )
        goto LABEL_151;
      goto LABEL_149;
    }
    v18 = *(_QWORD *)(v7 + 32);
    v21 = 88;
    v23 = *(struct _FILE_OBJECT **)(v7 + 48);
    v22 = 88;
    v50 = v18;
    goto LABEL_132;
  }
  v19 = (struct _FILE_OBJECT *)a2[6];
  v20 = a2;
  v21 = 88;
  v51 = a2;
  v22 = 88;
  v16 = 0;
LABEL_118:
  v50 = v18;
LABEL_119:
  v54 = v19;
  v71 = v16;
  if ( !v19 )
  {
    LODWORD(v23) = 0;
    goto LABEL_142;
  }
  if ( (*(_BYTE *)(v6 + 496) & v14 & 2) == 0 || (*(_DWORD *)(v18 + 120) & 2) != 0 )
    goto LABEL_131;
  v39 = RxFlushFcbInSystemCache((PFCB)v6, 1u);
  v42 = v39;
  if ( v39 >= 0 )
  {
LABEL_130:
    v20 = v51;
    v18 = v50;
    LODWORD(v16) = v71;
    v21 = v73;
    v22 = v47;
LABEL_131:
    v23 = v54;
    *(_QWORD *)(v6 + 488) = v20;
    *(_DWORD *)(v6 + 496) = *(_DWORD *)(v18 + 120);
    *(_BYTE *)(v6 + 500) = *(_BYTE *)(v18 + 124) & 7;
    *(_DWORD *)(v6 + 500) = v16 | *(_DWORD *)(v6 + 500) & 0xFFFFFEFF;
LABEL_132:
    if ( *(_QWORD *)(*(_QWORD *)(v6 + 304) + 16LL) )
    {
      FsRtlChangeBackingFileObject(0, v23, ChangeSharedCacheMap, 0);
      v18 = v50;
      v21 = v73;
      v22 = v47;
    }
    if ( *(_QWORD *)(*(_QWORD *)(v6 + 304) + 8LL) )
    {
      FsRtlChangeBackingFileObject(0, v23, ChangeDataControlArea, 0);
      v18 = v50;
      v21 = v73;
      v22 = v47;
    }
    v44 = *(_QWORD *)(v6 + 720);
    if ( v44 && v44 != v18 || !*(_QWORD *)(*(_QWORD *)(v6 + 304) + 24LL) )
      goto LABEL_144;
    FsRtlChangeBackingFileObject(0, v23, ChangeImageControlArea, 0);
LABEL_143:
    v22 = v47;
    v21 = v73;
LABEL_144:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqqqDDccqDDcc(
        WPP_GLOBAL_Control->AttachedDevice,
        (unsigned __int8)*(_DWORD *)(v6 + 500),
        v16,
        (_DWORD)v23,
        v6,
        *(_QWORD *)(v6 + 720),
        v7,
        v55,
        v56,
        v9,
        v10,
        *(_QWORD *)(v6 + 488),
        *(_DWORD *)(v6 + 496),
        *(_DWORD *)(v6 + 500),
        v22,
        v21);
    }
    goto LABEL_148;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    IrpMajorCode = v39;
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_4aafbbf870a73d89198003f1abc844b5_Traceguids);
  }
  RxCcLogError((PDEVICE_OBJECT)v6, (PUNICODE_STRING)v42, v40, v41, IrpMajorCode, v46);
  if ( a3 )
  {
    v43 = *(_QWORD *)(v6 + 488);
    if ( v43 != a3 && *(_QWORD *)(v43 + 32) != a3 )
    {
LABEL_149:
      if ( *(_QWORD *)(v6 + 488) == a3 )
        KeBugCheckEx(0x27u, 0xFCB002AD, a3, v6, 0);
      goto LABEL_151;
    }
    goto LABEL_130;
  }
LABEL_151:
  if ( Object[1] )
    ObDereferenceObjectDeferDelete(Object[1]);
  if ( v58[1] )
    ObDereferenceObjectDeferDelete(v58[1]);
  if ( v65[1] )
    ObDereferenceObjectDeferDelete(v65[1]);
  if ( v60[1] )
    ObDereferenceObjectDeferDelete(v60[1]);
}

```

## disassembly

```asm
0x140004180  mov     [rsp-8+arg_18], rbx
0x140004185  mov     [rsp-8+arg_8], rdx
0x14000418a  mov     [rsp-8+arg_0], rcx
0x14000418f  push    rbp
0x140004190  push    rsi
0x140004191  push    rdi
0x140004192  push    r12
0x140004194  push    r13
0x140004196  push    r14
0x140004198  push    r15
0x14000419a  lea     rbp, [rsp-30h]
0x14000419f  sub     rsp, 130h
0x1400041a6  xor     eax, eax
0x1400041a8  xorps   xmm0, xmm0
0x1400041ab  xorps   xmm1, xmm1
0x1400041ae  mov     [rbp+60h+var_68], rax
0x1400041b2  mov     [rbp+60h+var_50], rax
0x1400041b6  mov     r14d, r9d
0x1400041b9  mov     [rbp+60h+var_A0], rax
0x1400041bd  mov     r15, r8
0x1400041c0  mov     [rbp+60h+var_88], rax
0x1400041c4  mov     rbx, rcx
0x1400041c7  mov     eax, 0EC22h
0x1400041cc  movups  xmmword ptr [rbp+60h+Object], xmm0
0x1400041d0  movups  xmmword ptr [rbp+60h+var_60], xmm1
0x1400041d4  movups  xmmword ptr [rbp+60h+var_B0], xmm0
0x1400041d8  movups  xmmword ptr [rbp+60h+var_98], xmm1
0x1400041dc  cmp     [rcx], ax
0x1400041df  jnz     loc_140004A0D
0x1400041e5  mov     rdi, [rcx+1E8h]
0x1400041ec  mov     eax, [rcx+1F0h]
0x1400041f2  mov     [rbp+60h+var_C0], eax
0x1400041f5  mov     eax, [rcx+1F4h]
0x1400041fb  mov     [rbp+60h+var_BC], eax
0x1400041fe  mov     [rbp+60h+var_80], rdi
0x140004202  test    rdi, rdi
0x140004205  jz      short loc_140004257
0x140004207  mov     eax, [rdi+48h]
0x14000420a  mov     edx, 44h ; 'D'
0x14000420f  mov     rcx, [rdi+20h]
0x140004213  bt      eax, 16h
0x140004217  mov     r12d, 41h ; 'A'
0x14000421d  mov     r13d, 43h ; 'C'
0x140004223  setnb   sil
0x140004227  bt      eax, 16h
0x14000422b  mov     [rbp+60h+var_DE], sil
0x14000422f  mov     eax, [rcx+80h]
0x140004235  cmovb   r12d, edx
0x140004239  test    al, 8
0x14000423b  mov     eax, 55h ; 'U'
0x140004240  cmovnz  r13d, eax
0x140004244  call    RxReconnectSrvOpen
0x140004249  test    eax, eax
0x14000424b  js      short loc_140004262
0x14000424d  mov     [rbp+60h+var_DF], 0
0x140004251  mov     [rbp+60h+var_DE], sil
0x140004255  jmp     short loc_140004266
0x140004257  mov     r13b, 58h ; 'X'
0x14000425a  mov     [rbp+60h+var_DE], 1
0x14000425e  movzx   r12d, r13b
0x140004262  mov     [rbp+60h+var_DF], 1
0x140004266  mov     rcx, [rbx+130h]
0x14000426d  lea     r8, [rbp+60h+arg_10]
0x140004274  add     rcx, 8
0x140004278  mov     [rbp+60h+arg_10], 0
0x140004282  mov     edx, 7
0x140004287  call    cs:__imp_MmIsFileSectionActive
0x14000428e  nop     dword ptr [rax+rax+00h]
0x140004293  cmp     [rbp+60h+arg_10], 0
0x14000429a  jz      short loc_1400042BB
0x14000429c  mov     rcx, [rbx+130h]
0x1400042a3  add     rcx, 8; SectionPointer
0x1400042a7  call    cs:__imp_MmDoesFileHaveUserWritableReferences
0x1400042ae  nop     dword ptr [rax+rax+00h]
0x1400042b3  test    eax, eax
0x1400042b5  jz      short loc_1400042BB
0x1400042b7  mov     al, 1
0x1400042b9  jmp     short loc_1400042BD
0x1400042bb  xor     al, al
0x1400042bd  mov     esi, r14d
0x1400042c0  or      esi, 1
0x1400042c3  test    al, al
0x1400042c5  cmovz   esi, r14d
0x1400042c9  test    r15, r15
0x1400042cc  jz      short loc_14000432E
0x1400042ce  test    rdi, rdi
0x1400042d1  jz      short loc_1400042DE
0x1400042d3  cmp     r15, rdi
0x1400042d6  jz      short loc_14000432E
0x1400042d8  cmp     r15, [rdi+20h]
0x1400042dc  jz      short loc_14000432E
0x1400042de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042e5  lea     r14, WPP_GLOBAL_Control
0x1400042ec  cmp     rcx, r14
0x1400042ef  jz      loc_140004A12
0x1400042f5  test    dword ptr [rcx+2Ch], 200h
0x1400042fc  jz      loc_140004A12
0x140004302  cmp     byte ptr [rcx+29h], 4
0x140004306  jb      loc_140004A12
0x14000430c  mov     rcx, [rcx+18h]
0x140004310  lea     r8, WPP_4aafbbf870a73d89198003f1abc844b5_Traceguids
0x140004317  mov     edx, 0Ah
0x14000431c  mov     qword ptr [rsp+160h+IrpMajorCode], r15
0x140004321  mov     r9, rbx
0x140004324  call    WPP_SF_qq
0x140004329  jmp     loc_140004A12
0x14000432e  mov     r9, [rbp+60h+arg_8]
0x140004332  lea     r14, WPP_GLOBAL_Control
0x140004339  mov     byte ptr [rbp+60h+arg_10], 58h ; 'X'
0x140004340  mov     [rbp+60h+var_E0], 58h ; 'X'
0x140004344  test    r9, r9
0x140004347  jz      loc_1400044CA
0x14000434d  cmp     [rbp+60h+var_DE], 0
0x140004351  jz      loc_1400044CA
0x140004357  mov     rcx, [r9+20h]
0x14000435b  mov     eax, esi
0x14000435d  mov     edx, [rbp+60h+var_C0]
0x140004360  or      eax, 1
0x140004363  or      edx, [rcx+78h]
0x140004366  test    dl, 2
0x140004369  cmovnz  esi, eax
0x14000436c  cmp     dword ptr [rcx+5Ch], 0
0x140004370  jle     loc_1400044CA
0x140004376  call    RxReconnectSrvOpen
0x14000437b  test    eax, eax
0x14000437d  js      loc_1400044CA
0x140004383  mov     r9, [rbp+60h+arg_8]
0x140004387  mov     rdx, [r9+20h]
0x14000438b  mov     [rbp+60h+var_D8], rdx
0x14000438f  test    byte ptr [rdx+78h], 2
0x140004393  setz    cl
0x140004396  test    sil, 1
0x14000439a  setnz   al
0x14000439d  test    al, cl
0x14000439f  jnz     loc_14000446A
0x1400043a5  mov     eax, [rdx+80h]
0x1400043ab  test    al, 8
0x1400043ad  jnz     loc_140004436
0x1400043b3  test    rdi, rdi
0x1400043b6  jz      short loc_14000441C
0x1400043b8  mov     rax, [rdi+20h]
0x1400043bc  mov     ecx, [rax+80h]
0x1400043c2  test    cl, 8
0x1400043c5  jnz     short loc_14000441C
0x1400043c7  cmp     [rbp+60h+var_DF], 0
0x1400043cb  mov     eax, [rbp+60h+var_C0]
0x1400043ce  mov     [rbp+60h+var_38], eax
0x1400043d1  movzx   eax, byte ptr [rbp+60h+var_BC]
0x1400043d5  mov     [rbp+60h+var_34], eax
0x1400043d8  mov     [rbp+60h+var_48], rdi
0x1400043dc  mov     [rbp+60h+var_40], 0
0x1400043e4  jnz     short loc_140004402
0x1400043e6  movzx   r8d, sil
0x1400043ea  lea     rdx, [rbp+60h+var_48]
0x1400043ee  and     r8b, 1
0x1400043f2  mov     rcx, r9
0x1400043f5  call    IsBetterPagingFO
0x1400043fa  test    al, al
0x1400043fc  jz      short loc_140004470
0x1400043fe  mov     rdx, [rbp+60h+var_D8]
0x140004402  mov     rax, [r9+30h]
0x140004406  mov     rcx, r9
0x140004409  mov     r9b, 58h ; 'X'
0x14000440c  mov     [rbp+60h+var_D0], rcx
0x140004410  movzx   r10d, r9b
0x140004414  xor     r8d, r8d
0x140004417  jmp     loc_1400047DC
0x14000441c  mov     rax, [r9+30h]
0x140004420  mov     rcx, r9
0x140004423  mov     r9b, 58h ; 'X'
0x140004426  mov     [rbp+60h+var_D0], rcx
0x14000442a  movzx   r10d, r9b
0x14000442e  xor     r8d, r8d
0x140004431  jmp     loc_1400047D8
0x140004436  test    rdi, rdi
0x140004439  jz      short loc_140004453
0x14000443b  cmp     [rbp+60h+var_DF], 0
0x14000443f  jnz     short loc_140004453
0x140004441  test    byte ptr [rbp+60h+var_C0], 2
0x140004445  setz    cl
0x140004448  test    sil, 1
0x14000444c  setnz   al
0x14000444f  test    al, cl
0x140004451  jz      short loc_140004470
0x140004453  mov     rax, [r9+30h]
0x140004457  mov     rcx, r9
0x14000445a  mov     r9b, 58h ; 'X'
0x14000445d  mov     [rbp+60h+var_D0], rcx
0x140004461  movzx   r10d, r9b
0x140004465  jmp     loc_1400047D2
0x14000446a  cmp     [rbp+60h+var_DF], 0
0x14000446e  jnz     short loc_1400044CA
0x140004470  mov     rcx, cs:WPP_GLOBAL_Control
0x140004477  cmp     rcx, r14
0x14000447a  jz      short loc_1400044A8
0x14000447c  test    dword ptr [rcx+2Ch], 200h
0x140004483  jz      short loc_1400044A8
0x140004485  cmp     byte ptr [rcx+29h], 2
0x140004489  jb      short loc_1400044A8
0x14000448b  mov     rcx, [rcx+18h]
0x14000448f  lea     r8, WPP_4aafbbf870a73d89198003f1abc844b5_Traceguids
0x140004496  mov     edx, 0Bh
0x14000449b  mov     qword ptr [rsp+160h+IrpMajorCode], rbx
0x1400044a0  mov     r9, rdi
0x1400044a3  call    WPP_SF_qq
0x1400044a8  test    sil, 4
0x1400044ac  jz      loc_140004A0D
0x1400044b2  mov     rdx, [rdi+20h]
0x1400044b6  mov     r9b, 58h ; 'X'
0x1400044b9  mov     rsi, [rdi+30h]
0x1400044bd  movzx   r10d, r9b
0x1400044c1  mov     [rbp+60h+var_D8], rdx
0x1400044c5  jmp     loc_1400048C3
0x1400044ca  lea     rdx, [rbx+108h]
0x1400044d1  mov     r8d, 0EBAAh
0x1400044d7  mov     [rbp+60h+var_C8], rdx
0x1400044db  mov     rax, rdx
0x1400044de  mov     rax, [rax]
0x1400044e1  cmp     rax, rdx
0x1400044e4  jz      loc_14000473C
0x1400044ea  lea     rcx, [rax-88h]
0x1400044f1  cmp     [rcx], r8w
0x1400044f5  jz      short loc_1400044DE
0x1400044f7  test    rcx, rcx
0x1400044fa  jz      loc_14000473C
0x140004500  movzx   r14d, [rbp+60h+var_DF]
0x140004505  mov     rbx, rcx
0x140004508  mov     rdi, [rbp+60h+arg_8]
0x14000450c  cmp     rbx, r15
0x14000450f  jz      loc_140004708
0x140004515  mov     eax, [rbx+78h]
0x140004518  test    al, 1
0x14000451a  jz      loc_140004708
0x140004520  test    sil, 1
0x140004524  jz      short loc_14000452E
0x140004526  test    al, 2
0x140004528  jz      loc_140004708
0x14000452e  test    dword ptr [rbx+48h], 40Ch
0x140004535  jnz     loc_140004708
0x14000453b  cmp     dword ptr [rbx+5Ch], 0
0x14000453f  jz      loc_140004708
0x140004545  mov     rcx, rbx
0x140004548  call    RxReconnectSrvOpen
0x14000454d  mov     r8d, 0EBAAh
0x140004553  test    eax, eax
0x140004555  js      loc_140004704
0x14000455b  lea     rcx, [rbx+0B8h]
0x140004562  mov     [rbp+60h+var_D8], rcx
0x140004566  mov     rax, rcx
0x140004569  mov     rax, [rax]
0x14000456c  cmp     rax, rcx
0x14000456f  jz      loc_140004704
0x140004575  lea     r9, [rax-70h]
0x140004579  mov     [rbp+60h+var_D0], r9
0x14000457d  cmp     [r9], r8w
0x140004581  jz      short loc_140004569
0x140004583  test    r9, r9
0x140004586  jz      loc_140004704
0x14000458c  nop     dword ptr [rax+00h]
0x140004590  cmp     r9, r15
0x140004593  jz      loc_1400046E1
0x140004599  mov     r8d, [r9+48h]
0x14000459d  test    r8d, 1000002h
0x1400045a4  jnz     loc_1400046DB
0x1400045aa  mov     r10, [r9+30h]
0x1400045ae  mov     [rbp+60h+var_B8], r10
0x1400045b2  test    r10, r10
0x1400045b5  jz      loc_1400046DB
0x1400045bb  cmp     r9, rdi
0x1400045be  jz      short loc_1400045CE
0x1400045c0  test    dword ptr [r10+50h], 40000h
0x1400045c8  jz      loc_1400046DB
0x1400045ce  mov     eax, [r10+50h]
0x1400045d2  bt      eax, 15h
0x1400045d6  jb      loc_1400046DB
0x1400045dc  and     eax, 8
0x1400045df  bt      r8d, 16h
0x1400045e4  jb      short loc_140004658
0x1400045e6  test    eax, eax
0x1400045e8  jnz     short loc_14000462B
0x1400045ea  mov     eax, [rbx+78h]
0x1400045ed  test    al, 6
0x1400045ef  jz      short loc_1400045FB
0x1400045f1  cmp     qword ptr [r10+30h], 0
0x1400045f6  jz      short loc_1400045FB
0x1400045f8  or      esi, 1
0x1400045fb  test    r14b, r14b
0x1400045fe  jnz     short loc_14000461C
0x140004600  movzx   r8d, sil
0x140004604  lea     rdx, [rbp+60h+Object]
0x140004608  and     r8b, 1
0x14000460c  mov     rcx, r9
0x14000460f  call    IsBetterPagingFO
0x140004614  test    al, al
0x140004616  jz      loc_1400046D7
0x14000461c  xor     r8d, r8d
0x14000461f  lea     rcx, [rbp+60h+Object]
0x140004623  mov     rdx, r9
0x140004626  jmp     loc_1400046CE
0x14000462b  test    r14b, r14b
  ... truncated ...
```
