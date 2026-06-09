# CUSTOM_ERROR_HANDLER::SetupOneLiner(IHttpContext *,ushort)

- ea: `0x18000518c`
- end: `0x18000535a`
- name: `?SetupOneLiner@CUSTOM_ERROR_HANDLER@@QEAAJPEAVIHttpContext@@G@Z`
- size: `462`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_HANDLER *__hidden this, struct IHttpContext *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800012c0`

## callees

- `0x180002c88`
- `0x18000518c`
- `0x180007870`
- `0x180008010`

## import_xrefs

- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x1800052a7`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x1800052a7`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000528e`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000528e`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800052f0`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800052f0`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000520c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000520c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005335`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005335`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800052e2`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800052e2`

## pseudocode

```c
__int64 __fastcall CUSTOM_ERROR_HANDLER::SetupOneLiner(const char **this, struct IHttpContext *a2, unsigned __int16 a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v5)(struct IHttpContext *); // rax
  __int64 v7; // rsi
  int DetailedErrorResources; // ebx
  __int64 v9; // rax
  unsigned int CCH; // eax
  unsigned int v12; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v13; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v14; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v15; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v16; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v17; // [rsp+64h] [rbp-9Ch] BYREF
  int v18; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v19; // [rsp+70h] [rbp-90h] BYREF
  __int128 v20; // [rsp+78h] [rbp-88h] BYREF
  __int128 v21; // [rsp+88h] [rbp-78h]
  _BYTE v22[56]; // [rsp+98h] [rbp-68h] BYREF
  char v23[256]; // [rsp+D0h] [rbp-30h] BYREF

  v3 = *(_QWORD *)a2;
  v19 = 0;
  v17 = 0;
  v12 = 0;
  v5 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 32);
  v16 = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  v7 = v5(a2);
  STRA::STRA((STRA *)v22, v23, 0x100u);
  v18 = 0;
  v20 = 0;
  v21 = 0;
  DetailedErrorResources = CUSTOM_ERROR_HANDLER::FindDetailedErrorResources(
                             (CUSTOM_ERROR_HANDLER *)this,
                             a3,
                             0,
                             0,
                             &v12,
                             &v16,
                             &v15,
                             &v14,
                             &v13);
  if ( DetailedErrorResources >= 0 )
  {
    DetailedErrorResources = LANG_STRING::GetString(
                               (LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString,
                               v12,
                               this[4],
                               &v19,
                               &v17);
    if ( DetailedErrorResources >= 0 )
    {
      DetailedErrorResources = STRA::CopyWToUTF8Unescaped((STRA *)v22, v19);
      if ( DetailedErrorResources >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
        *(_QWORD *)(v9 + 256) = "text/html";
        *(_WORD *)(v9 + 248) = 9;
        LODWORD(v20) = 0;
        *((_QWORD *)&v20 + 1) = STRA::QueryStr((STRA *)v22);
        CCH = STRA::QueryCCH((STRA *)v22);
        *((_DWORD *)this + 6) = 0;
        LODWORD(v21) = CCH;
        DetailedErrorResources = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, _DWORD, int *, _QWORD))(*(_QWORD *)v7 + 168LL))(
                                   v7,
                                   &v20,
                                   1,
                                   0,
                                   0,
                                   &v18,
                                   0);
      }
    }
  }
  STRA::~STRA((STRA *)v22);
  return (unsigned int)DetailedErrorResources;
}

```

## disassembly

```asm
0x18000518c  push    rbp
0x18000518e  push    rbx
0x18000518f  push    rsi
0x180005190  push    rdi
0x180005191  push    r14
0x180005193  lea     rbp, [rsp-0E0h]
0x18000519b  sub     rsp, 1E0h
0x1800051a2  mov     rax, cs:__security_cookie
0x1800051a9  xor     rax, rsp
0x1800051ac  mov     [rbp+100h+var_30], rax
0x1800051b3  mov     rax, [rdx]
0x1800051b6  xor     r14d, r14d
0x1800051b9  xorps   xmm0, xmm0
0x1800051bc  mov     [rsp+200h+var_190], r14
0x1800051c1  mov     rdi, rcx
0x1800051c4  mov     [rsp+200h+var_19C], r14d
0x1800051c9  mov     rcx, rdx
0x1800051cc  mov     [rsp+200h+var_1B0], r14d
0x1800051d1  mov     rax, [rax+20h]
0x1800051d5  movzx   ebx, r8w
0x1800051d9  mov     [rsp+200h+var_1A0], r14d
0x1800051de  mov     [rsp+200h+var_1A4], r14d
0x1800051e3  mov     [rsp+200h+var_1A8], r14d
0x1800051e8  mov     [rsp+200h+var_1AC], r14d
0x1800051ed  movups  [rsp+200h+var_188], xmm0
0x1800051f2  movups  [rbp+100h+var_178], xmm0
0x1800051f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051fb  mov     r8d, 100h
0x180005201  lea     rdx, [rbp+100h+var_130]
0x180005205  lea     rcx, [rbp+100h+var_168]
0x180005209  mov     rsi, rax
0x18000520c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180005212  xorps   xmm0, xmm0
0x180005215  mov     [rsp+200h+var_198], r14d
0x18000521a  lea     rax, [rsp+200h+var_1AC]
0x18000521f  xor     r8d, r8d; unsigned __int16
0x180005222  mov     [rsp+200h+var_1C0], rax; unsigned int *
0x180005227  xor     r9d, r9d; int
0x18000522a  lea     rax, [rsp+200h+var_1A8]
0x18000522f  movzx   edx, bx; unsigned __int16
0x180005232  mov     [rsp+200h+var_1C8], rax; unsigned int *
0x180005237  mov     rcx, rdi; this
0x18000523a  lea     rax, [rsp+200h+var_1A4]
0x18000523f  mov     [rsp+200h+var_1D0], rax; unsigned int *
0x180005244  lea     rax, [rsp+200h+var_1A0]
0x180005249  mov     [rsp+200h+var_1D8], rax; unsigned int *
0x18000524e  lea     rax, [rsp+200h+var_1B0]
0x180005253  mov     [rsp+200h+var_1E0], rax; unsigned int *
0x180005258  movups  [rsp+200h+var_188], xmm0
0x18000525d  movups  [rbp+100h+var_178], xmm0
0x180005261  call    ?FindDetailedErrorResources@CUSTOM_ERROR_HANDLER@@AEAAJGGJPEAI0000@Z; CUSTOM_ERROR_HANDLER::FindDetailedErrorResources(ushort,ushort,long,uint *,uint *,uint *,uint *,uint *)
0x180005266  mov     ebx, eax
0x180005268  test    eax, eax
0x18000526a  js      loc_180005331
0x180005270  mov     r8, [rdi+20h]
0x180005274  lea     rax, [rsp+200h+var_19C]
0x180005279  mov     edx, [rsp+200h+var_1B0]
0x18000527d  lea     r9, [rsp+200h+var_190]
0x180005282  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180005289  mov     [rsp+200h+var_1E0], rax
0x18000528e  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180005294  mov     ebx, eax
0x180005296  test    eax, eax
0x180005298  js      loc_180005331
0x18000529e  mov     rdx, [rsp+200h+var_190]
0x1800052a3  lea     rcx, [rbp+100h+var_168]
0x1800052a7  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x1800052ad  mov     ebx, eax
0x1800052af  test    eax, eax
0x1800052b1  js      short loc_180005331
0x1800052b3  mov     rax, [rsi]
0x1800052b6  mov     rcx, rsi
0x1800052b9  mov     rax, [rax+8]
0x1800052bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c2  lea     rcx, aTextHtml; "text/html"
0x1800052c9  mov     [rax+100h], rcx
0x1800052d0  lea     rcx, [rbp+100h+var_168]
0x1800052d4  mov     word ptr [rax+0F8h], 9
0x1800052dd  mov     dword ptr [rsp+200h+var_188], r14d
0x1800052e2  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800052e8  lea     rcx, [rbp+100h+var_168]
0x1800052ec  mov     qword ptr [rbp+100h+var_188+8], rax
0x1800052f0  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800052f6  mov     [rdi+18h], r14d
0x1800052fa  lea     rcx, [rsp+200h+var_198]
0x1800052ff  mov     dword ptr [rbp+100h+var_178], eax
0x180005302  lea     r8d, [r14+1]
0x180005306  mov     rax, [rsi]
0x180005309  lea     rdx, [rsp+200h+var_188]
0x18000530e  mov     [rsp+200h+var_1D0], r14
0x180005313  xor     r9d, r9d
0x180005316  mov     [rsp+200h+var_1D8], rcx
0x18000531b  mov     rcx, rsi
0x18000531e  mov     dword ptr [rsp+200h+var_1E0], r14d
0x180005323  mov     rax, [rax+0A8h]
0x18000532a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000532f  mov     ebx, eax
0x180005331  lea     rcx, [rbp+100h+var_168]
0x180005335  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000533b  mov     eax, ebx
0x18000533d  mov     rcx, [rbp+100h+var_30]
0x180005344  xor     rcx, rsp; StackCookie
0x180005347  call    __security_check_cookie
0x18000534c  add     rsp, 1E0h
0x180005353  pop     r14
0x180005355  pop     rdi
0x180005356  pop     rsi
0x180005357  pop     rbx
0x180005358  pop     rbp
0x180005359  retn
```
