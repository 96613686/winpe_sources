# GetDescriptionStr(CLogInfo *,_EVENTLOGRECORD *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,int,ushort * *)

- ea: `0x18000d814`
- end: `0x18000de07`
- name: `?GetDescriptionStr@@YAPEAGPEAVCLogInfo@@PEAU_EVENTLOGRECORD@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HPEAPEAG@Z`
- size: `1523`
- prototype: `const unsigned __int16 *__fastcall(__int64, struct _EVENTLOGRECORD *, __int64, int, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `20`
- tags: `service_task`

## callers

- `0x18000aac0`
- `0x18000b6b8`
- `0x18001766c`
- `0x18001a330`

## callees

- `0x180001dd0`
- `0x1800027d0`
- `0x180004b7c`
- `0x180007014`
- `0x180007060`
- `0x18000ca0c`
- `0x18000cca8`
- `0x18000d7c4`
- `0x18000d814`
- `0x18000de10`
- `0x18000e664`
- `0x18000e908`
- `0x18000eb2c`
- `0x18001abd8`
- `0x18001ac04`
- `0x18001ae60`
- `0x18001fcf0`
- `0x180022292`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `msvcrt!free` at `0x18000dab9`
- `msvcrt!free` at `0x18000dab9`
- `msvcrt!malloc` at `0x18000d9bf`
- `msvcrt!malloc` at `0x18000d9bf`
- `KERNEL32!LocalAlloc` at `0x18000d92e`
- `KERNEL32!LocalAlloc` at `0x18000dc33`
- `KERNEL32!LocalAlloc` at `0x18000d92e`
- `KERNEL32!LocalAlloc` at `0x18000dc33`

## string_xrefs

- `0x18000d9ef`: `SYSTEM\CurrentControlSet\Services\EventLog`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
const unsigned __int16 *__fastcall GetDescriptionStr(
        __int64 a1,
        struct _EVENTLOGRECORD *a2,
        __int64 a3,
        int a4,
        unsigned __int16 **a5)
{
  const WCHAR *v8; // r14
  const unsigned __int16 **v9; // r12
  wchar_t *v10; // rax
  __int64 v11; // rdi
  unsigned __int64 v12; // rdi
  unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  void *v17; // rbx
  int v18; // esi
  int v19; // eax
  HKEY v20; // r8
  int RemoteSystemRoot; // ebx
  BOOL v22; // ecx
  unsigned __int16 **v23; // r13
  __int64 v24; // rbx
  int v25; // edi
  __int64 v26; // rcx
  unsigned __int16 **v27; // r14
  unsigned int v28; // r12d
  __int64 v29; // rdi
  unsigned __int16 **v30; // r13
  const unsigned __int16 **v31; // rbx
  __int64 v32; // r13
  __int64 v33; // rax
  int EventMessageFileList; // eax
  int v35; // edi
  unsigned __int64 v36; // rdi
  unsigned __int16 *v37; // rax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v40; // [rsp+48h] [rbp-B8h]
  unsigned int v41; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v42; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+54h] [rbp-ACh]
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 **v47; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 **v48; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 **v49; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v51; // [rsp+90h] [rbp-70h]
  void *Block; // [rsp+98h] [rbp-68h]
  __int64 v53; // [rsp+A0h] [rbp-60h]
  unsigned __int16 **v54; // [rsp+A8h] [rbp-58h]
  __int64 v55; // [rsp+B0h] [rbp-50h]
  __int64 v56; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v57; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v58[526]; // [rsp+C2h] [rbp-3Eh] BYREF

  v43 = a4;
  v56 = a3;
  v55 = a1;
  v54 = a5;
  v8 = (const WCHAR *)((a1 + 32) & -(__int64)(*(_WORD *)(a1 + 32) != 0));
  v9 = 0;
  if ( (*(_BYTE *)(a1 + 24) & 1) != 0 )
  {
    v10 = &g_wszAuxMessageSource;
    if ( !g_wszAuxMessageSource )
      v10 = (wchar_t *)((a1 + 32) & -(__int64)(*(_WORD *)(a1 + 32) != 0));
    v8 = v10;
  }
  v40 = v8 != 0;
  v48 = 0;
  v41 = 0;
  v49 = 0;
  v42 = 0;
  *(_QWORD *)Buffer = 0;
  v57 = 0;
  memset_0(v58, 0, 0x208u);
  phkResult = 0;
  v45 = 0;
  v44 = 0;
  if ( (unsigned int)IsNewEventType(a2)
    && GetDescriptionStrPtr
    && GetDescriptionStrPtr(a2, 0, (unsigned __int16 **)Buffer) )
  {
    if ( a5 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v11) );
      v12 = v11 + 1;
      v13 = (unsigned __int16 *)LocalAlloc(0, 2 * v12);
      *a5 = v13;
      v14 = *(const unsigned __int16 **)Buffer;
      if ( !*(_QWORD *)Buffer || !v13 )
        goto LABEL_85;
      StringCchCopyW(v13, v12, *(const unsigned __int16 **)Buffer);
    }
LABEL_84:
    v14 = *(const unsigned __int16 **)Buffer;
    goto LABEL_85;
  }
  if ( a3 )
    std::wstring::erase(a3, 0);
  v53 = a1 + 554;
  if ( a1 == -554 )
    goto LABEL_83;
  if ( a2 == (struct _EVENTLOGRECORD *)-56LL )
    goto LABEL_83;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(a1 + 554 + 2 * v15) );
  v16 = -1;
  do
    ++v16;
  while ( *((_WORD *)&a2[1].Length + v16) );
  v51 = v15 + 45 + v16;
  v17 = malloc(2 * v51);
  Block = v17;
  if ( !v17 )
  {
LABEL_83:
    CreateFallbackMessage(a2, (unsigned __int16 **)Buffer, a5);
    goto LABEL_84;
  }
  v18 = 0;
  v47 = 0;
  StringCchPrintfW(
    (unsigned __int16 *)v17,
    v51,
    L"%s\\%s\\%s",
    L"SYSTEM\\CurrentControlSet\\Services\\EventLog",
    v53,
    &a2[1]);
  v19 = CSafeReg::Open((CSafeReg *)&v45, HKEY_LOCAL_MACHINE, (const unsigned __int16 *)v17, 1u);
  LODWORD(v51) = v19 >= 0;
  RemoteSystemRoot = 0;
  if ( v19 >= 0 )
    RemoteSystemRoot = v19;
  if ( v8 )
  {
    RemoteSystemRoot = CSafeReg::Connect(&phkResult, v8, v20);
    if ( RemoteSystemRoot >= 0 )
    {
      RemoteSystemRoot = GetRemoteSystemRoot(phkResult, &v57, 0x105u);
      if ( RemoteSystemRoot >= 0 )
      {
        RemoteSystemRoot = CSafeReg::Open((CSafeReg *)&v44, phkResult, (const unsigned __int16 *)Block, 1u);
        if ( RemoteSystemRoot >= 0 )
        {
          RemoteSystemRoot = GetEventMessageFileList((struct CSafeReg *)&v44, v8, &v57, &v48, &v41);
          if ( RemoteSystemRoot >= 0 )
            v47 = v48;
        }
      }
    }
  }
  free(Block);
  v22 = v40;
  if ( RemoteSystemRoot < 0 )
    v22 = 0;
  v40 = v22;
  v23 = v47;
  v24 = v56;
  v25 = v51;
  while ( 1 )
  {
    if ( v22 )
    {
      if ( v23 < &v48[v41] && *v23 )
      {
        v18 = AttemptFormatMessage(a2->EventID, *v23, Buffer, v43);
        if ( v18 && v24 )
          std::wstring::assign(v24, *v23);
        ++v23;
        v22 = v40;
      }
      else
      {
        v22 = 0;
        v40 = 0;
      }
    }
    else if ( !v25 )
    {
      break;
    }
    if ( v18 )
      break;
    if ( v25 )
    {
      if ( !v9 )
      {
        if ( (int)GetEventMessageFileList((struct CSafeReg *)&v45, 0, (unsigned __int16 *)&String, &v49, &v42) < 0 )
          goto LABEL_81;
        v9 = (const unsigned __int16 **)v49;
      }
      if ( v9 >= (const unsigned __int16 **)&v49[v42] || !*v9 )
      {
LABEL_81:
        v25 = 0;
        goto LABEL_82;
      }
      v18 = AttemptFormatMessage(a2->EventID, *v9, Buffer, v43);
      if ( v18 && !v8 && v24 )
        std::wstring::assign(v24, *v9);
      ++v9;
      if ( v18 )
        break;
LABEL_82:
      v22 = v40;
    }
  }
  FreeStringArray(v48, v41);
  FreeStringArray(v49, v42);
  v26 = 0;
  v41 = 0;
  v27 = 0;
  v47 = 0;
  v28 = 0;
  v42 = 0;
  v50 = 0;
  v29 = -1;
  v30 = v54;
  if ( !v18 )
  {
    v31 = 0;
    v32 = v55;
    if ( !*(_DWORD *)(v55 + 4784) )
    {
      CSources::_Init((CSources *)(v55 + 4784));
      v26 = 0;
    }
    v33 = *(_QWORD *)(v32 + 4832);
    if ( v33 )
      v26 = *(_QWORD *)(v33 + 24);
    v41 = OpenPrimarySourceKey(v26, &a2[1], v53, &v50);
    if ( v41 == 4 )
    {
      EventMessageFileList = GetEventMessageFileList(
                               (struct CSafeReg *)&v50,
                               0,
                               (unsigned __int16 *)&String,
                               &v47,
                               &v42);
      v27 = v47;
      if ( EventMessageFileList >= 0 )
        v31 = (const unsigned __int16 **)v47;
      v28 = v42;
    }
    v35 = v43;
    do
    {
      if ( !v31 )
        break;
      if ( (unsigned int)(((char *)v31 - (char *)v27) >> 3) >= v28 )
        break;
      if ( !*v31 )
        break;
      v18 = AttemptFormatMessage(a2->EventID, *v31++, Buffer, v35);
    }
    while ( !v18 );
    v29 = -1;
    v30 = v54;
  }
  FreeStringArray(v27, v28);
  if ( !v18 )
    CreateFallbackMessage(a2, (unsigned __int16 **)Buffer, v30);
  v14 = *(const unsigned __int16 **)Buffer;
  if ( *(_QWORD *)Buffer )
  {
    if ( v18 && v30 )
    {
      do
        ++v29;
      while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v29) );
      v36 = v29 + 1;
      v37 = (unsigned __int16 *)LocalAlloc(0, 2 * v36);
      *v30 = v37;
      if ( v37 )
        StringCchCopyW(v37, v36, *(const unsigned __int16 **)Buffer);
    }
    ReplaceAllInserts(a2, v55, &v57, &v44, &v45, &v50, v41, Buffer);
    v14 = *(const unsigned __int16 **)Buffer;
  }
  CSafeReg::Close((CSafeReg *)&v50);
LABEL_85:
  CSafeReg::Close((CSafeReg *)&v44);
  CSafeReg::Close((CSafeReg *)&v45);
  CSafeReg::Close((CSafeReg *)&phkResult);
  return v14;
}

```

## disassembly

```asm
0x18000d814  mov     [rsp-8+arg_18], rbx
0x18000d819  push    rbp
0x18000d81a  push    rsi
0x18000d81b  push    rdi
0x18000d81c  push    r12
0x18000d81e  push    r13
0x18000d820  push    r14
0x18000d822  push    r15
0x18000d824  lea     rbp, [rsp-1E0h]
0x18000d82c  sub     rsp, 2E0h
0x18000d833  mov     rax, cs:__security_cookie
0x18000d83a  xor     rax, rsp
0x18000d83d  mov     [rbp+210h+var_40], rax
0x18000d844  mov     [rsp+310h+var_2BC], r9d
0x18000d849  mov     rbx, r8
0x18000d84c  mov     [rbp+210h+var_258], rbx
0x18000d850  mov     r15, rdx
0x18000d853  mov     rdi, rcx
0x18000d856  mov     [rbp+210h+var_260], rcx
0x18000d85a  mov     r13, [rbp+210h+arg_20]
0x18000d861  mov     [rbp+210h+var_268], r13
0x18000d865  add     rcx, 20h ; ' '
0x18000d869  movzx   eax, word ptr [rcx]
0x18000d86c  neg     ax
0x18000d86f  sbb     r14, r14
0x18000d872  and     r14, rcx
0x18000d875  xor     r12d, r12d
0x18000d878  test    byte ptr [rdi+18h], 1
0x18000d87c  jz      short loc_18000D894
0x18000d87e  lea     rax, ?g_wszAuxMessageSource@@3PAGA; ushort near * g_wszAuxMessageSource
0x18000d885  cmp     cs:?g_wszAuxMessageSource@@3PAGA, r12w; ushort near * g_wszAuxMessageSource
0x18000d88d  cmovz   rax, r14
0x18000d891  mov     r14, rax
0x18000d894  mov     eax, r12d
0x18000d897  test    r14, r14
0x18000d89a  setnz   al
0x18000d89d  mov     [rsp+310h+var_2C8], eax
0x18000d8a1  mov     [rsp+310h+var_298], r12
0x18000d8a6  mov     [rsp+310h+var_2C4], r12d
0x18000d8ab  mov     [rbp+210h+var_290], r12
0x18000d8af  mov     [rsp+310h+var_2C0], r12d
0x18000d8b4  mov     qword ptr [rsp+310h+Buffer], r12
0x18000d8b9  mov     [rbp+210h+var_250], r12w
0x18000d8be  xor     edx, edx; Val
0x18000d8c0  mov     r8d, 208h; Size
0x18000d8c6  lea     rcx, [rbp+210h+var_24E]; void *
0x18000d8ca  call    memset_0
0x18000d8cf  mov     [rsp+310h+phkResult], r12
0x18000d8d4  mov     [rsp+310h+var_2B0], r12
0x18000d8d9  mov     [rsp+310h+var_2B8], r12
0x18000d8de  mov     rcx, r15; struct _EVENTLOGRECORD *
0x18000d8e1  call    ?IsNewEventType@@YAHPEAU_EVENTLOGRECORD@@@Z; IsNewEventType(_EVENTLOGRECORD *)
0x18000d8e6  test    eax, eax
0x18000d8e8  jz      short loc_18000D962
0x18000d8ea  mov     rax, cs:?GetDescriptionStrPtr@@3P6AHPEAU_EVENTLOGRECORD@@KPEAPEAG@ZEA; int (*GetDescriptionStrPtr)(_EVENTLOGRECORD *,ulong,ushort * *)
0x18000d8f1  test    rax, rax
0x18000d8f4  jz      short loc_18000D962
0x18000d8f6  lea     r8, [rsp+310h+Buffer]
0x18000d8fb  xor     edx, edx
0x18000d8fd  mov     rcx, r15
0x18000d900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d905  test    eax, eax
0x18000d907  jz      short loc_18000D962
0x18000d909  test    r13, r13
0x18000d90c  jz      loc_18000DDB5
0x18000d912  mov     rax, qword ptr [rsp+310h+Buffer]
0x18000d917  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000d91b  inc     rdi
0x18000d91e  cmp     [rax+rdi*2], r12w
0x18000d923  jnz     short loc_18000D91B
0x18000d925  inc     rdi
0x18000d928  lea     rdx, [rdi+rdi]; uBytes
0x18000d92c  xor     ecx, ecx; uFlags
0x18000d92e  call    cs:__imp_LocalAlloc
0x18000d934  mov     [r13+0], rax
0x18000d938  mov     rbx, qword ptr [rsp+310h+Buffer]
0x18000d93d  test    rbx, rbx
0x18000d940  jz      loc_18000DDBA
0x18000d946  test    rax, rax
0x18000d949  jz      loc_18000DDBA
0x18000d94f  mov     r8, rbx; unsigned __int16 *
0x18000d952  mov     rdx, rdi; unsigned __int64
0x18000d955  mov     rcx, rax; unsigned __int16 *
0x18000d958  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d95d  jmp     loc_18000DDB5
0x18000d962  test    rbx, rbx
0x18000d965  jz      short loc_18000D971
0x18000d967  xor     edx, edx
0x18000d969  mov     rcx, rbx
0x18000d96c  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
0x18000d971  lea     rax, [rdi+22Ah]
0x18000d978  mov     [rbp+210h+var_270], rax
0x18000d97c  test    rax, rax
0x18000d97f  jz      loc_18000DDA5
0x18000d985  lea     rdx, [r15+38h]
0x18000d989  test    rdx, rdx
0x18000d98c  jz      loc_18000DDA5
0x18000d992  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000d996  mov     rcx, rdi
0x18000d999  inc     rcx
0x18000d99c  cmp     [rax+rcx*2], r12w
0x18000d9a1  jnz     short loc_18000D999
0x18000d9a3  mov     rax, rdi
0x18000d9a6  inc     rax
0x18000d9a9  cmp     [rdx+rax*2], r12w
0x18000d9ae  jnz     short loc_18000D9A6
0x18000d9b0  add     rcx, 2Dh ; '-'
0x18000d9b4  add     rax, rcx
0x18000d9b7  mov     [rbp+210h+var_280], rax
0x18000d9bb  lea     rcx, [rax+rax]; Size
0x18000d9bf  call    cs:__imp_malloc
0x18000d9c5  mov     rbx, rax
0x18000d9c8  mov     [rbp+210h+Block], rax
0x18000d9cc  test    rax, rax
0x18000d9cf  jz      loc_18000DDA5
0x18000d9d5  mov     esi, r12d
0x18000d9d8  mov     [rsp+310h+var_2A0], r12
0x18000d9dd  lea     rax, [r15+38h]
0x18000d9e1  mov     [rsp+310h+var_2E8], rax
0x18000d9e6  mov     rax, [rbp+210h+var_270]
0x18000d9ea  mov     [rsp+310h+var_2F0], rax
0x18000d9ef  lea     r9, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x18000d9f6  lea     r8, aSSS; "%s\\%s\\%s"
0x18000d9fd  mov     rdx, [rbp+210h+var_280]; unsigned __int64
0x18000da01  mov     rcx, rbx; unsigned __int16 *
0x18000da04  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000da09  mov     r9d, 1; unsigned int
0x18000da0f  mov     r8, rbx; unsigned __int16 *
0x18000da12  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18000da19  lea     rcx, [rsp+310h+var_2B0]; this
0x18000da1e  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x18000da23  mov     ecx, eax
0x18000da25  not     ecx
0x18000da27  shr     ecx, 1Fh
0x18000da2a  mov     dword ptr [rbp+210h+var_280], ecx
0x18000da2d  xor     ebx, ebx
0x18000da2f  test    eax, eax
0x18000da31  cmovns  ebx, eax
0x18000da34  test    r14, r14
0x18000da37  jz      short loc_18000DAB5
0x18000da39  mov     rdx, r14; lpMachineName
0x18000da3c  lea     rcx, [rsp+310h+phkResult]; phkResult
0x18000da41  call    ?Connect@CSafeReg@@QEAAJPEBGPEAUHKEY__@@@Z; CSafeReg::Connect(ushort const *,HKEY__ *)
0x18000da46  mov     ebx, eax
0x18000da48  test    eax, eax
0x18000da4a  js      short loc_18000DAB5
0x18000da4c  mov     r8d, 105h; unsigned int
0x18000da52  lea     rdx, [rbp+210h+var_250]; unsigned __int16 *
0x18000da56  mov     rcx, [rsp+310h+phkResult]; HKEY
0x18000da5b  call    ?GetRemoteSystemRoot@@YAJPEAUHKEY__@@PEAGK@Z; GetRemoteSystemRoot(HKEY__ *,ushort *,ulong)
0x18000da60  mov     ebx, eax
0x18000da62  test    eax, eax
0x18000da64  js      short loc_18000DAB5
0x18000da66  mov     r9d, 1; unsigned int
0x18000da6c  mov     r8, [rbp+210h+Block]; unsigned __int16 *
0x18000da70  mov     rdx, [rsp+310h+phkResult]; HKEY
0x18000da75  lea     rcx, [rsp+310h+var_2B8]; this
0x18000da7a  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x18000da7f  mov     ebx, eax
0x18000da81  test    eax, eax
0x18000da83  js      short loc_18000DAB5
0x18000da85  lea     rax, [rsp+310h+var_2C4]
0x18000da8a  mov     [rsp+310h+var_2F0], rax; unsigned int *
0x18000da8f  lea     r9, [rsp+310h+var_298]; unsigned __int16 ***
0x18000da94  lea     r8, [rbp+210h+var_250]; unsigned __int16 *
0x18000da98  mov     rdx, r14; unsigned __int16 *
0x18000da9b  lea     rcx, [rsp+310h+var_2B8]; this
0x18000daa0  call    ?GetEventMessageFileList@@YAJPEAVCSafeReg@@PEBGPEAGPEAPEAPEAGPEAK@Z; GetEventMessageFileList(CSafeReg *,ushort const *,ushort *,ushort * * *,ulong *)
0x18000daa5  mov     ebx, eax
0x18000daa7  test    eax, eax
0x18000daa9  js      short loc_18000DAB5
0x18000daab  mov     rax, [rsp+310h+var_298]
0x18000dab0  mov     [rsp+310h+var_2A0], rax
0x18000dab5  mov     rcx, [rbp+210h+Block]; Block
0x18000dab9  call    cs:__imp_free
0x18000dabf  xor     r8d, r8d
0x18000dac2  test    ebx, ebx
0x18000dac4  mov     ecx, [rsp+310h+var_2C8]
0x18000dac8  cmovs   ecx, r8d
0x18000dacc  mov     [rsp+310h+var_2C8], ecx
0x18000dad0  mov     r13, [rsp+310h+var_2A0]
0x18000dad5  mov     rbx, [rbp+210h+var_258]
0x18000dad9  mov     edi, dword ptr [rbp+210h+var_280]
0x18000dadc  test    ecx, ecx
0x18000dade  jnz     loc_18000DC9F
0x18000dae4  test    edi, edi
0x18000dae6  jnz     loc_18000DCFB
0x18000daec  mov     edx, [rsp+310h+var_2C4]; unsigned int
0x18000daf0  mov     rcx, [rsp+310h+var_298]; unsigned __int16 **
0x18000daf5  call    ?FreeStringArray@@YAXPEAPEAGK@Z; FreeStringArray(ushort * *,ulong)
0x18000dafa  mov     edx, [rsp+310h+var_2C0]; unsigned int
0x18000dafe  mov     rcx, [rbp+210h+var_290]; unsigned __int16 **
0x18000db02  call    ?FreeStringArray@@YAXPEAPEAGK@Z; FreeStringArray(ushort * *,ulong)
0x18000db07  xor     ecx, ecx
0x18000db09  mov     [rsp+310h+var_2C4], ecx
0x18000db0d  mov     r14d, ecx
0x18000db10  mov     [rsp+310h+var_2A0], rcx
0x18000db15  mov     r12d, ecx
0x18000db18  mov     [rsp+310h+var_2C0], ecx
0x18000db1c  mov     [rbp+210h+var_288], rcx
0x18000db20  test    esi, esi
0x18000db22  lea     rdi, [rcx-1]
0x18000db26  mov     r13, [rbp+210h+var_268]
0x18000db2a  jnz     loc_18000DBEB
0x18000db30  mov     ebx, ecx
0x18000db32  mov     r13, [rbp+210h+var_260]
0x18000db36  cmp     [r13+12B0h], ecx
0x18000db3d  jnz     short loc_18000DB4D
0x18000db3f  lea     rcx, [r13+12B0h]; this
0x18000db46  call    ?_Init@CSources@@AEAAJXZ; CSources::_Init(void)
0x18000db4b  xor     ecx, ecx
0x18000db4d  mov     rax, [r13+12E0h]
0x18000db54  test    rax, rax
0x18000db57  jz      short loc_18000DB5D
0x18000db59  mov     rcx, [rax+18h]
0x18000db5d  lea     r9, [rbp+210h+var_288]
0x18000db61  mov     r8, [rbp+210h+var_270]
0x18000db65  lea     rdx, [r15+38h]
0x18000db69  call    ?OpenPrimarySourceKey@@YA?AW4PSK@@PEBG00PEAVCSafeReg@@@Z; OpenPrimarySourceKey(ushort const *,ushort const *,ushort const *,CSafeReg *)
0x18000db6e  mov     [rsp+310h+var_2C4], eax
0x18000db72  cmp     eax, 4
0x18000db75  jnz     short loc_18000DBA8
0x18000db77  lea     rax, [rsp+310h+var_2C0]
0x18000db7c  mov     [rsp+310h+var_2F0], rax; unsigned int *
0x18000db81  lea     r9, [rsp+310h+var_2A0]; unsigned __int16 ***
0x18000db86  lea     r8, String; unsigned __int16 *
0x18000db8d  xor     edx, edx; unsigned __int16 *
0x18000db8f  lea     rcx, [rbp+210h+var_288]; this
0x18000db93  call    ?GetEventMessageFileList@@YAJPEAVCSafeReg@@PEBGPEAGPEAPEAPEAGPEAK@Z; GetEventMessageFileList(CSafeReg *,ushort const *,ushort *,ushort * * *,ulong *)
0x18000db98  mov     r14, [rsp+310h+var_2A0]
0x18000db9d  test    eax, eax
0x18000db9f  cmovns  rbx, r14
0x18000dba3  mov     r12d, [rsp+310h+var_2C0]
0x18000dba8  mov     edi, [rsp+310h+var_2BC]
0x18000dbac  test    rbx, rbx
0x18000dbaf  jz      short loc_18000DBE3
0x18000dbb1  mov     rax, rbx
0x18000dbb4  sub     rax, r14
0x18000dbb7  sar     rax, 3
0x18000dbbb  cmp     eax, r12d
0x18000dbbe  jnb     short loc_18000DBE3
0x18000dbc0  mov     rdx, [rbx]; unsigned __int16 *
0x18000dbc3  test    rdx, rdx
0x18000dbc6  jz      short loc_18000DBE3
0x18000dbc8  mov     r9d, edi; int
0x18000dbcb  lea     r8, [rsp+310h+Buffer]; lpBuffer
0x18000dbd0  mov     ecx, [r15+14h]; dwMessageId
0x18000dbd4  call    ?AttemptFormatMessage@@YAHKPEBGPEAPEAGH@Z; AttemptFormatMessage(ulong,ushort const *,ushort * *,int)
0x18000dbd9  mov     esi, eax
0x18000dbdb  add     rbx, 8
0x18000dbdf  test    eax, eax
0x18000dbe1  jz      short loc_18000DBAC
0x18000dbe3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000dbe7  mov     r13, [rbp+210h+var_268]
0x18000dbeb  mov     edx, r12d; unsigned int
0x18000dbee  mov     rcx, r14; unsigned __int16 **
0x18000dbf1  call    ?FreeStringArray@@YAXPEAPEAGK@Z; FreeStringArray(ushort * *,ulong)
0x18000dbf6  xor     r14d, r14d
0x18000dbf9  test    esi, esi
0x18000dbfb  jnz     short loc_18000DC0D
0x18000dbfd  mov     r8, r13; unsigned __int16 **
0x18000dc00  lea     rdx, [rsp+310h+Buffer]; unsigned __int16 **
0x18000dc05  mov     rcx, r15; struct _EVENTLOGRECORD *
0x18000dc08  call    ?CreateFallbackMessage@@YAXPEAU_EVENTLOGRECORD@@PEAPEAG1@Z; CreateFallbackMessage(_EVENTLOGRECORD *,ushort * *,ushort * *)
0x18000dc0d  mov     rbx, qword ptr [rsp+310h+Buffer]
0x18000dc12  test    rbx, rbx
0x18000dc15  jz      short loc_18000DC91
0x18000dc17  test    esi, esi
0x18000dc19  jz      short loc_18000DC52
0x18000dc1b  test    r13, r13
0x18000dc1e  jz      short loc_18000DC52
0x18000dc20  inc     rdi
0x18000dc23  cmp     [rbx+rdi*2], r14w
0x18000dc28  jnz     short loc_18000DC20
0x18000dc2a  inc     rdi
0x18000dc2d  lea     rdx, [rdi+rdi]; uBytes
0x18000dc31  xor     ecx, ecx; uFlags
0x18000dc33  call    cs:__imp_LocalAlloc
0x18000dc39  mov     [r13+0], rax
0x18000dc3d  test    rax, rax
0x18000dc40  jz      short loc_18000DC52
0x18000dc42  mov     r8, qword ptr [rsp+310h+Buffer]; unsigned __int16 *
0x18000dc47  mov     rdx, rdi; unsigned __int64
0x18000dc4a  mov     rcx, rax; unsigned __int16 *
0x18000dc4d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dc52  lea     rax, [rsp+310h+Buffer]
0x18000dc57  mov     [rsp+310h+var_2D8], rax
0x18000dc5c  mov     eax, [rsp+310h+var_2C4]
0x18000dc60  mov     [rsp+310h+var_2E0], eax
0x18000dc64  lea     rax, [rbp+210h+var_288]
0x18000dc68  mov     [rsp+310h+var_2E8], rax
0x18000dc6d  lea     rax, [rsp+310h+var_2B0]
0x18000dc72  mov     [rsp+310h+var_2F0], rax
0x18000dc77  lea     r9, [rsp+310h+var_2B8]
0x18000dc7c  lea     r8, [rbp+210h+var_250]
0x18000dc80  mov     rdx, [rbp+210h+var_260]
0x18000dc84  mov     rcx, r15
0x18000dc87  call    ?ReplaceAllInserts@@YAXPEAU_EVENTLOGRECORD@@PEAVCLogInfo@@PEAGPEAVCSafeReg@@33W4PSK@@PEAPEAG@Z; ReplaceAllInserts(_EVENTLOGRECORD *,CLogInfo *,ushort *,CSafeReg *,CSafeReg *,CSafeReg *,PSK,ushort * *)
0x18000dc8c  mov     rbx, qword ptr [rsp+310h+Buffer]
0x18000dc91  lea     rcx, [rbp+210h+var_288]; this
  ... truncated ...
```
