# TMetabase_XMLtable::GetColumnValue_Bool(ulong,ushort const *,ulong)

- ea: `0x180009e84`
- end: `0x18000a1bf`
- name: `?GetColumnValue_Bool@TMetabase_XMLtable@@AEAAJKPEBGK@Z`
- size: `827`
- prototype: `int(TMetabase_XMLtable *__hidden this, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009acc`

## callees

- `0x180002bc4`
- `0x180005870`
- `0x180009e84`
- `0x180011b38`
- `0x180012734`
- `0x18002e0b2`

## import_xrefs

- `msvcrt!_memicmp` at `0x180009f2a`
- `msvcrt!_memicmp` at `0x180009f2a`
- `msvcrt!wcstoul` at `0x18000a186`
- `msvcrt!wcstoul` at `0x18000a186`
- `ole32!CoTaskMemAlloc` at `0x180009f73`
- `ole32!CoTaskMemAlloc` at `0x180009f73`

## string_xrefs

- `0x18000a065`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000a133`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TMetabase_XMLtable::GetColumnValue_Bool(
        TMetabase_XMLtable *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  __int64 v4; // r15
  TMetabase_XMLtable *v6; // rsi
  __int64 v7; // rdi
  __int64 v8; // rbx
  unsigned int v9; // ebp
  wchar_t *v10; // rax
  const wchar_t *v11; // rbx
  unsigned int v12; // eax
  unsigned int *v14; // rbx
  __int64 v15; // [rsp+88h] [rbp-70h]
  __int64 v16; // [rsp+90h] [rbp-68h]
  char v17[8]; // [rsp+B0h] [rbp-48h] BYREF
  __int64 v18; // [rsp+B8h] [rbp-40h]
  wchar_t *v20; // [rsp+110h] [rbp+18h] BYREF

  v4 = a4;
  v6 = this;
  if ( a3 && a4 )
  {
    v7 = a2;
    *((_QWORD *)this + a2 + 101) = *((_QWORD *)this + 2 * a2 + 174);
    *((_DWORD *)this + a2 + 320) = 4;
    if ( *a3 <= 0x2Du || (unsigned __int16)(*a3 - 48) <= 9u )
    {
      v14 = (unsigned int *)*((_QWORD *)this + a2 + 101);
      *v14 = wcstoul(a3, 0, 10);
    }
    else
    {
      LODWORD(v8) = 0;
      v9 = 1;
      if ( TMetabase_XMLtable::m_kwszBoolStrings )
      {
        do
        {
          if ( !_memicmp((&TMetabase_XMLtable::m_kwszBoolStrings)[(unsigned int)v8], a3, 2LL * (unsigned int)v4) )
            break;
          v8 = (unsigned int)(v8 + 1);
        }
        while ( (&TMetabase_XMLtable::m_kwszBoolStrings)[v8] );
        v6 = this;
      }
      if ( !(&TMetabase_XMLtable::m_kwszBoolStrings)[(unsigned int)v8] )
      {
        v10 = (wchar_t *)CoTaskMemAlloc(saturated_mul((unsigned int)(v4 + 1), 2u));
        v11 = v10;
        v20 = v10;
        if ( !v10 )
        {
          v9 = -2147024882;
LABEL_17:
          TSmartPointerArray<bool>::~TSmartPointerArray<bool>((LPVOID *)&v20);
          return v9;
        }
        memcpy_0(v10, a3, 2 * v4);
        v11[v4] = 0;
        v12 = *((_DWORD *)v6 + 408);
        if ( v12 >= 0x32 )
        {
          if ( v12 != 50 )
            goto LABEL_17;
          *((_DWORD *)v6 + 408) = 51;
          v18 = 0;
          CErrorInterceptor::Init(
            (CErrorInterceptor *)v17,
            (_QWORD *)v6 + 225,
            *((_QWORD *)v6 + 214),
            0x80210523,
            2u,
            -1073606423,
            (const wchar_t *)v6 + 20,
            0,
            0,
            0,
            14,
            (__int64)L"MBProperty",
            1,
            -1,
            -1,
            (__int64)v6 + 40,
            2,
            v15,
            v16,
            *((_DWORD *)v6 + 426),
            -1);
          CErrorInterceptor::WriteToLog(
            (CErrorInterceptor *)v17,
            L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
            301,
            *((_DWORD *)v6 + 415));
        }
        else
        {
          *((_DWORD *)v6 + 408) = v12 + 1;
          v18 = 0;
          CErrorInterceptor::Init(
            (CErrorInterceptor *)v17,
            (_QWORD *)v6 + 225,
            *((_QWORD *)v6 + 214),
            0x80210523,
            2u,
            -2147348282,
            v11,
            0,
            0,
            0,
            14,
            (__int64)L"MBProperty",
            1,
            -1,
            -1,
            (__int64)v6 + 40,
            2,
            v15,
            v16,
            *((_DWORD *)v6 + 426),
            -1);
          CErrorInterceptor::WriteToLog(
            (CErrorInterceptor *)v17,
            L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
            301,
            *((_DWORD *)v6 + 415));
        }
        CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v17);
        goto LABEL_17;
      }
      **((_DWORD **)v6 + v7 + 101) = v8 & 1;
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
0x180009e84  mov     [rsp+arg_8], rbx
0x180009e89  mov     [rsp+arg_0], rcx
0x180009e8e  push    rbp
0x180009e8f  push    rsi
0x180009e90  push    rdi
0x180009e91  push    r12
0x180009e93  push    r13
0x180009e95  push    r14
0x180009e97  push    r15
0x180009e99  sub     rsp, 0C0h
0x180009ea0  mov     r15d, r9d
0x180009ea3  mov     r14, r8
0x180009ea6  mov     rsi, rcx
0x180009ea9  xor     r13d, r13d
0x180009eac  test    r8, r8
0x180009eaf  jz      loc_18000A190
0x180009eb5  test    r9d, r9d
0x180009eb8  jz      loc_18000A190
0x180009ebe  mov     edi, edx
0x180009ec0  lea     rax, [rdi+57h]
0x180009ec4  add     rax, rax
0x180009ec7  mov     rax, [rcx+rax*8]
0x180009ecb  mov     [rcx+rdi*8+328h], rax
0x180009ed3  mov     dword ptr [rcx+rdi*4+500h], 4
0x180009ede  movzx   eax, word ptr [r8]
0x180009ee2  cmp     ax, 2Dh ; '-'
0x180009ee6  jbe     loc_18000A175
0x180009eec  sub     ax, 30h ; '0'
0x180009ef0  cmp     ax, 9
0x180009ef4  jbe     loc_18000A175
0x180009efa  mov     ebx, r13d
0x180009efd  lea     rcx, ?m_kwszBoolStrings@TMetabase_XMLtable@@0PAPEBGA; ushort const * near * TMetabase_XMLtable::m_kwszBoolStrings
0x180009f04  lea     ebp, [r13+1]
0x180009f08  cmp     cs:?m_kwszBoolStrings@TMetabase_XMLtable@@0PAPEBGA, r13; ushort const * near * TMetabase_XMLtable::m_kwszBoolStrings
0x180009f0f  jz      short loc_180009F4B
0x180009f11  mov     r12d, r15d
0x180009f14  add     r12, r12
0x180009f17  lea     rsi, ?m_kwszBoolStrings@TMetabase_XMLtable@@0PAPEBGA; ushort const * near * TMetabase_XMLtable::m_kwszBoolStrings
0x180009f1e  mov     ecx, ebx
0x180009f20  mov     r8, r12; Size
0x180009f23  mov     rdx, r14; Buf2
0x180009f26  mov     rcx, [rsi+rcx*8]; Buf1
0x180009f2a  call    cs:__imp__memicmp
0x180009f30  test    eax, eax
0x180009f32  jz      short loc_180009F3C
0x180009f34  add     ebx, ebp
0x180009f36  cmp     [rsi+rbx*8], r13
0x180009f3a  jnz     short loc_180009F1E
0x180009f3c  mov     rsi, [rsp+0F8h+arg_0]
0x180009f44  lea     rcx, ?m_kwszBoolStrings@TMetabase_XMLtable@@0PAPEBGA; ushort const * near * TMetabase_XMLtable::m_kwszBoolStrings
0x180009f4b  mov     eax, ebx
0x180009f4d  cmp     [rcx+rax*8], r13
0x180009f51  jnz     loc_18000A167
0x180009f57  lea     ecx, [r15+1]
0x180009f5b  mov     r12d, 2
0x180009f61  mov     eax, r12d
0x180009f64  mul     rcx
0x180009f67  lea     rcx, [r12-3]
0x180009f6c  cmovb   rax, rcx
0x180009f70  mov     rcx, rax; cb
0x180009f73  call    cs:__imp_CoTaskMemAlloc
0x180009f79  mov     rbx, rax
0x180009f7c  mov     [rsp+0F8h+arg_10], rax
0x180009f84  test    rax, rax
0x180009f87  jnz     short loc_180009F93
0x180009f89  mov     ebp, 8007000Eh
0x180009f8e  jmp     loc_18000A156
0x180009f93  lea     rdi, [r15+r15]
0x180009f97  mov     r8, rdi; Size
0x180009f9a  mov     rdx, r14; Src
0x180009f9d  mov     rcx, rbx; void *
0x180009fa0  call    memcpy_0
0x180009fa5  mov     [rdi+rbx], r13w
0x180009faa  mov     eax, [rsi+660h]
0x180009fb0  cmp     eax, 32h ; '2'
0x180009fb3  jnb     loc_18000A07F
0x180009fb9  inc     eax
0x180009fbb  mov     [rsi+660h], eax
0x180009fc1  mov     [rsp+0F8h+var_40], r13
0x180009fc9  lea     rcx, [rsi+28h]
0x180009fcd  lea     rdx, [rsi+708h]
0x180009fd4  or      r8d, 0FFFFFFFFh
0x180009fd8  mov     [rsp+0F8h+var_58], r8d
0x180009fe0  mov     eax, [rsi+6A8h]
0x180009fe6  mov     [rsp+0F8h+var_60], eax
0x180009fed  mov     [rsp+0F8h+var_78], r12d
0x180009ff5  mov     [rsp+0F8h+var_80], rcx
0x180009ffa  mov     [rsp+0F8h+var_88], r8d
0x180009fff  mov     [rsp+0F8h+var_90], r8d
0x18000a004  mov     [rsp+0F8h+var_98], ebp
0x18000a008  lea     rax, aMbproperty; "MBProperty"
0x18000a00f  mov     [rsp+0F8h+var_A0], rax
0x18000a014  mov     [rsp+0F8h+var_A8], 0Eh
0x18000a01c  mov     [rsp+0F8h+var_B0], r13
0x18000a021  mov     [rsp+0F8h+var_B8], r13
0x18000a026  mov     [rsp+0F8h+var_C0], r13
0x18000a02b  mov     [rsp+0F8h+var_C8], rbx
0x18000a030  mov     [rsp+0F8h+var_D0], 800210C6h
0x18000a038  mov     [rsp+0F8h+var_D8], r12d
0x18000a03d  mov     r9d, 80210523h
0x18000a043  mov     r8, [rsi+6B0h]
0x18000a04a  lea     rcx, [rsp+0F8h+var_48]
0x18000a052  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000a057  nop
0x18000a058  mov     r9d, [rsi+67Ch]; unsigned int
0x18000a05f  mov     r8d, 12Dh; unsigned int
0x18000a065  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000a06c  lea     rcx, [rsp+0F8h+var_48]; this
0x18000a074  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000a079  nop
0x18000a07a  jmp     loc_18000A148
0x18000a07f  jnz     loc_18000A156
0x18000a085  mov     dword ptr [rsi+660h], 33h ; '3'
0x18000a08f  mov     [rsp+0F8h+var_40], r13
0x18000a097  lea     rcx, [rsi+28h]
0x18000a09b  lea     rdx, [rsi+708h]
0x18000a0a2  or      r8d, 0FFFFFFFFh
0x18000a0a6  mov     [rsp+0F8h+var_58], r8d
0x18000a0ae  mov     eax, [rsi+6A8h]
0x18000a0b4  mov     [rsp+0F8h+var_60], eax
0x18000a0bb  mov     [rsp+0F8h+var_78], r12d
0x18000a0c3  mov     [rsp+0F8h+var_80], rcx
0x18000a0c8  mov     [rsp+0F8h+var_88], r8d
0x18000a0cd  mov     [rsp+0F8h+var_90], r8d
0x18000a0d2  mov     [rsp+0F8h+var_98], ebp
0x18000a0d6  lea     rax, aMbproperty; "MBProperty"
0x18000a0dd  mov     [rsp+0F8h+var_A0], rax
0x18000a0e2  mov     [rsp+0F8h+var_A8], 0Eh
0x18000a0ea  mov     [rsp+0F8h+var_B0], r13
0x18000a0ef  mov     [rsp+0F8h+var_B8], r13
0x18000a0f4  mov     [rsp+0F8h+var_C0], r13
0x18000a0f9  mov     [rsp+0F8h+var_C8], rcx
0x18000a0fe  mov     [rsp+0F8h+var_D0], 0C00210E9h
0x18000a106  mov     [rsp+0F8h+var_D8], r12d
0x18000a10b  mov     r9d, 80210523h
0x18000a111  mov     r8, [rsi+6B0h]
0x18000a118  lea     rcx, [rsp+0F8h+var_48]
0x18000a120  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000a125  nop
0x18000a126  mov     r9d, [rsi+67Ch]; unsigned int
0x18000a12d  mov     r8d, 12Dh; unsigned int
0x18000a133  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000a13a  lea     rcx, [rsp+0F8h+var_48]; this
0x18000a142  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000a147  nop
0x18000a148  lea     rcx, [rsp+0F8h+var_48]; this
0x18000a150  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18000a155  nop
0x18000a156  lea     rcx, [rsp+0F8h+arg_10]; void *
0x18000a15e  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x18000a163  mov     eax, ebp
0x18000a165  jmp     short loc_18000A1A4
0x18000a167  and     ebx, ebp
0x18000a169  mov     rax, [rsi+rdi*8+328h]
0x18000a171  mov     [rax], ebx
0x18000a173  jmp     short loc_18000A1A2
0x18000a175  mov     rbx, [rcx+rdi*8+328h]
0x18000a17d  xor     edx, edx; EndPtr
0x18000a17f  lea     r8d, [rdx+0Ah]; Radix
0x18000a183  mov     rcx, r14; String
0x18000a186  call    cs:__imp_wcstoul
0x18000a18c  mov     [rbx], eax
0x18000a18e  jmp     short loc_18000A1A2
0x18000a190  mov     eax, edx
0x18000a192  mov     [rcx+rax*8+328h], r13
0x18000a19a  mov     [rcx+rax*4+500h], r13d
0x18000a1a2  xor     eax, eax
0x18000a1a4  mov     rbx, [rsp+0F8h+arg_8]
0x18000a1ac  add     rsp, 0C0h
0x18000a1b3  pop     r15
0x18000a1b5  pop     r14
0x18000a1b7  pop     r13
0x18000a1b9  pop     r12
0x18000a1bb  pop     rdi
0x18000a1bc  pop     rsi
0x18000a1bd  pop     rbp
0x18000a1be  retn
```
