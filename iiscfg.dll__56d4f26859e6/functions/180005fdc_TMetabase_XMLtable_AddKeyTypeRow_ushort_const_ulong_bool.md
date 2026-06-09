# TMetabase_XMLtable::AddKeyTypeRow(ushort const *,ulong,bool)

- ea: `0x180005fdc`
- end: `0x18000630a`
- name: `?AddKeyTypeRow@TMetabase_XMLtable@@AEAAJPEBGK_N@Z`
- size: `814`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this, const unsigned __int16 *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180006750`

## callees

- `0x180002bc4`
- `0x180005fdc`
- `0x180006310`
- `0x180009acc`
- `0x18000c9d4`
- `0x180011b38`
- `0x180012734`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## string_xrefs

- `0x180006136`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TMetabase_XMLtable::AddKeyTypeRow(
        TMetabase_XMLtable *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        char a4)
{
  unsigned int *v8; // rsi
  _QWORD *v9; // rdi
  __int64 result; // rax
  TMetabase_XMLtable *v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rax
  __int64 v14; // [rsp+88h] [rbp-A8h]
  __int64 v15; // [rsp+90h] [rbp-A0h]
  unsigned int v16; // [rsp+B0h] [rbp-80h] BYREF
  unsigned int v17; // [rsp+B4h] [rbp-7Ch] BYREF
  _BYTE v18[8]; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v19; // [rsp+C0h] [rbp-70h]
  _BYTE v20[16]; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-50h]
  __int64 v22; // [rsp+138h] [rbp+8h]
  __int64 v23; // [rsp+140h] [rbp+10h]
  __int64 v24; // [rsp+148h] [rbp+18h]
  int v25; // [rsp+168h] [rbp+38h]
  int v26; // [rsp+170h] [rbp+40h]
  int v27; // [rsp+174h] [rbp+44h]
  int v28; // [rsp+178h] [rbp+48h]

  v8 = (unsigned int *)((char *)this + 1668);
  v9 = (_QWORD *)((char *)this + 2040);
  if ( *((_DWORD *)this + 417) == -1
    && (*((_QWORD *)this + 258) = **((_QWORD **)this + 196),
        *((_QWORD *)this + 260) = L"KeyType",
        (*(int (__fastcall **)(_QWORD, _QWORD, __int64, char *, _QWORD, char *, unsigned int *))(*(_QWORD *)*v9 + 56LL))(
          *v9,
          0,
          2,
          (char *)this + 2048,
          0,
          (char *)this + 2064,
          v8) < 0) )
  {
    v19 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v18,
      (_QWORD *)this + 225,
      *((_QWORD *)this + 214),
      0x80210862,
      2u,
      -2147348291,
      *((const wchar_t **)this + 260),
      0,
      0,
      0,
      14,
      (__int64)L"MBProperty",
      1,
      -1,
      -1,
      (__int64)this + 40,
      1,
      v14,
      v15,
      *((_DWORD *)this + 426),
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v18,
      L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
      2174,
      *((_DWORD *)this + 415));
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v18);
    return 2149648482LL;
  }
  else
  {
    memset_0(v20, 0, 0x90u);
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v9 + 32LL))(*v9, *v8, 18);
    if ( (int)result >= 0 )
    {
      v12 = TMetabase_XMLtable::MetabaseTypeFromColumnMetaType(v11, (struct tCOLUMNMETARow *)v20);
      v17 = v12;
      *((_QWORD *)this + 101) = v21;
      *((_QWORD *)this + 102) = &v17;
      *((_DWORD *)this + 321) = v26;
      *((_QWORD *)this + 103) = v24;
      *((_DWORD *)this + 322) = v25;
      *((_QWORD *)this + 106) = v22;
      *((_DWORD *)this + 325) = v27;
      *((_QWORD *)this + 107) = v23;
      *((_DWORD *)this + 326) = v28;
      result = TMetabase_XMLtable::FillInColumn(this, 3u, a2, a3, v12, 0, 0);
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result == 1 )
          return 0;
      }
      else
      {
        if ( a4 )
        {
          *((_QWORD *)this + 101) = aLocationwithno;
          v13 = -1;
          do
            ++v13;
          while ( aLocationwithno[v13] );
          *((_DWORD *)this + 320) = 2 * v13 + 2;
          *((_QWORD *)this + 106) = &TMetabase_XMLtable::m_kLocationID;
          *((_DWORD *)this + 325) = 0;
          *((_QWORD *)this + 104) = 0;
          *((_DWORD *)this + 323) = 0;
        }
        v16 = 0;
        result = (*(__int64 (__fastcall **)(TMetabase_XMLtable *, unsigned int *))(*(_QWORD *)this + 72LL))(this, &v16);
        if ( (int)result >= 0 )
        {
          result = (*(__int64 (__fastcall **)(TMetabase_XMLtable *, _QWORD, __int64))(*(_QWORD *)this + 88LL))(
                     this,
                     v16,
                     9);
          if ( (int)result >= 0 )
            return TMetabase_XMLtable::AddPropertyToLocationMapping(this, *((const unsigned __int16 **)this + 105), v16);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005fdc  mov     [rsp-8+arg_18], rbx
0x180005fe1  push    rbp
0x180005fe2  push    rsi
0x180005fe3  push    rdi
0x180005fe4  push    r12
0x180005fe6  push    r13
0x180005fe8  push    r14
0x180005fea  push    r15
0x180005fec  lea     rbp, [rsp-90h]
0x180005ff4  sub     rsp, 1C0h
0x180005ffb  mov     rax, cs:__security_cookie
0x180006002  xor     rax, rsp
0x180006005  mov     [rbp+0C0h+var_40], rax
0x18000600c  mov     r14b, r9b
0x18000600f  mov     r12d, r8d
0x180006012  mov     r15, rdx
0x180006015  mov     rbx, rcx
0x180006018  lea     rsi, [rcx+684h]
0x18000601f  lea     rdi, [rcx+7F8h]
0x180006026  xor     r13d, r13d
0x180006029  cmp     dword ptr [rsi], 0FFFFFFFFh
0x18000602c  jnz     loc_180006157
0x180006032  lea     rdx, [rcx+810h]
0x180006039  mov     rax, [rcx+620h]
0x180006040  mov     rcx, [rax]
0x180006043  mov     [rdx], rcx
0x180006046  lea     rax, aKeytype; "KeyType"
0x18000604d  mov     [rbx+820h], rax
0x180006054  mov     rcx, [rdi]
0x180006057  mov     rax, [rcx]
0x18000605a  lea     r9, [rbx+800h]
0x180006061  mov     qword ptr [rsp+1F0h+var_1C0], rsi
0x180006066  mov     qword ptr [rsp+1F0h+var_1C8], rdx
0x18000606b  mov     qword ptr [rsp+1F0h+var_1D0], r13
0x180006070  xor     edx, edx
0x180006072  lea     r8d, [r13+2]
0x180006076  mov     rax, [rax+38h]
0x18000607a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000607f  test    eax, eax
0x180006081  jns     loc_180006157
0x180006087  mov     [rbp+0C0h+var_130], r13
0x18000608b  lea     rcx, [rbx+28h]
0x18000608f  lea     rdx, [rbx+708h]
0x180006096  or      r8d, 0FFFFFFFFh
0x18000609a  mov     [rsp+1F0h+var_150], r8d
0x1800060a2  mov     eax, [rbx+6A8h]
0x1800060a8  mov     [rsp+1F0h+var_158], eax
0x1800060af  mov     [rsp+1F0h+var_170], 1
0x1800060ba  mov     [rsp+1F0h+var_178], rcx
0x1800060bf  mov     [rsp+1F0h+var_180], r8d
0x1800060c4  mov     [rsp+1F0h+var_188], r8d
0x1800060c9  mov     [rsp+1F0h+var_190], 1
0x1800060d1  lea     rax, aMbproperty; "MBProperty"
0x1800060d8  mov     [rsp+1F0h+var_198], rax
0x1800060dd  mov     [rsp+1F0h+var_1A0], 0Eh
0x1800060e5  mov     [rsp+1F0h+var_1A8], r13
0x1800060ea  mov     [rsp+1F0h+var_1B0], r13
0x1800060ef  mov     [rsp+1F0h+var_1B8], r13
0x1800060f4  mov     rax, [rbx+820h]
0x1800060fb  mov     qword ptr [rsp+1F0h+var_1C0], rax
0x180006100  mov     [rsp+1F0h+var_1C8], 800210BDh
0x180006108  mov     [rsp+1F0h+var_1D0], 2
0x180006110  mov     edi, 80210862h
0x180006115  mov     r9d, edi
0x180006118  mov     r8, [rbx+6B0h]
0x18000611f  lea     rcx, [rbp+0C0h+var_138]
0x180006123  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180006128  nop
0x180006129  mov     r9d, [rbx+67Ch]; unsigned int
0x180006130  mov     r8d, 87Eh; unsigned int
0x180006136  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000613d  lea     rcx, [rbp+0C0h+var_138]; this
0x180006141  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180006146  nop
0x180006147  lea     rcx, [rbp+0C0h+var_138]; this
0x18000614b  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180006150  mov     eax, edi
0x180006152  jmp     loc_1800062E0
0x180006157  xor     edx, edx; Val
0x180006159  mov     r8d, 90h; Size
0x18000615f  lea     rcx, [rbp+0C0h+var_120]; void *
0x180006163  call    memset_0
0x180006168  mov     rcx, [rdi]
0x18000616b  mov     rax, [rcx]
0x18000616e  lea     rdx, [rbp+0C0h+var_120]
0x180006172  mov     qword ptr [rsp+1F0h+var_1C8], rdx
0x180006177  lea     rdx, [rbp+0C0h+var_90]
0x18000617b  mov     qword ptr [rsp+1F0h+var_1D0], rdx
0x180006180  xor     r9d, r9d
0x180006183  lea     r8d, [r9+12h]
0x180006187  mov     edx, [rsi]
0x180006189  mov     rax, [rax+20h]
0x18000618d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006192  test    eax, eax
0x180006194  js      loc_1800062E0
0x18000619a  lea     rdx, [rbp+0C0h+var_120]; struct tCOLUMNMETARow *
0x18000619e  call    ?MetabaseTypeFromColumnMetaType@TMetabase_XMLtable@@AEBAKAEAUtCOLUMNMETARow@@@Z; TMetabase_XMLtable::MetabaseTypeFromColumnMetaType(tCOLUMNMETARow &)
0x1800061a3  mov     edx, eax
0x1800061a5  mov     [rbp+0C0h+var_13C], eax
0x1800061a8  lea     rdi, [rbx+328h]
0x1800061af  mov     rcx, [rbp+0C0h+var_110]
0x1800061b3  mov     [rdi], rcx
0x1800061b6  lea     rax, [rbp+0C0h+var_13C]
0x1800061ba  mov     [rbx+330h], rax
0x1800061c1  mov     ecx, [rbp+0C0h+var_80]
0x1800061c4  mov     [rbx+504h], ecx
0x1800061ca  mov     rcx, [rbp+0C0h+var_A8]
0x1800061ce  mov     [rbx+338h], rcx
0x1800061d5  mov     ecx, [rbp+0C0h+var_88]
0x1800061d8  mov     [rbx+508h], ecx
0x1800061de  mov     rcx, [rbp+0C0h+var_B8]
0x1800061e2  mov     [rbx+350h], rcx
0x1800061e9  mov     eax, [rbp+0C0h+var_7C]
0x1800061ec  mov     [rbx+514h], eax
0x1800061f2  mov     rax, [rbp+0C0h+var_B0]
0x1800061f6  mov     [rbx+358h], rax
0x1800061fd  mov     eax, [rbp+0C0h+var_78]
0x180006200  mov     [rbx+518h], eax
0x180006206  mov     [rsp+1F0h+var_1C0], r13b; bool
0x18000620b  mov     [rsp+1F0h+var_1C8], r13d; unsigned int
0x180006210  mov     [rsp+1F0h+var_1D0], edx; unsigned int
0x180006214  mov     r9d, r12d; unsigned int
0x180006217  mov     r8, r15; unsigned __int16 *
0x18000621a  mov     edx, 3; unsigned int
0x18000621f  mov     rcx, rbx; this
0x180006222  call    ?FillInColumn@TMetabase_XMLtable@@AEAAJKPEBGKKK_N@Z; TMetabase_XMLtable::FillInColumn(ulong,ushort const *,ulong,ulong,ulong,bool)
0x180006227  test    eax, eax
0x180006229  jz      short loc_180006237
0x18000622b  cmp     eax, 1
0x18000622e  cmovz   eax, r13d
0x180006232  jmp     loc_1800062E0
0x180006237  test    r14b, r14b
0x18000623a  jz      short loc_180006284
0x18000623c  lea     rcx, aLocationwithno; "#LocationWithNoProperties"
0x180006243  mov     [rdi], rcx
0x180006246  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000624a  inc     rax
0x18000624d  cmp     [rcx+rax*2], r13w
0x180006252  jnz     short loc_18000624A
0x180006254  lea     eax, ds:2[rax*2]
0x18000625b  mov     [rbx+500h], eax
0x180006261  lea     rax, ?m_kLocationID@TMetabase_XMLtable@@0KA; ulong TMetabase_XMLtable::m_kLocationID
0x180006268  mov     [rbx+350h], rax
0x18000626f  mov     [rbx+514h], r13d
0x180006276  mov     [rbx+340h], r13
0x18000627d  mov     [rbx+50Ch], r13d
0x180006284  mov     [rbp+0C0h+var_140], r13d
0x180006288  mov     rax, [rbx]
0x18000628b  lea     rdx, [rbp+0C0h+var_140]
0x18000628f  mov     rcx, rbx
0x180006292  mov     rax, [rax+48h]
0x180006296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000629b  test    eax, eax
0x18000629d  js      short loc_1800062E0
0x18000629f  mov     rax, [rbx]
0x1800062a2  lea     rcx, [rbx+500h]
0x1800062a9  mov     qword ptr [rsp+1F0h+var_1C8], rdi
0x1800062ae  mov     qword ptr [rsp+1F0h+var_1D0], rcx
0x1800062b3  xor     r9d, r9d
0x1800062b6  lea     r8d, [r9+9]
0x1800062ba  mov     edx, [rbp+0C0h+var_140]
0x1800062bd  mov     rcx, rbx
0x1800062c0  mov     rax, [rax+58h]
0x1800062c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c9  test    eax, eax
0x1800062cb  js      short loc_1800062E0
0x1800062cd  mov     r8d, [rbp+0C0h+var_140]; unsigned int
0x1800062d1  mov     rdx, [rbx+348h]; unsigned __int16 *
0x1800062d8  mov     rcx, rbx; this
0x1800062db  call    ?AddPropertyToLocationMapping@TMetabase_XMLtable@@AEAAJPEBGK@Z; TMetabase_XMLtable::AddPropertyToLocationMapping(ushort const *,ulong)
0x1800062e0  mov     rcx, [rbp+0C0h+var_40]
0x1800062e7  xor     rcx, rsp; StackCookie
0x1800062ea  call    __security_check_cookie
0x1800062ef  mov     rbx, [rsp+1F0h+arg_18]
0x1800062f7  add     rsp, 1C0h
0x1800062fe  pop     r15
0x180006300  pop     r14
0x180006302  pop     r13
0x180006304  pop     r12
0x180006306  pop     rdi
0x180006307  pop     rsi
0x180006308  pop     rbp
0x180006309  retn
```
