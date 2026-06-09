# TMetabase_XMLtable::AddCommentRow(void)

- ea: `0x180005cb8`
- end: `0x180005fad`
- name: `?AddCommentRow@TMetabase_XMLtable@@AEAAJXZ`
- size: `757`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006750`

## callees

- `0x180002bc4`
- `0x180005cb8`
- `0x180006310`
- `0x180009acc`
- `0x18000c9d4`
- `0x180011b38`
- `0x180012734`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## string_xrefs

- `0x180005e0c`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x180005d17`: `CollectionComment`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TMetabase_XMLtable::AddCommentRow(TMetabase_XMLtable *this)
{
  unsigned int *v2; // rsi
  _QWORD *v3; // rdi
  __int64 result; // rax
  TMetabase_XMLtable *v5; // rcx
  unsigned int v6; // edx
  const unsigned __int16 *v7; // r8
  __int64 v8; // r9
  __int64 v9; // [rsp+88h] [rbp-A8h]
  __int64 v10; // [rsp+90h] [rbp-A0h]
  unsigned int v11; // [rsp+B0h] [rbp-80h] BYREF
  unsigned int v12; // [rsp+B4h] [rbp-7Ch] BYREF
  _BYTE v13[8]; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v14; // [rsp+C0h] [rbp-70h]
  _BYTE v15[16]; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v16; // [rsp+E0h] [rbp-50h]
  __int64 v17; // [rsp+138h] [rbp+8h]
  __int64 v18; // [rsp+140h] [rbp+10h]
  __int64 v19; // [rsp+148h] [rbp+18h]
  int v20; // [rsp+168h] [rbp+38h]
  int v21; // [rsp+170h] [rbp+40h]
  int v22; // [rsp+174h] [rbp+44h]
  int v23; // [rsp+178h] [rbp+48h]

  v2 = (unsigned int *)((char *)this + 1664);
  v3 = (_QWORD *)((char *)this + 2040);
  if ( *((_DWORD *)this + 416) == -1
    && (*((_QWORD *)this + 258) = **((_QWORD **)this + 196),
        *((_QWORD *)this + 260) = L"CollectionComment",
        (*(int (__fastcall **)(_QWORD, _QWORD, __int64, char *, _QWORD, char *, unsigned int *))(*(_QWORD *)*v3 + 56LL))(
          *v3,
          0,
          2,
          (char *)this + 2048,
          0,
          (char *)this + 2064,
          v2) < 0) )
  {
    v14 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v13,
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
      v9,
      v10,
      *((_DWORD *)this + 426),
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v13,
      L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
      2239,
      *((_DWORD *)this + 415));
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v13);
    return 2149648482LL;
  }
  else
  {
    memset_0(v15, 0, 0x90u);
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v3 + 32LL))(*v3, *v2, 18);
    if ( (int)result >= 0 )
    {
      v6 = TMetabase_XMLtable::MetabaseTypeFromColumnMetaType(v5, (struct tCOLUMNMETARow *)v15);
      v12 = v6;
      *((_QWORD *)this + 101) = v16;
      *((_QWORD *)this + 102) = &v12;
      *((_DWORD *)this + 321) = v21;
      *((_QWORD *)this + 103) = v19;
      *((_DWORD *)this + 322) = v20;
      *((_QWORD *)this + 106) = v17;
      *((_DWORD *)this + 325) = v22;
      *((_QWORD *)this + 107) = v18;
      *((_DWORD *)this + 326) = v23;
      v7 = (const unsigned __int16 *)*((_QWORD *)this + 220);
      v8 = -1;
      do
        ++v8;
      while ( v7[v8] );
      result = TMetabase_XMLtable::FillInColumn(this, 3u, v7, v8, v6, 0, 0);
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result == 1 )
          return 0;
      }
      else
      {
        v11 = 0;
        result = (*(__int64 (__fastcall **)(TMetabase_XMLtable *, unsigned int *))(*(_QWORD *)this + 72LL))(this, &v11);
        if ( (int)result >= 0 )
        {
          result = (*(__int64 (__fastcall **)(TMetabase_XMLtable *, _QWORD, __int64))(*(_QWORD *)this + 88LL))(
                     this,
                     v11,
                     9);
          if ( (int)result >= 0 )
          {
            result = TMetabase_XMLtable::AddPropertyToLocationMapping(
                       this,
                       *((const unsigned __int16 **)this + 105),
                       v11);
            if ( (int)result >= 0 )
            {
              **((_WORD **)this + 220) = 0;
              return 0;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005cb8  mov     [rsp-8+arg_8], rbx
0x180005cbd  mov     [rsp-8+arg_10], rsi
0x180005cc2  push    rbp
0x180005cc3  push    rdi
0x180005cc4  push    r14
0x180005cc6  lea     rbp, [rsp-90h]
0x180005cce  sub     rsp, 1C0h
0x180005cd5  mov     rax, cs:__security_cookie
0x180005cdc  xor     rax, rsp
0x180005cdf  mov     [rbp+0A0h+var_20], rax
0x180005ce6  mov     rbx, rcx
0x180005ce9  lea     rsi, [rcx+680h]
0x180005cf0  lea     rdi, [rcx+7F8h]
0x180005cf7  xor     r14d, r14d
0x180005cfa  cmp     dword ptr [rsi], 0FFFFFFFFh
0x180005cfd  jnz     loc_180005E2D
0x180005d03  lea     rdx, [rcx+810h]
0x180005d0a  mov     rax, [rcx+620h]
0x180005d11  mov     rcx, [rax]
0x180005d14  mov     [rdx], rcx
0x180005d17  lea     rax, aCollectioncomm; "CollectionComment"
0x180005d1e  mov     [rbx+820h], rax
0x180005d25  mov     rcx, [rdi]
0x180005d28  mov     rax, [rcx]
0x180005d2b  lea     r9, [rbx+800h]
0x180005d32  mov     qword ptr [rsp+1D0h+var_1A0], rsi
0x180005d37  mov     qword ptr [rsp+1D0h+var_1A8], rdx
0x180005d3c  mov     qword ptr [rsp+1D0h+var_1B0], r14
0x180005d41  xor     edx, edx
0x180005d43  lea     r8d, [r14+2]
0x180005d47  mov     rax, [rax+38h]
0x180005d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d50  test    eax, eax
0x180005d52  jns     loc_180005E2D
0x180005d58  mov     [rbp+0A0h+var_110], r14
0x180005d5c  lea     rcx, [rbx+28h]
0x180005d60  lea     rdx, [rbx+708h]
0x180005d67  mov     [rsp+1D0h+var_130], 0FFFFFFFFh
0x180005d72  mov     eax, [rbx+6A8h]
0x180005d78  mov     [rsp+1D0h+var_138], eax
0x180005d7f  mov     [rsp+1D0h+var_150], 1
0x180005d8a  mov     [rsp+1D0h+var_158], rcx
0x180005d8f  mov     [rsp+1D0h+var_160], 0FFFFFFFFh
0x180005d97  mov     [rsp+1D0h+var_168], 0FFFFFFFFh
0x180005d9f  mov     [rsp+1D0h+var_170], 1
0x180005da7  lea     rax, aMbproperty; "MBProperty"
0x180005dae  mov     [rsp+1D0h+var_178], rax
0x180005db3  mov     [rsp+1D0h+var_180], 0Eh
0x180005dbb  mov     [rsp+1D0h+var_188], r14
0x180005dc0  mov     [rsp+1D0h+var_190], r14
0x180005dc5  mov     [rsp+1D0h+var_198], r14
0x180005dca  mov     rax, [rbx+820h]
0x180005dd1  mov     qword ptr [rsp+1D0h+var_1A0], rax
0x180005dd6  mov     [rsp+1D0h+var_1A8], 800210BDh
0x180005dde  mov     [rsp+1D0h+var_1B0], 2
0x180005de6  mov     edi, 80210862h
0x180005deb  mov     r9d, edi
0x180005dee  mov     r8, [rbx+6B0h]
0x180005df5  lea     rcx, [rbp+0A0h+var_118]
0x180005df9  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180005dfe  nop
0x180005dff  mov     r9d, [rbx+67Ch]; unsigned int
0x180005e06  mov     r8d, 8BFh; unsigned int
0x180005e0c  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x180005e13  lea     rcx, [rbp+0A0h+var_118]; this
0x180005e17  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180005e1c  nop
0x180005e1d  lea     rcx, [rbp+0A0h+var_118]; this
0x180005e21  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180005e26  mov     eax, edi
0x180005e28  jmp     loc_180005F86
0x180005e2d  xor     edx, edx; Val
0x180005e2f  mov     r8d, 90h; Size
0x180005e35  lea     rcx, [rbp+0A0h+var_100]; void *
0x180005e39  call    memset_0
0x180005e3e  mov     rcx, [rdi]
0x180005e41  mov     rax, [rcx]
0x180005e44  lea     rdx, [rbp+0A0h+var_100]
0x180005e48  mov     qword ptr [rsp+1D0h+var_1A8], rdx
0x180005e4d  lea     rdx, [rbp+0A0h+var_70]
0x180005e51  mov     qword ptr [rsp+1D0h+var_1B0], rdx
0x180005e56  xor     r9d, r9d
0x180005e59  lea     r8d, [r9+12h]
0x180005e5d  mov     edx, [rsi]
0x180005e5f  mov     rax, [rax+20h]
0x180005e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e68  test    eax, eax
0x180005e6a  js      loc_180005F86
0x180005e70  lea     rdx, [rbp+0A0h+var_100]; struct tCOLUMNMETARow *
0x180005e74  call    ?MetabaseTypeFromColumnMetaType@TMetabase_XMLtable@@AEBAKAEAUtCOLUMNMETARow@@@Z; TMetabase_XMLtable::MetabaseTypeFromColumnMetaType(tCOLUMNMETARow &)
0x180005e79  mov     edx, eax
0x180005e7b  mov     [rbp+0A0h+var_11C], eax
0x180005e7e  lea     rdi, [rbx+328h]
0x180005e85  mov     rcx, [rbp+0A0h+var_F0]
0x180005e89  mov     [rdi], rcx
0x180005e8c  lea     rax, [rbp+0A0h+var_11C]
0x180005e90  mov     [rbx+330h], rax
0x180005e97  mov     ecx, [rbp+0A0h+var_60]
0x180005e9a  mov     [rbx+504h], ecx
0x180005ea0  mov     rcx, [rbp+0A0h+var_88]
0x180005ea4  mov     [rbx+338h], rcx
0x180005eab  mov     ecx, [rbp+0A0h+var_68]
0x180005eae  mov     [rbx+508h], ecx
0x180005eb4  mov     rcx, [rbp+0A0h+var_98]
0x180005eb8  mov     [rbx+350h], rcx
0x180005ebf  mov     eax, [rbp+0A0h+var_5C]
0x180005ec2  mov     [rbx+514h], eax
0x180005ec8  mov     rax, [rbp+0A0h+var_90]
0x180005ecc  mov     [rbx+358h], rax
0x180005ed3  mov     eax, [rbp+0A0h+var_58]
0x180005ed6  mov     [rbx+518h], eax
0x180005edc  mov     r8, [rbx+6E0h]; unsigned __int16 *
0x180005ee3  or      r9, 0FFFFFFFFFFFFFFFFh
0x180005ee7  inc     r9; unsigned int
0x180005eea  cmp     [r8+r9*2], r14w
0x180005eef  jnz     short loc_180005EE7
0x180005ef1  mov     [rsp+1D0h+var_1A0], r14b; bool
0x180005ef6  mov     [rsp+1D0h+var_1A8], r14d; unsigned int
0x180005efb  mov     [rsp+1D0h+var_1B0], edx; unsigned int
0x180005eff  mov     edx, 3; unsigned int
0x180005f04  mov     rcx, rbx; this
0x180005f07  call    ?FillInColumn@TMetabase_XMLtable@@AEAAJKPEBGKKK_N@Z; TMetabase_XMLtable::FillInColumn(ulong,ushort const *,ulong,ulong,ulong,bool)
0x180005f0c  test    eax, eax
0x180005f0e  jz      short loc_180005F19
0x180005f10  cmp     eax, 1
0x180005f13  cmovz   eax, r14d
0x180005f17  jmp     short loc_180005F86
0x180005f19  mov     [rbp+0A0h+var_120], r14d
0x180005f1d  mov     rax, [rbx]
0x180005f20  lea     rdx, [rbp+0A0h+var_120]
0x180005f24  mov     rcx, rbx
0x180005f27  mov     rax, [rax+48h]
0x180005f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f30  test    eax, eax
0x180005f32  js      short loc_180005F86
0x180005f34  mov     rax, [rbx]
0x180005f37  lea     rcx, [rbx+500h]
0x180005f3e  mov     qword ptr [rsp+1D0h+var_1A8], rdi
0x180005f43  mov     qword ptr [rsp+1D0h+var_1B0], rcx
0x180005f48  xor     r9d, r9d
0x180005f4b  lea     r8d, [r9+9]
0x180005f4f  mov     edx, [rbp+0A0h+var_120]
0x180005f52  mov     rcx, rbx
0x180005f55  mov     rax, [rax+58h]
0x180005f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f5e  test    eax, eax
0x180005f60  js      short loc_180005F86
0x180005f62  mov     r8d, [rbp+0A0h+var_120]; unsigned int
0x180005f66  mov     rdx, [rbx+348h]; unsigned __int16 *
0x180005f6d  mov     rcx, rbx; this
0x180005f70  call    ?AddPropertyToLocationMapping@TMetabase_XMLtable@@AEAAJPEBGK@Z; TMetabase_XMLtable::AddPropertyToLocationMapping(ushort const *,ulong)
0x180005f75  test    eax, eax
0x180005f77  js      short loc_180005F86
0x180005f79  mov     rcx, [rbx+6E0h]
0x180005f80  mov     [rcx], r14w
0x180005f84  xor     eax, eax
0x180005f86  mov     rcx, [rbp+0A0h+var_20]
0x180005f8d  xor     rcx, rsp; StackCookie
0x180005f90  call    __security_check_cookie
0x180005f95  lea     r11, [rsp+1D0h+var_10]
0x180005f9d  mov     rbx, [r11+28h]
0x180005fa1  mov     rsi, [r11+30h]
0x180005fa5  mov     rsp, r11
0x180005fa8  pop     r14
0x180005faa  pop     rdi
0x180005fab  pop     rbp
0x180005fac  retn
```
