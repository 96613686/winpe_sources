# CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)

- ea: `0x180171c98`
- end: `0x180171f33`
- name: `?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z`
- size: `667`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180172c90`

## callees

- `0x180008dc0`
- `0x1800d989c`
- `0x180171b6c`
- `0x180171c98`
- `0x18017282c`
- `0x180172ee8`
- `0x180172f9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180171ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180171eca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180171eeb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180171ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180171eca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180171eeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180171eb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180171ed9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180171efa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180171eb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180171ed9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180171efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180171d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180171d0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180171d05`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180171d05`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::AppendToSystemPath(char *Src, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // r15
  __int64 v5; // r14
  __int64 v6; // rsi
  signed int LastError; // eax
  unsigned int v8; // edi
  __int64 v9; // rdx
  WCHAR *v10; // rax
  __int64 v11; // rcx
  int Internal; // eax
  char *v13; // rbx
  int StringCch; // eax
  int v15; // eax
  int v16; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v18; // rax
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v22 = 0;
  v20 = 0;
  v21 = 0;
  v23 = 1;
  v24 = *(_DWORD *)L"\\";
  v4 = 0;
  v5 = 0;
  v6 = 0;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
LABEL_6:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_35;
  }
  v9 = 260;
  v10 = Buffer;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v8 = v9 == 0 ? 0x80070057 : 0;
  v11 = (260 - v9) & -(__int64)(v9 != 0);
  if ( !v9 )
    goto LABEL_6;
  if ( Buffer[v11 - 1] == 92 || Buffer[v11 - 1] == 47 )
    --v11;
  if ( v11 == (unsigned int)v11 )
  {
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v8 = 0;
  }
  else
  {
    v8 = -2147024362;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (v8 & 0x80000000) == 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer);
    v8 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    v5 = v20;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_6;
  v13 = Src + 2;
  if ( *(_WORD *)Src != 92 )
    v13 = Src;
  LODWORD(v20) = 0;
  if ( v13
    && (StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v13, &v20),
        v8 = StringCch,
        StringCch < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  else
  {
    v15 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v13);
    v8 = v15;
    if ( v15 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v15);
    v6 = v21;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_6;
  v16 = STRAPI_MultiCat(&v22, 3u, v5, &v24, v6);
  v8 = v16;
  if ( v16 >= 0 )
  {
    *a2 = v22;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
    v4 = v22;
  }
LABEL_35:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v4 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v8;
}

```

## disassembly

```asm
0x180171c98  mov     [rsp-8+arg_10], rbx
0x180171c9d  push    rbp
0x180171c9e  push    rsi
0x180171c9f  push    rdi
0x180171ca0  push    r12
0x180171ca2  push    r13
0x180171ca4  push    r14
0x180171ca6  push    r15
0x180171ca8  lea     rbp, [rsp-170h]
0x180171cb0  sub     rsp, 270h
0x180171cb7  mov     rax, cs:__security_cookie
0x180171cbe  xor     rax, rsp
0x180171cc1  mov     [rbp+1A0h+var_40], rax
0x180171cc8  mov     eax, dword ptr cs:Source; "\\"
0x180171cce  xor     edi, edi
0x180171cd0  mov     r12, rdx
0x180171cd3  mov     [rsp+2A0h+var_260], rdi
0x180171cd8  mov     r13, rcx
0x180171cdb  mov     [rsp+2A0h+var_270], rdi
0x180171ce0  mov     ebx, 104h
0x180171ce5  mov     [rsp+2A0h+var_268], rdi
0x180171cea  mov     edx, ebx; uSize
0x180171cec  mov     [rsp+2A0h+var_258], 1
0x180171cf4  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180171cf9  mov     [rsp+2A0h+var_254], eax
0x180171cfd  mov     r15d, edi
0x180171d00  mov     r14d, edi
0x180171d03  mov     esi, edi
0x180171d05  call    cs:__imp_GetSystemDirectoryW
0x180171d0b  test    eax, eax
0x180171d0d  jnz     short loc_180171D39
0x180171d0f  call    cs:__imp_GetLastError
0x180171d15  mov     edi, eax
0x180171d17  test    eax, eax
0x180171d19  jnz     short loc_180171D22
0x180171d1b  mov     edi, 80004005h
0x180171d20  jmp     short loc_180171D2D
0x180171d22  jle     short loc_180171D2D
0x180171d24  movzx   edi, ax
0x180171d27  or      edi, 80070000h
0x180171d2d  mov     ecx, edi
0x180171d2f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180171d34  jmp     loc_180171E9D
0x180171d39  mov     rdx, rbx
0x180171d3c  lea     rax, [rsp+2A0h+Buffer]
0x180171d41  cmp     [rax], di
0x180171d44  jz      short loc_180171D50
0x180171d46  add     rax, 2
0x180171d4a  sub     rdx, 1
0x180171d4e  jnz     short loc_180171D41
0x180171d50  mov     rax, rdx
0x180171d53  neg     rax
0x180171d56  mov     rax, rdx
0x180171d59  sbb     edi, edi
0x180171d5b  sub     rbx, rdx
0x180171d5e  not     edi
0x180171d60  and     edi, 80070057h
0x180171d66  neg     rax
0x180171d69  sbb     rcx, rcx
0x180171d6c  and     rcx, rbx
0x180171d6f  test    rdx, rdx
0x180171d72  jz      short loc_180171D2D
0x180171d74  mov     eax, 5Ch ; '\'
0x180171d79  cmp     ax, word ptr [rsp+rcx*2+2A0h+var_254+2]
0x180171d7e  jz      short loc_180171D8C
0x180171d80  mov     eax, 2Fh ; '/'
0x180171d85  cmp     ax, word ptr [rsp+rcx*2+2A0h+var_254+2]
0x180171d8a  jnz     short loc_180171D8F
0x180171d8c  dec     rcx
0x180171d8f  mov     ebx, ecx
0x180171d91  cmp     rcx, rbx
0x180171d94  jz      short loc_180171DA6
0x180171d96  mov     edi, 80070216h
0x180171d9b  xor     ebx, ebx
0x180171d9d  mov     ecx, edi
0x180171d9f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180171da4  jmp     short loc_180171DAF
0x180171da6  xor     ecx, ecx
0x180171da8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180171dad  xor     edi, edi
0x180171daf  mov     ecx, edi
0x180171db1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180171db6  test    edi, edi
0x180171db8  jns     short loc_180171DC3
0x180171dba  mov     ecx, edi
0x180171dbc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180171dc1  jmp     short loc_180171DE6
0x180171dc3  lea     r8, [rsp+2A0h+var_270]
0x180171dc8  mov     edx, ebx
0x180171dca  lea     rcx, [rsp+2A0h+Buffer]; Src
0x180171dcf  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180171dd4  mov     edi, eax
0x180171dd6  test    eax, eax
0x180171dd8  jns     short loc_180171DE1
0x180171dda  mov     ecx, eax
0x180171ddc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180171de1  mov     r14, [rsp+2A0h+var_270]
0x180171de6  mov     ecx, edi
0x180171de8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180171ded  test    edi, edi
0x180171def  js      loc_180171D2D
0x180171df5  lea     rbx, [r13+2]
0x180171df9  mov     eax, 5Ch ; '\'
0x180171dfe  cmp     ax, [r13+0]
0x180171e03  cmovnz  rbx, r13
0x180171e07  xor     r13d, r13d
0x180171e0a  mov     edx, r13d
0x180171e0d  mov     dword ptr [rsp+2A0h+var_270], edx
0x180171e11  test    rbx, rbx
0x180171e14  jz      short loc_180171E36
0x180171e16  lea     rdx, [rsp+2A0h+var_270]
0x180171e1b  mov     rcx, rbx
0x180171e1e  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180171e23  mov     edi, eax
0x180171e25  test    eax, eax
0x180171e27  jns     short loc_180171E32
0x180171e29  mov     ecx, eax
0x180171e2b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180171e30  jmp     short loc_180171E55
0x180171e32  mov     edx, dword ptr [rsp+2A0h+var_270]
0x180171e36  lea     r8, [rsp+2A0h+var_268]
0x180171e3b  mov     rcx, rbx; Src
0x180171e3e  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180171e43  mov     edi, eax
0x180171e45  test    eax, eax
0x180171e47  jns     short loc_180171E50
0x180171e49  mov     ecx, eax
0x180171e4b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180171e50  mov     rsi, [rsp+2A0h+var_268]
0x180171e55  mov     ecx, edi
0x180171e57  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180171e5c  test    edi, edi
0x180171e5e  js      loc_180171D2D
0x180171e64  lea     r9, [rsp+2A0h+var_254]
0x180171e69  mov     [rsp+2A0h+var_280], rsi
0x180171e6e  mov     r8, r14
0x180171e71  lea     rcx, [rsp+2A0h+var_260]; unsigned __int16 **
0x180171e76  mov     edx, 3; unsigned int
0x180171e7b  call    ?STRAPI_MultiCat@@YAJPEAPEAGKZZ; STRAPI_MultiCat(ushort * *,ulong,...)
0x180171e80  mov     edi, eax
0x180171e82  test    eax, eax
0x180171e84  jns     short loc_180171E94
0x180171e86  mov     ecx, eax
0x180171e88  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180171e8d  mov     r15, [rsp+2A0h+var_260]
0x180171e92  jmp     short loc_180171E9D
0x180171e94  mov     rax, [rsp+2A0h+var_260]
0x180171e99  mov     [r12], rax
0x180171e9d  mov     ecx, edi
0x180171e9f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180171ea4  test    rsi, rsi
0x180171ea7  jz      short loc_180171EC5
0x180171ea9  call    cs:__imp_GetProcessHeap
0x180171eaf  lea     r8, [rsi-4]; lpMem
0x180171eb3  xor     edx, edx; dwFlags
0x180171eb5  mov     rcx, rax; hHeap
0x180171eb8  call    cs:__imp_HeapFree
0x180171ebe  xor     ecx, ecx
0x180171ec0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180171ec5  test    r14, r14
0x180171ec8  jz      short loc_180171EE6
0x180171eca  call    cs:__imp_GetProcessHeap
0x180171ed0  lea     r8, [r14-4]; lpMem
0x180171ed4  xor     edx, edx; dwFlags
0x180171ed6  mov     rcx, rax; hHeap
0x180171ed9  call    cs:__imp_HeapFree
0x180171edf  xor     ecx, ecx
0x180171ee1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180171ee6  test    r15, r15
0x180171ee9  jz      short loc_180171F07
0x180171eeb  call    cs:__imp_GetProcessHeap
0x180171ef1  lea     r8, [r15-4]; lpMem
0x180171ef5  xor     edx, edx; dwFlags
0x180171ef7  mov     rcx, rax; hHeap
0x180171efa  call    cs:__imp_HeapFree
0x180171f00  xor     ecx, ecx
0x180171f02  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180171f07  mov     eax, edi
0x180171f09  mov     rcx, [rbp+1A0h+var_40]
0x180171f10  xor     rcx, rsp; StackCookie
0x180171f13  call    __security_check_cookie
0x180171f18  mov     rbx, [rsp+2A0h+arg_10]
0x180171f20  add     rsp, 270h
0x180171f27  pop     r15
0x180171f29  pop     r14
0x180171f2b  pop     r13
0x180171f2d  pop     r12
0x180171f2f  pop     rdi
0x180171f30  pop     rsi
0x180171f31  pop     rbp
0x180171f32  retn
```
