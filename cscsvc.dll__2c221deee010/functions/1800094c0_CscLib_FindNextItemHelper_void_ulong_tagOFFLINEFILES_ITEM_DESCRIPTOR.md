# CscLib_FindNextItemHelper(void *,ulong,tagOFFLINEFILES_ITEM_DESCRIPTOR *)

- ea: `0x1800094c0`
- end: `0x180009e0f`
- name: `?CscLib_FindNextItemHelper@@YAJPEAXKPEAUtagOFFLINEFILES_ITEM_DESCRIPTOR@@@Z`
- size: `2383`
- prototype: `int(void *, unsigned int, struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)`
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180008310`
- `0x180008f40`
- `0x180009440`

## callees

- `0x1800068b0`
- `0x180007230`
- `0x18000801c`
- `0x1800094c0`
- `0x180009e20`
- `0x18000a6c8`
- `0x18001b4e0`
- `0x180039610`
- `0x180039fb4`
- `0x18003c4e8`
- `0x180044a84`
- `0x180046ad8`
- `0x180087614`

## import_xrefs

- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x1800098bd`
- `ntdll!RtlpApplyLengthFunction` at `0x1800098d5`
- `ntdll!RtlpApplyLengthFunction` at `0x1800098d5`
- `ntdll!RtlAppendPathElement` at `0x1800098af`
- `ntdll!RtlAppendPathElement` at `0x1800098af`
- `ntdll!RtlpEnsureBufferSize` at `0x18000980d`
- `ntdll!RtlpEnsureBufferSize` at `0x1800099d1`
- `ntdll!RtlpEnsureBufferSize` at `0x18000980d`
- `ntdll!RtlpEnsureBufferSize` at `0x1800099d1`
- `ntdll!RtlFreeUnicodeString` at `0x180009d95`
- `ntdll!RtlFreeUnicodeString` at `0x180009d95`
- `ntdll!RtlInitUnicodeString` at `0x1800097d0`
- `ntdll!RtlInitUnicodeString` at `0x180009898`
- `ntdll!RtlInitUnicodeString` at `0x180009994`
- `ntdll!RtlInitUnicodeString` at `0x180009a7c`
- `ntdll!RtlInitUnicodeString` at `0x1800097d0`
- `ntdll!RtlInitUnicodeString` at `0x180009898`
- `ntdll!RtlInitUnicodeString` at `0x180009994`
- `ntdll!RtlInitUnicodeString` at `0x180009a7c`
- `ntdll!NtClose` at `0x180009ae3`
- `ntdll!NtClose` at `0x180009ae3`

## pseudocode

```c
__int64 __fastcall CscLib_FindNextItemHelper(__int64 *a1, int a2, struct tagOFFLINEFILES_ITEM_DESCRIPTOR *a3)
{
  __int64 *v3; // rsi
  int v4; // r12d
  struct tagOFFLINEFILES_ITEM_DESCRIPTOR *v5; // r13
  __int64 v6; // rcx
  int v7; // r15d
  int Next; // eax
  int v9; // ebx
  int v10; // ebx
  int v12; // r11d
  char *v13; // rdx
  _WORD *v14; // rdi
  __int64 v15; // r10
  _WORD *v16; // r8
  __int64 v17; // rcx
  __int64 v18; // r9
  _WORD *v19; // rcx
  _WORD *v20; // rdx
  __int64 v21; // r8
  char *v22; // rcx
  int v23; // eax
  _WORD *v24; // rcx
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  int v27; // eax
  __int128 v28; // xmm0
  __int64 v29; // xmm1_8
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int64 v32; // rax
  __int128 v33; // xmm0
  unsigned __int64 v35; // rcx
  const WCHAR *v36; // rdx
  USHORT v37; // r8
  unsigned __int16 v38; // dx
  SIZE_T v39; // rax
  unsigned __int64 v40; // r8
  int appended; // eax
  int v42; // ebx
  NTSTATUS v43; // eax
  WCHAR *v44; // rax
  const WCHAR *v45; // rbx
  USHORT Length; // r8
  unsigned __int16 v47; // dx
  SIZE_T v48; // rax
  unsigned __int64 v49; // rdx
  int v50; // r12d
  int v51; // r14d
  int v52; // edi
  int v53; // eax
  int v54; // r8d
  int v55; // edi
  CObjectMonitor *v56; // rcx
  __int16 v57; // ax
  int v58; // ecx
  unsigned __int64 v59; // xmm0_8
  WCHAR *v60; // rdx
  USHORT v61; // ax
  int v62; // eax
  unsigned int ConstBuffer; // eax
  __int64 v64; // r10
  unsigned int v65; // eax
  __int64 v66; // r10
  struct _UNICODE_STRING DestinationString_8; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v68; // [rsp+58h] [rbp-B0h] BYREF
  int UnicodeString; // [rsp+60h] [rbp-A8h]
  int UnicodeString_4; // [rsp+64h] [rbp-A4h]
  struct _UNICODE_STRING UnicodeString_8; // [rsp+68h] [rbp-A0h] BYREF
  struct tagOFFLINEFILES_ITEM_DESCRIPTOR *v72; // [rsp+78h] [rbp-90h]
  __int64 *v73; // [rsp+80h] [rbp-88h]
  __int128 v74; // [rsp+88h] [rbp-80h] BYREF
  __int128 v75; // [rsp+98h] [rbp-70h]
  __int128 v76; // [rsp+A8h] [rbp-60h]
  __int128 v77; // [rsp+B8h] [rbp-50h]
  __int128 v78; // [rsp+C8h] [rbp-40h]
  __int128 v79; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v80; // [rsp+E8h] [rbp-20h]
  __int128 v81; // [rsp+F8h] [rbp-10h]
  __int64 v82; // [rsp+108h] [rbp+0h]
  __int128 v83; // [rsp+110h] [rbp+8h] BYREF
  int v84; // [rsp+120h] [rbp+18h]
  _WORD v85[2]; // [rsp+128h] [rbp+20h] BYREF
  char v86; // [rsp+12Ch] [rbp+24h] BYREF
  int UnicodeStringOrUnicodeStringBuffer; // [rsp+330h] [rbp+228h] BYREF
  char v88; // [rsp+334h] [rbp+22Ch] BYREF
  PUCHAR v89; // [rsp+338h] [rbp+230h]
  _RTL_BUFFER Buffer; // [rsp+340h] [rbp+238h] BYREF

  v3 = a1;
  v4 = a2;
  v5 = a3;
  v72 = a3;
  UnicodeString = a2;
  v73 = a1;
  memset_0(a3, 0, 0x300u);
  memset_0(v85, 0, 0x226u);
  v6 = *v3;
  v7 = 0;
  v74 = 0;
  v82 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  Next = CscUmFindNext(v6, v85, &v74, &v79, 0);
  v9 = Next;
  if ( Next < 0 )
  {
    if ( Next == -2147483642 )
    {
      v10 = 1;
LABEL_4:
      memset_0(v5, 0, 0x300u);
      goto LABEL_5;
    }
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      ConstBuffer = (unsigned int)CPath::_GetConstBuffer((CPath *)(v3 + 1));
      WPP_SF_Sd(
        *(_QWORD *)(v64 + 16),
        10,
        (unsigned int)WPP_640353d05de230bd321f309b7bf8540c_Traceguids,
        ConstBuffer,
        v9);
    }
    v10 = ResultFromNtStatus(v9);
    if ( v10 )
      goto LABEL_4;
    goto LABEL_5;
  }
  v12 = v74;
  if ( (v4 & 0x10) == 0 && (v74 & 0x800000) != 0 )
  {
    v10 = -2147024846;
    goto LABEL_4;
  }
  v13 = &v86;
  v14 = (_WORD *)((char *)v5 + 214);
  v10 = 0;
  v15 = 2147483646;
  UnicodeString_4 = 0;
  v16 = (_WORD *)((char *)v5 + 214);
  v17 = 2147483646;
  v18 = 261;
  do
  {
    if ( !v17 )
      break;
    if ( !*(_WORD *)v13 )
      break;
    *v16 = *(_WORD *)v13;
    v13 += 2;
    ++v16;
    --v17;
    --v18;
  }
  while ( v18 );
  v19 = v16 - 1;
  v20 = (_WORD *)((char *)v5 + 736);
  if ( v18 )
    v19 = v16;
  v21 = 13;
  *v19 = 0;
  v22 = &v88;
  do
  {
    if ( !v15 )
      break;
    if ( !*(_WORD *)v22 )
      break;
    *v20 = *(_WORD *)v22;
    v22 += 2;
    ++v20;
    --v15;
    --v21;
  }
  while ( v21 );
  v23 = DWORD1(v74);
  v24 = v20 - 1;
  v25 = v75;
  v26 = v76;
  if ( v21 )
    v24 = v20;
  *v24 = 0;
  *(_DWORD *)v5 |= 7u;
  *((_OWORD *)v5 + 1) = v25;
  *((_DWORD *)v5 + 2) = v23;
  v27 = DWORD2(v74);
  v28 = v77;
  *((_OWORD *)v5 + 2) = v26;
  *((_DWORD *)v5 + 3) = v27;
  LOBYTE(v27) = BYTE8(v78);
  v29 = v78;
  *((_OWORD *)v5 + 3) = v28;
  *((_BYTE *)v5 + 212) = v27;
  v30 = v79;
  LOBYTE(v27) = BYTE9(v78);
  *((_QWORD *)v5 + 8) = v29;
  v31 = v80;
  *((_BYTE *)v5 + 213) = v27;
  v32 = -1;
  *(_OWORD *)((char *)v5 + 72) = v30;
  *((_DWORD *)v5 + 1) = v12;
  v33 = v81;
  *(_OWORD *)((char *)v5 + 88) = v31;
  *(_QWORD *)&v31 = v82;
  *(_OWORD *)((char *)v5 + 104) = v33;
  *((_QWORD *)v5 + 15) = v31;
  while ( v14[++v32] != 0 )
    ;
  v35 = (unsigned __int64)v5 + 2 * v32 + 214;
  if ( v35 > (unsigned __int64)v14 && *(_WORD *)(v35 - 2) == 92 )
    *(_WORD *)(v35 - 2) = 0;
  if ( *v14 != 46 || (v57 = *((_WORD *)v5 + 108)) != 0 && (v57 != 46 || *((_WORD *)v5 + 109)) )
  {
    v36 = (const WCHAR *)v3[68];
    if ( v36 == (const WCHAR *)v3[69] )
      v36 = (const WCHAR *)v3[67];
    v85[0] = 0;
    Buffer.Buffer = (PUCHAR)v85;
    Buffer.StaticBuffer = (PUCHAR)v85;
    Buffer.Size = 520;
    v89 = (PUCHAR)v85;
    Buffer.StaticSize = 520;
    UnicodeStringOrUnicodeStringBuffer = 34078720;
    if ( v36 && *v36 )
    {
      DestinationString_8 = 0;
      RtlInitUnicodeString(&DestinationString_8, v36);
      Length = DestinationString_8.Length;
      v47 = 0;
      LOWORD(UnicodeStringOrUnicodeStringBuffer) = 0;
      v48 = DestinationString_8.Length + 2LL;
      if ( v48 > 0xFFFE )
      {
        v58 = -1073741562;
      }
      else
      {
        if ( v48 <= Buffer.Size )
        {
LABEL_57:
          v89 = Buffer.Buffer;
          memmove_0(&Buffer.Buffer[2 * ((unsigned __int64)v47 >> 1)], DestinationString_8.Buffer, Length);
          v49 = (unsigned __int16)(DestinationString_8.Length + UnicodeStringOrUnicodeStringBuffer);
          LOWORD(UnicodeStringOrUnicodeStringBuffer) = v49;
          HIWORD(UnicodeStringOrUnicodeStringBuffer) = v49 + 2;
          *(_WORD *)&v89[2 * (v49 >> 1)] = 0;
          goto LABEL_34;
        }
        if ( RtlpEnsureBufferSize(0, &Buffer, DestinationString_8.Length + 2LL) >= 0 )
        {
          v47 = UnicodeStringOrUnicodeStringBuffer;
          Length = DestinationString_8.Length;
          goto LABEL_57;
        }
        v58 = -1073741801;
      }
    }
    else
    {
      DestinationString_8 = 0;
      RtlInitUnicodeString(&DestinationString_8, L"\\\\");
      v37 = DestinationString_8.Length;
      v38 = 0;
      LOWORD(UnicodeStringOrUnicodeStringBuffer) = 0;
      v39 = DestinationString_8.Length + 2LL;
      if ( v39 <= 0xFFFE )
      {
        if ( v39 > Buffer.Size )
        {
          if ( RtlpEnsureBufferSize(0, &Buffer, DestinationString_8.Length + 2LL) < 0 )
          {
            v58 = -1073741801;
            goto LABEL_85;
          }
          v38 = UnicodeStringOrUnicodeStringBuffer;
          v37 = DestinationString_8.Length;
        }
        v89 = Buffer.Buffer;
        memmove_0(&Buffer.Buffer[2 * ((unsigned __int64)v38 >> 1)], DestinationString_8.Buffer, v37);
        v40 = (unsigned __int16)(DestinationString_8.Length + UnicodeStringOrUnicodeStringBuffer);
        LOWORD(UnicodeStringOrUnicodeStringBuffer) = v40;
        HIWORD(UnicodeStringOrUnicodeStringBuffer) = v40 + 2;
        *(_WORD *)&v89[2 * (v40 >> 1)] = 0;
        goto LABEL_34;
      }
      v58 = -1073741562;
    }
LABEL_85:
    v10 = ResultFromNtStatus(v58);
LABEL_34:
    if ( v10 < 0 )
      goto LABEL_104;
    UnicodeString_8 = 0;
    RtlInitUnicodeString(&UnicodeString_8, (PCWSTR)v5 + 107);
    appended = RtlAppendPathElement(1, &UnicodeStringOrUnicodeStringBuffer, &UnicodeString_8);
    if ( appended < 0 && (int)ResultFromNtStatus(appended) < 0 )
      goto LABEL_104;
    v42 = 0;
    v43 = RtlpApplyLengthFunction(
            0,
            0x38u,
            &UnicodeStringOrUnicodeStringBuffer,
            RtlGetLengthWithoutTrailingPathSeperators);
    if ( v43 < 0 )
      v42 = ResultFromNtStatus(v43);
    if ( v42 < 0 )
      goto LABEL_104;
    v44 = (WCHAR *)Buffer.Buffer;
    v45 = (const WCHAR *)v89;
    if ( Buffer.Buffer != Buffer.StaticBuffer )
      v45 = (const WCHAR *)Buffer.Buffer;
    if ( (v4 & 2) == 0 || (*(_BYTE *)v5 & 0x10) != 0 )
    {
LABEL_42:
      if ( (v4 & 4) == 0 || (*(_BYTE *)v5 & 0x20) != 0 )
        goto LABEL_43;
      CscLib_FillInLocalDirtyByteCount(v45, *(union _LARGE_INTEGER *)((char *)v5 + 112), v5);
      *(_DWORD *)v5 |= 0x20u;
LABEL_104:
      v44 = (WCHAR *)Buffer.Buffer;
LABEL_43:
      if ( v44 && v44 != (WCHAR *)Buffer.StaticBuffer )
      {
        *(_QWORD *)&UnicodeString_8.Length = 0;
        UnicodeString_8.Buffer = v44;
        RtlFreeUnicodeString(&UnicodeString_8);
      }
      v10 = UnicodeString_4;
      v3 = v73;
      if ( Buffer.StaticBuffer )
        *(_WORD *)Buffer.StaticBuffer = 0;
      goto LABEL_5;
    }
    v68 = 0;
    v50 = v4 & 0x40000000;
    v51 = 0;
    UnicodeString_8 = 0;
    RtlInitUnicodeString(&UnicodeString_8, v45);
    *(_QWORD *)&DestinationString_8.Length = 0;
    v83 = 0;
    v84 = 0;
    if ( CscUmpLibraryState )
    {
      v52 = CscDriverOpenItemWithDispositionEx(
              (PHANDLE)&DestinationString_8,
              0,
              &UnicodeString_8,
              0,
              1048704,
              7u,
              1u,
              0);
      if ( v52 >= 0 )
      {
        v52 = CscDriverQueryHandleInformation(*(_QWORD *)&DestinationString_8.Length, &v83);
        if ( v52 >= 0 )
        {
          v51 = DWORD2(v83);
          v7 = HIDWORD(v83);
          v68 = *((_QWORD *)&v83 + 1);
        }
      }
      if ( *(_QWORD *)&DestinationString_8.Length )
        NtClose(*(HANDLE *)&DestinationString_8.Length);
      if ( v52 != -1073741209 )
      {
LABEL_64:
        if ( v52 >= 0 )
        {
LABEL_65:
          v53 = ResultFromNtStatus(v52);
          v55 = v53;
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_SDdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v54, (_DWORD)v45, v53, v51, v7);
          }
          v5 = v72;
          v44 = (WCHAR *)Buffer.Buffer;
          LOBYTE(v4) = UnicodeString;
          if ( v55 >= 0 )
          {
            *(_DWORD *)v72 |= 0x10u;
            *((_DWORD *)v5 + 51) = v51;
            *((_DWORD *)v5 + 52) = v7;
          }
          goto LABEL_42;
        }
        goto LABEL_72;
      }
      if ( v50 )
      {
        DestinationString_8 = 0;
        v56 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            (unsigned int)WPP_640353d05de230bd321f309b7bf8540c_Traceguids,
            (_DWORD)v45,
            v50 == 0);
          v56 = WPP_GLOBAL_Control;
        }
        if ( UnicodeString_8.Length < 2u )
        {
          v52 = -1073741585;
          goto LABEL_73;
        }
        DestinationString_8 = UnicodeString_8;
        v59 = _mm_srli_si128((__m128i)UnicodeString_8, 8).m128i_u64[0];
        v60 = (WCHAR *)(v59 + 2 * (((unsigned __int64)UnicodeString_8.Length >> 1) - 1));
        v61 = UnicodeString_8.Length;
        if ( v59 < (unsigned __int64)v60 )
        {
          do
          {
            if ( *v60 == 92 )
              break;
            v61 -= 2;
            --v60;
            DestinationString_8.Length = v61;
          }
          while ( DestinationString_8.Buffer < v60 );
        }
        DestinationString_8.MaximumLength = v61;
        v62 = CscUmQueryPathConnectionState(&DestinationString_8, 0, &v68, (char *)&v68 + 4);
        v51 = v68;
        v52 = v62;
        v7 = HIDWORD(v68);
        goto LABEL_64;
      }
    }
    else
    {
      v52 = -1073741436;
    }
LABEL_72:
    v56 = WPP_GLOBAL_Control;
LABEL_73:
    if ( v56 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v56 + 28) & 2) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)v56 + 2),
        27,
        (unsigned int)WPP_640353d05de230bd321f309b7bf8540c_Traceguids,
        (_DWORD)v45,
        v52);
    goto LABEL_65;
  }
LABEL_5:
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v65 = (unsigned int)CPath::_GetConstBuffer((CPath *)(v3 + 1));
    WPP_SF_Sd(*(_QWORD *)(v66 + 16), 11, (unsigned int)WPP_640353d05de230bd321f309b7bf8540c_Traceguids, v65, v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800094c0  mov     r11, rsp
0x1800094c3  push    rbp
0x1800094c4  push    rbx
0x1800094c5  push    rsi
0x1800094c6  lea     rbp, [r11-2A8h]
0x1800094cd  sub     rsp, 390h
0x1800094d4  mov     rax, cs:__security_cookie
0x1800094db  xor     rax, rsp
0x1800094de  mov     [rbp+2A0h+Buffer.ReservedForIMalloc], rax
0x1800094e5  mov     [r11-20h], r12
0x1800094e9  mov     rsi, rcx
0x1800094ec  mov     [r11-28h], r13
0x1800094f0  mov     r12d, edx
0x1800094f3  mov     r13, r8
0x1800094f6  mov     [rsp+3A0h+var_330], r8
0x1800094fb  mov     dword ptr [rsp+3A0h+UnicodeString.Length], edx
0x1800094ff  mov     r8d, 300h; Size
0x180009505  mov     [rsp+3A0h+var_328], rcx
0x18000950a  xor     edx, edx; Val
0x18000950c  mov     [r11-30h], r14
0x180009510  mov     rcx, r13; void *
0x180009513  mov     [r11-38h], r15
0x180009517  call    memset_0
0x18000951c  xor     edx, edx; Val
0x18000951e  lea     rcx, [rbp+2A0h+var_280]; void *
0x180009522  mov     r8d, 226h; Size
0x180009528  call    memset_0
0x18000952d  mov     rcx, [rsi]
0x180009530  lea     r9, [rbp+2A0h+var_2D0]
0x180009534  xorps   xmm0, xmm0
0x180009537  lea     r8, [rbp+2A0h+var_320]
0x18000953b  xor     r15d, r15d
0x18000953e  lea     rdx, [rbp+2A0h+var_280]
0x180009542  mov     qword ptr [rsp+3A0h+DestinationString.Length], r15
0x180009547  xor     eax, eax
0x180009549  mov     qword ptr [rsp+3A0h+var_370], r15
0x18000954e  mov     qword ptr [rsp+3A0h+var_380], r15
0x180009553  movups  [rbp+2A0h+var_320], xmm0
0x180009557  mov     [rbp+2A0h+var_2A0], rax
0x18000955b  movups  [rbp+2A0h+var_310], xmm0
0x18000955f  movups  [rbp+2A0h+var_300], xmm0
0x180009563  movups  [rbp+2A0h+var_2F0], xmm0
0x180009567  movups  [rbp+2A0h+var_2E0], xmm0
0x18000956b  movups  [rbp+2A0h+var_2D0], xmm0
0x18000956f  movups  [rbp+2A0h+var_2C0], xmm0
0x180009573  movups  [rbp+2A0h+var_2B0], xmm0
0x180009577  call    CscUmFindNext
0x18000957c  lea     r14, WPP_GLOBAL_Control
0x180009583  mov     ebx, eax
0x180009585  test    eax, eax
0x180009587  jns     short loc_1800095FC
0x180009589  cmp     eax, 80000006h
0x18000958e  jnz     loc_180009DA0
0x180009594  mov     ebx, 1
0x180009599  xor     edx, edx; Val
0x18000959b  mov     r8d, 300h; Size
0x1800095a1  mov     rcx, r13; void *
0x1800095a4  call    memset_0
0x1800095a9  mov     r10, cs:WPP_GLOBAL_Control
0x1800095b0  mov     r15, [rsp+3A0h+var_30]
0x1800095b8  cmp     r10, r14
0x1800095bb  mov     r14, [rsp+3A0h+var_28]
0x1800095c3  mov     r13, [rsp+3A0h+var_20]
0x1800095cb  mov     r12, [rsp+388h]
0x1800095d3  jz      short loc_1800095E0
0x1800095d5  test    byte ptr [r10+1Ch], 8
0x1800095da  jnz     loc_180009DE5
0x1800095e0  mov     eax, ebx
0x1800095e2  mov     rcx, [rbp+2A0h+Buffer.ReservedForIMalloc]
0x1800095e9  xor     rcx, rsp; StackCookie
0x1800095ec  call    __security_check_cookie
0x1800095f1  add     rsp, 390h
0x1800095f8  pop     rsi
0x1800095f9  pop     rbx
0x1800095fa  pop     rbp
0x1800095fb  retn
0x1800095fc  mov     r11d, dword ptr [rbp+2A0h+var_320]
0x180009600  test    r12b, 10h
0x180009604  jz      loc_180009950
0x18000960a  mov     [rsp+3A0h+arg_8], rdi
0x180009612  lea     rdx, [rbp+2A0h+var_27C]
0x180009616  lea     rdi, [r13+0D6h]
0x18000961d  mov     ebx, r15d
0x180009620  mov     r10d, 7FFFFFFEh
0x180009626  mov     dword ptr [rsp+3A0h+UnicodeString+4], ebx
0x18000962a  mov     r8, rdi
0x18000962d  mov     ecx, r10d
0x180009630  mov     r9d, 105h
0x180009636  test    rcx, rcx
0x180009639  jz      short loc_180009658
0x18000963b  movzx   eax, word ptr [rdx]
0x18000963e  test    ax, ax
0x180009641  jz      short loc_180009658
0x180009643  mov     [r8], ax
0x180009647  add     rdx, 2
0x18000964b  add     r8, 2
0x18000964f  dec     rcx
0x180009652  sub     r9, 1
0x180009656  jnz     short loc_180009636
0x180009658  lea     rcx, [r8-2]
0x18000965c  test    r9, r9
0x18000965f  lea     rdx, [r13+2E0h]
0x180009666  cmovnz  rcx, r8
0x18000966a  mov     r8d, 0Dh
0x180009670  mov     [rcx], r15w
0x180009674  lea     rcx, [rbp+2A0h+var_74]
0x18000967b  nop     dword ptr [rax+rax+00h]
0x180009680  test    r10, r10
0x180009683  jz      short loc_1800096A1
0x180009685  movzx   eax, word ptr [rcx]
0x180009688  test    ax, ax
0x18000968b  jz      short loc_1800096A1
0x18000968d  mov     [rdx], ax
0x180009690  add     rcx, 2
0x180009694  add     rdx, 2
0x180009698  dec     r10
0x18000969b  sub     r8, 1
0x18000969f  jnz     short loc_180009680
0x1800096a1  mov     eax, dword ptr [rbp+2A0h+var_320+4]
0x1800096a4  lea     rcx, [rdx-2]
0x1800096a8  movaps  xmm0, [rbp+2A0h+var_310]
0x1800096ac  test    r8, r8
0x1800096af  movaps  xmm1, [rbp+2A0h+var_300]
0x1800096b3  cmovnz  rcx, rdx
0x1800096b7  mov     [rcx], r15w
0x1800096bb  or      dword ptr [r13+0], 7
0x1800096c0  movups  xmmword ptr [r13+10h], xmm0
0x1800096c5  mov     [r13+8], eax
0x1800096c9  mov     eax, dword ptr [rbp+2A0h+var_320+8]
0x1800096cc  movaps  xmm0, [rbp+2A0h+var_2F0]
0x1800096d0  movups  xmmword ptr [r13+20h], xmm1
0x1800096d5  mov     [r13+0Ch], eax
0x1800096d9  movzx   eax, byte ptr [rbp+2A0h+var_2E0+8]
0x1800096dd  movsd   xmm1, qword ptr [rbp+2A0h+var_2E0]
0x1800096e2  movups  xmmword ptr [r13+30h], xmm0
0x1800096e7  mov     [r13+0D4h], al
0x1800096ee  movups  xmm0, [rbp+2A0h+var_2D0]
0x1800096f2  movzx   eax, byte ptr [rbp+2A0h+var_2E0+9]
0x1800096f6  movsd   qword ptr [r13+40h], xmm1
0x1800096fc  movups  xmm1, [rbp+2A0h+var_2C0]
0x180009700  mov     [r13+0D5h], al
0x180009707  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000970e  movups  xmmword ptr [r13+48h], xmm0
0x180009713  mov     [r13+4], r11d
0x180009717  movups  xmm0, [rbp+2A0h+var_2B0]
0x18000971b  movups  xmmword ptr [r13+58h], xmm1
0x180009720  movsd   xmm1, [rbp+2A0h+var_2A0]
0x180009725  movups  xmmword ptr [r13+68h], xmm0
0x18000972a  movsd   qword ptr [r13+78h], xmm1
0x180009730  cmp     [rdi+rax*2+2], bx
0x180009735  lea     rax, [rax+1]
0x180009739  jnz     short loc_180009730
0x18000973b  lea     rcx, [r13+0D6h]
0x180009742  lea     rcx, [rcx+rax*2]
0x180009746  cmp     rcx, rdi
0x180009749  ja      loc_180009965
0x18000974f  cmp     word ptr [rdi], 2Eh ; '.'
0x180009753  jz      loc_180009BBD
0x180009759  mov     rdx, [rsi+220h]
0x180009760  cmp     rdx, [rsi+228h]
0x180009767  jnz     short loc_180009770
0x180009769  mov     rdx, [rsi+218h]; SourceString
0x180009770  mov     [rbp+2A0h+var_280], r15w
0x180009775  lea     rax, [rbp+2A0h+var_280]
0x180009779  mov     [rbp+2A0h+Buffer.Buffer], rax
0x180009780  lea     rax, [rbp+2A0h+var_280]
0x180009784  mov     [rbp+2A0h+Buffer.StaticBuffer], rax
0x18000978b  mov     ecx, 208h
0x180009790  mov     [rbp+2A0h+Buffer.Size], rcx
0x180009797  lea     rax, [rbp+2A0h+var_280]
0x18000979b  mov     [rbp+2A0h+var_70], rax
0x1800097a2  mov     [rbp+2A0h+Buffer.StaticSize], rcx
0x1800097a9  mov     [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer], 2080000h
0x1800097b3  test    rdx, rdx
0x1800097b6  jnz     loc_18000997E
0x1800097bc  xorps   xmm0, xmm0
0x1800097bf  lea     rdx, asc_18008FC74; "\\\\"
0x1800097c6  lea     rcx, [rsp+3A0h+DestinationString.Buffer]; DestinationString
0x1800097cb  movups  xmmword ptr [rsp+3A0h+DestinationString.Buffer], xmm0
0x1800097d0  call    cs:__imp_RtlInitUnicodeString
0x1800097d6  movzx   r8d, word ptr [rsp+3A0h+DestinationString.Buffer]
0x1800097dc  mov     esi, 0FFFEh
0x1800097e1  mov     edx, r15d
0x1800097e4  mov     word ptr [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer], dx
0x1800097eb  lea     rax, [r8+2]
0x1800097ef  cmp     rax, rsi
0x1800097f2  ja      loc_180009BFB
0x1800097f8  cmp     rax, [rbp+2A0h+Buffer.Size]
0x1800097ff  jbe     short loc_180009828
0x180009801  mov     r8, rax; RequiredSize
0x180009804  lea     rdx, [rbp+2A0h+Buffer]; Buffer
0x18000980b  xor     ecx, ecx; Flags
0x18000980d  call    cs:__imp_RtlpEnsureBufferSize
0x180009813  test    eax, eax
0x180009815  js      loc_180009C02
0x18000981b  movzx   edx, word ptr [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer]
0x180009822  movzx   r8d, word ptr [rsp+3A0h+DestinationString.Buffer]
0x180009828  mov     rcx, [rbp+2A0h+Buffer.Buffer]
0x18000982f  movzx   eax, dx
0x180009832  mov     rdx, [rsp+3A0h+Src]; Src
0x180009837  shr     rax, 1
0x18000983a  mov     [rbp+2A0h+var_70], rcx
0x180009841  movzx   r8d, r8w; Size
0x180009845  lea     rcx, [rcx+rax*2]; void *
0x180009849  call    memmove_0
0x18000984e  movzx   eax, word ptr [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer]
0x180009855  add     ax, word ptr [rsp+3A0h+DestinationString.Buffer]
0x18000985a  movzx   r8d, ax
0x18000985e  mov     word ptr [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer], r8w
0x180009866  lea     eax, [r8+2]
0x18000986a  shr     r8, 1
0x18000986d  mov     word ptr [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer+2], ax
0x180009874  mov     rax, [rbp+2A0h+var_70]
0x18000987b  mov     [rax+r8*2], r15w
0x180009880  test    ebx, ebx
0x180009882  js      loc_180009D7A
0x180009888  xorps   xmm0, xmm0
0x18000988b  lea     rcx, [rsp+3A0h+UnicodeString.Buffer]; DestinationString
0x180009890  mov     rdx, rdi; SourceString
0x180009893  movups  xmmword ptr [rsp+3A0h+UnicodeString.Buffer], xmm0
0x180009898  call    cs:__imp_RtlInitUnicodeString
0x18000989e  lea     r8, [rsp+3A0h+UnicodeString.Buffer]
0x1800098a3  mov     ecx, 1
0x1800098a8  lea     rdx, [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer]
0x1800098af  call    cs:__imp_RtlAppendPathElement
0x1800098b5  test    eax, eax
0x1800098b7  js      loc_180009C13
0x1800098bd  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x1800098c4  lea     r8, [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer]; UnicodeStringOrUnicodeStringBuffer
0x1800098cb  mov     edx, 38h ; '8'; Type
0x1800098d0  xor     ecx, ecx; Flags
0x1800098d2  mov     ebx, r15d
0x1800098d5  call    cs:__imp_RtlpApplyLengthFunction
0x1800098db  test    eax, eax
0x1800098dd  js      loc_180009C27
0x1800098e3  test    ebx, ebx
0x1800098e5  js      loc_180009D7A
0x1800098eb  mov     rax, [rbp+2A0h+Buffer.Buffer]
0x1800098f2  cmp     rax, [rbp+2A0h+Buffer.StaticBuffer]
0x1800098f9  mov     rbx, [rbp+2A0h+var_70]
0x180009900  cmovnz  rbx, rax
0x180009904  test    r12b, 2
0x180009908  jnz     loc_180009A46
0x18000990e  test    r12b, 4
0x180009912  jnz     loc_180009D5B
0x180009918  test    rax, rax
0x18000991b  jz      short loc_18000992A
0x18000991d  cmp     rax, [rbp+2A0h+Buffer.StaticBuffer]
0x180009924  jnz     loc_180009D86
0x18000992a  mov     rcx, [rbp+2A0h+Buffer.StaticBuffer]
0x180009931  mov     ebx, dword ptr [rsp+3A0h+UnicodeString+4]
0x180009935  mov     rsi, [rsp+3A0h+var_328]
0x18000993a  test    rcx, rcx
0x18000993d  jnz     loc_180009B96
0x180009943  mov     rdi, [rsp+3A0h+arg_8]
0x18000994b  jmp     loc_1800095A9
0x180009950  bt      r11d, 17h
0x180009955  jnb     loc_18000960A
0x18000995b  mov     ebx, 80070032h
0x180009960  jmp     loc_180009599
0x180009965  mov     eax, 5Ch ; '\'
0x18000996a  cmp     ax, [rcx-2]
0x18000996e  jnz     loc_18000974F
0x180009974  mov     [rcx-2], r15w
0x180009979  jmp     loc_18000974F
0x18000997e  cmp     [rdx], bx
0x180009981  jz      loc_1800097BC
0x180009987  xorps   xmm0, xmm0
0x18000998a  lea     rcx, [rsp+3A0h+DestinationString.Buffer]; DestinationString
0x18000998f  movups  xmmword ptr [rsp+3A0h+DestinationString.Buffer], xmm0
0x180009994  call    cs:__imp_RtlInitUnicodeString
0x18000999a  movzx   r8d, word ptr [rsp+3A0h+DestinationString.Buffer]
0x1800099a0  mov     esi, 0FFFEh
0x1800099a5  mov     edx, r15d
0x1800099a8  mov     word ptr [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer], dx
0x1800099af  lea     rax, [r8+2]
0x1800099b3  cmp     rax, rsi
0x1800099b6  ja      loc_180009BE3
0x1800099bc  cmp     rax, [rbp+2A0h+Buffer.Size]
0x1800099c3  jbe     short loc_1800099EC
0x1800099c5  mov     r8, rax; RequiredSize
0x1800099c8  lea     rdx, [rbp+2A0h+Buffer]; Buffer
0x1800099cf  xor     ecx, ecx; Flags
0x1800099d1  call    cs:__imp_RtlpEnsureBufferSize
0x1800099d7  test    eax, eax
0x1800099d9  js      loc_180009BEA
0x1800099df  movzx   edx, word ptr [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer]
0x1800099e6  movzx   r8d, word ptr [rsp+3A0h+DestinationString.Buffer]
0x1800099ec  mov     rcx, [rbp+2A0h+Buffer.Buffer]
0x1800099f3  movzx   eax, dx
0x1800099f6  mov     rdx, [rsp+3A0h+Src]; Src
0x1800099fb  shr     rax, 1
0x1800099fe  mov     [rbp+2A0h+var_70], rcx
0x180009a05  movzx   r8d, r8w; Size
0x180009a09  lea     rcx, [rcx+rax*2]; void *
0x180009a0d  call    memmove_0
0x180009a12  movzx   eax, word ptr [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer]
0x180009a19  add     ax, word ptr [rsp+3A0h+DestinationString.Buffer]
0x180009a1e  movzx   edx, ax
0x180009a21  mov     word ptr [rbp+2A0h+UnicodeStringOrUnicodeStringBuffer], dx
  ... truncated ...
```
