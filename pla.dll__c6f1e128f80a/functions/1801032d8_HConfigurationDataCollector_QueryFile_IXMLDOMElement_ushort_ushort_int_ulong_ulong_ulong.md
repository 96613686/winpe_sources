# HConfigurationDataCollector::QueryFile(IXMLDOMElement *,ushort *,ushort *,int,ulong *,ulong *,ulong *)

- ea: `0x1801032d8`
- end: `0x1801039ee`
- name: `?QueryFile@HConfigurationDataCollector@@AEAAJPEAUIXMLDOMElement@@PEAG1HPEAK22@Z`
- size: `1814`
- prototype: `int(HConfigurationDataCollector *__hidden this, struct IXMLDOMElement *, unsigned __int16 *, unsigned __int16 *, int, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800e8f0c`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x1800123d4`
- `0x180012ef0`
- `0x1801032d8`
- `0x1801357c8`
- `0x18013ae9a`
- `0x18013aee0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18010355b`
- `msvcrt!wcsrchr` at `0x18010355b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103691`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180103683`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180103683`

## string_xrefs

- `0x1801033f6`: `HConfigurationDataCollector::QueryFile`
- `0x180103505`: `HConfigurationDataCollector::QueryFile`
- `0x180103904`: `HConfigurationDataCollector::QueryFile`

## pseudocode

```c
__int64 __fastcall HConfigurationDataCollector::QueryFile(
        HConfigurationDataCollector *this,
        struct IXMLDOMElement *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5,
        unsigned int *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  signed int v12; // edi
  __int64 v13; // rbx
  WCHAR *v14; // rsi
  __int64 v15; // rbx
  LPCWSTR v16; // r15
  wchar_t *v17; // rax
  int v18; // ecx
  unsigned __int64 v19; // rdx
  __int64 v20; // rbx
  int v21; // eax
  DWORD FullPathNameW; // eax
  signed int LastError; // eax
  WCHAR *v24; // rcx
  bool v25; // cc
  __int64 v26; // rax
  OLECHAR *v27; // rdx
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v32; // [rsp+78h] [rbp-88h] BYREF
  LPWSTR FilePart; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpFileName; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v35; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v36; // [rsp+98h] [rbp-68h]
  int v37; // [rsp+A0h] [rbp-60h]
  unsigned int *v38; // [rsp+A8h] [rbp-58h]
  unsigned int *v39; // [rsp+B0h] [rbp-50h]
  int v40; // [rsp+B8h] [rbp-48h]
  __int64 v41; // [rsp+C0h] [rbp-40h]
  struct IXMLDOMElement *v42; // [rsp+C8h] [rbp-38h]
  __int64 v43; // [rsp+D0h] [rbp-30h]
  unsigned int *v44; // [rsp+E0h] [rbp-20h]
  int v45; // [rsp+E8h] [rbp-18h]
  BOOL v46; // [rsp+ECh] [rbp-14h]
  int v47; // [rsp+F0h] [rbp-10h]
  unsigned __int16 v48[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v49[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v50[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v51[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v52[64]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v53[64]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v54[64]; // [rsp+400h] [rbp+300h] BYREF

  v32 = a8;
  FilePart = 0;
  memset_0(&v35, 0, 0x68u);
  lpFileName = (LPCWSTR)PlaiAlloc(0x800u, 1, 0, qword_180147320, v29);
  if ( !lpFileName )
  {
    v12 = -2147024882;
    LODWORD(v32) = -2147024882;
    v31 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v48, 0x4000000000000800uLL);
      v13 = -1;
      do
        ++v13;
      while ( v48[v13] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v32,
        4,
        qword_180147320,
        1,
        &v31,
        4,
        "HConfigurationDataCollector::QueryFile",
        39);
    }
    return (unsigned int)v12;
  }
  v14 = (WCHAR *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v30);
  if ( !v14 )
  {
    v12 = -2147024882;
    LODWORD(v32) = 0;
    v31 = -2147024882;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v49, 0x4000000000000800uLL);
      v15 = -1;
      do
        ++v15;
      while ( v49[v15] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v31,
        4,
        qword_180147320,
        1,
        &v32,
        4,
        "HConfigurationDataCollector::QueryFile",
        39);
    }
    v16 = lpFileName;
    goto LABEL_69;
  }
  v17 = wcsrchr(a4, 0x5Cu);
  if ( a4 < v17 && *(v17 - 1) == 92 )
  {
    v18 = 30;
    if ( (unsigned int)(*((_DWORD *)this + 55) - 1) <= 0x1D )
      v18 = *((_DWORD *)this + 55);
    v37 = v18;
  }
  else
  {
    v37 = 0;
  }
  v19 = *((_QWORD *)this + 9);
  v41 = *((_QWORD *)this + 32);
  v38 = a6;
  v42 = a2;
  v35 = a3;
  v20 = -1;
  v16 = lpFileName;
  v46 = *((_WORD *)this + 26) == 0xFFFF;
  v39 = a7;
  v40 = 0;
  v43 = *(_QWORD *)(*(_QWORD *)(v19 + 56) + 16LL);
  v45 = *(_DWORD *)(v19 + 32);
  v44 = v32;
  v47 = a5;
  v21 = PlaiExpandVariables((unsigned __int16 *)lpFileName, v19, a4);
  v12 = v21;
  if ( v21 >= 0 )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0x400u, v14, &FilePart);
    if ( !FullPathNameW )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v32) = 0;
      v31 = v12;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_69;
      }
      PlaiWhoAmI(v51, 0x4000000000000800uLL);
      do
        ++v20;
      while ( v51[v20] );
      goto LABEL_68;
    }
    if ( FullPathNameW < 0x400 )
    {
      v24 = FilePart;
      v25 = FilePart <= v14;
      if ( FilePart < v14 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v14[v26] );
        v24 = &v14[v26];
        FilePart = v24;
        v25 = v24 <= v14;
      }
      if ( !v25 && *(v24 - 1) == 92 )
      {
        *(v24 - 1) = 0;
        v24 = FilePart;
      }
      v27 = (OLECHAR *)L"*";
      if ( *v24 )
        v27 = v24;
      v36 = v27;
      if ( !a5 )
      {
        *v38 = 0;
        v12 = PlaiForEachFile<_PLA_FILE_CONTEXT *,long (*)(unsigned short const *,unsigned short const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *)>(
                v14,
                v36);
        if ( v12 < 0
          || v37
          && (v12 = PlaiForEachFile<_PLA_FILE_CONTEXT *,long (*)(unsigned short const *,unsigned short const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *)>(
                      v14,
                      L"*"),
              v12 < 0) )
        {
          LODWORD(v32) = 0;
          v31 = v12;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v53, 0x4000000000000800uLL);
            do
              ++v20;
            while ( v53[v20] );
            goto LABEL_68;
          }
          goto LABEL_69;
        }
        v27 = v36;
      }
      v12 = PlaiForEachFile<_PLA_FILE_CONTEXT *,long (*)(unsigned short const *,unsigned short const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *)>(
              v14,
              v27);
      if ( !v12 )
      {
        if ( !v37 )
          goto LABEL_69;
        v12 = PlaiForEachFile<_PLA_FILE_CONTEXT *,long (*)(unsigned short const *,unsigned short const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *)>(
                v14,
                L"*");
      }
      if ( v12 < 0 )
      {
        LODWORD(v32) = 0;
        v31 = v12;
        if ( (_DWORD)xmmword_180169738 )
        {
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v54, 0x4000000000000800uLL);
            do
              ++v20;
            while ( v54[v20] );
            goto LABEL_68;
          }
        }
      }
    }
    else
    {
      v12 = -2147024774;
      v31 = -2147024774;
      LODWORD(v32) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v52, 0x4000000000000800uLL);
        do
          ++v20;
        while ( v52[v20] );
        goto LABEL_68;
      }
    }
  }
  else
  {
    LODWORD(v32) = 0;
    v31 = v21;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v50, 0x4000000000000800uLL);
      do
        ++v20;
      while ( v50[v20] );
LABEL_68:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v31,
        4,
        qword_180147320,
        1,
        &v32,
        4,
        "HConfigurationDataCollector::QueryFile",
        39);
    }
  }
LABEL_69:
  PlaiFree(v16, 1);
  if ( v14 )
    PlaiFree(v14, 1);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1801032d8  push    rbp
0x1801032da  push    rbx
0x1801032db  push    rsi
0x1801032dc  push    rdi
0x1801032dd  push    r12
0x1801032df  push    r13
0x1801032e1  push    r14
0x1801032e3  push    r15
0x1801032e5  lea     rbp, [rsp-398h]
0x1801032ed  sub     rsp, 498h
0x1801032f4  mov     rax, cs:__security_cookie
0x1801032fb  xor     rax, rsp
0x1801032fe  mov     [rbp+3D0h+var_50], rax
0x180103305  mov     rax, [rbp+3D0h+arg_38]
0x18010330c  xor     esi, esi
0x18010330e  mov     r12, [rbp+3D0h+arg_28]
0x180103315  mov     r15, r8
0x180103318  mov     r13, [rbp+3D0h+arg_30]
0x18010331f  mov     rbx, rdx
0x180103322  mov     r14, rcx
0x180103325  mov     [rsp+4D0h+var_458], rax
0x18010332a  lea     r8d, [rsi+68h]; Size
0x18010332e  mov     [rbp+3D0h+FilePart], rsi
0x180103332  xor     edx, edx; Val
0x180103334  lea     rcx, [rbp+3D0h+var_440]; void *
0x180103338  mov     rdi, r9
0x18010333b  call    memset_0
0x180103340  lea     r9, qword_180147320; char *
0x180103347  xor     r8d, r8d; int
0x18010334a  lea     edx, [rsi+1]; int
0x18010334d  mov     ecx, 800h; dwBytes
0x180103352  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x180103357  mov     [rbp+3D0h+lpFileName], rax
0x18010335b  test    rax, rax
0x18010335e  jnz     loc_180103440
0x180103364  cmp     dword ptr cs:xmmword_180169738, esi
0x18010336a  mov     eax, 8007000Eh
0x18010336f  mov     edi, eax
0x180103371  mov     dword ptr [rsp+4D0h+var_458], eax
0x180103375  mov     [rsp+4D0h+var_460], esi
0x180103379  jz      loc_180103968
0x18010337f  mov     rdx, 4000000000000800h; unsigned __int64
0x180103389  test    qword ptr cs:xmmword_180169738+8, rdx
0x180103390  jz      loc_180103968
0x180103396  mov     rax, cs:qword_180169748
0x18010339d  and     rax, rdx
0x1801033a0  cmp     cs:qword_180169748, rax
0x1801033a7  jnz     loc_180103968
0x1801033ad  lea     rcx, [rbp+3D0h+var_3D0]; unsigned __int16 *
0x1801033b1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801033b6  lea     rax, [rbp+3D0h+var_3D0]
0x1801033ba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801033be  inc     rbx
0x1801033c1  cmp     [rax+rbx*2], si
0x1801033c5  jnz     short loc_1801033BE
0x1801033c7  lea     rax, [rbp+3D0h+var_3D0]
0x1801033cb  lea     ecx, [rbx+rbx]
0x1801033ce  add     rcx, 2
0x1801033d2  lea     r9, [rsp+4D0h+var_458]
0x1801033d7  mov     [rsp+4D0h+var_470], rcx
0x1801033dc  lea     rdx, PLA_EVENT_ERROR
0x1801033e3  mov     [rsp+4D0h+var_478], rax
0x1801033e8  lea     rcx, [rsp+4D0h+var_460]
0x1801033ed  mov     [rsp+4D0h+var_480], 27h ; '''
0x1801033f6  lea     rax, aHconfiguration_0; "HConfigurationDataCollector::QueryFile"
0x1801033fd  mov     [rsp+4D0h+var_488], rax
0x180103402  mov     eax, 4
0x180103407  mov     [rsp+4D0h+var_490], rax
0x18010340c  mov     [rsp+4D0h+var_498], rcx
0x180103411  lea     rcx, qword_180147320
0x180103418  mov     [rsp+4D0h+var_4A0], 1
0x180103421  mov     [rsp+4D0h+var_4A8], rcx
0x180103426  lea     r8d, [rax+1]
0x18010342a  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180103431  mov     [rsp+4D0h+var_4B0], rax
0x180103436  call    EventingWriteEvent
0x18010343b  jmp     loc_180103968
0x180103440  xor     r8d, r8d; int
0x180103443  lea     r9, qword_180147320; char *
0x18010344a  mov     ecx, 800h; dwBytes
0x18010344f  lea     edx, [r8+1]; int
0x180103453  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x180103458  mov     rsi, rax
0x18010345b  test    rax, rax
0x18010345e  jnz     loc_180103553
0x180103464  xor     r12d, r12d
0x180103467  mov     eax, 8007000Eh
0x18010346c  cmp     dword ptr cs:xmmword_180169738, r12d
0x180103473  mov     edi, eax
0x180103475  mov     dword ptr [rsp+4D0h+var_458], r12d
0x18010347a  mov     [rsp+4D0h+var_460], eax
0x18010347e  jz      loc_18010354A
0x180103484  mov     rdx, 4000000000000800h; unsigned __int64
0x18010348e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180103495  jz      loc_18010354A
0x18010349b  mov     rax, cs:qword_180169748
0x1801034a2  and     rax, rdx
0x1801034a5  cmp     cs:qword_180169748, rax
0x1801034ac  jnz     loc_18010354A
0x1801034b2  lea     rcx, [rbp+3D0h+var_350]; unsigned __int16 *
0x1801034b9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801034be  lea     rax, [rbp+3D0h+var_350]
0x1801034c5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801034c9  inc     rbx
0x1801034cc  cmp     [rax+rbx*2], r12w
0x1801034d1  jnz     short loc_1801034C9
0x1801034d3  lea     rax, [rbp+3D0h+var_350]
0x1801034da  lea     ecx, [rbx+rbx]
0x1801034dd  add     rcx, 2
0x1801034e1  lea     r9, [rsp+4D0h+var_460]
0x1801034e6  mov     [rsp+4D0h+var_470], rcx
0x1801034eb  lea     rdx, PLA_EVENT_ERROR
0x1801034f2  mov     [rsp+4D0h+var_478], rax
0x1801034f7  lea     rcx, [rsp+4D0h+var_458]
0x1801034fc  mov     [rsp+4D0h+var_480], 27h ; '''
0x180103505  lea     rax, aHconfiguration_0; "HConfigurationDataCollector::QueryFile"
0x18010350c  mov     [rsp+4D0h+var_488], rax
0x180103511  mov     eax, 4
0x180103516  mov     [rsp+4D0h+var_490], rax
0x18010351b  mov     [rsp+4D0h+var_498], rcx
0x180103520  lea     rcx, qword_180147320
0x180103527  mov     [rsp+4D0h+var_4A0], 1
0x180103530  mov     [rsp+4D0h+var_4A8], rcx
0x180103535  lea     r8d, [rax+1]
0x180103539  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180103540  mov     [rsp+4D0h+var_4B0], rax
0x180103545  call    EventingWriteEvent
0x18010354a  mov     r15, [rbp+3D0h+lpFileName]
0x18010354e  jmp     loc_180103949
0x180103553  mov     edx, 5Ch ; '\'; Ch
0x180103558  mov     rcx, rdi; Str
0x18010355b  call    cs:__imp_wcsrchr
0x180103561  cmp     rdi, rax
0x180103564  jnb     short loc_18010358B
0x180103566  mov     ecx, 5Ch ; '\'
0x18010356b  cmp     cx, [rax-2]
0x18010356f  jnz     short loc_18010358B
0x180103571  mov     edx, [r14+0DCh]
0x180103578  mov     ecx, 1Eh
0x18010357d  lea     eax, [rdx-1]
0x180103580  cmp     eax, 1Dh
0x180103583  cmovbe  ecx, edx
0x180103586  mov     [rbp+3D0h+var_430], ecx
0x180103589  jmp     short loc_180103592
0x18010358b  mov     [rbp+3D0h+var_430], 0
0x180103592  mov     rax, [r14+100h]
0x180103599  mov     r8, rdi; unsigned __int16 *
0x18010359c  mov     rdx, [r14+48h]; unsigned __int64
0x1801035a0  mov     [rbp+3D0h+var_410], rax
0x1801035a4  mov     [rbp+3D0h+var_428], r12
0x1801035a8  xor     r12d, r12d
0x1801035ab  mov     [rbp+3D0h+var_408], rbx
0x1801035af  mov     eax, r12d
0x1801035b2  mov     [rbp+3D0h+var_440], r15
0x1801035b6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801035ba  cmp     bx, [r14+34h]
0x1801035bf  mov     r15, [rbp+3D0h+lpFileName]
0x1801035c3  mov     r14d, [rbp+3D0h+arg_20]
0x1801035ca  setz    al
0x1801035cd  mov     [rbp+3D0h+var_3E4], eax
0x1801035d0  mov     [rbp+3D0h+var_420], r13
0x1801035d4  mov     [rbp+3D0h+var_418], r12d
0x1801035d8  mov     rax, [rdx+38h]
0x1801035dc  mov     rcx, [rax+10h]
0x1801035e0  mov     [rbp+3D0h+var_400], rcx
0x1801035e4  mov     rcx, r15; unsigned __int16 *
0x1801035e7  mov     eax, [rdx+20h]
0x1801035ea  mov     [rbp+3D0h+var_3E8], eax
0x1801035ed  mov     rax, [rsp+4D0h+var_458]
0x1801035f2  mov     [rbp+3D0h+var_3F0], rax
0x1801035f6  mov     [rbp+3D0h+var_3E0], r14d
0x1801035fa  call    ?PlaiExpandVariables@@YAJPEAG_KPEBG@Z; PlaiExpandVariables(ushort *,unsigned __int64,ushort const *)
0x1801035ff  mov     edi, eax
0x180103601  test    eax, eax
0x180103603  jns     short loc_180103672
0x180103605  cmp     dword ptr cs:xmmword_180169738, r12d
0x18010360c  mov     dword ptr [rsp+4D0h+var_458], r12d
0x180103611  mov     [rsp+4D0h+var_460], eax
0x180103615  jz      loc_180103949
0x18010361b  mov     rdx, 4000000000000800h; unsigned __int64
0x180103625  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010362c  jz      loc_180103949
0x180103632  mov     rax, cs:qword_180169748
0x180103639  and     rax, rdx
0x18010363c  cmp     cs:qword_180169748, rax
0x180103643  jnz     loc_180103949
0x180103649  lea     rcx, [rbp+3D0h+var_2D0]; unsigned __int16 *
0x180103650  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180103655  lea     rax, [rbp+3D0h+var_2D0]
0x18010365c  inc     rbx
0x18010365f  cmp     [rax+rbx*2], r12w
0x180103664  jnz     short loc_18010365C
0x180103666  lea     rax, [rbp+3D0h+var_2D0]
0x18010366d  jmp     loc_1801038D9
0x180103672  mov     edi, 400h
0x180103677  lea     r9, [rbp+3D0h+FilePart]; lpFilePart
0x18010367b  mov     edx, edi; nBufferLength
0x18010367d  mov     r8, rsi; lpBuffer
0x180103680  mov     rcx, r15; lpFileName
0x180103683  call    cs:__imp_GetFullPathNameW
0x180103689  test    eax, eax
0x18010368b  jnz     loc_180103713
0x180103691  call    cs:__imp_GetLastError
0x180103697  mov     edi, eax
0x180103699  test    eax, eax
0x18010369b  jle     short loc_1801036A6
0x18010369d  movzx   edi, ax
0x1801036a0  or      edi, 80070000h
0x1801036a6  cmp     dword ptr cs:xmmword_180169738, r12d
0x1801036ad  mov     dword ptr [rsp+4D0h+var_458], r12d
0x1801036b2  mov     [rsp+4D0h+var_460], edi
0x1801036b6  jz      loc_180103949
0x1801036bc  mov     rdx, 4000000000000800h; unsigned __int64
0x1801036c6  test    qword ptr cs:xmmword_180169738+8, rdx
0x1801036cd  jz      loc_180103949
0x1801036d3  mov     rax, cs:qword_180169748
0x1801036da  and     rax, rdx
0x1801036dd  cmp     cs:qword_180169748, rax
0x1801036e4  jnz     loc_180103949
0x1801036ea  lea     rcx, [rbp+3D0h+var_250]; unsigned __int16 *
0x1801036f1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801036f6  lea     rax, [rbp+3D0h+var_250]
0x1801036fd  inc     rbx
0x180103700  cmp     [rax+rbx*2], r12w
0x180103705  jnz     short loc_1801036FD
0x180103707  lea     rax, [rbp+3D0h+var_250]
0x18010370e  jmp     loc_1801038D9
0x180103713  cmp     eax, edi
0x180103715  jb      short loc_180103789
0x180103717  cmp     dword ptr cs:xmmword_180169738, r12d
0x18010371e  mov     edi, 8007007Ah
0x180103723  mov     [rsp+4D0h+var_460], edi
0x180103727  mov     dword ptr [rsp+4D0h+var_458], r12d
0x18010372c  jz      loc_180103949
0x180103732  mov     rdx, 4000000000000800h; unsigned __int64
0x18010373c  test    qword ptr cs:xmmword_180169738+8, rdx
0x180103743  jz      loc_180103949
0x180103749  mov     rax, cs:qword_180169748
0x180103750  and     rax, rdx
0x180103753  cmp     cs:qword_180169748, rax
0x18010375a  jnz     loc_180103949
0x180103760  lea     rcx, [rbp+3D0h+var_1D0]; unsigned __int16 *
0x180103767  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010376c  lea     rax, [rbp+3D0h+var_1D0]
0x180103773  inc     rbx
0x180103776  cmp     [rax+rbx*2], r12w
0x18010377b  jnz     short loc_180103773
0x18010377d  lea     rax, [rbp+3D0h+var_1D0]
0x180103784  jmp     loc_1801038D9
0x180103789  mov     rcx, [rbp+3D0h+FilePart]
0x18010378d  cmp     rcx, rsi
0x180103790  jnb     short loc_1801037AA
0x180103792  mov     rax, rbx
0x180103795  inc     rax
0x180103798  cmp     [rsi+rax*2], r12w
0x18010379d  jnz     short loc_180103795
0x18010379f  lea     rcx, [rsi+rax*2]
0x1801037a3  mov     [rbp+3D0h+FilePart], rcx
0x1801037a7  cmp     rcx, rsi
0x1801037aa  jbe     short loc_1801037C0
0x1801037ac  mov     eax, 5Ch ; '\'
0x1801037b1  cmp     [rcx-2], ax
0x1801037b5  jnz     short loc_1801037C0
0x1801037b7  mov     [rcx-2], r12w
0x1801037bc  mov     rcx, [rbp+3D0h+FilePart]
0x1801037c0  xor     eax, eax
0x1801037c2  lea     r13, asc_180147B0C; "*"
0x1801037c9  cmp     ax, [rcx]
0x1801037cc  mov     rdx, r13
0x1801037cf  cmovnz  rdx, rcx
0x1801037d3  mov     [rbp+3D0h+var_438], rdx
0x1801037d7  test    r14d, r14d
0x1801037da  jnz     short loc_18010382E
0x1801037dc  mov     rax, [rbp+3D0h+var_428]
0x1801037e0  lea     r9, [rbp+3D0h+var_440]
0x1801037e4  lea     r8, ?PlaiFileRecursiveFileCount@@YAJPEBG0PEAU_WIN32_FIND_DATAW@@PEAU_PLA_FILE_CONTEXT@@@Z; PlaiFileRecursiveFileCount(ushort const *,ushort const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *)
0x1801037eb  mov     rcx, rsi; unsigned __int16 *
0x1801037ee  mov     [rax], r12d
0x1801037f1  mov     rdx, [rbp+3D0h+var_438]; unsigned __int16 *
0x1801037f5  call    ??$PlaiForEachFile@PEAU_PLA_FILE_CONTEXT@@P6AJPEBG0PEAU_WIN32_FIND_DATAW@@PEAU1@@Z@@YAJPEBG0P6AJ00PEAU_WIN32_FIND_DATAW@@PEAU_PLA_FILE_CONTEXT@@@Z2@Z; PlaiForEachFile<_PLA_FILE_CONTEXT *,long (*)(ushort const *,ushort const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *)>(ushort const *,ushort const *,long (*)(ushort const *,ushort const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *),_PLA_FILE_CONTEXT *)
0x1801037fa  mov     edi, eax
0x1801037fc  test    eax, eax
0x1801037fe  js      loc_18010398D
0x180103804  cmp     [rbp+3D0h+var_430], r12d
0x180103808  jbe     short loc_18010382A
0x18010380a  lea     r9, [rbp+3D0h+var_440]
0x18010380e  mov     rdx, r13; unsigned __int16 *
0x180103811  lea     r8, ?PlaiFileRecursiveDirectoryCount@@YAJPEBG0PEAU_WIN32_FIND_DATAW@@PEAU_PLA_FILE_CONTEXT@@@Z; PlaiFileRecursiveDirectoryCount(ushort const *,ushort const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *)
0x180103818  mov     rcx, rsi; unsigned __int16 *
0x18010381b  call    ??$PlaiForEachFile@PEAU_PLA_FILE_CONTEXT@@P6AJPEBG0PEAU_WIN32_FIND_DATAW@@PEAU1@@Z@@YAJPEBG0P6AJ00PEAU_WIN32_FIND_DATAW@@PEAU_PLA_FILE_CONTEXT@@@Z2@Z; PlaiForEachFile<_PLA_FILE_CONTEXT *,long (*)(ushort const *,ushort const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *)>(ushort const *,ushort const *,long (*)(ushort const *,ushort const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *),_PLA_FILE_CONTEXT *)
0x180103820  mov     edi, eax
0x180103822  test    eax, eax
0x180103824  js      loc_18010398D
0x18010382a  mov     rdx, [rbp+3D0h+var_438]; unsigned __int16 *
0x18010382e  lea     r9, [rbp+3D0h+var_440]
0x180103832  mov     rcx, rsi; unsigned __int16 *
0x180103835  lea     r8, ?PlaiFileRecursiveFile@@YAJPEBG0PEAU_WIN32_FIND_DATAW@@PEAU_PLA_FILE_CONTEXT@@@Z; PlaiFileRecursiveFile(ushort const *,ushort const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *)
0x18010383c  call    ??$PlaiForEachFile@PEAU_PLA_FILE_CONTEXT@@P6AJPEBG0PEAU_WIN32_FIND_DATAW@@PEAU1@@Z@@YAJPEBG0P6AJ00PEAU_WIN32_FIND_DATAW@@PEAU_PLA_FILE_CONTEXT@@@Z2@Z; PlaiForEachFile<_PLA_FILE_CONTEXT *,long (*)(ushort const *,ushort const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *)>(ushort const *,ushort const *,long (*)(ushort const *,ushort const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *),_PLA_FILE_CONTEXT *)
0x180103841  mov     edi, eax
0x180103843  test    eax, eax
  ... truncated ...
```
