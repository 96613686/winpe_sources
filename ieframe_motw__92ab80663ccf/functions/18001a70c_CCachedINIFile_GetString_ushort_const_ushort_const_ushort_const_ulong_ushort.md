# CCachedINIFile::GetString(ushort const *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x18001a70c`
- end: `0x18001ad5f`
- name: `?GetString@CCachedINIFile@@QEAAJPEBG00KPEAPEAG@Z`
- size: `1619`
- prototype: `__int64 __fastcall(CCachedINIFile *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, char, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a580`
- `0x18001a70c`

## callees

- `0x18001a70c`
- `0x18001ad68`
- `0x180030298`
- `0x180055594`
- `0x180067574`
- `0x18047aab4`
- `0x180591ef6`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18001ac3c`
- `KERNEL32!lstrcmpW` at `0x18001ac3c`
- `KERNEL32!LocalAlloc` at `0x18001a98f`
- `KERNEL32!LocalAlloc` at `0x18001a98f`
- `KERNEL32!LocalFree` at `0x18001aaeb`
- `KERNEL32!LocalFree` at `0x18001aaeb`
- `ntdll!RtlFreeAnsiString` at `0x18001a7cb`
- `ntdll!RtlFreeAnsiString` at `0x18001a948`
- `ntdll!RtlFreeAnsiString` at `0x18001a7cb`
- `ntdll!RtlFreeAnsiString` at `0x18001a948`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18001a7a2`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18001a8bf`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18001a7a2`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18001a8bf`
- `iertutil!__imp_DPA_GetPtr` at `0x18001a85c`
- `iertutil!__imp_DPA_GetPtr` at `0x18001ab49`
- `iertutil!__imp_DPA_GetPtr` at `0x18001a85c`
- `iertutil!__imp_DPA_GetPtr` at `0x18001ab49`
- `iertutil!__imp_DPA_Search` at `0x18001a82f`
- `iertutil!__imp_DPA_Search` at `0x18001a923`
- `iertutil!__imp_DPA_Search` at `0x18001a82f`
- `iertutil!__imp_DPA_Search` at `0x18001a923`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18001ab7f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18001ab7f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001ab1b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001ab31`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001abd3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001aca5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001acbc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001ace4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001ad45`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001ab1b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001ab31`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001abd3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001aca5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001acbc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001ace4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18001ad45`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18001abb7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18001abb7`

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
              String = CCachedINIFile::GetString(this, v28, v61, &Default, 0, (unsigned __int16 **)&lpString2);
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
                  String = CCachedINIFile::GetString(this, v28, v44, &Default, 0, (unsigned __int16 **)&pv);
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
0x18001a70c  mov     [rsp-38h+arg_8], rbx
0x18001a711  mov     [rsp-38h+pv], r9
0x18001a716  mov     [rsp-38h+arg_10], r8
0x18001a71b  push    rbp
0x18001a71c  push    rsi
0x18001a71d  push    rdi
0x18001a71e  push    r12
0x18001a720  push    r13
0x18001a722  push    r14
0x18001a724  push    r15
0x18001a726  mov     rbp, rsp
0x18001a729  sub     rsp, 70h
0x18001a72d  mov     rax, [rcx+430h]
0x18001a734  xor     esi, esi
0x18001a736  mov     r15, rdx
0x18001a739  mov     r13, rcx
0x18001a73c  test    rax, rax
0x18001a73f  jnz     short loc_18001A74B
0x18001a741  mov     ebx, 80004005h
0x18001a746  jmp     loc_18001A7DB
0x18001a74b  cmp     [rax], esi
0x18001a74d  jz      short loc_18001A741
0x18001a74f  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001a753  xorps   xmm0, xmm0
0x18001a756  mov     edi, esi
0x18001a758  mov     ebx, esi
0x18001a75a  mov     r14d, 80004005h
0x18001a760  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001a764  lea     ecx, [r12+3]
0x18001a769  cmp     [r13+428h], esi
0x18001a770  jnz     loc_18001A7F6
0x18001a776  mov     dword ptr [rbp+SourceString+4], esi
0x18001a779  mov     rax, r12
0x18001a77c  mov     [rbp+SourceString.Buffer], r15
0x18001a780  inc     rax
0x18001a783  cmp     [rdx+rax*2], si
0x18001a787  jnz     short loc_18001A780
0x18001a789  add     ax, ax
0x18001a78c  lea     rdx, [rbp+SourceString]; SourceString
0x18001a790  mov     [rbp+SourceString.Length], ax
0x18001a794  mov     r8b, 1; AllocateDestinationString
0x18001a797  add     ax, cx
0x18001a79a  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001a79e  mov     [rbp+SourceString.MaximumLength], ax
0x18001a7a2  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18001a7a9  nop     dword ptr [rax+rax+00h]
0x18001a7ae  mov     ebx, eax
0x18001a7b0  test    eax, eax
0x18001a7b2  jle     short loc_18001A7BD
0x18001a7b4  movzx   ebx, ax
0x18001a7b7  or      ebx, 80070000h
0x18001a7bd  test    ebx, ebx
0x18001a7bf  jns     short loc_18001A7F6
0x18001a7c1  cmp     [rbp+DestinationString.Buffer], rsi
0x18001a7c5  jz      short loc_18001A7D7
0x18001a7c7  lea     rcx, [rbp+DestinationString]; AnsiString
0x18001a7cb  call    cs:__imp_RtlFreeAnsiString
0x18001a7d2  nop     dword ptr [rax+rax+00h]
0x18001a7d7  test    ebx, ebx
0x18001a7d9  jns     short loc_18001A84F
0x18001a7db  mov     eax, ebx
0x18001a7dd  mov     rbx, [rsp+70h+arg_8]
0x18001a7e5  add     rsp, 70h
0x18001a7e9  pop     r15
0x18001a7eb  pop     r14
0x18001a7ed  pop     r13
0x18001a7ef  pop     r12
0x18001a7f1  pop     rdi
0x18001a7f2  pop     rsi
0x18001a7f3  pop     rbp
0x18001a7f4  retn
0x18001a7f6  movsxd  rcx, dword ptr [r13+428h]
0x18001a7fd  mov     [rbp+var_30], rsi
0x18001a801  test    ecx, ecx
0x18001a803  jnz     loc_18001ABE4
0x18001a809  mov     rax, [rbp+DestinationString.Buffer]
0x18001a80d  mov     qword ptr [rbp+SourceString.Length], rax
0x18001a811  mov     [rsp+70h+options], esi; options
0x18001a815  lea     r9, ?s_CompareSection@CCachedINIFile@@CAHPEBUINISECTION@@0_J@Z; pfnCompare
0x18001a81c  mov     [rsp+70h+lParam], rcx; lParam
0x18001a821  lea     rdx, [rbp+SourceString]; pFind
0x18001a825  mov     rcx, [r13+430h]; hdpa
0x18001a82c  xor     r8d, r8d; iStart
0x18001a82f  call    cs:__imp_DPA_Search
0x18001a836  nop     dword ptr [rax+rax+00h]
0x18001a83b  cmp     eax, r12d
0x18001a83e  jnz     short loc_18001A848
0x18001a840  mov     ebx, r14d
0x18001a843  jmp     loc_18001A7C1
0x18001a848  mov     edi, eax
0x18001a84a  jmp     loc_18001A7C1
0x18001a84f  mov     rcx, [r13+430h]; hdpa
0x18001a856  mov     ebx, r14d
0x18001a859  movsxd  rdx, edi; i
0x18001a85c  call    cs:__imp_DPA_GetPtr
0x18001a863  nop     dword ptr [rax+rax+00h]
0x18001a868  mov     rdi, rax
0x18001a86b  mov     [rbp+pv], rsi
0x18001a86f  mov     r10, [rax+10h]
0x18001a873  test    r10, r10
0x18001a876  jz      loc_18001A954
0x18001a87c  xor     ebx, ebx
0x18001a87e  xorps   xmm0, xmm0
0x18001a881  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x18001a885  cmp     [r13+428h], ebx
0x18001a88c  jnz     short loc_18001A8E7
0x18001a88e  mov     rcx, [rbp+arg_10]
0x18001a892  mov     rax, r12
0x18001a895  mov     [rbp+DestinationString.Buffer], rcx
0x18001a899  mov     dword ptr [rbp+DestinationString+4], ebx
0x18001a89c  inc     rax
0x18001a89f  cmp     [rcx+rax*2], bx
0x18001a8a3  jnz     short loc_18001A89C
0x18001a8a5  add     ax, ax
0x18001a8a8  lea     rdx, [rbp+DestinationString]; SourceString
0x18001a8ac  mov     [rbp+DestinationString.Length], ax
0x18001a8b0  lea     rcx, [rbp+SourceString]; DestinationString
0x18001a8b4  add     ax, 2
0x18001a8b8  mov     r8b, 1; AllocateDestinationString
0x18001a8bb  mov     [rbp+DestinationString.MaximumLength], ax
0x18001a8bf  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18001a8c6  nop     dword ptr [rax+rax+00h]
0x18001a8cb  xor     r10d, r10d
0x18001a8ce  mov     ebx, eax
0x18001a8d0  test    eax, eax
0x18001a8d2  jle     short loc_18001A8DD
0x18001a8d4  movzx   ebx, ax
0x18001a8d7  or      ebx, 80070000h
0x18001a8dd  test    ebx, ebx
0x18001a8df  js      short loc_18001A93E
0x18001a8e1  mov     r10, [rdi+10h]
0x18001a8e5  xor     ebx, ebx
0x18001a8e7  movsxd  rcx, dword ptr [r13+428h]
0x18001a8ee  xorps   xmm0, xmm0
0x18001a8f1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001a8f5  movups  [rbp+var_18], xmm0
0x18001a8f9  test    ecx, ecx
0x18001a8fb  jnz     loc_18001ABF7
0x18001a901  mov     rax, [rbp+SourceString.Buffer]
0x18001a905  mov     qword ptr [rbp+DestinationString.Length], rax
0x18001a909  mov     [rsp+70h+options], ebx; options
0x18001a90d  lea     r9, ?s_CompareSection@CCachedINIFile@@CAHPEBUINISECTION@@0_J@Z; pfnCompare
0x18001a914  mov     [rsp+70h+lParam], rcx; lParam
0x18001a919  lea     rdx, [rbp+DestinationString]; pFind
0x18001a91d  mov     rcx, r10; hdpa
0x18001a920  xor     r8d, r8d; iStart
0x18001a923  call    cs:__imp_DPA_Search
0x18001a92a  nop     dword ptr [rax+rax+00h]
0x18001a92f  cmp     eax, r12d
0x18001a932  jnz     loc_18001AB42
0x18001a938  mov     ebx, r14d
0x18001a93b  xor     r10d, r10d
0x18001a93e  cmp     [rbp+SourceString.Buffer], r10
0x18001a942  jz      short loc_18001A957
0x18001a944  lea     rcx, [rbp+SourceString]; AnsiString
0x18001a948  call    cs:__imp_RtlFreeAnsiString
0x18001a94f  nop     dword ptr [rax+rax+00h]
0x18001a954  xor     r10d, r10d
0x18001a957  test    ebx, ebx
0x18001a959  js      loc_18001A7DB
0x18001a95f  test    [rbp+arg_20], 1
0x18001a963  jz      loc_18001AB02
0x18001a969  mov     qword ptr [rbp+SourceString.Length], r10
0x18001a96d  cmp     [rsi], r10w
0x18001a971  jz      loc_18001AB02
0x18001a977  mov     rax, r12
0x18001a97a  inc     rax
0x18001a97d  cmp     [r15+rax*2], r10w
0x18001a982  jnz     short loc_18001A97A
0x18001a984  lea     edi, [rax+3]
0x18001a987  mov     ecx, 40h ; '@'; uFlags
0x18001a98c  lea     edx, [rdi+rdi]; uBytes
0x18001a98f  call    cs:__imp_LocalAlloc
0x18001a996  nop     dword ptr [rax+rax+00h]
0x18001a99b  xor     r10d, r10d
0x18001a99e  mov     r14, rax
0x18001a9a1  test    rax, rax
0x18001a9a4  jz      loc_18001AB02
0x18001a9aa  mov     r8d, edi
0x18001a9ad  test    edi, edi
0x18001a9af  jz      loc_18001ACCD
0x18001a9b5  cmp     r8, 7FFFFFFFh
0x18001a9bc  ja      loc_18001AC23
0x18001a9c2  mov     r11d, 7FFFFFFEh
0x18001a9c8  mov     r9d, r8d
0x18001a9cb  mov     eax, r11d
0x18001a9ce  mov     r10, r14
0x18001a9d1  mov     edx, 2
0x18001a9d6  test    rax, rax
0x18001a9d9  jz      short loc_18001A9F7
0x18001a9db  movzx   ecx, word ptr [r15]
0x18001a9df  test    cx, cx
0x18001a9e2  jz      short loc_18001A9F7
0x18001a9e4  mov     [r10], cx
0x18001a9e8  add     r15, rdx
0x18001a9eb  add     r10, rdx
0x18001a9ee  dec     rax
0x18001a9f1  sub     r9, 1
0x18001a9f5  jnz     short loc_18001A9D6
0x18001a9f7  lea     rcx, [r10-2]
0x18001a9fb  mov     rax, r9
0x18001a9fe  neg     rax
0x18001aa01  mov     r15d, 8007007Ah
0x18001aa07  sbb     edx, edx
0x18001aa09  not     edx
0x18001aa0b  and     edx, r15d
0x18001aa0e  test    r9, r9
0x18001aa11  cmovnz  rcx, r10
0x18001aa15  xor     r10d, r10d
0x18001aa18  mov     [rcx], r10w
0x18001aa1c  test    r9, r9
0x18001aa1f  jz      loc_18001ACDA
0x18001aa25  mov     rcx, r8
0x18001aa28  lea     r9d, [r10+2]
0x18001aa2c  mov     rax, r14
0x18001aa2f  cmp     [rax], r10w
0x18001aa33  jz      short loc_18001AA3E
0x18001aa35  add     rax, r9
0x18001aa38  sub     rcx, 1
0x18001aa3c  jnz     short loc_18001AA2F
0x18001aa3e  mov     rax, rcx
0x18001aa41  neg     rax
0x18001aa44  sbb     edi, edi
0x18001aa46  not     edi
0x18001aa48  and     edi, 80070057h
0x18001aa4e  test    rcx, rcx
0x18001aa51  jz      loc_18001AC2D
0x18001aa57  mov     rax, r8
0x18001aa5a  sub     rax, rcx
0x18001aa5d  test    rcx, rcx
0x18001aa60  jz      loc_18001AAE8
0x18001aa66  lea     rcx, aA_8; ".A"
0x18001aa6d  lea     rdx, [r14+rax*2]
0x18001aa71  sub     r8, rax
0x18001aa74  jz      short loc_18001AA95
0x18001aa76  test    r11, r11
0x18001aa79  jz      short loc_18001AA95
0x18001aa7b  movzx   eax, word ptr [rcx]
0x18001aa7e  test    ax, ax
0x18001aa81  jz      short loc_18001AA95
0x18001aa83  mov     [rdx], ax
0x18001aa86  add     rcx, r9
0x18001aa89  add     rdx, r9
0x18001aa8c  dec     r11
0x18001aa8f  sub     r8, 1
0x18001aa93  jnz     short loc_18001AA76
0x18001aa95  mov     rax, r8
0x18001aa98  lea     rcx, [rdx-2]
0x18001aa9c  neg     rax
0x18001aa9f  sbb     edi, edi
0x18001aaa1  not     edi
0x18001aaa3  and     edi, r15d
0x18001aaa6  test    r8, r8
0x18001aaa9  cmovnz  rcx, rdx
0x18001aaad  mov     [rcx], r10w
0x18001aab1  jz      short loc_18001AAE8
0x18001aab3  mov     r15, [rbp+arg_10]
0x18001aab7  lea     rax, [rbp+lpString2]
0x18001aabb  mov     qword ptr [rsp+70h+options], rax; unsigned __int16 **
0x18001aac0  lea     r9, Default; unsigned __int16 *
0x18001aac7  mov     r8, r15; unsigned __int16 *
0x18001aaca  mov     dword ptr [rsp+70h+lParam], r10d; char
0x18001aacf  mov     rdx, r14; unsigned __int16 *
0x18001aad2  mov     [rbp+lpString2], r10
0x18001aad6  mov     rcx, r13; this
0x18001aad9  call    ?GetString@CCachedINIFile@@QEAAJPEBG00KPEAPEAG@Z; CCachedINIFile::GetString(ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18001aade  mov     edi, eax
0x18001aae0  test    eax, eax
0x18001aae2  jns     loc_18001AC35
0x18001aae8  mov     rcx, r14; hMem
0x18001aaeb  call    cs:__imp_LocalFree
0x18001aaf2  nop     dword ptr [rax+rax+00h]
0x18001aaf7  xor     r10d, r10d
0x18001aafa  test    edi, edi
0x18001aafc  jns     loc_18001ACE1
0x18001ab02  test    [rbp+arg_20], 2
0x18001ab06  jnz     loc_18001ACFC
0x18001ab0c  mov     rax, [rbp+arg_28]
0x18001ab10  mov     [rax], rsi
0x18001ab13  mov     rsi, r10
0x18001ab16  jmp     short loc_18001AB2E
0x18001ab18  mov     rcx, rdi; pv
0x18001ab1b  call    cs:__imp_CoTaskMemFree
0x18001ab22  nop     dword ptr [rax+rax+00h]
0x18001ab27  xor     r10d, r10d
0x18001ab2a  test    ebx, ebx
0x18001ab2c  jns     short loc_18001AB0C
0x18001ab2e  mov     rcx, rsi; pv
0x18001ab31  call    cs:__imp_CoTaskMemFree
0x18001ab38  nop     dword ptr [rax+rax+00h]
0x18001ab3d  jmp     loc_18001A7DB
0x18001ab42  mov     rcx, [rdi+10h]; hdpa
0x18001ab46  movsxd  rdx, eax; i
0x18001ab49  call    cs:__imp_DPA_GetPtr
0x18001ab50  nop     dword ptr [rax+rax+00h]
0x18001ab55  cmp     [r13+428h], ebx
0x18001ab5c  jnz     loc_18001AC04
0x18001ab62  mov     r14, [rax+10h]
0x18001ab66  mov     rax, r12
0x18001ab69  inc     rax
  ... truncated ...
```
