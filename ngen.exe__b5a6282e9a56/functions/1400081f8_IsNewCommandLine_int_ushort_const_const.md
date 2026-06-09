# IsNewCommandLine(int,ushort const * * const)

- ea: `0x1400081f8`
- end: `0x140008413`
- name: `?IsNewCommandLine@@YA_NHQEAPEBG@Z`
- size: `539`
- prototype: `char __fastcall(int, const unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009104`

## callees

- `0x140004694`
- `0x140004b08`
- `0x1400072ec`
- `0x140007f1c`
- `0x1400081f8`
- `0x140008414`
- `0x140013f30`

## string_xrefs

- `0x1400083b7`: `All compilation targets are up to date.\n`

## pseudocode

```c
char __fastcall IsNewCommandLine(int a1, const unsigned __int16 **const a2)
{
  char v2; // di
  int v3; // eax
  int v4; // eax
  struct ICorSvc *CorService; // rbx
  int v7; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v8; // [rsp+48h] [rbp-B8h] BYREF
  int v9; // [rsp+50h] [rbp-B0h]
  __int64 v10; // [rsp+58h] [rbp-A8h]
  int v11; // [rsp+60h] [rbp-A0h]
  __int64 v12; // [rsp+68h] [rbp-98h] BYREF
  int v13; // [rsp+70h] [rbp-90h]
  __int64 v14; // [rsp+78h] [rbp-88h] BYREF
  int v15; // [rsp+80h] [rbp-80h]
  int v16; // [rsp+88h] [rbp-78h]
  __int64 v17; // [rsp+90h] [rbp-70h] BYREF
  int v18; // [rsp+98h] [rbp-68h]
  __int64 v19; // [rsp+A0h] [rbp-60h] BYREF
  int v20; // [rsp+A8h] [rbp-58h]
  __int64 v21; // [rsp+B0h] [rbp-50h] BYREF
  int v22; // [rsp+B8h] [rbp-48h]
  __int64 v23; // [rsp+C0h] [rbp-40h]
  __int64 v24; // [rsp+C8h] [rbp-38h]
  __int128 v25; // [rsp+D0h] [rbp-30h]
  __m128i si128; // [rsp+E0h] [rbp-20h]
  __int64 v27; // [rsp+F0h] [rbp-10h] BYREF
  int v28; // [rsp+F8h] [rbp-8h]
  __int64 v29; // [rsp+100h] [rbp+0h] BYREF
  int v30; // [rsp+108h] [rbp+8h]
  int v31; // [rsp+110h] [rbp+10h]
  __int64 v32; // [rsp+118h] [rbp+18h]
  int v33; // [rsp+120h] [rbp+20h]
  __int64 *v34; // [rsp+130h] [rbp+30h]
  __int64 *v35; // [rsp+138h] [rbp+38h]
  __int64 *v36; // [rsp+140h] [rbp+40h]
  __int64 *v37; // [rsp+148h] [rbp+48h]
  __int64 *v38; // [rsp+150h] [rbp+50h]
  __int64 *v39; // [rsp+158h] [rbp+58h]
  __int64 *v40; // [rsp+160h] [rbp+60h]
  __int64 *v41; // [rsp+168h] [rbp+68h]
  void ***v42; // [rsp+1A0h] [rbp+A0h] BYREF
  void **v43; // [rsp+1A8h] [rbp+A8h] BYREF

  v43 = &CNGenParserCallback::`vftable';
  v42 = &v43;
  v34 = &v8;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v2 = 1;
  v11 = 1;
  v35 = &v12;
  v12 = 0;
  v13 = 0;
  v36 = &v14;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v37 = &v17;
  v17 = 0;
  v18 = 0;
  v38 = &v19;
  v19 = 0;
  v20 = 0;
  v39 = &v21;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffff000000030000000200000000);
  v40 = &v27;
  v27 = 0;
  v28 = 0;
  v41 = &v29;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  if ( NGenParser::ParseNewCommandLineHelper((NGenParser *)&v42, a1, a2, (struct NewCommandLineOptions *)&v7) )
  {
    if ( (v7 & 0xFFFFFFF9) == 0 && v7 != 6 )
    {
      v3 = dword_1400270F4;
      if ( !(_DWORD)v25 )
        v3 = 1;
      dword_1400270F4 = v3;
    }
    v4 = dword_1400270F0;
    if ( si128.m128i_i32[1] != 2 )
      v4 = si128.m128i_i32[1];
    dword_1400270F0 = v4;
    CorService = GetCorService();
    NGenParser::ProcessNewCommandLineOptionsHelper(
      (NGenParser *)&v42,
      (struct NewCommandLineOptions *)&v7,
      CorService,
      (struct ICompileProgressNotification *)cCompileProgressNotification,
      (struct ICorSvcLogger *)off_1400270E0);
    if ( dword_1400270F4 && dword_1400270F8 && !dword_1400270FC )
      CCompileProgressNotification::LogWorker(
        cCompileProgressNotification,
        2,
        L"All compilation targets are up to date.\n");
    if ( CorService )
      (*(void (__fastcall **)(struct ICorSvc *))(*(_QWORD *)CorService + 16LL))(CorService);
  }
  else
  {
    v2 = 0;
  }
  NewCommandLineOptions::~NewCommandLineOptions((NewCommandLineOptions *)&v7);
  return v2;
}

```

## disassembly

```asm
0x1400081f8  mov     [rsp-8+arg_0], rbx
0x1400081fd  mov     [rsp-8+arg_8], rsi
0x140008202  push    rbp
0x140008203  push    rdi
0x140008204  push    r14
0x140008206  lea     rbp, [rsp-70h]
0x14000820b  sub     rsp, 170h
0x140008212  lea     rax, ??_7CNGenParserCallback@@6B@; const CNGenParserCallback::`vftable'
0x140008219  mov     [rbp+80h+arg_18], rax
0x140008220  lea     rax, [rbp+80h+arg_18]
0x140008227  mov     [rbp+80h+arg_10], rax
0x14000822e  lea     rax, [rsp+180h+var_138]
0x140008233  mov     [rbp+80h+var_50], rax
0x140008237  xor     r14d, r14d
0x14000823a  mov     [rsp+180h+var_138], r14
0x14000823f  mov     [rsp+180h+var_130], r14d
0x140008244  mov     [rsp+180h+var_128], r14
0x140008249  lea     edi, [r14+1]
0x14000824d  mov     [rsp+180h+var_120], edi
0x140008251  lea     rax, [rsp+180h+var_118]
0x140008256  mov     [rbp+80h+var_48], rax
0x14000825a  mov     [rsp+180h+var_118], r14
0x14000825f  mov     [rsp+180h+var_110], r14d
0x140008264  lea     rax, [rsp+180h+var_108]
0x140008269  mov     [rbp+80h+var_40], rax
0x14000826d  mov     [rsp+180h+var_108], r14
0x140008272  mov     [rbp+80h+var_100], r14d
0x140008276  mov     [rbp+80h+var_F8], r14d
0x14000827a  lea     rax, [rbp+80h+var_F0]
0x14000827e  mov     [rbp+80h+var_38], rax
0x140008282  mov     [rbp+80h+var_F0], r14
0x140008286  mov     [rbp+80h+var_E8], r14d
0x14000828a  lea     rax, [rbp+80h+var_E0]
0x14000828e  mov     [rbp+80h+var_30], rax
0x140008292  mov     [rbp+80h+var_E0], r14
0x140008296  mov     [rbp+80h+var_D8], r14d
0x14000829a  lea     rax, [rbp+80h+var_D0]
0x14000829e  mov     [rbp+80h+var_28], rax
0x1400082a2  mov     [rbp+80h+var_D0], r14
0x1400082a6  mov     [rbp+80h+var_C8], r14d
0x1400082aa  mov     [rbp+80h+var_C0], r14
0x1400082ae  mov     [rbp+80h+var_B8], r14
0x1400082b2  xorps   xmm0, xmm0
0x1400082b5  movdqa  [rbp+80h+var_B0], xmm0
0x1400082ba  movdqa  xmm1, cs:__xmm@ffffffff000000030000000200000000
0x1400082c2  movdqa  [rbp+80h+var_A0], xmm1
0x1400082c7  lea     rax, [rbp+80h+var_90]
0x1400082cb  mov     [rbp+80h+var_20], rax
0x1400082cf  mov     [rbp+80h+var_90], r14
0x1400082d3  mov     [rbp+80h+var_88], r14d
0x1400082d7  lea     rax, [rbp+80h+var_80]
0x1400082db  mov     [rbp+80h+var_18], rax
0x1400082df  mov     [rbp+80h+var_80], r14
0x1400082e3  mov     [rbp+80h+var_78], r14d
0x1400082e7  mov     [rbp+80h+var_70], r14d
0x1400082eb  lea     rax, [rbp+80h+var_68]
0x1400082ef  mov     [rsp+180h+var_150], rax
0x1400082f4  mov     [rbp+80h+var_68], r14
0x1400082f8  mov     [rbp+80h+var_60], r14d
0x1400082fc  lea     r9, [rsp+180h+var_140]; struct NewCommandLineOptions *
0x140008301  mov     r8, rdx; unsigned __int16 **
0x140008304  mov     edx, ecx; int
0x140008306  lea     rcx, [rbp+80h+arg_10]; this
0x14000830d  call    ?ParseNewCommandLineHelper@NGenParser@@AEAA_NHQEAPEBGAEAUNewCommandLineOptions@@@Z; NGenParser::ParseNewCommandLineHelper(int,ushort const * * const,NewCommandLineOptions &)
0x140008312  test    al, al
0x140008314  jnz     short loc_14000831E
0x140008316  mov     dil, r14b
0x140008319  jmp     loc_1400083EE
0x14000831e  test    [rsp+180h+var_140], 0FFFFFFF9h
0x140008326  jnz     short loc_140008342
0x140008328  cmp     [rsp+180h+var_140], 6
0x14000832d  jz      short loc_140008342
0x14000832f  mov     eax, cs:dword_1400270F4
0x140008335  cmp     dword ptr [rbp+80h+var_B0], r14d
0x140008339  cmovz   eax, edi
0x14000833c  mov     cs:dword_1400270F4, eax
0x140008342  mov     eax, cs:dword_1400270F0
0x140008348  cmp     dword ptr [rbp+80h+var_A0+4], 2
0x14000834c  cmovnz  eax, dword ptr [rbp+80h+var_A0+4]
0x140008350  mov     cs:dword_1400270F0, eax
0x140008356  call    ?GetCorService@@YAPEAUICorSvc@@XZ; GetCorService(void)
0x14000835b  mov     rbx, rax
0x14000835e  mov     [rsp+180h+var_150], rax
0x140008363  mov     [rsp+180h+var_148], r14d
0x140008368  mov     esi, r14d
0x14000836b  test    rax, rax
0x14000836e  cmovnz  esi, edi
0x140008371  mov     [rsp+180h+var_148], esi
0x140008375  lea     rax, off_1400270E0
0x14000837c  mov     [rsp+180h+var_160], rax; struct ICorSvcLogger *
0x140008381  lea     r9, ?cCompileProgressNotification@@3VCCompileProgressNotification@@A; struct ICompileProgressNotification *
0x140008388  mov     r8, rbx; struct ICorSvc *
0x14000838b  lea     rdx, [rsp+180h+var_140]; struct NewCommandLineOptions *
0x140008390  lea     rcx, [rbp+80h+arg_10]; this
0x140008397  call    ?ProcessNewCommandLineOptionsHelper@NGenParser@@AEAAXAEAUNewCommandLineOptions@@PEAUICorSvc@@PEAUICompileProgressNotification@@PEAUICorSvcLogger@@@Z; NGenParser::ProcessNewCommandLineOptionsHelper(NewCommandLineOptions &,ICorSvc *,ICompileProgressNotification *,ICorSvcLogger *)
0x14000839c  cmp     cs:dword_1400270F4, r14d
0x1400083a3  jz      short loc_1400083D0
0x1400083a5  cmp     cs:dword_1400270F8, r14d
0x1400083ac  jz      short loc_1400083D0
0x1400083ae  cmp     cs:dword_1400270FC, r14d
0x1400083b5  jnz     short loc_1400083D0
0x1400083b7  lea     r8, aAllCompilation; "All compilation targets are up to date."...
0x1400083be  mov     edx, 2
0x1400083c3  lea     rcx, ?cCompileProgressNotification@@3VCCompileProgressNotification@@A; CCompileProgressNotification cCompileProgressNotification
0x1400083ca  call    ?LogWorker@CCompileProgressNotification@@AEAAXW4CorSvcLogLevel@@PEAGZZ; CCompileProgressNotification::LogWorker(CorSvcLogLevel,ushort *,...)
0x1400083cf  nop
0x1400083d0  test    esi, esi
0x1400083d2  jz      short loc_1400083EE
0x1400083d4  test    rbx, rbx
0x1400083d7  jz      short loc_1400083E9
0x1400083d9  mov     rcx, [rbx]
0x1400083dc  mov     rax, [rcx+10h]
0x1400083e0  mov     rcx, rbx
0x1400083e3  call    cs:__guard_dispatch_icall_fptr
0x1400083e9  mov     [rsp+180h+var_148], r14d
0x1400083ee  lea     rcx, [rsp+180h+var_140]; this
0x1400083f3  call    ??1NewCommandLineOptions@@QEAA@XZ; NewCommandLineOptions::~NewCommandLineOptions(void)
0x1400083f8  mov     al, dil
0x1400083fb  lea     r11, [rsp+180h+var_10]
0x140008403  mov     rbx, [r11+20h]
0x140008407  mov     rsi, [r11+28h]
0x14000840b  mov     rsp, r11
0x14000840e  pop     r14
0x140008410  pop     rdi
0x140008411  pop     rbp
0x140008412  retn
```
