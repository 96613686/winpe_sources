# TMetabase_XMLtable::FillInColumn(ulong,ushort const *,ulong,ulong,ulong,bool)

- ea: `0x180009acc`
- end: `0x180009dcd`
- name: `?FillInColumn@TMetabase_XMLtable@@AEAAJKPEBGKKK_N@Z`
- size: `769`
- prototype: `__int64 __usercall@<rax>(TMetabase_XMLtable *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, bool)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180005cb8`
- `0x180005fdc`
- `0x180006750`

## callees

- `0x180002bc4`
- `0x180009acc`
- `0x180009e3c`
- `0x180009e84`
- `0x18000a1c8`
- `0x18000a6b4`
- `0x18000a898`
- `0x18000a9b4`
- `0x180011b38`
- `0x180012734`

## string_xrefs

- `0x180009c32`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x180009d1a`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TMetabase_XMLtable::FillInColumn(
        TMetabase_XMLtable *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        bool a7)
{
  unsigned int v7; // r10d
  bool v9; // r11
  unsigned int v10; // edx
  unsigned int v11; // eax
  int v12; // edx
  TMetabase_XMLtable *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int *v16; // rdx
  unsigned int v18; // eax
  __int64 v19; // [rsp+88h] [rbp-40h]
  __int64 v20; // [rsp+90h] [rbp-38h]
  char v21[8]; // [rsp+B0h] [rbp-18h] BYREF
  __int64 v22; // [rsp+B8h] [rbp-10h]

  v7 = a2;
  v9 = a7;
  v10 = a5;
  while ( 1 )
  {
    if ( !a4 && ((TMetabase_XMLtable::GetColumnMetaType(this, v10) - 128) & 0xFFFFFFFD) != 0 )
    {
      v18 = *((_DWORD *)this + 408);
      if ( v18 >= 0x32 )
      {
        if ( v18 != 50 )
          return 1;
        *((_DWORD *)this + 408) = 51;
        v22 = 0;
        CErrorInterceptor::Init(
          (CErrorInterceptor *)v21,
          (_QWORD *)this + 225,
          *((_QWORD *)this + 214),
          0x80210523,
          2u,
          -1073606423,
          (const wchar_t *)this + 20,
          0,
          0,
          0,
          14,
          (__int64)L"MBProperty",
          1,
          -1,
          -1,
          (__int64)this + 40,
          2,
          v19,
          v20,
          *((_DWORD *)this + 426),
          -1);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)v21,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          164,
          *((_DWORD *)this + 415));
      }
      else
      {
        *((_DWORD *)this + 408) = v18 + 1;
        v22 = 0;
        CErrorInterceptor::Init(
          (CErrorInterceptor *)v21,
          (_QWORD *)this + 225,
          *((_QWORD *)this + 214),
          0x80210523,
          2u,
          -2147348240,
          &word_180034198,
          0,
          0,
          0,
          14,
          (__int64)L"MBProperty",
          1,
          -1,
          -1,
          (__int64)this + 40,
          2,
          v19,
          v20,
          *((_DWORD *)this + 426),
          -1);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)v21,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          164,
          *((_DWORD *)this + 415));
      }
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v21);
      return 1;
    }
    if ( v9 )
      return TMetabase_XMLtable::GetColumnValue_Bytes(this, v7, a3, a4);
    v11 = TMetabase_XMLtable::GetColumnMetaType(this, v10) - 19;
    if ( !v11 )
    {
      if ( (a6 & 0x20) != 0 )
        return TMetabase_XMLtable::GetColumnValue_Bool(this, v7, a3, a4);
      else
        return TMetabase_XMLtable::GetColumnValue_UI4(this, v7, a3, a4);
    }
    v14 = v11 - 53;
    if ( !v14 )
      return 2147500037LL;
    v15 = v14 - 56;
    if ( v15 )
      break;
    if ( v7 == 3 )
    {
      v16 = (unsigned int *)*((_QWORD *)this + 102);
      if ( v16 )
      {
        if ( TMetabase_XMLtable::GetColumnMetaType(v13, *v16) != 128 )
          continue;
      }
    }
    return TMetabase_XMLtable::GetColumnValue_Bytes(this, v7, a3, a4);
  }
  if ( v15 != 2 )
    return 2149647633LL;
  if ( (a6 & 0x2000000) != 0 || v12 == 5 )
    return TMetabase_XMLtable::GetColumnValue_MultiSZ(this, v7, a3, a4);
  return TMetabase_XMLtable::GetColumnValue_String(this, v7, a3, a4);
}

```

## disassembly

```asm
0x180009acc  push    rbx
0x180009ace  sub     rsp, 0C0h
0x180009ad5  mov     r10d, edx
0x180009ad8  mov     rbx, rcx
0x180009adb  mov     r11b, [rsp+0C8h+arg_30]
0x180009ae3  mov     edx, [rsp+0C8h+arg_20]; unsigned int
0x180009aea  test    r9d, r9d
0x180009aed  jnz     short loc_180009AFE
0x180009aef  call    ?GetColumnMetaType@TMetabase_XMLtable@@AEBAKK@Z; TMetabase_XMLtable::GetColumnMetaType(ulong)
0x180009af4  add     eax, 0FFFFFF80h
0x180009af7  test    eax, 0FFFFFFFDh
0x180009afc  jnz     short loc_180009B56
0x180009afe  test    r11b, r11b
0x180009b01  jnz     short loc_180009B43
0x180009b03  call    ?GetColumnMetaType@TMetabase_XMLtable@@AEBAKK@Z; TMetabase_XMLtable::GetColumnMetaType(ulong)
0x180009b08  sub     eax, 13h
0x180009b0b  jz      loc_180009DA3
0x180009b11  sub     eax, 35h ; '5'
0x180009b14  jz      loc_180009D95
0x180009b1a  sub     eax, 38h ; '8'
0x180009b1d  jnz     loc_180009D4A
0x180009b23  cmp     r10d, 3
0x180009b27  jnz     short loc_180009B43
0x180009b29  mov     rdx, [rbx+330h]
0x180009b30  test    rdx, rdx
0x180009b33  jz      short loc_180009B43
0x180009b35  mov     edx, [rdx]; unsigned int
0x180009b37  call    ?GetColumnMetaType@TMetabase_XMLtable@@AEBAKK@Z; TMetabase_XMLtable::GetColumnMetaType(ulong)
0x180009b3c  cmp     eax, 80h
0x180009b41  jnz     short loc_180009AEA
0x180009b43  mov     edx, r10d; unsigned int
0x180009b46  mov     rcx, rbx; this
0x180009b49  add     rsp, 0C0h
0x180009b50  pop     rbx
0x180009b51  jmp     ?GetColumnValue_Bytes@TMetabase_XMLtable@@AEAAJKPEBGK@Z; TMetabase_XMLtable::GetColumnValue_Bytes(ulong,ushort const *,ulong)
0x180009b56  mov     eax, [rbx+660h]
0x180009b5c  cmp     eax, 32h ; '2'
0x180009b5f  jnb     loc_180009C4C
0x180009b65  inc     eax
0x180009b67  mov     [rbx+660h], eax
0x180009b6d  mov     [rsp+0C8h+var_10], 0
0x180009b79  lea     rcx, [rbx+28h]
0x180009b7d  lea     rdx, [rbx+708h]
0x180009b84  or      r8d, 0FFFFFFFFh
0x180009b88  mov     [rsp+0C8h+var_28], r8d
0x180009b90  mov     eax, [rbx+6A8h]
0x180009b96  mov     [rsp+0C8h+var_30], eax
0x180009b9d  mov     [rsp+0C8h+var_48], 2
0x180009ba8  mov     [rsp+0C8h+var_50], rcx
0x180009bad  mov     [rsp+0C8h+var_58], r8d
0x180009bb2  mov     [rsp+0C8h+var_60], r8d
0x180009bb7  mov     [rsp+0C8h+var_68], 1
0x180009bbf  lea     rax, aMbproperty; "MBProperty"
0x180009bc6  mov     [rsp+0C8h+var_70], rax
0x180009bcb  mov     [rsp+0C8h+var_78], 0Eh
0x180009bd3  mov     [rsp+0C8h+var_80], 0
0x180009bdc  mov     [rsp+0C8h+var_88], 0
0x180009be5  mov     [rsp+0C8h+var_90], 0
0x180009bee  lea     rax, word_180034198
0x180009bf5  mov     [rsp+0C8h+var_98], rax
0x180009bfa  mov     [rsp+0C8h+var_A0], 800210F0h
0x180009c02  mov     [rsp+0C8h+var_A8], 2
0x180009c0a  mov     r9d, 80210523h
0x180009c10  mov     r8, [rbx+6B0h]
0x180009c17  lea     rcx, [rsp+0C8h+var_18]
0x180009c1f  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180009c24  nop
0x180009c25  mov     r9d, [rbx+67Ch]; unsigned int
0x180009c2c  mov     r8d, 0A4h; unsigned int
0x180009c32  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x180009c39  lea     rcx, [rsp+0C8h+var_18]; this
0x180009c41  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180009c46  nop
0x180009c47  jmp     loc_180009D2F
0x180009c4c  jnz     loc_180009D3C
0x180009c52  mov     dword ptr [rbx+660h], 33h ; '3'
0x180009c5c  mov     [rsp+0C8h+var_10], 0
0x180009c68  lea     rcx, [rbx+28h]
0x180009c6c  lea     rdx, [rbx+708h]
0x180009c73  or      r8d, 0FFFFFFFFh
0x180009c77  mov     [rsp+0C8h+var_28], r8d
0x180009c7f  mov     eax, [rbx+6A8h]
0x180009c85  mov     [rsp+0C8h+var_30], eax
0x180009c8c  mov     [rsp+0C8h+var_48], 2
0x180009c97  mov     [rsp+0C8h+var_50], rcx
0x180009c9c  mov     [rsp+0C8h+var_58], r8d
0x180009ca1  mov     [rsp+0C8h+var_60], r8d
0x180009ca6  mov     [rsp+0C8h+var_68], 1
0x180009cae  lea     rax, aMbproperty; "MBProperty"
0x180009cb5  mov     [rsp+0C8h+var_70], rax
0x180009cba  mov     [rsp+0C8h+var_78], 0Eh
0x180009cc2  mov     [rsp+0C8h+var_80], 0
0x180009ccb  mov     [rsp+0C8h+var_88], 0
0x180009cd4  mov     [rsp+0C8h+var_90], 0
0x180009cdd  mov     [rsp+0C8h+var_98], rcx
0x180009ce2  mov     [rsp+0C8h+var_A0], 0C00210E9h
0x180009cea  mov     [rsp+0C8h+var_A8], 2
0x180009cf2  mov     r9d, 80210523h
0x180009cf8  mov     r8, [rbx+6B0h]
0x180009cff  lea     rcx, [rsp+0C8h+var_18]
0x180009d07  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180009d0c  nop
0x180009d0d  mov     r9d, [rbx+67Ch]; unsigned int
0x180009d14  mov     r8d, 0A4h; unsigned int
0x180009d1a  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x180009d21  lea     rcx, [rsp+0C8h+var_18]; this
0x180009d29  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180009d2e  nop
0x180009d2f  lea     rcx, [rsp+0C8h+var_18]; this
0x180009d37  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180009d3c  mov     eax, 1
0x180009d41  add     rsp, 0C0h
0x180009d48  pop     rbx
0x180009d49  retn
0x180009d4a  cmp     eax, 2
0x180009d4d  jz      short loc_180009D5D
0x180009d4f  mov     eax, 80210511h
0x180009d54  add     rsp, 0C0h
0x180009d5b  pop     rbx
0x180009d5c  retn
0x180009d5d  test    [rsp+0C8h+arg_28], 2000000h
0x180009d68  jnz     short loc_180009D82
0x180009d6a  cmp     edx, 5
0x180009d6d  jz      short loc_180009D82
0x180009d6f  mov     edx, r10d; unsigned int
0x180009d72  mov     rcx, rbx; this
0x180009d75  add     rsp, 0C0h
0x180009d7c  pop     rbx
0x180009d7d  jmp     ?GetColumnValue_String@TMetabase_XMLtable@@AEAAJKPEBGK@Z; TMetabase_XMLtable::GetColumnValue_String(ulong,ushort const *,ulong)
0x180009d82  mov     edx, r10d; unsigned int
0x180009d85  mov     rcx, rbx; this
0x180009d88  add     rsp, 0C0h
0x180009d8f  pop     rbx
0x180009d90  jmp     ?GetColumnValue_MultiSZ@TMetabase_XMLtable@@AEAAJKPEBGK@Z; TMetabase_XMLtable::GetColumnValue_MultiSZ(ulong,ushort const *,ulong)
0x180009d95  mov     eax, 80004005h
0x180009d9a  add     rsp, 0C0h
0x180009da1  pop     rbx
0x180009da2  retn
0x180009da3  mov     edx, r10d; unsigned int
0x180009da6  mov     rcx, rbx; this
0x180009da9  test    byte ptr [rsp+0C8h+arg_28], 20h
0x180009db1  jz      short loc_180009DC0
0x180009db3  add     rsp, 0C0h
0x180009dba  pop     rbx
0x180009dbb  jmp     ?GetColumnValue_Bool@TMetabase_XMLtable@@AEAAJKPEBGK@Z; TMetabase_XMLtable::GetColumnValue_Bool(ulong,ushort const *,ulong)
0x180009dc0  add     rsp, 0C0h
0x180009dc7  pop     rbx
0x180009dc8  jmp     ?GetColumnValue_UI4@TMetabase_XMLtable@@AEAAJKPEBGK@Z; TMetabase_XMLtable::GetColumnValue_UI4(ulong,ushort const *,ulong)
```
