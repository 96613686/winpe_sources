# NgcUnpackGestureCollectionInputSerializationBuffer

- ea: `0x180011df0`
- end: `0x180012081`
- name: `NgcUnpackGestureCollectionInputSerializationBuffer`
- size: `657`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a594`
- `0x18000a5b4`
- `0x18000cfcc`
- `0x180011df0`
- `0x180055c5c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001203c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001203c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001200f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001200f`

## string_xrefs

- `0x180011e18`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011e45`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011e70`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011ea5`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011fbd`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180012021`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
__int64 __fastcall NgcUnpackGestureCollectionInputSerializationBuffer(
        __int64 a1,
        int a2,
        _DWORD *a3,
        int *a4,
        __int64 a5,
        LPWSTR *a6,
        __int64 a7,
        _DWORD *a8)
{
  _DWORD *v11; // rdi
  int v12; // eax
  unsigned int v13; // r14d
  LPWSTR *v14; // rbx
  const char *v15; // r9
  unsigned int LastError; // ebx
  int v17; // [rsp+20h] [rbp-C8h] BYREF
  int v18; // [rsp+24h] [rbp-C4h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-C0h] BYREF
  PSID Sid[2]; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-A8h]
  __int64 v22; // [rsp+48h] [rbp-A0h] BYREF
  int *v23; // [rsp+50h] [rbp-98h] BYREF
  int *v24; // [rsp+58h] [rbp-90h] BYREF
  __int64 v25; // [rsp+60h] [rbp-88h] BYREF
  PSID *v26; // [rsp+68h] [rbp-80h] BYREF
  __int64 v27; // [rsp+70h] [rbp-78h] BYREF
  int *v28; // [rsp+78h] [rbp-70h] BYREF
  _QWORD v29[13]; // [rsp+80h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  int v31; // [rsp+F0h] [rbp+8h] BYREF

  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v17);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v17);
    return 2147500035LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v17);
    return 2147500035LL;
  }
  v11 = a8;
  if ( !a8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v17);
    return 2147500035LL;
  }
  v31 = 0;
  v17 = 0;
  *(_OWORD *)Sid = 0;
  v21 = 0;
  v18 = 0;
  v28 = &v18;
  v27 = a7;
  v26 = Sid;
  v25 = a5;
  v24 = &v17;
  v23 = &v31;
  LODWORD(StringSid) = a2;
  v22 = a1;
  v29[0] = &v22;
  v29[1] = &StringSid;
  v29[2] = &v23;
  v29[3] = &v24;
  v29[4] = &v25;
  v29[5] = &v26;
  v29[6] = &v27;
  v29[7] = &v28;
  v12 = HResultErrorContract__lambda_a294572444e6881e43d8567d9ed0c838_(v29);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)(unsigned int)v12,
      v17);
    std::vector<unsigned char>::~vector<unsigned char>(Sid);
    return v13;
  }
  *a3 = v31;
  *a4 = v17;
  v14 = a6;
  if ( !a6 )
    goto LABEL_17;
  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid[0], &StringSid) )
  {
    *v14 = StringSid;
LABEL_17:
    *v11 = v18;
    std::vector<unsigned char>::~vector<unsigned char>(Sid);
    return 0;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x6F,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
                v15);
  if ( StringSid )
    LocalFree(StringSid);
  std::vector<unsigned char>::~vector<unsigned char>(Sid);
  return LastError;
}

```

## disassembly

```asm
0x180011df0  push    rbx
0x180011df2  push    rsi
0x180011df3  push    rdi
0x180011df4  push    r14
0x180011df6  sub     rsp, 0C8h
0x180011dfd  mov     rbx, r9
0x180011e00  mov     rsi, r8
0x180011e03  test    rcx, rcx
0x180011e06  jnz     short loc_180011E30
0x180011e08  mov     rcx, [rsp+0E8h]; this
0x180011e10  mov     ebx, 80004003h
0x180011e15  mov     r9d, ebx; char *
0x180011e18  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011e1f  mov     edx, 5Dh ; ']'; void *
0x180011e24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e29  mov     eax, ebx
0x180011e2b  jmp     loc_180012073
0x180011e30  test    rsi, rsi
0x180011e33  jnz     short loc_180011E5B
0x180011e35  mov     rcx, [rsp+0E8h]; this
0x180011e3d  mov     ebx, 80004003h
0x180011e42  mov     r9d, ebx; char *
0x180011e45  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011e4c  lea     edx, [rsi+5Eh]; void *
0x180011e4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e54  mov     eax, ebx
0x180011e56  jmp     loc_180012073
0x180011e5b  test    rbx, rbx
0x180011e5e  jnz     short loc_180011E88
0x180011e60  mov     rcx, [rsp+0E8h]; this
0x180011e68  mov     ebx, 80004003h
0x180011e6d  mov     r9d, ebx; char *
0x180011e70  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011e77  mov     edx, 5Fh ; '_'; void *
0x180011e7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e81  mov     eax, ebx
0x180011e83  jmp     loc_180012073
0x180011e88  mov     rdi, [rsp+0E8h+arg_38]
0x180011e90  test    rdi, rdi
0x180011e93  jnz     short loc_180011EBB
0x180011e95  mov     rcx, [rsp+0E8h]; this
0x180011e9d  mov     ebx, 80004003h
0x180011ea2  mov     r9d, ebx; char *
0x180011ea5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011eac  lea     edx, [rdi+60h]; void *
0x180011eaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011eb4  mov     eax, ebx
0x180011eb6  jmp     loc_180012073
0x180011ebb  mov     [rsp+0E8h+arg_0], 0
0x180011ec6  mov     [rsp+0E8h+var_C8], 0; int
0x180011ece  xorps   xmm0, xmm0
0x180011ed1  movdqu  xmmword ptr [rsp+0E8h+Sid], xmm0
0x180011ed7  mov     [rsp+0E8h+var_A8], 0
0x180011ee0  mov     [rsp+0E8h+var_C4], 0
0x180011ee8  lea     rax, [rsp+0E8h+var_C4]
0x180011eed  mov     [rsp+0E8h+var_70], rax
0x180011ef2  mov     rax, [rsp+0E8h+arg_30]
0x180011efa  mov     [rsp+0E8h+var_78], rax
0x180011eff  lea     rax, [rsp+0E8h+Sid]
0x180011f04  mov     [rsp+0E8h+var_80], rax
0x180011f09  mov     rax, [rsp+0E8h+arg_20]
0x180011f11  mov     [rsp+0E8h+var_88], rax
0x180011f16  lea     rax, [rsp+0E8h+var_C8]
0x180011f1b  mov     [rsp+0E8h+var_90], rax
0x180011f20  lea     rax, [rsp+0E8h+arg_0]
0x180011f28  mov     [rsp+0E8h+var_98], rax
0x180011f2d  mov     dword ptr [rsp+0E8h+StringSid], edx
0x180011f31  mov     [rsp+0E8h+var_A0], rcx
0x180011f36  lea     rax, [rsp+0E8h+var_A0]
0x180011f3b  mov     [rsp+0E8h+var_68], rax
0x180011f43  lea     rax, [rsp+0E8h+StringSid]
0x180011f48  mov     [rsp+0E8h+var_60], rax
0x180011f50  lea     rax, [rsp+0E8h+var_98]
0x180011f55  mov     [rsp+0E8h+var_58], rax
0x180011f5d  lea     rax, [rsp+0E8h+var_90]
0x180011f62  mov     [rsp+0E8h+var_50], rax
0x180011f6a  lea     rax, [rsp+0E8h+var_88]
0x180011f6f  mov     [rsp+0E8h+var_48], rax
0x180011f77  lea     rax, [rsp+0E8h+var_80]
0x180011f7c  mov     [rsp+0E8h+var_40], rax
0x180011f84  lea     rax, [rsp+0E8h+var_78]
0x180011f89  mov     [rsp+0E8h+var_38], rax
0x180011f91  lea     rax, [rsp+0E8h+var_70]
0x180011f96  mov     [rsp+0E8h+var_30], rax
0x180011f9e  lea     rcx, [rsp+0E8h+var_68]
0x180011fa6  call    HResultErrorContract__lambda_a294572444e6881e43d8567d9ed0c838___; HResultErrorContract__lambda_a294572444e6881e43d8567d9ed0c838_
0x180011fab  mov     r14d, eax
0x180011fae  test    eax, eax
0x180011fb0  jns     short loc_180011FE0
0x180011fb2  mov     rcx, [rsp+0E8h]; this
0x180011fba  mov     r9d, eax; char *
0x180011fbd  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011fc4  mov     edx, 67h ; 'g'; void *
0x180011fc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011fce  lea     rcx, [rsp+0E8h+Sid]
0x180011fd3  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011fd8  mov     eax, r14d
0x180011fdb  jmp     loc_180012073
0x180011fe0  mov     eax, [rsp+0E8h+arg_0]
0x180011fe7  mov     [rsi], eax
0x180011fe9  mov     eax, [rsp+0E8h+var_C8]
0x180011fed  mov     [rbx], eax
0x180011fef  mov     rbx, [rsp+0E8h+arg_28]
0x180011ff7  test    rbx, rbx
0x180011ffa  jz      short loc_180012058
0x180011ffc  mov     [rsp+0E8h+StringSid], 0
0x180012005  lea     rdx, [rsp+0E8h+StringSid]; StringSid
0x18001200a  mov     rcx, [rsp+0E8h+Sid]; Sid
0x18001200f  call    cs:__imp_ConvertSidToStringSidW
0x180012015  test    eax, eax
0x180012017  jnz     short loc_180012050
0x180012019  mov     rcx, [rsp+0E8h]; this
0x180012021  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180012028  lea     edx, [rax+6Fh]; void *
0x18001202b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012030  mov     ebx, eax
0x180012032  mov     rcx, [rsp+0E8h+StringSid]; hMem
0x180012037  test    rcx, rcx
0x18001203a  jz      short loc_180012042
0x18001203c  call    cs:__imp_LocalFree
0x180012042  lea     rcx, [rsp+0E8h+Sid]
0x180012047  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001204c  mov     eax, ebx
0x18001204e  jmp     short loc_180012073
0x180012050  mov     rax, [rsp+0E8h+StringSid]
0x180012055  mov     [rbx], rax
0x180012058  mov     eax, [rsp+0E8h+var_C4]
0x18001205c  mov     [rdi], eax
0x18001205e  lea     rcx, [rsp+0E8h+Sid]
0x180012063  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180012068  xor     eax, eax
0x18001206a  jmp     short loc_180012073
0x18001206c  mov     eax, [rsp+0E8h+arg_0]
0x180012073  add     rsp, 0C8h
0x18001207a  pop     r14
0x18001207c  pop     rdi
0x18001207d  pop     rsi
0x18001207e  pop     rbx
0x18001207f  retn
```
