# PAL_System_ThreadAlloc(uint (*)(void *),void *,ulong *,void * *)

- ea: `0x140109554`
- end: `0x140109764`
- name: `?PAL_System_ThreadAlloc@@YAJP6AIPEAX@Z0PEAKPEAPEAX@Z`
- size: `528`
- prototype: `__int64 __fastcall(unsigned int (*)(void *), void *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14010976c`

## callees

- `0x1400019e8`
- `0x140001b00`
- `0x1400b1d80`
- `0x140109554`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1401096ba`
- `KERNEL32!LocalFree` at `0x1401096ba`
- `KERNEL32!CreateThread` at `0x14010968d`
- `KERNEL32!CreateThread` at `0x14010968d`
- `KERNEL32!FreeLibrary` at `0x1401096a4`
- `KERNEL32!FreeLibrary` at `0x1401096a4`
- `KERNEL32!GetLastError` at `0x1401095ee`
- `KERNEL32!GetLastError` at `0x1401095ee`
- `KERNEL32!GetModuleHandleExW` at `0x1401095cc`
- `KERNEL32!GetModuleHandleExW` at `0x1401095cc`

## string_xrefs

- `0x140109610`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x1401096f5`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x140109605`: `PAL_System_ThreadAlloc`
- `0x1401096dc`: `PAL_System_ThreadAlloc`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadAlloc(unsigned int (*a1)(void *), void *a2, unsigned int *a3, void **a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  unsigned int v9; // ebx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  HANDLE v13; // rcx
  DWORD LastError; // [rsp+50h] [rbp-30h] BYREF
  int v16; // [rsp+54h] [rbp-2Ch] BYREF
  int v17; // [rsp+58h] [rbp-28h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-20h] BYREF
  const char *v19; // [rsp+68h] [rbp-18h] BYREF
  const char *v20; // [rsp+70h] [rbp-10h] BYREF
  const char *v21; // [rsp+78h] [rbp-8h] BYREF
  DWORD ThreadId; // [rsp+A0h] [rbp+20h] BYREF
  int v23; // [rsp+A4h] [rbp+24h]

  v23 = HIDWORD(a1);
  ThreadId = 0;
  phModule = 0;
  if ( a3 )
  {
    v7 = MIDL_user_allocate(0x18u);
    v8 = v7;
    if ( v7 )
    {
      v7[1] = a2;
      *v7 = CTSThread::TSStaticThreadEntry;
      if ( GetModuleHandleExW(4u, &g_TsSystemPalDllModule, &phModule) )
      {
        v8[2] = phModule;
        v13 = CreateThread(0, 0, PAL_System_Win32_ThreadProcWrapper, v8, 0, &ThreadId);
        if ( v13 )
        {
          *a3 = ThreadId;
          v9 = 0;
          *a4 = v13;
          return v9;
        }
        if ( phModule )
        {
          FreeLibrary(phModule);
          phModule = 0;
        }
        v9 = -2147467259;
      }
      else
      {
        v9 = -2147467259;
        if ( (unsigned int)dword_140150118 > 2 )
        {
          v16 = 1295;
          LastError = GetLastError();
          v19 = "PAL_System_ThreadAlloc";
          v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
          v21 = "Failed GetModuleHandleEx.  GetLastError: 0x%x";
          v17 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)byte_1401440D5,
            v11,
            v12,
            (__int64)&v21,
            (__int64)&v17,
            (__int64)&v20,
            (__int64)&v16,
            (__int64)&v19,
            (__int64)&LastError);
        }
      }
      LocalFree(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    if ( (unsigned int)dword_140150118 > 2 )
    {
      v17 = 1268;
      v21 = "PAL_System_ThreadAlloc";
      v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v19 = "NULL parameter passed";
      v16 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)qword_1401444A8,
        0,
        (_DWORD)a4,
        (__int64)&v19,
        (__int64)&v16,
        (__int64)&v20,
        (__int64)&v17,
        (__int64)&v21);
    }
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x140109554  mov     [rsp-18h+arg_8], rbx
0x140109559  mov     [rsp-18h+arg_10], rsi
0x14010955e  mov     qword ptr [rsp-18h+ThreadId], rcx
0x140109563  push    rbp
0x140109564  push    rdi
0x140109565  push    r14
0x140109567  mov     rbp, rsp
0x14010956a  sub     rsp, 80h
0x140109571  mov     [rbp+ThreadId], 0
0x140109578  mov     rsi, r9
0x14010957b  mov     [rbp+phModule], 0
0x140109583  mov     rbx, r8
0x140109586  mov     r14, rdx
0x140109589  test    r8, r8
0x14010958c  jz      loc_1401096D1
0x140109592  mov     ecx, 18h; size
0x140109597  call    MIDL_user_allocate
0x14010959c  mov     rdi, rax
0x14010959f  test    rax, rax
0x1401095a2  jnz     short loc_1401095AE
0x1401095a4  mov     ebx, 8007000Eh
0x1401095a9  jmp     loc_14010974A
0x1401095ae  mov     [rax+8], r14
0x1401095b2  lea     r8, [rbp+phModule]; phModule
0x1401095b6  lea     rax, ?TSStaticThreadEntry@CTSThread@@CAIPEAX@Z; CTSThread::TSStaticThreadEntry(void *)
0x1401095bd  mov     ecx, 4; dwFlags
0x1401095c2  lea     rdx, ?g_TsSystemPalDllModule@@3HA; lpModuleName
0x1401095c9  mov     [rdi], rax
0x1401095cc  call    cs:__imp_GetModuleHandleExW
0x1401095d2  test    eax, eax
0x1401095d4  jnz     loc_140109666
0x1401095da  mov     eax, cs:dword_140150118
0x1401095e0  mov     ebx, 80004005h
0x1401095e5  cmp     eax, 2
0x1401095e8  jbe     loc_1401096B7
0x1401095ee  call    cs:__imp_GetLastError
0x1401095f4  lea     rdx, byte_1401440D5
0x1401095fb  mov     [rbp+var_2C], 50Fh
0x140109602  mov     [rbp+var_30], eax
0x140109605  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x14010960c  mov     [rbp+var_18], rax
0x140109610  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140109617  mov     [rbp+var_10], rax
0x14010961b  lea     rax, aFailedGetmodul; "Failed GetModuleHandleEx.  GetLastError"...
0x140109622  mov     [rbp+var_8], rax
0x140109626  lea     rax, [rbp+var_30]
0x14010962a  mov     [rsp+80h+var_38], rax
0x14010962f  lea     rax, [rbp+var_18]
0x140109633  mov     [rsp+80h+var_40], rax
0x140109638  lea     rax, [rbp+var_2C]
0x14010963c  mov     [rsp+80h+var_48], rax
0x140109641  lea     rax, [rbp+var_10]
0x140109645  mov     [rsp+80h+var_50], rax
0x14010964a  lea     rax, [rbp+var_28]
0x14010964e  mov     [rsp+80h+lpThreadId], rax
0x140109653  lea     rax, [rbp+var_8]
0x140109657  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x14010965c  mov     [rbp+var_28], ebx
0x14010965f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140109664  jmp     short loc_1401096B7
0x140109666  mov     rax, [rbp+phModule]
0x14010966a  lea     r8, ?PAL_System_Win32_ThreadProcWrapper@@YAKPEAX@Z; lpStartAddress
0x140109671  mov     [rdi+10h], rax
0x140109675  mov     r9, rdi; lpParameter
0x140109678  lea     rax, [rbp+ThreadId]
0x14010967c  xor     edx, edx; dwStackSize
0x14010967e  mov     [rsp+80h+lpThreadId], rax; lpThreadId
0x140109683  xor     ecx, ecx; lpThreadAttributes
0x140109685  mov     [rsp+80h+dwCreationFlags], 0; dwCreationFlags
0x14010968d  call    cs:__imp_CreateThread
0x140109693  mov     rcx, rax
0x140109696  test    rax, rax
0x140109699  jnz     short loc_1401096C5
0x14010969b  mov     rcx, [rbp+phModule]; hLibModule
0x14010969f  test    rcx, rcx
0x1401096a2  jz      short loc_1401096B2
0x1401096a4  call    cs:__imp_FreeLibrary
0x1401096aa  mov     [rbp+phModule], 0
0x1401096b2  mov     ebx, 80004005h
0x1401096b7  mov     rcx, rdi; hMem
0x1401096ba  call    cs:__imp_LocalFree
0x1401096c0  jmp     loc_14010974A
0x1401096c5  mov     eax, [rbp+ThreadId]
0x1401096c8  mov     [rbx], eax
0x1401096ca  xor     ebx, ebx
0x1401096cc  mov     [rsi], rcx
0x1401096cf  jmp     short loc_14010974A
0x1401096d1  mov     eax, cs:dword_140150118
0x1401096d7  cmp     eax, 2
0x1401096da  jbe     short loc_140109745
0x1401096dc  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x1401096e3  mov     [rbp+var_28], 4F4h
0x1401096ea  mov     [rbp+var_8], rax
0x1401096ee  lea     rdx, qword_1401444A8
0x1401096f5  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1401096fc  mov     ebx, 80004005h
0x140109701  mov     [rbp+var_10], rax
0x140109705  lea     rax, aNullParameterP; "NULL parameter passed"
0x14010970c  mov     [rbp+var_18], rax
0x140109710  lea     rax, [rbp+var_8]
0x140109714  mov     [rsp+80h+var_40], rax
0x140109719  lea     rax, [rbp+var_28]
0x14010971d  mov     [rsp+80h+var_48], rax
0x140109722  lea     rax, [rbp+var_10]
0x140109726  mov     [rsp+80h+var_50], rax
0x14010972b  lea     rax, [rbp+var_2C]
0x14010972f  mov     [rsp+80h+lpThreadId], rax
0x140109734  lea     rax, [rbp+var_18]
0x140109738  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x14010973d  mov     [rbp+var_2C], ebx
0x140109740  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140109745  mov     ebx, 80070057h
0x14010974a  lea     r11, [rsp+80h+var_s0]
0x140109752  mov     eax, ebx
0x140109754  mov     rbx, [r11+28h]
0x140109758  mov     rsi, [r11+30h]
0x14010975c  mov     rsp, r11
0x14010975f  pop     r14
0x140109761  pop     rdi
0x140109762  pop     rbp
0x140109763  retn
```
