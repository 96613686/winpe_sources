# NgcPasskeys::SyncStore::PdrDataItem::FromCbor(SimpleCbor::Decoder &)

- ea: `0x180052ae8`
- end: `0x180052f03`
- name: `?FromCbor@PdrDataItem@SyncStore@NgcPasskeys@@SA?AU123@AEAVDecoder@SimpleCbor@@@Z`
- size: `1051`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180052f0c`

## callees

- `0x180003080`
- `0x18000ce74`
- `0x18000cfcc`
- `0x180013834`
- `0x18001565c`
- `0x18004ac3c`
- `0x180052698`
- `0x1800526d4`
- `0x180052ae8`
- `0x1800532d0`
- `0x18005385c`
- `0x180053a30`
- `0x180053aac`
- `0x180053c80`

## string_xrefs

- `0x180052b7c`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052be9`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052c11`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052c6a`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052c85`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052ca7`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052ce7`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052d06`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052d43`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052d5f`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052d9e`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052dc9`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`
- `0x180052e06`: `onecore\ds\security\ngc\lockbox\server\lib\syncstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall NgcPasskeys::SyncStore::PdrDataItem::FromCbor(char *a1, __int64 a2)
{
  __int64 v2; // rbx
  char *v3; // rdi
  __int16 v4; // si
  __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // r12
  int v8; // ebx
  int v9; // edi
  int v10; // r14d
  int v11; // r15d
  int v12; // r12d
  int v13; // r13d
  int v14; // esi
  int *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 ByteString; // rax
  __int64 TextWString; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  int v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+44h] [rbp-BCh]
  const char *v32; // [rsp+48h] [rbp-B8h]
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+54h] [rbp-ACh]
  const char *v35; // [rsp+58h] [rbp-A8h]
  char *Uint; // [rsp+60h] [rbp-A0h]
  char *v37; // [rsp+78h] [rbp-88h]
  _DWORD v38[2]; // [rsp+80h] [rbp-80h] BYREF
  const char *v39; // [rsp+88h] [rbp-78h]
  _DWORD v40[2]; // [rsp+90h] [rbp-70h] BYREF
  const char *v41; // [rsp+98h] [rbp-68h]
  _DWORD v42[2]; // [rsp+A0h] [rbp-60h] BYREF
  const char *v43; // [rsp+A8h] [rbp-58h]
  _DWORD v44[2]; // [rsp+B0h] [rbp-50h] BYREF
  const char *v45; // [rsp+B8h] [rbp-48h]
  _DWORD v46[2]; // [rsp+C0h] [rbp-40h] BYREF
  const char *v47; // [rsp+C8h] [rbp-38h]
  _DWORD v48[2]; // [rsp+D0h] [rbp-30h] BYREF
  const char *v49; // [rsp+D8h] [rbp-28h]
  _DWORD v50[2]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v51; // [rsp+E8h] [rbp-18h]
  _DWORD v52[2]; // [rsp+F0h] [rbp-10h] BYREF
  const char *v53; // [rsp+F8h] [rbp-8h]
  __int128 v54; // [rsp+100h] [rbp+0h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h]
  __int128 v56; // [rsp+120h] [rbp+20h] BYREF
  __int64 v57; // [rsp+130h] [rbp+30h]
  __int128 v58; // [rsp+138h] [rbp+38h] BYREF
  __int64 v59; // [rsp+148h] [rbp+48h]
  __int64 v60; // [rsp+150h] [rbp+50h]
  _BYTE v61[32]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v2 = a2;
  v3 = a1;
  v37 = a1;
  Uint = a1;
  v54 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v4 = 0;
  LOWORD(v54) = 0;
  v56 = 0;
  v5 = 0;
  v57 = 0;
  v58 = 0;
  v6 = 0;
  v59 = 0;
  v7 = 7;
  v60 = 7;
  LOWORD(v58) = 0;
  v33 = 41;
  v34 = v31;
  v35 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
  SimpleCbor::Decoder::EnterMap(a2, &v33);
  v33 = 42;
  v34 = v31;
  v35 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
  if ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(v2, &v33) )
  {
    v8 = v31;
    v9 = v31;
    v10 = v31;
    v11 = v31;
    v12 = v31;
    v13 = v31;
    v14 = v31;
    do
    {
      v38[0] = 44;
      v38[1] = v8;
      v39 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
      Uint = (char *)SimpleCbor::Decoder::GetUint(a2, v38);
      v40[0] = 45;
      v40[1] = v9;
      v41 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
      SimpleCbor::Decoder::NextItem(a2, v40);
      if ( Uint == (char *)1 )
      {
        v52[0] = 49;
        v52[1] = v10;
        v53 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
        TextWString = SimpleCbor::Decoder::GetTextWString(a2, v61, v52);
        std::wstring::operator=(&v54, TextWString);
        std::wstring::~wstring(v61, v21, v22);
        v30 = 50;
        v31 = v11;
        v32 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
        v15 = &v30;
      }
      else if ( Uint == (char *)2 )
      {
        v48[0] = 53;
        v48[1] = v12;
        v49 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
        ByteString = SimpleCbor::Decoder::GetByteString(a2, v61, v48);
        std::vector<unsigned char>::operator=(&v56, ByteString);
        std::vector<unsigned char>::~vector<unsigned char>(v61);
        v50[0] = 54;
        v50[1] = v13;
        v51 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
        v15 = v50;
      }
      else if ( Uint == (char *)3 )
      {
        v44[0] = 57;
        v44[1] = v31;
        v45 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
        v16 = SimpleCbor::Decoder::GetTextWString(a2, v61, v44);
        std::wstring::operator=(&v58, v16);
        std::wstring::~wstring(v61, v17, v18);
        v46[0] = 58;
        v46[1] = v31;
        v47 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
        v15 = v46;
      }
      else
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x3E,
          (unsigned int)"onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp",
          (const char *)0x8000FFFFLL,
          (int)"Unknown item in loaded data blob: %llu",
          Uint);
        v42[0] = 63;
        v42[1] = v14;
        v43 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
        v15 = v42;
      }
      SimpleCbor::Decoder::NextItem(a2, v15);
      v33 = 42;
      v34 = v31;
      v35 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
    }
    while ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(a2, &v33) );
    v7 = v60;
    v6 = v59;
    v5 = v57;
    v4 = v54;
    v2 = a2;
    v3 = v37;
  }
  v30 = 66;
  v32 = "onecore\\ds\\security\\ngc\\lockbox\\server\\lib\\syncstore.cpp";
  SimpleCbor::Decoder::LeaveContainer(v2, &v30);
  *(_OWORD *)v3 = 0;
  *(_WORD *)v3 = v4;
  *(_QWORD *)(v3 + 2) = *(_QWORD *)((char *)&v54 + 2);
  *(_DWORD *)(v3 + 10) = *(_DWORD *)((char *)&v54 + 10);
  *((_WORD *)v3 + 7) = HIWORD(v54);
  *((__m128i *)v3 + 1) = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v54) = 0;
  v57 = 0;
  v23 = *((_QWORD *)&v56 + 1);
  v24 = v56;
  v56 = 0u;
  *((_QWORD *)v3 + 4) = v24;
  *((_QWORD *)v3 + 5) = v23;
  *((_QWORD *)v3 + 6) = v5;
  *(_OWORD *)(v3 + 56) = v58;
  *((_QWORD *)v3 + 9) = v6;
  *((_QWORD *)v3 + 10) = v7;
  v59 = 0;
  v60 = 7;
  LOWORD(v58) = 0;
  std::wstring::~wstring(&v58, 0, v25);
  std::vector<unsigned char>::~vector<unsigned char>(&v56);
  std::wstring::~wstring(&v54, v26, v27);
  return v3;
}

```

## disassembly

```asm
0x180052ae8  mov     [rsp-8+arg_10], rbx
0x180052aed  push    rbp
0x180052aee  push    rsi
0x180052aef  push    rdi
0x180052af0  push    r12
0x180052af2  push    r13
0x180052af4  push    r14
0x180052af6  push    r15
0x180052af8  lea     rbp, [rsp-90h]
0x180052b00  sub     rsp, 190h
0x180052b07  mov     rax, cs:__security_cookie
0x180052b0e  xor     rax, rsp
0x180052b11  mov     [rbp+0C0h+var_40], rax
0x180052b18  mov     rbx, rdx
0x180052b1b  mov     [rsp+1C0h+var_190], rdx
0x180052b20  mov     rdi, rcx
0x180052b23  mov     [rsp+1C0h+var_148], rcx
0x180052b28  mov     [rsp+1C0h+var_160], rcx
0x180052b2d  xorps   xmm0, xmm0
0x180052b30  movups  [rbp+0C0h+var_C0], xmm0
0x180052b34  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180052b3c  movdqa  [rbp+0C0h+var_B0], xmm1
0x180052b41  xor     esi, esi
0x180052b43  mov     word ptr [rbp+0C0h+var_C0], si
0x180052b47  movdqa  [rbp+0C0h+var_A0], xmm0
0x180052b4c  xor     r14d, r14d
0x180052b4f  mov     [rbp+0C0h+var_90], r14
0x180052b53  movups  [rbp+0C0h+var_88], xmm0
0x180052b57  xor     r15d, r15d
0x180052b5a  mov     [rbp+0C0h+var_78], r15
0x180052b5e  lea     r12d, [rsi+7]
0x180052b62  mov     [rbp+0C0h+var_70], r12
0x180052b66  xor     eax, eax
0x180052b68  mov     word ptr [rbp+0C0h+var_88], ax
0x180052b6c  mov     [rsp+1C0h+var_170], 29h ; ')'
0x180052b74  mov     eax, [rsp+1C0h+var_17C]
0x180052b78  mov     [rsp+1C0h+var_16C], eax
0x180052b7c  lea     r13, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052b83  mov     [rsp+1C0h+var_168], r13
0x180052b88  lea     rdx, [rsp+1C0h+var_170]
0x180052b8d  mov     rcx, rbx
0x180052b90  call    ?EnterMap@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EnterMap(SimpleCbor::impl::slim_source_location)
0x180052b95  mov     [rsp+1C0h+var_170], 2Ah ; '*'
0x180052b9d  mov     eax, [rsp+1C0h+var_17C]
0x180052ba1  mov     [rsp+1C0h+var_16C], eax
0x180052ba5  mov     [rsp+1C0h+var_168], r13
0x180052baa  lea     rdx, [rsp+1C0h+var_170]
0x180052baf  mov     rcx, rbx
0x180052bb2  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x180052bb7  test    al, al
0x180052bb9  jnz     loc_180052E0D
0x180052bbf  mov     ebx, [rsp+1C0h+var_17C]
0x180052bc3  mov     edi, [rsp+1C0h+var_17C]
0x180052bc7  mov     r14d, [rsp+1C0h+var_17C]
0x180052bcc  mov     r15d, [rsp+1C0h+var_17C]
0x180052bd1  mov     r12d, [rsp+1C0h+var_17C]
0x180052bd6  mov     r13d, [rsp+1C0h+var_17C]
0x180052bdb  mov     esi, [rsp+1C0h+var_17C]
0x180052bdf  mov     [rbp+0C0h+var_140], 2Ch ; ','
0x180052be6  mov     [rbp+0C0h+var_13C], ebx
0x180052be9  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052bf0  mov     [rbp+0C0h+var_138], rax
0x180052bf4  lea     rdx, [rbp+0C0h+var_140]
0x180052bf8  mov     rcx, [rsp+1C0h+var_190]
0x180052bfd  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x180052c02  mov     [rsp+1C0h+var_160], rax
0x180052c07  mov     [rbp+0C0h+var_130], 2Dh ; '-'
0x180052c0e  mov     [rbp+0C0h+var_12C], edi
0x180052c11  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052c18  mov     [rbp+0C0h+var_128], rax
0x180052c1c  lea     rdx, [rbp+0C0h+var_130]
0x180052c20  mov     rcx, [rsp+1C0h+var_190]
0x180052c25  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x180052c2a  mov     rax, [rsp+1C0h+var_160]
0x180052c2f  mov     rcx, rax
0x180052c32  sub     rcx, 1
0x180052c36  jz      loc_180052D54
0x180052c3c  sub     rcx, 1
0x180052c40  jz      loc_180052CFB
0x180052c46  cmp     rcx, 1
0x180052c4a  jz      short loc_180052C99
0x180052c4c  mov     rcx, [rbp+0C8h]; this
0x180052c53  mov     [rsp+1C0h+var_198], rax; char *
0x180052c58  lea     rax, aUnknownItemInL; "Unknown item in loaded data blob: %llu"
0x180052c5f  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x180052c64  mov     r9d, 8000FFFFh; char *
0x180052c6a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052c71  mov     edx, 3Eh ; '>'; void *
0x180052c76  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052c7b  mov     [rbp+0C0h+var_120], 3Fh ; '?'
0x180052c82  mov     [rbp+0C0h+var_11C], esi
0x180052c85  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052c8c  mov     [rbp+0C0h+var_118], rax
0x180052c90  lea     rdx, [rbp+0C0h+var_120]
0x180052c94  jmp     loc_180052DAF
0x180052c99  mov     [rbp+0C0h+var_110], 39h ; '9'
0x180052ca0  mov     eax, [rsp+1C0h+var_17C]
0x180052ca4  mov     [rbp+0C0h+var_10C], eax
0x180052ca7  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052cae  mov     [rbp+0C0h+var_108], rax
0x180052cb2  lea     r8, [rbp+0C0h+var_110]
0x180052cb6  lea     rdx, [rbp+0C0h+var_60]
0x180052cba  mov     rcx, [rsp+1C0h+var_190]
0x180052cbf  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x180052cc4  mov     rdx, rax
0x180052cc7  lea     rcx, [rbp+0C0h+var_88]
0x180052ccb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180052cd0  lea     rcx, [rbp+0C0h+var_60]
0x180052cd4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052cd9  mov     [rbp+0C0h+var_100], 3Ah ; ':'
0x180052ce0  mov     eax, [rsp+1C0h+var_17C]
0x180052ce4  mov     [rbp+0C0h+var_FC], eax
0x180052ce7  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052cee  mov     [rbp+0C0h+var_F8], rax
0x180052cf2  lea     rdx, [rbp+0C0h+var_100]
0x180052cf6  jmp     loc_180052DAF
0x180052cfb  mov     [rbp+0C0h+var_F0], 35h ; '5'
0x180052d02  mov     [rbp+0C0h+var_EC], r12d
0x180052d06  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052d0d  mov     [rbp+0C0h+var_E8], rax
0x180052d11  lea     r8, [rbp+0C0h+var_F0]
0x180052d15  lea     rdx, [rbp+0C0h+var_60]
0x180052d19  mov     rcx, [rsp+1C0h+var_190]
0x180052d1e  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180052d23  mov     rdx, rax
0x180052d26  lea     rcx, [rbp+0C0h+var_A0]
0x180052d2a  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180052d2f  lea     rcx, [rbp+0C0h+var_60]
0x180052d33  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180052d38  mov     [rbp+0C0h+var_E0], 36h ; '6'
0x180052d3f  mov     [rbp+0C0h+var_DC], r13d
0x180052d43  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052d4a  mov     [rbp+0C0h+var_D8], rax
0x180052d4e  lea     rdx, [rbp+0C0h+var_E0]
0x180052d52  jmp     short loc_180052DAF
0x180052d54  mov     [rbp+0C0h+var_D0], 31h ; '1'
0x180052d5b  mov     [rbp+0C0h+var_CC], r14d
0x180052d5f  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052d66  mov     [rbp+0C0h+var_C8], rax
0x180052d6a  lea     r8, [rbp+0C0h+var_D0]
0x180052d6e  lea     rdx, [rbp+0C0h+var_60]
0x180052d72  mov     rcx, [rsp+1C0h+var_190]
0x180052d77  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x180052d7c  mov     rdx, rax
0x180052d7f  lea     rcx, [rbp+0C0h+var_C0]
0x180052d83  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180052d88  lea     rcx, [rbp+0C0h+var_60]
0x180052d8c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052d91  mov     [rsp+1C0h+var_180], 32h ; '2'
0x180052d99  mov     [rsp+1C0h+var_17C], r15d
0x180052d9e  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052da5  mov     [rsp+1C0h+var_178], rax
0x180052daa  lea     rdx, [rsp+1C0h+var_180]
0x180052daf  mov     rcx, [rsp+1C0h+var_190]
0x180052db4  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x180052db9  mov     [rsp+1C0h+var_170], 2Ah ; '*'
0x180052dc1  mov     eax, [rsp+1C0h+var_17C]
0x180052dc5  mov     [rsp+1C0h+var_16C], eax
0x180052dc9  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052dd0  mov     [rsp+1C0h+var_168], rax
0x180052dd5  lea     rdx, [rsp+1C0h+var_170]
0x180052dda  mov     rcx, [rsp+1C0h+var_190]
0x180052ddf  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x180052de4  test    al, al
0x180052de6  jz      loc_180052BDF
0x180052dec  mov     r12, [rbp+0C0h+var_70]
0x180052df0  mov     r15, [rbp+0C0h+var_78]
0x180052df4  mov     r14, [rbp+0C0h+var_90]
0x180052df8  movzx   esi, word ptr [rbp+0C0h+var_C0]
0x180052dfc  mov     rbx, [rsp+1C0h+var_190]
0x180052e01  mov     rdi, [rsp+1C0h+var_148]
0x180052e06  lea     r13, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\lockbox\\se"...
0x180052e0d  mov     [rsp+1C0h+var_180], 42h ; 'B'
0x180052e15  mov     eax, [rsp+1C0h+var_17C]
0x180052e19  mov     [rsp+1C0h+var_17C], eax
0x180052e1d  mov     [rsp+1C0h+var_178], r13
0x180052e22  lea     rdx, [rsp+1C0h+var_180]
0x180052e27  mov     rcx, rbx
0x180052e2a  call    ?LeaveContainer@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::LeaveContainer(SimpleCbor::impl::slim_source_location)
0x180052e2f  xorps   xmm0, xmm0
0x180052e32  movups  xmmword ptr [rdi], xmm0
0x180052e35  mov     [rdi], si
0x180052e38  movsd   xmm0, qword ptr [rbp+0C0h+var_C0+2]
0x180052e3d  movsd   qword ptr [rdi+2], xmm0
0x180052e42  mov     eax, dword ptr [rbp+0C0h+var_C0+0Ah]
0x180052e45  mov     [rdi+0Ah], eax
0x180052e48  movzx   eax, word ptr [rbp+0C0h+var_C0+0Eh]
0x180052e4c  mov     [rdi+0Eh], ax
0x180052e50  mov     rax, qword ptr [rbp+0C0h+var_B0]
0x180052e54  mov     [rdi+10h], rax
0x180052e58  mov     rax, qword ptr [rbp+0C0h+var_B0+8]
0x180052e5c  mov     [rdi+18h], rax
0x180052e60  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180052e68  movdqa  [rbp+0C0h+var_B0], xmm0
0x180052e6d  xor     edx, edx
0x180052e6f  mov     word ptr [rbp+0C0h+var_C0], dx
0x180052e73  mov     [rbp+0C0h+var_90], rdx
0x180052e77  mov     rcx, qword ptr [rbp+0C0h+var_A0+8]
0x180052e7b  mov     qword ptr [rbp+0C0h+var_A0+8], rdx
0x180052e7f  mov     rax, qword ptr [rbp+0C0h+var_A0]
0x180052e83  mov     qword ptr [rbp+0C0h+var_A0], rdx
0x180052e87  mov     [rdi+20h], rax
0x180052e8b  mov     [rdi+28h], rcx
0x180052e8f  mov     [rdi+30h], r14
0x180052e93  mov     rax, qword ptr [rbp+0C0h+var_88]
0x180052e97  mov     [rdi+38h], rax
0x180052e9b  mov     rcx, qword ptr [rbp+0C0h+var_88+8]
0x180052e9f  mov     [rdi+40h], rcx
0x180052ea3  mov     [rdi+48h], r15
0x180052ea7  mov     [rdi+50h], r12
0x180052eab  mov     [rbp+0C0h+var_78], rdx
0x180052eaf  mov     [rbp+0C0h+var_70], 7
0x180052eb7  mov     word ptr [rbp+0C0h+var_88], dx
0x180052ebb  lea     rcx, [rbp+0C0h+var_88]
0x180052ebf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052ec4  lea     rcx, [rbp+0C0h+var_A0]
0x180052ec8  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180052ecd  lea     rcx, [rbp+0C0h+var_C0]
0x180052ed1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052ed6  mov     rax, rdi
0x180052ed9  mov     rcx, [rbp+0C0h+var_40]
0x180052ee0  xor     rcx, rsp; StackCookie
0x180052ee3  call    __security_check_cookie
0x180052ee8  mov     rbx, [rsp+1C0h+arg_10]
0x180052ef0  add     rsp, 190h
0x180052ef7  pop     r15
0x180052ef9  pop     r14
0x180052efb  pop     r13
0x180052efd  pop     r12
0x180052eff  pop     rdi
0x180052f00  pop     rsi
0x180052f01  pop     rbp
0x180052f02  retn
```
