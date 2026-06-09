# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180003dbc`
- end: `0x1800041af`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1011`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180007e04`

## callees

- `0x180002340`
- `0x180002b00`
- `0x1800030dc`
- `0x180003dbc`
- `0x1800041b8`
- `0x18000450c`
- `0x180004d74`
- `0x1800072f0`
- `0x1800086a8`
- `0x1800087c4`
- `0x18002b472`
- `0x18002b4a0`
- `0x18002b560`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180003e36`
- `KERNEL32!lstrcmpiW` at `0x180003e36`
- `ADVAPI32!RegSetValueExW` at `0x180003fea`
- `ADVAPI32!RegSetValueExW` at `0x180004113`
- `ADVAPI32!RegSetValueExW` at `0x180004163`
- `ADVAPI32!RegSetValueExW` at `0x180003fea`
- `ADVAPI32!RegSetValueExW` at `0x180004113`
- `ADVAPI32!RegSetValueExW` at `0x180004163`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003fa4`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003fa4`
- `USER32!CharNextW` at `0x180003f25`
- `USER32!CharNextW` at `0x180003f40`
- `USER32!CharNextW` at `0x180003f25`
- `USER32!CharNextW` at `0x180003f40`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const WCHAR *v4; // r12
  HKEY *v5; // r15
  ATL::CRegParser *v6; // r13
  __int64 result; // rax
  unsigned int v8; // ebx
  int v9; // edi
  __int16 v10; // di
  __int64 v11; // rdi
  unsigned __int64 v12; // rax
  BYTE *v13; // rdi
  WCHAR *i; // rsi
  const WCHAR *v15; // rax
  LSTATUS v16; // edi
  HRESULT v17; // edi
  __int64 v18; // rdi
  DWORD cbData; // esi
  size_t v20; // r14
  unsigned __int64 v21; // rax
  BYTE *v22; // rcx
  int j; // r10d
  unsigned __int8 v24; // al
  int v25; // r10d
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-2198h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-2190h] BYREF
  ATL::CRegParser *v32; // [rsp+40h] [rbp-2188h] BYREF
  struct ATL::CRegKey *v33; // [rsp+48h] [rbp-2180h]
  const unsigned __int16 *v34; // [rsp+50h] [rbp-2178h]
  size_t v35; // [rsp+60h] [rbp-2168h]
  unsigned __int16 *v36; // [rsp+68h] [rbp-2160h]
  BYTE *lpData; // [rsp+70h] [rbp-2158h] BYREF
  _BYTE v38[264]; // [rsp+78h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+180h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v32 = this;
  v33 = (struct ATL::CRegKey *)a2;
  v34 = a3;
  v36 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  v8 = 0;
  if ( (int)result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return 2147614729LL;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    ATL::CRegParser::SkipWhiteSpace(v6);
    result = ATL::CRegParser::NextToken(v6, String1);
    if ( (int)result >= 0 )
    {
      if ( v10 == 8 )
      {
        v28 = -1;
        do
          ++v28;
        while ( String1[v28] );
        v16 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v28 + 2);
        goto LABEL_46;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v32 = 0;
          v17 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v17 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
            return (unsigned int)v17;
          }
          *(_DWORD *)Data = pulOut;
          v16 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_48:
            Token = ATL::CRegParser::NextToken(v6, v36);
            if ( Token < 0 )
              return (unsigned int)Token;
            return v8;
          }
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          lpData = 0;
          try
          {
            v12 = ATL::AtlMultiplyThrow<unsigned __int64>();
            if ( v12 <= 0x100 )
            {
              v13 = v38;
              lpData = v38;
            }
            else
            {
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
              v13 = lpData;
            }
          }
          catch ( ... )
          {
            v8 = 0;
            v13 = lpData;
            v6 = v32;
            v5 = (HKEY *)v33;
            v4 = v34;
          }
          if ( v13 )
          {
            for ( i = String1; *i; v13 += 2 )
            {
              v15 = CharNextW(i);
              if ( *i == 92 && *v15 == 48 )
              {
                *(_WORD *)v13 = 0;
                i = CharNextW(v15);
              }
              else
              {
                *(_WORD *)v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            v16 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)v5, v4, (const unsigned __int16 *)lpData);
          }
          else
          {
            v16 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_46:
        if ( v16 )
          return ATL::AtlHresultFromWin32(v16);
        goto LABEL_48;
      }
      v18 = -1;
      do
        ++v18;
      while ( String1[v18] );
      *(_DWORD *)Data = v18;
      if ( (v18 & 1) == 0 )
      {
        cbData = (int)v18 / 2;
        lpData = 0;
        v20 = (int)v18 / 2;
        v35 = v20;
        try
        {
          v21 = ATL::AtlMultiplyThrow<unsigned __int64>();
          if ( v21 <= 0x100 )
          {
            v22 = v38;
            lpData = v38;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v21);
            v22 = lpData;
          }
        }
        catch ( ... )
        {
          v8 = 0;
          LODWORD(v18) = *(_DWORD *)Data;
          v22 = lpData;
          v20 = v35;
          v6 = v32;
          v5 = (HKEY *)v33;
          v4 = v34;
          cbData = v35;
        }
        if ( v22 )
        {
          memset_0(v22, 0, v20);
          for ( j = 0; j < (int)v18; j = v25 + 1 )
          {
            v24 = ATL::CRegParser::ChToByte(String1[j]);
            *(_BYTE *)(v27 + v26) |= v24 << (4 - 4 * (v25 & 1));
          }
          v16 = RegSetValueExW(*v5, v4, 0, 3u, lpData, cbData);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_46;
        }
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      }
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003dbc  push    rbx
0x180003dbe  push    rsi
0x180003dbf  push    rdi
0x180003dc0  push    r12
0x180003dc2  push    r13
0x180003dc4  push    r14
0x180003dc6  push    r15
0x180003dc8  mov     eax, 2190h
0x180003dcd  call    _alloca_probe
0x180003dd2  sub     rsp, rax
0x180003dd5  mov     rax, cs:__security_cookie
0x180003ddc  xor     rax, rsp
0x180003ddf  mov     [rsp+21C8h+var_48], rax
0x180003de7  mov     r12, r8
0x180003dea  mov     r15, rdx
0x180003ded  mov     r13, rcx
0x180003df0  mov     [rsp+21C8h+var_2188], rcx
0x180003df5  mov     [rsp+21C8h+var_2180], rdx
0x180003dfa  mov     [rsp+21C8h+var_2178], r8
0x180003dff  mov     [rsp+21C8h+var_2160], r9
0x180003e04  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x180003e0c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003e11  xor     ebx, ebx
0x180003e13  test    eax, eax
0x180003e15  js      loc_18000418C
0x180003e1b  mov     edi, ebx
0x180003e1d  lea     r14, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180003e24  movsxd  rsi, edi
0x180003e27  add     rsi, rsi
0x180003e2a  mov     rdx, [r14+rsi*8]; lpString2
0x180003e2e  lea     rcx, [rsp+21C8h+String1]; lpString1
0x180003e36  call    cs:__imp_lstrcmpiW
0x180003e3c  test    eax, eax
0x180003e3e  jz      short loc_180003E51
0x180003e40  inc     edi
0x180003e42  cmp     edi, 4
0x180003e45  jb      short loc_180003E24
0x180003e47  mov     eax, 80020009h
0x180003e4c  jmp     loc_18000418C
0x180003e51  movzx   edi, word ptr [r14+rsi*8+8]
0x180003e57  mov     rcx, r13; this
0x180003e5a  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180003e5f  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x180003e67  mov     rcx, r13; this
0x180003e6a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003e6f  test    eax, eax
0x180003e71  js      loc_18000418C
0x180003e77  cmp     di, 8
0x180003e7b  jz      loc_180004127
0x180003e81  cmp     di, 11h
0x180003e85  jz      loc_180004001
0x180003e8b  cmp     di, 13h
0x180003e8f  jz      loc_180003F89
0x180003e95  mov     eax, 4008h
0x180003e9a  cmp     di, ax
0x180003e9d  jnz     loc_180004178
0x180003ea3  lea     rax, [rsp+21C8h+String1]
0x180003eab  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003eaf  inc     rdi
0x180003eb2  cmp     [rax+rdi*2], bx
0x180003eb6  jnz     short loc_180003EAF
0x180003eb8  add     edi, 2
0x180003ebb  mov     [rsp+21C8h+var_2158], rbx
0x180003ec0  movsxd  rcx, edi
0x180003ec3  mov     edx, 2
0x180003ec8  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180003ecd  cmp     rax, 100h
0x180003ed3  jbe     short loc_180003EE9
0x180003ed5  mov     rdx, rax
0x180003ed8  lea     rcx, [rsp+21C8h+var_2158]
0x180003edd  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003ee2  mov     rdi, [rsp+21C8h+var_2158]
0x180003ee7  jmp     short loc_180003EF3
0x180003ee9  lea     rdi, [rsp+21C8h+var_2150]
0x180003eee  mov     [rsp+21C8h+var_2158], rdi
0x180003ef3  jmp     short loc_180003F0B
0x180003ef5  xor     ebx, ebx
0x180003ef7  mov     rdi, [rsp+21C8h+var_2158]
0x180003efc  mov     r13, [rsp+21C8h+var_2188]
0x180003f01  mov     r15, [rsp+21C8h+var_2180]
0x180003f06  mov     r12, [rsp+21C8h+var_2178]
0x180003f0b  test    rdi, rdi
0x180003f0e  jz      short loc_180003F75
0x180003f10  lea     rsi, [rsp+21C8h+String1]
0x180003f18  cmp     [rsp+21C8h+String1], bx
0x180003f20  jz      short loc_180003F5B
0x180003f22  mov     rcx, rsi; lpsz
0x180003f25  call    cs:__imp_CharNextW
0x180003f2b  movzx   ecx, word ptr [rsi]
0x180003f2e  cmp     cx, 5Ch ; '\'
0x180003f32  jnz     short loc_180003F4B
0x180003f34  cmp     word ptr [rax], 30h ; '0'
0x180003f38  jnz     short loc_180003F4B
0x180003f3a  mov     [rdi], bx
0x180003f3d  mov     rcx, rax; lpsz
0x180003f40  call    cs:__imp_CharNextW
0x180003f46  mov     rsi, rax
0x180003f49  jmp     short loc_180003F52
0x180003f4b  mov     [rdi], cx
0x180003f4e  add     rsi, 2
0x180003f52  add     rdi, 2
0x180003f56  cmp     [rsi], bx
0x180003f59  jnz     short loc_180003F22
0x180003f5b  mov     dword ptr [rdi], 0
0x180003f61  mov     r8, [rsp+21C8h+var_2158]; unsigned __int16 *
0x180003f66  mov     rdx, r12; unsigned __int16 *
0x180003f69  mov     rcx, r15; this
0x180003f6c  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x180003f71  mov     edi, eax
0x180003f73  jmp     short loc_180003F7A
0x180003f75  mov     edi, 0Eh
0x180003f7a  lea     rcx, [rsp+21C8h+var_2158]
0x180003f7f  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180003f84  jmp     loc_18000416B
0x180003f89  mov     [rsp+21C8h+pulOut], ebx
0x180003f8d  mov     [rsp+21C8h+var_2188], rbx
0x180003f92  lea     r9, [rsp+21C8h+pulOut]; pulOut
0x180003f97  xor     r8d, r8d; dwFlags
0x180003f9a  xor     edx, edx; lcid
0x180003f9c  lea     rcx, [rsp+21C8h+String1]; strIn
0x180003fa4  call    cs:__imp_VarUI4FromStr
0x180003faa  mov     edi, eax
0x180003fac  test    eax, eax
0x180003fae  jns     short loc_180003FC1
0x180003fb0  lea     rcx, [rsp+21C8h+var_2188]
0x180003fb5  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003fba  mov     eax, edi
0x180003fbc  jmp     loc_18000418C
0x180003fc1  mov     eax, [rsp+21C8h+pulOut]
0x180003fc5  mov     dword ptr [rsp+21C8h+Data], eax
0x180003fc9  mov     [rsp+21C8h+cbData], 4; cbData
0x180003fd1  lea     rax, [rsp+21C8h+Data]
0x180003fd6  mov     [rsp+21C8h+lpData], rax; lpData
0x180003fdb  mov     r9d, 4; dwType
0x180003fe1  xor     r8d, r8d; Reserved
0x180003fe4  mov     rdx, r12; lpValueName
0x180003fe7  mov     rcx, [r15]; hKey
0x180003fea  call    cs:__imp_RegSetValueExW
0x180003ff0  mov     edi, eax
0x180003ff2  lea     rcx, [rsp+21C8h+var_2188]
0x180003ff7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003ffc  jmp     loc_18000416B
0x180004001  lea     rax, [rsp+21C8h+String1]
0x180004009  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000400d  inc     rdi
0x180004010  cmp     [rax+rdi*2], bx
0x180004014  jnz     short loc_18000400D
0x180004016  mov     dword ptr [rsp+21C8h+Data], edi
0x18000401a  test    dil, 1
0x18000401e  jz      short loc_18000402A
0x180004020  mov     eax, 80004005h
0x180004025  jmp     loc_18000418C
0x18000402a  mov     eax, edi
0x18000402c  cdq
0x18000402d  sub     eax, edx
0x18000402f  sar     eax, 1
0x180004031  movsxd  rsi, eax
0x180004034  mov     [rsp+21C8h+var_2158], rbx
0x180004039  mov     r14, rsi
0x18000403c  mov     [rsp+21C8h+var_2168], rsi
0x180004041  mov     edx, 1
0x180004046  mov     rcx, rsi
0x180004049  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000404e  cmp     rax, 100h
0x180004054  jbe     short loc_18000406A
0x180004056  mov     rdx, rax
0x180004059  lea     rcx, [rsp+21C8h+var_2158]
0x18000405e  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004063  mov     rcx, [rsp+21C8h+var_2158]
0x180004068  jmp     short loc_180004074
0x18000406a  lea     rcx, [rsp+21C8h+var_2150]
0x18000406f  mov     [rsp+21C8h+var_2158], rcx
0x180004074  jmp     short loc_180004098
0x180004076  xor     ebx, ebx
0x180004078  mov     edi, dword ptr [rsp+21C8h+Data]
0x18000407c  mov     rcx, [rsp+21C8h+var_2158]; void *
0x180004081  mov     r14, [rsp+21C8h+var_2168]
0x180004086  mov     r13, [rsp+21C8h+var_2188]
0x18000408b  mov     r15, [rsp+21C8h+var_2180]
0x180004090  mov     r12, [rsp+21C8h+var_2178]
0x180004095  mov     esi, r14d
0x180004098  test    rcx, rcx
0x18000409b  jnz     short loc_1800040AC
0x18000409d  lea     rcx, [rsp+21C8h+var_2158]
0x1800040a2  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800040a7  jmp     loc_180004020
0x1800040ac  mov     r8, r14; Size
0x1800040af  xor     edx, edx; Val
0x1800040b1  call    memset_0
0x1800040b6  mov     r10d, ebx
0x1800040b9  test    edi, edi
0x1800040bb  jle     short loc_1800040F6
0x1800040bd  mov     r9d, r10d
0x1800040c0  shr     r9, 1
0x1800040c3  mov     r8, [rsp+21C8h+var_2158]
0x1800040c8  mov     ecx, r10d
0x1800040cb  movzx   ecx, [rsp+rcx*2+21C8h+String1]; unsigned __int16
0x1800040d3  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x1800040d8  mov     edx, r10d
0x1800040db  and     edx, 1
0x1800040de  shl     edx, 2
0x1800040e1  mov     ecx, 4
0x1800040e6  sub     ecx, edx
0x1800040e8  shl     al, cl
0x1800040ea  or      [r9+r8], al
0x1800040ee  inc     r10d
0x1800040f1  cmp     r10d, edi
0x1800040f4  jl      short loc_1800040BD
0x1800040f6  mov     rax, [rsp+21C8h+var_2158]
0x1800040fb  mov     [rsp+21C8h+cbData], esi; cbData
0x1800040ff  mov     [rsp+21C8h+lpData], rax; lpData
0x180004104  mov     r9d, 3; dwType
0x18000410a  xor     r8d, r8d; Reserved
0x18000410d  mov     rdx, r12; lpValueName
0x180004110  mov     rcx, [r15]; hKey
0x180004113  call    cs:__imp_RegSetValueExW
0x180004119  mov     edi, eax
0x18000411b  lea     rcx, [rsp+21C8h+var_2158]
0x180004120  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180004125  jmp     short loc_18000416B
0x180004127  lea     rax, [rsp+21C8h+String1]
0x18000412f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004133  inc     rdi
0x180004136  cmp     [rax+rdi*2], bx
0x18000413a  jnz     short loc_180004133
0x18000413c  lea     eax, ds:2[rdi*2]
0x180004143  mov     [rsp+21C8h+cbData], eax; cbData
0x180004147  lea     rax, [rsp+21C8h+String1]
0x18000414f  mov     [rsp+21C8h+lpData], rax; lpData
0x180004154  mov     r9d, 1; dwType
0x18000415a  xor     r8d, r8d; Reserved
0x18000415d  mov     rdx, r12; lpValueName
0x180004160  mov     rcx, [r15]; hKey
0x180004163  call    cs:__imp_RegSetValueExW
0x180004169  mov     edi, eax
0x18000416b  test    edi, edi
0x18000416d  jz      short loc_180004178
0x18000416f  mov     ecx, edi; unsigned int
0x180004171  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180004176  jmp     short loc_18000418C
0x180004178  mov     rdx, [rsp+21C8h+var_2160]; unsigned __int16 *
0x18000417d  mov     rcx, r13; this
0x180004180  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004185  test    eax, eax
0x180004187  cmovs   ebx, eax
0x18000418a  mov     eax, ebx
0x18000418c  mov     rcx, [rsp+21C8h+var_48]
0x180004194  xor     rcx, rsp; StackCookie
0x180004197  call    __security_check_cookie
0x18000419c  add     rsp, 2190h
0x1800041a3  pop     r15
0x1800041a5  pop     r14
0x1800041a7  pop     r13
0x1800041a9  pop     r12
0x1800041ab  pop     rdi
0x1800041ac  pop     rsi
0x1800041ad  pop     rbx
0x1800041ae  retn
```
