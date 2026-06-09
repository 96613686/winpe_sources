# FveDataSetExternalDataDeleteEntries

- ea: `0x180117324`
- end: `0x180117618`
- name: `FveDataSetExternalDataDeleteEntries`
- size: `756`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800732bc`

## callees

- `0x18001b490`
- `0x18001de20`
- `0x18001eaf4`
- `0x18004fa04`
- `0x18005007c`
- `0x180117324`
- `0x1801185b8`
- `0x180118da0`
- `0x180118dcc`
- `0x180118df8`

## string_xrefs

- `0x180117352`: `FveDataSetExternalDataDeleteEntries`
- `0x180117429`: `FveDataSetExternalDataDeleteEntries`
- `0x1801174da`: `FveDataSetExternalDataDeleteEntries`
- `0x180117537`: `FveDataSetExternalDataDeleteEntries`
- `0x180117589`: `FveDataSetExternalDataDeleteEntries`
- `0x1801175b2`: `FveDataSetExternalDataDeleteEntries`
- `0x1801175e5`: `FveDataSetExternalDataDeleteEntries`
- `0x18011750c`: `Error during entry search/delete: 0x%08X`
- `0x180117446`: `Deleted entry at offset %lu, size %lu bytes`
- `0x180117561`: `FveDatasetCompress failed: 0x%08X`
- `0x1801175ca`: `FveDataSetExternalDataDeleteEntries: DeletedDataSizeBytes=%lu, EntryCountDeleted=%u, Status=0x%08X`

## pseudocode

```c
__int64 __fastcall FveDataSetExternalDataDeleteEntries(__int64 a1, __int64 a2, unsigned __int16 *a3)
{
  int v3; // ebx
  unsigned int v7; // r15d
  unsigned __int16 v8; // di
  unsigned int v9; // r12d
  int Next; // eax
  int DatumPointer; // eax
  __int64 v12; // r13
  int v13; // eax
  int v14; // edi
  int v15; // eax
  int v16; // eax
  char v18; // [rsp+28h] [rbp-28h]
  _WORD v19[2]; // [rsp+40h] [rbp-10h] BYREF
  char v20[4]; // [rsp+44h] [rbp-Ch] BYREF
  __int64 v21; // [rsp+48h] [rbp-8h] BYREF
  char v23; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  *(_DWORD *)v20 = 0;
  v19[0] = 0;
  v23 = 0;
  v21 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  FveLibTraceEntryHelper(
    "minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
    1524,
    "FveDataSetExternalDataDeleteEntries");
  if ( a2 && a1 )
  {
    if ( a3 )
      *a3 = 0;
    while ( 1 )
    {
      Next = FveDatasetGetNext(a1, 0xFFFF, 25, v7, (__int64)v20);
      if ( Next < 0 )
        break;
      v7 = *(_DWORD *)v20;
      DatumPointer = FveDatasetGetDatumPointer(a1, *(unsigned int *)v20, &v21);
      v3 = DatumPointer;
      if ( DatumPointer < 0 )
      {
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
          1547,
          (int)"FveDataSetExternalDataDeleteEntries",
          0,
          "FveDatasetGetDatumPointer failed: 0x%08X",
          DatumPointer);
        goto LABEL_29;
      }
      v12 = v21;
      v13 = FveExternalDataEntryMatches(a2, v21, &v23);
      v3 = v13;
      if ( v13 < 0 )
      {
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
          1556,
          (int)"FveDataSetExternalDataDeleteEntries",
          0,
          "EntryMatchesWithDecryption failed: 0x%08X",
          v13);
        goto LABEL_29;
      }
      v3 = 0;
      if ( v23 )
      {
        v3 = RtlUShortAdd(v8, 1, v19);
        if ( v3 < 0 )
          goto LABEL_29;
        v14 = *(unsigned __int16 *)(v12 + 10);
        v15 = FveDatasetEraseDatum(a1, v7);
        v3 = v15;
        if ( v15 < 0 )
        {
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
            1572,
            (int)"FveDataSetExternalDataDeleteEntries",
            0,
            "FveDatasetEraseDatum failed: 0x%08X",
            v15);
          goto LABEL_29;
        }
        if ( v14 + v9 < v9 )
        {
          v3 = -1073741675;
          LOBYTE(v9) = -1;
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
            1578,
            (int)"FveDataSetExternalDataDeleteEntries",
            0,
            "RtlULongAdd failed: 0x%08X",
            149);
          goto LABEL_29;
        }
        v9 += v14;
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
          1581,
          (int)"FveDataSetExternalDataDeleteEntries",
          0,
          "Deleted entry at offset %lu, size %lu bytes",
          v7);
        v8 = v19[0];
        v3 = 0;
      }
    }
    if ( Next != -1073741275 )
      v3 = Next;
    if ( v3 >= 0 )
    {
      if ( v8 )
      {
        v16 = FveDatasetCompress(a1);
        v3 = v16;
        if ( v16 >= 0 )
        {
          if ( a3 )
            *a3 = v8;
        }
        else
        {
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
            1612,
            (int)"FveDataSetExternalDataDeleteEntries",
            0,
            "FveDatasetCompress failed: 0x%08X",
            v16);
        }
      }
      else
      {
        v3 = -1073741275;
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
          1603,
          (int)"FveDataSetExternalDataDeleteEntries",
          0,
          "No entries matched for deletion.",
          v18);
      }
    }
    else
    {
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
        1597,
        (int)"FveDataSetExternalDataDeleteEntries",
        0,
        "Error during entry search/delete: 0x%08X",
        v3);
    }
  }
  else
  {
    v3 = -1073741811;
    FveLibTraceHelper(
      (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
      1529,
      (int)"FveDataSetExternalDataDeleteEntries",
      0,
      "Invalid parameter: EntrySelect=%p, DataSet=%p",
      a2);
  }
LABEL_29:
  FveLibTraceHelper(
    (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
    1622,
    (int)"FveDataSetExternalDataDeleteEntries",
    0,
    "FveDataSetExternalDataDeleteEntries: DeletedDataSizeBytes=%lu, EntryCountDeleted=%u, Status=0x%08X",
    v9);
  FveLibTraceExitHelper(
    "minkernel\\ngscb\\cornerstone\\fvevollib\\datumgenericdatarecord.c",
    1624,
    "FveDataSetExternalDataDeleteEntries");
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180117324  mov     [rsp-38h+arg_0], rbx
0x180117329  mov     [rsp-38h+arg_8], rdx
0x18011732e  push    rbp
0x18011732f  push    rsi
0x180117330  push    rdi
0x180117331  push    r12
0x180117333  push    r13
0x180117335  push    r14
0x180117337  push    r15
0x180117339  mov     rbp, rsp
0x18011733c  sub     rsp, 50h
0x180117340  xor     ebx, ebx
0x180117342  mov     r14, r8
0x180117345  mov     r13, rdx
0x180117348  mov     dword ptr [rbp+var_C], ebx
0x18011734b  mov     rsi, rcx
0x18011734e  mov     [rbp+var_10], bx
0x180117352  lea     r8, aFvedatasetexte_2; "FveDataSetExternalDataDeleteEntries"
0x180117359  mov     [rbp+arg_18], bl
0x18011735c  mov     edx, 5F4h
0x180117361  mov     [rbp+var_8], rbx
0x180117365  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18011736c  mov     r15d, ebx
0x18011736f  mov     edi, ebx
0x180117371  mov     r12d, ebx
0x180117374  call    FveLibTraceEntryHelper
0x180117379  test    r13, r13
0x18011737c  jz      loc_180117578
0x180117382  test    rsi, rsi
0x180117385  jz      loc_180117578
0x18011738b  test    r14, r14
0x18011738e  jz      short loc_180117394
0x180117390  mov     [r14], bx
0x180117394  lea     rax, [rbp+var_C]
0x180117398  mov     edx, 0FFFFh
0x18011739d  mov     r8d, 19h
0x1801173a3  mov     [rsp+50h+Format], rax
0x1801173a8  mov     r9d, r15d
0x1801173ab  mov     rcx, rsi
0x1801173ae  call    FveDatasetGetNext
0x1801173b3  test    eax, eax
0x1801173b5  js      loc_1801174FA
0x1801173bb  mov     r15d, dword ptr [rbp+var_C]
0x1801173bf  lea     r8, [rbp+var_8]
0x1801173c3  mov     edx, r15d
0x1801173c6  mov     rcx, rsi
0x1801173c9  call    FveDatasetGetDatumPointer
0x1801173ce  mov     ebx, eax
0x1801173d0  test    eax, eax
0x1801173d2  js      loc_1801174CA
0x1801173d8  mov     r13, [rbp+var_8]
0x1801173dc  lea     r8, [rbp+arg_18]
0x1801173e0  mov     rcx, [rbp+arg_8]
0x1801173e4  mov     rdx, r13
0x1801173e7  call    FveExternalDataEntryMatches
0x1801173ec  mov     ebx, eax
0x1801173ee  test    eax, eax
0x1801173f0  js      loc_1801174B8
0x1801173f6  xor     ebx, ebx
0x1801173f8  cmp     [rbp+arg_18], bl
0x1801173fb  jz      short loc_180117394
0x1801173fd  lea     edx, [rbx+1]
0x180117400  movzx   ecx, di
0x180117403  lea     r8, [rbp+var_10]
0x180117407  call    RtlUShortAdd
0x18011740c  mov     ebx, eax
0x18011740e  test    eax, eax
0x180117410  js      loc_1801174AF
0x180117416  movzx   edi, word ptr [r13+0Ah]
0x18011741b  mov     edx, r15d
0x18011741e  mov     rcx, rsi
0x180117421  call    FveDatasetEraseDatum
0x180117426  xor     r9d, r9d; int
0x180117429  lea     r8, aFvedatasetexte_2; "FveDataSetExternalDataDeleteEntries"
0x180117430  mov     ebx, eax
0x180117432  test    eax, eax
0x180117434  js      short loc_18011748E
0x180117436  lea     ecx, [rdi+r12]
0x18011743a  cmp     ecx, r12d
0x18011743d  jb      short loc_180117473
0x18011743f  mov     r12d, ecx
0x180117442  mov     dword ptr [rsp+50h+var_20], edi
0x180117446  lea     rax, aDeletedEntryAt; "Deleted entry at offset %lu, size %lu b"...
0x18011744d  mov     dword ptr [rsp+50h+var_28], r15d; char
0x180117452  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180117459  mov     [rsp+50h+Format], rax; Format
0x18011745e  mov     edx, 62Dh; int
0x180117463  call    FveLibTraceHelper
0x180117468  movzx   edi, [rbp+var_10]
0x18011746c  xor     ebx, ebx
0x18011746e  jmp     loc_180117394
0x180117473  mov     ebx, 0C0000095h
0x180117478  lea     rax, aRtlulongaddFai; "RtlULongAdd failed: 0x%08X"
0x18011747f  mov     dword ptr [rsp+50h+var_28], ebx
0x180117483  or      r12d, 0FFFFFFFFh
0x180117487  mov     edx, 62Ah
0x18011748c  jmp     short loc_18011749E
0x18011748e  mov     dword ptr [rsp+50h+var_28], eax; char
0x180117492  mov     edx, 624h; int
0x180117497  lea     rax, aFvedataseteras_1; "FveDatasetEraseDatum failed: 0x%08X"
0x18011749e  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801174a5  mov     [rsp+50h+Format], rax; Format
0x1801174aa  call    FveLibTraceHelper
0x1801174af  movzx   edi, [rbp+var_10]
0x1801174b3  jmp     loc_1801175AE
0x1801174b8  mov     dword ptr [rsp+50h+var_28], eax
0x1801174bc  mov     edx, 614h
0x1801174c1  lea     rax, aEntrymatcheswi; "EntryMatchesWithDecryption failed: 0x%0"...
0x1801174c8  jmp     short loc_1801174DA
0x1801174ca  mov     dword ptr [rsp+50h+var_28], eax; char
0x1801174ce  mov     edx, 60Bh; int
0x1801174d3  lea     rax, aFvedatasetgetd_1; "FveDatasetGetDatumPointer failed: 0x%08"...
0x1801174da  lea     r8, aFvedatasetexte_2; "FveDataSetExternalDataDeleteEntries"
0x1801174e1  mov     [rsp+50h+Format], rax; Format
0x1801174e6  xor     r9d, r9d; int
0x1801174e9  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801174f0  call    FveLibTraceHelper
0x1801174f5  jmp     loc_1801175AE
0x1801174fa  mov     ecx, 0C0000225h
0x1801174ff  cmp     eax, ecx
0x180117501  cmovnz  ebx, eax
0x180117504  test    ebx, ebx
0x180117506  jns     short loc_18011751A
0x180117508  mov     dword ptr [rsp+50h+var_28], ebx
0x18011750c  lea     rax, aErrorDuringEnt_0; "Error during entry search/delete: 0x%08"...
0x180117513  mov     edx, 63Dh
0x180117518  jmp     short loc_1801174DA
0x18011751a  test    di, di
0x18011751d  jnz     short loc_18011754A
0x18011751f  mov     ebx, ecx
0x180117521  lea     rax, aNoEntriesMatch; "No entries matched for deletion."
0x180117528  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18011752f  mov     [rsp+50h+Format], rax; Format
0x180117534  xor     r9d, r9d; int
0x180117537  lea     r8, aFvedatasetexte_2; "FveDataSetExternalDataDeleteEntries"
0x18011753e  mov     edx, 643h; int
0x180117543  call    FveLibTraceHelper
0x180117548  jmp     short loc_1801175AE
0x18011754a  mov     rcx, rsi
0x18011754d  call    FveDatasetCompress
0x180117552  mov     ebx, eax
0x180117554  test    eax, eax
0x180117556  jns     short loc_18011756D
0x180117558  mov     dword ptr [rsp+50h+var_28], eax
0x18011755c  mov     edx, 64Ch
0x180117561  lea     rax, aFvedatasetcomp; "FveDatasetCompress failed: 0x%08X"
0x180117568  jmp     loc_1801174DA
0x18011756d  test    r14, r14
0x180117570  jz      short loc_1801175AE
0x180117572  mov     [r14], di
0x180117576  jmp     short loc_1801175AE
0x180117578  mov     [rsp+50h+var_20], rsi
0x18011757d  lea     rax, aInvalidParamet_2; "Invalid parameter: EntrySelect=%p, Data"...
0x180117584  mov     qword ptr [rsp+50h+var_28], r13; char
0x180117589  lea     r8, aFvedatasetexte_2; "FveDataSetExternalDataDeleteEntries"
0x180117590  xor     r9d, r9d; int
0x180117593  mov     [rsp+50h+Format], rax; Format
0x180117598  mov     edx, 5F9h; int
0x18011759d  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801175a4  mov     ebx, 0C000000Dh
0x1801175a9  call    FveLibTraceHelper
0x1801175ae  mov     [rsp+50h+var_18], ebx
0x1801175b2  lea     r8, aFvedatasetexte_2; "FveDataSetExternalDataDeleteEntries"
0x1801175b9  movzx   eax, di
0x1801175bc  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801175c3  mov     dword ptr [rsp+50h+var_20], eax
0x1801175c7  xor     r9d, r9d; int
0x1801175ca  lea     rax, aFvedatasetexte_5; "FveDataSetExternalDataDeleteEntries: De"...
0x1801175d1  mov     dword ptr [rsp+50h+var_28], r12d; char
0x1801175d6  mov     edx, 656h; int
0x1801175db  mov     [rsp+50h+Format], rax; Format
0x1801175e0  call    FveLibTraceHelper
0x1801175e5  lea     r8, aFvedatasetexte_2; "FveDataSetExternalDataDeleteEntries"
0x1801175ec  mov     edx, 658h
0x1801175f1  lea     rcx, aMinkernelNgscb_23; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801175f8  call    FveLibTraceExitHelper
0x1801175fd  mov     eax, ebx
0x1801175ff  mov     rbx, [rsp+50h+arg_0]
0x180117607  add     rsp, 50h
0x18011760b  pop     r15
0x18011760d  pop     r14
0x18011760f  pop     r13
0x180117611  pop     r12
0x180117613  pop     rdi
0x180117614  pop     rsi
0x180117615  pop     rbp
0x180117616  retn
```
