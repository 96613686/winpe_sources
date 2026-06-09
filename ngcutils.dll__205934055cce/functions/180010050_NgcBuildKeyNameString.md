# NgcBuildKeyNameString

- ea: `0x180010050`
- end: `0x180010444`
- name: `NgcBuildKeyNameString`
- size: `1012`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003080`
- `0x18000530d`
- `0x18000a5b4`
- `0x18000c95c`
- `0x18000ce04`
- `0x18000ce74`
- `0x18000cfcc`
- `0x18000ed84`
- `0x180010050`
- `0x180013b3c`
- `0x180014790`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180010176`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180010176`

## string_xrefs

- `0x1800100aa`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x1800100d7`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010104`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010131`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x18001015e`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010307`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x18001038a`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall NgcBuildKeyNameString(
        void *Src,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int16 *a6)
{
  DWORD LengthSid; // eax
  __int64 v11; // rdi
  char *v12; // rbx
  __int64 v13; // rbx
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r8
  int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned __int16 **v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  NgcUtils *v29; // rcx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  unsigned int v33; // ebx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rdx
  __int64 v47; // r8
  int v48; // [rsp+20h] [rbp-118h]
  __int64 v49; // [rsp+30h] [rbp-108h] BYREF
  void *v50[2]; // [rsp+38h] [rbp-100h] BYREF
  __int64 v51; // [rsp+48h] [rbp-F0h]
  __int64 v52; // [rsp+50h] [rbp-E8h]
  NgcUtils *v53[2]; // [rsp+58h] [rbp-E0h] BYREF
  __m128i si128; // [rsp+68h] [rbp-D0h]
  _OWORD v55[2]; // [rsp+78h] [rbp-C0h] BYREF
  _OWORD v56[2]; // [rsp+98h] [rbp-A0h] BYREF
  _OWORD v57[2]; // [rsp+B8h] [rbp-80h] BYREF
  int v58[4]; // [rsp+D8h] [rbp-60h] BYREF
  __int128 v59; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v52 = a2;
  if ( Src )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        if ( a5 )
        {
          if ( a6 )
          {
            LengthSid = GetLengthSid(Src);
            v11 = LengthSid;
            *(_OWORD *)v50 = 0;
            v51 = 0;
            if ( LengthSid )
            {
              std::vector<unsigned char>::_Buy_nonzero(v50, LengthSid);
              v12 = (char *)v50[0];
              memmove_0(v50[0], Src, (unsigned int)v11);
              v50[1] = &v12[v11];
              v49 = 0;
              std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v49);
            }
            memset(v56, 0, sizeof(v56));
            v13 = -1;
            v14 = -1;
            do
              ++v14;
            while ( *(_WORD *)(a3 + 2 * v14) );
            std::wstring::_Construct<1,unsigned short const *>(v56, a3, v14);
            memset(v55, 0, sizeof(v55));
            v15 = -1;
            do
              ++v15;
            while ( *(_WORD *)(a4 + 2 * v15) );
            std::wstring::_Construct<1,unsigned short const *>(v55, a4, v15);
            memset(v57, 0, sizeof(v57));
            v16 = -1;
            do
              ++v16;
            while ( *(_WORD *)(a5 + 2 * v16) );
            std::wstring::_Construct<1,unsigned short const *>(v57, a5, v16);
            *(_OWORD *)v53 = 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v53[0]) = 0;
            *(_OWORD *)v58 = 0;
            v59 = 0;
            do
              ++v13;
            while ( *(_WORD *)(a5 + 2 * v13) );
            std::wstring::_Construct<1,unsigned short const *>(v58, a5, v13);
            v17 = NgcUtils::NgcKeyName::BuildNgcKeyNameString(v50, v52, v56, v55);
            std::wstring::~wstring(v58, v18, v19);
            if ( v17 >= 0 )
            {
              *(_QWORD *)a6 = 0;
              v29 = (NgcUtils *)v53;
              if ( si128.m128i_i64[1] > 7uLL )
                v29 = v53[0];
              v30 = NgcUtils::DuplicateString(v29, a6, v20);
              v33 = v30;
              if ( v30 >= 0 )
              {
                std::wstring::~wstring(v53, v31, v32);
                std::wstring::~wstring(v57, v42, v43);
                std::wstring::~wstring(v55, v44, v45);
                std::wstring::~wstring(v56, v46, v47);
                std::vector<unsigned char>::~vector<unsigned char>(v50);
                return 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x10F,
                  (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
                  (const char *)(unsigned int)v30,
                  (int)v58);
                std::wstring::~wstring(v53, v34, v35);
                std::wstring::~wstring(v57, v36, v37);
                std::wstring::~wstring(v55, v38, v39);
                std::wstring::~wstring(v56, v40, v41);
                std::vector<unsigned char>::~vector<unsigned char>(v50);
                return v33;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x10C,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
                (const char *)(unsigned int)v17,
                (int)v58);
              std::wstring::~wstring(v53, v21, v22);
              std::wstring::~wstring(v57, v23, v24);
              std::wstring::~wstring(v55, v25, v26);
              std::wstring::~wstring(v56, v27, v28);
              std::vector<unsigned char>::~vector<unsigned char>(v50);
              return (unsigned int)v17;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x104,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
              (const char *)0x80004003LL,
              v48);
            return 2147500035LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x103,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
            (const char *)0x80004003LL,
            v48);
          return 2147500035LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x102,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
          (const char *)0x80004003LL,
          v48);
        return 2147500035LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
        (const char *)0x80004003LL,
        v48);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v48);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180010050  push    rbx
0x180010052  push    rsi
0x180010053  push    rdi
0x180010054  push    r12
0x180010056  push    r13
0x180010058  push    r14
0x18001005a  push    r15
0x18001005c  sub     rsp, 100h
0x180010063  mov     rax, cs:__security_cookie
0x18001006a  xor     rax, rsp
0x18001006d  mov     [rsp+138h+var_40], rax
0x180010075  mov     r12, r9
0x180010078  mov     r15, r8
0x18001007b  mov     [rsp+138h+var_E8], rdx
0x180010080  mov     r14, rcx
0x180010083  mov     rsi, [rsp+138h+arg_20]
0x18001008b  mov     r13, [rsp+138h+arg_28]
0x180010093  xor     ebx, ebx
0x180010095  test    rcx, rcx
0x180010098  jnz     short loc_1800100C2
0x18001009a  mov     rcx, [rsp+138h]; this
0x1800100a2  mov     ebx, 80004003h
0x1800100a7  mov     r9d, ebx; char *
0x1800100aa  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800100b1  mov     edx, 100h; void *
0x1800100b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800100bb  mov     eax, ebx
0x1800100bd  jmp     loc_180010420
0x1800100c2  test    r15, r15
0x1800100c5  jnz     short loc_1800100EF
0x1800100c7  mov     rcx, [rsp+138h]; this
0x1800100cf  mov     ebx, 80004003h
0x1800100d4  mov     r9d, ebx; char *
0x1800100d7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800100de  mov     edx, 101h; void *
0x1800100e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800100e8  mov     eax, ebx
0x1800100ea  jmp     loc_180010420
0x1800100ef  test    r12, r12
0x1800100f2  jnz     short loc_18001011C
0x1800100f4  mov     rcx, [rsp+138h]; this
0x1800100fc  mov     ebx, 80004003h
0x180010101  mov     r9d, ebx; char *
0x180010104  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001010b  mov     edx, 102h; void *
0x180010110  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010115  mov     eax, ebx
0x180010117  jmp     loc_180010420
0x18001011c  test    rsi, rsi
0x18001011f  jnz     short loc_180010149
0x180010121  mov     rcx, [rsp+138h]; this
0x180010129  mov     ebx, 80004003h
0x18001012e  mov     r9d, ebx; char *
0x180010131  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010138  mov     edx, 103h; void *
0x18001013d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010142  mov     eax, ebx
0x180010144  jmp     loc_180010420
0x180010149  test    r13, r13
0x18001014c  jnz     short loc_180010176
0x18001014e  mov     rcx, [rsp+138h]; this
0x180010156  mov     ebx, 80004003h
0x18001015b  mov     r9d, ebx; char *
0x18001015e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010165  mov     edx, 104h; void *
0x18001016a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001016f  mov     eax, ebx
0x180010171  jmp     loc_180010420
0x180010176  call    cs:__imp_GetLengthSid
0x18001017c  mov     edi, eax
0x18001017e  xorps   xmm0, xmm0
0x180010181  movdqu  xmmword ptr [rsp+138h+var_100], xmm0
0x180010187  mov     [rsp+138h+var_F0], rbx
0x18001018c  test    eax, eax
0x18001018e  jz      short loc_1800101CB
0x180010190  mov     edx, edi
0x180010192  lea     rcx, [rsp+138h+var_100]
0x180010197  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x18001019c  mov     rbx, [rsp+138h+var_100]
0x1800101a1  mov     r8d, edi; Size
0x1800101a4  mov     rdx, r14; Src
0x1800101a7  mov     rcx, rbx; void *
0x1800101aa  call    memmove_0
0x1800101af  lea     rax, [rdi+rbx]
0x1800101b3  mov     [rsp+138h+var_100+8], rax
0x1800101b8  xor     edi, edi
0x1800101ba  mov     [rsp+138h+var_108], rdi
0x1800101bf  lea     rcx, [rsp+138h+var_108]
0x1800101c4  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x1800101c9  jmp     short loc_1800101CD
0x1800101cb  xor     edi, edi
0x1800101cd  xorps   xmm0, xmm0
0x1800101d0  movups  [rsp+138h+var_A0], xmm0
0x1800101d8  xorps   xmm1, xmm1
0x1800101db  movdqu  [rsp+138h+var_90], xmm1
0x1800101e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800101e8  mov     r8, rbx
0x1800101eb  inc     r8
0x1800101ee  cmp     [r15+r8*2], di
0x1800101f3  jnz     short loc_1800101EB
0x1800101f5  mov     rdx, r15
0x1800101f8  lea     rcx, [rsp+138h+var_A0]
0x180010200  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010205  nop
0x180010206  xorps   xmm0, xmm0
0x180010209  movups  [rsp+138h+var_C0], xmm0
0x18001020e  xorps   xmm1, xmm1
0x180010211  movdqu  [rsp+138h+var_B0], xmm1
0x18001021a  mov     r8, rbx
0x18001021d  inc     r8
0x180010220  cmp     [r12+r8*2], di
0x180010225  jnz     short loc_18001021D
0x180010227  mov     rdx, r12
0x18001022a  lea     rcx, [rsp+138h+var_C0]
0x18001022f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010234  nop
0x180010235  xorps   xmm0, xmm0
0x180010238  movups  [rsp+138h+var_80], xmm0
0x180010240  xorps   xmm1, xmm1
0x180010243  movdqu  [rsp+138h+var_70], xmm1
0x18001024c  mov     r8, rbx
0x18001024f  inc     r8
0x180010252  cmp     [rsi+r8*2], di
0x180010257  jnz     short loc_18001024F
0x180010259  mov     rdx, rsi
0x18001025c  lea     rcx, [rsp+138h+var_80]
0x180010264  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010269  nop
0x18001026a  xorps   xmm0, xmm0
0x18001026d  movups  xmmword ptr [rsp+138h+var_E0], xmm0
0x180010272  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001027a  movdqu  [rsp+138h+var_D0], xmm1
0x180010280  mov     word ptr [rsp+138h+var_E0], di
0x180010285  movups  xmmword ptr [rsp+138h+var_60], xmm0
0x18001028d  xorps   xmm1, xmm1
0x180010290  movdqu  [rsp+138h+var_50], xmm1
0x180010299  inc     rbx
0x18001029c  cmp     [rsi+rbx*2], di
0x1800102a0  jnz     short loc_180010299
0x1800102a2  mov     r8, rbx
0x1800102a5  mov     rdx, rsi
0x1800102a8  lea     rcx, [rsp+138h+var_60]
0x1800102b0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800102b5  nop
0x1800102b6  lea     rax, [rsp+138h+var_E0]
0x1800102bb  mov     [rsp+138h+var_110], rax
0x1800102c0  lea     rax, [rsp+138h+var_60]
0x1800102c8  mov     qword ptr [rsp+138h+var_118], rax; int
0x1800102cd  lea     r9, [rsp+138h+var_C0]
0x1800102d2  lea     r8, [rsp+138h+var_A0]
0x1800102da  mov     rdx, [rsp+138h+var_E8]
0x1800102df  lea     rcx, [rsp+138h+var_100]
0x1800102e4  call    ?BuildNgcKeyNameString@NgcKeyName@NgcUtils@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@22PEAV64@@Z; NgcUtils::NgcKeyName::BuildNgcKeyNameString(std::vector<uchar> const &,_GUID const &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring *)
0x1800102e9  mov     ebx, eax
0x1800102eb  lea     rcx, [rsp+138h+var_60]
0x1800102f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800102f8  test    ebx, ebx
0x1800102fa  jns     short loc_18001035C
0x1800102fc  mov     rcx, [rsp+138h]; this
0x180010304  mov     r9d, ebx; char *
0x180010307  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001030e  mov     edx, 10Ch; void *
0x180010313  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010318  nop
0x180010319  lea     rcx, [rsp+138h+var_E0]
0x18001031e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010323  nop
0x180010324  lea     rcx, [rsp+138h+var_80]
0x18001032c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010331  nop
0x180010332  lea     rcx, [rsp+138h+var_C0]
0x180010337  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001033c  nop
0x18001033d  lea     rcx, [rsp+138h+var_A0]
0x180010345  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001034a  nop
0x18001034b  lea     rcx, [rsp+138h+var_100]
0x180010350  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180010355  mov     eax, ebx
0x180010357  jmp     loc_180010420
0x18001035c  mov     [r13+0], rdi
0x180010360  lea     rcx, [rsp+138h+var_E0]
0x180010365  cmp     qword ptr [rsp+138h+var_D0+8], 7
0x18001036b  cmova   rcx, [rsp+138h+var_E0]; this
0x180010371  mov     rdx, r13; unsigned __int16 *
0x180010374  call    ?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::DuplicateString(ushort const *,ushort * *)
0x180010379  mov     ebx, eax
0x18001037b  test    eax, eax
0x18001037d  jns     short loc_1800103DC
0x18001037f  mov     rcx, [rsp+138h]; this
0x180010387  mov     r9d, eax; char *
0x18001038a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010391  mov     edx, 10Fh; void *
0x180010396  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001039b  nop
0x18001039c  lea     rcx, [rsp+138h+var_E0]
0x1800103a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800103a6  nop
0x1800103a7  lea     rcx, [rsp+138h+var_80]
0x1800103af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800103b4  nop
0x1800103b5  lea     rcx, [rsp+138h+var_C0]
0x1800103ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800103bf  nop
0x1800103c0  lea     rcx, [rsp+138h+var_A0]
0x1800103c8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800103cd  nop
0x1800103ce  lea     rcx, [rsp+138h+var_100]
0x1800103d3  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800103d8  mov     eax, ebx
0x1800103da  jmp     short loc_180010420
0x1800103dc  lea     rcx, [rsp+138h+var_E0]
0x1800103e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800103e6  nop
0x1800103e7  lea     rcx, [rsp+138h+var_80]
0x1800103ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800103f4  nop
0x1800103f5  lea     rcx, [rsp+138h+var_C0]
0x1800103fa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800103ff  nop
0x180010400  lea     rcx, [rsp+138h+var_A0]
0x180010408  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001040d  nop
0x18001040e  lea     rcx, [rsp+138h+var_100]
0x180010413  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180010418  xor     eax, eax
0x18001041a  jmp     short loc_180010420
0x18001041c  mov     eax, dword ptr [rsp+138h+var_108]
0x180010420  mov     rcx, [rsp+138h+var_40]
0x180010428  xor     rcx, rsp; StackCookie
0x18001042b  call    __security_check_cookie
0x180010430  add     rsp, 100h
0x180010437  pop     r15
0x180010439  pop     r14
0x18001043b  pop     r13
0x18001043d  pop     r12
0x18001043f  pop     rdi
0x180010440  pop     rsi
0x180010441  pop     rbx
0x180010442  retn
```
