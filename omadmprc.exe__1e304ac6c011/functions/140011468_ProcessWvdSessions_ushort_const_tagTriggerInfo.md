# ProcessWvdSessions(ushort const *,tagTriggerInfo *)

- ea: `0x140011468`
- end: `0x140011a76`
- name: `?ProcessWvdSessions@@YAJPEBGPEAUtagTriggerInfo@@@Z`
- size: `1550`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct tagTriggerInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000fff0`

## callees

- `0x14000271f`
- `0x140008504`
- `0x14000f13c`
- `0x14000f2b8`
- `0x140011468`
- `0x1400128d4`
- `0x140013350`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x14001154d`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x14001154d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001164f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400116d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011747`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001175d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400117e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400117fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011834`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001184e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400118c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001194b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011974`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001164f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400116d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011747`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001175d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400117e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400117fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011834`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001184e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400118c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001194b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011974`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x1400114d6`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x1400114d6`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1400115e4`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1400115e4`

## string_xrefs

- `0x140011537`: `SessionAutoDeleteKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ProcessWvdSessions(const unsigned __int16 *a1, struct tagTriggerInfo *a2)
{
  int InitiationInfo; // eax
  unsigned int v4; // ebx
  int DWORD; // eax
  int ChildInitiationInfo; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // edi
  int v13; // eax
  int v14; // eax
  int active; // eax
  int v16; // eax
  int v17; // [rsp+20h] [rbp-99h]
  int v18; // [rsp+20h] [rbp-99h]
  int v19; // [rsp+20h] [rbp-99h]
  int v20; // [rsp+20h] [rbp-99h]
  int v21; // [rsp+20h] [rbp-99h]
  int v22; // [rsp+20h] [rbp-99h]
  int v23; // [rsp+20h] [rbp-99h]
  int v24; // [rsp+20h] [rbp-99h]
  int v25; // [rsp+20h] [rbp-99h]
  int v26; // [rsp+50h] [rbp-69h] BYREF
  int v27; // [rsp+54h] [rbp-65h] BYREF
  int v28; // [rsp+58h] [rbp-61h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-59h] BYREF
  HLOCAL v30; // [rsp+68h] [rbp-51h] BYREF
  HLOCAL v31; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v32[5]; // [rsp+78h] [rbp-41h] BYREF
  char v33; // [rsp+A0h] [rbp-19h]
  _DWORD v34[4]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned int v35; // [rsp+C0h] [rbp+7h]
  int v36; // [rsp+C4h] [rbp+Bh]
  unsigned int v37; // [rsp+D8h] [rbp+1Fh]
  int v38; // [rsp+DCh] [rbp+23h]
  int v39; // [rsp+E0h] [rbp+27h]
  const unsigned __int16 *v40; // [rsp+E8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  const unsigned __int16 *v42; // [rsp+120h] [rbp+67h] BYREF
  struct tagTriggerInfo *v43; // [rsp+128h] [rbp+6Fh] BYREF
  int v44; // [rsp+130h] [rbp+77h] BYREF
  int v45; // [rsp+138h] [rbp+7Fh] BYREF

  v43 = a2;
  v42 = a1;
  v44 = 0;
  v27 = 0;
  memset_0(v34, 0, 0x40u);
  v32[0] = &v44;
  v32[1] = &v43;
  v32[2] = &v27;
  v32[3] = &v42;
  v32[4] = v34;
  v33 = 1;
  v34[0] = 64;
  InitiationInfo = OmaDmGetInitiationInfo(*((_QWORD *)a2 + 4), v34);
  v4 = InitiationInfo;
  v44 = InitiationInfo;
  if ( InitiationInfo >= 0 )
  {
    if ( v36 == 5 )
    {
      v33 = 0;
      lambda_9a9cf1d8bccff3470d69d83d4ea05085_::operator()(v32);
LABEL_11:
      v4 = 0;
      goto LABEL_12;
    }
    v45 = 0;
    DWORD = OmaDmRegistryGetDWORD(
              HKEY_LOCAL_MACHINE,
              *((const unsigned __int16 **)v43 + 4),
              L"SessionAutoDeleteKey",
              (unsigned int *)&v45);
    v4 = DWORD;
    if ( DWORD < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x721,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
        (const char *)(unsigned int)DWORD,
        v17);
      v33 = 0;
      lambda_9a9cf1d8bccff3470d69d83d4ea05085_::operator()(v32);
      goto LABEL_12;
    }
    if ( v40 )
    {
      if ( v38 )
      {
        v44 = TriggerSession(v40, v42, *((unsigned __int16 **)v43 + 4), 0, 0, v35, *((_BYTE *)v43 + 9), v37, 0);
LABEL_10:
        v33 = 0;
        lambda_9a9cf1d8bccff3470d69d83d4ea05085_::operator()(v32);
        goto LABEL_11;
      }
      hMem = 0;
      ChildInitiationInfo = CreateChildInitiationInfo(
                              *((const unsigned __int16 **)v43 + 4),
                              (struct OMADMINITIATIONINFO *)v34,
                              v45,
                              0,
                              (unsigned __int16 **)&hMem);
      v4 = ChildInitiationInfo;
      v44 = ChildInitiationInfo;
      if ( ChildInitiationInfo < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x739,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
          (const char *)(unsigned int)ChildInitiationInfo,
          v18);
        if ( hMem )
          LocalFree(hMem);
LABEL_16:
        v33 = 0;
        lambda_9a9cf1d8bccff3470d69d83d4ea05085_::operator()(v32);
        goto LABEL_12;
      }
      v26 = 0;
      v8 = TriggerSession(
             0,
             v42,
             (unsigned __int16 *)hMem,
             *((unsigned __int16 **)v43 + 4),
             0,
             v35,
             *((_BYTE *)v43 + 9),
             v37,
             &v26);
      v4 = v8;
      v44 = v8;
      if ( v8 >= 0 )
      {
        v30 = 0;
        v9 = CreateChildInitiationInfo(
               *((const unsigned __int16 **)v43 + 4),
               (struct OMADMINITIATIONINFO *)v34,
               v45,
               0,
               (unsigned __int16 **)&v30);
        v4 = v9;
        v44 = v9;
        if ( v9 >= 0 )
        {
          v28 = 0;
          v10 = TriggerSession(
                  v40,
                  v42,
                  (unsigned __int16 *)v30,
                  *((unsigned __int16 **)v43 + 4),
                  0,
                  v35,
                  *((_BYTE *)v43 + 9),
                  v37,
                  &v28);
          v4 = v10;
          if ( v10 >= 0 )
          {
            v11 = v26;
            if ( v26 < 0 || (v11 = v28, v28 < 0) )
              v27 = v11;
            if ( v30 )
              LocalFree(v30);
            if ( hMem )
              LocalFree(hMem);
            goto LABEL_10;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x756,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
            (const char *)(unsigned int)v10,
            v21);
          if ( v30 )
            LocalFree(v30);
          if ( hMem )
            LocalFree(hMem);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x74A,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
            (const char *)(unsigned int)v9,
            v20);
          if ( v30 )
            LocalFree(v30);
          if ( hMem )
            LocalFree(hMem);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x745,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
          (const char *)(unsigned int)v8,
          v19);
        if ( hMem )
          LocalFree(hMem);
      }
LABEL_49:
      v33 = 0;
      lambda_9a9cf1d8bccff3470d69d83d4ea05085_::operator()(v32);
      goto LABEL_12;
    }
    if ( !v39 )
    {
      v16 = TriggerSession(0, v42, *((unsigned __int16 **)v43 + 4), 0, 0, v35, *((_BYTE *)v43 + 9), v37, 0);
      v4 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x79C,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
          (const char *)(unsigned int)v16,
          v25);
        v33 = 0;
        lambda_9a9cf1d8bccff3470d69d83d4ea05085_::operator()(v32);
        goto LABEL_12;
      }
      goto LABEL_10;
    }
    v12 = 0;
    v26 = 0;
    if ( !v38 )
    {
      v31 = 0;
      v13 = CreateChildInitiationInfo(
              *((const unsigned __int16 **)v43 + 4),
              (struct OMADMINITIATIONINFO *)v34,
              v45,
              0,
              (unsigned __int16 **)&v31);
      v4 = v13;
      v44 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x76F,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
          (const char *)(unsigned int)v13,
          v22);
        if ( v31 )
          LocalFree(v31);
        goto LABEL_16;
      }
      v14 = TriggerSession(
              0,
              v42,
              (unsigned __int16 *)v31,
              *((unsigned __int16 **)v43 + 4),
              0,
              v35,
              *((_BYTE *)v43 + 9),
              v37,
              &v26);
      v4 = v14;
      v44 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x77A,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
          (const char *)(unsigned int)v14,
          v23);
        if ( v31 )
          LocalFree(v31);
        goto LABEL_49;
      }
      if ( v31 )
        LocalFree(v31);
      v12 = v26;
    }
    v28 = 0;
    active = TriggerSessionForAllActiveUsers(
               v42,
               *((unsigned __int16 **)v43 + 4),
               (struct OMADMINITIATIONINFO *)v34,
               v45,
               *((_BYTE *)v43 + 9),
               v37,
               &v28);
    v4 = active;
    v44 = active;
    if ( active < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x786,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
        (const char *)(unsigned int)active,
        v24);
      v33 = 0;
      lambda_9a9cf1d8bccff3470d69d83d4ea05085_::operator()(v32);
      goto LABEL_12;
    }
    if ( v12 >= 0 )
    {
      if ( v28 < 0 )
        v27 = v28;
    }
    else
    {
      v27 = v12;
    }
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x714,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
    (const char *)(unsigned int)InitiationInfo,
    v17);
  v33 = 0;
  lambda_9a9cf1d8bccff3470d69d83d4ea05085_::operator()(v32);
LABEL_12:
  OmaDmFreeInitiationInfo(v34);
  return v4;
}

```

## disassembly

```asm
0x140011468  mov     [rsp-8+arg_8], rdx
0x14001146d  mov     [rsp-8+arg_0], rcx
0x140011472  push    rbp
0x140011473  push    rbx
0x140011474  push    rsi
0x140011475  push    rdi
0x140011476  lea     rbp, [rsp-3Fh]
0x14001147b  sub     rsp, 0F8h
0x140011482  mov     rbx, rdx
0x140011485  xor     esi, esi
0x140011487  mov     [rbp+57h+arg_10], esi
0x14001148a  mov     [rbp+57h+var_BC], esi
0x14001148d  lea     edi, [rsi+40h]
0x140011490  mov     r8d, edi; Size
0x140011493  xor     edx, edx; Val
0x140011495  lea     rcx, [rbp+57h+var_60]; void *
0x140011499  call    memset_0
0x14001149e  nop
0x14001149f  lea     rax, [rbp+57h+arg_10]
0x1400114a3  mov     [rbp+57h+var_98], rax
0x1400114a7  lea     rax, [rbp+57h+arg_8]
0x1400114ab  mov     [rbp+57h+var_90], rax
0x1400114af  lea     rax, [rbp+57h+var_BC]
0x1400114b3  mov     [rbp+57h+var_88], rax
0x1400114b7  lea     rax, [rbp+57h+arg_0]
0x1400114bb  mov     [rbp+57h+var_80], rax
0x1400114bf  lea     rax, [rbp+57h+var_60]
0x1400114c3  mov     [rbp+57h+var_78], rax
0x1400114c7  mov     [rbp+57h+var_70], 1
0x1400114cb  mov     [rbp+57h+var_60], edi
0x1400114ce  lea     rdx, [rbp+57h+var_60]
0x1400114d2  mov     rcx, [rbx+20h]
0x1400114d6  call    cs:__imp_OmaDmGetInitiationInfo
0x1400114dd  nop     dword ptr [rax+rax+00h]
0x1400114e2  mov     ebx, eax
0x1400114e4  mov     [rbp+57h+arg_10], eax
0x1400114e7  test    eax, eax
0x1400114e9  jns     short loc_140011517
0x1400114eb  mov     rcx, [rbp+5Fh]; this
0x1400114ef  mov     r9d, eax; char *
0x1400114f2  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x1400114f9  mov     edx, 714h; void *
0x1400114fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011503  nop
0x140011504  mov     [rbp+57h+var_70], sil
0x140011508  lea     rcx, [rbp+57h+var_98]
0x14001150c  call    _lambda_9a9cf1d8bccff3470d69d83d4ea05085___operator__
0x140011511  nop
0x140011512  jmp     loc_1400115E0
0x140011517  cmp     [rbp+57h+var_4C], 5
0x14001151b  jnz     short loc_140011530
0x14001151d  mov     [rbp+57h+var_70], sil
0x140011521  lea     rcx, [rbp+57h+var_98]
0x140011525  call    _lambda_9a9cf1d8bccff3470d69d83d4ea05085___operator__
0x14001152a  nop
0x14001152b  jmp     loc_1400115DE
0x140011530  mov     [rbp+57h+arg_18], esi
0x140011533  lea     r9, [rbp+57h+arg_18]
0x140011537  lea     r8, aSessionautodel; "SessionAutoDeleteKey"
0x14001153e  mov     rdx, [rbp+57h+arg_8]
0x140011542  mov     rdx, [rdx+20h]
0x140011546  mov     rcx, 0FFFFFFFF80000002h
0x14001154d  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140011554  nop     dword ptr [rax+rax+00h]
0x140011559  mov     ebx, eax
0x14001155b  test    eax, eax
0x14001155d  jns     short loc_140011588
0x14001155f  mov     rcx, [rbp+5Fh]; this
0x140011563  mov     r9d, eax; char *
0x140011566  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x14001156d  mov     edx, 721h; void *
0x140011572  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011577  nop
0x140011578  mov     [rbp+57h+var_70], sil
0x14001157c  lea     rcx, [rbp+57h+var_98]
0x140011580  call    _lambda_9a9cf1d8bccff3470d69d83d4ea05085___operator__
0x140011585  nop
0x140011586  jmp     short loc_1400115E0
0x140011588  mov     rcx, [rbp+57h+var_28]
0x14001158c  test    rcx, rcx
0x14001158f  jz      loc_14001185F
0x140011595  cmp     [rbp+57h+var_34], esi
0x140011598  jz      short loc_1400115FF
0x14001159a  mov     [rsp+110h+var_D0], rsi
0x14001159f  mov     eax, [rbp+57h+var_38]
0x1400115a2  mov     [rsp+110h+var_D8], eax
0x1400115a6  mov     r8, [rbp+57h+arg_8]
0x1400115aa  mov     al, [r8+9]
0x1400115ae  mov     byte ptr [rsp+110h+var_E0], al
0x1400115b2  mov     eax, [rbp+57h+var_50]
0x1400115b5  mov     [rsp+110h+var_E8], eax
0x1400115b9  mov     dword ptr [rsp+110h+var_F0], esi
0x1400115bd  xor     r9d, r9d
0x1400115c0  mov     r8, [r8+20h]
0x1400115c4  mov     rdx, [rbp+57h+arg_0]
0x1400115c8  call    ?TriggerSession@@YAJPEBG000KW4OMADM_UIMODE@@EW4PushRouterSubmitOrigin@@PEAJ@Z; TriggerSession(ushort const *,ushort const *,ushort const *,ushort const *,ulong,OMADM_UIMODE,uchar,PushRouterSubmitOrigin,long *)
0x1400115cd  mov     [rbp+57h+arg_10], eax
0x1400115d0  mov     [rbp+57h+var_70], sil
0x1400115d4  lea     rcx, [rbp+57h+var_98]
0x1400115d8  call    _lambda_9a9cf1d8bccff3470d69d83d4ea05085___operator__
0x1400115dd  nop
0x1400115de  mov     ebx, esi
0x1400115e0  lea     rcx, [rbp+57h+var_60]
0x1400115e4  call    cs:__imp_OmaDmFreeInitiationInfo
0x1400115eb  nop     dword ptr [rax+rax+00h]
0x1400115f0  mov     eax, ebx
0x1400115f2  add     rsp, 0F8h
0x1400115f9  pop     rdi
0x1400115fa  pop     rsi
0x1400115fb  pop     rbx
0x1400115fc  pop     rbp
0x1400115fd  retn
0x1400115ff  mov     [rbp+57h+hMem], rsi
0x140011603  lea     rax, [rbp+57h+hMem]
0x140011607  mov     [rsp+110h+var_F0], rax; int
0x14001160c  xor     r9d, r9d; unsigned __int16 *
0x14001160f  mov     r8d, [rbp+57h+arg_18]; int
0x140011613  lea     rdx, [rbp+57h+var_60]; struct OMADMINITIATIONINFO *
0x140011617  mov     rcx, [rbp+57h+arg_8]
0x14001161b  mov     rcx, [rcx+20h]; unsigned __int16 *
0x14001161f  call    ?CreateChildInitiationInfo@@YAJPEBGPEAUOMADMINITIATIONINFO@@H0PEAPEAG@Z; CreateChildInitiationInfo(ushort const *,OMADMINITIATIONINFO *,int,ushort const *,ushort * *)
0x140011624  mov     ebx, eax
0x140011626  mov     [rbp+57h+arg_10], eax
0x140011629  test    eax, eax
0x14001162b  jns     short loc_14001166F
0x14001162d  mov     rcx, [rbp+5Fh]; this
0x140011631  mov     r9d, eax; char *
0x140011634  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x14001163b  mov     edx, 739h; void *
0x140011640  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011645  nop
0x140011646  mov     rcx, [rbp+57h+hMem]; hMem
0x14001164a  test    rcx, rcx
0x14001164d  jz      short loc_14001165C
0x14001164f  call    cs:__imp_LocalFree
0x140011656  nop     dword ptr [rax+rax+00h]
0x14001165b  nop
0x14001165c  mov     [rbp+57h+var_70], sil
0x140011660  lea     rcx, [rbp+57h+var_98]
0x140011664  call    _lambda_9a9cf1d8bccff3470d69d83d4ea05085___operator__
0x140011669  nop
0x14001166a  jmp     loc_1400115E0
0x14001166f  mov     [rbp+57h+var_C0], esi
0x140011672  lea     rax, [rbp+57h+var_C0]
0x140011676  mov     [rsp+110h+var_D0], rax
0x14001167b  mov     eax, [rbp+57h+var_38]
0x14001167e  mov     [rsp+110h+var_D8], eax
0x140011682  mov     r9, [rbp+57h+arg_8]
0x140011686  mov     al, [r9+9]
0x14001168a  mov     byte ptr [rsp+110h+var_E0], al
0x14001168e  mov     eax, [rbp+57h+var_50]
0x140011691  mov     [rsp+110h+var_E8], eax
0x140011695  mov     dword ptr [rsp+110h+var_F0], esi; int
0x140011699  mov     r9, [r9+20h]
0x14001169d  mov     r8, [rbp+57h+hMem]
0x1400116a1  mov     rdx, [rbp+57h+arg_0]
0x1400116a5  xor     ecx, ecx
0x1400116a7  call    ?TriggerSession@@YAJPEBG000KW4OMADM_UIMODE@@EW4PushRouterSubmitOrigin@@PEAJ@Z; TriggerSession(ushort const *,ushort const *,ushort const *,ushort const *,ulong,OMADM_UIMODE,uchar,PushRouterSubmitOrigin,long *)
0x1400116ac  mov     ebx, eax
0x1400116ae  mov     [rbp+57h+arg_10], eax
0x1400116b1  test    eax, eax
0x1400116b3  jns     short loc_1400116F7
0x1400116b5  mov     rcx, [rbp+5Fh]; this
0x1400116b9  mov     r9d, eax; char *
0x1400116bc  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x1400116c3  mov     edx, 745h; void *
0x1400116c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400116cd  nop
0x1400116ce  mov     rcx, [rbp+57h+hMem]; hMem
0x1400116d2  test    rcx, rcx
0x1400116d5  jz      short loc_1400116E4
0x1400116d7  call    cs:__imp_LocalFree
0x1400116de  nop     dword ptr [rax+rax+00h]
0x1400116e3  nop
0x1400116e4  mov     [rbp+57h+var_70], sil
0x1400116e8  lea     rcx, [rbp+57h+var_98]
0x1400116ec  call    _lambda_9a9cf1d8bccff3470d69d83d4ea05085___operator__
0x1400116f1  nop
0x1400116f2  jmp     loc_1400115E0
0x1400116f7  mov     [rbp+57h+var_A8], rsi
0x1400116fb  lea     rax, [rbp+57h+var_A8]
0x1400116ff  mov     [rsp+110h+var_F0], rax; int
0x140011704  xor     r9d, r9d; unsigned __int16 *
0x140011707  mov     r8d, [rbp+57h+arg_18]; int
0x14001170b  lea     rdx, [rbp+57h+var_60]; struct OMADMINITIATIONINFO *
0x14001170f  mov     rcx, [rbp+57h+arg_8]
0x140011713  mov     rcx, [rcx+20h]; unsigned __int16 *
0x140011717  call    ?CreateChildInitiationInfo@@YAJPEBGPEAUOMADMINITIATIONINFO@@H0PEAPEAG@Z; CreateChildInitiationInfo(ushort const *,OMADMINITIATIONINFO *,int,ushort const *,ushort * *)
0x14001171c  mov     ebx, eax
0x14001171e  mov     [rbp+57h+arg_10], eax
0x140011721  test    eax, eax
0x140011723  jns     short loc_14001177D
0x140011725  mov     rcx, [rbp+5Fh]; this
0x140011729  mov     r9d, eax; char *
0x14001172c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140011733  mov     edx, 74Ah; void *
0x140011738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001173d  nop
0x14001173e  mov     rcx, [rbp+57h+var_A8]; hMem
0x140011742  test    rcx, rcx
0x140011745  jz      short loc_140011754
0x140011747  call    cs:__imp_LocalFree
0x14001174e  nop     dword ptr [rax+rax+00h]
0x140011753  nop
0x140011754  mov     rcx, [rbp+57h+hMem]; hMem
0x140011758  test    rcx, rcx
0x14001175b  jz      short loc_14001176A
0x14001175d  call    cs:__imp_LocalFree
0x140011764  nop     dword ptr [rax+rax+00h]
0x140011769  nop
0x14001176a  mov     [rbp+57h+var_70], sil
0x14001176e  lea     rcx, [rbp+57h+var_98]
0x140011772  call    _lambda_9a9cf1d8bccff3470d69d83d4ea05085___operator__
0x140011777  nop
0x140011778  jmp     loc_1400115E0
0x14001177d  mov     [rbp+57h+var_B8], esi
0x140011780  lea     rax, [rbp+57h+var_B8]
0x140011784  mov     [rsp+110h+var_D0], rax
0x140011789  mov     eax, [rbp+57h+var_38]
0x14001178c  mov     [rsp+110h+var_D8], eax
0x140011790  mov     r9, [rbp+57h+arg_8]
0x140011794  mov     al, [r9+9]
0x140011798  mov     byte ptr [rsp+110h+var_E0], al
0x14001179c  mov     eax, [rbp+57h+var_50]
0x14001179f  mov     [rsp+110h+var_E8], eax
0x1400117a3  mov     dword ptr [rsp+110h+var_F0], esi; int
0x1400117a7  mov     r9, [r9+20h]
0x1400117ab  mov     r8, [rbp+57h+var_A8]
0x1400117af  mov     rdx, [rbp+57h+arg_0]
0x1400117b3  mov     rcx, [rbp+57h+var_28]
0x1400117b7  call    ?TriggerSession@@YAJPEBG000KW4OMADM_UIMODE@@EW4PushRouterSubmitOrigin@@PEAJ@Z; TriggerSession(ushort const *,ushort const *,ushort const *,ushort const *,ulong,OMADM_UIMODE,uchar,PushRouterSubmitOrigin,long *)
0x1400117bc  mov     ebx, eax
0x1400117be  test    eax, eax
0x1400117c0  jns     short loc_14001181A
0x1400117c2  mov     rcx, [rbp+5Fh]; this
0x1400117c6  mov     r9d, eax; char *
0x1400117c9  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x1400117d0  mov     edx, 756h; void *
0x1400117d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400117da  nop
0x1400117db  mov     rcx, [rbp+57h+var_A8]; hMem
0x1400117df  test    rcx, rcx
0x1400117e2  jz      short loc_1400117F1
0x1400117e4  call    cs:__imp_LocalFree
0x1400117eb  nop     dword ptr [rax+rax+00h]
0x1400117f0  nop
0x1400117f1  mov     rcx, [rbp+57h+hMem]; hMem
0x1400117f5  test    rcx, rcx
0x1400117f8  jz      short loc_140011807
0x1400117fa  call    cs:__imp_LocalFree
0x140011801  nop     dword ptr [rax+rax+00h]
0x140011806  nop
0x140011807  mov     [rbp+57h+var_70], sil
0x14001180b  lea     rcx, [rbp+57h+var_98]
0x14001180f  call    _lambda_9a9cf1d8bccff3470d69d83d4ea05085___operator__
0x140011814  nop
0x140011815  jmp     loc_1400115E0
0x14001181a  mov     eax, [rbp+57h+var_C0]
0x14001181d  test    eax, eax
0x14001181f  js      short loc_140011828
0x140011821  mov     eax, [rbp+57h+var_B8]
0x140011824  test    eax, eax
0x140011826  jns     short loc_14001182B
0x140011828  mov     [rbp+57h+var_BC], eax
0x14001182b  mov     rcx, [rbp+57h+var_A8]; hMem
0x14001182f  test    rcx, rcx
0x140011832  jz      short loc_140011841
0x140011834  call    cs:__imp_LocalFree
0x14001183b  nop     dword ptr [rax+rax+00h]
0x140011840  nop
0x140011841  mov     rcx, [rbp+57h+hMem]; hMem
0x140011845  test    rcx, rcx
0x140011848  jz      loc_1400115D0
0x14001184e  call    cs:__imp_LocalFree
0x140011855  nop     dword ptr [rax+rax+00h]
0x14001185a  jmp     loc_1400115D0
0x14001185f  cmp     [rbp+57h+var_30], esi
0x140011862  jz      loc_140011A0A
0x140011868  mov     edi, esi
0x14001186a  mov     [rbp+57h+var_C0], esi
0x14001186d  cmp     [rbp+57h+var_34], esi
0x140011870  jnz     loc_140011983
0x140011876  mov     [rbp+57h+var_A0], rsi
0x14001187a  lea     rax, [rbp+57h+var_A0]
0x14001187e  mov     [rsp+110h+var_F0], rax; int
0x140011883  xor     r9d, r9d; unsigned __int16 *
0x140011886  mov     r8d, [rbp+57h+arg_18]; int
0x14001188a  lea     rdx, [rbp+57h+var_60]; struct OMADMINITIATIONINFO *
0x14001188e  mov     rcx, [rbp+57h+arg_8]
0x140011892  mov     rcx, [rcx+20h]; unsigned __int16 *
0x140011896  call    ?CreateChildInitiationInfo@@YAJPEBGPEAUOMADMINITIATIONINFO@@H0PEAPEAG@Z; CreateChildInitiationInfo(ushort const *,OMADMINITIATIONINFO *,int,ushort const *,ushort * *)
0x14001189b  mov     ebx, eax
0x14001189d  mov     [rbp+57h+arg_10], eax
0x1400118a0  test    eax, eax
0x1400118a2  jns     short loc_1400118E6
0x1400118a4  mov     rcx, [rbp+5Fh]; this
0x1400118a8  mov     r9d, eax; char *
0x1400118ab  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x1400118b2  mov     edx, 76Fh; void *
0x1400118b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
