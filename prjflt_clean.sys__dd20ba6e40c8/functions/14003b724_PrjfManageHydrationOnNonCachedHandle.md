# PrjfManageHydrationOnNonCachedHandle

- ea: `0x14003b724`
- end: `0x14003be81`
- name: `PrjfManageHydrationOnNonCachedHandle`
- size: `1885`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140035f3c`

## callees

- `0x14000b1a0`
- `0x14000b1d0`
- `0x14000bb80`
- `0x14000d128`
- `0x14000d754`
- `0x14000ef78`
- `0x140011984`
- `0x140012870`
- `0x140012984`
- `0x140012a98`
- `0x140012bd0`
- `0x14003b724`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003b758`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003b758`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003b8ae`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003b8ae`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14003bd80`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14003bd80`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14003bac1`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14003bac1`
- `FLTMGR!FltWriteFileEx` at `0x14003bbac`
- `FLTMGR!FltWriteFileEx` at `0x14003bdd9`
- `FLTMGR!FltWriteFileEx` at `0x14003bbac`
- `FLTMGR!FltWriteFileEx` at `0x14003bdd9`

## string_xrefs

- `0x14003ba56`: `bytesToWrite Not Aligned and Offset + BytesToWrite != FileSize`

## pseudocode

```c
__int64 __fastcall PrjfManageHydrationOnNonCachedHandle(
        struct _FLT_INSTANCE *a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        __int64 a4)
{
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // r14
  __int64 SectorSize; // r15
  unsigned __int64 v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rdi
  unsigned __int64 v17; // rcx
  int v18; // edx
  unsigned int v19; // ebx
  bool v20; // cc
  char v21; // r12
  char *v22; // rax
  __int64 v23; // r8
  int v24; // ebx
  int v25; // ecx
  struct _FLT_INSTANCE *v26; // rbx
  SIZE_T v27; // r8
  int v28; // edx
  int v29; // ecx
  int v30; // r8d
  PVOID PoolAlignedWithTag; // r12
  unsigned int v32; // r14d
  unsigned int v33; // eax
  unsigned int v34; // esi
  int v35; // edx
  int v36; // r8d
  unsigned __int64 v37; // rdx
  int v38; // edx
  int v39; // r8d
  int BugCheckOnFailure; // [rsp+20h] [rbp-A8h]
  int BugCheckOnFailurea; // [rsp+20h] [rbp-A8h]
  ULONG Priority; // [rsp+28h] [rbp-A0h]
  ULONG Prioritya; // [rsp+28h] [rbp-A0h]
  int v45; // [rsp+30h] [rbp-98h]
  int v46; // [rsp+38h] [rbp-90h]
  int v47; // [rsp+40h] [rbp-88h]
  int v48; // [rsp+48h] [rbp-80h]
  ULONG AlignmentRequirement; // [rsp+80h] [rbp-48h]
  char *v50; // [rsp+88h] [rbp-40h]
  int v52; // [rsp+D8h] [rbp+10h] BYREF
  __int64 v53; // [rsp+E0h] [rbp+18h] BYREF

  v53 = a3;
  v52 = 0;
  RelatedDeviceObject = IoGetRelatedDeviceObject(a2);
  v12 = (__int64 *)(a3 + 104);
  SectorSize = RelatedDeviceObject->SectorSize;
  AlignmentRequirement = RelatedDeviceObject->AlignmentRequirement;
  v14 = *((_QWORD *)a2->FsContext + 4);
  v15 = *(_QWORD *)(a3 + 104);
  if ( v15 < 0 || (__int64)v14 < v15 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v9, v8, v10, v11);
  v16 = v14 - *v12;
  v17 = v14 >> 63;
  v18 = -1;
  if ( v14 >> 63 != (unsigned __int64)*v12 >> 63 && (_DWORD)v17 != (unsigned __int64)v16 > 0x7FFFFFFFFFFFFFFFLL )
  {
    v19 = -1073741675;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDiid(v17, v18, v10, *((_QWORD *)WPP_GLOBAL_Control + 8));
    }
    return v19;
  }
  if ( *(unsigned int *)(a3 + 112) < v16 )
  {
    v21 = 0;
    LODWORD(v16) = *(_DWORD *)(a3 + 112);
  }
  else
  {
    v20 = (unsigned __int64)v16 <= 0xFFFFFFFF;
    if ( v16 > 0xFFFFFFFFLL )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, 0x7FFFFFFFFFFFFFFFLL, v10, *v12);
      v20 = (unsigned __int64)v16 <= 0xFFFFFFFF;
    }
    if ( !v20 )
    {
      v19 = -1073741675;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDid(v17, v18, v10, *((_QWORD *)WPP_GLOBAL_Control + 8));
      }
      return v19;
    }
    v21 = 1;
  }
  if ( (*(_BYTE *)(a4 + 10) & 5) != 0 )
    v22 = *(char **)(a4 + 24);
  else
    v22 = (char *)MmMapLockedPagesSpecifyCache((PMDL)a4, 0, MmCached, 0, 0, 0x40000010u);
  v50 = v22;
  if ( !v22 )
  {
    v19 = -1073741670;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        526,
        v18,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        183,
        (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        212,
        154,
        (__int64)&a2->FileName);
    }
    return v19;
  }
  v23 = *v12;
  v24 = SectorSize - 1;
  if ( ((unsigned int)(SectorSize - 1) & (unsigned __int64)*v12) != 0 )
  {
    v19 = -1073740684;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v18,
        v23,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        184,
        (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        226,
        116);
    }
    return v19;
  }
  v25 = *(_DWORD *)(v53 + 112);
  if ( (v24 & v25) != 0 )
  {
    if ( !v21 )
    {
      v19 = -1073741811;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x40;
        WPP_RECORDER_AND_TRACE_SF_sDiiiid(
          v25,
          v18,
          v23,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          BugCheckOnFailure,
          Priority);
      }
      return v19;
    }
  }
  else
  {
    if ( !(_DWORD)SectorSize )
      goto LABEL_71;
    if ( a2->FsContext && (v24 & (unsigned int)v16) != 0 && v23 + (unsigned int)v16 != v14 )
      MicrosoftTelemetryAssertTriggeredMsgKM("bytesToWrite Not Aligned and Offset + BytesToWrite != FileSize");
    if ( (AlignmentRequirement & (unsigned int)v50) == 0 )
    {
LABEL_71:
      v19 = FltWriteFileEx(a1, a2, v12, ~v24 & (unsigned int)(v16 + SectorSize - 1), 0, 14, &v52, 0, 0, 0, a4);
      if ( (v19 & 0x80000000) != 0
        && ((BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v38) = BYTE1(xmmword_14001A3D0) & 4;
        LOBYTE(v39) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          522,
          v38,
          v39,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          10,
          190,
          (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          229,
          v19,
          (__int64)&a2->FileName);
      }
      return v19;
    }
  }
  v26 = a1;
  v53 = *v12;
  if ( (unsigned int)v16 <= 0x100000 )
    v27 = ~(SectorSize - 1) & ((unsigned int)v16 + SectorSize - 1);
  else
    v27 = 0x100000;
  PoolAlignedWithTag = FltAllocatePoolAlignedWithTag(a1, (POOL_TYPE)512, v27, 0x66774A50u);
  if ( PoolAlignedWithTag )
  {
    v32 = 0;
    if ( (_DWORD)v16 )
    {
      while ( 1 )
      {
        v33 = 0x100000;
        if ( (unsigned int)v16 < 0x100000 )
          v33 = v16;
        v34 = -(int)SectorSize & (v33 + SectorSize - 1);
        memmove(PoolAlignedWithTag, &v50[v32], v33);
        v19 = FltWriteFileEx(v26, a2, &v53, v34, PoolAlignedWithTag, 14, &v52, 0, 0, 0, 0);
        if ( (v19 & 0x80000000) != 0 )
          break;
        if ( (unsigned int)v16 < v34 )
          LODWORD(v16) = 0;
        else
          LODWORD(v16) = v16 - v34;
        v37 = v53 + v34;
        if ( v53 >= 0 )
        {
          v36 = -1;
          if ( (unsigned __int64)v53 >> 63 != v37 > 0x7FFFFFFFFFFFFFFFLL )
          {
            v53 = -1;
            if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v37) = BYTE1(xmmword_14001A3D0) & 0x40;
              LOBYTE(v36) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDiD(
                -1,
                v37,
                v36,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                BugCheckOnFailurea,
                Prioritya,
                v45,
                v46,
                v47,
                v48,
                -1,
                v34);
            }
            v19 = -1073741675;
            goto LABEL_70;
          }
        }
        v53 += v34;
        if ( v32 + v34 < v32 )
        {
          v19 = -1073741675;
          if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v37) = BYTE1(xmmword_14001A3D0) & 0x40;
            LOBYTE(v36) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDDd(
              526,
              v37,
              v36,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              14,
              189,
              (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
              198,
              -1,
              v34);
          }
          goto LABEL_70;
        }
        if ( !(_DWORD)v16 )
          goto LABEL_69;
        v26 = a1;
        v32 += v34;
      }
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v35) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v36) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v35,
          v36,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          187,
          (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          156,
          v19,
          (__int64)&a2->FileName);
      }
    }
    else
    {
LABEL_69:
      v19 = 0;
    }
LABEL_70:
    FltFreePoolAlignedWithTag(a1, PoolAlignedWithTag, 0x66774A50u);
  }
  else
  {
    v19 = -1073741670;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v28) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v30) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdPZ(v29, v28, v30, *((_QWORD *)WPP_GLOBAL_Control + 8), BugCheckOnFailure, Priority);
    }
  }
  return v19;
}

```

## disassembly

```asm
0x14003b724  mov     rax, rsp
0x14003b727  mov     [rax+20h], rbx
0x14003b72b  mov     [rax+18h], r8
0x14003b72f  mov     [rax+8], rcx
0x14003b733  push    rbp
0x14003b734  push    rsi
0x14003b735  push    rdi
0x14003b736  push    r12
0x14003b738  push    r13
0x14003b73a  push    r14
0x14003b73c  push    r15
0x14003b73e  sub     rsp, 90h
0x14003b745  mov     rcx, rdx; FileObject
0x14003b748  mov     dword ptr [rax+10h], 0
0x14003b74f  mov     r13, r9
0x14003b752  mov     rbx, r8
0x14003b755  mov     rbp, rdx
0x14003b758  call    cs:__imp_IoGetRelatedDeviceObject
0x14003b75f  nop     dword ptr [rax+rax+00h]
0x14003b764  lea     r14, [rbx+68h]
0x14003b768  movzx   r15d, word ptr [rax+130h]
0x14003b770  mov     eax, [rax+98h]
0x14003b776  mov     [rsp+0C8h+var_48], eax
0x14003b77d  mov     rax, [rbp+18h]
0x14003b781  mov     rsi, [rax+20h]
0x14003b785  mov     rax, [r14]
0x14003b788  test    rax, rax
0x14003b78b  js      short loc_14003B792
0x14003b78d  cmp     rsi, rax
0x14003b790  jge     short loc_14003B797
0x14003b792  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003b797  mov     r9, [r14]
0x14003b79a  mov     rdi, rsi
0x14003b79d  mov     rax, r9
0x14003b7a0  mov     rcx, rsi
0x14003b7a3  shr     rax, 3Fh
0x14003b7a7  sub     rdi, r9
0x14003b7aa  shr     rcx, 3Fh
0x14003b7ae  mov     rdx, 7FFFFFFFFFFFFFFFh
0x14003b7b8  cmp     ecx, eax
0x14003b7ba  jz      short loc_14003B816
0x14003b7bc  xor     eax, eax
0x14003b7be  cmp     rdi, rdx
0x14003b7c1  setnbe  al
0x14003b7c4  cmp     ecx, eax
0x14003b7c6  jz      short loc_14003B816
0x14003b7c8  mov     ebx, 0C0000095h
0x14003b7cd  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003b7d3  lea     rax, WPP_RECORDER_INITIALIZED
0x14003b7da  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003b7e1  setnz   r8b
0x14003b7e5  and     dl, 40h
0x14003b7e8  jnz     short loc_14003B7F3
0x14003b7ea  test    r8b, r8b
0x14003b7ed  jz      loc_14003BE63
0x14003b7f3  mov     dword ptr [rsp+0C8h+var_68], ebx
0x14003b7f7  mov     [rsp+0C8h+var_70], rsi
0x14003b7fc  mov     [rsp+0C8h+var_78], r9
0x14003b801  mov     r9, cs:WPP_GLOBAL_Control
0x14003b808  mov     r9, [r9+40h]
0x14003b80c  call    WPP_RECORDER_AND_TRACE_SF_sDiid
0x14003b811  jmp     loc_14003BE63
0x14003b816  mov     eax, [rbx+70h]
0x14003b819  mov     ebx, 0FFFFFFFFh
0x14003b81e  cmp     rax, rdi
0x14003b821  jl      short loc_14003B880
0x14003b823  cmp     rdi, rbx
0x14003b826  jle     short loc_14003B830
0x14003b828  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003b82d  cmp     rdi, rbx
0x14003b830  ja      short loc_14003B837
0x14003b832  mov     r12b, 1
0x14003b835  jmp     short loc_14003B885
0x14003b837  mov     ebx, 0C0000095h
0x14003b83c  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003b842  lea     rax, WPP_RECORDER_INITIALIZED
0x14003b849  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003b850  setnz   r8b
0x14003b854  and     dl, 40h
0x14003b857  jnz     short loc_14003B862
0x14003b859  test    r8b, r8b
0x14003b85c  jz      loc_14003BE63
0x14003b862  mov     r9, cs:WPP_GLOBAL_Control
0x14003b869  mov     dword ptr [rsp+0C8h+var_70], ebx
0x14003b86d  mov     [rsp+0C8h+var_78], rdi
0x14003b872  mov     r9, [r9+40h]
0x14003b876  call    WPP_RECORDER_AND_TRACE_SF_sDid
0x14003b87b  jmp     loc_14003BE63
0x14003b880  xor     r12b, r12b
0x14003b883  mov     edi, eax
0x14003b885  test    byte ptr [r13+0Ah], 5
0x14003b88a  jz      short loc_14003B892
0x14003b88c  mov     rax, [r13+18h]
0x14003b890  jmp     short loc_14003B8BA
0x14003b892  xor     r9d, r9d; RequestedAddress
0x14003b895  mov     [rsp+0C8h+Priority], 40000010h; Priority
0x14003b89d  xor     edx, edx; AccessMode
0x14003b89f  mov     [rsp+0C8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14003b8a7  mov     rcx, r13; MemoryDescriptorList
0x14003b8aa  lea     r8d, [r9+1]; CacheType
0x14003b8ae  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003b8b5  nop     dword ptr [rax+rax+00h]
0x14003b8ba  xor     r11d, r11d
0x14003b8bd  mov     [rsp+0C8h+var_40], rax
0x14003b8c5  test    rax, rax
0x14003b8c8  jnz     short loc_14003B93B
0x14003b8ca  mov     ebx, 0C000009Ah
0x14003b8cf  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003b8d5  lea     rax, WPP_RECORDER_INITIALIZED
0x14003b8dc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003b8e3  setnz   r8b
0x14003b8e7  and     dl, 40h
0x14003b8ea  jnz     short loc_14003B8F5
0x14003b8ec  test    r8b, r8b
0x14003b8ef  jz      loc_14003BE63
0x14003b8f5  lea     rax, [rbp+58h]
0x14003b8f9  mov     ecx, 20Eh
0x14003b8fe  mov     [rsp+0C8h+var_70], rax
0x14003b903  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003b90a  mov     dword ptr [rsp+0C8h+var_78], ebx
0x14003b90e  mov     dword ptr [rsp+0C8h+var_80], 1ED4h
0x14003b916  mov     [rsp+0C8h+var_88], rax
0x14003b91b  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003b922  mov     [rsp+0C8h+var_90], rax
0x14003b927  mov     word ptr [rsp+0C8h+var_98], 0B7h
0x14003b92e  mov     [rsp+0C8h+Priority], 0Eh
0x14003b936  jmp     loc_14003BE4E
0x14003b93b  mov     r8, [r14]
0x14003b93e  lea     ebx, [r15-1]
0x14003b942  mov     eax, ebx
0x14003b944  test    r8, rax
0x14003b947  jz      short loc_14003B9C6
0x14003b949  mov     ebx, 0C0000474h
0x14003b94e  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003b954  lea     rax, WPP_RECORDER_INITIALIZED
0x14003b95b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003b962  setnz   r8b
0x14003b966  and     dl, 40h
0x14003b969  jnz     short loc_14003B974
0x14003b96b  test    r8b, r8b
0x14003b96e  jz      loc_14003BE63
0x14003b974  mov     r9, cs:WPP_GLOBAL_Control
0x14003b97b  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003b982  mov     dword ptr [rsp+0C8h+var_78], ebx
0x14003b986  mov     ecx, 20Eh
0x14003b98b  mov     dword ptr [rsp+0C8h+var_80], 1EE2h
0x14003b993  mov     [rsp+0C8h+var_88], rax
0x14003b998  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003b99f  mov     r9, [r9+40h]
0x14003b9a3  mov     [rsp+0C8h+var_90], rax
0x14003b9a8  mov     word ptr [rsp+0C8h+var_98], 0B8h
0x14003b9af  mov     [rsp+0C8h+Priority], 0Eh
0x14003b9b7  mov     byte ptr [rsp+0C8h+BugCheckOnFailure], 2
0x14003b9bc  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003b9c1  jmp     loc_14003BE63
0x14003b9c6  mov     rcx, [rsp+0C8h+arg_10]
0x14003b9ce  mov     ecx, [rcx+70h]
0x14003b9d1  test    ecx, ebx
0x14003b9d3  jz      short loc_14003BA39
0x14003b9d5  test    r12b, r12b
0x14003b9d8  jnz     loc_14003BA7A
0x14003b9de  mov     ebx, 0C000000Dh
0x14003b9e3  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003b9e9  lea     rax, WPP_RECORDER_INITIALIZED
0x14003b9f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003b9f7  setnz   r10b
0x14003b9fb  and     dl, 40h
0x14003b9fe  jnz     short loc_14003BA09
0x14003ba00  test    r10b, r10b
0x14003ba03  jz      loc_14003BE63
0x14003ba09  mov     r9, cs:WPP_GLOBAL_Control
0x14003ba10  lea     rax, [r8+rcx]
0x14003ba14  mov     [rsp+0C8h+var_60], rsi
0x14003ba19  mov     [rsp+0C8h+var_68], rax
0x14003ba1e  mov     [rsp+0C8h+var_70], rcx
0x14003ba23  mov     r9, [r9+40h]
0x14003ba27  mov     [rsp+0C8h+var_78], r8
0x14003ba2c  mov     r8b, r10b
0x14003ba2f  call    WPP_RECORDER_AND_TRACE_SF_sDiiiid
0x14003ba34  jmp     loc_14003BE63
0x14003ba39  test    r15d, r15d
0x14003ba3c  jz      loc_14003BD91
0x14003ba42  cmp     [rbp+18h], r11
0x14003ba46  jz      short loc_14003BA65
0x14003ba48  test    edi, ebx
0x14003ba4a  jz      short loc_14003BA65
0x14003ba4c  mov     eax, edi
0x14003ba4e  add     rax, r8
0x14003ba51  cmp     rax, rsi
0x14003ba54  jz      short loc_14003BA65
0x14003ba56  lea     rcx, aBytestowriteNo; "bytesToWrite Not Aligned and Offset + B"...
0x14003ba5d  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003ba62  xor     r11d, r11d
0x14003ba65  mov     eax, [rsp+0C8h+var_48]
0x14003ba6c  test    [rsp+0C8h+var_40], rax
0x14003ba74  jz      loc_14003BD91
0x14003ba7a  mov     rax, [r14]
0x14003ba7d  mov     r9d, 66774A50h; Tag
0x14003ba83  mov     rbx, [rsp+0C8h+Instance]
0x14003ba8b  mov     edx, 200h; PoolType
0x14003ba90  mov     [rsp+0C8h+arg_10], rax
0x14003ba98  mov     rcx, rbx; Instance
0x14003ba9b  mov     eax, 100000h
0x14003baa0  cmp     edi, eax
0x14003baa2  jbe     short loc_14003BAAB
0x14003baa4  mov     esi, eax
0x14003baa6  mov     r8d, eax
0x14003baa9  jmp     short loc_14003BAC1
0x14003baab  mov     eax, edi
0x14003baad  lea     rsi, [r15-1]
0x14003bab1  add     rsi, rax
0x14003bab4  lea     rax, [r15-1]
0x14003bab8  not     rax
0x14003babb  and     rsi, rax
0x14003babe  mov     r8, rsi; NumberOfBytes
0x14003bac1  call    cs:__imp_FltAllocatePoolAlignedWithTag
0x14003bac8  nop     dword ptr [rax+rax+00h]
0x14003bacd  mov     r12, rax
0x14003bad0  test    rax, rax
0x14003bad3  jnz     short loc_14003BB23
0x14003bad5  mov     ebx, 0C000009Ah
0x14003bada  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003bae0  lea     rax, WPP_RECORDER_INITIALIZED
0x14003bae7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003baee  setnz   r8b
0x14003baf2  and     dl, 40h
0x14003baf5  jnz     short loc_14003BB00
0x14003baf7  test    r8b, r8b
0x14003bafa  jz      loc_14003BE63
0x14003bb00  mov     r9, cs:WPP_GLOBAL_Control
0x14003bb07  lea     rax, [rbp+58h]
0x14003bb0b  mov     [rsp+0C8h+var_68], rax
0x14003bb10  mov     [rsp+0C8h+var_70], rsi
0x14003bb15  mov     r9, [r9+40h]
0x14003bb19  call    WPP_RECORDER_AND_TRACE_SF_sDdPZ
0x14003bb1e  jmp     loc_14003BE63
0x14003bb23  xor     r14d, r14d
0x14003bb26  test    edi, edi
0x14003bb28  jz      loc_14003BD6D
0x14003bb2e  mov     r13d, r15d
0x14003bb31  neg     r13d
0x14003bb34  mov     eax, 100000h
0x14003bb39  mov     edx, r14d
0x14003bb3c  cmp     edi, eax
0x14003bb3e  lea     esi, [r15-1]
0x14003bb42  mov     rcx, r12; void *
0x14003bb45  cmovb   eax, edi
0x14003bb48  add     rdx, [rsp+0C8h+var_40]; Src
0x14003bb50  add     esi, eax
0x14003bb52  mov     r8d, eax; Size
0x14003bb55  and     esi, r13d
0x14003bb58  call    memmove
0x14003bb5d  mov     [rsp+0C8h+var_78], 0
0x14003bb66  lea     rax, [rsp+0C8h+arg_8]
0x14003bb6e  mov     [rsp+0C8h+var_80], 0
0x14003bb77  lea     r8, [rsp+0C8h+arg_10]
0x14003bb7f  mov     [rsp+0C8h+var_88], 0
0x14003bb88  mov     r9d, esi
0x14003bb8b  mov     [rsp+0C8h+var_90], 0
0x14003bb94  mov     rdx, rbp
0x14003bb97  mov     [rsp+0C8h+var_98], rax
0x14003bb9c  mov     rcx, rbx
0x14003bb9f  mov     [rsp+0C8h+Priority], 0Eh
0x14003bba7  mov     qword ptr [rsp+0C8h+BugCheckOnFailure], r12
0x14003bbac  call    cs:__imp_FltWriteFileEx
0x14003bbb3  nop     dword ptr [rax+rax+00h]
0x14003bbb8  mov     ebx, eax
0x14003bbba  test    eax, eax
0x14003bbbc  js      loc_14003BCF3
0x14003bbc2  cmp     edi, esi
0x14003bbc4  jb      short loc_14003BBCA
0x14003bbc6  sub     edi, esi
0x14003bbc8  jmp     short loc_14003BBCC
0x14003bbca  xor     edi, edi
0x14003bbcc  mov     rcx, [rsp+0C8h+arg_10]
0x14003bbd4  mov     edx, esi
0x14003bbd6  add     rdx, rcx
0x14003bbd9  shr     rcx, 3Fh
0x14003bbdd  test    ecx, ecx
0x14003bbdf  jnz     short loc_14003BBF7
0x14003bbe1  xor     eax, eax
0x14003bbe3  mov     r8, 7FFFFFFFFFFFFFFFh
0x14003bbed  cmp     rdx, r8
0x14003bbf0  setnbe  al
0x14003bbf3  cmp     ecx, eax
0x14003bbf5  jnz     short loc_14003BC20
0x14003bbf7  lea     eax, [r14+rsi]
0x14003bbfb  mov     [rsp+0C8h+arg_10], rdx
0x14003bc03  cmp     eax, r14d
0x14003bc06  jb      short loc_14003BC71
0x14003bc08  test    edi, edi
0x14003bc0a  jz      loc_14003BD6D
0x14003bc10  mov     rbx, [rsp+0C8h+Instance]
0x14003bc18  mov     r14d, eax
0x14003bc1b  jmp     loc_14003BB34
0x14003bc20  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14003bc24  mov     [rsp+0C8h+arg_10], rcx
0x14003bc2c  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003bc32  lea     rax, WPP_RECORDER_INITIALIZED
0x14003bc39  cmp     cs:WPP_RECORDER_INITIALIZED, rax
  ... truncated ...
```
