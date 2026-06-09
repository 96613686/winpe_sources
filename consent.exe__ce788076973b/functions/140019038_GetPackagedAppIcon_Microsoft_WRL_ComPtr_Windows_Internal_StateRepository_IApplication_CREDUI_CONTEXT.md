# GetPackagedAppIcon(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplication>,_CREDUI_CONTEXT *)

- ea: `0x140019038`
- end: `0x140019331`
- name: `?GetPackagedAppIcon@@YAXV?$ComPtr@UIApplication@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEAU_CREDUI_CONTEXT@@@Z`
- size: `761`
- prototype: `HRESULT __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000eee4`

## callees

- `0x14000fbec`
- `0x140010ad3`
- `0x140019038`
- `0x140019634`
- `0x14001e050`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001932a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001932a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001908b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140019113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001917b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400192d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001908b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140019113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001917b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400192d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1400190b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1400190b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400191c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400191c5`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x1400191dc`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x1400191dc`
- `gdiplus!GdipCreateBitmapFromFile` at `0x140019249`
- `gdiplus!GdipCreateBitmapFromFile` at `0x140019249`
- `gdiplus!GdipCreateHICONFromBitmap` at `0x14001925f`
- `gdiplus!GdipCreateHICONFromBitmap` at `0x14001925f`
- `gdiplus!GdipAlloc` at `0x140019222`
- `gdiplus!GdipAlloc` at `0x140019222`
- `gdiplus!GdiplusStartup` at `0x140019210`
- `gdiplus!GdiplusStartup` at `0x140019210`

## pseudocode

```c
HRESULT __fastcall GetPackagedAppIcon(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING *); // rbx
  int v6; // ebx
  HRESULT v7; // eax
  bool v8; // al
  __int64 v9; // rdi
  int (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // ebx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  HRESULT v15; // eax
  int v16; // r8d
  char v17; // di
  __int64 v18; // rbx
  __int64 v19; // rcx
  int HICONFromBitmap; // eax
  HRESULT v21; // eax
  __int64 v22; // rcx
  bool v23[8]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string1; // [rsp+38h] [rbp-C8h] BYREF
  INT32 result[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v26; // [rsp+48h] [rbp-B8h] BYREF
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+60h] [rbp-A0h]
  WCHAR pszOutBuf[264]; // [rsp+70h] [rbp-90h] BYREF

  v26 = a1;
  string1 = 0;
  v23[0] = 0;
  v4 = *a1;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a1 + 688LL);
  WindowsDeleteString(0);
  string1 = 0;
  v6 = v5(v4, &string1);
  result[0] = 0;
  v7 = WindowsCompareStringOrdinal(string1, 0, result);
  if ( v7 < 0 )
  {
    RaiseException(v7, 1u, 0, 0);
    JUMPOUT(0x140019330LL);
  }
  v8 = result[0] != 0;
  v23[0] = result[0] != 0;
  if ( v6 >= 0 && result[0] )
  {
LABEL_8:
    if ( v8 )
      goto LABEL_13;
    goto LABEL_9;
  }
  if ( (*(int (__fastcall **)(_QWORD, bool *))(*(_QWORD *)*a1 + 256LL))(*a1, v23) >= 0 && v23[0] )
  {
    v9 = *a1;
    v10 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a1 + 656LL);
    WindowsDeleteString(string1);
    string1 = 0;
    if ( v10(v9, &string1) >= 0 )
    {
      v8 = v23[0];
      goto LABEL_8;
    }
  }
LABEL_9:
  v11 = (*(__int64 (__fastcall **)(_QWORD, bool *))(*(_QWORD *)*a1 + 296LL))(*a1, v23);
  if ( v11 < 0
    || !v23[0]
    || (v12 = *a1,
        v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a1 + 752LL),
        WindowsDeleteString(string1),
        string1 = 0,
        v11 = v13(v12, &string1),
        v11 < 0)
    || !v23[0] )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_D(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        21,
        WPP_bed9811735e730a365d52877ff824444_Traceguids,
        (unsigned int)v11);
    goto LABEL_24;
  }
LABEL_13:
  memset_0(pszOutBuf, 0, 0x208u);
  StringRawBuffer = WindowsGetStringRawBuffer(string1, 0);
  v15 = SHLoadIndirectString(StringRawBuffer, pszOutBuf, 0x104u, 0);
  v17 = v15;
  if ( v15 >= 0 )
  {
    v27 = 1;
    v28 = 0;
    v29 = 0;
    v26 = 0;
    v17 = 5;
    if ( !(unsigned int)GdiplusStartup(&v26, &v27, 0) )
    {
      v18 = GdipAlloc(24);
      if ( v18 )
      {
        *(_QWORD *)v18 = &Gdiplus::Image::`vftable';
        *(_QWORD *)result = 0;
        *(_DWORD *)(v18 + 16) = GdipCreateBitmapFromFile(pszOutBuf, result);
        v19 = *(_QWORD *)result;
        *(_QWORD *)(v18 + 8) = *(_QWORD *)result;
        HICONFromBitmap = GdipCreateHICONFromBitmap(v19, a2 + 8);
        if ( !HICONFromBitmap )
          goto LABEL_24;
        *(_DWORD *)(v18 + 16) = HICONFromBitmap;
      }
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_SD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, v16, (unsigned int)pszOutBuf, v17);
LABEL_24:
  v21 = WindowsDeleteString(string1);
  string1 = 0;
  v22 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return v21;
}

```

## disassembly

```asm
0x140019038  mov     [rsp-8+arg_10], rbx
0x14001903d  push    rbp
0x14001903e  push    rsi
0x14001903f  push    rdi
0x140019040  push    r14
0x140019042  push    r15
0x140019044  lea     rbp, [rsp-190h]
0x14001904c  sub     rsp, 290h
0x140019053  mov     rax, cs:__security_cookie
0x14001905a  xor     rax, rsp
0x14001905d  mov     [rbp+1B0h+var_30], rax
0x140019064  mov     r14, rdx
0x140019067  mov     rsi, rcx
0x14001906a  mov     [rsp+2B0h+var_268], rcx
0x14001906f  xor     r15d, r15d
0x140019072  mov     [rsp+2B0h+string1], r15
0x140019077  mov     [rsp+2B0h+var_280], r15b
0x14001907c  mov     rdi, [rcx]
0x14001907f  mov     rax, [rdi]
0x140019082  mov     rbx, [rax+2B0h]
0x140019089  xor     ecx, ecx; string
0x14001908b  call    cs:__imp_WindowsDeleteString
0x140019091  mov     [rsp+2B0h+string1], r15
0x140019096  lea     rdx, [rsp+2B0h+string1]
0x14001909b  mov     rcx, rdi
0x14001909e  mov     rax, rbx
0x1400190a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400190a6  mov     ebx, eax
0x1400190a8  mov     [rsp+2B0h+result], r15d
0x1400190ad  lea     r8, [rsp+2B0h+result]; result
0x1400190b2  xor     edx, edx; string2
0x1400190b4  mov     rcx, [rsp+2B0h+string1]; string1
0x1400190b9  call    cs:__imp_WindowsCompareStringOrdinal
0x1400190bf  test    eax, eax
0x1400190c1  js      loc_14001931E
0x1400190c7  mov     ecx, [rsp+2B0h+result]
0x1400190cb  test    ecx, ecx
0x1400190cd  setnz   al
0x1400190d0  mov     [rsp+2B0h+var_280], al
0x1400190d4  test    ebx, ebx
0x1400190d6  js      short loc_1400190DC
0x1400190d8  test    ecx, ecx
0x1400190da  jnz     short loc_140019138
0x1400190dc  mov     rcx, [rsi]
0x1400190df  mov     rax, [rcx]
0x1400190e2  lea     rdx, [rsp+2B0h+var_280]
0x1400190e7  mov     rax, [rax+100h]
0x1400190ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400190f3  mov     ebx, eax
0x1400190f5  test    eax, eax
0x1400190f7  js      short loc_14001913C
0x1400190f9  mov     al, [rsp+2B0h+var_280]
0x1400190fd  test    al, al
0x1400190ff  jz      short loc_14001913C
0x140019101  mov     rdi, [rsi]
0x140019104  mov     rax, [rdi]
0x140019107  mov     rbx, [rax+290h]
0x14001910e  mov     rcx, [rsp+2B0h+string1]; string
0x140019113  call    cs:__imp_WindowsDeleteString
0x140019119  mov     [rsp+2B0h+string1], r15
0x14001911e  lea     rdx, [rsp+2B0h+string1]
0x140019123  mov     rcx, rdi
0x140019126  mov     rax, rbx
0x140019129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001912e  mov     ebx, eax
0x140019130  test    eax, eax
0x140019132  js      short loc_14001913C
0x140019134  mov     al, [rsp+2B0h+var_280]
0x140019138  test    al, al
0x14001913a  jnz     short loc_1400191AC
0x14001913c  mov     rcx, [rsi]
0x14001913f  mov     rax, [rcx]
0x140019142  lea     rdx, [rsp+2B0h+var_280]
0x140019147  mov     rax, [rax+128h]
0x14001914e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019153  mov     ebx, eax
0x140019155  test    eax, eax
0x140019157  js      loc_14001929E
0x14001915d  mov     al, [rsp+2B0h+var_280]
0x140019161  test    al, al
0x140019163  jz      loc_14001929E
0x140019169  mov     rdi, [rsi]
0x14001916c  mov     rax, [rdi]
0x14001916f  mov     rbx, [rax+2F0h]
0x140019176  mov     rcx, [rsp+2B0h+string1]; string
0x14001917b  call    cs:__imp_WindowsDeleteString
0x140019181  mov     [rsp+2B0h+string1], r15
0x140019186  lea     rdx, [rsp+2B0h+string1]
0x14001918b  mov     rcx, rdi
0x14001918e  mov     rax, rbx
0x140019191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019196  mov     ebx, eax
0x140019198  test    eax, eax
0x14001919a  js      loc_14001929E
0x1400191a0  mov     al, [rsp+2B0h+var_280]
0x1400191a4  test    al, al
0x1400191a6  jz      loc_14001929E
0x1400191ac  xor     edx, edx; Val
0x1400191ae  mov     r8d, 208h; Size
0x1400191b4  lea     rcx, [rsp+2B0h+pszOutBuf]; void *
0x1400191b9  call    memset_0
0x1400191be  xor     edx, edx; length
0x1400191c0  mov     rcx, [rsp+2B0h+string1]; string
0x1400191c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1400191cb  mov     rcx, rax; pszSource
0x1400191ce  xor     r9d, r9d; ppvReserved
0x1400191d1  mov     r8d, 104h; cchOutBuf
0x1400191d7  lea     rdx, [rsp+2B0h+pszOutBuf]; pszOutBuf
0x1400191dc  call    cs:__imp_SHLoadIndirectString
0x1400191e2  mov     edi, eax
0x1400191e4  test    eax, eax
0x1400191e6  js      loc_14001926C
0x1400191ec  mov     [rsp+2B0h+var_260], 1
0x1400191f4  mov     [rsp+2B0h+var_258], r15
0x1400191f9  mov     [rsp+2B0h+var_250], r15
0x1400191fe  mov     [rsp+2B0h+var_268], r15
0x140019203  xor     r8d, r8d
0x140019206  lea     rdx, [rsp+2B0h+var_260]
0x14001920b  lea     rcx, [rsp+2B0h+var_268]
0x140019210  call    cs:__imp_GdiplusStartup
0x140019216  mov     edi, 80004005h
0x14001921b  test    eax, eax
0x14001921d  jnz     short loc_14001926C
0x14001921f  lea     ecx, [rax+18h]
0x140019222  call    cs:__imp_GdipAlloc
0x140019228  mov     rbx, rax
0x14001922b  test    rax, rax
0x14001922e  jz      short loc_14001926C
0x140019230  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x140019237  mov     [rbx], rax
0x14001923a  mov     qword ptr [rsp+2B0h+result], r15
0x14001923f  lea     rdx, [rsp+2B0h+result]
0x140019244  lea     rcx, [rsp+2B0h+pszOutBuf]
0x140019249  call    cs:__imp_GdipCreateBitmapFromFile
0x14001924f  mov     [rbx+10h], eax
0x140019252  mov     rcx, qword ptr [rsp+2B0h+result]
0x140019257  mov     [rbx+8], rcx
0x14001925b  lea     rdx, [r14+8]
0x14001925f  call    cs:__imp_GdipCreateHICONFromBitmap
0x140019265  test    eax, eax
0x140019267  jz      short loc_1400192D0
0x140019269  mov     [rbx+10h], eax
0x14001926c  lea     rax, WPP_GLOBAL_Control
0x140019273  mov     rcx, cs:WPP_GLOBAL_Control
0x14001927a  cmp     rcx, rax
0x14001927d  jz      short loc_1400192D0
0x14001927f  test    byte ptr [rcx+1Ch], 2
0x140019283  jz      short loc_1400192D0
0x140019285  mov     edx, 14h
0x14001928a  mov     [rsp+2B0h+var_290], edi
0x14001928e  lea     r9, [rsp+2B0h+pszOutBuf]
0x140019293  mov     rcx, [rcx+10h]
0x140019297  call    WPP_SF_SD
0x14001929c  jmp     short loc_1400192D0
0x14001929e  lea     rax, WPP_GLOBAL_Control
0x1400192a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400192ac  cmp     rcx, rax
0x1400192af  jz      short loc_1400192D0
0x1400192b1  test    byte ptr [rcx+1Ch], 2
0x1400192b5  jz      short loc_1400192D0
0x1400192b7  mov     edx, 15h
0x1400192bc  mov     r9d, ebx
0x1400192bf  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x1400192c6  mov     rcx, [rcx+10h]
0x1400192ca  call    WPP_SF_D
0x1400192cf  nop
0x1400192d0  mov     rcx, [rsp+2B0h+string1]; string
0x1400192d5  call    cs:__imp_WindowsDeleteString
0x1400192db  mov     [rsp+2B0h+string1], r15
0x1400192e0  mov     rcx, [rsi]
0x1400192e3  test    rcx, rcx
0x1400192e6  jz      short loc_1400192F8
0x1400192e8  mov     [rsi], r15
0x1400192eb  mov     rax, [rcx]
0x1400192ee  mov     rax, [rax+10h]
0x1400192f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400192f7  nop
0x1400192f8  mov     rcx, [rbp+1B0h+var_30]
0x1400192ff  xor     rcx, rsp; StackCookie
0x140019302  call    __security_check_cookie
0x140019307  mov     rbx, [rsp+2B0h+arg_10]
0x14001930f  add     rsp, 290h
0x140019316  pop     r15
0x140019318  pop     r14
0x14001931a  pop     rdi
0x14001931b  pop     rsi
0x14001931c  pop     rbp
0x14001931d  retn
0x14001931e  xor     r9d, r9d; lpArguments
0x140019321  xor     r8d, r8d; nNumberOfArguments
0x140019324  lea     edx, [r9+1]; dwExceptionFlags
0x140019328  mov     ecx, eax; dwExceptionCode
0x14001932a  call    cs:__imp_RaiseException
```
