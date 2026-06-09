# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001102c`
- end: `0x1800112e2`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c648`
- `0x180011b70`

## callees

- `0x18000fa10`
- `0x18001039c`
- `0x18001102c`
- `0x1800113cc`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800111df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800111df`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001115e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001115e`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&word_18001A40A;
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
0x18001102c  mov     [rsp+arg_18], rbx
0x180011031  push    rbp
0x180011032  push    rsi
0x180011033  push    rdi
0x180011034  push    r14
0x180011036  push    r15
0x180011038  sub     rsp, 250h
0x18001103f  mov     rax, cs:__security_cookie
0x180011046  xor     rax, rsp
0x180011049  mov     [rsp+278h+var_38], rax
0x180011051  mov     rbx, r8
0x180011054  mov     rsi, rdx
0x180011057  mov     r14, rcx
0x18001105a  xor     r15d, r15d
0x18001105d  test    rdx, rdx
0x180011060  jz      loc_1800112B9
0x180011066  test    rcx, rcx
0x180011069  jz      loc_1800112B9
0x18001106f  mov     [rcx], r15w
0x180011073  mov     rax, cs:g_pfnResultLoggingCallback
0x18001107a  test    rax, rax
0x18001107d  jz      short loc_1800110A0
0x18001107f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180011086  jz      short loc_1800110A0
0x180011088  mov     r8, rdx
0x18001108b  mov     rdx, rcx
0x18001108e  mov     rcx, rbx
0x180011091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011096  cmp     [r14], r15w
0x18001109a  jnz     loc_1800112B9
0x1800110a0  mov     ecx, [rbx]
0x1800110a2  mov     bpl, 8
0x1800110a5  test    ecx, ecx
0x1800110a7  jz      short loc_1800110F2
0x1800110a9  sub     ecx, 1
0x1800110ac  jz      short loc_1800110DA
0x1800110ae  sub     ecx, 1
0x1800110b1  jz      short loc_1800110CA
0x1800110b3  cmp     ecx, 1
0x1800110b6  jz      short loc_1800110C1
0x1800110b8  lea     rdi, word_18001A40A
0x1800110bf  jmp     short loc_1800110F9
0x1800110c1  lea     rdi, aFailfast; "FailFast"
0x1800110c8  jmp     short loc_1800110F9
0x1800110ca  lea     rax, aLoghr; "LogHr"
0x1800110d1  lea     rdi, aLognt; "LogNt"
0x1800110d8  jmp     short loc_1800110E8
0x1800110da  lea     rax, aReturnhr; "ReturnHr"
0x1800110e1  lea     rdi, aReturnnt; "ReturnNt"
0x1800110e8  test    [rbx+4], bpl
0x1800110ec  cmovz   rdi, rax
0x1800110f0  jmp     short loc_1800110F9
0x1800110f2  lea     rdi, aException; "Exception"
0x1800110f9  xor     edx, edx; Val
0x1800110fb  mov     r8d, 200h; Size
0x180011101  lea     rcx, [rsp+278h+Buffer]; void *
0x180011106  call    memset_0
0x18001110b  test    [rbx+4], bpl
0x18001110f  jz      short loc_180011134
0x180011111  mov     ebp, [rbx+0Ch]
0x180011114  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001111b  test    rax, rax
0x18001111e  jz      short loc_180011164
0x180011120  mov     r8d, 100h
0x180011126  lea     rdx, [rsp+278h+Buffer]
0x18001112b  mov     ecx, ebp
0x18001112d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011132  jmp     short loc_180011164
0x180011134  mov     ebp, [rbx+8]
0x180011137  mov     [rsp+278h+Arguments], r15; Arguments
0x18001113c  mov     [rsp+278h+nSize], 100h; nSize
0x180011144  lea     rax, [rsp+278h+Buffer]
0x180011149  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001114e  mov     r9d, 400h; dwLanguageId
0x180011154  mov     r8d, ebp; dwMessageId
0x180011157  xor     edx, edx; lpSource
0x180011159  mov     ecx, 1200h; dwFlags
0x18001115e  call    cs:__imp_FormatMessageW
0x180011164  lea     rsi, [r14+rsi*2]
0x180011168  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001116c  mov     rax, [rbx+88h]
0x180011173  mov     rcx, [rbx+80h]
0x18001117a  mov     rdx, rsi; unsigned __int16 *
0x18001117d  test    r9, r9
0x180011180  jz      short loc_1800111A4
0x180011182  mov     [rsp+278h+Arguments], rax
0x180011187  mov     qword ptr [rsp+278h+nSize], rcx
0x18001118c  mov     eax, [rbx+40h]
0x18001118f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011193  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001119a  mov     rcx, r14; this
0x18001119d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800111a2  jmp     short loc_1800111BB
0x1800111a4  mov     [rsp+278h+lpBuffer], rax
0x1800111a9  mov     r9, rcx; unsigned __int16 *
0x1800111ac  lea     r8, aHsP; "%hs!%p: "
0x1800111b3  mov     rcx, r14; this
0x1800111b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800111bb  mov     r14, rax
0x1800111be  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800111c5  test    r9, r9
0x1800111c8  jz      short loc_1800111DF
0x1800111ca  lea     r8, aCallerP; "(caller: %p) "
0x1800111d1  mov     rdx, rsi; unsigned __int16 *
0x1800111d4  mov     rcx, rax; this
0x1800111d7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800111dc  mov     r14, rax
0x1800111df  call    cs:__imp_GetCurrentThreadId
0x1800111e5  lea     rcx, [rsp+278h+Buffer]
0x1800111ea  mov     [rsp+278h+var_240], rcx
0x1800111ef  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800111f3  mov     [rsp+278h+nSize], eax
0x1800111f7  mov     eax, [rbx+44h]
0x1800111fa  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800111fe  mov     r9, rdi; unsigned __int16 *
0x180011201  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180011208  mov     rdx, rsi; unsigned __int16 *
0x18001120b  mov     rcx, r14; this
0x18001120e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011213  cmp     [rbx+18h], r15
0x180011217  jnz     short loc_180011229
0x180011219  cmp     [rbx+48h], r15
0x18001121d  jnz     short loc_180011229
0x18001121f  cmp     [rbx+30h], r15
0x180011223  jz      loc_1800112B9
0x180011229  lea     r8, asc_18001A960; "    "
0x180011230  mov     rdx, rsi; unsigned __int16 *
0x180011233  mov     rcx, rax; this
0x180011236  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001123b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001123f  test    r9, r9
0x180011242  jz      short loc_180011256
0x180011244  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001124b  mov     rdx, rsi; unsigned __int16 *
0x18001124e  mov     rcx, rax; this
0x180011251  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011256  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001125a  test    r9, r9
0x18001125d  jz      short loc_180011271
0x18001125f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180011266  mov     rdx, rsi; unsigned __int16 *
0x180011269  mov     rcx, rax; this
0x18001126c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011271  mov     rcx, [rbx+28h]
0x180011275  mov     r9, [rbx+30h]; unsigned __int16 *
0x180011279  mov     rdx, rsi; unsigned __int16 *
0x18001127c  test    rcx, rcx
0x18001127f  jz      short loc_180011297
0x180011281  mov     [rsp+278h+lpBuffer], rcx
0x180011286  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001128d  mov     rcx, rax; this
0x180011290  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011295  jmp     short loc_1800112B9
0x180011297  mov     rcx, rax; this
0x18001129a  test    r9, r9
0x18001129d  jz      short loc_1800112AD
0x18001129f  lea     r8, aHs; "[%hs]\n"
0x1800112a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800112ab  jmp     short loc_1800112B9
0x1800112ad  lea     r8, asc_18001A9D8; "\n"
0x1800112b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800112b9  xor     eax, eax
0x1800112bb  mov     rcx, [rsp+278h+var_38]
0x1800112c3  xor     rcx, rsp; StackCookie
0x1800112c6  call    __security_check_cookie
0x1800112cb  mov     rbx, [rsp+278h+arg_18]
0x1800112d3  add     rsp, 250h
0x1800112da  pop     r15
0x1800112dc  pop     r14
0x1800112de  pop     rdi
0x1800112df  pop     rsi
0x1800112e0  pop     rbp
0x1800112e1  retn
```
