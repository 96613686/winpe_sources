# CCachedINIFile::GetString(ushort const *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x1800171bc`
- end: `0x18001778c`
- name: `?GetString@CCachedINIFile@@QEAAJPEBG00KPEAPEAG@Z`
- size: `1488`
- prototype: `__int64 __fastcall(CCachedINIFile *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, char, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180017030`
- `0x1800171bc`

## callees

- `0x1800171bc`
- `0x180017794`
- `0x18002dcc8`
- `0x180051980`
- `0x180062d24`
- `0x18043ffe8`
- `0x18054e286`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x180017687`
- `KERNEL32!lstrcmpW` at `0x180017687`
- `KERNEL32!LocalAlloc` at `0x18001740a`
- `KERNEL32!LocalAlloc` at `0x18001740a`
- `KERNEL32!LocalFree` at `0x180017560`
- `KERNEL32!LocalFree` at `0x180017560`
- `ntdll!RtlFreeAnsiString` at `0x180017271`
- `ntdll!RtlFreeAnsiString` at `0x1800173c9`
- `ntdll!RtlFreeAnsiString` at `0x180017271`
- `ntdll!RtlFreeAnsiString` at `0x1800173c9`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18001724e`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18001734c`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18001724e`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18001734c`
- `iertutil!__imp_DPA_GetPtr` at `0x1800172ef`
- `iertutil!__imp_DPA_GetPtr` at `0x1800175ac`
- `iertutil!__imp_DPA_GetPtr` at `0x1800172ef`
- `iertutil!__imp_DPA_GetPtr` at `0x1800175ac`
- `iertutil!__imp_DPA_Search` at `0x1800172ce`
- `iertutil!__imp_DPA_Search` at `0x1800173aa`
- `iertutil!__imp_DPA_Search` at `0x1800172ce`
- `iertutil!__imp_DPA_Search` at `0x1800173aa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1800175dc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1800175dc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001758a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001759a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180017624`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800176ea`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800176fb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001771d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180017778`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001758a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001759a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180017624`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800176ea`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800176fb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001771d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180017778`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18001760e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18001760e`

## pseudocode

```c
__int64 __fastcall CCachedINIFile::GetString(
        CCachedINIFile *this,
        WCHAR *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        char a5,
        unsigned __int16 **a6)
{
  _DWORD *v6; // rax
  WCHAR *v7; // rsi
  WCHAR *v8; // r15
  signed int v10; // ebx
  __int64 v11; // r12
  int v12; // edi
  __int64 v13; // rax
  NTSTATUS v14; // eax
  LPARAM lParam; // rcx
  int v17; // eax
  __int64 v18; // rcx
  PVOID Ptr; // rdi
  struct _DPA *v20; // r10
  __int64 v21; // rax
  NTSTATUS v22; // eax
  LPARAM v23; // rcx
  int v24; // eax
  __int64 v25; // rax
  unsigned int v26; // edi
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // r14
  __int64 v29; // r8
  __int64 v30; // r11
  __int64 v31; // r9
  __int64 v32; // rax
  unsigned __int16 *v33; // r10
  unsigned __int16 *v34; // rcx
  unsigned int v35; // edx
  __int64 v36; // rcx
  unsigned __int16 *v37; // rax
  signed int String; // edi
  __int64 v39; // rax
  const unsigned __int16 *v40; // rcx
  unsigned __int16 *v41; // rdx
  __int64 i; // r8
  unsigned __int16 *v43; // rcx
  unsigned __int16 *v44; // r15
  PVOID v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rcx
  const CHAR *v48; // r14
  __int64 v49; // rax
  SIZE_T v50; // rbx
  void *v51; // rax
  void *v52; // rdi
  size_t v53; // rax
  signed int v54; // eax
  WCHAR *v55; // rdi
  UNICODE_STRING SourceString; // [rsp+30h] [rbp-40h] BYREF
  __int64 v57; // [rsp+40h] [rbp-30h]
  _STRING DestinationString; // [rsp+48h] [rbp-28h] BYREF
  __int128 v59; // [rsp+58h] [rbp-18h]
  LPCWSTR lpString2; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 *v61; // [rsp+C0h] [rbp+50h]
  LPVOID pv; // [rsp+C8h] [rbp+58h] BYREF

  pv = a4;
  v61 = a3;
  v6 = (_DWORD *)*((_QWORD *)this + 134);
  v7 = 0;
  v8 = a2;
  if ( !v6 || !*v6 )
    return (unsigned int)-2147467259;
  v11 = -1;
  v12 = 0;
  v10 = 0;
  DestinationString = 0;
  if ( *((_DWORD *)this + 266) )
    goto LABEL_14;
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  v13 = -1;
  SourceString.Buffer = a2;
  do
    ++v13;
  while ( a2[v13] );
  SourceString.Length = 2 * v13;
  SourceString.MaximumLength = 2 * v13 + 2;
  v14 = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 1u);
  v10 = v14;
  if ( v14 > 0 )
    v10 = (unsigned __int16)v14 | 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_14:
    lParam = *((int *)this + 266);
    v57 = 0;
    if ( (_DWORD)lParam )
      SourceString.Buffer = v8;
    else
      *(_QWORD *)&SourceString.Length = DestinationString.Buffer;
    v17 = DPA_Search(*((HDPA *)this + 134), &SourceString, 0, CCachedINIFile::s_CompareSection, lParam, 0);
    if ( v17 == -1 )
      v10 = -2147467259;
    else
      v12 = v17;
  }
  if ( DestinationString.Buffer )
    RtlFreeAnsiString(&DestinationString);
  if ( v10 >= 0 )
  {
    v10 = -2147467259;
    Ptr = DPA_GetPtr(*((HDPA *)this + 134), v12);
    pv = 0;
    v20 = (struct _DPA *)*((_QWORD *)Ptr + 2);
    if ( !v20 )
      goto LABEL_33;
    SourceString = 0;
    if ( !*((_DWORD *)this + 266) )
    {
      v21 = -1;
      DestinationString.Buffer = (PCHAR)v61;
      *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
      do
        ++v21;
      while ( v61[v21] );
      DestinationString.Length = 2 * v21;
      DestinationString.MaximumLength = 2 * v21 + 2;
      v22 = RtlUnicodeStringToAnsiString((PANSI_STRING)&SourceString, (PCUNICODE_STRING)&DestinationString, 1u);
      v10 = v22;
      if ( v22 > 0 )
        v10 = (unsigned __int16)v22 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_31;
      v20 = (struct _DPA *)*((_QWORD *)Ptr + 2);
    }
    v23 = *((int *)this + 266);
    DestinationString = 0;
    v59 = 0;
    if ( (_DWORD)v23 )
      DestinationString.Buffer = (PCHAR)v61;
    else
      *(_QWORD *)&DestinationString.Length = SourceString.Buffer;
    v24 = DPA_Search(v20, &DestinationString, 0, CCachedINIFile::s_CompareSection, v23, 0);
    if ( v24 == -1 )
    {
      v10 = -2147467259;
    }
    else
    {
      v45 = DPA_GetPtr(*((HDPA *)Ptr + 2), v24);
      if ( *((_DWORD *)this + 266) )
      {
        v54 = _AllocString<CTCoAllocPolicy>(v47, v46, *((_QWORD *)v45 + 3), &pv);
        v7 = (WCHAR *)pv;
        v10 = v54;
      }
      else
      {
        v48 = (const CHAR *)*((_QWORD *)v45 + 2);
        v49 = -1;
        do
          ++v49;
        while ( v48[v49] );
        v50 = 2 * (int)v49 + 2;
        v51 = CoTaskMemAlloc(v50);
        v52 = v51;
        if ( v51 )
        {
          v53 = CTCoAllocPolicy::_CoTaskMemSize(v51);
          memset_0(v52, 0, v53);
          if ( SHAnsiToUnicode(v48, (PWSTR)v52, v50 >> 1) )
          {
            v7 = (WCHAR *)v52;
            v10 = 0;
            v52 = 0;
          }
          else
          {
            v10 = -2147467259;
          }
          CoTaskMemFree(v52);
        }
        else
        {
          v10 = -2147024882;
        }
      }
    }
LABEL_31:
    if ( SourceString.Buffer )
      RtlFreeAnsiString((PANSI_STRING)&SourceString);
LABEL_33:
    if ( v10 < 0 )
      return (unsigned int)v10;
    if ( (a5 & 1) == 0 )
      goto LABEL_64;
    *(_QWORD *)&SourceString.Length = 0;
    if ( !*v7 )
      goto LABEL_64;
    v25 = -1;
    do
      ++v25;
    while ( v8[v25] );
    v26 = v25 + 3;
    v27 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(2 * (v25 + 3)));
    v28 = v27;
    if ( !v27 )
      goto LABEL_64;
    v29 = v26;
    if ( v26 )
    {
      if ( v26 > 0x7FFFFFFFuLL )
      {
        v35 = -2147024809;
        *v27 = 0;
      }
      else
      {
        v30 = 2147483646;
        v31 = v26;
        v32 = 2147483646;
        v33 = v28;
        do
        {
          if ( !v32 )
            break;
          if ( !*v8 )
            break;
          *v33++ = *v8++;
          --v32;
          --v31;
        }
        while ( v31 );
        v34 = v33 - 1;
        v35 = v31 == 0 ? 0x8007007A : 0;
        if ( v31 )
          v34 = v33;
        *v34 = 0;
        if ( v31 )
        {
          v36 = v26;
          v37 = v28;
          do
          {
            if ( !*v37 )
              break;
            ++v37;
            --v36;
          }
          while ( v36 );
          String = v36 == 0 ? 0x80070057 : 0;
          if ( v36 )
            v39 = v29 - v36;
          else
            v39 = 0;
          if ( v36 )
          {
            v40 = L".A";
            v41 = &v28[v39];
            for ( i = v29 - v39; i; --i )
            {
              if ( !v30 )
                break;
              if ( !*v40 )
                break;
              *v41++ = *v40++;
              --v30;
            }
            v43 = v41 - 1;
            String = i == 0 ? 0x8007007A : 0;
            if ( i )
              v43 = v41;
            *v43 = 0;
            if ( i )
            {
              v44 = v61;
              lpString2 = 0;
              String = CCachedINIFile::GetString(this, v28, v61, &SrcStr, 0, (unsigned __int16 **)&lpString2);
              if ( String >= 0 )
              {
                if ( lstrcmpW(v7, lpString2) )
                {
                  String = -2147467259;
                }
                else
                {
                  if ( *v28 )
                  {
                    do
                      ++v11;
                    while ( v28[v11] );
                    v28[v11 - 1] = 87;
                  }
                  pv = 0;
                  String = CCachedINIFile::GetString(this, v28, v44, &SrcStr, 0, (unsigned __int16 **)&pv);
                  if ( String >= 0 )
                  {
                    String = ConvertToUnicodeUTF7((const unsigned __int16 *)pv, (unsigned __int16 **)&SourceString);
                    CoTaskMemFree(pv);
                  }
                }
                CoTaskMemFree((LPVOID)lpString2);
              }
            }
          }
          goto LABEL_62;
        }
      }
    }
    else
    {
      v35 = -2147024809;
    }
    String = v35;
LABEL_62:
    LocalFree(v28);
    if ( String >= 0 )
    {
      CoTaskMemFree(v7);
      v7 = *(WCHAR **)&SourceString.Length;
    }
LABEL_64:
    if ( (a5 & 2) == 0 )
      goto LABEL_65;
    pv = 0;
    v10 = _AllocArray<unsigned short,CTCoAllocPolicy>(v18, 1, 260, &pv);
    if ( v10 >= 0 )
    {
      v55 = (WCHAR *)pv;
      v10 = -2147467259;
      if ( (unsigned int)SHExpandEnvironmentStringsW(v7, (unsigned __int16 *)pv, 0x104u) )
      {
        CoTaskMemFree(v7);
        v7 = v55;
        v10 = 0;
        v55 = 0;
      }
      CoTaskMemFree(v55);
      if ( v10 >= 0 )
      {
LABEL_65:
        *a6 = v7;
        v7 = 0;
      }
    }
    CoTaskMemFree(v7);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800171bc  mov     [rsp-38h+arg_8], rbx
0x1800171c1  mov     [rsp-38h+pv], r9
0x1800171c6  mov     [rsp-38h+arg_10], r8
0x1800171cb  push    rbp
0x1800171cc  push    rsi
0x1800171cd  push    rdi
0x1800171ce  push    r12
0x1800171d0  push    r13
0x1800171d2  push    r14
0x1800171d4  push    r15
0x1800171d6  mov     rbp, rsp
0x1800171d9  sub     rsp, 70h
0x1800171dd  mov     rax, [rcx+430h]
0x1800171e4  xor     esi, esi
0x1800171e6  mov     r15, rdx
0x1800171e9  mov     r13, rcx
0x1800171ec  test    rax, rax
0x1800171ef  jnz     short loc_1800171FB
0x1800171f1  mov     ebx, 80004005h
0x1800171f6  jmp     loc_18001727B
0x1800171fb  cmp     [rax], esi
0x1800171fd  jz      short loc_1800171F1
0x1800171ff  or      r12, 0FFFFFFFFFFFFFFFFh
0x180017203  xorps   xmm0, xmm0
0x180017206  mov     edi, esi
0x180017208  mov     ebx, esi
0x18001720a  mov     r14d, 80004005h
0x180017210  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180017214  lea     ecx, [r12+3]
0x180017219  cmp     [r13+428h], esi
0x180017220  jnz     short loc_180017295
0x180017222  mov     dword ptr [rbp+SourceString+4], esi
0x180017225  mov     rax, r12
0x180017228  mov     [rbp+SourceString.Buffer], r15
0x18001722c  inc     rax
0x18001722f  cmp     [rdx+rax*2], si
0x180017233  jnz     short loc_18001722C
0x180017235  add     ax, ax
0x180017238  lea     rdx, [rbp+SourceString]; SourceString
0x18001723c  mov     [rbp+SourceString.Length], ax
0x180017240  mov     r8b, 1; AllocateDestinationString
0x180017243  add     ax, cx
0x180017246  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001724a  mov     [rbp+SourceString.MaximumLength], ax
0x18001724e  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180017254  mov     ebx, eax
0x180017256  test    eax, eax
0x180017258  jle     short loc_180017263
0x18001725a  movzx   ebx, ax
0x18001725d  or      ebx, 80070000h
0x180017263  test    ebx, ebx
0x180017265  jns     short loc_180017295
0x180017267  cmp     [rbp+DestinationString.Buffer], rsi
0x18001726b  jz      short loc_180017277
0x18001726d  lea     rcx, [rbp+DestinationString]; AnsiString
0x180017271  call    cs:__imp_RtlFreeAnsiString
0x180017277  test    ebx, ebx
0x180017279  jns     short loc_1800172E2
0x18001727b  mov     eax, ebx
0x18001727d  mov     rbx, [rsp+70h+arg_8]
0x180017285  add     rsp, 70h
0x180017289  pop     r15
0x18001728b  pop     r14
0x18001728d  pop     r13
0x18001728f  pop     r12
0x180017291  pop     rdi
0x180017292  pop     rsi
0x180017293  pop     rbp
0x180017294  retn
0x180017295  movsxd  rcx, dword ptr [r13+428h]
0x18001729c  mov     [rbp+var_30], rsi
0x1800172a0  test    ecx, ecx
0x1800172a2  jnz     loc_18001762F
0x1800172a8  mov     rax, [rbp+DestinationString.Buffer]
0x1800172ac  mov     qword ptr [rbp+SourceString.Length], rax
0x1800172b0  mov     [rsp+70h+options], esi; options
0x1800172b4  lea     r9, ?s_CompareSection@CCachedINIFile@@CAHPEBUINISECTION@@0_J@Z; pfnCompare
0x1800172bb  mov     [rsp+70h+lParam], rcx; lParam
0x1800172c0  lea     rdx, [rbp+SourceString]; pFind
0x1800172c4  mov     rcx, [r13+430h]; hdpa
0x1800172cb  xor     r8d, r8d; iStart
0x1800172ce  call    cs:__imp_DPA_Search
0x1800172d4  cmp     eax, r12d
0x1800172d7  jnz     short loc_1800172DE
0x1800172d9  mov     ebx, r14d
0x1800172dc  jmp     short loc_180017267
0x1800172de  mov     edi, eax
0x1800172e0  jmp     short loc_180017267
0x1800172e2  mov     rcx, [r13+430h]; hdpa
0x1800172e9  mov     ebx, r14d
0x1800172ec  movsxd  rdx, edi; i
0x1800172ef  call    cs:__imp_DPA_GetPtr
0x1800172f5  mov     rdi, rax
0x1800172f8  mov     [rbp+pv], rsi
0x1800172fc  mov     r10, [rax+10h]
0x180017300  test    r10, r10
0x180017303  jz      loc_1800173CF
0x180017309  xor     ebx, ebx
0x18001730b  xorps   xmm0, xmm0
0x18001730e  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x180017312  cmp     [r13+428h], ebx
0x180017319  jnz     short loc_18001736E
0x18001731b  mov     rcx, [rbp+arg_10]
0x18001731f  mov     rax, r12
0x180017322  mov     [rbp+DestinationString.Buffer], rcx
0x180017326  mov     dword ptr [rbp+DestinationString+4], ebx
0x180017329  inc     rax
0x18001732c  cmp     [rcx+rax*2], bx
0x180017330  jnz     short loc_180017329
0x180017332  add     ax, ax
0x180017335  lea     rdx, [rbp+DestinationString]; SourceString
0x180017339  mov     [rbp+DestinationString.Length], ax
0x18001733d  lea     rcx, [rbp+SourceString]; DestinationString
0x180017341  add     ax, 2
0x180017345  mov     r8b, 1; AllocateDestinationString
0x180017348  mov     [rbp+DestinationString.MaximumLength], ax
0x18001734c  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180017352  xor     r10d, r10d
0x180017355  mov     ebx, eax
0x180017357  test    eax, eax
0x180017359  jle     short loc_180017364
0x18001735b  movzx   ebx, ax
0x18001735e  or      ebx, 80070000h
0x180017364  test    ebx, ebx
0x180017366  js      short loc_1800173BF
0x180017368  mov     r10, [rdi+10h]
0x18001736c  xor     ebx, ebx
0x18001736e  movsxd  rcx, dword ptr [r13+428h]
0x180017375  xorps   xmm0, xmm0
0x180017378  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001737c  movups  [rbp+var_18], xmm0
0x180017380  test    ecx, ecx
0x180017382  jnz     loc_180017642
0x180017388  mov     rax, [rbp+SourceString.Buffer]
0x18001738c  mov     qword ptr [rbp+DestinationString.Length], rax
0x180017390  mov     [rsp+70h+options], ebx; options
0x180017394  lea     r9, ?s_CompareSection@CCachedINIFile@@CAHPEBUINISECTION@@0_J@Z; pfnCompare
0x18001739b  mov     [rsp+70h+lParam], rcx; lParam
0x1800173a0  lea     rdx, [rbp+DestinationString]; pFind
0x1800173a4  mov     rcx, r10; hdpa
0x1800173a7  xor     r8d, r8d; iStart
0x1800173aa  call    cs:__imp_DPA_Search
0x1800173b0  cmp     eax, r12d
0x1800173b3  jnz     loc_1800175A5
0x1800173b9  mov     ebx, r14d
0x1800173bc  xor     r10d, r10d
0x1800173bf  cmp     [rbp+SourceString.Buffer], r10
0x1800173c3  jz      short loc_1800173D2
0x1800173c5  lea     rcx, [rbp+SourceString]; AnsiString
0x1800173c9  call    cs:__imp_RtlFreeAnsiString
0x1800173cf  xor     r10d, r10d
0x1800173d2  test    ebx, ebx
0x1800173d4  js      loc_18001727B
0x1800173da  test    [rbp+arg_20], 1
0x1800173de  jz      loc_180017571
0x1800173e4  mov     qword ptr [rbp+SourceString.Length], r10
0x1800173e8  cmp     [rsi], r10w
0x1800173ec  jz      loc_180017571
0x1800173f2  mov     rax, r12
0x1800173f5  inc     rax
0x1800173f8  cmp     [r15+rax*2], r10w
0x1800173fd  jnz     short loc_1800173F5
0x1800173ff  lea     edi, [rax+3]
0x180017402  mov     ecx, 40h ; '@'; uFlags
0x180017407  lea     edx, [rdi+rdi]; uBytes
0x18001740a  call    cs:__imp_LocalAlloc
0x180017410  xor     r10d, r10d
0x180017413  mov     r14, rax
0x180017416  test    rax, rax
0x180017419  jz      loc_180017571
0x18001741f  mov     r8d, edi
0x180017422  test    edi, edi
0x180017424  jz      loc_180017706
0x18001742a  cmp     r8, 7FFFFFFFh
0x180017431  ja      loc_18001766E
0x180017437  mov     r11d, 7FFFFFFEh
0x18001743d  mov     r9d, r8d
0x180017440  mov     eax, r11d
0x180017443  mov     r10, r14
0x180017446  mov     edx, 2
0x18001744b  test    rax, rax
0x18001744e  jz      short loc_18001746C
0x180017450  movzx   ecx, word ptr [r15]
0x180017454  test    cx, cx
0x180017457  jz      short loc_18001746C
0x180017459  mov     [r10], cx
0x18001745d  add     r15, rdx
0x180017460  add     r10, rdx
0x180017463  dec     rax
0x180017466  sub     r9, 1
0x18001746a  jnz     short loc_18001744B
0x18001746c  lea     rcx, [r10-2]
0x180017470  mov     rax, r9
0x180017473  neg     rax
0x180017476  mov     r15d, 8007007Ah
0x18001747c  sbb     edx, edx
0x18001747e  not     edx
0x180017480  and     edx, r15d
0x180017483  test    r9, r9
0x180017486  cmovnz  rcx, r10
0x18001748a  xor     r10d, r10d
0x18001748d  mov     [rcx], r10w
0x180017491  test    r9, r9
0x180017494  jz      loc_180017713
0x18001749a  mov     rcx, r8
0x18001749d  lea     r9d, [r10+2]
0x1800174a1  mov     rax, r14
0x1800174a4  cmp     [rax], r10w
0x1800174a8  jz      short loc_1800174B3
0x1800174aa  add     rax, r9
0x1800174ad  sub     rcx, 1
0x1800174b1  jnz     short loc_1800174A4
0x1800174b3  mov     rax, rcx
0x1800174b6  neg     rax
0x1800174b9  sbb     edi, edi
0x1800174bb  not     edi
0x1800174bd  and     edi, 80070057h
0x1800174c3  test    rcx, rcx
0x1800174c6  jz      loc_180017678
0x1800174cc  mov     rax, r8
0x1800174cf  sub     rax, rcx
0x1800174d2  test    rcx, rcx
0x1800174d5  jz      loc_18001755D
0x1800174db  lea     rcx, aA_8; ".A"
0x1800174e2  lea     rdx, [r14+rax*2]
0x1800174e6  sub     r8, rax
0x1800174e9  jz      short loc_18001750A
0x1800174eb  test    r11, r11
0x1800174ee  jz      short loc_18001750A
0x1800174f0  movzx   eax, word ptr [rcx]
0x1800174f3  test    ax, ax
0x1800174f6  jz      short loc_18001750A
0x1800174f8  mov     [rdx], ax
0x1800174fb  add     rcx, r9
0x1800174fe  add     rdx, r9
0x180017501  dec     r11
0x180017504  sub     r8, 1
0x180017508  jnz     short loc_1800174EB
0x18001750a  mov     rax, r8
0x18001750d  lea     rcx, [rdx-2]
0x180017511  neg     rax
0x180017514  sbb     edi, edi
0x180017516  not     edi
0x180017518  and     edi, r15d
0x18001751b  test    r8, r8
0x18001751e  cmovnz  rcx, rdx
0x180017522  mov     [rcx], r10w
0x180017526  jz      short loc_18001755D
0x180017528  mov     r15, [rbp+arg_10]
0x18001752c  lea     rax, [rbp+lpString2]
0x180017530  mov     qword ptr [rsp+70h+options], rax; unsigned __int16 **
0x180017535  lea     r9, SrcStr; unsigned __int16 *
0x18001753c  mov     r8, r15; unsigned __int16 *
0x18001753f  mov     dword ptr [rsp+70h+lParam], r10d; char
0x180017544  mov     rdx, r14; unsigned __int16 *
0x180017547  mov     [rbp+lpString2], r10
0x18001754b  mov     rcx, r13; this
0x18001754e  call    ?GetString@CCachedINIFile@@QEAAJPEBG00KPEAPEAG@Z; CCachedINIFile::GetString(ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x180017553  mov     edi, eax
0x180017555  test    eax, eax
0x180017557  jns     loc_180017680
0x18001755d  mov     rcx, r14; hMem
0x180017560  call    cs:__imp_LocalFree
0x180017566  xor     r10d, r10d
0x180017569  test    edi, edi
0x18001756b  jns     loc_18001771A
0x180017571  test    [rbp+arg_20], 2
0x180017575  jnz     loc_18001772F
0x18001757b  mov     rax, [rbp+arg_28]
0x18001757f  mov     [rax], rsi
0x180017582  mov     rsi, r10
0x180017585  jmp     short loc_180017597
0x180017587  mov     rcx, rdi; pv
0x18001758a  call    cs:__imp_CoTaskMemFree
0x180017590  xor     r10d, r10d
0x180017593  test    ebx, ebx
0x180017595  jns     short loc_18001757B
0x180017597  mov     rcx, rsi; pv
0x18001759a  call    cs:__imp_CoTaskMemFree
0x1800175a0  jmp     loc_18001727B
0x1800175a5  mov     rcx, [rdi+10h]; hdpa
0x1800175a9  movsxd  rdx, eax; i
0x1800175ac  call    cs:__imp_DPA_GetPtr
0x1800175b2  cmp     [r13+428h], ebx
0x1800175b9  jnz     loc_18001764F
0x1800175bf  mov     r14, [rax+10h]
0x1800175c3  mov     rax, r12
0x1800175c6  inc     rax
0x1800175c9  cmp     [r14+rax], bl
0x1800175cd  jnz     short loc_1800175C6
0x1800175cf  lea     eax, ds:2[rax*2]
0x1800175d6  movsxd  rbx, eax
0x1800175d9  mov     rcx, rbx; cb
0x1800175dc  call    cs:__imp_CoTaskMemAlloc
0x1800175e2  xor     r10d, r10d
0x1800175e5  mov     rdi, rax
0x1800175e8  test    rax, rax
0x1800175eb  jz      short loc_180017638
0x1800175ed  mov     rcx, rax; void *
0x1800175f0  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
  ... truncated ...
```
