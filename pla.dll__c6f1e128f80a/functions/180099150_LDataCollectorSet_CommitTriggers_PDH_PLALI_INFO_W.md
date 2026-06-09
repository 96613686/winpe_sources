# LDataCollectorSet::CommitTriggers(_PDH_PLALI_INFO_W *)

- ea: `0x180099150`
- end: `0x180099a87`
- name: `?CommitTriggers@LDataCollectorSet@@EEAAJPEAU_PDH_PLALI_INFO_W@@@Z`
- size: `2359`
- prototype: `__int64 __fastcall(LDataCollectorSet *__hidden this, struct _PDH_PLALI_INFO_W *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180024ea0`
- `0x18002b3a0`
- `0x180090e30`
- `0x180099150`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800997a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800998d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800999fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800997a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800998d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800999fc`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180099975`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180099975`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180099798`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800998c4`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180099798`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800998c4`

## string_xrefs

- `0x180099215`: `LDataCollectorSet::CommitTriggers`
- `0x1800992ed`: `LDataCollectorSet::CommitTriggers`
- `0x1800993ed`: `LDataCollectorSet::CommitTriggers`
- `0x1800996bb`: `LDataCollectorSet::CommitTriggers`

## pseudocode

```c
__int64 __fastcall LDataCollectorSet::CommitTriggers(LDataCollectorSet *this, struct _PDH_PLALI_INFO_W *a2)
{
  int v2; // eax
  int Schedules; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  LDataCollectorSet **v8; // r9
  LDataCollectorSet **v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  unsigned int v14; // ecx
  struct IScheduleCollectionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_Item)(IScheduleCollection *, VARIANT, ISchedule **); // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rax
  DWORD LastError; // eax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  DWORD v28; // eax
  int v29; // eax
  __int64 v30; // rax
  __int64 dwHighDateTime; // rcx
  __int64 v32; // rcx
  DWORD v34; // eax
  int v35; // eax
  __int64 v36; // rax
  __int64 v37; // [rsp+48h] [rbp-B8h]
  __int64 v38; // [rsp+50h] [rbp-B0h]
  int v39; // [rsp+70h] [rbp-90h] BYREF
  LDataCollectorSet *v40; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v41; // [rsp+80h] [rbp-80h] BYREF
  int v42; // [rsp+84h] [rbp-7Ch] BYREF
  int v43; // [rsp+88h] [rbp-78h] BYREF
  struct IScheduleCollection *v44; // [rsp+90h] [rbp-70h] BYREF
  __int64 v45; // [rsp+98h] [rbp-68h] BYREF
  struct _FILETIME FileTime; // [rsp+A0h] [rbp-60h] BYREF
  struct tagVARIANT v47; // [rsp+A8h] [rbp-58h] BYREF
  struct tagVARIANT vtime; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v49; // [rsp+E0h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+F0h] [rbp-10h]
  struct _SYSTEMTIME SystemTime; // [rsp+100h] [rbp+0h] BYREF
  struct _SYSTEMTIME v52; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v53[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v54[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v55[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v56[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v57[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v58[64]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int16 v59[64]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 v60[64]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v61[64]; // [rsp+520h] [rbp+420h] BYREF
  unsigned __int16 v62[64]; // [rsp+5A0h] [rbp+4A0h] BYREF

  v40 = this;
  v42 = 0;
  v2 = *((_DWORD *)this + 14);
  v41 = 0;
  FileTime = 0;
  memset(&vtime, 0, sizeof(vtime));
  v43 = 0;
  SystemTime = 0;
  v45 = 0;
  v52 = 0;
  v44 = 0;
  memset(&v47, 0, sizeof(v47));
  v39 = v2;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_METHOD,
      3,
      "LDataCollectorSet::CommitTriggers",
      34,
      &v40,
      8,
      &v39,
      4,
      v37,
      v38);
  }
  PlaiVariantInit(&vtime);
  PlaiVariantInit(&v47);
  Schedules = DataCollectorSet::get_Schedules(this, &v44);
  v6 = Schedules;
  if ( Schedules >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(struct IScheduleCollection *, int *))v44->lpVtbl->get_Count)(v44, &v42);
    v6 = v10;
    if ( v10 < 0 )
    {
      LODWORD(v40) = 0;
      v39 = v10;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_82;
      }
      PlaiWhoAmI(v54, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v54[v11] );
      goto LABEL_19;
    }
    *(_DWORD *)a2 |= 0xC80u;
    *((_QWORD *)a2 + 13) = 65537;
    *((_QWORD *)a2 + 15) = 131073;
    *((_DWORD *)a2 + 39) = 0;
    v12 = (*(__int64 (__fastcall **)(LDataCollectorSet *, unsigned int *))(*(_QWORD *)this + 64LL))(this, &v41);
    v6 = v12;
    if ( v12 < 0 )
    {
      LODWORD(v40) = 0;
      v39 = v12;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_82;
      }
      PlaiWhoAmI(v55, 0x4000000000000800uLL);
      v13 = -1;
      do
        ++v13;
      while ( v55[v13] );
      goto LABEL_19;
    }
    v14 = v41;
    if ( v41 )
    {
      *((_DWORD *)a2 + 30) = 131074;
      *((_DWORD *)a2 + 31) = 3;
      if ( v14 > 0x1869F )
      {
        *((_DWORD *)a2 + 33) = 4;
        *((_DWORD *)a2 + 32) = v14 / 0x15180;
      }
      else
      {
        *((_DWORD *)a2 + 33) = 1;
        *((_DWORD *)a2 + 32) = v14;
      }
    }
    if ( v42 <= 0 )
      goto LABEL_82;
    v47.vt = 3;
    v47.lVal = 0;
    lpVtbl = v44->lpVtbl;
    pRecInfo = v47.pRecInfo;
    get_Item = lpVtbl->get_Item;
    v49 = *(_OWORD *)&v47.vt;
    v17 = ((__int64 (__fastcall *)(struct IScheduleCollection *, __int128 *, __int64 *))get_Item)(v44, &v49, &v45);
    v6 = v17;
    if ( v17 < 0 )
    {
      LODWORD(v40) = 0;
      v39 = v17;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_82;
      }
      PlaiWhoAmI(v56, 0x4000000000000800uLL);
      v18 = -1;
      do
        ++v18;
      while ( v56[v18] );
LABEL_19:
      v8 = (LDataCollectorSet **)&v39;
      v9 = &v40;
LABEL_12:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        v8,
        4,
        qword_180147320,
        1,
        v9,
        4,
        "LDataCollectorSet::CommitTriggers",
        34);
      goto LABEL_82;
    }
    if ( v41 )
    {
      v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 104LL))(v45, &v43);
      v6 = v19;
      if ( v19 < 0 )
      {
        LODWORD(v40) = 0;
        v39 = v19;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_82;
        }
        PlaiWhoAmI(v57, 0x4000000000000800uLL);
        v20 = -1;
        do
          ++v20;
        while ( v57[v20] );
        goto LABEL_46;
      }
      if ( v43 == 127 )
      {
        *((_DWORD *)a2 + 38) = 458754;
        *((_DWORD *)a2 + 41) = 5;
        *((_DWORD *)a2 + 39) = 4;
        *((_DWORD *)a2 + 40) = 127;
      }
    }
    v21 = (*(__int64 (__fastcall **)(__int64, struct tagVARIANT *))(*(_QWORD *)v45 + 56LL))(v45, &vtime);
    v6 = v21;
    if ( v21 < 0 )
    {
      LODWORD(v40) = 0;
      v39 = v21;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_82;
      }
      PlaiWhoAmI(v58, 0x4000000000000800uLL);
      v22 = -1;
      do
        ++v22;
      while ( v58[v22] );
      goto LABEL_46;
    }
    if ( !VariantTimeToSystemTime(vtime.dblVal, &SystemTime) )
    {
      LastError = GetLastError();
      v24 = PlaiHResultFromWin32(LastError);
      v6 = v24;
      if ( v24 < 0 )
      {
        LODWORD(v40) = 0;
        v39 = v24;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_82;
        }
        PlaiWhoAmI(v59, 0x4000000000000800uLL);
        v25 = -1;
        do
          ++v25;
        while ( v59[v25] );
        goto LABEL_46;
      }
    }
    v26 = (*(__int64 (__fastcall **)(__int64, struct tagVARIANT *))(*(_QWORD *)v45 + 88LL))(v45, &vtime);
    v6 = v26;
    if ( v26 < 0 )
    {
      LODWORD(v40) = 0;
      v39 = v26;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_82;
      }
      PlaiWhoAmI(v60, 0x4000000000000800uLL);
      v27 = -1;
      do
        ++v27;
      while ( v60[v27] );
      goto LABEL_46;
    }
    if ( !VariantTimeToSystemTime(vtime.dblVal, &v52) )
    {
      v28 = GetLastError();
      v29 = PlaiHResultFromWin32(v28);
      v6 = v29;
      if ( v29 < 0 )
      {
        LODWORD(v40) = 0;
        v39 = v29;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_82;
        }
        PlaiWhoAmI(v61, 0x4000000000000800uLL);
        v30 = -1;
        do
          ++v30;
        while ( v61[v30] );
        goto LABEL_46;
      }
    }
    SystemTime.wHour = v52.wHour;
    SystemTime.wMinute = v52.wMinute;
    SystemTime.wSecond = v52.wSecond;
    if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      v6 = 0;
    }
    else
    {
      v34 = GetLastError();
      v35 = PlaiHResultFromWin32(v34);
      v6 = v35;
      if ( v35 < 0 )
      {
        LODWORD(v40) = 0;
        v39 = v35;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_82;
        }
        PlaiWhoAmI(v62, 0x4000000000000800uLL);
        v36 = -1;
        do
          ++v36;
        while ( v62[v36] );
LABEL_46:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v39,
          4,
          qword_180147320,
          1,
          &v40,
          4,
          "LDataCollectorSet::CommitTriggers",
          34);
        goto LABEL_82;
      }
    }
    dwHighDateTime = FileTime.dwHighDateTime;
    *(_DWORD *)a2 |= 0x400u;
    v32 = FileTime.dwLowDateTime + (dwHighDateTime << 32);
    *((_DWORD *)a2 + 26) = 65537;
    *((_QWORD *)a2 + 14) = v32;
    *((_DWORD *)a2 + 27) = 2;
    goto LABEL_82;
  }
  v39 = 0;
  LODWORD(v40) = Schedules;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v53, 0x4000000000000800uLL);
    v7 = -1;
    do
      ++v7;
    while ( v53[v7] );
    v8 = &v40;
    v9 = (LDataCollectorSet **)&v39;
    goto LABEL_12;
  }
LABEL_82:
  if ( v44 )
  {
    ((void (__fastcall *)(struct IScheduleCollection *))v44->lpVtbl->Release)(v44);
    v44 = 0;
  }
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  return v6;
}

```

## disassembly

```asm
0x180099150  mov     [rsp-8+arg_10], rbx
0x180099155  push    rbp
0x180099156  push    rsi
0x180099157  push    rdi
0x180099158  push    r12
0x18009915a  push    r13
0x18009915c  push    r14
0x18009915e  push    r15
0x180099160  lea     rbp, [rsp-530h]
0x180099168  sub     rsp, 630h
0x18009916f  mov     rax, cs:__security_cookie
0x180099176  xor     rax, rsp
0x180099179  mov     [rbp+560h+var_40], rax
0x180099180  xor     r12d, r12d
0x180099183  mov     [rsp+660h+var_5E8], rcx
0x180099188  xor     eax, eax
0x18009918a  mov     [rbp+560h+var_5DC], r12d
0x18009918e  cmp     dword ptr cs:xmmword_180169738, r12d
0x180099195  xorps   xmm0, xmm0
0x180099198  mov     [rbp+560h+var_590], rax
0x18009919c  xorps   xmm1, xmm1
0x18009919f  mov     qword ptr [rbp+560h+var_5B8+10h], rax
0x1800991a3  lea     r13d, [r12+4]
0x1800991a8  mov     eax, [rcx+38h]
0x1800991ab  lea     r15d, [r12+22h]
0x1800991b0  mov     rdi, rdx
0x1800991b3  mov     [rbp+560h+var_5E0], r12d
0x1800991b7  mov     rsi, rcx
0x1800991ba  mov     qword ptr [rbp+560h+FileTime.dwLowDateTime], r12
0x1800991be  movups  xmmword ptr [rbp+560h+vtime], xmm0
0x1800991c2  mov     [rbp+560h+var_5D8], r12d
0x1800991c6  movups  xmmword ptr [rbp+560h+SystemTime.wYear], xmm0
0x1800991ca  mov     [rbp+560h+var_5C8], r12
0x1800991ce  movups  xmmword ptr [rbp+560h+var_550.wYear], xmm1
0x1800991d2  mov     [rbp+560h+var_5D0], r12
0x1800991d6  movups  xmmword ptr [rbp+560h+var_5B8], xmm0
0x1800991da  mov     [rsp+660h+var_5F0], eax
0x1800991de  jz      short loc_18009924C
0x1800991e0  mov     rdx, 4000000000000400h
0x1800991ea  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800991f1  jz      short loc_18009924C
0x1800991f3  mov     rax, cs:qword_180169748
0x1800991fa  and     rax, rdx
0x1800991fd  cmp     cs:qword_180169748, rax
0x180099204  jnz     short loc_18009924C
0x180099206  mov     [rsp+660h+var_620], r13
0x18009920b  lea     rax, [rsp+660h+var_5F0]
0x180099210  mov     [rsp+660h+var_628], rax
0x180099215  lea     r9, aLdatacollector_6; "LDataCollectorSet::CommitTriggers"
0x18009921c  lea     rax, [rsp+660h+var_5E8]
0x180099221  mov     [rsp+660h+var_630], 8
0x18009922a  mov     [rsp+660h+var_638], rax
0x18009922f  lea     r8d, [r12+3]
0x180099234  lea     rdx, PLA_EVENT_METHOD
0x18009923b  mov     [rsp+660h+var_640], r15
0x180099240  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180099247  call    EventingWriteEvent
0x18009924c  lea     rcx, [rbp+560h+vtime]; struct tagVARIANT *
0x180099250  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x180099255  lea     rcx, [rbp+560h+var_5B8]; struct tagVARIANT *
0x180099259  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x18009925e  lea     rdx, [rbp+560h+var_5D0]; struct IScheduleCollection **
0x180099262  mov     rcx, rsi; this
0x180099265  call    ?get_Schedules@DataCollectorSet@@UEAAJPEAPEAUIScheduleCollection@@@Z; DataCollectorSet::get_Schedules(IScheduleCollection * *)
0x18009926a  mov     ebx, eax
0x18009926c  test    eax, eax
0x18009926e  jns     loc_180099347
0x180099274  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009927b  mov     [rsp+660h+var_5F0], r12d
0x180099280  mov     dword ptr [rsp+660h+var_5E8], eax
0x180099284  jz      loc_1800999A2
0x18009928a  mov     rdx, 4000000000000800h; unsigned __int64
0x180099294  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009929b  jz      loc_1800999A2
0x1800992a1  mov     rax, cs:qword_180169748
0x1800992a8  and     rax, rdx
0x1800992ab  cmp     cs:qword_180169748, rax
0x1800992b2  jnz     loc_1800999A2
0x1800992b8  lea     rcx, [rbp+560h+var_540]; unsigned __int16 *
0x1800992bc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800992c1  lea     rcx, [rbp+560h+var_540]
0x1800992c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800992c9  inc     rax
0x1800992cc  cmp     [rcx+rax*2], r12w
0x1800992d1  jnz     short loc_1800992C9
0x1800992d3  lea     ecx, [rax+rax]
0x1800992d6  lea     rax, [rbp+560h+var_540]
0x1800992da  add     rcx, 2
0x1800992de  mov     [rsp+660h+var_600], rcx
0x1800992e3  lea     r9, [rsp+660h+var_5E8]
0x1800992e8  mov     [rsp+660h+var_608], rax
0x1800992ed  lea     rax, aLdatacollector_6; "LDataCollectorSet::CommitTriggers"
0x1800992f4  mov     [rsp+660h+var_610], r15
0x1800992f9  mov     r15d, 1
0x1800992ff  mov     [rsp+660h+var_618], rax
0x180099304  lea     rax, [rsp+660h+var_5F0]
0x180099309  mov     r8d, 5
0x18009930f  mov     [rsp+660h+var_620], r13
0x180099314  lea     rdx, PLA_EVENT_ERROR
0x18009931b  mov     [rsp+660h+var_628], rax
0x180099320  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180099327  lea     rax, qword_180147320
0x18009932e  mov     [rsp+660h+var_630], r15
0x180099333  mov     [rsp+660h+var_638], rax
0x180099338  mov     [rsp+660h+var_640], r13
0x18009933d  call    EventingWriteEvent
0x180099342  jmp     loc_1800999A2
0x180099347  mov     rcx, [rbp+560h+var_5D0]
0x18009934b  lea     rdx, [rbp+560h+var_5DC]
0x18009934f  mov     rax, [rcx]
0x180099352  mov     rax, [rax+38h]
0x180099356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009935b  mov     ebx, eax
0x18009935d  test    eax, eax
0x18009935f  jns     loc_180099408
0x180099365  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009936c  mov     dword ptr [rsp+660h+var_5E8], r12d
0x180099371  mov     [rsp+660h+var_5F0], eax
0x180099375  jz      loc_1800999A2
0x18009937b  mov     rdx, 4000000000000800h; unsigned __int64
0x180099385  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009938c  jz      loc_1800999A2
0x180099392  mov     rax, cs:qword_180169748
0x180099399  and     rax, rdx
0x18009939c  cmp     cs:qword_180169748, rax
0x1800993a3  jnz     loc_1800999A2
0x1800993a9  lea     rcx, [rbp+560h+var_4C0]; unsigned __int16 *
0x1800993b0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800993b5  lea     rcx, [rbp+560h+var_4C0]
0x1800993bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800993c0  inc     rax
0x1800993c3  cmp     [rcx+rax*2], r12w
0x1800993c8  jnz     short loc_1800993C0
0x1800993ca  lea     ecx, [rax+rax]
0x1800993cd  add     rcx, 2
0x1800993d1  lea     rax, [rbp+560h+var_4C0]
0x1800993d8  mov     [rsp+660h+var_600], rcx
0x1800993dd  mov     [rsp+660h+var_608], rax
0x1800993e2  mov     [rsp+660h+var_610], r15
0x1800993e7  mov     r15d, 1
0x1800993ed  lea     rax, aLdatacollector_6; "LDataCollectorSet::CommitTriggers"
0x1800993f4  mov     [rsp+660h+var_618], rax
0x1800993f9  lea     r9, [rsp+660h+var_5F0]
0x1800993fe  lea     rax, [rsp+660h+var_5E8]
0x180099403  jmp     loc_180099309
0x180099408  or      dword ptr [rdi], 0C80h
0x18009940e  lea     rdx, [rbp+560h+var_5E0]
0x180099412  mov     qword ptr [rdi+68h], 10001h
0x18009941a  mov     r15d, 1
0x180099420  mov     qword ptr [rdi+78h], 20001h
0x180099428  mov     rcx, rsi
0x18009942b  mov     [rdi+9Ch], r12d
0x180099432  mov     rax, [rsi]
0x180099435  lea     r14d, [r15+1]
0x180099439  mov     rax, [rax+40h]
0x18009943d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099442  mov     ebx, eax
0x180099444  test    eax, eax
0x180099446  jns     loc_1800994D6
0x18009944c  cmp     dword ptr cs:xmmword_180169738, r12d
0x180099453  mov     dword ptr [rsp+660h+var_5E8], r12d
0x180099458  mov     [rsp+660h+var_5F0], eax
0x18009945c  jz      loc_1800999A2
0x180099462  mov     rdx, 4000000000000800h; unsigned __int64
0x18009946c  test    qword ptr cs:xmmword_180169738+8, rdx
0x180099473  jz      loc_1800999A2
0x180099479  mov     rax, cs:qword_180169748
0x180099480  and     rax, rdx
0x180099483  cmp     cs:qword_180169748, rax
0x18009948a  jnz     loc_1800999A2
0x180099490  lea     rcx, [rbp+560h+var_440]; unsigned __int16 *
0x180099497  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009949c  lea     rcx, [rbp+560h+var_440]
0x1800994a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800994a7  inc     rax
0x1800994aa  cmp     [rcx+rax*2], r12w
0x1800994af  jnz     short loc_1800994A7
0x1800994b1  lea     ecx, [rax+rax]
0x1800994b4  lea     rax, [rbp+560h+var_440]
0x1800994bb  add     rcx, r14
0x1800994be  mov     [rsp+660h+var_600], rcx
0x1800994c3  mov     [rsp+660h+var_608], rax
0x1800994c8  mov     [rsp+660h+var_610], 22h ; '"'
0x1800994d1  jmp     loc_1800993ED
0x1800994d6  mov     ecx, [rbp+560h+var_5E0]
0x1800994d9  mov     eax, 3
0x1800994de  test    ecx, ecx
0x1800994e0  jz      short loc_180099554
0x1800994e2  mov     dword ptr [rdi+78h], 20002h
0x1800994e9  mov     [rdi+7Ch], eax
0x1800994ec  cmp     ecx, 1869Fh
0x1800994f2  ja      short loc_180099503
0x1800994f4  mov     [rdi+84h], r15d
0x1800994fb  mov     [rdi+80h], ecx
0x180099501  jmp     short loc_180099554
0x180099503  cmp     ecx, 0E10h
0x180099509  ja      short loc_18009951E
0x18009950b  mov     eax, 88888889h
0x180099510  mov     [rdi+84h], r14d
0x180099517  mul     ecx
0x180099519  shr     edx, 5
0x18009951c  jmp     short loc_180099549
0x18009951e  cmp     ecx, 15180h
0x180099524  jnb     short loc_180099538
0x180099526  mov     [rdi+84h], eax
0x18009952c  mov     eax, 91A2B3C5h
0x180099531  mul     ecx
0x180099533  shr     edx, 0Bh
0x180099536  jmp     short loc_180099549
0x180099538  mov     eax, 0C22E4507h
0x18009953d  mov     [rdi+84h], r13d
0x180099544  mul     ecx
0x180099546  shr     edx, 10h
0x180099549  mov     eax, 3
0x18009954e  mov     [rdi+80h], edx
0x180099554  cmp     [rbp+560h+var_5DC], r12d
0x180099558  jle     loc_1800999A2
0x18009955e  mov     rcx, [rbp+560h+var_5D0]
0x180099562  lea     r8, [rbp+560h+var_5C8]
0x180099566  movsd   xmm1, qword ptr [rbp+560h+var_5B8+10h]
0x18009956b  lea     rdx, [rbp+560h+var_580]
0x18009956f  mov     word ptr [rbp+560h+var_5B8], ax
0x180099573  mov     dword ptr [rbp+560h+var_5B8+8], r12d
0x180099577  mov     rax, [rcx]
0x18009957a  movups  xmm0, xmmword ptr [rbp+560h+var_5B8]
0x18009957e  movsd   [rbp+560h+var_570], xmm1
0x180099583  mov     rax, [rax+40h]
0x180099587  movaps  [rbp+560h+var_580], xmm0
0x18009958b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099590  mov     ebx, eax
0x180099592  test    eax, eax
0x180099594  jns     short loc_18009960A
0x180099596  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009959d  mov     dword ptr [rsp+660h+var_5E8], r12d
0x1800995a2  mov     [rsp+660h+var_5F0], eax
0x1800995a6  jz      loc_1800999A2
0x1800995ac  mov     rdx, 4000000000000800h; unsigned __int64
0x1800995b6  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800995bd  jz      loc_1800999A2
0x1800995c3  mov     rax, cs:qword_180169748
0x1800995ca  and     rax, rdx
0x1800995cd  cmp     cs:qword_180169748, rax
0x1800995d4  jnz     loc_1800999A2
0x1800995da  lea     rcx, [rbp+560h+var_3C0]; unsigned __int16 *
0x1800995e1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800995e6  lea     rcx, [rbp+560h+var_3C0]
0x1800995ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800995f1  inc     rax
0x1800995f4  cmp     [rcx+rax*2], r12w
0x1800995f9  jnz     short loc_1800995F1
0x1800995fb  lea     ecx, [rax+rax]
0x1800995fe  lea     rax, [rbp+560h+var_3C0]
0x180099605  jmp     loc_1800994BB
0x18009960a  mov     esi, 5
0x18009960f  cmp     [rbp+560h+var_5E0], r12d
0x180099613  jz      loc_180099701
0x180099619  mov     rcx, [rbp+560h+var_5C8]
0x18009961d  lea     rdx, [rbp+560h+var_5D8]
0x180099621  mov     rax, [rcx]
0x180099624  mov     rax, [rax+68h]
0x180099628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009962d  mov     ebx, eax
0x18009962f  test    eax, eax
0x180099631  jns     loc_1800996DA
0x180099637  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009963e  mov     dword ptr [rsp+660h+var_5E8], r12d
0x180099643  mov     [rsp+660h+var_5F0], eax
0x180099647  jz      loc_1800999A2
0x18009964d  mov     rdx, 4000000000000800h; unsigned __int64
0x180099657  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009965e  jz      loc_1800999A2
0x180099664  mov     rax, cs:qword_180169748
0x18009966b  and     rax, rdx
0x18009966e  cmp     cs:qword_180169748, rax
0x180099675  jnz     loc_1800999A2
0x18009967b  lea     rcx, [rbp+560h+var_340]; unsigned __int16 *
0x180099682  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180099687  lea     rcx, [rbp+560h+var_340]
0x18009968e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180099692  inc     rax
0x180099695  cmp     [rcx+rax*2], r12w
0x18009969a  jnz     short loc_180099692
0x18009969c  lea     ecx, [rax+rax]
0x18009969f  lea     rax, [rbp+560h+var_340]
0x1800996a6  add     rcx, r14
0x1800996a9  lea     r9, [rsp+660h+var_5F0]
0x1800996ae  mov     [rsp+660h+var_600], rcx
0x1800996b3  mov     r8d, esi
0x1800996b6  mov     [rsp+660h+var_608], rax
0x1800996bb  lea     rax, aLdatacollector_6; "LDataCollectorSet::CommitTriggers"
0x1800996c2  mov     [rsp+660h+var_610], 22h ; '"'
0x1800996cb  mov     [rsp+660h+var_618], rax
0x1800996d0  lea     rax, [rsp+660h+var_5E8]
0x1800996d5  jmp     loc_18009930F
0x1800996da  cmp     [rbp+560h+var_5D8], 7Fh
0x1800996de  jnz     short loc_180099701
0x1800996e0  mov     dword ptr [rdi+98h], 70002h
0x1800996ea  mov     [rdi+0A4h], esi
0x1800996f0  mov     [rdi+9Ch], r13d
0x1800996f7  mov     dword ptr [rdi+0A0h], 7Fh
  ... truncated ...
```
