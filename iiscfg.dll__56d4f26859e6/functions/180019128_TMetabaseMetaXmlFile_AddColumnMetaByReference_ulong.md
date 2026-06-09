# TMetabaseMetaXmlFile::AddColumnMetaByReference(ulong)

- ea: `0x180019128`
- end: `0x18001954d`
- name: `?AddColumnMetaByReference@TMetabaseMetaXmlFile@@AEAAXK@Z`
- size: `1061`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800199c8`
- `0x18001b354`

## callees

- `0x180002bc4`
- `0x180011b38`
- `0x180012734`
- `0x180017ad8`
- `0x180019128`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## string_xrefs

- `0x180019241`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180019268`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001936b`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180019392`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180019261`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001938b`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TMetabaseMetaXmlFile::AddColumnMetaByReference(TMetabaseMetaXmlFile *this)
{
  unsigned int *v2; // rsi
  bool v3; // cf
  __int64 v4; // rax
  const wchar_t *v5; // rax
  unsigned int v6; // ebx
  const wchar_t *v7; // rbx
  const wchar_t *v8; // rax
  __int64 v9; // rax
  __int64 (__fastcall *v10)(TMetabaseMetaXmlFile *, _QWORD); // rbx
  int v11; // edx
  __int64 v12; // [rsp+88h] [rbp-A8h]
  __int64 v13; // [rsp+90h] [rbp-A0h]
  _DWORD v14[2]; // [rsp+B8h] [rbp-78h] BYREF
  __int128 v15; // [rsp+C0h] [rbp-70h]
  _DWORD v16[24]; // [rsp+D0h] [rbp-60h] BYREF

  v2 = (unsigned int *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *))(*(_QWORD *)this + 176LL))(this);
  *((_DWORD *)this + 634) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(
                              this,
                              *((unsigned int *)this + 643));
  v3 = ((*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(this, v2[6]) & 0x10) != 0;
  v4 = *(_QWORD *)this;
  if ( v3 )
  {
    v5 = (const wchar_t *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v4 + 144))(this, v2[2]);
    *(_QWORD *)&v15 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v14,
      0,
      *((_QWORD *)this + 325),
      0x80210861,
      3u,
      -1073606453,
      v5,
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0,
      v12,
      v13,
      -1,
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v14,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      573,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v14);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x23Du,
      0);
  }
  if ( ((*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v4 + 152))(this, v2[6]) & 0xC0) != 0 )
  {
    v6 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 384LL))(
           this,
           *v2,
           v2[1],
           0);
    if ( v6 == -1 )
    {
      v7 = (const wchar_t *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(
                              this,
                              v2[2]);
      v8 = (const wchar_t *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(
                              this,
                              *v2);
      *(_QWORD *)&v15 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v14,
        0,
        *((_QWORD *)this + 325),
        0x80210861,
        3u,
        -1073606452,
        v8,
        v7,
        &word_180034198,
        &word_180034198,
        0,
        0,
        0,
        -1,
        -1,
        0,
        0,
        v12,
        v13,
        -1,
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v14,
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        583,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v14);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
        0x247u,
        0);
    }
    while ( v6 < (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *))(*(_QWORD *)this + 328LL))(this)
         && *(_DWORD *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 240LL))(this, v6) == *v2
         && *(_DWORD *)((*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 240LL))(this, v6)
                      + 4) == v2[1] )
    {
      v9 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 240LL))(this, v6);
      v15 = 0;
      v14[0] = *((_DWORD *)this + 636);
      v14[1] = *((_DWORD *)this + 634);
      v15 = *(_OWORD *)(v9 + 8);
      (*(void (__fastcall **)(TMetabaseMetaXmlFile *, _DWORD *, __int64))(*(_QWORD *)this + 120LL))(this, v14, 1);
      ++v6;
    }
  }
  memset_0(v16, 0, 0x54u);
  v16[0] = *((_DWORD *)this + 636);
  v16[1] = *((_DWORD *)this + 634);
  v16[2] = v2[2];
  v16[3] = v2[3];
  v16[4] = v2[4];
  v16[5] = v2[5];
  v16[6] = v2[6];
  v16[7] = v2[7];
  v16[8] = v2[8];
  v16[9] = v2[9];
  v16[10] = v2[10];
  v16[11] = v2[11];
  v10 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL);
  v11 = 0;
  if ( v2[12] )
    v11 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(this, v2[12]);
  v16[12] = v10(this, v11 | 0x440u);
  v16[13] = v2[13];
  v16[14] = v2[14];
  v16[15] = v2[15];
  v16[16] = v2[16];
  v16[17] = v2[17];
  (*(void (__fastcall **)(TMetabaseMetaXmlFile *, _DWORD *, __int64))(*(_QWORD *)this + 56LL))(this, v16, 1);
  ++*((_DWORD *)this + 643);
}

```

## disassembly

```asm
0x180019128  mov     [rsp-8+arg_10], rbx
0x18001912d  mov     [rsp-8+arg_18], rsi
0x180019132  push    rbp
0x180019133  push    rdi
0x180019134  push    r14
0x180019136  lea     rbp, [rsp-10h]
0x18001913b  sub     rsp, 140h
0x180019142  mov     rax, cs:__security_cookie
0x180019149  xor     rax, rsp
0x18001914c  mov     [rbp+20h+var_20], rax
0x180019150  mov     rdi, rcx
0x180019153  mov     rax, [rcx]
0x180019156  mov     rax, [rax+0B0h]
0x18001915d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019162  mov     rsi, rax
0x180019165  mov     rcx, [rdi]
0x180019168  mov     rax, [rcx+10h]
0x18001916c  mov     edx, [rdi+0A0Ch]
0x180019172  mov     rcx, rdi
0x180019175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001917a  mov     [rdi+9E8h], eax
0x180019180  mov     rcx, [rdi]
0x180019183  mov     rax, [rcx+98h]
0x18001918a  mov     edx, [rsi+18h]
0x18001918d  mov     rcx, rdi
0x180019190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019195  bt      eax, 4
0x180019199  mov     rax, [rdi]
0x18001919c  mov     rcx, rdi
0x18001919f  jnb     loc_180019275
0x1800191a5  mov     edx, [rsi+8]
0x1800191a8  mov     rax, [rax+90h]
0x1800191af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191b4  xor     edx, edx
0x1800191b6  mov     qword ptr [rbp+20h+var_90], rdx
0x1800191ba  or      r14d, 0FFFFFFFFh
0x1800191be  mov     [rsp+150h+var_B0], r14d
0x1800191c6  mov     [rsp+150h+var_B8], r14d
0x1800191ce  mov     [rsp+150h+var_D0], edx
0x1800191d5  mov     [rsp+150h+var_D8], rdx
0x1800191da  mov     [rsp+150h+var_E0], r14d
0x1800191df  mov     [rsp+150h+var_E8], r14d
0x1800191e4  mov     [rsp+150h+var_F0], edx
0x1800191e8  mov     [rsp+150h+var_F8], rdx
0x1800191ed  mov     [rsp+150h+var_100], edx
0x1800191f1  lea     rcx, word_180034198
0x1800191f8  mov     [rsp+150h+var_108], rcx
0x1800191fd  mov     [rsp+150h+var_110], rcx
0x180019202  mov     [rsp+150h+var_118], rcx
0x180019207  mov     [rsp+150h+var_120], rax
0x18001920c  mov     [rsp+150h+var_128], 0C00210CBh
0x180019214  mov     [rsp+150h+var_130], 3
0x18001921c  mov     r9d, 80210861h
0x180019222  mov     r8, [rdi+0A28h]
0x180019229  lea     rcx, [rbp+20h+var_98]
0x18001922d  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180019232  nop
0x180019233  mov     ebx, 23Dh
0x180019238  mov     r9d, 400000h; unsigned int
0x18001923e  mov     r8d, ebx; unsigned int
0x180019241  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180019248  lea     rcx, [rbp+20h+var_98]; this
0x18001924c  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180019251  nop
0x180019252  lea     rcx, [rbp+20h+var_98]; this
0x180019256  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001925b  xor     r9d, r9d; unsigned int
0x18001925e  mov     r8d, ebx; unsigned int
0x180019261  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x180019268  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001926f  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180019275  mov     edx, [rsi+18h]
0x180019278  mov     rax, [rax+98h]
0x18001927f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019284  test    al, 0C0h
0x180019286  jz      loc_180019459
0x18001928c  mov     rax, [rdi]
0x18001928f  xor     r9d, r9d
0x180019292  mov     r8d, [rsi+4]
0x180019296  mov     edx, [rsi]
0x180019298  mov     rcx, rdi
0x18001929b  mov     rax, [rax+180h]
0x1800192a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192a7  mov     ebx, eax
0x1800192a9  or      r14d, 0FFFFFFFFh
0x1800192ad  cmp     eax, r14d
0x1800192b0  jnz     loc_18001939F
0x1800192b6  mov     rax, [rdi]
0x1800192b9  mov     edx, [rsi+8]
0x1800192bc  mov     rcx, rdi
0x1800192bf  mov     rax, [rax+90h]
0x1800192c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192cb  mov     rbx, rax
0x1800192ce  mov     rcx, [rdi]
0x1800192d1  mov     rax, [rcx+90h]
0x1800192d8  mov     edx, [rsi]
0x1800192da  mov     rcx, rdi
0x1800192dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192e2  xor     edx, edx
0x1800192e4  mov     qword ptr [rbp+20h+var_90], rdx
0x1800192e8  mov     [rsp+150h+var_B0], r14d
0x1800192f0  mov     [rsp+150h+var_B8], r14d
0x1800192f8  mov     [rsp+150h+var_D0], edx
0x1800192ff  mov     [rsp+150h+var_D8], rdx
0x180019304  mov     [rsp+150h+var_E0], r14d
0x180019309  mov     [rsp+150h+var_E8], r14d
0x18001930e  mov     [rsp+150h+var_F0], edx
0x180019312  mov     [rsp+150h+var_F8], rdx
0x180019317  mov     [rsp+150h+var_100], edx
0x18001931b  lea     rcx, word_180034198
0x180019322  mov     [rsp+150h+var_108], rcx
0x180019327  mov     [rsp+150h+var_110], rcx
0x18001932c  mov     [rsp+150h+var_118], rbx
0x180019331  mov     [rsp+150h+var_120], rax
0x180019336  mov     [rsp+150h+var_128], 0C00210CCh
0x18001933e  mov     [rsp+150h+var_130], 3
0x180019346  mov     r9d, 80210861h
0x18001934c  mov     r8, [rdi+0A28h]
0x180019353  lea     rcx, [rbp+20h+var_98]
0x180019357  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001935c  nop
0x18001935d  mov     ebx, 247h
0x180019362  mov     r9d, 400000h; unsigned int
0x180019368  mov     r8d, ebx; unsigned int
0x18001936b  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180019372  lea     rcx, [rbp+20h+var_98]; this
0x180019376  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001937b  nop
0x18001937c  lea     rcx, [rbp+20h+var_98]; this
0x180019380  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180019385  xor     r9d, r9d; unsigned int
0x180019388  mov     r8d, ebx; unsigned int
0x18001938b  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x180019392  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180019399  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001939f  mov     rax, [rdi]
0x1800193a2  mov     rcx, rdi
0x1800193a5  mov     rax, [rax+148h]
0x1800193ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193b1  cmp     ebx, eax
0x1800193b3  jnb     loc_180019459
0x1800193b9  mov     rax, [rdi]
0x1800193bc  mov     edx, ebx
0x1800193be  mov     rcx, rdi
0x1800193c1  mov     rax, [rax+0F0h]
0x1800193c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193cd  mov     ecx, [rax]
0x1800193cf  cmp     ecx, [rsi]
0x1800193d1  jnz     loc_180019459
0x1800193d7  mov     rax, [rdi]
0x1800193da  mov     edx, ebx
0x1800193dc  mov     rcx, rdi
0x1800193df  mov     rax, [rax+0F0h]
0x1800193e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193eb  mov     ecx, [rax+4]
0x1800193ee  cmp     ecx, [rsi+4]
0x1800193f1  jnz     short loc_180019459
0x1800193f3  mov     rax, [rdi]
0x1800193f6  mov     edx, ebx
0x1800193f8  mov     rcx, rdi
0x1800193fb  mov     rax, [rax+0F0h]
0x180019402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019407  xorps   xmm0, xmm0
0x18001940a  movdqu  [rbp+20h+var_90], xmm0
0x18001940f  mov     ecx, [rdi+9F0h]
0x180019415  mov     [rbp+20h+var_98], ecx
0x180019418  mov     ecx, [rdi+9E8h]
0x18001941e  mov     [rbp+20h+var_94], ecx
0x180019421  mov     ecx, [rax+8]
0x180019424  mov     dword ptr [rbp+20h+var_90], ecx
0x180019427  mov     ecx, [rax+0Ch]
0x18001942a  mov     dword ptr [rbp+20h+var_90+4], ecx
0x18001942d  mov     ecx, [rax+10h]
0x180019430  mov     dword ptr [rbp+20h+var_90+8], ecx
0x180019433  mov     eax, [rax+14h]
0x180019436  mov     dword ptr [rbp+20h+var_90+0Ch], eax
0x180019439  mov     rax, [rdi]
0x18001943c  mov     r8d, 1
0x180019442  lea     rdx, [rbp+20h+var_98]
0x180019446  mov     rcx, rdi
0x180019449  mov     rax, [rax+78h]
0x18001944d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019452  inc     ebx
0x180019454  jmp     loc_18001939F
0x180019459  xor     edx, edx; Val
0x18001945b  lea     r8d, [rdx+54h]; Size
0x18001945f  lea     rcx, [rbp+20h+var_80]; void *
0x180019463  call    memset_0
0x180019468  mov     eax, [rdi+9F0h]
0x18001946e  mov     [rbp+20h+var_80], eax
0x180019471  mov     eax, [rdi+9E8h]
0x180019477  mov     [rbp+20h+var_7C], eax
0x18001947a  mov     eax, [rsi+8]
0x18001947d  mov     [rbp+20h+var_78], eax
0x180019480  mov     eax, [rsi+0Ch]
0x180019483  mov     [rbp+20h+var_74], eax
0x180019486  mov     eax, [rsi+10h]
0x180019489  mov     [rbp+20h+var_70], eax
0x18001948c  mov     eax, [rsi+14h]
0x18001948f  mov     [rbp+20h+var_6C], eax
0x180019492  mov     eax, [rsi+18h]
0x180019495  mov     [rbp+20h+var_68], eax
0x180019498  mov     eax, [rsi+1Ch]
0x18001949b  mov     [rbp+20h+var_64], eax
0x18001949e  mov     eax, [rsi+20h]
0x1800194a1  mov     [rbp+20h+var_60], eax
0x1800194a4  mov     eax, [rsi+24h]
0x1800194a7  mov     [rbp+20h+var_5C], eax
0x1800194aa  mov     eax, [rsi+28h]
0x1800194ad  mov     [rbp+20h+var_58], eax
0x1800194b0  mov     eax, [rsi+2Ch]
0x1800194b3  mov     [rbp+20h+var_54], eax
0x1800194b6  mov     rax, [rdi]
0x1800194b9  mov     rbx, [rax+10h]
0x1800194bd  xor     edx, edx
0x1800194bf  cmp     [rsi+30h], edx
0x1800194c2  jz      short loc_1800194D8
0x1800194c4  mov     edx, [rsi+30h]
0x1800194c7  mov     rcx, rdi
0x1800194ca  mov     rax, [rax+98h]
0x1800194d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194d6  mov     edx, eax
0x1800194d8  or      edx, 440h
0x1800194de  mov     rcx, rdi
0x1800194e1  mov     rax, rbx
0x1800194e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194e9  mov     [rbp+20h+var_50], eax
0x1800194ec  mov     eax, [rsi+34h]
0x1800194ef  mov     [rbp+20h+var_4C], eax
0x1800194f2  mov     eax, [rsi+38h]
0x1800194f5  mov     [rbp+20h+var_48], eax
0x1800194f8  mov     eax, [rsi+3Ch]
0x1800194fb  mov     [rbp+20h+var_44], eax
0x1800194fe  mov     eax, [rsi+40h]
0x180019501  mov     [rbp+20h+var_40], eax
0x180019504  mov     eax, [rsi+44h]
0x180019507  mov     [rbp+20h+var_3C], eax
0x18001950a  mov     rax, [rdi]
0x18001950d  mov     r8d, 1
0x180019513  lea     rdx, [rbp+20h+var_80]
0x180019517  mov     rcx, rdi
0x18001951a  mov     rax, [rax+38h]
0x18001951e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019523  inc     dword ptr [rdi+0A0Ch]
0x180019529  mov     rcx, [rbp+20h+var_20]
0x18001952d  xor     rcx, rsp; StackCookie
0x180019530  call    __security_check_cookie
0x180019535  lea     r11, [rsp+150h+var_10]
0x18001953d  mov     rbx, [r11+30h]
0x180019541  mov     rsi, [r11+38h]
0x180019545  mov     rsp, r11
0x180019548  pop     r14
0x18001954a  pop     rdi
0x18001954b  pop     rbp
0x18001954c  retn
```
