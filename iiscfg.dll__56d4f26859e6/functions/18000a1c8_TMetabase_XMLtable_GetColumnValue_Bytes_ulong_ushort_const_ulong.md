# TMetabase_XMLtable::GetColumnValue_Bytes(ulong,ushort const *,ulong)

- ea: `0x18000a1c8`
- end: `0x18000a6ab`
- name: `?GetColumnValue_Bytes@TMetabase_XMLtable@@AEAAJKPEBGK@Z`
- size: `1251`
- prototype: `int(TMetabase_XMLtable *__hidden this, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180009acc`

## callees

- `0x180002bc4`
- `0x180005870`
- `0x18000a1c8`
- `0x18000bdf4`
- `0x180011b38`
- `0x180012734`
- `0x18002e0b2`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000a224`
- `ole32!CoTaskMemAlloc` at `0x18000a4b9`
- `ole32!CoTaskMemAlloc` at `0x18000a224`
- `ole32!CoTaskMemAlloc` at `0x18000a4b9`

## string_xrefs

- `0x18000a30b`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000a3ce`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000a5a0`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000a663`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TMetabase_XMLtable::GetColumnValue_Bytes(
        TMetabase_XMLtable *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  __int64 v4; // rdi
  unsigned int v7; // r14d
  char *v8; // rax
  char *v9; // rbx
  size_t v10; // rdi
  unsigned int v11; // eax
  __int64 v13; // rbx
  _BYTE *v14; // rdx
  unsigned int v15; // r8d
  const unsigned __int16 *v16; // r9
  int v17; // eax
  char v18; // cl
  char v19; // cl
  int v20; // eax
  char v21; // al
  char *v22; // rax
  char *v23; // rbx
  size_t v24; // rdi
  unsigned int v25; // eax
  char v26[8]; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v27; // [rsp+B8h] [rbp+Fh]
  char *v28; // [rsp+120h] [rbp+77h] BYREF

  v4 = a4;
  if ( a3 && a4 )
  {
    v7 = 1;
    if ( (a4 & 1) != 0 )
    {
      v8 = (char *)CoTaskMemAlloc(saturated_mul(a4 + 1, 2u));
      v9 = v8;
      v28 = v8;
      if ( !v8 )
      {
        v7 = -2147024882;
LABEL_11:
        TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v28);
        return v7;
      }
      v10 = 2 * v4;
      memcpy_0(v8, a3, v10);
      *(_WORD *)&v9[v10] = 0;
      v11 = *((_DWORD *)this + 408);
      if ( v11 >= 0x32 )
      {
        if ( v11 != 50 )
          goto LABEL_11;
        *((_DWORD *)this + 408) = 51;
        v27 = 0;
        CErrorInterceptor::Init(
          v26,
          (char *)this + 1800,
          *((_QWORD *)this + 214),
          2149647651LL,
          2,
          -1073606423,
          (char *)this + 40,
          0,
          0,
          0,
          14,
          L"MBProperty",
          1,
          -1,
          -1,
          (char *)this + 40,
          2);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)v26,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          332,
          *((_DWORD *)this + 415));
      }
      else
      {
        *((_DWORD *)this + 408) = v11 + 1;
        v27 = 0;
        CErrorInterceptor::Init(
          v26,
          (char *)this + 1800,
          *((_QWORD *)this + 214),
          2149647651LL,
          2,
          -2147348290,
          v9,
          0,
          0,
          0,
          14,
          L"MBProperty",
          1,
          -1,
          -1,
          (char *)this + 40,
          2);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)v26,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          332,
          *((_DWORD *)this + 415));
      }
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v26);
      goto LABEL_11;
    }
    v13 = a2;
    *((_DWORD *)this + a2 + 320) = a4 >> 1;
    if ( a4 >> 1 )
    {
      TGrowableBuffer::Grow((TMetabase_XMLtable *)((char *)this + 16 * a2 + 1392), a4 >> 1);
      v14 = (_BYTE *)*((_QWORD *)this + 2 * v13 + 174);
      *((_QWORD *)this + v13 + 101) = v14;
      v15 = v4;
      v16 = a3;
      while ( v15 > 1 )
      {
        v17 = *v16;
        if ( (v17 & 0xFFFFFF80) != 0
          || (v18 = *((_BYTE *)qword_1800365F0 + (v17 & 0x7F)), v18 == -1)
          || (v19 = 16 * v18, *v14 = v19, v20 = v16[1], (v20 & 0xFFFFFF80) != 0)
          || (v21 = *((_BYTE *)qword_1800365F0 + (v20 & 0x7F)), v21 == -1) )
        {
          v22 = (char *)CoTaskMemAlloc(saturated_mul((unsigned int)(v4 + 1), 2u));
          v23 = v22;
          v28 = v22;
          if ( !v22 )
          {
            v7 = -2147024882;
            goto LABEL_11;
          }
          v24 = 2 * v4;
          memcpy_0(v22, a3, v24);
          *(_WORD *)&v23[v24] = 0;
          v25 = *((_DWORD *)this + 408);
          if ( v25 >= 0x32 )
          {
            if ( v25 != 50 )
              goto LABEL_11;
            *((_DWORD *)this + 408) = 51;
            v27 = 0;
            CErrorInterceptor::Init(
              v26,
              (char *)this + 1800,
              *((_QWORD *)this + 214),
              2149647651LL,
              2,
              -1073606423,
              (char *)this + 40,
              0,
              0,
              0,
              14,
              L"MBProperty",
              1,
              -1,
              -1,
              (char *)this + 40,
              2);
            CErrorInterceptor::WriteToLog(
              (CErrorInterceptor *)v26,
              L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
              357,
              *((_DWORD *)this + 415));
          }
          else
          {
            *((_DWORD *)this + 408) = v25 + 1;
            v27 = 0;
            CErrorInterceptor::Init(
              v26,
              (char *)this + 1800,
              *((_QWORD *)this + 214),
              2149647651LL,
              2,
              -2147348289,
              v23,
              0,
              0,
              0,
              14,
              L"MBProperty",
              1,
              -1,
              -1,
              (char *)this + 40,
              2);
            CErrorInterceptor::WriteToLog(
              (CErrorInterceptor *)v26,
              L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
              357,
              *((_DWORD *)this + 415));
          }
          CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v26);
          goto LABEL_11;
        }
        v16 += 2;
        *v14++ = v19 | v21;
        v15 -= 2;
      }
    }
    else
    {
      *((_QWORD *)this + a2 + 101) = 0;
      *((_DWORD *)this + a2 + 320) = 0;
    }
  }
  else
  {
    *((_QWORD *)this + a2 + 101) = 0;
    *((_DWORD *)this + a2 + 320) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a1c8  push    rbp
0x18000a1ca  push    rbx
0x18000a1cb  push    rsi
0x18000a1cc  push    rdi
0x18000a1cd  push    r12
0x18000a1cf  push    r13
0x18000a1d1  push    r14
0x18000a1d3  push    r15
0x18000a1d5  lea     rbp, [rsp-1Fh]
0x18000a1da  sub     rsp, 0C8h
0x18000a1e1  mov     edi, r9d
0x18000a1e4  mov     r12, r8
0x18000a1e7  mov     rsi, rcx
0x18000a1ea  xor     r13d, r13d
0x18000a1ed  test    r8, r8
0x18000a1f0  jz      loc_18000A683
0x18000a1f6  test    r9d, r9d
0x18000a1f9  jz      loc_18000A683
0x18000a1ff  lea     r14d, [r13+1]
0x18000a203  test    r14b, dil
0x18000a206  jz      loc_18000A3FA
0x18000a20c  lea     ecx, [rdi+1]
0x18000a20f  lea     r15d, [r13+2]
0x18000a213  mov     eax, r15d
0x18000a216  mul     rcx
0x18000a219  lea     rcx, [r13-1]
0x18000a21d  cmovb   rax, rcx
0x18000a221  mov     rcx, rax; cb
0x18000a224  call    cs:__imp_CoTaskMemAlloc
0x18000a22a  mov     rbx, rax
0x18000a22d  mov     [rbp+57h+arg_10], rax
0x18000a231  test    rax, rax
0x18000a234  jnz     short loc_18000A241
0x18000a236  mov     r14d, 8007000Eh
0x18000a23c  jmp     loc_18000A3E9
0x18000a241  add     rdi, rdi
0x18000a244  mov     r8, rdi; Size
0x18000a247  mov     rdx, r12; Src
0x18000a24a  mov     rcx, rbx; void *
0x18000a24d  call    memcpy_0
0x18000a252  mov     [rdi+rbx], r13w
0x18000a257  mov     eax, [rsi+660h]
0x18000a25d  cmp     eax, 32h ; '2'
0x18000a260  jnb     loc_18000A321
0x18000a266  inc     eax
0x18000a268  mov     [rsi+660h], eax
0x18000a26e  mov     [rbp+57h+var_48], r13
0x18000a272  lea     rcx, [rsi+28h]
0x18000a276  lea     rdx, [rsi+708h]
0x18000a27d  or      r8d, 0FFFFFFFFh
0x18000a281  mov     [rsp+100h+var_60], r8d
0x18000a289  mov     eax, [rsi+6A8h]
0x18000a28f  mov     [rsp+100h+var_68], eax
0x18000a296  mov     [rsp+100h+var_80], r15d
0x18000a29e  mov     [rsp+100h+var_88], rcx
0x18000a2a3  mov     [rsp+100h+var_90], r8d
0x18000a2a8  mov     [rsp+100h+var_98], r8d
0x18000a2ad  mov     [rsp+100h+var_A0], r14d
0x18000a2b2  lea     rax, aMbproperty; "MBProperty"
0x18000a2b9  mov     [rsp+100h+var_A8], rax
0x18000a2be  mov     [rsp+100h+var_B0], 0Eh
0x18000a2c6  mov     [rsp+100h+var_B8], r13
0x18000a2cb  mov     [rsp+100h+var_C0], r13
0x18000a2d0  mov     [rsp+100h+var_C8], r13
0x18000a2d5  mov     [rsp+100h+var_D0], rbx
0x18000a2da  mov     [rsp+100h+var_D8], 800210BEh
0x18000a2e2  mov     [rsp+100h+var_E0], r15d
0x18000a2e7  mov     r9d, 80210523h
0x18000a2ed  mov     r8, [rsi+6B0h]
0x18000a2f4  lea     rcx, [rbp+57h+var_50]
0x18000a2f8  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000a2fd  nop
0x18000a2fe  mov     r9d, [rsi+67Ch]; unsigned int
0x18000a305  mov     r8d, 14Ch; unsigned int
0x18000a30b  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000a312  lea     rcx, [rbp+57h+var_50]; this
0x18000a316  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000a31b  nop
0x18000a31c  jmp     loc_18000A3DF
0x18000a321  jnz     loc_18000A3E9
0x18000a327  mov     dword ptr [rsi+660h], 33h ; '3'
0x18000a331  mov     [rbp+57h+var_48], r13
0x18000a335  lea     rcx, [rsi+28h]
0x18000a339  lea     rdx, [rsi+708h]
0x18000a340  or      r8d, 0FFFFFFFFh
0x18000a344  mov     [rsp+100h+var_60], r8d
0x18000a34c  mov     eax, [rsi+6A8h]
0x18000a352  mov     [rsp+100h+var_68], eax
0x18000a359  mov     [rsp+100h+var_80], r15d
0x18000a361  mov     [rsp+100h+var_88], rcx
0x18000a366  mov     [rsp+100h+var_90], r8d
0x18000a36b  mov     [rsp+100h+var_98], r8d
0x18000a370  mov     [rsp+100h+var_A0], r14d
0x18000a375  lea     rax, aMbproperty; "MBProperty"
0x18000a37c  mov     [rsp+100h+var_A8], rax
0x18000a381  mov     [rsp+100h+var_B0], 0Eh
0x18000a389  mov     [rsp+100h+var_B8], r13
0x18000a38e  mov     [rsp+100h+var_C0], r13
0x18000a393  mov     [rsp+100h+var_C8], r13
0x18000a398  mov     [rsp+100h+var_D0], rcx
0x18000a39d  mov     [rsp+100h+var_D8], 0C00210E9h
0x18000a3a5  mov     [rsp+100h+var_E0], r15d
0x18000a3aa  mov     r9d, 80210523h
0x18000a3b0  mov     r8, [rsi+6B0h]
0x18000a3b7  lea     rcx, [rbp+57h+var_50]
0x18000a3bb  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000a3c0  nop
0x18000a3c1  mov     r9d, [rsi+67Ch]; unsigned int
0x18000a3c8  mov     r8d, 14Ch; unsigned int
0x18000a3ce  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000a3d5  lea     rcx, [rbp+57h+var_50]; this
0x18000a3d9  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000a3de  nop
0x18000a3df  lea     rcx, [rbp+57h+var_50]; this
0x18000a3e3  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18000a3e8  nop
0x18000a3e9  lea     rcx, [rbp+57h+arg_10]; void *
0x18000a3ed  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x18000a3f2  mov     eax, r14d
0x18000a3f5  jmp     loc_18000A697
0x18000a3fa  mov     eax, edi
0x18000a3fc  shr     eax, 1
0x18000a3fe  mov     ebx, edx
0x18000a400  mov     [rcx+rbx*4+500h], eax
0x18000a407  jnz     short loc_18000A41E
0x18000a409  mov     [rcx+rbx*8+328h], r13
0x18000a411  mov     [rcx+rbx*4+500h], r13d
0x18000a419  jmp     loc_18000A695
0x18000a41e  mov     edx, eax; unsigned __int64
0x18000a420  lea     rcx, [rbx+57h]
0x18000a424  shl     rcx, 4
0x18000a428  add     rcx, rsi; this
0x18000a42b  call    ?Grow@TGrowableBuffer@@QEAAX_K@Z; TGrowableBuffer::Grow(unsigned __int64)
0x18000a430  lea     rax, [rbx+57h]
0x18000a434  add     rax, rax
0x18000a437  mov     rdx, [rsi+rax*8]
0x18000a43b  mov     [rsi+rbx*8+328h], rdx
0x18000a443  mov     r8d, edi
0x18000a446  mov     r9, r12
0x18000a449  mov     r10d, 0FFFFFF80h
0x18000a44f  lea     r11, qword_1800365F0
0x18000a456  cmp     r8d, r14d
0x18000a459  jbe     loc_18000A695
0x18000a45f  movzx   eax, word ptr [r9]
0x18000a463  test    r10d, eax
0x18000a466  jnz     short loc_18000A49F
0x18000a468  and     eax, 7Fh
0x18000a46b  mov     cl, [rax+r11]
0x18000a46f  cmp     cl, 0FFh
0x18000a472  jz      short loc_18000A49F
0x18000a474  shl     cl, 4
0x18000a477  mov     [rdx], cl
0x18000a479  movzx   eax, word ptr [r9+2]
0x18000a47e  test    r10d, eax
0x18000a481  jnz     short loc_18000A49F
0x18000a483  and     eax, 7Fh
0x18000a486  mov     al, [rax+r11]
0x18000a48a  cmp     al, 0FFh
0x18000a48c  jz      short loc_18000A49F
0x18000a48e  add     r9, 4
0x18000a492  or      al, cl
0x18000a494  mov     [rdx], al
0x18000a496  add     rdx, r14
0x18000a499  add     r8d, 0FFFFFFFEh
0x18000a49d  jmp     short loc_18000A456
0x18000a49f  lea     ecx, [rdi+1]
0x18000a4a2  mov     r15d, 2
0x18000a4a8  mov     eax, r15d
0x18000a4ab  mul     rcx
0x18000a4ae  lea     rcx, [r15-3]
0x18000a4b2  cmovb   rax, rcx
0x18000a4b6  mov     rcx, rax; cb
0x18000a4b9  call    cs:__imp_CoTaskMemAlloc
0x18000a4bf  mov     rbx, rax
0x18000a4c2  mov     [rbp+57h+arg_10], rax
0x18000a4c6  test    rax, rax
0x18000a4c9  jnz     short loc_18000A4D6
0x18000a4cb  mov     r14d, 8007000Eh
0x18000a4d1  jmp     loc_18000A67E
0x18000a4d6  add     rdi, rdi
0x18000a4d9  mov     r8, rdi; Size
0x18000a4dc  mov     rdx, r12; Src
0x18000a4df  mov     rcx, rbx; void *
0x18000a4e2  call    memcpy_0
0x18000a4e7  mov     [rdi+rbx], r13w
0x18000a4ec  mov     eax, [rsi+660h]
0x18000a4f2  cmp     eax, 32h ; '2'
0x18000a4f5  jnb     loc_18000A5B6
0x18000a4fb  inc     eax
0x18000a4fd  mov     [rsi+660h], eax
0x18000a503  mov     [rbp+57h+var_48], r13
0x18000a507  lea     rcx, [rsi+28h]
0x18000a50b  lea     rdx, [rsi+708h]
0x18000a512  or      r8d, 0FFFFFFFFh
0x18000a516  mov     [rsp+100h+var_60], r8d
0x18000a51e  mov     eax, [rsi+6A8h]
0x18000a524  mov     [rsp+100h+var_68], eax
0x18000a52b  mov     [rsp+100h+var_80], r15d
0x18000a533  mov     [rsp+100h+var_88], rcx
0x18000a538  mov     [rsp+100h+var_90], r8d
0x18000a53d  mov     [rsp+100h+var_98], r8d
0x18000a542  mov     [rsp+100h+var_A0], r14d
0x18000a547  lea     rax, aMbproperty; "MBProperty"
0x18000a54e  mov     [rsp+100h+var_A8], rax
0x18000a553  mov     [rsp+100h+var_B0], 0Eh
0x18000a55b  mov     [rsp+100h+var_B8], r13
0x18000a560  mov     [rsp+100h+var_C0], r13
0x18000a565  mov     [rsp+100h+var_C8], r13
0x18000a56a  mov     [rsp+100h+var_D0], rbx
0x18000a56f  mov     [rsp+100h+var_D8], 800210BFh
0x18000a577  mov     [rsp+100h+var_E0], r15d
0x18000a57c  mov     r9d, 80210523h
0x18000a582  mov     r8, [rsi+6B0h]
0x18000a589  lea     rcx, [rbp+57h+var_50]
0x18000a58d  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000a592  nop
0x18000a593  mov     r9d, [rsi+67Ch]; unsigned int
0x18000a59a  mov     r8d, 165h; unsigned int
0x18000a5a0  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000a5a7  lea     rcx, [rbp+57h+var_50]; this
0x18000a5ab  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000a5b0  nop
0x18000a5b1  jmp     loc_18000A674
0x18000a5b6  jnz     loc_18000A67E
0x18000a5bc  mov     dword ptr [rsi+660h], 33h ; '3'
0x18000a5c6  mov     [rbp+57h+var_48], r13
0x18000a5ca  lea     rcx, [rsi+28h]
0x18000a5ce  lea     rdx, [rsi+708h]
0x18000a5d5  or      r8d, 0FFFFFFFFh
0x18000a5d9  mov     [rsp+100h+var_60], r8d
0x18000a5e1  mov     eax, [rsi+6A8h]
0x18000a5e7  mov     [rsp+100h+var_68], eax
0x18000a5ee  mov     [rsp+100h+var_80], r15d
0x18000a5f6  mov     [rsp+100h+var_88], rcx
0x18000a5fb  mov     [rsp+100h+var_90], r8d
0x18000a600  mov     [rsp+100h+var_98], r8d
0x18000a605  mov     [rsp+100h+var_A0], r14d
0x18000a60a  lea     rax, aMbproperty; "MBProperty"
0x18000a611  mov     [rsp+100h+var_A8], rax
0x18000a616  mov     [rsp+100h+var_B0], 0Eh
0x18000a61e  mov     [rsp+100h+var_B8], r13
0x18000a623  mov     [rsp+100h+var_C0], r13
0x18000a628  mov     [rsp+100h+var_C8], r13
0x18000a62d  mov     [rsp+100h+var_D0], rcx
0x18000a632  mov     [rsp+100h+var_D8], 0C00210E9h
0x18000a63a  mov     [rsp+100h+var_E0], r15d
0x18000a63f  mov     r9d, 80210523h
0x18000a645  mov     r8, [rsi+6B0h]
0x18000a64c  lea     rcx, [rbp+57h+var_50]
0x18000a650  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000a655  nop
0x18000a656  mov     r9d, [rsi+67Ch]; unsigned int
0x18000a65d  mov     r8d, 165h; unsigned int
0x18000a663  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000a66a  lea     rcx, [rbp+57h+var_50]; this
0x18000a66e  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000a673  nop
0x18000a674  lea     rcx, [rbp+57h+var_50]; this
0x18000a678  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18000a67d  nop
0x18000a67e  jmp     loc_18000A3E9
0x18000a683  mov     eax, edx
0x18000a685  mov     [rcx+rax*8+328h], r13
0x18000a68d  mov     [rcx+rax*4+500h], r13d
0x18000a695  xor     eax, eax
0x18000a697  add     rsp, 0C8h
0x18000a69e  pop     r15
0x18000a6a0  pop     r14
0x18000a6a2  pop     r13
0x18000a6a4  pop     r12
0x18000a6a6  pop     rdi
0x18000a6a7  pop     rsi
0x18000a6a8  pop     rbx
0x18000a6a9  pop     rbp
0x18000a6aa  retn
```
