# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140009350`
- end: `0x140009606`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x140003cd4`
- `0x140003f54`
- `0x1400042ec`
- `0x140009ee4`
- `0x140010c10`
- `0x140011791`
- `0x1400118c5`

## callees

- `0x1400022a0`
- `0x140002d4c`
- `0x140009350`
- `0x14000a1e4`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009503`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009503`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140009482`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140009482`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  wil::details *v15; // r14
  const unsigned __int16 *v16; // r9
  wil::details *v17; // rax
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r9
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
          v7 = (const char *)&dword_140013B84;
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
  v10 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
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
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x140009350  mov     [rsp+arg_18], rbx
0x140009355  push    rbp
0x140009356  push    rsi
0x140009357  push    rdi
0x140009358  push    r14
0x14000935a  push    r15
0x14000935c  sub     rsp, 250h
0x140009363  mov     rax, cs:__security_cookie
0x14000936a  xor     rax, rsp
0x14000936d  mov     [rsp+278h+var_38], rax
0x140009375  mov     rbx, r8
0x140009378  mov     rsi, rdx
0x14000937b  mov     r14, rcx
0x14000937e  xor     r15d, r15d
0x140009381  test    rdx, rdx
0x140009384  jz      loc_1400095DD
0x14000938a  test    rcx, rcx
0x14000938d  jz      loc_1400095DD
0x140009393  mov     [rcx], r15w
0x140009397  mov     rax, cs:g_pfnResultLoggingCallback
0x14000939e  test    rax, rax
0x1400093a1  jz      short loc_1400093C4
0x1400093a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400093aa  jz      short loc_1400093C4
0x1400093ac  mov     r8, rdx
0x1400093af  mov     rdx, rcx
0x1400093b2  mov     rcx, rbx
0x1400093b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093ba  cmp     [r14], r15w
0x1400093be  jnz     loc_1400095DD
0x1400093c4  mov     ecx, [rbx]
0x1400093c6  mov     bpl, 8
0x1400093c9  test    ecx, ecx
0x1400093cb  jz      short loc_140009416
0x1400093cd  sub     ecx, 1
0x1400093d0  jz      short loc_1400093FE
0x1400093d2  sub     ecx, 1
0x1400093d5  jz      short loc_1400093EE
0x1400093d7  cmp     ecx, 1
0x1400093da  jz      short loc_1400093E5
0x1400093dc  lea     rdi, dword_140013B84
0x1400093e3  jmp     short loc_14000941D
0x1400093e5  lea     rdi, aFailfast; "FailFast"
0x1400093ec  jmp     short loc_14000941D
0x1400093ee  lea     rax, aLoghr; "LogHr"
0x1400093f5  lea     rdi, aLognt; "LogNt"
0x1400093fc  jmp     short loc_14000940C
0x1400093fe  lea     rax, aReturnhr; "ReturnHr"
0x140009405  lea     rdi, aReturnnt; "ReturnNt"
0x14000940c  test    [rbx+4], bpl
0x140009410  cmovz   rdi, rax
0x140009414  jmp     short loc_14000941D
0x140009416  lea     rdi, aException; "Exception"
0x14000941d  xor     edx, edx; Val
0x14000941f  mov     r8d, 200h; Size
0x140009425  lea     rcx, [rsp+278h+Buffer]; void *
0x14000942a  call    memset_0
0x14000942f  test    [rbx+4], bpl
0x140009433  jz      short loc_140009458
0x140009435  mov     ebp, [rbx+0Ch]
0x140009438  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000943f  test    rax, rax
0x140009442  jz      short loc_140009488
0x140009444  mov     r8d, 100h
0x14000944a  lea     rdx, [rsp+278h+Buffer]
0x14000944f  mov     ecx, ebp
0x140009451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009456  jmp     short loc_140009488
0x140009458  mov     ebp, [rbx+8]
0x14000945b  mov     [rsp+278h+Arguments], r15; Arguments
0x140009460  mov     [rsp+278h+nSize], 100h; nSize
0x140009468  lea     rax, [rsp+278h+Buffer]
0x14000946d  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140009472  mov     r9d, 400h; dwLanguageId
0x140009478  mov     r8d, ebp; dwMessageId
0x14000947b  xor     edx, edx; lpSource
0x14000947d  mov     ecx, 1200h; dwFlags
0x140009482  call    cs:__imp_FormatMessageW
0x140009488  lea     rsi, [r14+rsi*2]
0x14000948c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140009490  mov     rax, [rbx+88h]
0x140009497  mov     rcx, [rbx+80h]
0x14000949e  mov     rdx, rsi; unsigned __int16 *
0x1400094a1  test    r9, r9
0x1400094a4  jz      short loc_1400094C8
0x1400094a6  mov     [rsp+278h+Arguments], rax
0x1400094ab  mov     qword ptr [rsp+278h+nSize], rcx
0x1400094b0  mov     eax, [rbx+40h]
0x1400094b3  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400094b7  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400094be  mov     rcx, r14; this
0x1400094c1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400094c6  jmp     short loc_1400094DF
0x1400094c8  mov     [rsp+278h+lpBuffer], rax
0x1400094cd  mov     r9, rcx; unsigned __int16 *
0x1400094d0  lea     r8, aHsP; "%hs!%p: "
0x1400094d7  mov     rcx, r14; this
0x1400094da  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400094df  mov     r14, rax
0x1400094e2  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400094e9  test    r9, r9
0x1400094ec  jz      short loc_140009503
0x1400094ee  lea     r8, aCallerP; "(caller: %p) "
0x1400094f5  mov     rdx, rsi; unsigned __int16 *
0x1400094f8  mov     rcx, rax; this
0x1400094fb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009500  mov     r14, rax
0x140009503  call    cs:__imp_GetCurrentThreadId
0x140009509  lea     rcx, [rsp+278h+Buffer]
0x14000950e  mov     [rsp+278h+var_240], rcx
0x140009513  mov     dword ptr [rsp+278h+Arguments], ebp
0x140009517  mov     [rsp+278h+nSize], eax
0x14000951b  mov     eax, [rbx+44h]
0x14000951e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140009522  mov     r9, rdi; unsigned __int16 *
0x140009525  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000952c  mov     rdx, rsi; unsigned __int16 *
0x14000952f  mov     rcx, r14; this
0x140009532  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009537  cmp     [rbx+18h], r15
0x14000953b  jnz     short loc_14000954D
0x14000953d  cmp     [rbx+48h], r15
0x140009541  jnz     short loc_14000954D
0x140009543  cmp     [rbx+30h], r15
0x140009547  jz      loc_1400095DD
0x14000954d  lea     r8, asc_140013CA8; "    "
0x140009554  mov     rdx, rsi; unsigned __int16 *
0x140009557  mov     rcx, rax; this
0x14000955a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000955f  mov     r9, [rbx+18h]; unsigned __int16 *
0x140009563  test    r9, r9
0x140009566  jz      short loc_14000957A
0x140009568  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000956f  mov     rdx, rsi; unsigned __int16 *
0x140009572  mov     rcx, rax; this
0x140009575  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000957a  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000957e  test    r9, r9
0x140009581  jz      short loc_140009595
0x140009583  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000958a  mov     rdx, rsi; unsigned __int16 *
0x14000958d  mov     rcx, rax; this
0x140009590  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009595  mov     rcx, [rbx+28h]
0x140009599  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000959d  mov     rdx, rsi; unsigned __int16 *
0x1400095a0  test    rcx, rcx
0x1400095a3  jz      short loc_1400095BB
0x1400095a5  mov     [rsp+278h+lpBuffer], rcx
0x1400095aa  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400095b1  mov     rcx, rax; this
0x1400095b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400095b9  jmp     short loc_1400095DD
0x1400095bb  mov     rcx, rax; this
0x1400095be  test    r9, r9
0x1400095c1  jz      short loc_1400095D1
0x1400095c3  lea     r8, aHs; "[%hs]\n"
0x1400095ca  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400095cf  jmp     short loc_1400095DD
0x1400095d1  lea     r8, asc_140013D20; "\n"
0x1400095d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400095dd  xor     eax, eax
0x1400095df  mov     rcx, [rsp+278h+var_38]
0x1400095e7  xor     rcx, rsp; StackCookie
0x1400095ea  call    __security_check_cookie
0x1400095ef  mov     rbx, [rsp+278h+arg_18]
0x1400095f7  add     rsp, 250h
0x1400095fe  pop     r15
0x140009600  pop     r14
0x140009602  pop     rdi
0x140009603  pop     rsi
0x140009604  pop     rbp
0x140009605  retn
```
