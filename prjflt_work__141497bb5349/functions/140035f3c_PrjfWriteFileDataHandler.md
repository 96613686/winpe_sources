# PrjfWriteFileDataHandler

- ea: `0x140035f3c`
- end: `0x1400368bb`
- name: `PrjfWriteFileDataHandler`
- size: `2431`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x140031a00`

## callees

- `0x140001008`
- `0x140003e6c`
- `0x14000ba20`
- `0x14000d008`
- `0x14000d128`
- `0x14000d754`
- `0x140010a70`
- `0x140010c3c`
- `0x140011158`
- `0x140021f8c`
- `0x140035f3c`
- `0x14003b724`
- `0x14003ee54`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14003687f`
- `ntoskrnl!IoFreeMdl` at `0x14003687f`
- `ntoskrnl!MmUnlockPages` at `0x14003686b`
- `ntoskrnl!MmUnlockPages` at `0x14003686b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14003661b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14003661b`
- `ntoskrnl!IoAllocateMdl` at `0x14003655c`
- `ntoskrnl!IoAllocateMdl` at `0x14003655c`
- `ntoskrnl!ProbeForRead` at `0x14003653d`
- `ntoskrnl!ProbeForRead` at `0x14003653d`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400361b8`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400361b8`
- `ntoskrnl!ObfReferenceObject` at `0x140036245`
- `ntoskrnl!ObfReferenceObject` at `0x140036245`
- `ntoskrnl!ObfDereferenceObject` at `0x14003684a`
- `ntoskrnl!ObfDereferenceObject` at `0x14003684a`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036110`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036110`
- `FLTMGR!FltWriteFileEx` at `0x1400366db`
- `FLTMGR!FltWriteFileEx` at `0x1400366db`
- `FLTMGR!FltReleaseResource` at `0x1400361cf`
- `FLTMGR!FltReleaseResource` at `0x140036267`
- `FLTMGR!FltReleaseResource` at `0x1400361cf`
- `FLTMGR!FltReleaseResource` at `0x140036267`
- `FLTMGR!FltAcquireResourceShared` at `0x1400361a1`
- `FLTMGR!FltAcquireResourceShared` at `0x1400361a1`

## pseudocode

```c
__int64 __fastcall PrjfWriteFileDataHandler(struct _FLT_INSTANCE *a1, __int64 a2, unsigned int a3)
{
  _QWORD *v4; // r13
  char v5; // r14
  struct _MDL *v6; // r12
  __int64 v7; // rdx
  int v8; // esi
  char v9; // r10
  _QWORD *UnionContextByVirtualizationInstanceInfo; // rax
  struct _KPROCESS *v11; // rbx
  int v12; // r8d
  _QWORD *v13; // rax
  _QWORD *v14; // rsi
  int v15; // r8d
  __int64 v16; // r14
  int v17; // ecx
  int v18; // r8d
  __int64 v19; // r9
  __int64 v20; // r9
  __int64 v21; // r8
  unsigned __int64 v22; // rdx
  unsigned int v23; // esi
  struct _MDL *Mdl; // rax
  int v25; // r8d
  int v26; // eax
  int v27; // r8d
  int v28; // eax
  int v29; // r8d
  __int16 v31; // [rsp+30h] [rbp-128h]
  char v32; // [rsp+48h] [rbp-110h]
  char v33; // [rsp+80h] [rbp-D8h]
  struct _FLT_INSTANCE *v34; // [rsp+88h] [rbp-D0h] BYREF
  PVOID Object; // [rsp+90h] [rbp-C8h]
  _DWORD v36[2]; // [rsp+98h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-B8h] BYREF
  struct _MDL *v38; // [rsp+A8h] [rbp-B0h]
  _QWORD *v39; // [rsp+B0h] [rbp-A8h]
  char v40[32]; // [rsp+C0h] [rbp-98h] BYREF
  struct _FLT_INSTANCE **v41; // [rsp+E0h] [rbp-78h]
  __int64 v42; // [rsp+E8h] [rbp-70h]
  _DWORD *v43; // [rsp+F0h] [rbp-68h]
  __int64 v44; // [rsp+F8h] [rbp-60h]
  __int64 v45; // [rsp+100h] [rbp-58h]
  _DWORD v46[2]; // [rsp+108h] [rbp-50h] BYREF
  __int64 *v47; // [rsp+110h] [rbp-48h]
  __int64 v48; // [rsp+118h] [rbp-40h]

  v34 = a1;
  v4 = 0;
  Object = 0;
  v36[0] = 0;
  v5 = 0;
  v33 = 0;
  v6 = 0;
  v38 = 0;
  if ( *(_DWORD *)a2 <= a3 )
  {
    if ( *(_DWORD *)a2 >= 0x78u )
    {
      UnionContextByVirtualizationInstanceInfo = PrjfGetUnionContextByVirtualizationInstanceInfo(
                                                   (__int128 *)(a2 + 8),
                                                   a1);
      v4 = UnionContextByVirtualizationInstanceInfo;
      v39 = UnionContextByVirtualizationInstanceInfo;
      if ( UnionContextByVirtualizationInstanceInfo )
      {
        v11 = (struct _KPROCESS *)UnionContextByVirtualizationInstanceInfo[4];
        if ( IoGetCurrentProcess() != v11 )
        {
          v8 = -1073741790;
          LOBYTE(v7) = BYTE1(xmmword_14001A3D0) & 0x40;
          if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sD(
              526,
              v7,
              v12,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              14,
              54,
              (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
              194);
          }
          goto LABEL_59;
        }
        FltAcquireResourceShared((PERESOURCE)(v4 + 12));
        v13 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(v4 + 25), (PVOID)(a2 + 88));
        v14 = v13;
        if ( !v13 )
        {
          FltReleaseResource((PERESOURCE)(v4 + 12));
          v8 = -1073741816;
          LOBYTE(v7) = BYTE1(xmmword_14001A3D0) & 0x40;
          if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              526,
              v7,
              v15,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              14,
              55,
              (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
              207,
              8);
          }
          goto LABEL_59;
        }
        v16 = v13[2];
        Object = (PVOID)v16;
        ObfReferenceObject((PVOID)v16);
        v8 = PrjfValidateHandleAccess(v14[3], 6, v16);
        FltReleaseResource((PERESOURCE)(v4 + 12));
        if ( v8 >= 0 )
        {
          v19 = *(_QWORD *)(v16 + 24);
          if ( v19 )
          {
            v20 = *(_QWORD *)(v19 + 32);
            v21 = *(_QWORD *)(a2 + 104);
            if ( v21 < 0 || v21 > v20 )
            {
              v7 = 3221225485LL;
              v8 = -1073741811;
              if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                LOBYTE(v7) = BYTE1(xmmword_14001A3D0) & 0x40;
                LOBYTE(v17) = BYTE1(xmmword_14001A3D0) & 0x40;
                WPP_RECORDER_AND_TRACE_SF_sDdiiZ(v17, v7, v21, *((_QWORD *)WPP_GLOBAL_Control + 8));
              }
            }
            else
            {
              v22 = *(unsigned int *)(a2 + 112);
              v37 = v22;
              v23 = v20 - v21;
              if ( v22 <= v20 - v21 )
              {
                v23 = v37;
              }
              else if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0
                     || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                LOBYTE(v22) = BYTE9(xmmword_14001A3D0) & 0x40;
                WPP_RECORDER_AND_TRACE_SF_sDsiLiLZ(v16 + 88, v22, v21, *((_QWORD *)WPP_GLOBAL_Control + 8));
              }
              ProbeForRead(*(volatile void **)(a2 + 120), *(unsigned int *)(a2 + 112), 1u);
              Mdl = IoAllocateMdl(*(PVOID *)(a2 + 120), *(_DWORD *)(a2 + 112), 0, 0, 0);
              v6 = Mdl;
              v38 = Mdl;
              if ( !Mdl )
              {
                v8 = -1073741670;
                v36[1] = -1073741670;
                LOBYTE(v7) = BYTE1(xmmword_14001A3D0) & 0x40;
                if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                  || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v25) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                  WPP_RECORDER_AND_TRACE_SF_sDdZ(
                    526,
                    v7,
                    v25,
                    *((_QWORD *)WPP_GLOBAL_Control + 8),
                    2,
                    14,
                    60,
                    (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                    (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                    78,
                    154,
                    (__int64)Object + 88);
                }
                v5 = 0;
                goto LABEL_59;
              }
              MmProbeAndLockPages(Mdl, 0, IoReadAccess);
              v33 = 1;
              if ( (*(_DWORD *)(v16 + 80) & 8) != 0 )
              {
                v26 = PrjfManageHydrationOnNonCachedHandle(v34, v16, a2, v6);
                v8 = v26;
                if ( v26 < 0 )
                {
                  LOBYTE(v7) = BYTE1(xmmword_14001A3D0) & 0x40;
                  if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                    || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                    WPP_RECORDER_AND_TRACE_SF_sDL(
                      526,
                      v7,
                      v27,
                      *((_QWORD *)WPP_GLOBAL_Control + 8),
                      2,
                      14,
                      62,
                      (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                      112,
                      v26);
                  }
                }
              }
              else
              {
                v28 = FltWriteFileEx(v34, v16, a2 + 104, v23, 0, 4, v36, 0, 0, 0, v6);
                v8 = v28;
                if ( v28 < 0 )
                {
                  LOBYTE(v7) = BYTE1(xmmword_14001A3D0) & 4;
                  if ( (BYTE1(xmmword_14001A3D0) & 4) != 0
                    || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                    WPP_RECORDER_AND_TRACE_SF_sDdZ(
                      522,
                      v7,
                      v29,
                      *((_QWORD *)WPP_GLOBAL_Control + 8),
                      2,
                      10,
                      63,
                      (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                      140,
                      v28,
                      v16 + 88);
                  }
                }
              }
            }
          }
          else
          {
            v8 = -1073741637;
            LOBYTE(v7) = BYTE1(xmmword_14001A3D0) & 0x40;
            if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDdZ(
                526,
                v7,
                v18,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                14,
                57,
                (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                249,
                187,
                v16 + 88);
            }
            if ( (unsigned int)dword_14001A068 > 5 )
            {
              v7 = 0x400000000000LL;
              if ( (qword_14001A078 & 0x400000000000LL) != 0 && (qword_14001A080 & 0x400000000000LL) == qword_14001A080 )
              {
                LODWORD(v34) = (*(_DWORD *)(v16 + 80) >> 3) & 1;
                v41 = &v34;
                v42 = 4;
                v43 = v46;
                v44 = 2;
                v45 = *(_QWORD *)(v16 + 96);
                v46[0] = *(unsigned __int16 *)(v16 + 88);
                v46[1] = 0;
                v37 = 0x1000000;
                v47 = &v37;
                v48 = 8;
                tlgWriteTransfer_EtwWriteTransfer(&dword_14001A068, &dword_1400165A4, 0, 0, 6, v40);
              }
            }
          }
        }
        else
        {
          LOBYTE(v7) = BYTE1(xmmword_14001A3D0) & 0x40;
          if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              526,
              v7,
              v18,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              14,
              56,
              (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
              235,
              v8);
          }
        }
        v5 = v33;
        goto LABEL_59;
      }
      v7 = 3221225485LL;
      v8 = -1073741811;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      v9 = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v32 = -74;
        v31 = 53;
        goto LABEL_5;
      }
    }
    else
    {
      v7 = 3221225485LL;
      v8 = -1073741811;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      v9 = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v32 = -85;
        v31 = 52;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v7 = 3221225485LL;
    v8 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    v9 = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v32 = -95;
      v31 = 51;
LABEL_5:
      LOBYTE(v7) = v9;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v7,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        v31,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        v32,
        13);
    }
  }
LABEL_59:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v4 )
    PrjfReleaseUnionContext((char *)v4, v7);
  if ( v5 )
    MmUnlockPages(v6);
  if ( v6 )
    IoFreeMdl(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140035f3c  mov     [rsp+arg_10], rbx
0x140035f41  mov     [rsp+arg_18], rsi
0x140035f46  push    rdi
0x140035f47  push    r12
0x140035f49  push    r13
0x140035f4b  push    r14
0x140035f4d  push    r15
0x140035f4f  sub     rsp, 130h
0x140035f56  mov     rax, cs:__security_cookie
0x140035f5d  xor     rax, rsp
0x140035f60  mov     [rsp+158h+var_38], rax
0x140035f68  mov     r15, rdx
0x140035f6b  mov     rdx, rcx
0x140035f6e  mov     [rsp+158h+var_D0], rcx
0x140035f76  xor     edi, edi
0x140035f78  mov     r13d, edi
0x140035f7b  mov     [rsp+158h+Object], rdi
0x140035f83  mov     [rsp+158h+var_C0], edi
0x140035f8a  mov     r14b, dil
0x140035f8d  mov     [rsp+158h+var_D8], dil
0x140035f95  mov     r12d, edi
0x140035f98  mov     [rsp+158h+var_B0], rdi
0x140035fa0  mov     eax, [r15]
0x140035fa3  cmp     eax, r8d
0x140035fa6  jbe     loc_140036030
0x140035fac  mov     edx, 0C000000Dh
0x140035fb1  mov     esi, edx
0x140035fb3  mov     r10b, byte ptr cs:xmmword_14001A3D0+1
0x140035fba  lea     rbx, WPP_RECORDER_INITIALIZED
0x140035fc1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140035fc8  setnz   r8b
0x140035fcc  and     r10b, 40h
0x140035fd0  jnz     short loc_140035FDB
0x140035fd2  test    r8b, r8b
0x140035fd5  jz      loc_14003683D
0x140035fdb  mov     dword ptr [rsp+158h+var_108], edx
0x140035fdf  mov     dword ptr [rsp+158h+var_110], 5A1h
0x140035fe7  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140035fee  mov     [rsp+158h+var_118], rax
0x140035ff3  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140035ffa  mov     [rsp+158h+var_120], rax
0x140035fff  mov     word ptr [rsp+158h+var_128], 33h ; '3'
0x140036006  mov     dl, r10b
0x140036009  mov     ecx, 20Eh
0x14003600e  mov     r9, cs:WPP_GLOBAL_Control
0x140036015  mov     dword ptr [rsp+158h+var_130], 0Eh
0x14003601d  mov     r9, [r9+40h]
0x140036021  mov     byte ptr [rsp+158h+Irp], 2
0x140036026  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003602b  jmp     loc_14003683D
0x140036030  cmp     eax, 78h ; 'x'
0x140036033  jnb     short loc_140036094
0x140036035  mov     edx, 0C000000Dh
0x14003603a  mov     esi, edx
0x14003603c  mov     r10b, byte ptr cs:xmmword_14001A3D0+1
0x140036043  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003604a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140036051  setnz   r8b
0x140036055  and     r10b, 40h
0x140036059  jnz     short loc_140036064
0x14003605b  test    r8b, r8b
0x14003605e  jz      loc_14003683D
0x140036064  mov     dword ptr [rsp+158h+var_108], edx
0x140036068  mov     dword ptr [rsp+158h+var_110], 5ABh
0x140036070  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140036077  mov     [rsp+158h+var_118], rax
0x14003607c  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140036083  mov     [rsp+158h+var_120], rax
0x140036088  mov     word ptr [rsp+158h+var_128], 34h ; '4'
0x14003608f  jmp     loc_140036006
0x140036094  lea     rcx, [r15+8]
0x140036098  call    PrjfGetUnionContextByVirtualizationInstanceInfo
0x14003609d  mov     r13, rax
0x1400360a0  mov     [rsp+158h+var_A8], rax
0x1400360a8  test    rax, rax
0x1400360ab  jnz     short loc_14003610C
0x1400360ad  mov     edx, 0C000000Dh
0x1400360b2  mov     esi, edx
0x1400360b4  mov     r10b, byte ptr cs:xmmword_14001A3D0+1
0x1400360bb  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400360c2  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400360c9  setnz   r8b
0x1400360cd  and     r10b, 40h
0x1400360d1  jnz     short loc_1400360DC
0x1400360d3  test    r8b, r8b
0x1400360d6  jz      loc_14003683D
0x1400360dc  mov     dword ptr [rsp+158h+var_108], edx
0x1400360e0  mov     dword ptr [rsp+158h+var_110], 5B6h
0x1400360e8  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400360ef  mov     [rsp+158h+var_118], rax
0x1400360f4  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400360fb  mov     [rsp+158h+var_120], rax
0x140036100  mov     word ptr [rsp+158h+var_128], 35h ; '5'
0x140036107  jmp     loc_140036006
0x14003610c  mov     rbx, [rax+20h]
0x140036110  call    cs:__imp_IoGetCurrentProcess
0x140036117  nop     dword ptr [rax+rax+00h]
0x14003611c  cmp     rax, rbx
0x14003611f  jz      short loc_14003619A
0x140036121  mov     esi, 0C0000022h
0x140036126  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003612c  lea     rbx, WPP_RECORDER_INITIALIZED
0x140036133  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003613a  setnz   r8b
0x14003613e  and     dl, 40h
0x140036141  jnz     short loc_14003614C
0x140036143  test    r8b, r8b
0x140036146  jz      loc_14003683D
0x14003614c  mov     ecx, 20Eh
0x140036151  mov     dword ptr [rsp+158h+var_110], 5C2h
0x140036159  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140036160  mov     [rsp+158h+var_118], rax
0x140036165  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14003616c  mov     [rsp+158h+var_120], rax
0x140036171  mov     word ptr [rsp+158h+var_128], 36h ; '6'
0x140036178  mov     dword ptr [rsp+158h+var_130], 0Eh
0x140036180  mov     byte ptr [rsp+158h+Irp], 2
0x140036185  mov     r9, cs:WPP_GLOBAL_Control
0x14003618c  mov     r9, [r9+40h]
0x140036190  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140036195  jmp     loc_14003683D
0x14003619a  lea     rbx, [r13+60h]
0x14003619e  mov     rcx, rbx; Resource
0x1400361a1  call    cs:__imp_FltAcquireResourceShared
0x1400361a8  nop     dword ptr [rax+rax+00h]
0x1400361ad  lea     rdx, [r15+58h]; Buffer
0x1400361b1  lea     rcx, [r13+0C8h]; Table
0x1400361b8  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1400361bf  nop     dword ptr [rax+rax+00h]
0x1400361c4  mov     rsi, rax
0x1400361c7  test    rax, rax
0x1400361ca  jnz     short loc_140036236
0x1400361cc  mov     rcx, rbx; Resource
0x1400361cf  call    cs:__imp_FltReleaseResource
0x1400361d6  nop     dword ptr [rax+rax+00h]
0x1400361db  mov     esi, 0C0000008h
0x1400361e0  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400361e6  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400361ed  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400361f4  setnz   r8b
0x1400361f8  and     dl, 40h
0x1400361fb  jnz     short loc_140036206
0x1400361fd  test    r8b, r8b
0x140036200  jz      loc_14003683D
0x140036206  mov     dword ptr [rsp+158h+var_108], esi
0x14003620a  mov     dword ptr [rsp+158h+var_110], 5CFh
0x140036212  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140036219  mov     [rsp+158h+var_118], rax
0x14003621e  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140036225  mov     [rsp+158h+var_120], rax
0x14003622a  mov     word ptr [rsp+158h+var_128], 37h ; '7'
0x140036231  jmp     loc_140036009
0x140036236  mov     r14, [rax+10h]
0x14003623a  mov     [rsp+158h+Object], r14
0x140036242  mov     rcx, r14; Object
0x140036245  call    cs:__imp_ObfReferenceObject
0x14003624c  nop     dword ptr [rax+rax+00h]
0x140036251  mov     r8, r14
0x140036254  mov     edx, 6
0x140036259  mov     rcx, [rsi+18h]
0x14003625d  call    PrjfValidateHandleAccess
0x140036262  mov     esi, eax
0x140036264  mov     rcx, rbx; Resource
0x140036267  call    cs:__imp_FltReleaseResource
0x14003626e  nop     dword ptr [rax+rax+00h]
0x140036273  test    esi, esi
0x140036275  jns     short loc_1400362EF
0x140036277  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003627d  lea     rbx, WPP_RECORDER_INITIALIZED
0x140036284  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003628b  setnz   r8b
0x14003628f  and     dl, 40h
0x140036292  jnz     short loc_14003629D
0x140036294  test    r8b, r8b
0x140036297  jz      loc_140036835
0x14003629d  mov     dword ptr [rsp+158h+var_108], esi
0x1400362a1  mov     dword ptr [rsp+158h+var_110], 5EBh
0x1400362a9  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400362b0  mov     [rsp+158h+var_118], rax
0x1400362b5  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400362bc  mov     [rsp+158h+var_120], rax
0x1400362c1  mov     word ptr [rsp+158h+var_128], 38h ; '8'
0x1400362c8  mov     ecx, 20Eh
0x1400362cd  mov     dword ptr [rsp+158h+var_130], 0Eh
0x1400362d5  mov     byte ptr [rsp+158h+Irp], 2
0x1400362da  mov     r9, cs:WPP_GLOBAL_Control
0x1400362e1  mov     r9, [r9+40h]
0x1400362e5  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400362ea  jmp     loc_140036835
0x1400362ef  mov     r9, [r14+18h]
0x1400362f3  test    r9, r9
0x1400362f6  jnz     loc_14003647B
0x1400362fc  mov     esi, 0C00000BBh
0x140036301  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140036307  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003630e  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140036315  setnz   r8b
0x140036319  and     dl, 40h
0x14003631c  jnz     short loc_140036323
0x14003631e  test    r8b, r8b
0x140036321  jz      short loc_140036379
0x140036323  lea     rax, [r14+58h]
0x140036327  mov     ecx, 20Eh
0x14003632c  mov     [rsp+158h+var_100], rax
0x140036331  mov     dword ptr [rsp+158h+var_108], esi
0x140036335  mov     dword ptr [rsp+158h+var_110], 5F9h
0x14003633d  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140036344  mov     [rsp+158h+var_118], rax
0x140036349  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140036350  mov     [rsp+158h+var_120], rax
0x140036355  mov     word ptr [rsp+158h+var_128], 39h ; '9'
0x14003635c  mov     dword ptr [rsp+158h+var_130], 0Eh
0x140036364  mov     byte ptr [rsp+158h+Irp], 2
0x140036369  mov     r9, cs:WPP_GLOBAL_Control
0x140036370  mov     r9, [r9+40h]
0x140036374  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140036379  mov     eax, cs:dword_14001A068
0x14003637f  cmp     eax, 5
0x140036382  jbe     loc_140036835
0x140036388  mov     rcx, cs:qword_14001A080
0x14003638f  mov     rax, cs:qword_14001A078
0x140036396  mov     rdx, 400000000000h
0x1400363a0  test    rdx, rax
0x1400363a3  jz      loc_140036835
0x1400363a9  mov     rax, rcx
0x1400363ac  and     rax, rdx
0x1400363af  cmp     rax, rcx
0x1400363b2  jnz     loc_140036835
0x1400363b8  mov     eax, [r14+50h]
0x1400363bc  shr     eax, 3
0x1400363bf  and     eax, 1
0x1400363c2  mov     dword ptr [rsp+158h+var_D0], eax
0x1400363c9  lea     rax, [rsp+158h+var_D0]
0x1400363d1  mov     [rsp+158h+var_78], rax
0x1400363d9  mov     [rsp+158h+var_70], 4
0x1400363e5  lea     rax, [rsp+158h+var_50]
0x1400363ed  mov     [rsp+158h+var_68], rax
0x1400363f5  mov     [rsp+158h+var_60], 2
0x140036401  mov     rax, [r14+60h]
0x140036405  mov     [rsp+158h+var_58], rax
0x14003640d  movzx   eax, word ptr [r14+58h]
0x140036412  mov     [rsp+158h+var_50], eax
0x140036419  mov     [rsp+158h+var_4C], edi
0x140036420  mov     [rsp+158h+var_B8], 1000000h
0x14003642c  lea     rax, [rsp+158h+var_B8]
0x140036434  mov     [rsp+158h+var_48], rax
0x14003643c  mov     [rsp+158h+var_40], 8
0x140036448  lea     rax, [rsp+158h+var_98]
0x140036450  mov     [rsp+158h+var_130], rax
0x140036455  mov     dword ptr [rsp+158h+Irp], 6
0x14003645d  xor     r9d, r9d
0x140036460  xor     r8d, r8d
0x140036463  lea     rdx, dword_1400165A4
0x14003646a  lea     rcx, dword_14001A068
0x140036471  call    _tlgWriteTransfer_EtwWriteTransfer
0x140036476  jmp     loc_140036835
0x14003647b  mov     r9, [r9+20h]
0x14003647f  mov     r8, [r15+68h]
0x140036483  test    r8, r8
0x140036486  js      loc_1400367E0
0x14003648c  cmp     r8, r9
0x14003648f  jg      loc_1400367E0
0x140036495  mov     edx, [r15+70h]
0x140036499  mov     [rsp+158h+var_B8], rdx
0x1400364a1  mov     rsi, r9
0x1400364a4  sub     rsi, r8
0x1400364a7  cmp     rdx, rsi
0x1400364aa  jbe     short loc_140036520
0x1400364ac  mov     r10b, byte ptr cs:xmmword_14001A3D0+9
0x1400364b3  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400364ba  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400364c1  setnz   r11b
0x1400364c5  and     r10b, 40h
0x1400364c9  jnz     short loc_1400364D0
0x1400364cb  test    r11b, r11b
0x1400364ce  jz      short loc_14003652F
0x1400364d0  lea     rcx, [r14+58h]
0x1400364d4  mov     eax, [r14+50h]
0x1400364d8  test    al, 8
0x1400364da  lea     r12, byte_1400155F0
0x1400364e1  lea     rax, aNon; "Non-"
0x1400364e8  cmovz   rax, r12
0x1400364ec  mov     [rsp+158h+var_E0], rcx
0x1400364f1  mov     [rsp+158h+var_E8], edx
0x1400364f5  mov     [rsp+158h+var_F0], r9
0x1400364fa  mov     dword ptr [rsp+158h+var_F8], edx
0x1400364fe  mov     [rsp+158h+var_100], r8
0x140036503  mov     [rsp+158h+var_108], rax
0x140036508  mov     r9, cs:WPP_GLOBAL_Control
0x14003650f  mov     r9, [r9+40h]
0x140036513  mov     r8b, r11b
0x140036516  mov     dl, r10b
0x140036519  call    WPP_RECORDER_AND_TRACE_SF_sDsiLiLZ
0x14003651e  jmp     short loc_14003652F
0x140036520  lea     rbx, WPP_RECORDER_INITIALIZED
0x140036527  mov     rsi, [rsp+158h+var_B8]
0x14003652f  mov     edx, [r15+70h]; Length
0x140036533  mov     r8d, 1; Alignment
0x140036539  mov     rcx, [r15+78h]; Address
0x14003653d  call    cs:__imp_ProbeForRead
  ... truncated ...
```
