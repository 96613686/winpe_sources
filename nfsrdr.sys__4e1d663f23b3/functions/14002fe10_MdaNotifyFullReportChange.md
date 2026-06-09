# MdaNotifyFullReportChange

- ea: `0x14002fe10`
- end: `0x14003062f`
- name: `MdaNotifyFullReportChange`
- size: `2079`
- prototype: `PDEVICE_OBJECT *__fastcall(PFAST_MUTEX FastMutex, _QWORD **, __int64, unsigned __int16, __int16, int, int, int)`
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001add0`
- `0x14001bbbc`
- `0x14001c694`
- `0x14001d6b0`
- `0x140030ef0`
- `0x1400316d0`

## callees

- `0x1400159cc`
- `0x14002f954`
- `0x14002fe10`
- `0x14003083c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003004f`
- `ntoskrnl!RtlCompareMemory` at `0x14003004f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002ff3b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002ff3b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400305de`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003b777`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400305de`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003b777`
- `ntoskrnl!RtlxOemStringToUnicodeSize` at `0x1400302c9`
- `ntoskrnl!RtlxOemStringToUnicodeSize` at `0x140030325`
- `ntoskrnl!RtlxOemStringToUnicodeSize` at `0x1400302c9`
- `ntoskrnl!RtlxOemStringToUnicodeSize` at `0x140030325`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030421`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030421`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003054e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003054e`
- `ntoskrnl!ExAllocatePool2` at `0x14003045c`
- `ntoskrnl!ExAllocatePool2` at `0x14003045c`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall MdaNotifyFullReportChange(
        PFAST_MUTEX FastMutex,
        _QWORD **a2,
        __int64 a3,
        unsigned __int16 a4,
        __int16 a5,
        int a6,
        int a7,
        int a8)
{
  PDEVICE_OBJECT *result; // rax
  unsigned __int16 v9; // si
  _QWORD **v10; // r13
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  unsigned __int16 *v14; // r9
  struct _KTHREAD *CurrentThread; // rdi
  _QWORD *v16; // r14
  _QWORD *v17; // rdi
  unsigned __int16 v18; // ax
  __int16 v19; // cx
  SIZE_T v20; // rdx
  unsigned __int64 v21; // rax
  __int16 *v22; // r12
  char v23; // r15
  __int64 v24; // rcx
  bool v25; // zf
  SIZE_T v26; // rax
  __int64 v27; // r9
  __int16 v28; // r8
  unsigned int v29; // r13d
  _QWORD *v30; // rcx
  __int16 v31; // r8
  __int64 *v32; // r14
  __int64 v33; // rdx
  USHORT v34; // dx
  __int16 v35; // ax
  char v36; // r10
  unsigned int v37; // edx
  int v38; // r9d
  unsigned int i; // r8d
  __int64 v40; // r8
  int v41; // esi
  ULONG Length; // eax
  unsigned int v43; // esi
  unsigned int *v44; // r15
  unsigned int v45; // r8d
  unsigned int v46; // r12d
  _DWORD *Pool2; // rax
  _QWORD *v48; // r14
  __int64 v49; // r9
  _DWORD *v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rcx
  void *v53; // rcx
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-108h]
  _QWORD *v55; // [rsp+50h] [rbp-D8h]
  unsigned int *v56; // [rsp+58h] [rbp-D0h]
  __int128 *v57; // [rsp+60h] [rbp-C8h]
  __int64 v58; // [rsp+70h] [rbp-B8h]
  STRING v59; // [rsp+78h] [rbp-B0h] BYREF
  STRING OemString; // [rsp+88h] [rbp-A0h] BYREF
  __int64 v61; // [rsp+98h] [rbp-90h]
  __int64 v62; // [rsp+A0h] [rbp-88h]
  _QWORD *v63; // [rsp+A8h] [rbp-80h]
  __int128 v64; // [rsp+B0h] [rbp-78h] BYREF
  _QWORD *v65; // [rsp+C0h] [rbp-68h]
  _QWORD *v66; // [rsp+C8h] [rbp-60h]
  _QWORD *v67; // [rsp+D0h] [rbp-58h]
  _QWORD *v68; // [rsp+D8h] [rbp-50h]
  PVOID *p_Owner; // [rsp+E0h] [rbp-48h]
  PFAST_MUTEX v70; // [rsp+E8h] [rbp-40h]
  _UNKNOWN *retaddr; // [rsp+128h] [rbp+0h] BYREF
  __int64 v74; // [rsp+140h] [rbp+18h]
  unsigned __int16 v76; // [rsp+150h] [rbp+28h]
  unsigned int v77; // [rsp+158h] [rbp+30h]

  result = (PDEVICE_OBJECT *)&retaddr;
  v74 = a3;
  v9 = a4;
  v10 = a2;
  v64 = 0;
  v59 = 0;
  OemString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
  {
    result = (PDEVICE_OBJECT *)WPP_SF_(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 17,
                                 WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
    a3 = v74;
  }
  if ( !v9 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    {
      v13 = 18;
      return (PDEVICE_OBJECT *)WPP_SF_(v12->AttachedDevice, v13, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
    }
    return result;
  }
  if ( v9 > *(_WORD *)a3 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    {
      v13 = 19;
      return (PDEVICE_OBJECT *)WPP_SF_(v12->AttachedDevice, v13, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
    }
    return result;
  }
  v58 = 0;
  v59.Buffer = 0;
  v76 = 0;
  v59.Length = 0;
  if ( !FastMutex )
    return result;
  v61 = a3;
  v14 = 0;
  v57 = 0;
  CurrentThread = KeGetCurrentThread();
  v70 = FastMutex + 1;
  if ( CurrentThread != *(struct _KTHREAD **)&FastMutex[1].Count )
  {
    ExAcquireFastMutexUnsafe(FastMutex);
    *(_QWORD *)&FastMutex[1].Count = CurrentThread;
    v14 = 0;
    a3 = v74;
  }
  p_Owner = &FastMutex[1].Owner;
  ++LODWORD(FastMutex[1].Owner);
  v16 = *v10;
  while ( 1 )
  {
    v63 = v16;
    v55 = v16;
    if ( v16 == v10 )
      break;
    v17 = v16 - 70;
    v65 = v16 - 70;
    if ( *((_WORD *)v16 - 268) && (*((_DWORD *)v17 + 149) & a7) != 0 )
    {
      if ( !v14 )
      {
        *((_QWORD *)&v64 + 1) = *(_QWORD *)(a3 + 8);
        v18 = v9;
        LOWORD(v64) = v9;
        v19 = *((unsigned __int8 *)v17 + 594);
        if ( v9 != v19 )
        {
          v18 = v9 - v19;
          LOWORD(v64) = v9 - v19;
        }
        WORD1(v64) = v18;
        v14 = (unsigned __int16 *)&v64;
        v57 = &v64;
      }
      v20 = *((unsigned __int16 *)v17 + 12);
      v21 = *v14;
      if ( (unsigned __int16)v20 <= (unsigned __int16)v21 )
      {
        v22 = (__int16 *)(v17 + 74);
        if ( (_WORD)v20 == (_WORD)v21 )
        {
          v23 = 1;
          goto LABEL_33;
        }
        if ( (*v22 & 1) == 0 )
          goto LABEL_108;
        if ( (*v22 & 0x10) == 0 )
        {
          v24 = *((unsigned __int16 *)v17 + 12);
          if ( *((_BYTE *)v17 + 594) == 1 )
          {
            v25 = *(_BYTE *)(v24 + *((_QWORD *)v14 + 1)) == 92;
LABEL_31:
            if ( !v25 )
              goto LABEL_108;
          }
          else if ( v21 >= v24 + 2 )
          {
            v25 = *(_WORD *)(v20 + *((_QWORD *)v14 + 1)) == 92;
            goto LABEL_31;
          }
        }
        v23 = 0;
LABEL_33:
        v26 = RtlCompareMemory((const void *)v17[4], *((const void **)v14 + 1), v20);
        v27 = *((unsigned __int16 *)v17 + 12);
        if ( v26 != v27 )
          goto LABEL_108;
        v66 = v17 + 74;
        v28 = *v22;
        if ( (*v22 & 2) != 0 )
          goto LABEL_106;
        v29 = *((_DWORD *)v17 + 154);
        if ( !v29 )
          goto LABEL_105;
        v62 = 0;
        v56 = (unsigned int *)v17 + 155;
        if ( *((_DWORD *)v17 + 155) )
        {
          v29 = *((_DWORD *)v17 + 155);
        }
        else
        {
          v30 = (_QWORD *)v17[72];
          if ( v30 != v17 + 72 )
          {
            v62 = *(v30 - 1);
            v29 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v62 + 40) + 184LL) + 8LL);
          }
        }
        if ( v23 )
        {
          OemString.Length = 0;
          v34 = 0;
          v32 = (__int64 *)(v61 + 8);
        }
        else
        {
          v31 = v28 & 0x10;
          if ( v31 )
          {
            v32 = (__int64 *)(v61 + 8);
          }
          else
          {
            v32 = (__int64 *)(v74 + 8);
            v33 = *((_QWORD *)v57 + 1);
            if ( v33 == *(_QWORD *)(v74 + 8) )
            {
              OemString.Buffer = (PCHAR)(v33 + v27 + *((unsigned __int8 *)v17 + 594));
              v34 = *(_WORD *)v57 - *((unsigned __int8 *)v17 + 594) - *((_WORD *)v17 + 12);
              goto LABEL_65;
            }
          }
          if ( !v58 )
          {
            v58 = *v32;
            v76 = v9;
            v35 = *((unsigned __int8 *)v17 + 594);
            if ( v9 != v35 )
              v76 = v9 - v35;
          }
          v36 = 0;
          v37 = 0;
          if ( v31 )
          {
            v40 = v58;
          }
          else
          {
            v38 = 1;
            for ( i = 0; i < *((unsigned __int16 *)v17 + 12) >> 1; ++i )
            {
              if ( *(_WORD *)(v17[4] + 2LL * i) == 92 )
                ++v38;
            }
            v40 = v58;
            while ( v37 < v76 >> 1 )
            {
              if ( *(_WORD *)(v58 + 2LL * v37) == 92 && (unsigned __int8)++v36 == v38 )
                break;
              ++v37;
            }
            v37 *= *((unsigned __int8 *)v17 + 594);
          }
          v77 = v37 + *((unsigned __int8 *)v17 + 594);
          OemString.Buffer = (PCHAR)(v40 + v77);
          v34 = v76 - v77;
LABEL_65:
          OemString.Length = v34;
          OemString.MaximumLength = v34;
        }
        v41 = 12;
        if ( !v23 )
        {
          if ( *((_BYTE *)v17 + 594) == 1 )
            v41 = RtlxOemStringToUnicodeSize(&OemString) + 12;
          else
            v41 = v34 + 14;
        }
        if ( !v59.Buffer )
        {
          v59.Buffer = (PCHAR)(*v32 + a4);
          v59.Length = *(_WORD *)v74 - a4;
          v59.MaximumLength = v59.Length;
        }
        if ( *((_BYTE *)v17 + 594) == 1 )
          Length = RtlxOemStringToUnicodeSize(&v59) - 2;
        else
          Length = v59.Length;
        v43 = Length + v41;
        v44 = (unsigned int *)(v17 + 78);
        v67 = v17 + 78;
        if ( v43 <= v29 )
        {
          v45 = (*v44 + 3) & 0xFFFFFFFC;
          v46 = v45 + v43;
          if ( v45 + v43 <= v29 )
          {
            Pool2 = 0;
            v48 = v17 + 76;
            v68 = v17 + 76;
            v49 = v17[76];
            if ( v49 )
            {
              *(_DWORD *)(*((unsigned int *)v17 + 157) + v49) = v45 - *((_DWORD *)v17 + 157);
              *((_DWORD *)v17 + 157) = v45;
              v50 = (_DWORD *)*v48;
              Pool2 = (_DWORD *)(*v48 + v45);
              goto LABEL_89;
            }
            if ( !v62 )
              goto LABEL_88;
            v51 = *(_QWORD *)(v62 + 40);
            v50 = *(_DWORD **)(v51 + 24);
            if ( v50 )
            {
              Pool2 = *(_DWORD **)(v51 + 24);
              *v48 = v50;
              *v56 = v29;
              goto LABEL_89;
            }
            v52 = *(_QWORD *)(v51 + 8);
            if ( v52 )
            {
              if ( (*(_BYTE *)(v52 + 10) & 5) != 0 )
                Pool2 = *(_DWORD **)(v52 + 24);
              else
                Pool2 = MmMapLockedPagesSpecifyCache((PMDL)v52, 0, MmCached, 0, 0, 0x40000010u);
              *v48 = Pool2;
              *v56 = v29;
              v50 = Pool2;
            }
            else
            {
LABEL_88:
              v50 = (_DWORD *)v17[76];
            }
LABEL_89:
            if ( !v50 )
            {
              Pool2 = (_DWORD *)ExAllocatePool2(258, v29, 911369806);
              *v48 = Pool2;
              v17[75] = Pool2;
              *v56 = v29;
            }
            if ( Pool2 )
            {
              if ( MdaNotifyUpdateBuffer(
                     Pool2,
                     a8,
                     (const void **)&OemString,
                     (const void **)&v59,
                     BugCheckOnFailure,
                     v43) )
              {
                *v44 = v46;
                goto LABEL_94;
              }
              v22 = (__int16 *)(v17 + 74);
LABEL_98:
              *v22 |= 2u;
            }
            else
            {
LABEL_94:
              v22 = (__int16 *)(v17 + 74);
            }
            if ( (*(_BYTE *)v22 & 2) != 0 && *v48 )
            {
              v53 = (void *)v17[75];
              if ( v53 )
                ExFreePoolWithTag(v53, 0);
              *v48 = 0;
              v17[75] = 0;
              *((_DWORD *)v17 + 157) = 0;
              *v44 = 0;
              *v56 = 0;
            }
            v16 = v55;
            v9 = a4;
LABEL_105:
            v10 = a2;
LABEL_106:
            *v22 &= ~8u;
            if ( (_QWORD *)v17[72] != v17 + 72 )
              MdaNotifyCompleteIrpList(v17, 0);
            goto LABEL_108;
          }
          v22 = (__int16 *)(v17 + 74);
        }
        v48 = v17 + 76;
        goto LABEL_98;
      }
    }
LABEL_108:
    v16 = (_QWORD *)*v16;
    v14 = (unsigned __int16 *)v57;
    a3 = v74;
  }
  v25 = (*(_DWORD *)p_Owner)-- == 1;
  if ( v25 )
  {
    *(_QWORD *)&v70->Count = 0;
    ExReleaseFastMutexUnsafe(FastMutex);
  }
  v12 = WPP_GLOBAL_Control;
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
  {
    v13 = 20;
    return (PDEVICE_OBJECT *)WPP_SF_(v12->AttachedDevice, v13, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14002fe10  mov     rax, rsp
0x14002fe13  mov     [rax+20h], r9w
0x14002fe18  mov     [rax+18h], r8
0x14002fe1c  mov     [rax+10h], rdx
0x14002fe20  mov     [rax+8], rcx
0x14002fe24  push    rbx
0x14002fe25  push    rsi
0x14002fe26  push    rdi
0x14002fe27  push    r12
0x14002fe29  push    r13
0x14002fe2b  push    r14
0x14002fe2d  push    r15
0x14002fe2f  sub     rsp, 0F0h
0x14002fe36  movzx   esi, r9w
0x14002fe3a  mov     r13, rdx
0x14002fe3d  mov     r15, rcx
0x14002fe40  xorps   xmm0, xmm0
0x14002fe43  movups  xmmword ptr [rax-78h], xmm0
0x14002fe47  xorps   xmm1, xmm1
0x14002fe4a  movups  xmmword ptr [rsp+128h+var_B0.Length], xmm1
0x14002fe4f  movups  xmmword ptr [rax-0A0h], xmm0
0x14002fe56  lea     r12, WPP_GLOBAL_Control
0x14002fe5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe64  mov     r14d, 80000h
0x14002fe6a  cmp     rcx, r12
0x14002fe6d  jz      short loc_14002FE92
0x14002fe6f  test    [rcx+2Ch], r14d
0x14002fe73  jz      short loc_14002FE92
0x14002fe75  mov     edx, 11h
0x14002fe7a  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14002fe81  mov     rcx, [rcx+18h]
0x14002fe85  call    WPP_SF_
0x14002fe8a  mov     r8, [rsp+128h+arg_10]
0x14002fe92  xor     ebx, ebx
0x14002fe94  test    si, si
0x14002fe97  jnz     short loc_14002FEBB
0x14002fe99  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fea0  cmp     rcx, r12
0x14002fea3  jz      loc_14003061B
0x14002fea9  test    [rcx+2Ch], r14d
0x14002fead  jz      loc_14003061B
0x14002feb3  lea     edx, [rbx+12h]
0x14002feb6  jmp     loc_14003060B
0x14002febb  cmp     si, [r8]
0x14002febf  jbe     short loc_14002FEE5
0x14002fec1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fec8  cmp     rcx, r12
0x14002fecb  jz      loc_14003061B
0x14002fed1  test    [rcx+2Ch], r14d
0x14002fed5  jz      loc_14003061B
0x14002fedb  mov     edx, 13h
0x14002fee0  jmp     loc_14003060B
0x14002fee5  mov     [rsp+128h+var_B8], rbx
0x14002feea  mov     [rsp+128h+var_B0.Buffer], rbx
0x14002fef2  mov     [rsp+128h+arg_20], bx
0x14002fefa  mov     [rsp+128h+var_C0], bx
0x14002feff  mov     [rsp+128h+var_B0.Length], bx
0x14002ff04  test    r15, r15
0x14002ff07  jz      loc_14003061B
0x14002ff0d  mov     [rsp+128h+var_90], r8
0x14002ff15  mov     r9, rbx
0x14002ff18  mov     [rsp+128h+var_C8], rbx
0x14002ff1d  mov     rdi, gs:188h
0x14002ff26  lea     r12, [r15+38h]
0x14002ff2a  mov     [rsp+128h+var_40], r12
0x14002ff32  cmp     rdi, [r12]
0x14002ff36  jz      short loc_14002FF56
0x14002ff38  mov     rcx, r15; FastMutex
0x14002ff3b  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002ff42  nop     dword ptr [rax+rax+00h]
0x14002ff47  mov     [r12], rdi
0x14002ff4b  mov     r9, rbx
0x14002ff4e  mov     r8, [rsp+128h+arg_10]
0x14002ff56  lea     rax, [r15+40h]
0x14002ff5a  mov     [rsp+128h+var_48], rax
0x14002ff62  inc     dword ptr [rax]
0x14002ff64  mov     r14, [r13+0]
0x14002ff68  mov     [rsp+128h+var_80], r14
0x14002ff70  mov     [rsp+128h+var_D8], r14
0x14002ff75  cmp     r14, r13
0x14002ff78  jz      loc_1400305BE
0x14002ff7e  lea     rdi, [r14-230h]
0x14002ff85  mov     [rsp+128h+var_68], rdi
0x14002ff8d  cmp     [rdi+18h], bx
0x14002ff91  jnz     short loc_14002FF98
0x14002ff93  jmp     loc_1400305A9
0x14002ff98  mov     eax, [rdi+254h]
0x14002ff9e  test    [rsp+128h+arg_30], eax
0x14002ffa5  jz      short loc_14002FF93
0x14002ffa7  test    r9, r9
0x14002ffaa  jnz     short loc_14002FFEF
0x14002ffac  mov     rax, [r8+8]
0x14002ffb0  mov     [rsp+128h+var_70], rax
0x14002ffb8  movzx   eax, si
0x14002ffbb  mov     [rsp+128h+var_78], ax
0x14002ffc3  movzx   ecx, byte ptr [rdi+252h]
0x14002ffca  cmp     si, cx
0x14002ffcd  jz      short loc_14002FFDA
0x14002ffcf  sub     ax, cx
0x14002ffd2  mov     [rsp+128h+var_78], ax
0x14002ffda  mov     [rsp+128h+var_76], ax
0x14002ffe2  lea     r9, [rsp+128h+var_78]
0x14002ffea  mov     [rsp+128h+var_C8], r9
0x14002ffef  movzx   edx, word ptr [rdi+18h]
0x14002fff3  movzx   eax, word ptr [r9]
0x14002fff7  cmp     dx, ax
0x14002fffa  ja      short loc_14002FF93
0x14002fffc  lea     r12, [rdi+250h]
0x140030003  mov     [rsp+128h+var_E8], r12
0x140030008  jnz     short loc_14003000F
0x14003000a  mov     r15b, 1
0x14003000d  jmp     short loc_140030044
0x14003000f  movzx   ecx, word ptr [r12]
0x140030014  test    cl, 1
0x140030017  jz      loc_14002FF93
0x14003001d  test    cl, 10h
0x140030020  jnz     short loc_140030041
0x140030022  movzx   ecx, word ptr [rdi+18h]
0x140030026  cmp     byte ptr [rdi+252h], 1
0x14003002d  jnz     loc_1400300E3
0x140030033  mov     rax, [r9+8]
0x140030037  cmp     byte ptr [rcx+rax], 5Ch ; '\'
0x14003003b  jnz     loc_14002FF93
0x140030041  mov     r15b, bl
0x140030044  mov     r8, rdx; Length
0x140030047  mov     rdx, [r9+8]; Source2
0x14003004b  mov     rcx, [rdi+20h]; Source1
0x14003004f  call    cs:__imp_RtlCompareMemory
0x140030056  nop     dword ptr [rax+rax+00h]
0x14003005b  movzx   r9d, word ptr [rdi+18h]
0x140030060  cmp     rax, r9
0x140030063  jnz     loc_14002FF93
0x140030069  mov     [rsp+128h+var_60], r12
0x140030071  movzx   r8d, word ptr [r12]
0x140030076  test    r8b, 2
0x14003007a  jnz     loc_140030589
0x140030080  mov     r13d, [rdi+268h]
0x140030087  test    r13d, r13d
0x14003008a  jz      loc_140030581
0x140030090  mov     [rsp+128h+var_F4], ebx
0x140030094  mov     [rsp+128h+var_F4], ebx
0x140030098  mov     [rsp+128h+var_88], rbx
0x1400300a0  lea     rax, [rdi+26Ch]
0x1400300a7  mov     [rsp+128h+var_D0], rax
0x1400300ac  mov     eax, [rax]
0x1400300ae  test    eax, eax
0x1400300b0  jnz     short loc_1400300FE
0x1400300b2  lea     rax, [rdi+240h]
0x1400300b9  mov     rcx, [rax]
0x1400300bc  cmp     rcx, rax
0x1400300bf  jz      short loc_1400300DC
0x1400300c1  mov     rdx, [rcx-8]
0x1400300c5  mov     [rsp+128h+var_88], rdx
0x1400300cd  mov     rax, [rdx+28h]
0x1400300d1  mov     rcx, [rax+0B8h]
0x1400300d8  mov     r13d, [rcx+8]
0x1400300dc  mov     [rsp+128h+var_F4], r13d
0x1400300e1  jmp     short loc_140030105
0x1400300e3  add     rcx, 2
0x1400300e7  cmp     rax, rcx
0x1400300ea  jb      loc_140030041
0x1400300f0  mov     rax, [r9+8]
0x1400300f4  cmp     word ptr [rdx+rax], 5Ch ; '\'
0x1400300f9  jmp     loc_14003003B
0x1400300fe  mov     r13d, eax
0x140030101  mov     [rsp+128h+var_F4], eax
0x140030105  test    r15b, r15b
0x140030108  jnz     loc_140030298
0x14003010e  and     r8w, 10h
0x140030113  jnz     short loc_14003015C
0x140030115  mov     r14, [rsp+128h+arg_10]
0x14003011d  add     r14, 8
0x140030121  mov     r10, [rsp+128h+var_C8]
0x140030126  mov     rdx, [r10+8]
0x14003012a  cmp     rdx, [r14]
0x14003012d  jnz     short loc_140030168
0x14003012f  movzx   ecx, byte ptr [rdi+252h]
0x140030136  lea     rax, [rdx+r9]
0x14003013a  add     rcx, rax
0x14003013d  mov     [rsp+128h+OemString.Buffer], rcx
0x140030145  movzx   eax, byte ptr [rdi+252h]
0x14003014c  movzx   edx, word ptr [r10]
0x140030150  sub     dx, ax
0x140030153  sub     dx, [rdi+18h]
0x140030157  jmp     loc_140030286
0x14003015c  mov     r14, [rsp+128h+var_90]
0x140030164  add     r14, 8
0x140030168  cmp     [rsp+128h+var_B8], rbx
0x14003016d  jnz     short loc_1400301A8
0x14003016f  mov     rax, [r14]
0x140030172  mov     [rsp+128h+var_B8], rax
0x140030177  movzx   ecx, si
0x14003017a  mov     [rsp+128h+arg_20], cx
0x140030182  mov     [rsp+128h+var_C0], cx
0x140030187  movzx   eax, byte ptr [rdi+252h]
0x14003018e  cmp     si, ax
0x140030191  jz      short loc_1400301A3
0x140030193  sub     cx, ax
0x140030196  mov     [rsp+128h+arg_20], cx
0x14003019e  mov     [rsp+128h+var_C0], cx
0x1400301a3  mov     [rsp+128h+var_BE], cx
0x1400301a8  mov     r10b, bl
0x1400301ab  mov     [rsp+128h+var_F8], bl
0x1400301af  mov     edx, ebx
0x1400301b1  mov     [rsp+128h+arg_28], ebx
0x1400301b8  test    r8w, r8w
0x1400301bc  jnz     loc_140030259
0x1400301c2  mov     [rsp+128h+var_E0], ebx
0x1400301c6  mov     [rsp+128h+var_DC], ebx
0x1400301ca  mov     r11d, 1
0x1400301d0  mov     r9d, r11d
0x1400301d3  mov     [rsp+128h+var_E0], r11d
0x1400301d8  mov     r8d, ebx
0x1400301db  mov     [rsp+128h+var_DC], ebx
0x1400301df  movzx   eax, word ptr [rdi+18h]
0x1400301e3  shr     eax, 1
0x1400301e5  cmp     r8d, eax
0x1400301e8  jnb     short loc_14003020A
0x1400301ea  mov     ecx, r8d
0x1400301ed  mov     rax, [rdi+20h]
0x1400301f1  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x1400301f6  jnz     short loc_140030200
0x1400301f8  add     r9d, r11d
0x1400301fb  mov     [rsp+128h+var_E0], r9d
0x140030200  add     r8d, r11d
0x140030203  mov     [rsp+128h+var_DC], r8d
0x140030208  jmp     short loc_1400301DF
0x14003020a  movzx   ecx, [rsp+128h+arg_20]
0x140030212  mov     r8, [rsp+128h+var_B8]
0x140030217  mov     eax, ecx
0x140030219  shr     eax, 1
0x14003021b  cmp     edx, eax
0x14003021d  jnb     short loc_140030246
0x14003021f  mov     eax, edx
0x140030221  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140030227  jnz     short loc_14003023A
0x140030229  add     r10b, r11b
0x14003022c  mov     [rsp+128h+var_F8], r10b
0x140030231  movzx   eax, r10b
0x140030235  cmp     eax, r9d
0x140030238  jz      short loc_140030246
0x14003023a  add     edx, r11d
0x14003023d  mov     [rsp+128h+arg_28], edx
0x140030244  jmp     short loc_140030217
0x140030246  movzx   eax, byte ptr [rdi+252h]
0x14003024d  imul    edx, eax
0x140030250  mov     [rsp+128h+arg_28], edx
0x140030257  jmp     short loc_14003025E
0x140030259  mov     r8, [rsp+128h+var_B8]
0x14003025e  movzx   ecx, byte ptr [rdi+252h]
0x140030265  add     ecx, edx
0x140030267  mov     [rsp+128h+arg_28], ecx
0x14003026e  mov     eax, ecx
0x140030270  add     rax, r8
0x140030273  mov     [rsp+128h+OemString.Buffer], rax
0x14003027b  movzx   edx, [rsp+128h+arg_20]
0x140030283  sub     dx, cx
0x140030286  mov     [rsp+128h+OemString.Length], dx
0x14003028e  mov     [rsp+128h+OemString.MaximumLength], dx
0x140030296  jmp     short loc_1400302AE
0x140030298  mov     [rsp+128h+OemString.Length], bx
0x1400302a0  mov     edx, ebx
0x1400302a2  mov     r14, [rsp+128h+var_90]
0x1400302aa  add     r14, 8
0x1400302ae  mov     esi, 0Ch
0x1400302b3  test    r15b, r15b
0x1400302b6  jnz     short loc_1400302E0
0x1400302b8  cmp     byte ptr [rdi+252h], 1
0x1400302bf  jnz     short loc_1400302DA
0x1400302c1  lea     rcx, [rsp+128h+OemString]; OemString
0x1400302c9  call    cs:__imp_RtlxOemStringToUnicodeSize
0x1400302d0  nop     dword ptr [rax+rax+00h]
0x1400302d5  lea     esi, [rax+0Ch]
0x1400302d8  jmp     short loc_1400302E0
0x1400302da  movzx   esi, dx
0x1400302dd  add     esi, 0Eh
0x1400302e0  cmp     [rsp+128h+var_B0.Buffer], rbx
0x1400302e8  jnz     short loc_140030317
0x1400302ea  movzx   ecx, [rsp+128h+arg_18]
0x1400302f2  mov     eax, ecx
0x1400302f4  add     rax, [r14]
0x1400302f7  mov     [rsp+128h+var_B0.Buffer], rax
0x1400302ff  mov     rax, [rsp+128h+arg_10]
0x140030307  movzx   eax, word ptr [rax]
0x14003030a  sub     ax, cx
0x14003030d  mov     [rsp+128h+var_B0.Length], ax
0x140030312  mov     [rsp+128h+var_B0.MaximumLength], ax
0x140030317  cmp     byte ptr [rdi+252h], 1
0x14003031e  jnz     short loc_140030336
0x140030320  lea     rcx, [rsp+128h+var_B0]; OemString
0x140030325  call    cs:__imp_RtlxOemStringToUnicodeSize
0x14003032c  nop     dword ptr [rax+rax+00h]
0x140030331  add     eax, 0FFFFFFFEh
0x140030334  jmp     short loc_14003033B
0x140030336  movzx   eax, [rsp+128h+var_B0.Length]
0x14003033b  add     esi, eax
0x14003033d  mov     [rsp+128h+arg_28], esi
0x140030344  lea     r15, [rdi+270h]
0x14003034b  mov     [rsp+128h+var_58], r15
0x140030353  cmp     esi, r13d
  ... truncated ...
```
