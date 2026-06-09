# BuildSiufLocPath(ushort const *,ushort const *,ushort *,uint)

- ea: `0x1400103f8`
- end: `0x14001062f`
- name: `?BuildSiufLocPath@@YAJPEBG0PEAGI@Z`
- size: `567`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140010c40`

## callees

- `0x140001418`
- `0x14000b904`
- `0x1400103f8`
- `0x14001522c`
- `0x1400195e2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400105f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400105f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010607`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010607`

## string_xrefs

- `0x1400104be`: `GetSiufLocPath failed.`
- `0x140010492`: `BuildSiufLocPath`
- `0x140010576`: `BuildSiufLocPath`
- `0x1400105a2`: `StringCchPrintfW failed to build loc file path string.`

## pseudocode

```c
__int64 __fastcall BuildSiufLocPath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  int SiufLocPath; // ebx
  int v8; // r9d
  int v9; // r8d
  int v10; // ecx
  char *v11; // rdx
  __int64 *v12; // rax
  HANDLE ProcessHeap; // rax
  const char **v15; // [rsp+30h] [rbp-50h]
  const char **v16; // [rsp+38h] [rbp-48h]
  __int64 *v17; // [rsp+48h] [rbp-38h]
  LPVOID lpMem; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-28h] BYREF
  const char *v20; // [rsp+60h] [rbp-20h] BYREF
  const char *v21; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v22[2]; // [rsp+70h] [rbp-10h] BYREF
  int v23; // [rsp+A0h] [rbp+20h] BYREF
  int v24; // [rsp+B8h] [rbp+38h] BYREF

  v24 = a4;
  lpMem = 0;
  if ( !a1 || !a2 || !a3 )
    return (unsigned int)-2147467261;
  SiufLocPath = GetSiufLocPath((unsigned __int16 **)&lpMem);
  if ( SiufLocPath >= 0 )
  {
    memset_0(a3, 0, 0x208u);
    SiufLocPath = StringCchPrintfW(a3, 0x104u, L"%s\\%s-%s", lpMem, a2, a1);
    if ( SiufLocPath < 0 && (unsigned int)dword_140028000 > 2 )
    {
      v10 = qword_140028018;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v22[0] = 0x1000000;
        v21 = "BuildSiufLocPath";
        v11 = byte_140022F8D;
        v24 = 404;
        v20 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
        v19 = (__int64)"StringCchPrintfW failed to build loc file path string.";
        v17 = v22;
        v16 = &v21;
        v15 = &v20;
        v12 = &v19;
        goto LABEL_15;
      }
    }
  }
  else if ( (unsigned int)dword_140028000 > 2 )
  {
    v9 = qword_140028018;
    v10 = qword_140028010;
    if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
    {
      v19 = 0x1000000;
      v20 = "BuildSiufLocPath";
      v11 = &byte_140022DB7;
      v24 = 387;
      v21 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
      v22[0] = "GetSiufLocPath failed.";
      v17 = &v19;
      v16 = &v20;
      v15 = &v21;
      v12 = v22;
LABEL_15:
      v23 = SiufLocPath;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v10,
        (_DWORD)v11,
        v9,
        v8,
        (__int64)v12,
        (__int64)&v23,
        (__int64)v15,
        (__int64)v16,
        (__int64)&v24,
        (__int64)v17);
    }
  }
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  return (unsigned int)SiufLocPath;
}

```

## disassembly

```asm
0x1400103f8  mov     [rsp-18h+arg_8], rbx
0x1400103fd  mov     [rsp-18h+arg_10], rsi
0x140010402  mov     [rsp-18h+arg_18], r9d
0x140010407  push    rbp
0x140010408  push    r14
0x14001040a  push    r15
0x14001040c  mov     rbp, rsp
0x14001040f  sub     rsp, 80h
0x140010416  mov     [rbp+lpMem], 0
0x14001041e  mov     rsi, r8
0x140010421  mov     r14, rdx
0x140010424  mov     r15, rcx
0x140010427  test    rcx, rcx
0x14001042a  jnz     short loc_140010436
0x14001042c  mov     ebx, 80004003h
0x140010431  jmp     loc_140010613
0x140010436  test    r14, r14
0x140010439  jz      short loc_14001042C
0x14001043b  test    rsi, rsi
0x14001043e  jz      short loc_14001042C
0x140010440  lea     rcx, [rbp+lpMem]; unsigned __int16 **
0x140010444  call    ?GetSiufLocPath@@YAJPEAPEAG@Z; GetSiufLocPath(ushort * *)
0x140010449  mov     ebx, eax
0x14001044b  test    eax, eax
0x14001044d  jns     loc_1400104FF
0x140010453  mov     ecx, cs:dword_140028000
0x140010459  cmp     ecx, 2
0x14001045c  jbe     loc_1400105EB
0x140010462  mov     r8, cs:qword_140028018
0x140010469  mov     rdx, 400000000000h
0x140010473  mov     rcx, cs:qword_140028010
0x14001047a  test    rdx, rcx
0x14001047d  jz      loc_1400105EB
0x140010483  mov     rax, r8
0x140010486  and     rax, rdx
0x140010489  cmp     rax, r8
0x14001048c  jnz     loc_1400105EB
0x140010492  lea     rax, aBuildsiuflocpa; "BuildSiufLocPath"
0x140010499  mov     [rbp+var_28], 1000000h
0x1400104a1  mov     [rbp+var_20], rax
0x1400104a5  lea     rdx, byte_140022DB7
0x1400104ac  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400104b3  mov     [rbp+arg_18], 183h
0x1400104ba  mov     [rbp+var_18], rax
0x1400104be  lea     rax, aGetsiuflocpath; "GetSiufLocPath failed."
0x1400104c5  mov     [rbp+var_10], rax
0x1400104c9  lea     rax, [rbp+var_28]
0x1400104cd  mov     [rsp+80h+var_38], rax
0x1400104d2  lea     rax, [rbp+arg_18]
0x1400104d6  mov     [rsp+80h+var_40], rax
0x1400104db  lea     rax, [rbp+var_20]
0x1400104df  mov     [rsp+80h+var_48], rax
0x1400104e4  lea     rax, [rbp+var_18]
0x1400104e8  mov     [rsp+80h+var_50], rax
0x1400104ed  lea     rax, [rbp+arg_0]
0x1400104f1  mov     [rsp+80h+var_58], rax
0x1400104f6  lea     rax, [rbp+var_10]
0x1400104fa  jmp     loc_1400105DE
0x1400104ff  xor     edx, edx; Val
0x140010501  mov     r8d, 208h; Size
0x140010507  mov     rcx, rsi; void *
0x14001050a  call    memset_0
0x14001050f  mov     r9, [rbp+lpMem]
0x140010513  lea     r8, aSSS; "%s\\%s-%s"
0x14001051a  mov     edx, 104h; unsigned __int64
0x14001051f  mov     [rsp+80h+var_58], r15
0x140010524  mov     rcx, rsi; unsigned __int16 *
0x140010527  mov     [rsp+80h+var_60], r14
0x14001052c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140010531  mov     ebx, eax
0x140010533  test    eax, eax
0x140010535  jns     loc_1400105EB
0x14001053b  mov     eax, cs:dword_140028000
0x140010541  cmp     eax, 2
0x140010544  jbe     loc_1400105EB
0x14001054a  mov     rcx, cs:qword_140028018
0x140010551  mov     rdx, 400000000000h
0x14001055b  mov     rax, cs:qword_140028010
0x140010562  test    rdx, rax
0x140010565  jz      loc_1400105EB
0x14001056b  mov     rax, rcx
0x14001056e  and     rax, rdx
0x140010571  cmp     rax, rcx
0x140010574  jnz     short loc_1400105EB
0x140010576  lea     rax, aBuildsiuflocpa; "BuildSiufLocPath"
0x14001057d  mov     [rbp+var_10], 1000000h
0x140010585  mov     [rbp+var_18], rax
0x140010589  lea     rdx, byte_140022F8D
0x140010590  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010597  mov     [rbp+arg_18], 194h
0x14001059e  mov     [rbp+var_20], rax
0x1400105a2  lea     rax, aStringcchprint; "StringCchPrintfW failed to build loc fi"...
0x1400105a9  mov     [rbp+var_28], rax
0x1400105ad  lea     rax, [rbp+var_10]
0x1400105b1  mov     [rsp+80h+var_38], rax
0x1400105b6  lea     rax, [rbp+arg_18]
0x1400105ba  mov     [rsp+80h+var_40], rax
0x1400105bf  lea     rax, [rbp+var_18]
0x1400105c3  mov     [rsp+80h+var_48], rax
0x1400105c8  lea     rax, [rbp+var_20]
0x1400105cc  mov     [rsp+80h+var_50], rax
0x1400105d1  lea     rax, [rbp+arg_0]
0x1400105d5  mov     [rsp+80h+var_58], rax
0x1400105da  lea     rax, [rbp+var_28]
0x1400105de  mov     [rsp+80h+var_60], rax
0x1400105e3  mov     [rbp+arg_0], ebx
0x1400105e6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400105eb  cmp     [rbp+lpMem], 0
0x1400105f0  jz      short loc_140010613
0x1400105f2  call    cs:__imp_GetProcessHeap
0x1400105f9  nop     dword ptr [rax+rax+00h]
0x1400105fe  mov     r8, [rbp+lpMem]; lpMem
0x140010602  xor     edx, edx; dwFlags
0x140010604  mov     rcx, rax; hHeap
0x140010607  call    cs:__imp_HeapFree
0x14001060e  nop     dword ptr [rax+rax+00h]
0x140010613  lea     r11, [rsp+80h+var_s0]
0x14001061b  mov     eax, ebx
0x14001061d  mov     rbx, [r11+28h]
0x140010621  mov     rsi, [r11+30h]
0x140010625  mov     rsp, r11
0x140010628  pop     r15
0x14001062a  pop     r14
0x14001062c  pop     rbp
0x14001062d  retn
```
