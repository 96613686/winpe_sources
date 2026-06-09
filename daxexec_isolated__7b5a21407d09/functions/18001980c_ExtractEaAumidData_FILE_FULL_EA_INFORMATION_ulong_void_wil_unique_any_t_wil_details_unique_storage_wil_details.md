# ExtractEaAumidData(_FILE_FULL_EA_INFORMATION *,ulong,void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,bool,bool &)

- ea: `0x18001980c`
- end: `0x180019b6e`
- name: `?ExtractEaAumidData@@YAJPEAU_FILE_FULL_EA_INFORMATION@@KPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@_NAEA_N@Z`
- size: `866`
- prototype: `int __fastcall(__int64, unsigned int, void *, const void **, char, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022bb0`

## callees

- `0x180004f70`
- `0x180005340`
- `0x1800059a8`
- `0x18000aef0`
- `0x18000b126`
- `0x18000ff04`
- `0x18000ff24`
- `0x18001980c`
- `0x18001cfec`
- `0x18001ee90`
- `0x180020950`
- `0x1800bec14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001988b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001988b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001986c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001986c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001990b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001990b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001987d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001998c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019a0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019a2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019a89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001987d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001998c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019a0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019a2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019a89`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001992f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001992f`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180019a5a`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180019a5a`

## string_xrefs

- `0x1800199cb`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180019a6e`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180019b1e`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180019b50`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
int __fastcall ExtractEaAumidData(__int64 a1, unsigned int a2, void *a3, const void **a4, char a5, bool *a6)
{
  __int64 v10; // r9
  __int64 v11; // rdx
  void *v12; // rsi
  unsigned int v13; // r15d
  DWORD LastError; // ebx
  unsigned int v15; // ebx
  unsigned __int8 *v16; // rbx
  HLOCAL v17; // rax
  void *v18; // rsi
  const char *v20; // r9
  int v21; // edi
  __int64 v22; // rax
  unsigned int v23; // r14d
  unsigned int v24; // r12d
  char *v25; // rax
  char *v26; // rsi
  int v27; // eax
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-50h]
  int bIgnoreCasea; // [rsp+20h] [rbp-50h]
  unsigned int v32; // [rsp+30h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-38h] BYREF
  HLOCAL v34; // [rsp+40h] [rbp-30h] BYREF
  bool *v35; // [rsp+48h] [rbp-28h]
  _BYTE FileInformation[24]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v35 = a6;
  *a6 = 0;
  if ( !a3 )
  {
    v10 = 3221225485LL;
    v11 = 1237;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v11,
             (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
             (const char *)v10,
             bIgnoreCase);
  }
  v12 = (void *)*a4;
  v13 = 0;
  v32 = 0;
  if ( v12 )
  {
    LastError = GetLastError();
    LocalFree(v12);
    SetLastError(LastError);
  }
  *a4 = 0;
  if ( a2 < 0xC )
  {
    v10 = 3221225507LL;
LABEL_23:
    v11 = 1243;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v11,
             (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
             (const char *)v10,
             bIgnoreCase);
  }
  if ( *(_BYTE *)(a1 + 5) != 40 || strncmp_0("MICROSOFT.WINDOWS.SPARSEGENERATION.AUMID", (const char *)(a1 + 8), 0x28u) )
  {
LABEL_22:
    v10 = 3221225485LL;
    goto LABEL_23;
  }
  if ( !*(_WORD *)(a1 + 6) )
    return 0;
  v15 = *(unsigned __int16 *)(a1 + 6) >> 1;
  if ( v15 <= 3 )
  {
    v10 = 3221227787LL;
    goto LABEL_23;
  }
  if ( CompareStringOrdinal((LPCWCH)(a1 + 49), 3, L"V1 ", 3, 0) != 2 )
  {
    v16 = 0;
    goto LABEL_26;
  }
  v17 = LocalAlloc(0x40u, 2LL * (v15 + 1));
  v18 = v17;
  if ( !v17 )
  {
    v10 = 3221225495LL;
    goto LABEL_23;
  }
  memcpy_0(v17, (const void *)(a1 + 49), *(unsigned __int16 *)(a1 + 6));
  hMem = 0;
  v34 = 0;
  if ( !(unsigned int)ParseAutoSparseEAData(
                        (const unsigned __int16 *)v18,
                        v15,
                        (unsigned __int8 **)&v34,
                        &v32,
                        (unsigned __int16 **)&hMem) )
  {
    if ( hMem )
      LocalFree(hMem);
    if ( v34 )
      LocalFree(v34);
    LocalFree(v18);
    goto LABEL_22;
  }
  v16 = (unsigned __int8 *)v34;
  *a4 = hMem;
  LocalFree(v18);
  v13 = v32;
LABEL_26:
  if ( !*a4 )
    return 0;
  if ( !a5 )
    goto LABEL_28;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( GetFileInformationByHandleEx(a3, MaximumFileInfoByHandleClass, FileInformation, 0x18u) )
  {
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)*a4 + v22) );
    v23 = 2 * v22;
    v24 = 2 * v22 + 24;
    v25 = (char *)operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
    v26 = v25;
    if ( v25 )
    {
      memset_0(v25, 0, v24);
      *(_QWORD *)v26 = *(_QWORD *)FileInformation;
      *(_OWORD *)(v26 + 8) = *(_OWORD *)&FileInformation[8];
      memcpy_0(v26 + 24, *a4, v23);
      v27 = VerifyEASignature((const unsigned __int8 *)v26, v24, v16, v13, v35);
      v21 = v27;
      if ( v27 >= 0 )
      {
        operator delete(v26, v28);
LABEL_28:
        if ( v16 )
          LocalFree(v16);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x504,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)(unsigned int)v27,
        bIgnoreCasea);
      operator delete(v26, v29);
    }
    else
    {
      v21 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F1,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)0x8007000ELL,
        bIgnoreCase);
    }
  }
  else
  {
    v21 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x4EA,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            v20);
  }
  if ( v16 )
    LocalFree(v16);
  return v21;
}

```

## disassembly

```asm
0x18001980c  mov     [rsp-38h+arg_8], rbx
0x180019811  push    rbp
0x180019812  push    rsi
0x180019813  push    rdi
0x180019814  push    r12
0x180019816  push    r13
0x180019818  push    r14
0x18001981a  push    r15
0x18001981c  mov     rbp, rsp
0x18001981f  sub     rsp, 70h
0x180019823  mov     rax, cs:__security_cookie
0x18001982a  xor     rax, rsp
0x18001982d  mov     [rbp+var_8], rax
0x180019831  mov     rax, [rbp+arg_28]
0x180019835  mov     r14, rcx
0x180019838  xor     ecx, ecx
0x18001983a  mov     [rbp+var_28], rax
0x18001983e  mov     rdi, r9
0x180019841  mov     r13, r8
0x180019844  mov     r12d, edx
0x180019847  mov     [rax], cl
0x180019849  test    r8, r8
0x18001984c  jnz     short loc_18001985E
0x18001984e  mov     r9d, 0C000000Dh
0x180019854  mov     edx, 4D5h
0x180019859  jmp     loc_1800199C7
0x18001985e  mov     rsi, [r9]
0x180019861  mov     r15d, ecx
0x180019864  mov     [rbp+var_40], ecx
0x180019867  test    rsi, rsi
0x18001986a  jz      short loc_180019897
0x18001986c  call    cs:__imp_GetLastError
0x180019873  nop     dword ptr [rax+rax+00h]
0x180019878  mov     rcx, rsi; hMem
0x18001987b  mov     ebx, eax
0x18001987d  call    cs:__imp_LocalFree
0x180019884  nop     dword ptr [rax+rax+00h]
0x180019889  mov     ecx, ebx; dwErrCode
0x18001988b  call    cs:__imp_SetLastError
0x180019892  nop     dword ptr [rax+rax+00h]
0x180019897  xor     esi, esi
0x180019899  mov     [rdi], rsi
0x18001989c  cmp     r12d, 0Ch
0x1800198a0  jnb     short loc_1800198AD
0x1800198a2  mov     r9d, 0C0000023h
0x1800198a8  jmp     loc_1800199C2
0x1800198ad  mov     r8d, 28h ; '('; MaxCount
0x1800198b3  cmp     [r14+5], r8b
0x1800198b7  jnz     loc_1800199BC
0x1800198bd  lea     rdx, [r14+8]; Str2
0x1800198c1  lea     rcx, Str1; "MICROSOFT.WINDOWS.SPARSEGENERATION.AUMI"...
0x1800198c8  call    strncmp_0
0x1800198cd  test    eax, eax
0x1800198cf  jnz     loc_1800199BC
0x1800198d5  cmp     [r14+6], si
0x1800198da  jbe     loc_180019A3B
0x1800198e0  movzx   ebx, word ptr [r14+6]
0x1800198e5  lea     edx, [rax+3]; cchCount1
0x1800198e8  shr     ebx, 1
0x1800198ea  cmp     ebx, edx
0x1800198ec  ja      short loc_1800198F9
0x1800198ee  mov     r9d, 0C000090Bh
0x1800198f4  jmp     loc_1800199C2
0x1800198f9  mov     r9d, edx; cchCount2
0x1800198fc  mov     [rsp+70h+bIgnoreCase], esi; bIgnoreCase
0x180019900  lea     r8, String2; "V1 "
0x180019907  lea     rcx, [r14+31h]; lpString1
0x18001990b  call    cs:__imp_CompareStringOrdinal
0x180019912  nop     dword ptr [rax+rax+00h]
0x180019917  cmp     eax, 2
0x18001991a  jz      short loc_180019924
0x18001991c  mov     rbx, rsi
0x18001991f  jmp     loc_180019A1C
0x180019924  lea     edx, [rbx+1]
0x180019927  mov     ecx, 40h ; '@'; uFlags
0x18001992c  add     rdx, rdx; uBytes
0x18001992f  call    cs:__imp_LocalAlloc
0x180019936  nop     dword ptr [rax+rax+00h]
0x18001993b  mov     rsi, rax
0x18001993e  test    rax, rax
0x180019941  jnz     short loc_18001994B
0x180019943  mov     r9d, 0C0000017h
0x180019949  jmp     short loc_1800199C2
0x18001994b  movzx   r8d, word ptr [r14+6]; Size
0x180019950  lea     rdx, [r14+31h]; Src
0x180019954  mov     rcx, rsi; void *
0x180019957  call    memcpy_0
0x18001995c  lea     rax, [rbp+hMem]
0x180019960  mov     [rbp+hMem], r15
0x180019964  lea     r9, [rbp+var_40]; unsigned int *
0x180019968  mov     qword ptr [rsp+70h+bIgnoreCase], rax; int
0x18001996d  lea     r8, [rbp+var_30]; unsigned __int8 **
0x180019971  mov     [rbp+var_30], r15
0x180019975  mov     edx, ebx; unsigned int
0x180019977  mov     rcx, rsi; unsigned __int16 *
0x18001997a  call    ?ParseAutoSparseEAData@@YAHPEBGIPEAPEAEPEAIPEAPEAG@Z; ParseAutoSparseEAData(ushort const *,uint,uchar * *,uint *,ushort * *)
0x18001997f  test    eax, eax
0x180019981  jnz     short loc_1800199FC
0x180019983  mov     rcx, [rbp+hMem]; hMem
0x180019987  test    rcx, rcx
0x18001998a  jz      short loc_180019998
0x18001998c  call    cs:__imp_LocalFree
0x180019993  nop     dword ptr [rax+rax+00h]
0x180019998  mov     rcx, [rbp+var_30]; hMem
0x18001999c  test    rcx, rcx
0x18001999f  jz      short loc_1800199AD
0x1800199a1  call    cs:__imp_LocalFree
0x1800199a8  nop     dword ptr [rax+rax+00h]
0x1800199ad  mov     rcx, rsi; hMem
0x1800199b0  call    cs:__imp_LocalFree
0x1800199b7  nop     dword ptr [rax+rax+00h]
0x1800199bc  mov     r9d, 0C000000Dh; char *
0x1800199c2  mov     edx, 4DBh; void *
0x1800199c7  mov     rcx, [rbp+38h]; this
0x1800199cb  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800199d2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800199d7  mov     rcx, [rbp+var_8]
0x1800199db  xor     rcx, rsp; StackCookie
0x1800199de  call    __security_check_cookie
0x1800199e3  mov     rbx, [rsp+70h+arg_8]
0x1800199eb  add     rsp, 70h
0x1800199ef  pop     r15
0x1800199f1  pop     r14
0x1800199f3  pop     r13
0x1800199f5  pop     r12
0x1800199f7  pop     rdi
0x1800199f8  pop     rsi
0x1800199f9  pop     rbp
0x1800199fa  retn
0x1800199fc  mov     rax, [rbp+hMem]
0x180019a00  mov     rcx, rsi; hMem
0x180019a03  mov     rbx, [rbp+var_30]
0x180019a07  mov     [rdi], rax
0x180019a0a  call    cs:__imp_LocalFree
0x180019a11  nop     dword ptr [rax+rax+00h]
0x180019a16  mov     r15d, [rbp+var_40]
0x180019a1a  xor     esi, esi
0x180019a1c  cmp     [rdi], rsi
0x180019a1f  jz      short loc_180019A3B
0x180019a21  cmp     [rbp+arg_20], sil
0x180019a25  jnz     short loc_180019A3F
0x180019a27  test    rbx, rbx
0x180019a2a  jz      short loc_180019A3B
0x180019a2c  mov     rcx, rbx; hMem
0x180019a2f  call    cs:__imp_LocalFree
0x180019a36  nop     dword ptr [rax+rax+00h]
0x180019a3b  xor     eax, eax
0x180019a3d  jmp     short loc_1800199D7
0x180019a3f  xor     eax, eax
0x180019a41  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180019a45  xorps   xmm0, xmm0
0x180019a48  mov     [rbp+var_10], rax
0x180019a4c  mov     rcx, r13; hFile
0x180019a4f  movups  [rbp+FileInformation], xmm0
0x180019a53  lea     r9d, [rax+18h]; dwBufferSize
0x180019a57  lea     edx, [rax+12h]; FileInformationClass
0x180019a5a  call    cs:__imp_GetFileInformationByHandleEx
0x180019a61  nop     dword ptr [rax+rax+00h]
0x180019a66  test    eax, eax
0x180019a68  jnz     short loc_180019A9C
0x180019a6a  mov     rcx, [rbp+38h]; this
0x180019a6e  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180019a75  mov     edx, 4EAh; void *
0x180019a7a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019a7f  mov     edi, eax
0x180019a81  test    rbx, rbx
0x180019a84  jz      short loc_180019A95
0x180019a86  mov     rcx, rbx; hMem
0x180019a89  call    cs:__imp_LocalFree
0x180019a90  nop     dword ptr [rax+rax+00h]
0x180019a95  mov     eax, edi
0x180019a97  jmp     loc_1800199D7
0x180019a9c  mov     rcx, [rdi]
0x180019a9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019aa3  inc     rax
0x180019aa6  cmp     [rcx+rax*2], si
0x180019aaa  jnz     short loc_180019AA3
0x180019aac  lea     r14d, [rax+rax]
0x180019ab0  lea     r12d, [r14+18h]
0x180019ab4  mov     ecx, r12d; unsigned __int64
0x180019ab7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019abe  mov     r13d, r12d
0x180019ac1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019ac6  mov     rsi, rax
0x180019ac9  test    rax, rax
0x180019acc  jz      short loc_180019B4C
0x180019ace  mov     r8d, r13d; Size
0x180019ad1  xor     edx, edx; Val
0x180019ad3  mov     rcx, rax; void *
0x180019ad6  call    memset_0
0x180019adb  mov     rcx, qword ptr [rbp+FileInformation]
0x180019adf  mov     [rsi], rcx
0x180019ae2  lea     rcx, [rsi+18h]; void *
0x180019ae6  movups  xmm0, [rbp+FileInformation+8]
0x180019aea  mov     r8d, r14d; Size
0x180019aed  movdqu  xmmword ptr [rsi+8], xmm0
0x180019af2  mov     rdx, [rdi]; Src
0x180019af5  call    memcpy_0
0x180019afa  mov     rax, [rbp+var_28]
0x180019afe  mov     r9d, r15d; unsigned int
0x180019b01  mov     r8, rbx; unsigned __int8 *
0x180019b04  mov     qword ptr [rsp+70h+bIgnoreCase], rax; int
0x180019b09  mov     edx, r12d; unsigned int
0x180019b0c  mov     rcx, rsi; unsigned __int8 *
0x180019b0f  call    ?VerifyEASignature@@YAJPEBEK0IAEA_N@Z; VerifyEASignature(uchar const *,ulong,uchar const *,uint,bool &)
0x180019b14  mov     edi, eax
0x180019b16  test    eax, eax
0x180019b18  jns     short loc_180019B3F
0x180019b1a  mov     rcx, [rbp+38h]; this
0x180019b1e  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180019b25  mov     r9d, eax; char *
0x180019b28  mov     edx, 504h; void *
0x180019b2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b32  mov     rcx, rsi; void *
0x180019b35  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019b3a  jmp     loc_180019A81
0x180019b3f  mov     rcx, rsi; void *
0x180019b42  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019b47  jmp     loc_180019A27
0x180019b4c  mov     rcx, [rbp+38h]; this
0x180019b50  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180019b57  mov     edi, 8007000Eh
0x180019b5c  mov     edx, 4F1h; void *
0x180019b61  mov     r9d, edi; char *
0x180019b64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b69  jmp     loc_180019A81
```
