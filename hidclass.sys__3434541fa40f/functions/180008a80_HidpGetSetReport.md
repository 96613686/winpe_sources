# HidpGetSetReport

- ea: `0x180008a80`
- end: `0x1800094a8`
- name: `HidpGetSetReport`
- size: `2600`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180006ac8`

## callees

- `0x180003090`
- `0x180008a80`
- `0x1800094b0`
- `0x180009664`
- `0x180013860`
- `0x18001952c`
- `0x180021bb0`
- `0x180022ba0`
- `0x180022d2c`
- `0x18003de60`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180008e76`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180008f22`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000907f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180008e76`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180008f22`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000907f`
- `ntoskrnl!IoIncrementKeepAliveCount` at `0x18000935e`
- `ntoskrnl!IoIncrementKeepAliveCount` at `0x18000935e`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x180008fd1`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x180008fd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180008d91`
- `ntoskrnl!ExFreePoolWithTag` at `0x180008d91`
- `ntoskrnl!ExAllocatePool2` at `0x180008c79`
- `ntoskrnl!ExAllocatePool2` at `0x180008c79`
- `ntoskrnl!KeGetCurrentIrql` at `0x180008aba`
- `ntoskrnl!KeGetCurrentIrql` at `0x180008aba`

## pseudocode

```c
__int64 __fastcall HidpGetSetReport(__int64 a1, _QWORD *a2, unsigned int a3, _BYTE *a4)
{
  unsigned int v4; // ebp
  __int64 v5; // rsi
  __int64 v7; // rdi
  int v8; // edx
  int v9; // r8d
  __int64 v10; // rbx
  __int64 v11; // rax
  unsigned int *v12; // r14
  __int64 v13; // r9
  unsigned int v14; // r11d
  __int64 i; // rdx
  __int64 v16; // r8
  __int16 v17; // di
  volatile signed __int32 *v18; // rcx
  unsigned int v19; // r12d
  unsigned __int8 *v20; // r15
  _BYTE *v21; // r8
  unsigned __int8 v22; // al
  unsigned __int8 v23; // cl
  char v24; // bl
  __int64 j; // rax
  unsigned __int8 *v26; // rdx
  unsigned int v27; // eax
  unsigned int v28; // ebx
  __int64 Pool2; // rax
  int v30; // edx
  __int64 v31; // r8
  void *v32; // rdi
  __int64 v33; // rax
  __int64 v34; // rdx
  _QWORD *v35; // rbp
  int v36; // eax
  int v37; // edx
  int v38; // r8d
  __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned int v42; // eax
  __int64 v43; // rcx
  const char *v44; // r9
  __int64 v45; // r8
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-B8h]
  ULONG Priority; // [rsp+28h] [rbp-B0h]
  int v48; // [rsp+30h] [rbp-A8h]
  int v49; // [rsp+38h] [rbp-A0h]
  char v50; // [rsp+80h] [rbp-58h]

  v4 = a3;
  v5 = *(_QWORD *)(a1 + 96) + 32LL;
  *a4 = 0;
  v7 = a1;
  if ( !KeGetCurrentIrql() )
  {
    v10 = a2[23];
    v11 = *(_QWORD *)(v10 + 48);
    if ( !v11 || (v12 = *(unsigned int **)(v11 + 24)) == 0 )
    {
      v28 = -1073741727;
      LOBYTE(v8) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qdqL(
          WPP_GLOBAL_Control->AttachedDevice,
          v8,
          v9,
          *(_QWORD *)(v5 + 672),
          2,
          8,
          16,
          (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v7 + 96) + 32LL),
          *(_DWORD *)(v7 + 40),
          *(_QWORD *)(v7 + 80),
          97);
        v4 = a3;
      }
      v44 = "FsContext NULL";
      v45 = 0;
      goto LABEL_91;
    }
    v13 = *(_QWORD *)(v5 + 160);
    v14 = *v12;
    if ( !v13 )
      goto LABEL_92;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= *(_DWORD *)(v5 + 168) )
        goto LABEL_92;
      v16 = v13 + 40 * i;
      if ( *(unsigned __int8 *)(v16 + 4) == v14 )
        break;
    }
    if ( !v16 )
    {
LABEL_92:
      TraceLoggingGetCollectionDescFailed(v5, v14);
      return (unsigned int)-1073741667;
    }
    switch ( v4 )
    {
      case 0xB0191u:
        v17 = *(_WORD *)(v16 + 24);
        v18 = (volatile signed __int32 *)(v12 + 45);
LABEL_11:
        v19 = *(_DWORD *)(v10 + 16);
        v20 = (unsigned __int8 *)a2[3];
        break;
      case 0xB0192u:
        v41 = a2[1];
        v20 = 0;
        v17 = *(_WORD *)(v16 + 24);
        if ( v41 )
        {
          if ( (*(_BYTE *)(v41 + 10) & 5) != 0 )
          {
            v20 = *(unsigned __int8 **)(v41 + 24);
            v18 = (volatile signed __int32 *)(v12 + 44);
            v19 = *(_DWORD *)(v10 + 8);
            break;
          }
          v20 = (unsigned __int8 *)MmMapLockedPagesSpecifyCache((PMDL)v41, 0, MmCached, 0, 0, 0x40000010u);
        }
        v19 = *(_DWORD *)(v10 + 8);
        v18 = (volatile signed __int32 *)(v12 + 44);
        break;
      case 0xB0195u:
        v17 = *(_WORD *)(v16 + 22);
        v18 = (volatile signed __int32 *)(v12 + 42);
        goto LABEL_11;
      case 0xB01A2u:
        v43 = a2[1];
        v20 = 0;
        v17 = *(_WORD *)(v16 + 20);
        if ( v43 )
        {
          if ( (*(_BYTE *)(v43 + 10) & 5) != 0 )
          {
            v20 = *(unsigned __int8 **)(v43 + 24);
            v18 = (volatile signed __int32 *)(v12 + 41);
            v19 = *(_DWORD *)(v10 + 8);
            break;
          }
          v20 = (unsigned __int8 *)MmMapLockedPagesSpecifyCache((PMDL)v43, 0, MmCached, 0, 0, 0x40000010u);
        }
        v19 = *(_DWORD *)(v10 + 8);
        v18 = (volatile signed __int32 *)(v12 + 41);
        break;
      case 0xB01A6u:
        v40 = a2[1];
        v20 = 0;
        v17 = *(_WORD *)(v16 + 22);
        if ( v40 )
        {
          if ( (*(_BYTE *)(v40 + 10) & 5) != 0 )
            v20 = *(unsigned __int8 **)(v40 + 24);
          else
            v20 = (unsigned __int8 *)MmMapLockedPagesSpecifyCache((PMDL)v40, 0, MmCached, 0, 0, 0x40000010u);
        }
        v19 = *(_DWORD *)(v10 + 8);
        v18 = (volatile signed __int32 *)(v12 + 43);
        break;
      default:
        goto LABEL_108;
    }
    _InterlockedIncrement(v18);
    if ( v17 )
    {
      if ( !v20 || !v19 )
      {
        TraceLoggingGetSetReportFailed(v5, v4, *v12, "Report length zero");
        return (unsigned int)-1073741592;
      }
      v21 = *(_BYTE **)(v5 + 176);
      v22 = *v20;
      if ( !*v21 )
      {
        ++v20;
        --v19;
      }
      v23 = 0;
      if ( *v21 )
        v23 = v22;
      v24 = v23;
      v50 = v23;
      if ( !v21 )
      {
LABEL_57:
        TraceLoggingGetReportIdentifierFailed(v5, v23);
        return (unsigned int)-1073741811;
      }
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)j >= *(_DWORD *)(v5 + 184) )
          goto LABEL_57;
        v26 = &v21[8 * j];
        if ( *v26 == v23 )
          break;
      }
      if ( !v26 )
        goto LABEL_57;
      if ( v26[1] == *v12 )
      {
        switch ( v4 )
        {
          case 0xB0191u:
            v27 = *((unsigned __int16 *)v26 + 3);
            if ( !(_WORD)v27 || v19 < v27 )
            {
LABEL_30:
              v28 = -1073741811;
              LOBYTE(v26) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                         && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
              if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_qdqdLd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  (_DWORD)v26,
                  (_DWORD)v21,
                  *(_QWORD *)(v5 + 672),
                  BugCheckOnFailure,
                  Priority);
              }
              v45 = *v12;
              v44 = "Buffer size invalid";
              goto LABEL_91;
            }
            goto LABEL_78;
          case 0xB0192u:
            v42 = *((unsigned __int16 *)v26 + 3);
            break;
          case 0xB0195u:
            v27 = *((unsigned __int16 *)v26 + 2);
            if ( !(_WORD)v27 || v19 < v27 )
              goto LABEL_30;
LABEL_78:
            v19 = v27;
            goto LABEL_38;
          case 0xB01A2u:
            v42 = *((unsigned __int16 *)v26 + 1);
            break;
          default:
            v42 = *((unsigned __int16 *)v26 + 2);
            break;
        }
        if ( !(_WORD)v42 || v19 < v42 )
          goto LABEL_30;
LABEL_38:
        Pool2 = ExAllocatePool2(64, 16, 1130654024);
        v32 = (void *)Pool2;
        if ( !Pool2 )
          return (unsigned int)-1073741670;
        *(_QWORD *)Pool2 = v20;
        *(_DWORD *)(Pool2 + 8) = v19;
        *(_BYTE *)(Pool2 + 12) = v24;
        a2[14] = Pool2;
        v33 = a2[23];
        *(_BYTE *)(v33 - 72) = 15;
        *(_DWORD *)(v33 - 48) = a3;
        if ( a3 == 721318 )
          goto LABEL_40;
        if ( a3 != 721297 )
        {
          if ( a3 == 721298 )
          {
LABEL_40:
            *(_DWORD *)(v33 - 64) = 16;
LABEL_41:
            v34 = *((_QWORD *)v12 + 17);
            if ( v34 )
            {
              IoIncrementKeepAliveCount(*((_QWORD *)v12 + 12));
              _InterlockedIncrement((volatile signed __int32 *)v12 + 36);
            }
            LOBYTE(v34) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                       && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
            LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            if ( (_BYTE)v34 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v35 = a2;
              WPP_RECORDER_AND_TRACE_SF_qdqLDq(
                WPP_GLOBAL_Control->AttachedDevice,
                v34,
                v31,
                *(_QWORD *)(v5 + 672),
                BugCheckOnFailure,
                Priority,
                v48,
                v49,
                *(_QWORD *)(*(_QWORD *)(a1 + 96) + 32LL),
                *(_DWORD *)(a1 + 40),
                *(_QWORD *)(a1 + 80),
                a3,
                v24,
                (char)a2);
            }
            else
            {
              v35 = a2;
            }
            v36 = HidpCallDriverSynchronous(*(_QWORD *)v5, v35, v31);
            v28 = v36;
            if ( v36 < 0 )
            {
              LOBYTE(v37) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                         && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
              if ( (_BYTE)v37 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v38) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_qdqLDqd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v37,
                  v38,
                  *(_QWORD *)(v5 + 672),
                  BugCheckOnFailure,
                  Priority,
                  v48,
                  v49,
                  *(_QWORD *)(*(_QWORD *)(a1 + 96) + 32LL),
                  *(_DWORD *)(a1 + 40),
                  *(_QWORD *)(a1 + 80),
                  a3,
                  v50,
                  (char)v35,
                  v36);
              }
            }
            if ( *((_QWORD *)v12 + 17) )
            {
              IoDecrementKeepAliveCount(*((_QWORD *)v12 + 12));
              _InterlockedDecrement((volatile signed __int32 *)v12 + 36);
            }
            ExFreePoolWithTag(v32, 0);
            *a4 = 0;
            return v28;
          }
          if ( a3 != 721301 )
          {
            if ( a3 != 721314 )
            {
              LOBYTE(v30) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              if ( (_BYTE)v30 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_qdqL(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v30,
                  v31,
                  *(_QWORD *)(v5 + 672),
                  2,
                  8,
                  20,
                  (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
                  *(_QWORD *)(*(_QWORD *)(a1 + 96) + 32LL),
                  *(_DWORD *)(a1 + 40),
                  *(_QWORD *)(a1 + 80),
                  a3);
              }
              goto LABEL_41;
            }
            goto LABEL_40;
          }
        }
        *(_DWORD *)(v33 - 56) = 16;
        goto LABEL_41;
      }
      v28 = -1073741808;
      LOBYTE(v26) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qdqLd(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v26,
          (_DWORD)v21,
          *(_QWORD *)(v5 + 672),
          3,
          8,
          18,
          (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
          *(_QWORD *)(*(_QWORD *)(a1 + 96) + 32LL),
          *(_DWORD *)(a1 + 40),
          *(_QWORD *)(a1 + 80),
          v23,
          16);
      }
      v45 = *v12;
      v44 = "Mismatch collection number";
LABEL_91:
      TraceLoggingGetSetReportFailed(v5, v4, v45, v44);
      return v28;
    }
    v7 = a1;
LABEL_108:
    v28 = -1073741808;
    LOBYTE(i) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( (_BYTE)i || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqLd(
        WPP_GLOBAL_Control->AttachedDevice,
        i,
        v16,
        *(_QWORD *)(v5 + 672),
        3,
        8,
        17,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        *(_QWORD *)(*(_QWORD *)(v7 + 96) + 32LL),
        *(_DWORD *)(v7 + 40),
        *(_QWORD *)(v7 + 80),
        v4,
        16);
    }
    v45 = *v12;
    v44 = "Report length zero";
    goto LABEL_91;
  }
  v28 = -1073741808;
  LOBYTE(v8) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qdqL(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v9,
      *(_QWORD *)(v5 + 672),
      2,
      8,
      15,
      (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
      *(_QWORD *)(*(_QWORD *)(v7 + 96) + 32LL),
      *(_DWORD *)(v7 + 40),
      *(_QWORD *)(v7 + 80),
      16);
  }
  return v28;
}

```

## disassembly

```asm
0x180008a80  mov     [rsp+arg_18], r9
0x180008a85  mov     [rsp+arg_10], r8d
0x180008a8a  mov     [rsp+arg_8], rdx
0x180008a8f  mov     [rsp+arg_0], rcx
0x180008a94  push    rbx
0x180008a95  push    rbp
0x180008a96  push    rsi
0x180008a97  push    rdi
0x180008a98  push    r12
0x180008a9a  push    r13
0x180008a9c  push    r15
0x180008a9e  sub     rsp, 0A0h
0x180008aa5  mov     rsi, [rcx+60h]
0x180008aa9  mov     ebp, r8d
0x180008aac  add     rsi, 20h ; ' '
0x180008ab0  mov     byte ptr [r9], 0
0x180008ab4  mov     r13, rdx
0x180008ab7  mov     rdi, rcx
0x180008aba  call    cs:__imp_KeGetCurrentIrql
0x180008ac1  nop     dword ptr [rax+rax+00h]
0x180008ac6  test    al, al
0x180008ac8  jnz     loc_180009093
0x180008ace  mov     rbx, [r13+0B8h]
0x180008ad5  mov     [rsp+0D8h+var_40], r14
0x180008add  mov     rax, [rbx+30h]
0x180008ae1  test    rax, rax
0x180008ae4  jz      loc_180008F5E
0x180008aea  mov     r14, [rax+18h]
0x180008aee  test    r14, r14
0x180008af1  jz      loc_180008F5E
0x180008af7  mov     r9, [rsi+0A0h]
0x180008afe  mov     r11d, [r14]
0x180008b01  test    r9, r9
0x180008b04  jz      loc_180008FB8
0x180008b0a  mov     r10d, [rsi+0A8h]
0x180008b11  xor     edx, edx
0x180008b13  cmp     edx, r10d
0x180008b16  jnb     loc_180008FB8
0x180008b1c  lea     rcx, [rdx+rdx*4]
0x180008b20  movzx   eax, byte ptr [r9+rcx*8+4]
0x180008b26  lea     r8, [r9+rcx*8]
0x180008b2a  cmp     eax, r11d
0x180008b2d  jnz     loc_180008BD0
0x180008b33  test    r8, r8
0x180008b36  jz      loc_180008FB8
0x180008b3c  cmp     ebp, 0B0191h
0x180008b42  jnz     loc_180008DF4
0x180008b48  movzx   edi, word ptr [r8+18h]
0x180008b4d  lea     rcx, [r14+0B4h]
0x180008b54  mov     r12d, [rbx+10h]
0x180008b58  mov     r15, [r13+18h]
0x180008b5c  lock inc dword ptr [rcx]
0x180008b5f  test    di, di
0x180008b62  jz      loc_180009133
0x180008b68  test    r15, r15
0x180008b6b  jz      loc_180009411
0x180008b71  test    r12d, r12d
0x180008b74  jz      loc_180009411
0x180008b7a  mov     r8, [rsi+0B0h]
0x180008b81  movzx   eax, byte ptr [r15]
0x180008b85  movzx   edx, byte ptr [r8]
0x180008b89  test    dl, dl
0x180008b8b  jnz     short loc_180008B93
0x180008b8d  inc     r15
0x180008b90  dec     r12d
0x180008b93  xor     ecx, ecx
0x180008b95  test    dl, dl
0x180008b97  cmovnz  ecx, eax
0x180008b9a  movzx   ebx, cl
0x180008b9d  mov     dword ptr [rsp+0D8h+var_58], ebx
0x180008ba4  test    r8, r8
0x180008ba7  jz      loc_180008DDC
0x180008bad  mov     r9d, [rsi+0B8h]
0x180008bb4  xor     eax, eax
0x180008bb6  cmp     eax, r9d
0x180008bb9  jnb     loc_180008DDC
0x180008bbf  movzx   ecx, byte ptr [r8+rax*8]
0x180008bc4  lea     rdx, [r8+rax*8]
0x180008bc8  cmp     ecx, ebx
0x180008bca  jz      short loc_180008BD7
0x180008bcc  inc     eax
0x180008bce  jmp     short loc_180008BB6
0x180008bd0  inc     edx
0x180008bd2  jmp     loc_180008B13
0x180008bd7  test    rdx, rdx
0x180008bda  jz      loc_180008DDC
0x180008be0  movzx   eax, byte ptr [rdx+1]
0x180008be4  cmp     eax, [r14]
0x180008be7  jnz     loc_1800091E5
0x180008bed  cmp     ebp, 0B0191h
0x180008bf3  jnz     short loc_180008C3F
0x180008bf5  movzx   eax, word ptr [rdx+6]
0x180008bf9  test    ax, ax
0x180008bfc  jz      short loc_180008C07
0x180008bfe  cmp     r12d, eax
0x180008c01  jnb     loc_180008EDA
0x180008c07  mov     ebx, 0C000000Dh
0x180008c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c13  lea     r15, WPP_GLOBAL_Control
0x180008c1a  cmp     rcx, r15
0x180008c1d  jz      loc_1800093A6
0x180008c23  mov     eax, [rcx+2Ch]
0x180008c26  test    al, al
0x180008c28  jns     loc_1800093A6
0x180008c2e  cmp     byte ptr [rcx+29h], 3
0x180008c32  jb      loc_1800093A6
0x180008c38  mov     dl, 1
0x180008c3a  jmp     loc_1800093A8
0x180008c3f  mov     eax, ebp
0x180008c41  sub     eax, 0B0192h
0x180008c46  jz      loc_180008E95
0x180008c4c  sub     eax, 3
0x180008c4f  jz      loc_180008EC4
0x180008c55  sub     eax, 0Dh
0x180008c58  jz      loc_180008F41
0x180008c5e  cmp     eax, 4
0x180008c61  jz      loc_18000929F
0x180008c67  mov     ebp, 10h
0x180008c6c  mov     r8d, 43646948h
0x180008c72  mov     edx, ebp
0x180008c74  mov     ecx, 40h ; '@'
0x180008c79  call    cs:__imp_ExAllocatePool2
0x180008c80  nop     dword ptr [rax+rax+00h]
0x180008c85  mov     rdi, rax
0x180008c88  test    rax, rax
0x180008c8b  jz      loc_180008DED
0x180008c91  mov     [rax], r15
0x180008c94  lea     r15, WPP_GLOBAL_Control
0x180008c9b  mov     [rax+8], r12d
0x180008c9f  mov     r12d, [rsp+0D8h+arg_10]
0x180008ca7  mov     [rax+0Ch], bl
0x180008caa  mov     [r13+70h], rax
0x180008cae  mov     rax, [r13+0B8h]
0x180008cb5  lea     r13, WPP_RECORDER_INITIALIZED
0x180008cbc  mov     byte ptr [rax-48h], 0Fh
0x180008cc0  mov     [rax-30h], r12d
0x180008cc4  cmp     r12d, 0B01A6h
0x180008ccb  jnz     loc_180008DC5
0x180008cd1  mov     [rax-40h], ebp
0x180008cd4  mov     rdx, [r14+88h]
0x180008cdb  test    rdx, rdx
0x180008cde  jnz     loc_18000935A
0x180008ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ceb  cmp     rcx, r15
0x180008cee  jz      short loc_180008CFB
0x180008cf0  mov     eax, [rcx+2Ch]
0x180008cf3  test    al, al
0x180008cf5  js      loc_180009377
0x180008cfb  xor     dl, dl
0x180008cfd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180008d04  setnz   r8b
0x180008d08  test    dl, dl
0x180008d0a  jnz     short loc_180008D1B
0x180008d0c  test    r8b, r8b
0x180008d0f  jnz     short loc_180008D1B
0x180008d11  mov     rbp, [rsp+0D8h+arg_8]
0x180008d19  jmp     short loc_180008D67
0x180008d1b  mov     r10, [rsp+0D8h+arg_0]
0x180008d23  mov     rbp, [rsp+0D8h+arg_8]
0x180008d2b  mov     rcx, [rcx+18h]
0x180008d2f  mov     [rsp+0D8h+var_70], rbp
0x180008d34  mov     rax, [r10+50h]
0x180008d38  mov     r9, [r10+60h]
0x180008d3c  mov     [rsp+0D8h+var_78], ebx
0x180008d40  mov     [rsp+0D8h+var_80], r12d
0x180008d45  mov     [rsp+0D8h+var_88], rax
0x180008d4a  mov     eax, [r10+28h]
0x180008d4e  mov     [rsp+0D8h+var_90], eax
0x180008d52  mov     rax, [r9+20h]
0x180008d56  mov     r9, [rsi+2A0h]
0x180008d5d  mov     [rsp+0D8h+var_98], rax
0x180008d62  call    WPP_RECORDER_AND_TRACE_SF_qdqLDq
0x180008d67  mov     rcx, [rsi]
0x180008d6a  mov     rdx, rbp
0x180008d6d  call    HidpCallDriverSynchronous
0x180008d72  mov     ebx, eax
0x180008d74  test    eax, eax
0x180008d76  js      loc_180008FEA
0x180008d7c  mov     rdx, [r14+88h]
0x180008d83  test    rdx, rdx
0x180008d86  jnz     loc_180008FCD
0x180008d8c  xor     edx, edx; Tag
0x180008d8e  mov     rcx, rdi; P
0x180008d91  call    cs:__imp_ExFreePoolWithTag
0x180008d98  nop     dword ptr [rax+rax+00h]
0x180008d9d  mov     rax, [rsp+0D8h+arg_18]
0x180008da5  mov     byte ptr [rax], 0
0x180008da8  mov     r14, [rsp+0D8h+var_40]
0x180008db0  mov     eax, ebx
0x180008db2  add     rsp, 0A0h
0x180008db9  pop     r15
0x180008dbb  pop     r13
0x180008dbd  pop     r12
0x180008dbf  pop     rdi
0x180008dc0  pop     rsi
0x180008dc1  pop     rbp
0x180008dc2  pop     rbx
0x180008dc3  retn
0x180008dc5  mov     ecx, r12d
0x180008dc8  sub     ecx, 0B0191h
0x180008dce  jnz     loc_1800092A8
0x180008dd4  mov     [rax-38h], ebp
0x180008dd7  jmp     loc_180008CD4
0x180008ddc  mov     edx, ebx
0x180008dde  mov     rcx, rsi
0x180008de1  call    TraceLoggingGetReportIdentifierFailed
0x180008de6  mov     ebx, 0C000000Dh
0x180008deb  jmp     short loc_180008DA8
0x180008ded  mov     ebx, 0C000009Ah
0x180008df2  jmp     short loc_180008DA8
0x180008df4  mov     eax, ebp
0x180008df6  sub     eax, 0B0192h
0x180008dfb  jz      short loc_180008E47
0x180008dfd  sub     eax, 3
0x180008e00  jz      loc_180008EE2
0x180008e06  sub     eax, 0Dh
0x180008e09  jz      loc_180008EF3
0x180008e0f  cmp     eax, 4
0x180008e12  jnz     loc_18000913B
0x180008e18  mov     rcx, [r13+8]; MemoryDescriptorList
0x180008e1c  xor     r15d, r15d
0x180008e1f  movzx   edi, word ptr [r8+16h]
0x180008e24  test    rcx, rcx
0x180008e27  jz      short loc_180008E37
0x180008e29  test    byte ptr [rcx+0Ah], 5
0x180008e2d  jz      loc_180009067
0x180008e33  mov     r15, [rcx+18h]
0x180008e37  mov     r12d, [rbx+8]
0x180008e3b  lea     rcx, [r14+0ACh]
0x180008e42  jmp     loc_180008B5C
0x180008e47  mov     rcx, [r13+8]; MemoryDescriptorList
0x180008e4b  xor     r15d, r15d
0x180008e4e  movzx   edi, word ptr [r8+18h]
0x180008e53  test    rcx, rcx
0x180008e56  jz      short loc_180008E85
0x180008e58  test    byte ptr [rcx+0Ah], 5
0x180008e5c  jnz     short loc_180008EB0
0x180008e5e  mov     [rsp+0D8h+Priority], 40000010h; Priority
0x180008e66  xor     r9d, r9d; RequestedAddress
0x180008e69  xor     edx, edx; AccessMode
0x180008e6b  mov     [rsp+0D8h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x180008e70  mov     r8d, 1; CacheType
0x180008e76  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180008e7d  nop     dword ptr [rax+rax+00h]
0x180008e82  mov     r15, rax
0x180008e85  mov     r12d, [rbx+8]
0x180008e89  lea     rcx, [r14+0B0h]
0x180008e90  jmp     loc_180008B5C
0x180008e95  movzx   eax, word ptr [rdx+6]
0x180008e99  test    ax, ax
0x180008e9c  jz      loc_180008C07
0x180008ea2  cmp     r12d, eax
0x180008ea5  jnb     loc_180008C67
0x180008eab  jmp     loc_180008C07
0x180008eb0  mov     r15, [rcx+18h]
0x180008eb4  lea     rcx, [r14+0B0h]
0x180008ebb  mov     r12d, [rbx+8]
0x180008ebf  jmp     loc_180008B5C
0x180008ec4  movzx   eax, word ptr [rdx+4]
0x180008ec8  test    ax, ax
0x180008ecb  jz      loc_180008C07
0x180008ed1  cmp     r12d, eax
0x180008ed4  jb      loc_180008C07
0x180008eda  mov     r12d, eax
0x180008edd  jmp     loc_180008C67
0x180008ee2  movzx   edi, word ptr [r8+16h]
0x180008ee7  lea     rcx, [r14+0A8h]
0x180008eee  jmp     loc_180008B54
0x180008ef3  mov     rcx, [r13+8]; MemoryDescriptorList
0x180008ef7  xor     r15d, r15d
0x180008efa  movzx   edi, word ptr [r8+14h]
0x180008eff  test    rcx, rcx
0x180008f02  jz      short loc_180008F31
0x180008f04  test    byte ptr [rcx+0Ah], 5
0x180008f08  jnz     short loc_180008F4A
0x180008f0a  mov     [rsp+0D8h+Priority], 40000010h; Priority
0x180008f12  xor     r9d, r9d; RequestedAddress
0x180008f15  xor     edx, edx; AccessMode
0x180008f17  mov     [rsp+0D8h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x180008f1c  mov     r8d, 1; CacheType
0x180008f22  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180008f29  nop     dword ptr [rax+rax+00h]
0x180008f2e  mov     r15, rax
0x180008f31  mov     r12d, [rbx+8]
0x180008f35  lea     rcx, [r14+0A4h]
0x180008f3c  jmp     loc_180008B5C
0x180008f41  movzx   eax, word ptr [rdx+2]
0x180008f45  jmp     loc_180008E99
0x180008f4a  mov     r15, [rcx+18h]
0x180008f4e  lea     rcx, [r14+0A4h]
0x180008f55  mov     r12d, [rbx+8]
0x180008f59  jmp     loc_180008B5C
0x180008f5e  mov     ebx, 0C0000061h
0x180008f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f6a  lea     r15, WPP_GLOBAL_Control
0x180008f71  cmp     rcx, r15
0x180008f74  jnz     loc_18000942F
0x180008f7a  xor     dl, dl
0x180008f7c  lea     r13, WPP_RECORDER_INITIALIZED
0x180008f83  cmp     cs:WPP_RECORDER_INITIALIZED, r13
  ... truncated ...
```
