# TraceInformAttempt

- ea: `0x18004304c`
- end: `0x1800433a9`
- name: `TraceInformAttempt`
- size: `861`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180034fe4`

## callees

- `0x18000f98c`
- `0x180010b1c`
- `0x180015668`
- `0x18001cef0`
- `0x18004304c`
- `0x18004c89c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180043085`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800430af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180043085`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800430af`

## pseudocode

```c
char __fastcall TraceInformAttempt(__int64 a1, ULONGLONG a2, int a3, int a4, int a5)
{
  ULONGLONG v9; // rsi
  ULONGLONG TickCount64; // rax
  HRESULT v11; // eax
  int v12; // r8d
  int v13; // r9d
  ULONGLONG v14; // rbx
  char result; // al
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  ULONGLONG pullResult; // [rsp+A0h] [rbp-80h] BYREF
  int v20; // [rsp+A8h] [rbp-78h] BYREF
  int v21; // [rsp+ACh] [rbp-74h] BYREF
  int v22; // [rsp+B0h] [rbp-70h] BYREF
  int v23; // [rsp+B4h] [rbp-6Ch] BYREF
  int v24; // [rsp+B8h] [rbp-68h] BYREF
  int v25; // [rsp+BCh] [rbp-64h] BYREF
  int v26; // [rsp+C0h] [rbp-60h] BYREF
  ULONGLONG v27; // [rsp+C8h] [rbp-58h] BYREF
  ULONGLONG v28; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v29; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v30; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v31; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v32; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v33; // [rsp+F8h] [rbp-28h] BYREF
  char v34[32]; // [rsp+100h] [rbp-20h] BYREF
  int *v35; // [rsp+120h] [rbp+0h]
  __int64 v36; // [rsp+128h] [rbp+8h]
  ULONGLONG *v37; // [rsp+130h] [rbp+10h]
  __int64 v38; // [rsp+138h] [rbp+18h]
  int *v39; // [rsp+140h] [rbp+20h]
  __int64 v40; // [rsp+148h] [rbp+28h]
  int *v41; // [rsp+150h] [rbp+30h]
  __int64 v42; // [rsp+158h] [rbp+38h]
  int *v43; // [rsp+160h] [rbp+40h]
  __int64 v44; // [rsp+168h] [rbp+48h]
  ULONGLONG *v45; // [rsp+170h] [rbp+50h]
  __int64 v46; // [rsp+178h] [rbp+58h]
  __int64 v47; // [rsp+180h] [rbp+60h]
  __int64 v48; // [rsp+188h] [rbp+68h]
  int *v49; // [rsp+190h] [rbp+70h]
  __int64 v50; // [rsp+198h] [rbp+78h]
  int *v51; // [rsp+1A0h] [rbp+80h]
  __int64 v52; // [rsp+1A8h] [rbp+88h]
  int *v53; // [rsp+1B0h] [rbp+90h]
  __int64 v54; // [rsp+1B8h] [rbp+98h]
  __int64 v55; // [rsp+1C0h] [rbp+A0h]
  __int64 v56; // [rsp+1C8h] [rbp+A8h]
  UUID *v57; // [rsp+1D0h] [rbp+B0h]
  __int64 v58; // [rsp+1D8h] [rbp+B8h]
  __int64 *v59; // [rsp+1E0h] [rbp+C0h]
  __int64 v60; // [rsp+1E8h] [rbp+C8h]
  ULONGLONG *p_pullResult; // [rsp+1F0h] [rbp+D0h]
  __int64 v62; // [rsp+1F8h] [rbp+D8h]
  __int64 *v63; // [rsp+200h] [rbp+E0h]
  __int64 v64; // [rsp+208h] [rbp+E8h]
  __int64 *v65; // [rsp+210h] [rbp+F0h]
  __int64 v66; // [rsp+218h] [rbp+F8h]
  __int64 *v67; // [rsp+220h] [rbp+100h]
  __int64 v68; // [rsp+228h] [rbp+108h]
  __int64 *v69; // [rsp+230h] [rbp+110h]
  __int64 v70; // [rsp+238h] [rbp+118h]

  pullResult = 0;
  v9 = GetTickCount64() / 0x3E8;
  TickCount64 = GetTickCount64();
  v11 = ULongLongSub(TickCount64, a2, &pullResult);
  v14 = pullResult;
  if ( v11 )
    v14 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dIdddI_guid_ddd_guid__guid_IdIII(
      a1 + 2112,
      a1 + 32,
      v12,
      v13,
      v14,
      a3,
      a4,
      a5,
      v9,
      a1 + 32,
      *(_DWORD *)(a1 + 48),
      *(_DWORD *)(a1 + 112),
      *(_DWORD *)(a1 + 116),
      a1 + 2112);
  result = dword_1800610D8;
  if ( (unsigned int)dword_1800610D8 > 5 )
  {
    result = tlgKeywordOn((__int64)&dword_1800610D8, 0x400000000000LL);
    if ( result )
    {
      v20 = 1;
      v35 = &v20;
      v36 = 4;
      v37 = &v27;
      v39 = &v21;
      v41 = &v22;
      v43 = &v23;
      v45 = &v28;
      v47 = a1 + 32;
      v24 = *(_DWORD *)(a1 + 48);
      v49 = &v24;
      v25 = *(_DWORD *)(a1 + 112);
      v51 = &v25;
      v26 = *(_DWORD *)(a1 + 116);
      v53 = &v26;
      v55 = a1 + 2112;
      v57 = &DhcpGlobalBootGuid;
      v29 = *(_QWORD *)(a1 + 1960);
      v59 = &v29;
      LODWORD(pullResult) = *(_DWORD *)(a1 + 440);
      p_pullResult = &pullResult;
      v30 = *(_QWORD *)(a1 + 448);
      v63 = &v30;
      v31 = *(_QWORD *)(a1 + 456);
      v65 = &v31;
      v32 = *(_QWORD *)(a1 + 464);
      v67 = &v32;
      v69 = &v33;
      v27 = v14;
      v38 = 8;
      v21 = a3;
      v40 = 4;
      v22 = a4;
      v42 = 4;
      v23 = a5;
      v44 = 4;
      v28 = v9;
      v46 = 8;
      v48 = 16;
      v50 = 4;
      v52 = 4;
      v54 = 4;
      v56 = 16;
      v58 = 16;
      v60 = 8;
      v62 = 4;
      v64 = 8;
      v66 = 8;
      v68 = 8;
      v33 = 0x1000000;
      v70 = 8;
      return tlgWriteTransfer_EtwEventWriteTransfer(v16, (unsigned __int8 *)byte_180059EE7, v17, v18, 20, (__int64)v34);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004304c  push    rbp
0x18004304e  push    rbx
0x18004304f  push    rsi
0x180043050  push    rdi
0x180043051  push    r12
0x180043053  push    r13
0x180043055  push    r14
0x180043057  push    r15
0x180043059  lea     rbp, [rsp-138h]
0x180043061  sub     rsp, 258h
0x180043068  mov     rax, cs:__security_cookie
0x18004306f  xor     rax, rsp
0x180043072  mov     [rbp+170h+var_50], rax
0x180043079  mov     r14d, r9d
0x18004307c  mov     r15d, r8d
0x18004307f  mov     rbx, rdx
0x180043082  mov     rdi, rcx
0x180043085  call    cs:__imp_GetTickCount64
0x18004308b  mov     rsi, rax
0x18004308e  xor     r13d, r13d
0x180043091  mov     rax, 624DD2F1A9FBE77h
0x18004309b  mov     [rbp+170h+pullResult], r13
0x18004309f  mul     rsi
0x1800430a2  sub     rsi, rdx
0x1800430a5  shr     rsi, 1
0x1800430a8  add     rsi, rdx
0x1800430ab  shr     rsi, 9
0x1800430af  call    cs:__imp_GetTickCount64
0x1800430b5  lea     r8, [rbp+170h+pullResult]; pullResult
0x1800430b9  mov     rdx, rbx; ullSubtrahend
0x1800430bc  mov     rcx, rax; ullMinuend
0x1800430bf  call    ULongLongSub
0x1800430c4  mov     rbx, [rbp+170h+pullResult]
0x1800430c8  test    eax, eax
0x1800430ca  cmovnz  rbx, r13
0x1800430ce  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800430d5  mov     r12d, [rbp+170h+arg_20]
0x1800430dc  jz      loc_180043170
0x1800430e2  mov     rax, [rdi+1D0h]
0x1800430e9  lea     rcx, [rdi+840h]
0x1800430f0  mov     [rsp+290h+var_1F8], rax
0x1800430f8  lea     rdx, [rdi+20h]
0x1800430fc  mov     rax, [rdi+1C8h]
0x180043103  mov     [rsp+290h+var_200], rax
0x18004310b  mov     rax, [rdi+1C0h]
0x180043112  mov     [rsp+290h+var_208], rax
0x18004311a  mov     eax, [rdi+1B8h]
0x180043120  mov     [rsp+290h+var_210], eax
0x180043127  mov     rax, [rdi+7A8h]
0x18004312e  mov     [rsp+290h+var_218], rax
0x180043133  mov     eax, [rdi+74h]
0x180043136  mov     [rsp+290h+var_228], rcx
0x18004313b  mov     [rsp+290h+var_230], eax
0x18004313f  mov     eax, [rdi+70h]
0x180043142  mov     [rsp+290h+var_238], eax
0x180043146  mov     eax, [rdi+30h]
0x180043149  mov     [rsp+290h+var_240], eax
0x18004314d  mov     [rsp+290h+var_248], rdx
0x180043152  mov     [rsp+290h+var_250], rsi
0x180043157  mov     [rsp+290h+var_258], r12d
0x18004315c  mov     [rsp+290h+var_260], r14d
0x180043161  mov     dword ptr [rsp+290h+var_268], r15d
0x180043166  mov     [rsp+290h+var_270], rbx
0x18004316b  call    WPP_SF_dIdddI_guid_ddd_guid__guid_IdIII
0x180043170  mov     eax, cs:dword_1800610D8
0x180043176  cmp     eax, 5
0x180043179  jbe     loc_180043386
0x18004317f  mov     rdx, 400000000000h
0x180043189  lea     rcx, dword_1800610D8
0x180043190  call    _tlgKeywordOn
0x180043195  test    al, al
0x180043197  jz      loc_180043386
0x18004319d  lea     rax, [rbp+170h+var_1E8]
0x1800431a1  mov     [rbp+170h+var_1E8], 1
0x1800431a8  mov     [rbp+170h+var_170], rax
0x1800431ac  lea     rdx, byte_180059EE7
0x1800431b3  lea     rax, [rbp+170h+var_1C8]
0x1800431b7  mov     [rbp+170h+var_168], 4
0x1800431bf  mov     [rbp+170h+var_160], rax
0x1800431c3  lea     rax, [rbp+170h+var_1E4]
0x1800431c7  mov     [rbp+170h+var_150], rax
0x1800431cb  lea     rax, [rbp+170h+var_1E0]
0x1800431cf  mov     [rbp+170h+var_140], rax
0x1800431d3  lea     rax, [rbp+170h+var_1DC]
0x1800431d7  mov     [rbp+170h+var_130], rax
0x1800431db  lea     rax, [rbp+170h+var_1C0]
0x1800431df  mov     [rbp+170h+var_120], rax
0x1800431e3  lea     rax, [rdi+20h]
0x1800431e7  mov     [rbp+170h+var_110], rax
0x1800431eb  mov     eax, [rdi+30h]
0x1800431ee  mov     [rbp+170h+var_1D8], eax
0x1800431f1  lea     rax, [rbp+170h+var_1D8]
0x1800431f5  mov     [rbp+170h+var_100], rax
0x1800431f9  mov     eax, [rdi+70h]
0x1800431fc  mov     [rbp+170h+var_1D4], eax
0x1800431ff  lea     rax, [rbp+170h+var_1D4]
0x180043203  mov     [rbp+170h+var_F0], rax
0x18004320a  mov     eax, [rdi+74h]
0x18004320d  mov     [rbp+170h+var_1D0], eax
0x180043210  lea     rax, [rbp+170h+var_1D0]
0x180043214  mov     [rbp+170h+var_E0], rax
0x18004321b  lea     rax, [rdi+840h]
0x180043222  mov     [rbp+170h+var_D0], rax
0x180043229  lea     rax, DhcpGlobalBootGuid
0x180043230  mov     [rbp+170h+var_C0], rax
0x180043237  mov     rax, [rdi+7A8h]
0x18004323e  mov     [rbp+170h+var_1B8], rax
0x180043242  lea     rax, [rbp+170h+var_1B8]
0x180043246  mov     [rbp+170h+var_B0], rax
0x18004324d  mov     eax, [rdi+1B8h]
0x180043253  mov     dword ptr [rbp+170h+pullResult], eax
0x180043256  lea     rax, [rbp+170h+pullResult]
0x18004325a  mov     [rbp+170h+var_A0], rax
0x180043261  mov     rax, [rdi+1C0h]
0x180043268  mov     [rbp+170h+var_1B0], rax
0x18004326c  lea     rax, [rbp+170h+var_1B0]
0x180043270  mov     [rbp+170h+var_90], rax
0x180043277  mov     rax, [rdi+1C8h]
0x18004327e  mov     [rbp+170h+var_1A8], rax
0x180043282  lea     rax, [rbp+170h+var_1A8]
0x180043286  mov     [rbp+170h+var_80], rax
0x18004328d  mov     rax, [rdi+1D0h]
0x180043294  mov     [rbp+170h+var_1A0], rax
0x180043298  lea     rax, [rbp+170h+var_1A0]
0x18004329c  mov     [rbp+170h+var_70], rax
0x1800432a3  lea     rax, [rbp+170h+var_198]
0x1800432a7  mov     [rbp+170h+var_60], rax
0x1800432ae  lea     rax, [rbp+170h+var_190]
0x1800432b2  mov     [rsp+290h+var_268], rax
0x1800432b7  mov     dword ptr [rsp+290h+var_270], 14h
0x1800432bf  mov     [rbp+170h+var_1C8], rbx
0x1800432c3  mov     [rbp+170h+var_158], 8
0x1800432cb  mov     [rbp+170h+var_1E4], r15d
0x1800432cf  mov     [rbp+170h+var_148], 4
0x1800432d7  mov     [rbp+170h+var_1E0], r14d
0x1800432db  mov     [rbp+170h+var_138], 4
0x1800432e3  mov     [rbp+170h+var_1DC], r12d
0x1800432e7  mov     [rbp+170h+var_128], 4
0x1800432ef  mov     [rbp+170h+var_1C0], rsi
0x1800432f3  mov     [rbp+170h+var_118], 8
0x1800432fb  mov     [rbp+170h+var_108], 10h
0x180043303  mov     [rbp+170h+var_F8], 4
0x18004330b  mov     [rbp+170h+var_E8], 4
0x180043316  mov     [rbp+170h+var_D8], 4
0x180043321  mov     [rbp+170h+var_C8], 10h
0x18004332c  mov     [rbp+170h+var_B8], 10h
0x180043337  mov     [rbp+170h+var_A8], 8
0x180043342  mov     [rbp+170h+var_98], 4
0x18004334d  mov     [rbp+170h+var_88], 8
0x180043358  mov     [rbp+170h+var_78], 8
0x180043363  mov     [rbp+170h+var_68], 8
0x18004336e  mov     [rbp+170h+var_198], 1000000h
0x180043376  mov     [rbp+170h+var_58], 8
0x180043381  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180043386  mov     rcx, [rbp+170h+var_50]
0x18004338d  xor     rcx, rsp; StackCookie
0x180043390  call    __security_check_cookie
0x180043395  add     rsp, 258h
0x18004339c  pop     r15
0x18004339e  pop     r14
0x1800433a0  pop     r13
0x1800433a2  pop     r12
0x1800433a4  pop     rdi
0x1800433a5  pop     rsi
0x1800433a6  pop     rbx
0x1800433a7  pop     rbp
0x1800433a8  retn
```
