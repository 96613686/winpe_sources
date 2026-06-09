# ExecuteNGenCommand(ushort const *,ICompileProgressNotification *,ICorSvcLogger *,bool,AssemblyExclusion &)

- ea: `0x180011e5c`
- end: `0x180012409`
- name: `?ExecuteNGenCommand@@YAXPEBGPEAUICompileProgressNotification@@PEAUICorSvcLogger@@_NAEAVAssemblyExclusion@@@Z`
- size: `1453`
- prototype: `void __fastcall(const unsigned __int16 *, struct ICompileProgressNotification *, struct ICorSvcLogger *, char, struct AssemblyExclusion *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180012884`

## callees

- `0x180001d80`
- `0x180001da0`
- `0x180002504`
- `0x180002dec`
- `0x180008780`
- `0x1800100bc`
- `0x180010530`
- `0x180011b00`
- `0x180011e5c`
- `0x18001240c`
- `0x18002e418`
- `0x180032654`
- `0x180034fd4`
- `0x1800350c4`
- `0x1800361a0`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180012129`
- `KERNEL32!HeapFree` at `0x1800122df`
- `KERNEL32!HeapFree` at `0x180012129`
- `KERNEL32!HeapFree` at `0x1800122df`
- `KERNEL32!GetProcessHeap` at `0x180012114`
- `KERNEL32!GetProcessHeap` at `0x1800122ca`
- `KERNEL32!GetProcessHeap` at `0x180012114`
- `KERNEL32!GetProcessHeap` at `0x1800122ca`

## string_xrefs

- `0x180011eff`: `Executing command from offline queue: %s\n`
- `0x180012317`: `Error parsing command line in offline Queue\n`
- `0x180012343`: `error parsing the command line passed to the offline queue`
- `0x180012365`: `Error:  NGen Queue command must be install, uninstall or update\n`
- `0x1800123b3`: `Error:  NGen Queue command cannot be uninstall *\n`
- `0x180012137`: `Exclusion list entry found for %s; it will not be installed\n`
- `0x180012240`: `Successfully executed command from the offline queue: %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall ExecuteNGenCommand(
        const unsigned __int16 *a1,
        struct ICompileProgressNotification *a2,
        struct ICorSvcLogger *a3,
        char a4,
        struct AssemblyExclusion *a5)
{
  const unsigned __int16 **v9; // rax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rax
  unsigned int v13; // ebx
  char v14; // bl
  void *v15; // rdi
  HANDLE ProcessHeap; // rax
  int Svc; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  void *v21; // rbx
  HANDLE v22; // rax
  __int64 v23; // rdx
  const struct SString *v24; // rax
  __int64 v25; // rdx
  const struct SString *v26; // rax
  __int64 v27; // rdx
  const struct SString *v28; // rax
  _DWORD v29[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v30; // [rsp+40h] [rbp-C0h]
  LPVOID lpMem; // [rsp+48h] [rbp-B8h]
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+58h] [rbp-A8h]
  struct ICorSvc *v34; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+68h] [rbp-98h]
  unsigned int v36; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v37[2]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v38; // [rsp+88h] [rbp-78h] BYREF
  struct ICorSvc **v39; // [rsp+90h] [rbp-70h]
  int v40; // [rsp+A0h] [rbp-60h] BYREF
  _WORD *v41; // [rsp+A8h] [rbp-58h] BYREF
  int v42; // [rsp+B0h] [rbp-50h]
  __int64 v43; // [rsp+B8h] [rbp-48h]
  int v44; // [rsp+C0h] [rbp-40h]
  __int64 v45; // [rsp+C8h] [rbp-38h] BYREF
  int v46; // [rsp+D0h] [rbp-30h]
  __int64 v47; // [rsp+D8h] [rbp-28h] BYREF
  int v48; // [rsp+E0h] [rbp-20h]
  int v49; // [rsp+E8h] [rbp-18h]
  __int64 v50; // [rsp+F0h] [rbp-10h] BYREF
  int v51; // [rsp+F8h] [rbp-8h]
  __int64 v52; // [rsp+100h] [rbp+0h] BYREF
  int v53; // [rsp+108h] [rbp+8h]
  __int64 v54; // [rsp+110h] [rbp+10h] BYREF
  int v55; // [rsp+118h] [rbp+18h]
  __int64 v56; // [rsp+120h] [rbp+20h]
  __int64 v57; // [rsp+128h] [rbp+28h]
  __int128 v58; // [rsp+130h] [rbp+30h]
  __m128i si128; // [rsp+140h] [rbp+40h]
  __int64 v60; // [rsp+150h] [rbp+50h] BYREF
  int v61; // [rsp+158h] [rbp+58h]
  __int64 v62; // [rsp+160h] [rbp+60h] BYREF
  int v63; // [rsp+168h] [rbp+68h]
  int v64; // [rsp+170h] [rbp+70h]
  __int64 v65; // [rsp+178h] [rbp+78h] BYREF
  int v66; // [rsp+180h] [rbp+80h]
  _WORD **v67; // [rsp+190h] [rbp+90h]
  __int64 *v68; // [rsp+198h] [rbp+98h]
  __int64 *v69; // [rsp+1A0h] [rbp+A0h]
  __int64 *v70; // [rsp+1A8h] [rbp+A8h]
  __int64 *v71; // [rsp+1B0h] [rbp+B0h]
  __int64 *v72; // [rsp+1B8h] [rbp+B8h]
  __int64 *v73; // [rsp+1C0h] [rbp+C0h]
  __int64 *v74; // [rsp+1C8h] [rbp+C8h]
  _BYTE v75[24]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v76[24]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v77[32]; // [rsp+200h] [rbp+100h] BYREF
  int v78; // [rsp+220h] [rbp+120h] BYREF
  __int64 v79; // [rsp+224h] [rbp+124h]
  LPVOID v80; // [rsp+230h] [rbp+130h]
  __int16 v81; // [rsp+238h] [rbp+138h] BYREF

  v37[0] = &CNGenParserCallback::`vftable';
  v37[1] = a3;
  v38 = v37;
  v79 = 512;
  v80 = &v81;
  v78 = 2;
  v81 = 0;
  SString::Printf((SString *)&v78, L"Executing command from offline queue: %s\n", a1);
  CNGenParserCallback::Output((CNGenParserCallback *)v37, (const struct SString *)&v78);
  v9 = (const unsigned __int16 **)SegmentCommandLine(a1, &v36);
  v67 = &v41;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 1;
  v68 = &v45;
  v45 = 0;
  v46 = 0;
  v69 = &v47;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v70 = &v50;
  v50 = 0;
  v51 = 0;
  v71 = &v52;
  v52 = 0;
  v53 = 0;
  v72 = &v54;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffff000000030000000200000000);
  v73 = &v60;
  v60 = 0;
  v61 = 0;
  v74 = &v62;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v39 = (struct ICorSvc **)&v65;
  v65 = 0;
  v66 = 0;
  if ( !NGenParser::ParseNewCommandLineHelper((NGenParser *)&v38, v36, v9, (struct NewCommandLineOptions *)&v40) )
  {
    SString::SString((SString *)v29, L"Error parsing command line in offline Queue\n");
    CNGenParserCallback::Output((CNGenParserCallback *)v37, (const struct SString *)v29);
    WriteBuffer::~WriteBuffer((WriteBuffer *)v29);
    v24 = (const struct SString *)SString::SString(
                                    v75,
                                    v23,
                                    L"error parsing the command line passed to the offline queue");
    ThrowHR(-2147024736, v24);
  }
  v10 = (__int64)v41;
  if ( v40 )
  {
    if ( v40 == 1 )
    {
      if ( v41 && *v41 == 42 && !v41[1] )
      {
        SString::SString((SString *)v29, L"Error:  NGen Queue command cannot be uninstall *\n");
        CNGenParserCallback::Output((CNGenParserCallback *)v37, (const struct SString *)v29);
        WriteBuffer::~WriteBuffer((WriteBuffer *)v29);
        v28 = (const struct SString *)SString::SString(
                                        v77,
                                        v27,
                                        L"requested action is not supported by the offline queue");
        ThrowHR(-2147024736, v28);
      }
    }
    else if ( v40 != 2 )
    {
      SString::SString((SString *)v29, L"Error:  NGen Queue command must be install, uninstall or update\n");
      CNGenParserCallback::Output((CNGenParserCallback *)v37, (const struct SString *)v29);
      WriteBuffer::~WriteBuffer((WriteBuffer *)v29);
      v26 = (const struct SString *)SString::SString(
                                      v76,
                                      v25,
                                      L"requested action is not supported by the offline queue");
      ThrowHR(-2147024736, v26);
    }
  }
  v11 = v58;
  if ( !(_DWORD)v58 )
    v11 = 1;
  LODWORD(v58) = v11;
  if ( !a4 || v40 )
    goto LABEL_27;
  v12 = -1;
  do
    ++v12;
  while ( v41[v12] );
  v29[0] = 2 * v12 + 2;
  v29[1] = v29[0];
  lpMem = v41;
  v10 = 4294967288LL;
  v30 = 276;
  v13 = 0;
  if ( (*(_DWORD *)a5 & 0xFFFFFFF8) != 0 )
  {
    while ( !(unsigned int)SString::EqualsCaseInsensitive(
                             *(SString **)(*((_QWORD *)a5 + 2) + 8LL * v13),
                             (const struct SString *)v29) )
    {
      if ( ++v13 >= *(_DWORD *)a5 >> 3 )
        goto LABEL_18;
    }
    v14 = 1;
  }
  else
  {
LABEL_18:
    v14 = 0;
  }
  if ( (v30 & 8) != 0 )
  {
    v15 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v15);
    }
  }
  if ( v14 )
  {
    SString::Printf((SString *)&v78, L"Exclusion list entry found for %s; it will not be installed\n", v41);
    CNGenParserCallback::Output((CNGenParserCallback *)v37, (const struct SString *)&v78);
    NewCommandLineOptions::~NewCommandLineOptions((NewCommandLineOptions *)&v40);
  }
  else
  {
LABEL_27:
    DWORD2(v58) = 1;
    v33 = 0;
    v39 = (struct ICorSvc **)&v32;
    v32 = 0;
    Svc = CorGetSvc(&v32, (const struct NoThrow *)v10);
    if ( Svc < 0 )
      ThrowHR(Svc);
    v18 = v33;
    if ( v32 )
      v18 = 1;
    v33 = v18;
    v35 = 0;
    v39 = &v34;
    v34 = 0;
    v19 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ICorSvc **))v32)(v32, &IID_ICorSvc, &v34);
    if ( v19 < 0 )
      ThrowHR(v19);
    v20 = v35;
    if ( v34 )
      v20 = 1;
    v35 = v20;
    NGenParser::ProcessNewCommandLineOptionsHelper(
      (NGenParser *)&v38,
      (struct NewCommandLineOptions *)&v40,
      v34,
      a2,
      a3);
    if ( NGENService::g_bProcessNGENService )
      NGENService::EventLog(
        0,
        0,
        0x452u,
        (unsigned int)L"Successfully executed command from the offline queue: %s\n",
        a1);
    if ( v35 )
    {
      if ( v34 )
        (*(void (__fastcall **)(struct ICorSvc *))(*(_QWORD *)v34 + 16LL))(v34);
      v35 = 0;
    }
    if ( v33 )
    {
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      v33 = 0;
    }
    NewCommandLineOptions::~NewCommandLineOptions((NewCommandLineOptions *)&v40);
  }
  if ( (v79 & 0x800000000LL) != 0 )
  {
    v21 = v80;
    if ( v80 )
    {
      v22 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v22 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v22;
      }
      HeapFree(v22, 0, v21);
    }
  }
}

```

## disassembly

```asm
0x180011e5c  mov     [rsp-8+arg_18], rbx
0x180011e61  push    rbp
0x180011e62  push    rsi
0x180011e63  push    rdi
0x180011e64  push    r12
0x180011e66  push    r13
0x180011e68  push    r14
0x180011e6a  push    r15
0x180011e6c  lea     rbp, [rsp-350h]
0x180011e74  sub     rsp, 450h
0x180011e7b  mov     rax, cs:__security_cookie
0x180011e82  xor     rax, rsp
0x180011e85  mov     [rbp+380h+var_40], rax
0x180011e8c  mov     bl, r9b
0x180011e8f  mov     r14, r8
0x180011e92  mov     r15, rdx
0x180011e95  mov     rsi, rcx
0x180011e98  mov     rdi, [rbp+380h+arg_20]
0x180011e9f  xor     r12d, r12d
0x180011ea2  mov     [rsp+480h+var_450], r12d
0x180011ea7  lea     rax, ??_7CNGenParserCallback@@6B@; const CNGenParserCallback::`vftable'
0x180011eae  mov     [rsp+480h+var_408], rax
0x180011eb3  mov     [rbp+380h+var_400], r8
0x180011eb7  lea     rax, [rsp+480h+var_408]
0x180011ebc  mov     [rbp+380h+var_3F8], rax
0x180011ec0  mov     [rbp+380h+var_260], r12
0x180011ec7  mov     [rbp+380h+var_260+4], 200h
0x180011ed2  mov     [rbp+380h+var_250], r12
0x180011ed9  lea     rax, [rbp+380h+var_248]
0x180011ee0  mov     [rbp+380h+var_250], rax
0x180011ee7  mov     dword ptr [rbp+380h+var_260], 2
0x180011ef1  mov     rax, [rbp+380h+var_250]
0x180011ef8  mov     [rax], r12w
0x180011efc  mov     r8, rcx
0x180011eff  lea     rdx, aExecutingComma; "Executing command from offline queue: %"...
0x180011f06  lea     rcx, [rbp+380h+var_260]; this
0x180011f0d  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180011f12  lea     rdx, [rbp+380h+var_260]; struct SString *
0x180011f19  lea     rcx, [rsp+480h+var_408]; this
0x180011f1e  call    ?Output@CNGenParserCallback@@UEAAXAEBVSString@@@Z; CNGenParserCallback::Output(SString const &)
0x180011f23  lea     rdx, [rsp+480h+var_410]; unsigned int *
0x180011f28  mov     rcx, rsi; unsigned __int16 *
0x180011f2b  call    ?SegmentCommandLine@@YAPEAPEAGPEBGPEAK@Z; SegmentCommandLine(ushort const *,ulong *)
0x180011f30  lea     rcx, [rbp+380h+var_3D8]
0x180011f34  mov     [rbp+380h+var_2F0], rcx
0x180011f3b  mov     [rbp+380h+var_3D8], r12
0x180011f3f  mov     [rbp+380h+var_3D0], r12d
0x180011f43  mov     [rbp+380h+var_3C8], r12
0x180011f47  lea     r13d, [r12+1]
0x180011f4c  mov     [rbp+380h+var_3C0], r13d
0x180011f50  lea     rcx, [rbp+380h+var_3B8]
0x180011f54  mov     [rbp+380h+var_2E8], rcx
0x180011f5b  mov     [rbp+380h+var_3B8], r12
0x180011f5f  mov     [rbp+380h+var_3B0], r12d
0x180011f63  lea     rcx, [rbp+380h+var_3A8]
0x180011f67  mov     [rbp+380h+var_2E0], rcx
0x180011f6e  mov     [rbp+380h+var_3A8], r12
0x180011f72  mov     [rbp+380h+var_3A0], r12d
0x180011f76  mov     [rbp+380h+var_398], r12d
0x180011f7a  lea     rcx, [rbp+380h+var_390]
0x180011f7e  mov     [rbp+380h+var_2D8], rcx
0x180011f85  mov     [rbp+380h+var_390], r12
0x180011f89  mov     [rbp+380h+var_388], r12d
0x180011f8d  lea     rcx, [rbp+380h+var_380]
0x180011f91  mov     [rbp+380h+var_2D0], rcx
0x180011f98  mov     [rbp+380h+var_380], r12
0x180011f9c  mov     [rbp+380h+var_378], r12d
0x180011fa0  lea     rcx, [rbp+380h+var_370]
0x180011fa4  mov     [rbp+380h+var_2C8], rcx
0x180011fab  mov     [rbp+380h+var_370], r12
0x180011faf  mov     [rbp+380h+var_368], r12d
0x180011fb3  mov     [rbp+380h+var_360], r12
0x180011fb7  mov     [rbp+380h+var_358], r12
0x180011fbb  xorps   xmm0, xmm0
0x180011fbe  movdqa  [rbp+380h+var_350], xmm0
0x180011fc3  movdqa  xmm1, cs:__xmm@ffffffff000000030000000200000000
0x180011fcb  movdqa  [rbp+380h+var_340], xmm1
0x180011fd0  lea     rcx, [rbp+380h+var_330]
0x180011fd4  mov     [rbp+380h+var_2C0], rcx
0x180011fdb  mov     [rbp+380h+var_330], r12
0x180011fdf  mov     [rbp+380h+var_328], r12d
0x180011fe3  lea     rcx, [rbp+380h+var_320]
0x180011fe7  mov     [rbp+380h+var_2B8], rcx
0x180011fee  mov     [rbp+380h+var_320], r12
0x180011ff2  mov     [rbp+380h+var_318], r12d
0x180011ff6  mov     [rbp+380h+var_310], r12d
0x180011ffa  lea     rcx, [rbp+380h+var_308]
0x180011ffe  mov     [rbp+380h+var_3F0], rcx
0x180012002  mov     [rbp+380h+var_308], r12
0x180012006  mov     [rbp+380h+var_300], r12d
0x18001200d  lea     r9, [rbp+380h+var_3E0]; struct NewCommandLineOptions *
0x180012011  mov     r8, rax; unsigned __int16 **
0x180012014  mov     edx, [rsp+480h+var_410]; int
0x180012018  lea     rcx, [rbp+380h+var_3F8]; this
0x18001201c  call    ?ParseNewCommandLineHelper@NGenParser@@AEAA_NHQEAPEBGAEAUNewCommandLineOptions@@@Z; NGenParser::ParseNewCommandLineHelper(int,ushort const * * const,NewCommandLineOptions &)
0x180012021  test    al, al
0x180012023  jz      loc_180012317
0x180012029  mov     rdx, [rbp+380h+var_3D8]
0x18001202d  mov     ecx, [rbp+380h+var_3E0]
0x180012030  test    ecx, ecx
0x180012032  jz      short loc_180012042
0x180012034  cmp     ecx, r13d
0x180012037  jz      short loc_180012047
0x180012039  cmp     ecx, 2
0x18001203c  jnz     loc_180012365
0x180012042  cmp     ecx, r13d
0x180012045  jnz     short loc_18001205D
0x180012047  test    rdx, rdx
0x18001204a  jz      short loc_18001205D
0x18001204c  cmp     word ptr [rdx], 2Ah ; '*'
0x180012050  jnz     short loc_18001205D
0x180012052  cmp     [rdx+2], r12w
0x180012057  jz      loc_1800123B3
0x18001205d  mov     eax, dword ptr [rbp+380h+var_350]
0x180012060  test    eax, eax
0x180012062  cmovz   eax, r13d
0x180012066  mov     dword ptr [rbp+380h+var_350], eax
0x180012069  test    bl, bl
0x18001206b  jz      loc_180012170
0x180012071  test    ecx, ecx
0x180012073  jnz     loc_180012170
0x180012079  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001207d  inc     rax
0x180012080  cmp     [rdx+rax*2], r12w
0x180012085  jnz     short loc_18001207D
0x180012087  lea     eax, ds:2[rax*2]
0x18001208e  mov     [rsp+480h+var_448], eax
0x180012092  mov     [rsp+480h+var_444], eax
0x180012096  mov     [rsp+480h+var_440], 10h
0x18001209e  mov     [rsp+480h+lpMem], rdx
0x1800120a3  mov     ecx, [rsp+480h+var_440]
0x1800120a7  mov     edx, 0FFFFFFF8h
0x1800120ac  and     ecx, edx
0x1800120ae  mov     [rsp+480h+var_440], ecx
0x1800120b2  mov     eax, ecx
0x1800120b4  or      eax, 4
0x1800120b7  mov     [rsp+480h+var_440], eax
0x1800120bb  or      ecx, 104h
0x1800120c1  mov     [rsp+480h+var_440], ecx
0x1800120c5  mov     ebx, r12d
0x1800120c8  test    [rdi], edx
0x1800120ca  jbe     short loc_1800120F4
0x1800120cc  mov     eax, ebx
0x1800120ce  mov     rcx, [rdi+10h]
0x1800120d2  lea     rdx, [rsp+480h+var_448]; struct SString *
0x1800120d7  mov     rcx, [rcx+rax*8]; this
0x1800120db  call    ?EqualsCaseInsensitive@SString@@QEBAHAEBV1@@Z; SString::EqualsCaseInsensitive(SString const &)
0x1800120e0  test    eax, eax
0x1800120e2  jnz     loc_18001216B
0x1800120e8  add     ebx, r13d
0x1800120eb  mov     eax, [rdi]
0x1800120ed  shr     eax, 3
0x1800120f0  cmp     ebx, eax
0x1800120f2  jb      short loc_1800120CC
0x1800120f4  mov     bl, r12b
0x1800120f7  test    byte ptr [rsp+480h+var_440], 8
0x1800120fc  jz      short loc_18001212F
0x1800120fe  mov     rdi, [rsp+480h+lpMem]
0x180012103  test    rdi, rdi
0x180012106  jz      short loc_18001212F
0x180012108  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001210f  test    rax, rax
0x180012112  jnz     short loc_180012121
0x180012114  call    cs:__imp_GetProcessHeap
0x18001211a  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180012121  mov     r8, rdi; lpMem
0x180012124  xor     edx, edx; dwFlags
0x180012126  mov     rcx, rax; hHeap
0x180012129  call    cs:__imp_HeapFree
0x18001212f  test    bl, bl
0x180012131  jz      short loc_180012170
0x180012133  mov     r8, [rbp+380h+var_3D8]
0x180012137  lea     rdx, aExclusionListE; "Exclusion list entry found for %s; it w"...
0x18001213e  lea     rcx, [rbp+380h+var_260]; this
0x180012145  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x18001214a  lea     rdx, [rbp+380h+var_260]; struct SString *
0x180012151  lea     rcx, [rsp+480h+var_408]; this
0x180012156  call    ?Output@CNGenParserCallback@@UEAAXAEBVSString@@@Z; CNGenParserCallback::Output(SString const &)
0x18001215b  nop
0x18001215c  lea     rcx, [rbp+380h+var_3E0]; this
0x180012160  call    ??1NewCommandLineOptions@@QEAA@XZ; NewCommandLineOptions::~NewCommandLineOptions(void)
0x180012165  nop
0x180012166  jmp     loc_1800122A9
0x18001216b  mov     bl, r13b
0x18001216e  jmp     short loc_1800120F7
0x180012170  mov     dword ptr [rbp+380h+var_350+8], r13d
0x180012174  mov     [rsp+480h+var_430], r12
0x180012179  mov     [rsp+480h+var_428], r12d
0x18001217e  lea     rax, [rsp+480h+var_430]
0x180012183  mov     [rbp+380h+var_3F0], rax
0x180012187  mov     [rsp+480h+var_430], r12
0x18001218c  mov     [rsp+480h+var_450], r13d
0x180012191  lea     rcx, [rsp+480h+var_430]
0x180012196  call    CorGetSvc
0x18001219b  test    eax, eax
0x18001219d  js      loc_180012401
0x1800121a3  mov     ebx, r13d
0x1800121a6  and     ebx, 0FFFFFFFEh
0x1800121a9  mov     [rsp+480h+var_450], ebx
0x1800121ad  mov     eax, [rsp+480h+var_428]
0x1800121b1  cmp     [rsp+480h+var_430], r12
0x1800121b6  cmovnz  eax, r13d
0x1800121ba  mov     [rsp+480h+var_428], eax
0x1800121be  mov     [rsp+480h+var_420], r12
0x1800121c3  mov     [rsp+480h+var_418], r12d
0x1800121c8  mov     rcx, [rsp+480h+var_430]
0x1800121cd  lea     rax, [rsp+480h+var_420]
0x1800121d2  mov     [rbp+380h+var_3F0], rax
0x1800121d6  mov     [rsp+480h+var_420], r12
0x1800121db  or      ebx, 2
0x1800121de  mov     [rsp+480h+var_450], ebx
0x1800121e2  mov     rax, [rcx]
0x1800121e5  lea     r8, [rsp+480h+var_420]
0x1800121ea  lea     rdx, IID_ICorSvc
0x1800121f1  mov     rax, [rax]
0x1800121f4  call    cs:__guard_dispatch_icall_fptr
0x1800121fa  test    eax, eax
0x1800121fc  js      loc_18001230F
0x180012202  and     ebx, 0FFFFFFFDh
0x180012205  mov     [rsp+480h+var_450], ebx
0x180012209  mov     eax, [rsp+480h+var_418]
0x18001220d  mov     r8, [rsp+480h+var_420]; struct ICorSvc *
0x180012212  test    r8, r8
0x180012215  cmovnz  eax, r13d
0x180012219  mov     [rsp+480h+var_418], eax
0x18001221d  mov     [rsp+480h+var_460], r14; struct ICorSvcLogger *
0x180012222  mov     r9, r15; struct ICompileProgressNotification *
0x180012225  lea     rdx, [rbp+380h+var_3E0]; struct NewCommandLineOptions *
0x180012229  lea     rcx, [rbp+380h+var_3F8]; this
0x18001222d  call    ?ProcessNewCommandLineOptionsHelper@NGenParser@@AEAAXAEAUNewCommandLineOptions@@PEAUICorSvc@@PEAUICompileProgressNotification@@PEAUICorSvcLogger@@@Z; NGenParser::ProcessNewCommandLineOptionsHelper(NewCommandLineOptions &,ICorSvc *,ICompileProgressNotification *,ICorSvcLogger *)
0x180012232  cmp     cs:?g_bProcessNGENService@NGENService@@3_NA, r12b; bool NGENService::g_bProcessNGENService
0x180012239  jz      short loc_180012259
0x18001223b  mov     [rsp+480h+var_460], rsi; unsigned __int16 *
0x180012240  lea     r9, aSuccessfullyEx; "Successfully executed command from the "...
0x180012247  mov     r8d, 452h; unsigned __int16
0x18001224d  movzx   edx, r12w; unsigned __int16 *
0x180012251  xor     ecx, ecx; this
0x180012253  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x180012258  nop
0x180012259  cmp     [rsp+480h+var_418], r12d
0x18001225e  jz      short loc_18001227C
0x180012260  mov     rcx, [rsp+480h+var_420]
0x180012265  test    rcx, rcx
0x180012268  jz      short loc_180012277
0x18001226a  mov     rax, [rcx]
0x18001226d  mov     rax, [rax+10h]
0x180012271  call    cs:__guard_dispatch_icall_fptr
0x180012277  mov     [rsp+480h+var_418], r12d
0x18001227c  cmp     [rsp+480h+var_428], r12d
0x180012281  jz      short loc_18001229F
0x180012283  mov     rcx, [rsp+480h+var_430]
0x180012288  test    rcx, rcx
0x18001228b  jz      short loc_18001229A
0x18001228d  mov     rax, [rcx]
0x180012290  mov     rax, [rax+10h]
0x180012294  call    cs:__guard_dispatch_icall_fptr
0x18001229a  mov     [rsp+480h+var_428], r12d
0x18001229f  lea     rcx, [rbp+380h+var_3E0]; this
0x1800122a3  call    ??1NewCommandLineOptions@@QEAA@XZ; NewCommandLineOptions::~NewCommandLineOptions(void)
0x1800122a8  nop
0x1800122a9  test    [rbp+380h+var_258], 8
0x1800122b0  jz      short loc_1800122E5
0x1800122b2  mov     rbx, [rbp+380h+var_250]
0x1800122b9  test    rbx, rbx
0x1800122bc  jz      short loc_1800122E5
0x1800122be  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800122c5  test    rax, rax
0x1800122c8  jnz     short loc_1800122D7
0x1800122ca  call    cs:__imp_GetProcessHeap
0x1800122d0  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800122d7  mov     r8, rbx; lpMem
0x1800122da  xor     edx, edx; dwFlags
0x1800122dc  mov     rcx, rax; hHeap
0x1800122df  call    cs:__imp_HeapFree
0x1800122e5  mov     rcx, [rbp+380h+var_40]
0x1800122ec  xor     rcx, rsp; StackCookie
0x1800122ef  call    __security_check_cookie
0x1800122f4  mov     rbx, [rsp+480h+arg_18]
0x1800122fc  add     rsp, 450h
0x180012303  pop     r15
0x180012305  pop     r14
0x180012307  pop     r13
0x180012309  pop     r12
0x18001230b  pop     rdi
0x18001230c  pop     rsi
0x18001230d  pop     rbp
0x18001230e  retn
0x18001230f  mov     ecx, eax; int
0x180012311  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180012317  lea     rdx, aErrorParsingCo; "Error parsing command line in offline Q"...
0x18001231e  lea     rcx, [rsp+480h+var_448]; this
0x180012323  call    ??0SString@@QEAA@PEBG@Z; SString::SString(ushort const *)
0x180012328  nop
0x180012329  lea     rdx, [rsp+480h+var_448]; struct SString *
0x18001232e  lea     rcx, [rsp+480h+var_408]; this
0x180012333  call    ?Output@CNGenParserCallback@@UEAAXAEBVSString@@@Z; CNGenParserCallback::Output(SString const &)
0x180012338  nop
0x180012339  lea     rcx, [rsp+480h+var_448]; this
0x18001233e  call    ??1WriteBuffer@@QEAA@XZ; WriteBuffer::~WriteBuffer(void)
0x180012343  lea     r8, aErrorParsingTh; "error parsing the command line passed t"...
  ... truncated ...
```
