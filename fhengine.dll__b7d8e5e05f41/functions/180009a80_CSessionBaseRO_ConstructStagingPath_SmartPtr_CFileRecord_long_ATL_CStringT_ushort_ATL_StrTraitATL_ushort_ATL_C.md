# CSessionBaseRO::ConstructStagingPath(SmartPtr<CFileRecord>,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180009a80`
- end: `0x180009d67`
- name: `?ConstructStagingPath@CSessionBaseRO@@IEAAJV?$SmartPtr@VCFileRecord@@@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `743`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _QWORD *)`
- caller_count: `6`
- callee_count: `12`
- tags: ``

## callers

- `0x18000c450`
- `0x18000cafc`
- `0x18000f728`
- `0x180012b44`
- `0x180013e14`
- `0x180024170`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x180007a9c`
- `0x18000815c`
- `0x1800091a4`
- `0x1800092d0`
- `0x18000935c`
- `0x180009694`
- `0x180009920`
- `0x180009a80`
- `0x18000a1ec`
- `0x180028280`

## pseudocode

```c
__int64 __fastcall CSessionBaseRO::ConstructStagingPath(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4)
{
  int Name; // edi
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rbx
  int *v12; // rsi
  __int64 v13; // rbx
  _QWORD *v14; // rcx
  _QWORD *v15; // rcx
  int *v16; // rsi
  __int64 v17; // r13
  __int64 v19; // [rsp+30h] [rbp-58h] BYREF
  __int64 v20; // [rsp+40h] [rbp-48h] BYREF
  __int64 v21; // [rsp+48h] [rbp-40h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-38h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v20);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v21);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v22);
  Name = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    v22,
    L"%d",
    a3);
  v9 = *(_QWORD *)ATL::operator+(&v19, a1 + 48, v22);
  v10 = (_QWORD *)(v9 - 24);
  v11 = v20;
  v12 = (int *)(v20 - 24);
  if ( v9 - 24 != v20 - 24 )
  {
    if ( v12[4] >= 0 && *v10 == *(_QWORD *)v12 )
    {
      v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v10);
      ATL::CStringData::Release((ATL::CStringData *)v12);
      v11 = v13 + 24;
      v20 = v11;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v20, v9, *(unsigned int *)(v9 - 16));
      v11 = v20;
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
  v14 = *(_QWORD **)a2;
  if ( *(_QWORD *)a2 && *v14 )
  {
    Name = CFileRecord::GetName(*v14, &v21);
    if ( Name >= 0 )
    {
      Name = FhePathOperations::ConstructStagingPath(
               (unsigned int)&v20,
               (unsigned int)&v21,
               *(_DWORD *)(**(_QWORD **)a2 + 32LL),
               *(_DWORD *)(**(_QWORD **)a2 + 36LL),
               (__int64)a4);
      if ( Name < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          WPP_f93405c69d16307d22252aee29235708_Traceguids,
          *(unsigned int *)(**(_QWORD **)a2 + 16LL),
          Name);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        WPP_f93405c69d16307d22252aee29235708_Traceguids,
        *(unsigned int *)(**(_QWORD **)a2 + 16LL),
        Name);
    }
  }
  else
  {
    v15 = (_QWORD *)(v11 - 24);
    v16 = (int *)(*a4 - 24LL);
    if ( (int *)(v11 - 24) != v16 )
    {
      if ( v16[4] >= 0 && *v15 == *(_QWORD *)v16 )
      {
        v17 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v15);
        ATL::CStringData::Release((ATL::CStringData *)v16);
        *a4 = v17 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a4, v11, *(unsigned int *)(v11 - 16));
      }
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v22[0] - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(a2);
  return (unsigned int)Name;
}

```

## disassembly

```asm
0x180009a80  mov     rax, rsp
0x180009a83  mov     [rax+8], rbx
0x180009a87  mov     [rax+20h], rsi
0x180009a8b  mov     [rax+18h], r8d
0x180009a8f  mov     [rax+10h], rdx
0x180009a93  push    rdi
0x180009a94  push    r12
0x180009a96  push    r13
0x180009a98  push    r14
0x180009a9a  push    r15
0x180009a9c  sub     rsp, 60h
0x180009aa0  mov     r15, r9
0x180009aa3  mov     r12d, r8d
0x180009aa6  mov     r14, rdx
0x180009aa9  mov     rbx, rcx
0x180009aac  lea     rcx, [rax-48h]
0x180009ab0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180009ab5  nop
0x180009ab6  lea     rcx, [rsp+88h+var_40]
0x180009abb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180009ac0  nop
0x180009ac1  lea     rcx, [rsp+88h+var_38]
0x180009ac6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180009acb  nop
0x180009acc  xor     edi, edi
0x180009ace  mov     r8d, r12d
0x180009ad1  lea     rdx, aD; "%d"
0x180009ad8  lea     rcx, [rsp+88h+var_38]
0x180009add  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180009ae2  lea     rdx, [rbx+30h]
0x180009ae6  lea     r8, [rsp+88h+var_38]
0x180009aeb  lea     rcx, [rsp+88h+var_58]
0x180009af0  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180009af5  nop
0x180009af6  mov     rdx, [rax]
0x180009af9  lea     rcx, [rdx-18h]
0x180009afd  mov     rbx, [rsp+88h+var_48]
0x180009b02  lea     rsi, [rbx-18h]
0x180009b06  cmp     rcx, rsi
0x180009b09  jz      short loc_180009B46
0x180009b0b  cmp     [rsi+10h], edi
0x180009b0e  jl      short loc_180009B33
0x180009b10  mov     rax, [rsi]
0x180009b13  cmp     [rcx], rax
0x180009b16  jnz     short loc_180009B33
0x180009b18  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180009b1d  mov     rbx, rax
0x180009b20  mov     rcx, rsi; this
0x180009b23  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009b28  add     rbx, 18h
0x180009b2c  mov     [rsp+88h+var_48], rbx
0x180009b31  jmp     short loc_180009B46
0x180009b33  mov     r8d, [rdx-10h]
0x180009b37  lea     rcx, [rsp+88h+var_48]
0x180009b3c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180009b41  mov     rbx, [rsp+88h+var_48]
0x180009b46  mov     rcx, [rsp+88h+var_58]
0x180009b4b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180009b4f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009b54  mov     rcx, [r14]
0x180009b57  test    rcx, rcx
0x180009b5a  jz      loc_180009C2F
0x180009b60  cmp     qword ptr [rcx], 0
0x180009b64  jz      loc_180009C2F
0x180009b6a  lea     rdx, [rsp+88h+var_40]
0x180009b6f  mov     rcx, [rcx]
0x180009b72  call    ?GetName@CFileRecord@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CFileRecord::GetName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180009b77  mov     edi, eax
0x180009b79  test    eax, eax
0x180009b7b  jns     short loc_180009BC0
0x180009b7d  lea     rcx, WPP_GLOBAL_Control
0x180009b84  mov     r10, cs:WPP_GLOBAL_Control
0x180009b8b  cmp     r10, rcx
0x180009b8e  jz      short loc_180009BBB
0x180009b90  test    byte ptr [r10+1Ch], 1
0x180009b95  jz      short loc_180009BBB
0x180009b97  mov     rax, [r14]
0x180009b9a  mov     r9, [rax]
0x180009b9d  mov     edx, 2Eh ; '.'
0x180009ba2  mov     dword ptr [rsp+88h+var_68], edi
0x180009ba6  mov     r9d, [r9+10h]
0x180009baa  lea     r8, WPP_f93405c69d16307d22252aee29235708_Traceguids
0x180009bb1  mov     rcx, [r10+10h]
0x180009bb5  call    WPP_SF_dd
0x180009bba  nop
0x180009bbb  jmp     loc_180009D1B
0x180009bc0  mov     rax, [r14]
0x180009bc3  mov     r8, [rax]
0x180009bc6  mov     [rsp+88h+var_68], r15
0x180009bcb  mov     r9d, [r8+24h]
0x180009bcf  mov     r8d, [r8+20h]
0x180009bd3  lea     rdx, [rsp+88h+var_40]
0x180009bd8  lea     rcx, [rsp+88h+var_48]
0x180009bdd  call    ?ConstructStagingPath@FhePathOperations@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0JJAEAV23@@Z; FhePathOperations::ConstructStagingPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180009be2  mov     edi, eax
0x180009be4  test    eax, eax
0x180009be6  jns     loc_180009C76
0x180009bec  lea     rcx, WPP_GLOBAL_Control
0x180009bf3  mov     r10, cs:WPP_GLOBAL_Control
0x180009bfa  cmp     r10, rcx
0x180009bfd  jz      short loc_180009C2A
0x180009bff  test    byte ptr [r10+1Ch], 1
0x180009c04  jz      short loc_180009C2A
0x180009c06  mov     rax, [r14]
0x180009c09  mov     r9, [rax]
0x180009c0c  mov     edx, 2Fh ; '/'
0x180009c11  mov     dword ptr [rsp+88h+var_68], edi
0x180009c15  mov     r9d, [r9+10h]
0x180009c19  lea     r8, WPP_f93405c69d16307d22252aee29235708_Traceguids
0x180009c20  mov     rcx, [r10+10h]
0x180009c24  call    WPP_SF_dd
0x180009c29  nop
0x180009c2a  jmp     loc_180009D1B
0x180009c2f  lea     rcx, [rbx-18h]
0x180009c33  mov     rsi, [r15]
0x180009c36  add     rsi, 0FFFFFFFFFFFFFFE8h
0x180009c3a  cmp     rcx, rsi
0x180009c3d  jz      short loc_180009C76
0x180009c3f  cmp     dword ptr [rsi+10h], 0
0x180009c43  jl      short loc_180009C66
0x180009c45  mov     rax, [rsi]
0x180009c48  cmp     [rcx], rax
0x180009c4b  jnz     short loc_180009C66
0x180009c4d  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180009c52  mov     r13, rax
0x180009c55  mov     rcx, rsi; this
0x180009c58  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009c5d  lea     rax, [r13+18h]
0x180009c61  mov     [r15], rax
0x180009c64  jmp     short loc_180009C76
0x180009c66  mov     r8d, [rbx-10h]
0x180009c6a  mov     rdx, rbx
0x180009c6d  mov     rcx, r15
0x180009c70  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180009c75  nop
0x180009c76  jmp     short loc_180009C91
0x180009c78  mov     r12d, [rsp+88h+arg_10]
0x180009c80  mov     r14, [rsp+88h+arg_8]
0x180009c88  mov     rbx, [rsp+88h+var_48]
0x180009c8d  mov     edi, dword ptr [rsp+88h+var_58]
0x180009c91  mov     rax, [r14]
0x180009c94  test    rax, rax
0x180009c97  jz      short loc_180009CE1
0x180009c99  cmp     qword ptr [rax], 0
0x180009c9d  jz      short loc_180009CE1
0x180009c9f  test    edi, edi
0x180009ca1  jns     short loc_180009D1B
0x180009ca3  lea     rcx, WPP_GLOBAL_Control
0x180009caa  mov     rax, cs:WPP_GLOBAL_Control
0x180009cb1  cmp     rax, rcx
0x180009cb4  jz      short loc_180009D1B
0x180009cb6  test    byte ptr [rax+1Ch], 1
0x180009cba  jz      short loc_180009D1B
0x180009cbc  mov     edx, 30h ; '0'
0x180009cc1  mov     [rsp+88h+var_60], edi
0x180009cc5  mov     dword ptr [rsp+88h+var_68], r12d
0x180009cca  mov     r9, [rsp+88h+var_40]
0x180009ccf  lea     r8, WPP_f93405c69d16307d22252aee29235708_Traceguids
0x180009cd6  mov     rcx, [rax+10h]
0x180009cda  call    WPP_SF_Sdd
0x180009cdf  jmp     short loc_180009D1B
0x180009ce1  test    edi, edi
0x180009ce3  jns     short loc_180009D1B
0x180009ce5  lea     rcx, WPP_GLOBAL_Control
0x180009cec  mov     rax, cs:WPP_GLOBAL_Control
0x180009cf3  cmp     rax, rcx
0x180009cf6  jz      short loc_180009D1B
0x180009cf8  test    byte ptr [rax+1Ch], 1
0x180009cfc  jz      short loc_180009D1B
0x180009cfe  mov     edx, 31h ; '1'
0x180009d03  mov     dword ptr [rsp+88h+var_68], edi
0x180009d07  mov     r9d, r12d
0x180009d0a  lea     r8, WPP_f93405c69d16307d22252aee29235708_Traceguids
0x180009d11  mov     rcx, [rax+10h]
0x180009d15  call    WPP_SF_dd
0x180009d1a  nop
0x180009d1b  mov     rcx, [rsp+88h+var_38]
0x180009d20  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180009d24  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009d29  nop
0x180009d2a  mov     rcx, [rsp+88h+var_40]
0x180009d2f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180009d33  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009d38  nop
0x180009d39  lea     rcx, [rbx-18h]; this
0x180009d3d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009d42  nop
0x180009d43  mov     rcx, r14
0x180009d46  call    ??1?$SmartPtr@VCFileRecord@@@@QEAA@XZ; SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(void)
0x180009d4b  mov     eax, edi
0x180009d4d  lea     r11, [rsp+88h+var_28]
0x180009d52  mov     rbx, [r11+30h]
0x180009d56  mov     rsi, [r11+48h]
0x180009d5a  mov     rsp, r11
0x180009d5d  pop     r15
0x180009d5f  pop     r14
0x180009d61  pop     r13
0x180009d63  pop     r12
0x180009d65  pop     rdi
0x180009d66  retn
```
