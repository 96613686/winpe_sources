# CClfsMarshallingContext::ReadMarshalledLogRecord(CLogIocb &,ulong &,uchar &)

- ea: `0x180011cfc`
- end: `0x180012407`
- name: `?ReadMarshalledLogRecord@CClfsMarshallingContext@@AEAAKAEAVCLogIocb@@AEAKAEAE@Z`
- size: `1803`
- prototype: `unsigned int(CClfsMarshallingContext *__hidden this, struct CLogIocb *, unsigned int *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001195c`
- `0x1800124f0`

## callees

- `0x1800026c6`
- `0x18000f4a8`
- `0x18000f60c`
- `0x18001067c`
- `0x180011330`
- `0x180011cfc`
- `0x180014ac8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800121ed`
- `ntdll!RtlLeaveCriticalSection` at `0x1800123e0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800123f4`
- `ntdll!RtlLeaveCriticalSection` at `0x180015a4c`
- `ntdll!RtlLeaveCriticalSection` at `0x180015a70`
- `ntdll!RtlLeaveCriticalSection` at `0x1800121ed`
- `ntdll!RtlLeaveCriticalSection` at `0x1800123e0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800123f4`
- `ntdll!RtlLeaveCriticalSection` at `0x180015a4c`
- `ntdll!RtlLeaveCriticalSection` at `0x180015a70`
- `ntdll!RtlEnterCriticalSection` at `0x180011db9`
- `ntdll!RtlEnterCriticalSection` at `0x180011ddf`
- `ntdll!RtlEnterCriticalSection` at `0x180011db9`
- `ntdll!RtlEnterCriticalSection` at `0x180011ddf`
- `ntdll!RtlNtStatusToDosError` at `0x180011edf`
- `ntdll!RtlNtStatusToDosError` at `0x180011f02`
- `ntdll!RtlNtStatusToDosError` at `0x180011edf`
- `ntdll!RtlNtStatusToDosError` at `0x180011f02`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::ReadMarshalledLogRecord(
        CClfsMarshallingContext *this,
        struct CLogIocb *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  union _CLS_LSN v8; // rbx
  char v10; // r12
  CLFS_CONTAINER_ID cidContainer; // r13d
  char v12; // al
  unsigned int v13; // edx
  __int64 v14; // rcx
  CLFS_RECORD_INDEX *v15; // rax
  CLFS_RECORD_INDEX *v16; // rax
  __int64 v17; // r13
  unsigned int v18; // edi
  int v19; // r9d
  int v20; // r11d
  signed int v21; // eax
  unsigned int v22; // r9d
  unsigned int v23; // r8d
  __int64 i; // r10
  unsigned int v25; // eax
  unsigned int v26; // edi
  struct _RTL_CRITICAL_SECTION *v27; // r13
  unsigned __int8 *v28; // r10
  struct _CLFS_RECORD_HEADER *v29; // rcx
  int v30; // ecx
  int v31; // edx
  CLFS_LSN v32; // rcx
  unsigned __int64 v33; // r8
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rtt
  union _CLS_LSN *v36; // r11
  unsigned int v37; // eax
  unsigned int v38; // ecx
  struct _CLFS_RECORD_HEADER *FirstRecord; // rax
  __int64 v40; // r10
  __int64 v41; // rdx
  unsigned int v42; // r8d
  unsigned int v43; // edx
  unsigned int v44; // ecx
  int v45; // r8d
  unsigned int v46; // r10d
  __int64 v47; // r9
  unsigned int v48; // edx
  unsigned int v49; // edx
  int v50; // ecx
  __int64 v51; // rcx
  unsigned int v52; // ecx
  int v53; // edx
  __int64 v54; // rax
  CLFS_LSN v55; // rax
  unsigned __int8 v56; // [rsp+42h] [rbp-A6h]
  unsigned int v57; // [rsp+48h] [rbp-A0h]
  union _CLS_LSN v58; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v59; // [rsp+58h] [rbp-90h]
  unsigned int v60; // [rsp+5Ch] [rbp-8Ch]
  CLFS_LSN *v61; // [rsp+60h] [rbp-88h]
  CLFS_LSN v62; // [rsp+68h] [rbp-80h]
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+70h] [rbp-78h]
  union _CLS_LSN v64; // [rsp+78h] [rbp-70h] BYREF
  struct _CLFS_RECORD_HEADER *v65; // [rsp+80h] [rbp-68h] BYREF
  unsigned int v66; // [rsp+88h] [rbp-60h]
  int v67; // [rsp+8Ch] [rbp-5Ch]
  __int64 v68; // [rsp+90h] [rbp-58h]
  unsigned int v69[2]; // [rsp+98h] [rbp-50h] BYREF
  PRTL_CRITICAL_SECTION v70; // [rsp+A0h] [rbp-48h]
  unsigned __int64 v72; // [rsp+100h] [rbp+18h]

  v64 = CLFS_LSN_INVALID;
  v65 = 0;
  *a3 = 0;
  *a4 = 0;
  v61 = (CLFS_LSN *)((char *)a2 + 160);
  v8 = *(union _CLS_LSN *)((char *)a2 + 160);
  v58 = v8;
  if ( CLFS_LSN_INVALID.ullOffset == v8.ullOffset )
    return (*((_BYTE *)a2 + 28) & 0x10) != 0 ? 6618 : 87;
  if ( !*((_DWORD *)this + 31) )
    return 1168;
  v70 = (PRTL_CRITICAL_SECTION)((char *)this + 288);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 288));
  v10 = 1;
  CriticalSection = (PRTL_CRITICAL_SECTION)((char *)this + 328);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
  if ( this == (CClfsMarshallingContext *)-200LL )
  {
    v12 = 0;
    cidContainer = v58.offset.cidContainer;
  }
  else
  {
    cidContainer = v58.offset.cidContainer;
    if ( __PAIR64__(v58.offset.cidContainer, v8.offset.idxRecord) >= *((_QWORD *)this + 25) )
      goto LABEL_68;
    v12 = 1;
  }
  if ( v12 )
  {
    v57 = 0;
    while ( 1 )
    {
      if ( (unsigned int)CFlushQ::IsEmpty((CClfsMarshallingContext *)((char *)this + 232))
        || (v13 = v57, v57 >= *((_DWORD *)this + 58)) )
      {
        v27 = CriticalSection;
        goto LABEL_90;
      }
      v14 = *(_QWORD *)(*((_QWORD *)this + 30) + 16LL * v57 + 8);
      v68 = v14;
      v15 = (CLFS_RECORD_INDEX *)(v14 + 176);
      if ( v14 != -176 )
      {
        if ( cidContainer < *(_DWORD *)(v14 + 180)
          || cidContainer == *(_DWORD *)(v14 + 180) && v8.offset.idxRecord <= *v15 )
        {
          goto LABEL_19;
        }
        LOBYTE(v15) = 1;
      }
      if ( (_BYTE)v15 )
        goto LABEL_66;
LABEL_19:
      v16 = (CLFS_RECORD_INDEX *)(v14 + 184);
      if ( v14 != -184 )
      {
        if ( cidContainer > *(_DWORD *)(v14 + 188)
          || cidContainer == *(_DWORD *)(v14 + 188) && v8.offset.idxRecord >= *v16 )
        {
          goto LABEL_25;
        }
        LOBYTE(v16) = 1;
      }
      if ( (_BYTE)v16 )
        goto LABEL_66;
LABEL_25:
      memcpy_0(*((void **)a2 + 8), *(const void **)(v14 + 64), *((unsigned int *)this + 33));
      v17 = *((_QWORD *)a2 + 8);
      v56 = *(_BYTE *)(v17 + 2);
      v18 = *(unsigned __int16 *)(v17 + 4);
      RtlNtStatusToDosError(0);
      v20 = *(_DWORD *)(v17 + 12);
      if ( !v20 )
        goto LABEL_33;
      if ( v20 != -1 )
      {
        *(_DWORD *)(v17 + 12) = 0;
        v22 = -1;
        v23 = v18 << 9;
        v66 = v18 << 9;
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v67 = i;
          v25 = v23--;
          v66 = v23;
          if ( !v25 )
            break;
          v22 = *((_DWORD *)&CCrc32::m_rgCrcTable
                + ((unsigned __int8)v22 ^ (unsigned __int64)*(unsigned __int8 *)(i + v17)))
              ^ (v22 >> 8);
        }
        v19 = ~v22;
        if ( v20 == v19 )
        {
LABEL_33:
          v21 = ClfsDecodeBlockPrivate((struct _CLFS_LOG_BLOCK_HEADER *)v17, v18, v56, v19, v69);
          goto LABEL_34;
        }
        *(_DWORD *)(v17 + 12) = v20;
      }
      v21 = RtlNtStatusToDosError(-1072037878);
LABEL_34:
      v26 = v21;
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_slqD(*((_QWORD *)WPP_GLOBAL_Control + 2));
        }
        v26 = 1359;
        v27 = CriticalSection;
        goto LABEL_91;
      }
      *((_DWORD *)a2 + 18) = *(_DWORD *)(v68 + 72);
      *((_QWORD *)a2 + 14) = *((_QWORD *)a2 + 8);
      *((_QWORD *)a2 + 13) = CLogIocb::GetFirstRecord(a2);
      ClfsFindLsnInBlock(&v58, v28, &v65, &v64);
      if ( v8.ullOffset == v64.ullOffset )
      {
        v29 = v65;
        *((_QWORD *)a2 + 14) = *((_QWORD *)a2 + 8);
        if ( v29 )
          *((_QWORD *)a2 + 13) = v29;
        else
          *((_QWORD *)a2 + 13) = CLogIocb::GetFirstRecord(a2);
        v30 = *((_DWORD *)this + 34);
        if ( v30 )
          v31 = -v30 & (v30 + (*(unsigned __int16 *)(v17 + 4) << 9) - 1);
        else
          v31 = 0;
        *a3 = v31;
        v68 = 0;
        v32 = CLFS_LSN_INVALID;
        if ( CLFS_LSN_INVALID.ullOffset != v8.ullOffset )
        {
          v33 = *((_QWORD *)this + 21);
          v35 = v33 * v58.offset.cidContainer + v31 + (v8.offset.idxRecord & 0xFFFFFE00);
          v34 = v35 % v33;
          v72 = v35 / v33;
          if ( !((v35 / v33) >> 32) && !HIDWORD(v34) && (_DWORD)v72 != -1 && (v34 & 0x1FF) == 0 )
          {
            v62.ullOffset = __PAIR64__(v72, v34);
            v32.ullOffset = __PAIR64__(v72, v34);
          }
        }
        v36 = v61;
        *v61 = v32;
        *a4 = 1;
        v27 = CriticalSection;
        goto LABEL_92;
      }
      v37 = -1;
      if ( a2 != (struct CLogIocb *)-160LL )
        v37 = *((_DWORD *)a2 + 40) & 0xFFFFFE00;
      v38 = -1;
      if ( a2 != (struct CLogIocb *)-160LL )
        v38 = *((_DWORD *)a2 + 41);
      if ( v38 == -1 || (v37 & 0x1FF) != 0 )
      {
        v62 = CLFS_LSN_INVALID;
      }
      else
      {
        v69[1] = v38;
        v69[0] = v37;
        v62.ullOffset = __PAIR64__(v38, v37);
      }
      FirstRecord = CLogIocb::GetFirstRecord(a2);
      if ( FirstRecord )
        LOBYTE(FirstRecord) = *(_QWORD *)FirstRecord == v40;
      if ( (_BYTE)FirstRecord )
      {
        *a3 = *(unsigned __int16 *)(v17 + 4) << 9;
        v26 = 1168;
        v27 = CriticalSection;
        goto LABEL_92;
      }
      v13 = v57;
LABEL_66:
      v57 = v13 + 1;
      cidContainer = v58.offset.cidContainer;
    }
  }
LABEL_68:
  v27 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 328);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
  v10 = 0;
  v41 = *((_QWORD *)this + 20);
  if ( v41 && (ClfsFindLsnInBlock(&v58, *(unsigned __int8 **)(v41 + 64), &v65, &v64), v8.ullOffset == v64.ullOffset) )
  {
    memcpy_0(
      *((void **)a2 + 8),
      *(const void **)(*((_QWORD *)this + 20) + 64LL),
      *(unsigned int *)(*((_QWORD *)this + 20) + 72LL));
    v42 = *(_DWORD *)(*((_QWORD *)this + 20) + 72LL);
    v43 = v42 / 0x1FE;
    v59 = v42 / 0x1FE;
    if ( v42 != 510 * (v42 / 0x1FE) )
      v59 = ++v43;
    v44 = v42 + ((2 * v43 + 7) & 0xFFFFFFF8);
    *a3 = v44;
    *((_DWORD *)a2 + 18) = v44;
    v45 = *((_DWORD *)this + 34);
    v46 = *(_DWORD *)(*((_QWORD *)this + 20) + 72LL);
    v47 = *((_QWORD *)a2 + 8);
    v48 = v46 / 0x1FE;
    v60 = v46 / 0x1FE;
    if ( v46 != 510 * (v46 / 0x1FE) )
      v60 = ++v48;
    if ( v45 )
      v49 = -v45 & (v45 + v46 + ((2 * v48 + 7) & 0xFFFFFFF8) - 1);
    else
      v49 = 0;
    v50 = (unsigned __int16)(v49 >> 9);
    *(_WORD *)(v47 + 6) = v50;
    *(_WORD *)(v47 + 4) = v50;
    *(_DWORD *)(v47 + 104) = v49 - ((2 * v50 + 7) & 0xFFFFFFF8);
    v51 = *((_QWORD *)a2 + 13);
    *((_QWORD *)a2 + 14) = *((_QWORD *)a2 + 8);
    if ( v51 )
      *((_QWORD *)a2 + 13) = v51;
    else
      *((_QWORD *)a2 + 13) = CLogIocb::GetFirstRecord(a2);
    *a4 = 0;
    v52 = -1;
    if ( v65 )
      v52 = *(_DWORD *)v65 & 0xFFFFFE00;
    v53 = -1;
    if ( v65 )
      v53 = *((_DWORD *)v65 + 1);
    if ( v53 == -1 || (v52 & 0x1FF) != 0 || (v54 = *((_QWORD *)this + 20), (*(_DWORD *)(v54 + 76) & 0xFFFFFE00) != 0) )
      v55 = CLFS_LSN_INVALID;
    else
      v55.ullOffset = __PAIR64__(v53, *(_DWORD *)(v54 + 76) | v52);
    v36 = v61;
    *v61 = v55;
    v26 = 0;
  }
  else
  {
LABEL_90:
    v26 = 1168;
LABEL_91:
    v36 = v61;
  }
LABEL_92:
  if ( v26 == 1168 )
    *v36 = v8;
  if ( v10 )
    RtlLeaveCriticalSection(v27);
  RtlLeaveCriticalSection(v70);
  return v26;
}

```

## disassembly

```asm
0x180011cfc  mov     r11, rsp
0x180011cff  mov     [r11+20h], r9
0x180011d03  mov     [r11+18h], r8
0x180011d07  mov     [r11+10h], rdx
0x180011d0b  mov     [r11+8], rcx
0x180011d0f  push    rbx
0x180011d10  push    rsi
0x180011d11  push    rdi
0x180011d12  push    r12
0x180011d14  push    r13
0x180011d16  push    r14
0x180011d18  push    r15
0x180011d1a  sub     rsp, 0B0h
0x180011d21  mov     r15, r9
0x180011d24  mov     rdi, r8
0x180011d27  mov     rsi, rdx
0x180011d2a  mov     r14, rcx
0x180011d2d  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180011d34  mov     [r11-70h], rax
0x180011d38  xor     r13d, r13d
0x180011d3b  mov     [r11-68h], r13
0x180011d3f  mov     [r8], r13d
0x180011d42  mov     [r9], r13b
0x180011d45  lea     rax, [rdx+0A0h]
0x180011d4c  mov     [rsp+0E8h+var_88], rax
0x180011d51  mov     rbx, [rdx+0A0h]
0x180011d58  mov     qword ptr [rsp+0E8h+var_98], rbx
0x180011d5d  cmp     qword ptr cs:CLFS_LSN_INVALID, rbx
0x180011d64  jnz     short loc_180011D8B
0x180011d66  mov     al, [rdx+1Ch]
0x180011d69  and     al, 10h
0x180011d6b  neg     al
0x180011d6d  sbb     eax, eax
0x180011d6f  and     eax, 1983h
0x180011d74  add     eax, 57h ; 'W'
0x180011d77  add     rsp, 0B0h
0x180011d7e  pop     r15
0x180011d80  pop     r14
0x180011d82  pop     r13
0x180011d84  pop     r12
0x180011d86  pop     rdi
0x180011d87  pop     rsi
0x180011d88  pop     rbx
0x180011d89  retn
0x180011d8b  mov     [rsp+0E8h+var_A4], r13d
0x180011d90  mov     [rsp+0E8h+var_A7], r13b
0x180011d95  mov     [rsp+0E8h+var_A8], r13b
0x180011d9a  cmp     [rcx+7Ch], r13d
0x180011d9e  jnz     short loc_180011DA7
0x180011da0  mov     eax, 490h
0x180011da5  jmp     short loc_180011D77
0x180011da7  lea     rax, [rcx+120h]
0x180011dae  mov     [rsp+0E8h+var_48], rax
0x180011db6  mov     rcx, rax; CriticalSection
0x180011db9  call    cs:__imp_RtlEnterCriticalSection
0x180011dc0  nop     dword ptr [rax+rax+00h]
0x180011dc5  mov     r12d, 1
0x180011dcb  mov     [rsp+0E8h+var_A7], r12b
0x180011dd0  lea     rax, [r14+148h]
0x180011dd7  mov     [rsp+0E8h+CriticalSection], rax
0x180011ddc  mov     rcx, rax; CriticalSection
0x180011ddf  call    cs:__imp_RtlEnterCriticalSection
0x180011de6  nop     dword ptr [rax+rax+00h]
0x180011deb  mov     [rsp+0E8h+var_A8], r12b
0x180011df0  lea     rax, [r14+0C8h]
0x180011df7  test    rax, rax
0x180011dfa  jz      short loc_180011E1A
0x180011dfc  mov     r13d, dword ptr [rsp+0E8h+var_98+4]
0x180011e01  cmp     r13d, [rax+4]
0x180011e05  ja      loc_1800121E3
0x180011e0b  jnz     short loc_180011E15
0x180011e0d  cmp     ebx, [rax]
0x180011e0f  jnb     loc_1800121E3
0x180011e15  mov     al, r12b
0x180011e18  jmp     short loc_180011E22
0x180011e1a  mov     al, r13b
0x180011e1d  mov     r13d, dword ptr [rsp+0E8h+var_98+4]
0x180011e22  test    al, al
0x180011e24  jz      loc_1800121E3
0x180011e2a  mov     [rsp+0E8h+var_A0], 0
0x180011e32  or      r15d, 0FFFFFFFFh
0x180011e36  lea     rdi, [r14+0E8h]
0x180011e3d  mov     rcx, rdi; this
0x180011e40  call    ?IsEmpty@CFlushQ@@QEAAHXZ; CFlushQ::IsEmpty(void)
0x180011e45  test    eax, eax
0x180011e47  jnz     loc_1800121D9
0x180011e4d  mov     edx, [rsp+0E8h+var_A0]
0x180011e51  cmp     edx, [rdi]
0x180011e53  jnb     loc_1800121D9
0x180011e59  mov     ecx, edx
0x180011e5b  add     rcx, rcx
0x180011e5e  mov     rax, [r14+0F0h]
0x180011e65  mov     rcx, [rax+rcx*8+8]
0x180011e6a  mov     [rsp+0E8h+var_58], rcx
0x180011e72  lea     rax, [rcx+0B0h]
0x180011e79  test    rax, rax
0x180011e7c  jz      short loc_180011E8D
0x180011e7e  cmp     r13d, [rax+4]
0x180011e82  jb      short loc_180011E95
0x180011e84  jnz     short loc_180011E8A
0x180011e86  cmp     ebx, [rax]
0x180011e88  jbe     short loc_180011E95
0x180011e8a  mov     al, r12b
0x180011e8d  test    al, al
0x180011e8f  jnz     loc_1800121C8
0x180011e95  lea     rax, [rcx+0B8h]
0x180011e9c  test    rax, rax
0x180011e9f  jz      short loc_180011EB0
0x180011ea1  cmp     r13d, [rax+4]
0x180011ea5  ja      short loc_180011EB8
0x180011ea7  jnz     short loc_180011EAD
0x180011ea9  cmp     ebx, [rax]
0x180011eab  jnb     short loc_180011EB8
0x180011ead  mov     al, r12b
0x180011eb0  test    al, al
0x180011eb2  jnz     loc_1800121C8
0x180011eb8  mov     r8d, [r14+84h]; Size
0x180011ebf  mov     rdx, [rcx+40h]; Src
0x180011ec3  mov     rcx, [rsi+40h]; void *
0x180011ec7  call    memcpy_0
0x180011ecc  mov     r13, [rsi+40h]
0x180011ed0  mov     al, [r13+2]
0x180011ed4  mov     [rsp+0E8h+var_A6], al
0x180011ed8  movzx   edi, word ptr [r13+4]
0x180011edd  xor     ecx, ecx; Status
0x180011edf  call    cs:__imp_RtlNtStatusToDosError
0x180011ee6  nop     dword ptr [rax+rax+00h]
0x180011eeb  mov     r11d, [r13+0Ch]
0x180011eef  test    r11d, r11d
0x180011ef2  jz      loc_180011F78
0x180011ef8  cmp     r11d, r15d
0x180011efb  jnz     short loc_180011F13
0x180011efd  mov     ecx, 0C01A000Ah; Status
0x180011f02  call    cs:__imp_RtlNtStatusToDosError
0x180011f09  nop     dword ptr [rax+rax+00h]
0x180011f0e  jmp     loc_180011F94
0x180011f13  mov     dword ptr [r13+0Ch], 0
0x180011f1b  mov     r9d, r15d
0x180011f1e  mov     r8d, edi
0x180011f21  shl     r8d, 9
0x180011f25  mov     [rsp+0E8h+var_60], r8d
0x180011f2d  xor     r10d, r10d
0x180011f30  mov     [rsp+0E8h+var_5C], r10d
0x180011f38  mov     eax, r8d
0x180011f3b  add     r8d, r15d
0x180011f3e  mov     [rsp+0E8h+var_60], r8d
0x180011f46  test    eax, eax
0x180011f48  jz      short loc_180011F6A
0x180011f4a  movzx   edx, byte ptr [r10+r13]
0x180011f4f  movzx   ecx, r9b
0x180011f53  xor     rdx, rcx
0x180011f56  lea     rax, ?m_rgCrcTable@CCrc32@@0PAKA; ulong near * CCrc32::m_rgCrcTable
0x180011f5d  shr     r9d, 8
0x180011f61  xor     r9d, [rax+rdx*4]
0x180011f65  add     r10d, r12d
0x180011f68  jmp     short loc_180011F30
0x180011f6a  not     r9d
0x180011f6d  cmp     r11d, r9d
0x180011f70  jz      short loc_180011F78
0x180011f72  mov     [r13+0Ch], r11d
0x180011f76  jmp     short loc_180011EFD
0x180011f78  lea     rax, [rsp+0E8h+var_50]
0x180011f80  mov     [rsp+0E8h+var_C8], rax; unsigned int *
0x180011f85  mov     r8b, [rsp+0E8h+var_A6]; unsigned __int8
0x180011f8a  mov     edx, edi; unsigned int
0x180011f8c  mov     rcx, r13; struct _CLFS_LOG_BLOCK_HEADER *
0x180011f8f  call    ?ClfsDecodeBlockPrivate@@YAKPEAU_CLFS_LOG_BLOCK_HEADER@@KEEAEAK@Z; ClfsDecodeBlockPrivate(_CLFS_LOG_BLOCK_HEADER *,ulong,uchar,uchar,ulong &)
0x180011f94  mov     edi, eax
0x180011f96  mov     [rsp+0E8h+var_A4], eax
0x180011f9a  test    eax, eax
0x180011f9c  jns     short loc_180011FDF
0x180011f9e  lea     rax, WPP_GLOBAL_Control
0x180011fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fac  cmp     rcx, rax
0x180011faf  jz      short loc_180011FD0
0x180011fb1  test    dword ptr [rcx+1Ch], 8000000h
0x180011fb8  jz      short loc_180011FD0
0x180011fba  mov     [rsp+0E8h+var_B8], edi
0x180011fbe  mov     rax, [rsi+40h]
0x180011fc2  mov     [rsp+0E8h+var_C0], rax
0x180011fc7  mov     rcx, [rcx+10h]
0x180011fcb  call    WPP_SF_slqD
0x180011fd0  mov     edi, 54Fh
0x180011fd5  mov     r13, [rsp+0E8h+CriticalSection]
0x180011fda  jmp     loc_1800123C4
0x180011fdf  mov     rax, [rsp+0E8h+var_58]
0x180011fe7  mov     eax, [rax+48h]
0x180011fea  mov     [rsi+48h], eax
0x180011fed  mov     r10, [rsi+40h]
0x180011ff1  mov     [rsi+70h], r10
0x180011ff5  mov     rcx, rsi; this
0x180011ff8  call    ?GetFirstRecord@CLogIocb@@QEAAPEAU_CLFS_RECORD_HEADER@@XZ; CLogIocb::GetFirstRecord(void)
0x180011ffd  mov     [rsi+68h], rax
0x180012001  lea     r9, [rsp+0E8h+var_70]; union _CLS_LSN *
0x180012006  lea     r8, [rsp+0E8h+var_68]; struct _CLFS_RECORD_HEADER **
0x18001200e  mov     rdx, r10; unsigned __int8 *
0x180012011  lea     rcx, [rsp+0E8h+var_98]; union _CLS_LSN *
0x180012016  call    ?ClfsFindLsnInBlock@@YAKAEBT_CLS_LSN@@PEAEAEAPEAU_CLFS_RECORD_HEADER@@AEAT1@@Z; ClfsFindLsnInBlock(_CLS_LSN const &,uchar *,_CLFS_RECORD_HEADER * &,_CLS_LSN &)
0x18001201b  cmp     rbx, qword ptr [rsp+0E8h+var_70]
0x180012020  jnz     loc_180012132
0x180012026  mov     rcx, [rsp+0E8h+var_68]
0x18001202e  mov     rax, [rsi+40h]
0x180012032  mov     [rsi+70h], rax
0x180012036  test    rcx, rcx
0x180012039  jnz     short loc_180012049
0x18001203b  mov     rcx, rsi; this
0x18001203e  call    ?GetFirstRecord@CLogIocb@@QEAAPEAU_CLFS_RECORD_HEADER@@XZ; CLogIocb::GetFirstRecord(void)
0x180012043  mov     [rsi+68h], rax
0x180012047  jmp     short loc_18001204D
0x180012049  mov     [rsi+68h], rcx
0x18001204d  mov     ecx, [r14+88h]
0x180012054  test    ecx, ecx
0x180012056  jnz     short loc_18001205C
0x180012058  xor     edx, edx
0x18001205a  jmp     short loc_18001206C
0x18001205c  movzx   edx, word ptr [r13+4]
0x180012061  shl     edx, 9
0x180012064  dec     edx
0x180012066  add     edx, ecx
0x180012068  neg     ecx
0x18001206a  and     edx, ecx
0x18001206c  mov     rcx, [rsp+0E8h+arg_10]
0x180012074  mov     [rcx], edx
0x180012076  mov     [rsp+0E8h+arg_10], 0
0x180012082  mov     [rsp+0E8h+var_58], 0
0x18001208e  mov     rcx, qword ptr cs:CLFS_LSN_INVALID
0x180012095  cmp     rcx, rbx
0x180012098  jz      short loc_180012115
0x18001209a  mov     r8, [r14+0A8h]
0x1800120a1  mov     eax, ebx
0x1800120a3  and     eax, 0FFFFFE00h
0x1800120a8  add     eax, edx
0x1800120aa  mov     edx, dword ptr [rsp+0E8h+var_98+4]
0x1800120ae  imul    rdx, r8
0x1800120b2  add     rax, rdx
0x1800120b5  xor     edx, edx
0x1800120b7  div     r8
0x1800120ba  mov     [rsp+0E8h+arg_10], rax
0x1800120c2  shr     rax, 20h
0x1800120c6  test    eax, eax
0x1800120c8  jnz     short loc_180012115
0x1800120ca  mov     r8d, dword ptr [rsp+0E8h+arg_10]
0x1800120d2  mov     [rsp+0E8h+arg_10], rdx
0x1800120da  shr     rdx, 20h
0x1800120de  test    edx, edx
0x1800120e0  jnz     short loc_180012115
0x1800120e2  cmp     r8d, r15d
0x1800120e5  jz      short loc_180012115
0x1800120e7  mov     eax, dword ptr [rsp+0E8h+arg_10]
0x1800120ee  test    eax, 1FFh
0x1800120f3  jnz     short loc_180012115
0x1800120f5  mov     dword ptr [rsp+0E8h+var_80+4], r8d
0x1800120fa  mov     dword ptr [rsp+0E8h+var_80], eax
0x1800120fe  mov     dword ptr [rsp+0E8h+arg_10], eax
0x180012105  mov     dword ptr [rsp+0E8h+arg_10+4], r8d
0x18001210d  mov     rcx, [rsp+0E8h+arg_10]
0x180012115  mov     r11, [rsp+0E8h+var_88]
0x18001211a  mov     [r11], rcx
0x18001211d  mov     rax, [rsp+0E8h+arg_18]
0x180012125  mov     [rax], r12b
0x180012128  mov     r13, [rsp+0E8h+CriticalSection]
0x18001212d  jmp     loc_1800123CD
0x180012132  mov     eax, r15d
0x180012135  lea     r11, [rsi+0A0h]
0x18001213c  test    r11, r11
0x18001213f  jz      short loc_180012149
0x180012141  mov     eax, [r11]
0x180012144  and     eax, 0FFFFFE00h
0x180012149  mov     ecx, r15d
0x18001214c  test    r11, r11
0x18001214f  jz      short loc_180012155
0x180012151  mov     ecx, [r11+4]
0x180012155  cmp     ecx, r15d
0x180012158  jz      short loc_18001217E
0x18001215a  test    eax, 1FFh
0x18001215f  jnz     short loc_18001217E
0x180012161  mov     [rsp+0E8h+var_4C], ecx
0x180012168  mov     [rsp+0E8h+var_50], eax
0x18001216f  mov     dword ptr [rsp+0E8h+var_80], eax
0x180012173  mov     dword ptr [rsp+0E8h+var_80+4], ecx
0x180012177  mov     r10, [rsp+0E8h+var_80]
0x18001217c  jmp     short loc_18001218A
0x18001217e  mov     r10, qword ptr cs:CLFS_LSN_INVALID
0x180012185  mov     [rsp+0E8h+var_80], r10
0x18001218a  mov     rcx, rsi; this
0x18001218d  call    ?GetFirstRecord@CLogIocb@@QEAAPEAU_CLFS_RECORD_HEADER@@XZ; CLogIocb::GetFirstRecord(void)
0x180012192  test    rax, rax
0x180012195  jz      short loc_18001219D
0x180012197  cmp     [rax], r10
0x18001219a  setz    al
0x18001219d  test    al, al
0x18001219f  jz      short loc_1800121C2
0x1800121a1  movzx   eax, word ptr [r13+4]
0x1800121a6  shl     eax, 9
0x1800121a9  mov     rcx, [rsp+0E8h+arg_10]
0x1800121b1  mov     [rcx], eax
0x1800121b3  mov     edi, 490h
0x1800121b8  mov     r13, [rsp+0E8h+CriticalSection]
0x1800121bd  jmp     loc_1800123C9
0x1800121c2  mov     edx, [rsp+0E8h+var_A0]
  ... truncated ...
```
