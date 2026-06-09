# NgcBuildDefaultDecryptionKeyNameString

- ea: `0x18000fdc0`
- end: `0x180010040`
- name: `NgcBuildDefaultDecryptionKeyNameString`
- size: `640`
- prototype: `__int64 __fastcall(void *Src)`
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
- `0x18000fdc0`
- `0x180013b3c`
- `0x180014790`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000fe44`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000fe44`

## string_xrefs

- `0x18000fdff`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x18000fe2c`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x18000ff7c`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x18000ffd8`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall NgcBuildDefaultDecryptionKeyNameString(void *Src, __int64 a2, const unsigned __int16 *a3)
{
  DWORD LengthSid; // eax
  __int64 v8; // rdi
  char *v9; // rbx
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned __int16 **v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  NgcUtils *v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // [rsp+20h] [rbp-E8h]
  __int64 v28; // [rsp+30h] [rbp-D8h] BYREF
  void *v29[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-C0h]
  NgcUtils *v31[2]; // [rsp+50h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A8h]
  int v33[4]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v34; // [rsp+80h] [rbp-88h]
  _OWORD v35[2]; // [rsp+90h] [rbp-78h] BYREF
  _OWORD v36[2]; // [rsp+B0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( Src )
  {
    if ( a3 )
    {
      LengthSid = GetLengthSid(Src);
      v8 = LengthSid;
      *(_OWORD *)v29 = 0;
      v30 = 0;
      if ( LengthSid )
      {
        std::vector<unsigned char>::_Buy_nonzero(v29, LengthSid);
        v9 = (char *)v29[0];
        memmove_0(v29[0], Src, (unsigned int)v8);
        v29[1] = &v9[v8];
        v28 = 0;
        std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v28);
      }
      *(_OWORD *)v31 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v31[0]) = 0;
      v36[0] = 0;
      v36[1] = si128;
      LOWORD(v36[0]) = 0;
      v35[0] = 0;
      v35[1] = si128;
      LOWORD(v35[0]) = 0;
      *(_OWORD *)v33 = 0;
      v34 = 0;
      std::wstring::_Construct<1,unsigned short const *>(v33, L"9DDC52DB-DC02-4A8C-B892-38DEF4FA748F", 36);
      v10 = NgcUtils::NgcKeyName::BuildNgcKeyNameString(v29, a2, v36, v35);
      std::wstring::~wstring(v33, v11, v12);
      std::wstring::~wstring(v35, v13, v14);
      std::wstring::~wstring(v36, v15, v16);
      if ( v10 >= 0 )
      {
        *(_QWORD *)a3 = 0;
        v20 = (NgcUtils *)v31;
        if ( si128.m128i_i64[1] > 7uLL )
          v20 = v31[0];
        v21 = NgcUtils::DuplicateString(v20, a3, v17);
        v24 = v21;
        if ( v21 >= 0 )
        {
          std::wstring::~wstring(v31, v22, v23);
          std::vector<unsigned char>::~vector<unsigned char>(v29);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11F,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
            (const char *)(unsigned int)v21,
            (int)v33);
          std::wstring::~wstring(v31, v25, v26);
          std::vector<unsigned char>::~vector<unsigned char>(v29);
          return v24;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11C,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
          (const char *)(unsigned int)v10,
          (int)v33);
        std::wstring::~wstring(v31, v18, v19);
        std::vector<unsigned char>::~vector<unsigned char>(v29);
        return (unsigned int)v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
        (const char *)0x80004003LL,
        v27);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v27);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18000fdc0  push    rbx
0x18000fdc2  push    rsi
0x18000fdc3  push    rdi
0x18000fdc4  push    r14
0x18000fdc6  push    r15
0x18000fdc8  sub     rsp, 0E0h
0x18000fdcf  mov     rax, cs:__security_cookie
0x18000fdd6  xor     rax, rsp
0x18000fdd9  mov     [rsp+108h+var_38], rax
0x18000fde1  mov     r14, r8
0x18000fde4  mov     r15, rdx
0x18000fde7  mov     rsi, rcx
0x18000fdea  test    rcx, rcx
0x18000fded  jnz     short loc_18000FE17
0x18000fdef  mov     rcx, [rsp+108h]; this
0x18000fdf7  mov     ebx, 80004003h
0x18000fdfc  mov     r9d, ebx; char *
0x18000fdff  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000fe06  mov     edx, 117h; void *
0x18000fe0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fe10  mov     eax, ebx
0x18000fe12  jmp     loc_180010020
0x18000fe17  test    r14, r14
0x18000fe1a  jnz     short loc_18000FE44
0x18000fe1c  mov     rcx, [rsp+108h]; this
0x18000fe24  mov     ebx, 80004003h
0x18000fe29  mov     r9d, ebx; char *
0x18000fe2c  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000fe33  mov     edx, 118h; void *
0x18000fe38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fe3d  mov     eax, ebx
0x18000fe3f  jmp     loc_180010020
0x18000fe44  call    cs:__imp_GetLengthSid
0x18000fe4a  mov     edi, eax
0x18000fe4c  xorps   xmm0, xmm0
0x18000fe4f  movdqu  xmmword ptr [rsp+108h+var_D0], xmm0
0x18000fe55  mov     [rsp+108h+var_C0], 0
0x18000fe5e  test    eax, eax
0x18000fe60  jz      short loc_18000FE9E
0x18000fe62  mov     edx, edi
0x18000fe64  lea     rcx, [rsp+108h+var_D0]
0x18000fe69  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x18000fe6e  mov     rbx, [rsp+108h+var_D0]
0x18000fe73  mov     r8d, edi; Size
0x18000fe76  mov     rdx, rsi; Src
0x18000fe79  mov     rcx, rbx; void *
0x18000fe7c  call    memmove_0
0x18000fe81  lea     rax, [rdi+rbx]
0x18000fe85  mov     [rsp+108h+var_D0+8], rax
0x18000fe8a  mov     [rsp+108h+var_D8], 0
0x18000fe93  lea     rcx, [rsp+108h+var_D8]
0x18000fe98  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18000fe9d  nop
0x18000fe9e  xorps   xmm0, xmm0
0x18000fea1  movups  xmmword ptr [rsp+108h+var_B8], xmm0
0x18000fea6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000feae  movdqu  [rsp+108h+var_A8], xmm1
0x18000feb4  xor     eax, eax
0x18000feb6  mov     word ptr [rsp+108h+var_B8], ax
0x18000febb  movups  [rsp+108h+var_58], xmm0
0x18000fec3  movdqu  [rsp+108h+var_48], xmm1
0x18000fecc  mov     word ptr [rsp+108h+var_58], ax
0x18000fed4  movups  [rsp+108h+var_78], xmm0
0x18000fedc  movdqu  [rsp+108h+var_68], xmm1
0x18000fee5  mov     word ptr [rsp+108h+var_78], ax
0x18000feed  movups  xmmword ptr [rsp+108h+var_98], xmm0
0x18000fef2  xorps   xmm1, xmm1
0x18000fef5  movdqu  [rsp+108h+var_88], xmm1
0x18000fefe  lea     r8d, [rax+24h]
0x18000ff02  lea     rdx, a9ddc52dbDc024a; "9DDC52DB-DC02-4A8C-B892-38DEF4FA748F"
0x18000ff09  lea     rcx, [rsp+108h+var_98]
0x18000ff0e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ff13  nop
0x18000ff14  lea     rax, [rsp+108h+var_B8]
0x18000ff19  mov     [rsp+108h+var_E0], rax
0x18000ff1e  lea     rax, [rsp+108h+var_98]
0x18000ff23  mov     qword ptr [rsp+108h+var_E8], rax; int
0x18000ff28  lea     r9, [rsp+108h+var_78]
0x18000ff30  lea     r8, [rsp+108h+var_58]
0x18000ff38  mov     rdx, r15
0x18000ff3b  lea     rcx, [rsp+108h+var_D0]
0x18000ff40  call    ?BuildNgcKeyNameString@NgcKeyName@NgcUtils@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@22PEAV64@@Z; NgcUtils::NgcKeyName::BuildNgcKeyNameString(std::vector<uchar> const &,_GUID const &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring *)
0x18000ff45  mov     ebx, eax
0x18000ff47  lea     rcx, [rsp+108h+var_98]
0x18000ff4c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ff51  nop
0x18000ff52  lea     rcx, [rsp+108h+var_78]
0x18000ff5a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ff5f  nop
0x18000ff60  lea     rcx, [rsp+108h+var_58]
0x18000ff68  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ff6d  test    ebx, ebx
0x18000ff6f  jns     short loc_18000FFA7
0x18000ff71  mov     rcx, [rsp+108h]; this
0x18000ff79  mov     r9d, ebx; char *
0x18000ff7c  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000ff83  mov     edx, 11Ch; void *
0x18000ff88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ff8d  nop
0x18000ff8e  lea     rcx, [rsp+108h+var_B8]
0x18000ff93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ff98  nop
0x18000ff99  lea     rcx, [rsp+108h+var_D0]
0x18000ff9e  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000ffa3  mov     eax, ebx
0x18000ffa5  jmp     short loc_180010020
0x18000ffa7  mov     qword ptr [r14], 0
0x18000ffae  lea     rcx, [rsp+108h+var_B8]
0x18000ffb3  cmp     qword ptr [rsp+108h+var_A8+8], 7
0x18000ffb9  cmova   rcx, [rsp+108h+var_B8]; this
0x18000ffbf  mov     rdx, r14; unsigned __int16 *
0x18000ffc2  call    ?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::DuplicateString(ushort const *,ushort * *)
0x18000ffc7  mov     ebx, eax
0x18000ffc9  test    eax, eax
0x18000ffcb  jns     short loc_180010003
0x18000ffcd  mov     rcx, [rsp+108h]; this
0x18000ffd5  mov     r9d, eax; char *
0x18000ffd8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000ffdf  mov     edx, 11Fh; void *
0x18000ffe4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffe9  nop
0x18000ffea  lea     rcx, [rsp+108h+var_B8]
0x18000ffef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000fff4  nop
0x18000fff5  lea     rcx, [rsp+108h+var_D0]
0x18000fffa  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000ffff  mov     eax, ebx
0x180010001  jmp     short loc_180010020
0x180010003  lea     rcx, [rsp+108h+var_B8]
0x180010008  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001000d  nop
0x18001000e  lea     rcx, [rsp+108h+var_D0]
0x180010013  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180010018  xor     eax, eax
0x18001001a  jmp     short loc_180010020
0x18001001c  mov     eax, dword ptr [rsp+108h+var_D8]
0x180010020  mov     rcx, [rsp+108h+var_38]
0x180010028  xor     rcx, rsp; StackCookie
0x18001002b  call    __security_check_cookie
0x180010030  add     rsp, 0E0h
0x180010037  pop     r15
0x180010039  pop     r14
0x18001003b  pop     rdi
0x18001003c  pop     rsi
0x18001003d  pop     rbx
0x18001003e  retn
```
