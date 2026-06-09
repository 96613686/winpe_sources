# CClfsLogFcbPhysical::ReadLogBlock(_FILE_OBJECT *,_CLS_LSN const &,ulong,_CLFS_READ_BUFFER const &,ulong,IClfsRequestAsync *,ulong,_CLS_LSN &,ulong &)

- ea: `0x1400075d0`
- end: `0x140007f24`
- name: `?ReadLogBlock@CClfsLogFcbPhysical@@UEAAJPEAU_FILE_OBJECT@@AEBT_CLS_LSN@@KAEBU_CLFS_READ_BUFFER@@KPEAUIClfsRequestAsync@@KAEAT3@AEAK@Z`
- size: `2388`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, struct _FILE_OBJECT *@<rdx>, const union _CLS_LSN *@<r8>, unsigned int@<r9d>, const struct _CLFS_READ_BUFFER *, unsigned int, struct IClfsRequestAsync *, unsigned int, union _CLS_LSN *, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x140016190`

## callees

- `0x140003040`
- `0x140003530`
- `0x140005840`
- `0x14000593c`
- `0x140005f00`
- `0x1400075d0`
- `0x140008330`
- `0x140008394`
- `0x14000a990`
- `0x14000ab30`
- `0x14000c874`
- `0x14000d32c`
- `0x140010148`
- `0x140010548`
- `0x140017f20`
- `0x140018280`
- `0x140066e00`
- `0x140066e90`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140018e7a`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140018e7a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000777d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000777d`
- `ntoskrnl!KeBugCheckEx` at `0x140007c88`
- `ntoskrnl!KeBugCheckEx` at `0x140007c88`
- `ntoskrnl!CcCopyRead` at `0x140007bfb`
- `ntoskrnl!CcCopyRead` at `0x140007bfb`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::ReadLogBlock(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *a2,
        const union _CLS_LSN *a3,
        int a4,
        const struct _CLFS_READ_BUFFER *a5,
        unsigned int a6,
        struct IClfsRequestAsync *a7,
        char a8,
        union _CLS_LSN *a9,
        unsigned int *a10)
{
  CClfsLogFcbPhysical *v11; // r15
  CLFS_LSN v12; // r14
  ULONG v13; // ecx
  int v14; // r12d
  struct _CLFS_LOG_BLOCK_HEADER *Address; // rdi
  struct IClfsRequestAsync *v17; // rbx
  ULONGLONG v18; // rax
  char v19; // al
  union _CLS_LSN *v20; // rdx
  unsigned int *v21; // rax
  union _CLS_LSN v22; // rsi
  unsigned int v23; // edi
  unsigned int v24; // edx
  char v25; // al
  ULONG v26; // ebx
  char v27; // cl
  struct IClfsRequestAsync *v28; // rax
  char v29; // si
  LARGE_INTEGER v30; // rdi
  ULONG v31; // eax
  signed __int64 v32; // rax
  unsigned int v33; // esi
  unsigned int Information; // edi
  unsigned int v35; // eax
  __int16 v36; // r8
  _BYTE *v37; // r9
  unsigned int v38; // ecx
  unsigned int v39; // edi
  union _CLS_LSN *v40; // rdi
  BOOLEAN v41; // si
  unsigned int v42; // r9d
  struct _CLFS_LOG_BLOCK_HEADER *v43; // rdi
  unsigned __int8 Buffer; // [rsp+20h] [rbp-148h]
  BOOLEAN v45; // [rsp+40h] [rbp-128h]
  char v46; // [rsp+41h] [rbp-127h]
  unsigned int v47; // [rsp+48h] [rbp-120h]
  unsigned int v48; // [rsp+50h] [rbp-118h] BYREF
  int v49; // [rsp+54h] [rbp-114h]
  ULONG v50; // [rsp+58h] [rbp-110h]
  unsigned __int64 QuadPart; // [rsp+60h] [rbp-108h]
  unsigned int v52[2]; // [rsp+68h] [rbp-100h] BYREF
  ULONG v53; // [rsp+70h] [rbp-F8h]
  int v54; // [rsp+74h] [rbp-F4h]
  unsigned int v55; // [rsp+78h] [rbp-F0h] BYREF
  PVOID v56; // [rsp+80h] [rbp-E8h]
  union _CLS_LSN v57; // [rsp+88h] [rbp-E0h] BYREF
  LARGE_INTEGER FileOffset; // [rsp+90h] [rbp-D8h] BYREF
  ULONG v59; // [rsp+98h] [rbp-D0h]
  int v60; // [rsp+9Ch] [rbp-CCh]
  union _CLS_LSN v61; // [rsp+A0h] [rbp-C8h] BYREF
  ULONGLONG v62; // [rsp+A8h] [rbp-C0h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+B0h] [rbp-B8h] BYREF
  union _CLS_LSN *v64; // [rsp+C0h] [rbp-A8h]
  union _CLS_LSN *v65; // [rsp+C8h] [rbp-A0h]
  CClfsLogFcbPhysical *v66; // [rsp+D0h] [rbp-98h]
  unsigned int v67[2]; // [rsp+D8h] [rbp-90h]
  struct _CLFS_LOG_BLOCK_HEADER *v68; // [rsp+E0h] [rbp-88h]
  __int128 v69; // [rsp+E8h] [rbp-80h] BYREF
  __int64 v70; // [rsp+F8h] [rbp-70h]
  union _CLS_LSN v71; // [rsp+100h] [rbp-68h] BYREF
  signed __int64 v72; // [rsp+108h] [rbp-60h]
  union _CLS_LSN v73; // [rsp+110h] [rbp-58h] BYREF
  union _CLS_LSN v74; // [rsp+118h] [rbp-50h] BYREF
  union _CLS_LSN v75; // [rsp+120h] [rbp-48h] BYREF
  char v79; // [rsp+188h] [rbp+20h]

  v79 = a4;
  v11 = this;
  v12 = CLFS_LSN_INVALID;
  *(CLFS_LSN *)v52 = CLFS_LSN_INVALID;
  IoStatus.Pointer = 0;
  IoStatus.Information = 0;
  FileOffset.QuadPart = 0;
  v55 = 0;
  v48 = 0;
  v13 = *(_DWORD *)(*((_QWORD *)this + 89) + 144LL);
  v53 = v13;
  v59 = v13;
  if ( v13 - 1 > 0xFFF || (v13 & 0x1FF) != 0 || 0x1000 % v13 )
    return 3221225624LL;
  *(_QWORD *)v67 = a9;
  v66 = v11;
  v14 = 0;
  v49 = 0;
  v45 = 0;
  *a10 = 0;
  *a9 = CLFS_LSN_INVALID;
  v69 = *(_OWORD *)a5;
  v70 = *((_QWORD *)a5 + 2);
  if ( (unsigned int)(a4 - 1) > 1 )
    return 3221225659LL;
  Address = (struct _CLFS_LOG_BLOCK_HEADER *)_CLFS_READ_BUFFER::GetAddress(a5);
  v68 = Address;
  if ( !Address || (v56 = _CLFS_READ_BUFFER::GetAddress((_CLFS_READ_BUFFER *)&v69)) == 0 )
  {
    v14 = -1073741670;
    goto LABEL_8;
  }
  v54 = a8 & 1;
  v60 = v54;
  if ( (_BYTE)v54
    || a2->PrivateCacheMap
    || (v14 = (**(__int64 (__fastcall ***)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, CClfsLogFcbPhysical *))v11)(
                v11,
                a2,
                v11),
        v14 >= 0) )
  {
    if ( !CClfsLogFcbCommon::IsMainLocked(v11) )
      v45 = ExAcquireResourceSharedLite((PERESOURCE)((char *)v11 + 200), 1u);
    if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v11 + 312LL))(v11) && (a8 & 8) != 0 )
    {
      v14 = -1072037858;
      goto LABEL_8;
    }
    if ( (*((_DWORD *)v11 + 91) & 0x1000) != 0 )
    {
      v14 = -1072037845;
      CClfsLogFcbCommon::SetInvalidLogTag(v11, 0xFu, -1072037845);
      goto LABEL_8;
    }
    v18 = *(_QWORD *)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, ULONGLONG *))(*(_QWORD *)v11 + 352LL))(v11, &v62);
    v62 = v18;
    if ( a3 )
    {
      if ( a3->ullOffset >= v18 )
      {
LABEL_28:
        v64 = (union _CLS_LSN *)((char *)v11 + 480);
        if ( !(unsigned __int8)operator>=(a3) )
        {
          v62 = (ULONGLONG)v20;
          v65 = v20;
          if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v11 + 312LL))(v11) )
          {
            v12 = **(CLFS_LSN **)&CClfsLogFcbPhysical::GetNextOwnerPageLsn(v11, &v61, (unsigned int)a3);
            *(CLFS_LSN *)v52 = v12;
          }
          v17 = a7;
          if ( a7 )
            v49 = (*(__int64 (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a7 + 16LL))(a7);
          v21 = a10;
          *a10 = 0;
          v22 = *a3;
          v57 = v22;
          v23 = a6;
          v47 = a6;
          while ( 1 )
          {
            v24 = *v21;
            if ( *v21 >= v23 )
              break;
            if ( v64 )
            {
              if ( v22.ullOffset >= v64->ullOffset )
                break;
              v25 = 1;
            }
            else
            {
              v25 = 0;
            }
            if ( !v25 )
              break;
            v26 = v23 - v24;
            v50 = v23 - v24;
            if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v11 + 312LL))(v11) )
            {
              QuadPart = *(_QWORD *)CClfsLogFcbPhysical::AddLsnOffset(v11, &v71, (unsigned int)&v57).ullOffset;
              if ( QuadPart > __PAIR64__(v52[1], v12.offset.idxRecord) )
              {
                v26 = (v12.offset.idxRecord & 0xFFFFFE00) - (v22.offset.idxRecord & 0xFFFFFE00);
                v50 = v26;
              }
            }
            if ( v26 % v53 )
            {
              v14 = -1073741811;
              goto LABEL_8;
            }
            v27 = 0;
            v46 = 0;
            if ( (v79 & 1) != 0 )
            {
              v46 = 0;
              if ( !*a10 )
              {
                v26 = v53;
                v50 = v53;
                v27 = 1;
                v46 = 1;
              }
            }
            if ( (_BYTE)v54 )
            {
              v28 = a7;
              if ( v27 )
                v28 = 0;
              v14 = CClfsLogFcbPhysical::ReadLog(
                      v11,
                      &v57,
                      (const struct _CLFS_READ_BUFFER *)&v69,
                      v26 >> 9,
                      3u,
                      v28,
                      a9,
                      &v48);
              v29 = v46;
              if ( v46 && a7 )
                (*(void (__fastcall **)(struct IClfsRequestAsync *, _QWORD, _QWORD))(*(_QWORD *)a7 + 88LL))(
                  a7,
                  (unsigned int)v14,
                  v48);
              v17 = a7;
            }
            else
            {
              if ( CLFS_LSN_INVALID.ullOffset == v22.ullOffset )
              {
                v30.QuadPart = -1;
              }
              else
              {
                LODWORD(QuadPart) = -1;
                if ( v11 != (CClfsLogFcbPhysical *)-1368LL )
                  LODWORD(QuadPart) = *((_DWORD *)v11 + 343);
                v31 = ClfsLsnBlockOffset((const CLFS_LSN *)v11 + 171);
                v30.QuadPart = (v22.offset.idxRecord & 0xFFFFFE00)
                             + *((_QWORD *)v11 + 87)
                             * (v57.offset.cidContainer - (unsigned __int64)(unsigned int)QuadPart)
                             - v31;
                v11 = this;
              }
              QuadPart = v30.QuadPart;
              FileOffset = v30;
              v32 = CClfsLogFcbPhysical::LsnToCacheOffset(v11, v65);
              if ( (QuadPart & 0x8000000000000000uLL) != 0LL || v32 < 0 )
                goto LABEL_67;
              if ( v32 >= v30.QuadPart + v26 )
              {
                v33 = v47;
              }
              else
              {
                v26 = v32 - v30.LowPart;
                v72 = v32 - v30.QuadPart;
                if ( (unsigned __int64)(v32 - v30.QuadPart) >> 32 )
                  goto LABEL_67;
                v50 = v32 - v30.LowPart;
                v33 = v47;
                memset((char *)v56 + v26, 0, v47 - *a10 - v26);
                v30 = FileOffset;
              }
              v61.ullOffset = 0;
              if ( v30.QuadPart < 0
                || v33 - *a10 < v26
                || (int)RtlLongLongAdd(v30.QuadPart, v26, (__int64 *)&v61) < 0
                || (__int64)v61.ullOffset > *((_QWORD *)v66 + 10) )
              {
LABEL_67:
                v14 = -1072037875;
                goto LABEL_8;
              }
              if ( CcCopyRead(a2, &FileOffset, v26, 1u, v56, &IoStatus) )
              {
                if ( IoStatus.Status )
                  KeBugCheckEx(0xC1F5u, 0x3Eu, IoStatus.Status, (ULONG_PTR)v11, 0);
                v14 = 0;
                Information = IoStatus.Information;
                v48 = IoStatus.Information;
                *a9 = **(union _CLS_LSN **)&CClfsLogFcbPhysical::AddLsnOffset(v11, &v73, (unsigned int)&v57);
                v17 = a7;
                if ( a7 )
                  (*(void (__fastcall **)(struct IClfsRequestAsync *, _QWORD, _QWORD))(*(_QWORD *)a7 + 88LL))(
                    a7,
                    0,
                    Information);
              }
              else
              {
                v17 = a7;
              }
              v29 = v46;
            }
            if ( v14 == -1073741807 || v14 == -1072037869 )
            {
              v23 = v47;
              break;
            }
            if ( v29 )
            {
              if ( !v14 )
              {
                v35 = CClfsLogFcbPhysical::RawSectorAlign(v11, *((unsigned __int16 *)v56 + 2) << 9);
                if ( *v37 )
                {
                  if ( v36 )
                  {
                    v38 = v47;
                    if ( v35 < v47 )
                      v38 = v35;
                    v47 = v38;
                  }
                }
              }
            }
            v39 = v48;
            *a10 += v48;
            LODWORD(v70) = v39 + v70;
            v56 = (char *)v56 + v39;
            if ( v14 < 0 )
              goto LABEL_104;
            if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v11 + 312LL))(v11) )
            {
              v40 = *(union _CLS_LSN **)v67;
              if ( **(_QWORD **)v67 == v12.ullOffset )
              {
                *v40 = **(union _CLS_LSN **)&CClfsLogFcbPhysical::AddLsnOffset(v11, &v74, v67[0]);
                v12 = **(CLFS_LSN **)&CClfsLogFcbPhysical::AddLsnOffset(v11, &v75, (unsigned int)v52);
                *(CLFS_LSN *)v52 = v12;
              }
            }
            else
            {
              v40 = a9;
            }
            v22 = *v40;
            v57 = *v40;
            v23 = v47;
            v21 = a10;
          }
          v41 = v45;
          if ( v45 )
          {
            ClfsReleaseResourceLite((char *)v11 + 200);
            v41 = 0;
          }
          if ( !v17 && v14 >= 0 )
          {
            v42 = v23;
            v43 = v68;
            v14 = CClfsLogFcbPhysical::ValidateLogBlock(v11, a3, v68, v42, Buffer, 4, &v55);
            if ( v14 >= 0 )
              v14 = ClfsDecodeBlock(v43, *((unsigned __int16 *)v43 + 2), *((_BYTE *)v43 + 2), 4u, &v55);
          }
          goto LABEL_105;
        }
        if ( (a8 & 0x10) == 0 )
          ClfsCheckAndResetReadInProgress(Address, a6);
        v14 = -1073741807;
        goto LABEL_8;
      }
      v19 = 1;
    }
    else
    {
      v19 = 0;
    }
    if ( v19 )
    {
      if ( (a8 & 0x10) == 0 )
        ClfsCheckAndResetReadInProgress(Address, a6);
      v14 = -1072037869;
      goto LABEL_8;
    }
    goto LABEL_28;
  }
LABEL_8:
  v17 = a7;
LABEL_104:
  v41 = v45;
LABEL_105:
  if ( v41 )
    ClfsReleaseResourceLite((char *)v11 + 200);
  if ( v14 < 0 )
  {
    *a10 = 0;
    if ( v17 )
      (*(void (__fastcall **)(struct IClfsRequestAsync *, _QWORD, _QWORD))(*(_QWORD *)v17 + 88LL))(
        v17,
        (unsigned int)v14,
        0);
  }
  if ( v49 && (*(unsigned int (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)v17 + 24LL))(v17) && v14 >= 0 )
    return 259;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400075d0  mov     r11, rsp
0x1400075d3  mov     [r11+20h], r9d
0x1400075d7  mov     [r11+18h], r8
0x1400075db  mov     [r11+10h], rdx
0x1400075df  mov     [r11+8], rcx
0x1400075e3  push    rbx
0x1400075e4  push    rsi
0x1400075e5  push    rdi
0x1400075e6  push    r12
0x1400075e8  push    r13
0x1400075ea  push    r14
0x1400075ec  push    r15
0x1400075ee  sub     rsp, 130h
0x1400075f5  mov     rsi, r8
0x1400075f8  mov     r15, rcx
0x1400075fb  mov     r14, qword ptr cs:CLFS_LSN_INVALID
0x140007602  mov     qword ptr [rsp+168h+var_100], r14
0x140007607  xor     r13d, r13d
0x14000760a  mov     [r11-0B8h], r13
0x140007611  mov     [r11-0B0h], r13
0x140007618  mov     [r11-0D8h], r13
0x14000761f  mov     [rsp+168h+var_F0], r13d
0x140007624  mov     [rsp+168h+var_118], r13d
0x140007629  mov     rax, [rcx+2C8h]
0x140007630  mov     ecx, [rax+90h]
0x140007636  mov     [rsp+168h+var_F8], ecx
0x14000763a  mov     [rsp+168h+var_D0], ecx
0x140007641  lea     eax, [rcx-1]
0x140007644  cmp     eax, 0FFFh
0x140007649  ja      loc_140007F0B
0x14000764f  test    ecx, 1FFh
0x140007655  jnz     loc_140007F0B
0x14000765b  xor     edx, edx
0x14000765d  mov     eax, 1000h
0x140007662  div     ecx
0x140007664  test    edx, edx
0x140007666  jnz     loc_140007F0B
0x14000766c  mov     rcx, [rsp+168h+arg_40]
0x140007674  mov     qword ptr [rsp+168h+var_90], rcx
0x14000767c  mov     [rsp+168h+var_98], r15
0x140007684  mov     r12d, r13d
0x140007687  mov     [rsp+168h+var_124], r13d
0x14000768c  mov     [rsp+168h+var_114], r13d
0x140007691  mov     [rsp+168h+var_128], r13b
0x140007696  mov     rax, [rsp+168h+arg_48]
0x14000769e  mov     [rax], r13d
0x1400076a1  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400076a8  mov     [rcx], rax
0x1400076ab  mov     rcx, [rsp+168h+arg_20]; this
0x1400076b3  movups  xmm0, xmmword ptr [rcx]
0x1400076b6  movups  xmmword ptr [r11-80h], xmm0
0x1400076bb  movsd   xmm1, qword ptr [rcx+10h]
0x1400076c0  movsd   qword ptr [r11-70h], xmm1
0x1400076c6  lea     eax, [r9-1]
0x1400076ca  cmp     eax, 1
0x1400076cd  jbe     short loc_1400076D9
0x1400076cf  mov     eax, 0C00000BBh
0x1400076d4  jmp     loc_140007F10
0x1400076d9  call    ?GetAddress@_CLFS_READ_BUFFER@@QEBAPEAEXZ; _CLFS_READ_BUFFER::GetAddress(void)
0x1400076de  mov     rdi, rax
0x1400076e1  mov     [rsp+168h+var_88], rax
0x1400076e9  test    rax, rax
0x1400076ec  jnz     short loc_140007706
0x1400076ee  mov     r12d, 0C000009Ah
0x1400076f4  mov     [rsp+168h+var_124], r12d
0x1400076f9  mov     rbx, [rsp+168h+arg_30]
0x140007701  jmp     loc_140007EA0
0x140007706  lea     rcx, [rsp+168h+var_80]; this
0x14000770e  call    ?GetAddress@_CLFS_READ_BUFFER@@QEBAPEAEXZ; _CLFS_READ_BUFFER::GetAddress(void)
0x140007713  mov     [rsp+168h+var_E8], rax
0x14000771b  test    rax, rax
0x14000771e  jz      short loc_1400076EE
0x140007720  mov     ebx, dword ptr [rsp+168h+arg_38]
0x140007727  mov     eax, ebx
0x140007729  and     eax, 1
0x14000772c  mov     [rsp+168h+var_F4], eax
0x140007730  mov     [rsp+168h+var_CC], eax
0x140007737  test    al, al
0x140007739  jnz     short loc_140007768
0x14000773b  mov     rcx, [rsp+168h+FileObject]
0x140007743  cmp     [rcx+30h], r13
0x140007747  jnz     short loc_140007768
0x140007749  mov     rax, [r15]
0x14000774c  mov     rax, [rax]
0x14000774f  mov     r8, r15
0x140007752  mov     rdx, rcx
0x140007755  mov     rcx, r15
0x140007758  call    _guard_dispatch_icall
0x14000775d  mov     r12d, eax
0x140007760  mov     [rsp+168h+var_124], eax
0x140007764  test    eax, eax
0x140007766  js      short loc_1400076F9
0x140007768  mov     rcx, r15; this
0x14000776b  call    ?IsMainLocked@CClfsLogFcbCommon@@QEAAEXZ; CClfsLogFcbCommon::IsMainLocked(void)
0x140007770  test    al, al
0x140007772  jnz     short loc_14000778D
0x140007774  lea     rcx, [r15+0C8h]; Resource
0x14000777b  mov     dl, 1; Wait
0x14000777d  call    cs:__imp_ExAcquireResourceSharedLite
0x140007784  nop     dword ptr [rax+rax+00h]
0x140007789  mov     [rsp+168h+var_128], al
0x14000778d  mov     rcx, [r15]
0x140007790  mov     rax, [rcx+138h]
0x140007797  mov     rcx, r15
0x14000779a  call    _guard_dispatch_icall
0x14000779f  test    al, al
0x1400077a1  jz      short loc_1400077B3
0x1400077a3  test    bl, 8
0x1400077a6  jz      short loc_1400077B3
0x1400077a8  mov     r12d, 0C01A001Eh
0x1400077ae  jmp     loc_1400076F4
0x1400077b3  mov     eax, [r15+16Ch]
0x1400077ba  mov     rcx, r15; this
0x1400077bd  bt      eax, 0Ch
0x1400077c1  jnb     short loc_1400077E0
0x1400077c3  mov     r12d, 0C01A002Bh
0x1400077c9  mov     [rsp+168h+var_124], r12d
0x1400077ce  mov     r8d, r12d; int
0x1400077d1  mov     edx, 0Fh; unsigned int
0x1400077d6  call    ?SetInvalidLogTag@CClfsLogFcbCommon@@QEAAXKJ@Z; CClfsLogFcbCommon::SetInvalidLogTag(ulong,long)
0x1400077db  jmp     loc_1400076F9
0x1400077e0  mov     rax, [r15]
0x1400077e3  mov     rax, [rax+160h]
0x1400077ea  lea     rdx, [rsp+168h+var_C0]
0x1400077f2  call    _guard_dispatch_icall
0x1400077f7  mov     rax, [rax]
0x1400077fa  mov     [rsp+168h+var_C0], rax
0x140007802  test    rsi, rsi
0x140007805  jz      short loc_14000781D
0x140007807  mov     rcx, rax
0x14000780a  shr     rcx, 20h
0x14000780e  cmp     [rsi+4], ecx
0x140007811  ja      short loc_140007843
0x140007813  jnz     short loc_140007819
0x140007815  cmp     [rsi], eax
0x140007817  jnb     short loc_140007843
0x140007819  mov     al, 1
0x14000781b  jmp     short loc_140007820
0x14000781d  mov     al, r13b
0x140007820  test    al, al
0x140007822  jz      short loc_140007843
0x140007824  test    bl, 10h
0x140007827  jnz     short loc_140007838
0x140007829  mov     edx, [rsp+168h+arg_28]
0x140007830  mov     rcx, rdi
0x140007833  call    ClfsCheckAndResetReadInProgress
0x140007838  mov     r12d, 0C01A0013h
0x14000783e  jmp     loc_1400076F4
0x140007843  lea     rdx, [r15+1E0h]
0x14000784a  mov     [rsp+168h+var_A8], rdx
0x140007852  mov     rcx, rsi
0x140007855  call    ??P@YAEAEBT_CLS_LSN@@0@Z; operator>=(_CLS_LSN const &,_CLS_LSN const &)
0x14000785a  test    al, al
0x14000785c  jz      short loc_14000787D
0x14000785e  test    bl, 10h
0x140007861  jnz     short loc_140007872
0x140007863  mov     edx, [rsp+168h+arg_28]
0x14000786a  mov     rcx, rdi
0x14000786d  call    ClfsCheckAndResetReadInProgress
0x140007872  mov     r12d, 0C0000011h
0x140007878  jmp     loc_1400076F4
0x14000787d  mov     [rsp+168h+var_C0], rdx
0x140007885  mov     [rsp+168h+var_A0], rdx
0x14000788d  mov     rax, [r15]
0x140007890  mov     rax, [rax+138h]
0x140007897  mov     rcx, r15
0x14000789a  call    _guard_dispatch_icall
0x14000789f  test    al, al
0x1400078a1  jz      short loc_1400078C1
0x1400078a3  xor     r9d, r9d
0x1400078a6  mov     r8, rsi; unsigned int
0x1400078a9  lea     rdx, [rsp+168h+var_C8]; union _CLS_LSN *
0x1400078b1  mov     rcx, r15; this
0x1400078b4  call    ?GetNextOwnerPageLsn@CClfsLogFcbPhysical@@AEAA?AT_CLS_LSN@@AEBT2@K@Z; CClfsLogFcbPhysical::GetNextOwnerPageLsn(_CLS_LSN const &,ulong)
0x1400078b9  mov     r14, [rax]
0x1400078bc  mov     qword ptr [rsp+168h+var_100], r14
0x1400078c1  mov     rbx, [rsp+168h+arg_30]
0x1400078c9  test    rbx, rbx
0x1400078cc  jz      short loc_1400078E1
0x1400078ce  mov     rax, [rbx]
0x1400078d1  mov     rax, [rax+10h]
0x1400078d5  mov     rcx, rbx
0x1400078d8  call    _guard_dispatch_icall
0x1400078dd  mov     [rsp+168h+var_114], eax
0x1400078e1  mov     rax, [rsp+168h+arg_48]
0x1400078e9  mov     [rax], r13d
0x1400078ec  mov     rsi, [rsi]
0x1400078ef  mov     qword ptr [rsp+168h+var_E0], rsi
0x1400078f7  mov     edi, [rsp+168h+arg_28]
0x1400078fe  mov     [rsp+168h+var_120], edi
0x140007902  mov     rcx, rsi
0x140007905  mov     edx, [rax]
0x140007907  cmp     edx, edi
0x140007909  jnb     loc_140007E1D
0x14000790f  mov     r8, [rsp+168h+var_A8]
0x140007917  test    r8, r8
0x14000791a  jz      short loc_14000793B
0x14000791c  mov     eax, [r8+4]
0x140007920  shr     rcx, 20h
0x140007924  cmp     ecx, eax
0x140007926  ja      loc_140007E1D
0x14000792c  jnz     short loc_140007937
0x14000792e  cmp     esi, [r8]
0x140007931  jnb     loc_140007E1D
0x140007937  mov     al, 1
0x140007939  jmp     short loc_14000793E
0x14000793b  mov     al, r13b
0x14000793e  test    al, al
0x140007940  jz      loc_140007E1D
0x140007946  mov     ebx, edi
0x140007948  sub     ebx, edx
0x14000794a  mov     [rsp+168h+var_110], ebx
0x14000794e  mov     rax, [r15]
0x140007951  mov     rax, [rax+138h]
0x140007958  mov     rcx, r15
0x14000795b  call    _guard_dispatch_icall
0x140007960  test    al, al
0x140007962  jz      short loc_1400079AF
0x140007964  mov     r9d, ebx
0x140007967  lea     r8, [rsp+168h+var_E0]; unsigned int
0x14000796f  lea     rdx, [rsp+168h+var_68]; union _CLS_LSN *
0x140007977  mov     rcx, r15; this
0x14000797a  call    ?AddLsnOffset@CClfsLogFcbPhysical@@AEAA?AT_CLS_LSN@@AEBT2@K@Z; CClfsLogFcbPhysical::AddLsnOffset(_CLS_LSN const &,ulong)
0x14000797f  mov     rax, [rax]
0x140007982  mov     [rsp+168h+var_108], rax
0x140007987  mov     rcx, rax
0x14000798a  shr     rcx, 20h
0x14000798e  cmp     ecx, [rsp+168h+var_100+4]
0x140007992  jb      short loc_1400079AF
0x140007994  jnz     short loc_14000799B
0x140007996  cmp     eax, r14d
0x140007999  jbe     short loc_1400079AF
0x14000799b  mov     ebx, r14d
0x14000799e  mov     ecx, 0FFFFFE00h
0x1400079a3  and     ebx, ecx
0x1400079a5  mov     eax, esi
0x1400079a7  and     eax, ecx
0x1400079a9  sub     ebx, eax
0x1400079ab  mov     [rsp+168h+var_110], ebx
0x1400079af  xor     edx, edx
0x1400079b1  mov     eax, ebx
0x1400079b3  mov     r8d, [rsp+168h+var_F8]
0x1400079b8  div     r8d
0x1400079bb  test    edx, edx
0x1400079bd  jz      short loc_1400079CA
0x1400079bf  mov     r12d, 0C000000Dh
0x1400079c5  jmp     loc_1400076F4
0x1400079ca  mov     cl, r13b
0x1400079cd  mov     [rsp+168h+var_127], cl
0x1400079d1  test    [rsp+168h+arg_18], 1
0x1400079d9  jz      short loc_1400079F9
0x1400079db  mov     [rsp+168h+var_127], cl
0x1400079df  mov     rax, [rsp+168h+arg_48]
0x1400079e7  cmp     [rax], r13d
0x1400079ea  jnz     short loc_1400079F9
0x1400079ec  mov     ebx, r8d
0x1400079ef  mov     [rsp+168h+var_110], ebx
0x1400079f3  mov     cl, 1
0x1400079f5  mov     [rsp+168h+var_127], cl
0x1400079f9  cmp     byte ptr [rsp+168h+var_F4], r13b
0x1400079fe  jz      loc_140007A8C
0x140007a04  mov     rdi, [rsp+168h+arg_30]
0x140007a0c  mov     rax, rdi
0x140007a0f  test    cl, cl
0x140007a11  cmovnz  rax, r13
0x140007a15  shr     ebx, 9
0x140007a18  lea     rcx, [rsp+168h+var_118]
0x140007a1d  mov     [rsp+168h+var_130], rcx; unsigned int *
0x140007a22  mov     rdx, [rsp+168h+arg_40]
0x140007a2a  mov     [rsp+168h+var_138], rdx; union _CLS_LSN *
0x140007a2f  mov     [rsp+168h+IoStatus], rax; struct IClfsRequestAsync *
0x140007a34  mov     dword ptr [rsp+168h+Buffer], 3; unsigned int
0x140007a3c  mov     r9d, ebx; unsigned int
0x140007a3f  lea     r8, [rsp+168h+var_80]; struct _CLFS_READ_BUFFER *
0x140007a47  lea     rdx, [rsp+168h+var_E0]; union _CLS_LSN *
0x140007a4f  mov     rcx, r15; this
0x140007a52  call    ?ReadLog@CClfsLogFcbPhysical@@AEAAJAEBT_CLS_LSN@@AEBU_CLFS_READ_BUFFER@@KKPEAUIClfsRequestAsync@@AEAT2@AEAK@Z; CClfsLogFcbPhysical::ReadLog(_CLS_LSN const &,_CLFS_READ_BUFFER const &,ulong,ulong,IClfsRequestAsync *,_CLS_LSN &,ulong &)
0x140007a57  mov     r12d, eax
0x140007a5a  mov     [rsp+168h+var_124], eax
0x140007a5e  mov     sil, [rsp+168h+var_127]
0x140007a63  test    sil, sil
0x140007a66  jz      short loc_140007A84
0x140007a68  test    rdi, rdi
0x140007a6b  jz      short loc_140007A84
0x140007a6d  mov     rax, [rdi]
0x140007a70  mov     rax, [rax+58h]
0x140007a74  mov     r8d, [rsp+168h+var_118]
0x140007a79  mov     edx, r12d
0x140007a7c  mov     rcx, rdi
0x140007a7f  call    _guard_dispatch_icall
0x140007a84  mov     rbx, rdi
0x140007a87  jmp     loc_140007D00
0x140007a8c  cmp     qword ptr cs:CLFS_LSN_INVALID, rsi
0x140007a93  jnz     short loc_140007A9B
0x140007a95  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140007a99  jmp     short loc_140007AE9
0x140007a9b  lea     rcx, [r15+558h]; plsn
0x140007aa2  mov     dword ptr [rsp+168h+var_108], 0FFFFFFFFh
0x140007aaa  test    rcx, rcx
0x140007aad  jz      short loc_140007AB6
  ... truncated ...
```
