# HsmFltPreQUERY_ALLOCATED_RANGES

- ea: `0x1400345b4`
- end: `0x140034da3`
- name: `HsmFltPreQUERY_ALLOCATED_RANGES`
- size: `2031`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x14004d8e0`

## callees

- `0x140003c50`
- `0x14001d570`
- `0x14001d63c`
- `0x14001d6ec`
- `0x14001e1c0`
- `0x1400345b4`
- `0x140058ddc`
- `0x14007036c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140034726`
- `ntoskrnl!ProbeForRead` at `0x140034726`
- `ntoskrnl!ProbeForWrite` at `0x140034756`
- `ntoskrnl!ProbeForWrite` at `0x140034756`
- `FLTMGR!FltQueryInformationFile` at `0x1400348a3`
- `FLTMGR!FltQueryInformationFile` at `0x1400348a3`

## pseudocode

```c
__int64 __fastcall HsmFltPreQUERY_ALLOCATED_RANGES(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // r13d
  __int64 v5; // r12
  struct _FLT_INSTANCE *v6; // rbx
  struct _FILE_OBJECT *v7; // rdx
  SIZE_T v8; // rsi
  __int64 v9; // r14
  __int64 v10; // rax
  NTSTATUS FileRange; // ebx
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 *v14; // r13
  __int64 *v15; // r12
  __int64 v16; // r14
  __int64 v17; // r13
  __int64 v18; // rax
  __int64 v19; // r10
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rax
  struct _FILE_OBJECT *v23; // r13
  __int64 v24; // r14
  __int64 v25; // rax
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 StreamSize; // rax
  __int64 v33; // r8
  int v35; // [rsp+70h] [rbp-D8h]
  char v36[4]; // [rsp+78h] [rbp-D0h] BYREF
  int v37; // [rsp+7Ch] [rbp-CCh]
  int v38; // [rsp+80h] [rbp-C8h]
  __int64 v39; // [rsp+88h] [rbp-C0h] BYREF
  int v40; // [rsp+90h] [rbp-B8h]
  __int64 v41; // [rsp+98h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-A8h]
  __int64 *v43; // [rsp+A8h] [rbp-A0h]
  __int64 v44; // [rsp+B0h] [rbp-98h]
  struct _FILE_OBJECT *v45; // [rsp+B8h] [rbp-90h]
  __int64 v46; // [rsp+C0h] [rbp-88h]
  __int64 v47; // [rsp+C8h] [rbp-80h]
  __int64 v48; // [rsp+D0h] [rbp-78h]
  _QWORD v49[4]; // [rsp+D8h] [rbp-70h] BYREF
  __int128 FileInformation; // [rsp+F8h] [rbp-50h] BYREF
  __int64 v51; // [rsp+108h] [rbp-40h]

  v44 = a1;
  v4 = 4;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = *(struct _FLT_INSTANCE **)(v5 + 16);
  v7 = *(struct _FILE_OBJECT **)(v5 + 8);
  v45 = v7;
  FileInformation = 0;
  v51 = 0;
  LODWORD(v39) = *(_DWORD *)(v5 + 32);
  v8 = *(unsigned int *)(v5 + 24);
  v37 = v8;
  v35 = v8;
  v46 = 0;
  v48 = 0;
  v9 = *(_QWORD *)(a3 + 16);
  v47 = v9;
  v49[1] = v9;
  v10 = *(_QWORD *)(*(_QWORD *)(v9 + 16) + 32LL);
  v42 = v10;
  if ( (unsigned int)v39 >= 0x10 )
  {
    v40 = v39;
    v49[2] = v10;
    v14 = *(__int64 **)(v5 + 48);
    v49[3] = v14;
    v15 = *(__int64 **)(v5 + 56);
    v43 = v15;
    if ( *(_BYTE *)(a1 + 80) )
    {
      ProbeForRead(v14, (unsigned int)v39, 4u);
      v16 = *v14;
      v48 = *v14;
      v17 = v14[1];
      v46 = v17;
      ProbeForWrite(v15, v8, 4u);
      v7 = v45;
    }
    else
    {
      if ( (((unsigned __int8)v15 | (unsigned __int8)v14) & 3) != 0 )
      {
        FileRange = -1073741592;
        HsmDbgBreakOnStatus(-1073741592);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          StreamSize = HsmpGetStreamSize(v9);
          WPP_SF_qPDPDiqLid(
            *(_QWORD *)(v33 + 24),
            14,
            v33,
            a1,
            v14,
            v39,
            v15,
            v8,
            v42,
            v9,
            *(_DWORD *)(v9 + 28),
            StreamSize,
            -1073741592);
        }
        v4 = 4;
        goto LABEL_55;
      }
      v16 = *v14;
      v48 = *v14;
      v17 = v14[1];
      v46 = v17;
    }
    if ( v17 < 0 || v16 < 0 || v17 > 0x7FFFFFFFFFFFFFFFLL - v16 )
    {
      FileRange = -1073741811;
      HsmDbgBreakOnStatus(-1073741811);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v29 = HsmpGetStreamSize(v47);
        WPP_SF_qiiiqLid(
          *(_QWORD *)(v30 + 24),
          v30,
          v31,
          a1,
          v16,
          v17,
          v42,
          v31,
          *(_DWORD *)(v31 + 28),
          v29,
          -1073741811);
      }
    }
    else
    {
      FileRange = FltQueryInformationFile(v6, v7, &FileInformation, 0x18u, FileStandardInformation, 0);
      HsmDbgBreakOnStatus(FileRange);
      if ( FileRange >= 0 )
      {
        if ( !v17
          || (v45 = (struct _FILE_OBJECT *)*((_QWORD *)&FileInformation + 1), v16 >= *((__int64 *)&FileInformation + 1)) )
        {
          v4 = 1;
          *(_QWORD *)(a1 + 32) = 0;
LABEL_49:
          v27 = v35;
          goto LABEL_56;
        }
        if ( *((_QWORD *)&FileInformation + 1) - v16 < v17 )
          v17 = *((_QWORD *)&FileInformation + 1) - v16;
        v46 = v17;
        if ( (unsigned int)v8 >= 0x10 )
        {
          v41 = v16;
          v21 = v16 + v17;
          v49[0] = v16 + v17;
          v22 = v16;
          v39 = v16;
          v23 = v45;
          while ( v16 < v21 )
          {
            v36[0] = 0;
            v24 = v47;
            FileRange = HsmiQueryFileRange(
                          v47,
                          16982,
                          (unsigned int)&v41,
                          (unsigned int)v49,
                          (__int64)v36,
                          (__int64)&v39);
            v38 = FileRange;
            HsmDbgBreakOnStatus(FileRange);
            if ( FileRange < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v25 = HsmpGetStreamSize(v24);
                WPP_SF_qiqLid(*(_QWORD *)(v26 + 24), 17, v26, a1, v42, v24, *(_DWORD *)(v24 + 28), v25, FileRange);
              }
              v4 = 4;
              v27 = v35;
              goto LABEL_56;
            }
            if ( v36[0] )
            {
              v28 = HsmpGetStreamSize(v24);
              if ( v39 == v28 )
                v39 = (__int64)v23;
              if ( (unsigned int)v8 < 0x10 )
                goto LABEL_37;
              *v15 = v41;
              v15[1] = v39 - v41;
              v15 += 2;
              v43 = v15;
              LODWORD(v8) = v8 - 16;
              v37 = v8;
            }
            v22 = v39;
            v16 = v39;
            v41 = v39;
            v21 = v49[0];
          }
          if ( v22 < v21 )
          {
            if ( (unsigned int)v8 < 0x10 )
            {
LABEL_37:
              FileRange = -2147483643;
              v38 = -2147483643;
              HsmDbgBreakOnStatus(-2147483643);
              v4 = 4;
              v27 = v35;
              goto LABEL_56;
            }
            *v15 = v22;
            v15[1] = (__int64)v23 - v41;
            v43 = v15 + 2;
            LODWORD(v8) = v8 - 16;
            v37 = v8;
          }
          *(_QWORD *)(a1 + 32) = (unsigned int)(v35 - v8);
          *(_DWORD *)(a1 + 24) = 0;
          v4 = 4;
          goto LABEL_49;
        }
        FileRange = -2147483643;
        HsmDbgBreakOnStatus(-2147483643);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v18 = HsmpGetStreamSize(v47);
        WPP_SF_qiqLid(*(_QWORD *)(v19 + 24), 16, v20, a1, v42, v20, *(_DWORD *)(v20 + 28), v18, FileRange);
      }
    }
    v4 = 4;
    goto LABEL_49;
  }
  FileRange = -1073741811;
  HsmDbgBreakOnStatus(-1073741811);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v12 = HsmpGetStreamSize(v9);
    WPP_SF_qiqLid(*(_QWORD *)(v13 + 24), 12, v13, a1, v42, v9, *(_DWORD *)(v9 + 28), v12, -1073741811);
  }
LABEL_55:
  v27 = v8;
LABEL_56:
  if ( FileRange < 0 )
  {
    *(_DWORD *)(a1 + 24) = FileRange;
    *(_QWORD *)(a1 + 32) = (unsigned int)(v27 - v8);
    return 4;
  }
  return v4;
}

```

## disassembly

```asm
0x1400345b4  mov     r11, rsp
0x1400345b7  mov     [r11+10h], rbx
0x1400345bb  push    rsi
0x1400345bc  push    rdi
0x1400345bd  push    r12
0x1400345bf  push    r13
0x1400345c1  push    r14
0x1400345c3  sub     rsp, 120h
0x1400345ca  mov     rax, cs:__security_cookie
0x1400345d1  xor     rax, rsp
0x1400345d4  mov     [rsp+148h+var_38], rax
0x1400345dc  mov     rdi, rcx
0x1400345df  mov     [rsp+148h+var_98], rcx
0x1400345e7  mov     r13d, 4
0x1400345ed  mov     [rsp+148h+var_D4], r13d
0x1400345f2  mov     r12, [rcx+10h]
0x1400345f6  mov     rbx, [r12+10h]
0x1400345fb  mov     rdx, [r12+8]; FileObject
0x140034600  mov     [rsp+148h+var_90], rdx
0x140034608  xorps   xmm0, xmm0
0x14003460b  xor     eax, eax
0x14003460d  movups  xmmword ptr [r11-50h], xmm0
0x140034612  mov     [r11-40h], rax
0x140034616  mov     ecx, [r12+20h]
0x14003461b  mov     dword ptr [rsp+148h+var_C0], ecx
0x140034622  mov     esi, [r12+18h]
0x140034627  mov     [rsp+148h+var_CC], esi
0x14003462b  mov     [rsp+148h+var_D8], esi
0x14003462f  mov     [r11-88h], rax
0x140034636  mov     [r11-78h], rax
0x14003463a  mov     r14, [r8+10h]
0x14003463e  mov     [rsp+148h+var_80], r14
0x140034646  mov     [rsp+148h+var_68], r14
0x14003464e  mov     rax, [r14+10h]
0x140034652  mov     rax, [rax+20h]
0x140034656  mov     [rsp+148h+var_A8], rax
0x14003465e  cmp     ecx, 10h
0x140034661  jnb     loc_1400346E7
0x140034667  mov     r12d, 0C000000Dh
0x14003466d  mov     ebx, r12d
0x140034670  mov     ecx, r12d
0x140034673  call    HsmDbgBreakOnStatus
0x140034678  lea     rax, WPP_GLOBAL_Control
0x14003467f  mov     r8, cs:WPP_GLOBAL_Control
0x140034686  cmp     r8, rax
0x140034689  jz      loc_140034D62
0x14003468f  mov     eax, [r8+2Ch]
0x140034693  test    al, 1
0x140034695  jz      loc_140034D62
0x14003469b  cmp     byte ptr [r8+29h], 2
0x1400346a0  jb      loc_140034D62
0x1400346a6  mov     rcx, r14
0x1400346a9  call    HsmpGetStreamSize
0x1400346ae  lea     edx, [r13+8]
0x1400346b2  mov     dword ptr [rsp+148h+var_108], r12d
0x1400346b7  mov     [rsp+148h+var_110], rax
0x1400346bc  mov     eax, [r14+1Ch]
0x1400346c0  mov     dword ptr [rsp+148h+var_118], eax
0x1400346c4  mov     [rsp+148h+LengthReturned], r14
0x1400346c9  mov     rax, [rsp+148h+var_A8]
0x1400346d1  mov     qword ptr [rsp+148h+FileInformationClass], rax
0x1400346d6  mov     r9, rdi
0x1400346d9  mov     rcx, [r8+18h]
0x1400346dd  call    WPP_SF_qiqLid
0x1400346e2  jmp     loc_140034D62
0x1400346e7  mov     [rsp+148h+var_B8], ecx
0x1400346ee  mov     [rsp+148h+var_60], rax
0x1400346f6  mov     r13, [r12+30h]
0x1400346fb  mov     [rsp+148h+var_58], r13
0x140034703  mov     r12, [r12+38h]
0x140034708  mov     [rsp+148h+var_A0], r12
0x140034710  cmp     byte ptr [rdi+50h], 0
0x140034714  jz      loc_140034833
0x14003471a  mov     rdx, rcx; Length
0x14003471d  mov     r8d, 4; Alignment
0x140034723  mov     rcx, r13; Address
0x140034726  call    cs:__imp_ProbeForRead
0x14003472d  nop     dword ptr [rax+rax+00h]
0x140034732  mov     r14, [r13+0]
0x140034736  mov     [rsp+148h+var_78], r14
0x14003473e  mov     r13, [r13+8]
0x140034742  mov     [rsp+148h+var_88], r13
0x14003474a  mov     rdx, rsi; Length
0x14003474d  mov     r8d, 4; Alignment
0x140034753  mov     rcx, r12; Address
0x140034756  call    cs:__imp_ProbeForWrite
0x14003475d  nop     dword ptr [rax+rax+00h]
0x140034762  nop
0x140034763  mov     rdx, [rsp+148h+var_90]
0x14003476b  jmp     loc_140034859
0x140034770  mov     ebx, 0C00000E8h
0x140034775  mov     ecx, ebx
0x140034777  call    HsmDbgBreakOnStatus
0x14003477c  lea     rax, WPP_GLOBAL_Control
0x140034783  mov     r8, cs:WPP_GLOBAL_Control
0x14003478a  cmp     r8, rax
0x14003478d  jz      loc_140034819
0x140034793  mov     eax, [r8+2Ch]
0x140034797  test    al, 1
0x140034799  jz      short loc_140034819
0x14003479b  cmp     byte ptr [r8+29h], 2
0x1400347a0  jb      short loc_140034819
0x1400347a2  mov     rcx, [rsp+148h+var_68]
0x1400347aa  call    HsmpGetStreamSize
0x1400347af  mov     edx, 0Dh
0x1400347b4  mov     [rsp+148h+var_E8], ebx
0x1400347b8  mov     [rsp+148h+var_F0], rax
0x1400347bd  mov     eax, [rcx+1Ch]
0x1400347c0  mov     [rsp+148h+var_F8], eax
0x1400347c4  mov     [rsp+148h+var_100], rcx
0x1400347c9  mov     rax, [rsp+148h+var_60]
0x1400347d1  mov     [rsp+148h+var_108], rax
0x1400347d6  mov     esi, [rsp+148h+var_CC]
0x1400347da  mov     dword ptr [rsp+148h+var_110], esi
0x1400347de  mov     rax, [rsp+148h+var_A0]
0x1400347e6  mov     [rsp+148h+var_118], rax
0x1400347eb  mov     eax, [rsp+148h+var_B8]
0x1400347f2  mov     dword ptr [rsp+148h+LengthReturned], eax
0x1400347f6  mov     rax, [rsp+148h+var_58]
0x1400347fe  mov     qword ptr [rsp+148h+FileInformationClass], rax
0x140034803  mov     rdi, [rsp+148h+var_98]
0x14003480b  mov     r9, rdi
0x14003480e  mov     rcx, [r8+18h]
0x140034812  call    WPP_SF_qPDPDiqLid
0x140034817  jmp     short loc_140034825
0x140034819  mov     esi, [rsp+148h+var_CC]
0x14003481d  mov     rdi, [rsp+148h+var_98]
0x140034825  mov     r13d, [rsp+148h+var_D4]
0x14003482a  mov     eax, [rsp+148h+var_D8]
0x14003482e  jmp     loc_140034D64
0x140034833  mov     al, r13b
0x140034836  or      al, r12b
0x140034839  test    al, 3
0x14003483b  jnz     loc_140034CDA
0x140034841  mov     r14, [r13+0]
0x140034845  mov     [rsp+148h+var_78], r14
0x14003484d  mov     r13, [r13+8]
0x140034851  mov     [rsp+148h+var_88], r13
0x140034859  test    r13, r13
0x14003485c  js      loc_140034C51
0x140034862  test    r14, r14
0x140034865  js      loc_140034C51
0x14003486b  mov     rax, 7FFFFFFFFFFFFFFFh
0x140034875  sub     rax, r14
0x140034878  cmp     r13, rax
0x14003487b  jg      loc_140034C51
0x140034881  mov     [rsp+148h+LengthReturned], 0; LengthReturned
0x14003488a  mov     [rsp+148h+FileInformationClass], 5; FileInformationClass
0x140034892  mov     r9d, 18h; Length
0x140034898  lea     r8, [rsp+148h+FileInformation]; FileInformation
0x1400348a0  mov     rcx, rbx; Instance
0x1400348a3  call    cs:__imp_FltQueryInformationFile
0x1400348aa  nop     dword ptr [rax+rax+00h]
0x1400348af  mov     ebx, eax
0x1400348b1  mov     ecx, eax
0x1400348b3  call    HsmDbgBreakOnStatus
0x1400348b8  test    ebx, ebx
0x1400348ba  jns     short loc_140034933
0x1400348bc  lea     rax, WPP_GLOBAL_Control
0x1400348c3  mov     r10, cs:WPP_GLOBAL_Control
0x1400348ca  cmp     r10, rax
0x1400348cd  jz      loc_140034CCC
0x1400348d3  mov     eax, [r10+2Ch]
0x1400348d7  test    al, 1
0x1400348d9  jz      loc_140034CCC
0x1400348df  cmp     byte ptr [r10+29h], 2
0x1400348e4  jb      loc_140034CCC
0x1400348ea  mov     r8, [rsp+148h+var_80]
0x1400348f2  mov     rcx, r8
0x1400348f5  call    HsmpGetStreamSize
0x1400348fa  mov     edx, 10h
0x1400348ff  mov     dword ptr [rsp+148h+var_108], ebx
0x140034903  mov     [rsp+148h+var_110], rax
0x140034908  mov     eax, [r8+1Ch]
0x14003490c  mov     dword ptr [rsp+148h+var_118], eax
0x140034910  mov     [rsp+148h+LengthReturned], r8
0x140034915  mov     rax, [rsp+148h+var_A8]
0x14003491d  mov     qword ptr [rsp+148h+FileInformationClass], rax
0x140034922  mov     r9, rdi
0x140034925  mov     rcx, [r10+18h]
0x140034929  call    WPP_SF_qiqLid
0x14003492e  jmp     loc_140034CCC
0x140034933  test    r13, r13
0x140034936  jnz     short loc_14003494B
0x140034938  mov     r13d, 1
0x14003493e  mov     qword ptr [rdi+20h], 0
0x140034946  jmp     loc_140034CD1
0x14003494b  mov     rcx, [rsp+148h+var_48]
0x140034953  mov     [rsp+148h+var_90], rcx
0x14003495b  cmp     r14, rcx
0x14003495e  jge     short loc_140034938
0x140034960  mov     rax, rcx
0x140034963  sub     rax, r14
0x140034966  cmp     rax, r13
0x140034969  cmovl   r13, rax
0x14003496d  mov     [rsp+148h+var_88], r13
0x140034975  cmp     esi, 10h
0x140034978  jnb     short loc_14003498B
0x14003497a  mov     ecx, 80000005h
0x14003497f  mov     ebx, ecx
0x140034981  call    HsmDbgBreakOnStatus
0x140034986  jmp     loc_140034CCC
0x14003498b  mov     [rsp+148h+var_B0], r14
0x140034993  lea     rcx, [r14+r13]
0x140034997  mov     [rsp+148h+var_70], rcx
0x14003499f  mov     rax, r14
0x1400349a2  mov     [rsp+148h+var_C0], rax
0x1400349aa  mov     r13, [rsp+148h+var_90]
0x1400349b2  cmp     r14, rcx
0x1400349b5  jge     loc_140034B19
0x1400349bb  mov     [rsp+148h+var_D0], 0
0x1400349c0  lea     rax, [rsp+148h+var_C0]
0x1400349c8  mov     [rsp+148h+LengthReturned], rax
0x1400349cd  lea     rax, [rsp+148h+var_D0]
0x1400349d2  mov     qword ptr [rsp+148h+FileInformationClass], rax
0x1400349d7  lea     r9, [rsp+148h+var_70]
0x1400349df  lea     r8, [rsp+148h+var_B0]
0x1400349e7  mov     edx, 4256h
0x1400349ec  mov     r14, [rsp+148h+var_80]
0x1400349f4  mov     rcx, r14
0x1400349f7  call    HsmiQueryFileRange
0x1400349fc  mov     ebx, eax
0x1400349fe  mov     [rsp+148h+var_C8], eax
0x140034a05  mov     ecx, eax
0x140034a07  call    HsmDbgBreakOnStatus
0x140034a0c  test    ebx, ebx
0x140034a0e  jns     short loc_140034A7C
0x140034a10  lea     rax, WPP_GLOBAL_Control
0x140034a17  mov     r8, cs:WPP_GLOBAL_Control
0x140034a1e  cmp     r8, rax
0x140034a21  jz      short loc_140034A6E
0x140034a23  mov     eax, [r8+2Ch]
0x140034a27  test    al, 1
0x140034a29  jz      short loc_140034A6E
0x140034a2b  cmp     byte ptr [r8+29h], 2
0x140034a30  jb      short loc_140034A6E
0x140034a32  mov     rcx, r14
0x140034a35  call    HsmpGetStreamSize
0x140034a3a  mov     edx, 11h
0x140034a3f  mov     dword ptr [rsp+148h+var_108], ebx
0x140034a43  mov     [rsp+148h+var_110], rax
0x140034a48  mov     eax, [r14+1Ch]
0x140034a4c  mov     dword ptr [rsp+148h+var_118], eax
0x140034a50  mov     [rsp+148h+LengthReturned], r14
0x140034a55  mov     rax, [rsp+148h+var_A8]
0x140034a5d  mov     qword ptr [rsp+148h+FileInformationClass], rax
0x140034a62  mov     r9, rdi
0x140034a65  mov     rcx, [r8+18h]
0x140034a69  call    WPP_SF_qiqLid
0x140034a6e  mov     r13d, [rsp+148h+var_D4]
0x140034a73  mov     eax, [rsp+148h+var_D8]
0x140034a77  jmp     loc_140034D64
0x140034a7c  cmp     [rsp+148h+var_D0], 0
0x140034a81  jnz     short loc_140034A85
0x140034a83  jmp     short loc_140034AF9
0x140034a85  mov     rcx, r14
0x140034a88  call    HsmpGetStreamSize
0x140034a8d  cmp     [rsp+148h+var_C0], rax
0x140034a95  jnz     short loc_140034A9F
0x140034a97  mov     [rsp+148h+var_C0], r13
0x140034a9f  cmp     esi, 10h
0x140034aa2  jnb     short loc_140034AC5
0x140034aa4  mov     ecx, 80000005h
0x140034aa9  mov     ebx, ecx
0x140034aab  mov     [rsp+148h+var_C8], ecx
0x140034ab2  call    HsmDbgBreakOnStatus
0x140034ab7  mov     r13d, [rsp+148h+var_D4]
0x140034abc  mov     eax, [rsp+148h+var_D8]
0x140034ac0  jmp     loc_140034D64
0x140034ac5  mov     rax, [rsp+148h+var_B0]
0x140034acd  mov     [r12], rax
0x140034ad1  mov     rax, [rsp+148h+var_C0]
0x140034ad9  sub     rax, [rsp+148h+var_B0]
0x140034ae1  mov     [r12+8], rax
0x140034ae6  add     r12, 10h
0x140034aea  mov     [rsp+148h+var_A0], r12
0x140034af2  add     esi, 0FFFFFFF0h
0x140034af5  mov     [rsp+148h+var_CC], esi
0x140034af9  mov     rax, [rsp+148h+var_C0]
0x140034b01  mov     r14, rax
0x140034b04  mov     [rsp+148h+var_B0], rax
0x140034b0c  mov     rcx, [rsp+148h+var_70]
0x140034b14  jmp     loc_1400349B2
0x140034b19  cmp     rax, rcx
0x140034b1c  jge     short loc_140034B6B
0x140034b1e  cmp     esi, 10h
0x140034b21  jnb     short loc_140034B44
0x140034b23  mov     ecx, 80000005h
0x140034b28  mov     ebx, ecx
0x140034b2a  mov     [rsp+148h+var_C8], ecx
0x140034b31  call    HsmDbgBreakOnStatus
0x140034b36  mov     r13d, [rsp+148h+var_D4]
0x140034b3b  mov     eax, [rsp+148h+var_D8]
0x140034b3f  jmp     loc_140034D64
0x140034b44  mov     [r12], rax
0x140034b48  mov     rcx, r13
0x140034b4b  sub     rcx, [rsp+148h+var_B0]
0x140034b53  mov     [r12+8], rcx
0x140034b58  add     r12, 10h
0x140034b5c  mov     [rsp+148h+var_A0], r12
  ... truncated ...
```
