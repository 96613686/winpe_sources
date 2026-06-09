# FveDataSetExternalDataCreateAndAppendEntry

- ea: `0x180116e80`
- end: `0x18011731e`
- name: `FveDataSetExternalDataCreateAndAppendEntry`
- size: `1182`
- prototype: `__int64 __usercall@<rax>(char@<cl>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180073004`

## callees

- `0x18001b260`
- `0x180046a90`
- `0x1800570ac`
- `0x180116e80`
- `0x1801180d8`
- `0x18011825c`
- `0x1801186b4`
- `0x180118c04`
- `0x180118da0`
- `0x180118dcc`
- `0x180118df8`
- `0x18011f010`

## string_xrefs

- `0x180116ebb`: `FveDataSetExternalDataCreateAndAppendEntry`
- `0x180116f50`: `FveDataSetExternalDataCreateAndAppendEntry`
- `0x180116f86`: `FveDataSetExternalDataCreateAndAppendEntry`
- `0x180117020`: `FveDataSetExternalDataCreateAndAppendEntry`
- `0x180117045`: `FveDataSetExternalDataCreateAndAppendEntry`
- `0x18011707c`: `FveDataSetExternalDataCreateAndAppendEntry`
- `0x1801170c6`: `FveDataSetExternalDataCreateAndAppendEntry`
- `0x1801171cf`: `FveDataSetExternalDataCreateAndAppendEntry`
- `0x180117222`: `FveDataSetExternalDataCreateAndAppendEntry`
- `0x1801172d5`: `FveDataSetExternalDataCreateAndAppendEntry`
- `0x1801171c8`: `FveDatumGenericDataRecordProtectedCreate failed: 0x%08X`
- `0x1801170cd`: `EntryId collision after %d attempts`
- `0x18011705e`: `FveDataSetExternalDataCreateAndAppendEntry: EntrySpaceAvailableBytes=%lu, RawDataSizeBytes=%u, EntryTypeId=%!GUID!, Status=0x%08X`
- `0x180117279`: `FveDatumGenericDataRecordCreate failed: 0x%08X`

## pseudocode

```c
__int64 __fastcall FveDataSetExternalDataCreateAndAppendEntry(
        __int64 a1,
        int a2,
        __int64 a3,
        __int16 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  char v8; // r14
  __int64 v11; // rdi
  int EntryInfoStructureSize; // ebx
  char *Format; // rax
  int v14; // edx
  __int64 v16; // rdi
  int IsUniqueEntryId; // eax
  __int64 *v18; // r9
  int v19; // r14d
  bool v20; // zf
  int v21; // eax
  int appended; // eax
  int v23; // eax
  int v24; // eax
  char v25; // [rsp+28h] [rbp-79h]
  __int16 v27; // [rsp+54h] [rbp-4Dh] BYREF
  __int64 v28; // [rsp+58h] [rbp-49h] BYREF
  int v29; // [rsp+60h] [rbp-41h]
  __int64 v30; // [rsp+68h] [rbp-39h] BYREF
  __int64 v31; // [rsp+70h] [rbp-31h]
  __int64 v32; // [rsp+78h] [rbp-29h]
  __int128 v33; // [rsp+80h] [rbp-21h] BYREF
  __int128 v34; // [rsp+90h] [rbp-11h]

  v31 = a6;
  v8 = a2;
  v29 = a2;
  v32 = a7;
  v27 = 0;
  v34 = 0;
  v30 = 0;
  v11 = 0;
  v33 = 0;
  v28 = 0;
  FveLibTraceEntryHelper(
    "minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
    887,
    "FveDataSetExternalDataCreateAndAppendEntry");
  if ( a1 && a3 && a5 && a4 )
  {
    EntryInfoStructureSize = FveExternalDataGetEntryInfoStructureSize(*(unsigned __int16 *)(a3 + 2), &v27);
    if ( EntryInfoStructureSize < 0 )
    {
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
        904,
        (int)"FveDataSetExternalDataCreateAndAppendEntry",
        0,
        "Invalid structure version: %u",
        *(_WORD *)(a3 + 2));
      goto LABEL_16;
    }
    if ( *(_WORD *)a3 != v27 )
    {
      EntryInfoStructureSize = -1073741811;
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
        911,
        (int)"FveDataSetExternalDataCreateAndAppendEntry",
        0,
        "Structure size mismatch: Provided=%u, Expected=%u",
        *(_WORD *)a3);
      goto LABEL_16;
    }
    v34 = *(_OWORD *)(a3 + 4);
    if ( (v8 & 1) != 0 )
    {
      while ( (unsigned __int16)v11 < 3u )
      {
        EntryInfoStructureSize = FveLibGenGuid(&v33);
        if ( EntryInfoStructureSize < 0 )
        {
          Format = "Failed to generate GUID";
          v14 = 924;
          goto LABEL_15;
        }
        EntryInfoStructureSize = FveDataSetExternalDataIsUniqueEntryId(a1, &v33);
        if ( EntryInfoStructureSize >= 0 )
          goto LABEL_19;
        LOWORD(v11) = v11 + 1;
      }
      if ( EntryInfoStructureSize < 0 )
      {
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
          937,
          (int)"FveDataSetExternalDataCreateAndAppendEntry",
          0,
          "EntryId collision after %d attempts",
          3);
        goto LABEL_16;
      }
LABEL_19:
      v16 = a3 + 20;
      *(_OWORD *)(a3 + 20) = v33;
    }
    else
    {
      v16 = a3 + 20;
      IsUniqueEntryId = FveDataSetExternalDataIsUniqueEntryId(a1, a3 + 20);
      EntryInfoStructureSize = IsUniqueEntryId;
      if ( IsUniqueEntryId < 0 || IsUniqueEntryId == 0x40000000 )
        goto LABEL_16;
    }
    v18 = 0;
    v19 = v8 & 2;
    if ( !v19 )
    {
      v18 = &v30;
      v30 = *(_QWORD *)(a3 + 68);
    }
    v20 = (v29 & 4) == 0;
    *(_WORD *)(a3 + 66) = 0;
    if ( !v20 )
    {
      if ( !v31 )
      {
        EntryInfoStructureSize = -1071579136;
        Format = "Missing Vmk for VMK-protected entry";
        v14 = 972;
LABEL_15:
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
          v14,
          (int)"FveDataSetExternalDataCreateAndAppendEntry",
          0,
          Format,
          v25);
        goto LABEL_16;
      }
      if ( !v32 )
      {
        EntryInfoStructureSize = -1073741811;
        Format = "Missing Nonce for VMK-protected entry";
        v14 = 977;
        goto LABEL_15;
      }
      v21 = FveDatumGenericDataRecordProtectedCreate(
              v32,
              v31,
              v16,
              (int)a3 + 4,
              a3 + 36,
              (__int64)v18,
              a4,
              a5,
              (__int64)&v28);
      EntryInfoStructureSize = v21;
      if ( v21 < 0 )
      {
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
          992,
          (int)"FveDataSetExternalDataCreateAndAppendEntry",
          0,
          "FveDatumGenericDataRecordProtectedCreate failed: 0x%08X",
          v21);
LABEL_31:
        v11 = v28;
        goto LABEL_41;
      }
      v11 = v28;
      appended = FveDatasetAppendDatum(a1, v28, 45);
      EntryInfoStructureSize = appended;
      if ( appended < 0 )
      {
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
          1001,
          (int)"FveDataSetExternalDataCreateAndAppendEntry",
          0,
          "FveDatasetAppendDatum ExternalDataEncrypted failed: 0x%08X",
          appended);
        goto LABEL_41;
      }
LABEL_38:
      if ( v19 )
        *(_QWORD *)(a3 + 68) = *(_QWORD *)(v11 + 76);
      goto LABEL_41;
    }
    v23 = FveDatumGenericDataRecordCreate(v16, a3 + 4, a3 + 36, v18, a4, a5, &v28);
    EntryInfoStructureSize = v23;
    if ( v23 < 0 )
    {
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
        1014,
        (int)"FveDataSetExternalDataCreateAndAppendEntry",
        0,
        "FveDatumGenericDataRecordCreate failed: 0x%08X",
        v23);
      goto LABEL_31;
    }
    v11 = v28;
    v24 = FveDatasetAppendDatum(a1, v28, 27);
    EntryInfoStructureSize = v24;
    if ( v24 >= 0 )
      goto LABEL_38;
    FveLibTraceHelper(
      (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
      1023,
      (int)"FveDataSetExternalDataCreateAndAppendEntry",
      0,
      "FveDatasetAppendDatum ExternalDataPlain failed: 0x%08X",
      v24);
  }
  else
  {
    EntryInfoStructureSize = -1073741811;
    FveLibTraceHelper(
      (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
      895,
      (int)"FveDataSetExternalDataCreateAndAppendEntry",
      0,
      "Invalid parameter: DataSet=%p, NewEntryInfo=%p, RawData=%p, RawDataSizeBytes=%u",
      a1);
  }
LABEL_41:
  if ( v11 )
    FveDatumFree(v11);
LABEL_16:
  FveLibTraceHelper(
    (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
    1039,
    (int)"FveDataSetExternalDataCreateAndAppendEntry",
    0,
    "FveDataSetExternalDataCreateAndAppendEntry: EntrySpaceAvailableBytes=%lu, RawDataSizeBytes=%u, EntryTypeId=%!GUID!, Status=0x%08X",
    0);
  FveLibTraceExitHelper(
    "minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
    1041,
    "FveDataSetExternalDataCreateAndAppendEntry");
  return (unsigned int)EntryInfoStructureSize;
}

```

## disassembly

```asm
0x180116e80  mov     [rsp-8+arg_8], rbx
0x180116e85  push    rbp
0x180116e86  push    rsi
0x180116e87  push    rdi
0x180116e88  push    r12
0x180116e8a  push    r13
0x180116e8c  push    r14
0x180116e8e  push    r15
0x180116e90  lea     rbp, [rsp-0Fh]
0x180116e95  sub     rsp, 0B0h
0x180116e9c  mov     rax, cs:__security_cookie
0x180116ea3  xor     rax, rsp
0x180116ea6  mov     [rbp+3Fh+var_40], rax
0x180116eaa  mov     rax, [rbp+3Fh+arg_28]
0x180116eae  xor     ebx, ebx
0x180116eb0  mov     r13, [rbp+3Fh+arg_20]
0x180116eb4  mov     rsi, r8
0x180116eb7  mov     [rbp+3Fh+var_70], rax
0x180116ebb  lea     r8, aFvedatasetexte_3; "FveDataSetExternalDataCreateAndAppendEn"...
0x180116ec2  mov     rax, [rbp+3Fh+arg_30]
0x180116ec6  mov     r14d, edx
0x180116ec9  movzx   r12d, r9w
0x180116ecd  mov     r15, rcx
0x180116ed0  mov     [rbp+3Fh+var_80], edx
0x180116ed3  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180116eda  xorps   xmm0, xmm0
0x180116edd  mov     [rbp+3Fh+var_68], rax
0x180116ee1  xorps   xmm1, xmm1
0x180116ee4  mov     [rbp+3Fh+var_90], r12w
0x180116ee9  mov     edx, 377h
0x180116eee  mov     [rbp+3Fh+var_8C], bx
0x180116ef2  movups  [rbp+3Fh+var_50], xmm0
0x180116ef6  mov     [rbp+3Fh+var_78], rbx
0x180116efa  mov     edi, ebx
0x180116efc  movups  [rbp+3Fh+var_60], xmm1
0x180116f00  mov     [rbp+3Fh+var_88], rbx
0x180116f04  call    FveLibTraceEntryHelper
0x180116f09  test    r15, r15
0x180116f0c  jz      loc_1801172C4
0x180116f12  test    rsi, rsi
0x180116f15  jz      loc_1801172C4
0x180116f1b  test    r13, r13
0x180116f1e  jz      loc_1801172C4
0x180116f24  test    r12w, r12w
0x180116f28  jz      loc_1801172C4
0x180116f2e  movzx   ecx, word ptr [rsi+2]
0x180116f32  lea     rdx, [rbp+3Fh+var_8C]
0x180116f36  call    FveExternalDataGetEntryInfoStructureSize
0x180116f3b  mov     ebx, eax
0x180116f3d  test    eax, eax
0x180116f3f  jns     short loc_180116F79
0x180116f41  movzx   ecx, word ptr [rsi+2]
0x180116f45  lea     rax, aInvalidStructu; "Invalid structure version: %u"
0x180116f4c  mov     dword ptr [rsp+0E0h+var_B8], ecx; char
0x180116f50  lea     r8, aFvedatasetexte_3; "FveDataSetExternalDataCreateAndAppendEn"...
0x180116f57  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180116f5e  mov     [rsp+0E0h+Format], rax; Format
0x180116f63  xor     r9d, r9d; int
0x180116f66  mov     edx, 388h; int
0x180116f6b  call    FveLibTraceHelper
0x180116f70  movzx   r13d, r12w
0x180116f74  jmp     loc_180117038
0x180116f79  movzx   ecx, word ptr [rsi]
0x180116f7c  cmp     cx, [rbp+3Fh+var_8C]
0x180116f80  jz      short loc_180116FBC
0x180116f82  movzx   eax, [rbp+3Fh+var_8C]
0x180116f86  lea     r8, aFvedatasetexte_3; "FveDataSetExternalDataCreateAndAppendEn"...
0x180116f8d  mov     dword ptr [rsp+0E0h+var_B0], eax
0x180116f91  xor     r9d, r9d; int
0x180116f94  mov     dword ptr [rsp+0E0h+var_B8], ecx; char
0x180116f98  lea     rax, aStructureSizeM; "Structure size mismatch: Provided=%u, E"...
0x180116f9f  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180116fa6  mov     [rsp+0E0h+Format], rax; Format
0x180116fab  mov     edx, 38Fh; int
0x180116fb0  mov     ebx, 0C000000Dh
0x180116fb5  call    FveLibTraceHelper
0x180116fba  jmp     short loc_180116F70
0x180116fbc  lea     r12, [rsi+4]
0x180116fc0  movups  xmm0, xmmword ptr [r12]
0x180116fc5  movdqu  [rbp+3Fh+var_50], xmm0
0x180116fca  test    r14b, 1
0x180116fce  jz      loc_180117100
0x180116fd4  mov     eax, 3
0x180116fd9  cmp     di, ax
0x180116fdc  jnb     loc_1801170BE
0x180116fe2  lea     rcx, [rbp+3Fh+var_60]
0x180116fe6  call    FveLibGenGuid
0x180116feb  mov     ebx, eax
0x180116fed  test    eax, eax
0x180116fef  js      short loc_18011700C
0x180116ff1  lea     rdx, [rbp+3Fh+var_60]
0x180116ff5  mov     rcx, r15
0x180116ff8  call    FveDataSetExternalDataIsUniqueEntryId
0x180116ffd  mov     ebx, eax
0x180116fff  test    eax, eax
0x180117001  jns     loc_1801170F2
0x180117007  inc     di
0x18011700a  jmp     short loc_180116FD4
0x18011700c  lea     rax, aFailedToGenera; "Failed to generate GUID"
0x180117013  mov     edx, 39Ch; int
0x180117018  xor     r9d, r9d; int
0x18011701b  mov     [rsp+0E0h+Format], rax; Format
0x180117020  lea     r8, aFvedatasetexte_3; "FveDataSetExternalDataCreateAndAppendEn"...
0x180117027  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18011702e  call    FveLibTraceHelper
0x180117033  movzx   r13d, [rbp+3Fh+var_90]
0x180117038  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x18011703c  lea     rdx, [rbp+3Fh+var_50]
0x180117040  mov     [rsp+0E0h+var_A8], rdx
0x180117045  lea     r8, aFvedatasetexte_3; "FveDataSetExternalDataCreateAndAppendEn"...
0x18011704c  movzx   eax, r13w
0x180117050  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180117057  mov     dword ptr [rsp+0E0h+var_B0], eax
0x18011705b  xor     r9d, r9d; int
0x18011705e  lea     rax, aFvedatasetexte; "FveDataSetExternalDataCreateAndAppendEn"...
0x180117065  mov     dword ptr [rsp+0E0h+var_B8], 0; char
0x18011706d  mov     edx, 40Fh; int
0x180117072  mov     [rsp+0E0h+Format], rax; Format
0x180117077  call    FveLibTraceHelper
0x18011707c  lea     r8, aFvedatasetexte_3; "FveDataSetExternalDataCreateAndAppendEn"...
0x180117083  mov     edx, 411h
0x180117088  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18011708f  call    FveLibTraceExitHelper
0x180117094  mov     eax, ebx
0x180117096  mov     rcx, [rbp+3Fh+var_40]
0x18011709a  xor     rcx, rsp; StackCookie
0x18011709d  call    __security_check_cookie
0x1801170a2  mov     rbx, [rsp+0E0h+arg_8]
0x1801170aa  add     rsp, 0B0h
0x1801170b1  pop     r15
0x1801170b3  pop     r14
0x1801170b5  pop     r13
0x1801170b7  pop     r12
0x1801170b9  pop     rdi
0x1801170ba  pop     rsi
0x1801170bb  pop     rbp
0x1801170bc  retn
0x1801170be  test    ebx, ebx
0x1801170c0  jns     short loc_1801170F2
0x1801170c2  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x1801170c6  lea     r8, aFvedatasetexte_3; "FveDataSetExternalDataCreateAndAppendEn"...
0x1801170cd  lea     rax, aEntryidCollisi; "EntryId collision after %d attempts"
0x1801170d4  xor     r9d, r9d; int
0x1801170d7  mov     edx, 3A9h; int
0x1801170dc  mov     [rsp+0E0h+Format], rax; Format
0x1801170e1  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801170e8  call    FveLibTraceHelper
0x1801170ed  jmp     loc_180117033
0x1801170f2  movups  xmm0, [rbp+3Fh+var_60]
0x1801170f6  lea     rdi, [rsi+14h]
0x1801170fa  movdqu  xmmword ptr [rdi], xmm0
0x1801170fe  jmp     short loc_180117124
0x180117100  lea     rdi, [rsi+14h]
0x180117104  mov     rcx, r15
0x180117107  mov     rdx, rdi
0x18011710a  call    FveDataSetExternalDataIsUniqueEntryId
0x18011710f  mov     ebx, eax
0x180117111  test    eax, eax
0x180117113  js      loc_180117033
0x180117119  cmp     eax, 40000000h
0x18011711e  jz      loc_180117033
0x180117124  xor     r9d, r9d
0x180117127  and     r14d, 2
0x18011712b  jnz     short loc_180117139
0x18011712d  mov     rax, [rsi+44h]
0x180117131  lea     r9, [rbp+3Fh+var_78]
0x180117135  mov     [rbp+3Fh+var_78], rax
0x180117139  xor     eax, eax
0x18011713b  test    byte ptr [rbp+3Fh+var_80], 4
0x18011713f  mov     [rsi+42h], ax
0x180117143  jz      loc_180117242
0x180117149  mov     rdx, [rbp+3Fh+var_70]
0x18011714d  test    rdx, rdx
0x180117150  jnz     short loc_180117168
0x180117152  mov     ebx, 0C0210000h
0x180117157  lea     rax, aMissingVmkForV; "Missing Vmk for VMK-protected entry"
0x18011715e  mov     edx, 3CCh
0x180117163  jmp     loc_180117018
0x180117168  mov     rcx, [rbp+3Fh+var_68]
0x18011716c  test    rcx, rcx
0x18011716f  jnz     short loc_180117187
0x180117171  mov     ebx, 0C000000Dh
0x180117176  lea     rax, aMissingNonceFo; "Missing Nonce for VMK-protected entry"
0x18011717d  mov     edx, 3D1h
0x180117182  jmp     loc_180117018
0x180117187  lea     r8, [rbp+3Fh+var_88]
0x18011718b  mov     [rsp+0E0h+var_A0], r8
0x180117190  lea     rax, [rsi+24h]
0x180117194  mov     [rsp+0E0h+var_A8], r13
0x180117199  mov     r8, rdi
0x18011719c  movzx   r13d, [rbp+3Fh+var_90]
0x1801171a1  mov     word ptr [rsp+0E0h+var_B0], r13w
0x1801171a7  mov     qword ptr [rsp+0E0h+var_B8], r9
0x1801171ac  mov     r9, r12
0x1801171af  mov     [rsp+0E0h+Format], rax
0x1801171b4  call    FveDatumGenericDataRecordProtectedCreate
0x1801171b9  mov     ebx, eax
0x1801171bb  test    eax, eax
0x1801171bd  jns     short loc_1801171F3
0x1801171bf  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x1801171c3  mov     edx, 3E0h; int
0x1801171c8  lea     rax, aFvedatumgeneri_0; "FveDatumGenericDataRecordProtectedCreat"...
0x1801171cf  lea     r8, aFvedatasetexte_3; "FveDataSetExternalDataCreateAndAppendEn"...
0x1801171d6  mov     [rsp+0E0h+Format], rax; Format
0x1801171db  xor     r9d, r9d; int
0x1801171de  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801171e5  call    FveLibTraceHelper
0x1801171ea  mov     rdi, [rbp+3Fh+var_88]
0x1801171ee  jmp     loc_180117308
0x1801171f3  mov     rdi, [rbp+3Fh+var_88]
0x1801171f7  mov     r8d, 2Dh ; '-'
0x1801171fd  mov     rdx, rdi
0x180117200  mov     rcx, r15
0x180117203  call    FveDatasetAppendDatum
0x180117208  mov     ebx, eax
0x18011720a  test    eax, eax
0x18011720c  jns     loc_1801172B5
0x180117212  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x180117216  mov     edx, 3E9h; int
0x18011721b  lea     rax, aFvedatasetappe_2; "FveDatasetAppendDatum ExternalDataEncry"...
0x180117222  lea     r8, aFvedatasetexte_3; "FveDataSetExternalDataCreateAndAppendEn"...
0x180117229  mov     [rsp+0E0h+Format], rax; Format
0x18011722e  xor     r9d, r9d; int
0x180117231  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180117238  call    FveLibTraceHelper
0x18011723d  jmp     loc_180117308
0x180117242  lea     rax, [rbp+3Fh+var_88]
0x180117246  mov     rdx, r12
0x180117249  mov     [rsp+0E0h+var_B0], rax
0x18011724e  lea     r8, [rsi+24h]
0x180117252  mov     qword ptr [rsp+0E0h+var_B8], r13
0x180117257  mov     rcx, rdi
0x18011725a  movzx   r13d, [rbp+3Fh+var_90]
0x18011725f  mov     word ptr [rsp+0E0h+Format], r13w
0x180117265  call    FveDatumGenericDataRecordCreate
0x18011726a  mov     ebx, eax
0x18011726c  test    eax, eax
0x18011726e  jns     short loc_180117285
0x180117270  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180117274  mov     edx, 3F6h
0x180117279  lea     rax, aFvedatumgeneri; "FveDatumGenericDataRecordCreate failed:"...
0x180117280  jmp     loc_1801171CF
0x180117285  mov     rdi, [rbp+3Fh+var_88]
0x180117289  mov     r8d, 1Bh
0x18011728f  mov     rdx, rdi
0x180117292  mov     rcx, r15
0x180117295  call    FveDatasetAppendDatum
0x18011729a  mov     ebx, eax
0x18011729c  test    eax, eax
0x18011729e  jns     short loc_1801172B5
0x1801172a0  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1801172a4  mov     edx, 3FFh
0x1801172a9  lea     rax, aFvedatasetappe_1; "FveDatasetAppendDatum ExternalDataPlain"...
0x1801172b0  jmp     loc_180117222
0x1801172b5  test    r14d, r14d
0x1801172b8  jz      short loc_180117308
0x1801172ba  mov     rax, [rdi+4Ch]
0x1801172be  mov     [rsi+44h], rax
0x1801172c2  jmp     short loc_180117308
0x1801172c4  mov     dword ptr [rsp+0E0h+var_A0], r12d
0x1801172c9  lea     rax, aInvalidParamet; "Invalid parameter: DataSet=%p, NewEntry"...
0x1801172d0  mov     [rsp+0E0h+var_A8], r13
0x1801172d5  lea     r8, aFvedatasetexte_3; "FveDataSetExternalDataCreateAndAppendEn"...
0x1801172dc  mov     [rsp+0E0h+var_B0], rsi
0x1801172e1  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801172e8  mov     qword ptr [rsp+0E0h+var_B8], r15; char
0x1801172ed  xor     r9d, r9d; int
0x1801172f0  mov     edx, 37Fh; int
0x1801172f5  mov     [rsp+0E0h+Format], rax; Format
0x1801172fa  mov     ebx, 0C000000Dh
0x1801172ff  call    FveLibTraceHelper
0x180117304  movzx   r13d, r12w
0x180117308  test    rdi, rdi
0x18011730b  jz      loc_180117038
0x180117311  mov     rcx, rdi
0x180117314  call    FveDatumFree
0x180117319  jmp     loc_180117038
```
