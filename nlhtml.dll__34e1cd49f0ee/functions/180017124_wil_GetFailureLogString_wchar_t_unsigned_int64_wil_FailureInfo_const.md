# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180017124`
- end: `0x1800173da`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180015604`
- `0x180017b0c`
- `0x180018110`
- `0x18001aac0`

## callees

- `0x180013b2c`
- `0x180014130`
- `0x180014ff0`
- `0x180017124`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800172d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800172d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180017256`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180017256`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !this )
    return 0;
  *(_WORD *)this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, a2);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v8 = "ReturnHr";
      v7 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v7 = "FailFast";
        else
          v7 = (const char *)&dword_18003138C;
        goto LABEL_18;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_18;
  }
  v7 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v9 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v9, Buffer, 0x100u);
  }
  else
  {
    v9 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v9, 0x400u, Buffer, 0x100u, 0);
  }
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = (wil::details *)v14;
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017124  mov     [rsp+arg_18], rbx
0x180017129  push    rbp
0x18001712a  push    rsi
0x18001712b  push    rdi
0x18001712c  push    r14
0x18001712e  push    r15
0x180017130  sub     rsp, 250h
0x180017137  mov     rax, cs:__security_cookie
0x18001713e  xor     rax, rsp
0x180017141  mov     [rsp+278h+var_38], rax
0x180017149  mov     rbx, r8
0x18001714c  mov     rsi, rdx
0x18001714f  mov     r14, rcx
0x180017152  xor     r15d, r15d
0x180017155  test    rdx, rdx
0x180017158  jz      loc_1800173B1
0x18001715e  test    rcx, rcx
0x180017161  jz      loc_1800173B1
0x180017167  mov     [rcx], r15w
0x18001716b  mov     rax, cs:g_pfnResultLoggingCallback
0x180017172  test    rax, rax
0x180017175  jz      short loc_180017198
0x180017177  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001717e  jz      short loc_180017198
0x180017180  mov     r8, rdx
0x180017183  mov     rdx, rcx
0x180017186  mov     rcx, rbx
0x180017189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001718e  cmp     [r14], r15w
0x180017192  jnz     loc_1800173B1
0x180017198  mov     ecx, [rbx]
0x18001719a  mov     bpl, 8
0x18001719d  test    ecx, ecx
0x18001719f  jz      short loc_1800171EA
0x1800171a1  sub     ecx, 1
0x1800171a4  jz      short loc_1800171D2
0x1800171a6  sub     ecx, 1
0x1800171a9  jz      short loc_1800171C2
0x1800171ab  cmp     ecx, 1
0x1800171ae  jz      short loc_1800171B9
0x1800171b0  lea     rdi, dword_18003138C
0x1800171b7  jmp     short loc_1800171F1
0x1800171b9  lea     rdi, aFailfast; "FailFast"
0x1800171c0  jmp     short loc_1800171F1
0x1800171c2  lea     rax, aLoghr; "LogHr"
0x1800171c9  lea     rdi, aLognt; "LogNt"
0x1800171d0  jmp     short loc_1800171E0
0x1800171d2  lea     rax, aReturnhr; "ReturnHr"
0x1800171d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800171e0  test    [rbx+4], bpl
0x1800171e4  cmovz   rdi, rax
0x1800171e8  jmp     short loc_1800171F1
0x1800171ea  lea     rdi, aException; "Exception"
0x1800171f1  xor     edx, edx; Val
0x1800171f3  mov     r8d, 200h; Size
0x1800171f9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800171fe  call    memset_0
0x180017203  test    [rbx+4], bpl
0x180017207  jz      short loc_18001722C
0x180017209  mov     ebp, [rbx+0Ch]
0x18001720c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180017213  test    rax, rax
0x180017216  jz      short loc_18001725C
0x180017218  mov     r8d, 100h
0x18001721e  lea     rdx, [rsp+278h+Buffer]
0x180017223  mov     ecx, ebp
0x180017225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001722a  jmp     short loc_18001725C
0x18001722c  mov     ebp, [rbx+8]
0x18001722f  mov     [rsp+278h+Arguments], r15; Arguments
0x180017234  mov     [rsp+278h+nSize], 100h; nSize
0x18001723c  lea     rax, [rsp+278h+Buffer]
0x180017241  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180017246  mov     r9d, 400h; dwLanguageId
0x18001724c  mov     r8d, ebp; dwMessageId
0x18001724f  xor     edx, edx; lpSource
0x180017251  mov     ecx, 1200h; dwFlags
0x180017256  call    cs:__imp_FormatMessageW
0x18001725c  lea     rsi, [r14+rsi*2]
0x180017260  mov     r9, [rbx+38h]; wchar_t *
0x180017264  mov     rax, [rbx+88h]
0x18001726b  mov     rcx, [rbx+80h]
0x180017272  mov     rdx, rsi; wchar_t *
0x180017275  test    r9, r9
0x180017278  jz      short loc_18001729C
0x18001727a  mov     [rsp+278h+Arguments], rax
0x18001727f  mov     qword ptr [rsp+278h+nSize], rcx
0x180017284  mov     eax, [rbx+40h]
0x180017287  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001728b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180017292  mov     rcx, r14; this
0x180017295  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18001729a  jmp     short loc_1800172B3
0x18001729c  mov     [rsp+278h+lpBuffer], rax
0x1800172a1  mov     r9, rcx; wchar_t *
0x1800172a4  lea     r8, aHsP; "%hs!%p: "
0x1800172ab  mov     rcx, r14; this
0x1800172ae  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800172b3  mov     r14, rax
0x1800172b6  mov     r9, [rbx+90h]; wchar_t *
0x1800172bd  test    r9, r9
0x1800172c0  jz      short loc_1800172D7
0x1800172c2  lea     r8, aCallerP; "(caller: %p) "
0x1800172c9  mov     rdx, rsi; wchar_t *
0x1800172cc  mov     rcx, rax; this
0x1800172cf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800172d4  mov     r14, rax
0x1800172d7  call    cs:__imp_GetCurrentThreadId
0x1800172dd  lea     rcx, [rsp+278h+Buffer]
0x1800172e2  mov     [rsp+278h+var_240], rcx
0x1800172e7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800172eb  mov     [rsp+278h+nSize], eax
0x1800172ef  mov     eax, [rbx+44h]
0x1800172f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800172f6  mov     r9, rdi; wchar_t *
0x1800172f9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180017300  mov     rdx, rsi; wchar_t *
0x180017303  mov     rcx, r14; this
0x180017306  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18001730b  cmp     [rbx+18h], r15
0x18001730f  jnz     short loc_180017321
0x180017311  cmp     [rbx+48h], r15
0x180017315  jnz     short loc_180017321
0x180017317  cmp     [rbx+30h], r15
0x18001731b  jz      loc_1800173B1
0x180017321  lea     r8, asc_1800314B8; "    "
0x180017328  mov     rdx, rsi; wchar_t *
0x18001732b  mov     rcx, rax; this
0x18001732e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180017333  mov     r9, [rbx+18h]; wchar_t *
0x180017337  test    r9, r9
0x18001733a  jz      short loc_18001734E
0x18001733c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180017343  mov     rdx, rsi; wchar_t *
0x180017346  mov     rcx, rax; this
0x180017349  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18001734e  mov     r9, [rbx+48h]; wchar_t *
0x180017352  test    r9, r9
0x180017355  jz      short loc_180017369
0x180017357  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001735e  mov     rdx, rsi; wchar_t *
0x180017361  mov     rcx, rax; this
0x180017364  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180017369  mov     rcx, [rbx+28h]
0x18001736d  mov     r9, [rbx+30h]; wchar_t *
0x180017371  mov     rdx, rsi; wchar_t *
0x180017374  test    rcx, rcx
0x180017377  jz      short loc_18001738F
0x180017379  mov     [rsp+278h+lpBuffer], rcx
0x18001737e  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x180017385  mov     rcx, rax; this
0x180017388  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18001738d  jmp     short loc_1800173B1
0x18001738f  mov     rcx, rax; this
0x180017392  test    r9, r9
0x180017395  jz      short loc_1800173A5
0x180017397  lea     r8, aHs; "[%hs]\n"
0x18001739e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800173a3  jmp     short loc_1800173B1
0x1800173a5  lea     r8, asc_180031530; "\n"
0x1800173ac  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800173b1  xor     eax, eax
0x1800173b3  mov     rcx, [rsp+278h+var_38]
0x1800173bb  xor     rcx, rsp; StackCookie
0x1800173be  call    __security_check_cookie
0x1800173c3  mov     rbx, [rsp+278h+arg_18]
0x1800173cb  add     rsp, 250h
0x1800173d2  pop     r15
0x1800173d4  pop     r14
0x1800173d6  pop     rdi
0x1800173d7  pop     rsi
0x1800173d8  pop     rbp
0x1800173d9  retn
```
