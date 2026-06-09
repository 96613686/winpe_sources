# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006fe4`
- end: `0x18000729a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180004788`
- `0x180004a08`
- `0x180004cb4`
- `0x18000af80`
- `0x18000be28`
- `0x180058b26`
- `0x180058c5a`
- `0x180059970`
- `0x180059d63`

## callees

- `0x1800024e0`
- `0x180002efc`
- `0x180006fe4`
- `0x180007a38`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007197`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007116`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007116`

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
          v7 = (const char *)&word_180065826;
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
0x180006fe4  mov     [rsp+arg_18], rbx
0x180006fe9  push    rbp
0x180006fea  push    rsi
0x180006feb  push    rdi
0x180006fec  push    r14
0x180006fee  push    r15
0x180006ff0  sub     rsp, 250h
0x180006ff7  mov     rax, cs:__security_cookie
0x180006ffe  xor     rax, rsp
0x180007001  mov     [rsp+278h+var_38], rax
0x180007009  mov     rbx, r8
0x18000700c  mov     rsi, rdx
0x18000700f  mov     r14, rcx
0x180007012  xor     r15d, r15d
0x180007015  test    rdx, rdx
0x180007018  jz      loc_180007271
0x18000701e  test    rcx, rcx
0x180007021  jz      loc_180007271
0x180007027  mov     [rcx], r15w
0x18000702b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007032  test    rax, rax
0x180007035  jz      short loc_180007058
0x180007037  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000703e  jz      short loc_180007058
0x180007040  mov     r8, rdx
0x180007043  mov     rdx, rcx
0x180007046  mov     rcx, rbx
0x180007049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000704e  cmp     [r14], r15w
0x180007052  jnz     loc_180007271
0x180007058  mov     ecx, [rbx]
0x18000705a  mov     bpl, 8
0x18000705d  test    ecx, ecx
0x18000705f  jz      short loc_1800070AA
0x180007061  sub     ecx, 1
0x180007064  jz      short loc_180007092
0x180007066  sub     ecx, 1
0x180007069  jz      short loc_180007082
0x18000706b  cmp     ecx, 1
0x18000706e  jz      short loc_180007079
0x180007070  lea     rdi, word_180065826
0x180007077  jmp     short loc_1800070B1
0x180007079  lea     rdi, aFailfast; "FailFast"
0x180007080  jmp     short loc_1800070B1
0x180007082  lea     rax, aLoghr; "LogHr"
0x180007089  lea     rdi, aLognt; "LogNt"
0x180007090  jmp     short loc_1800070A0
0x180007092  lea     rax, aReturnhr; "ReturnHr"
0x180007099  lea     rdi, aReturnnt; "ReturnNt"
0x1800070a0  test    [rbx+4], bpl
0x1800070a4  cmovz   rdi, rax
0x1800070a8  jmp     short loc_1800070B1
0x1800070aa  lea     rdi, aException; "Exception"
0x1800070b1  xor     edx, edx; Val
0x1800070b3  mov     r8d, 200h; Size
0x1800070b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800070be  call    memset_0
0x1800070c3  test    [rbx+4], bpl
0x1800070c7  jz      short loc_1800070EC
0x1800070c9  mov     ebp, [rbx+0Ch]
0x1800070cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800070d3  test    rax, rax
0x1800070d6  jz      short loc_18000711C
0x1800070d8  mov     r8d, 100h
0x1800070de  lea     rdx, [rsp+278h+Buffer]
0x1800070e3  mov     ecx, ebp
0x1800070e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070ea  jmp     short loc_18000711C
0x1800070ec  mov     ebp, [rbx+8]
0x1800070ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800070f4  mov     [rsp+278h+nSize], 100h; nSize
0x1800070fc  lea     rax, [rsp+278h+Buffer]
0x180007101  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007106  mov     r9d, 400h; dwLanguageId
0x18000710c  mov     r8d, ebp; dwMessageId
0x18000710f  xor     edx, edx; lpSource
0x180007111  mov     ecx, 1200h; dwFlags
0x180007116  call    cs:__imp_FormatMessageW
0x18000711c  lea     rsi, [r14+rsi*2]
0x180007120  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007124  mov     rax, [rbx+88h]
0x18000712b  mov     rcx, [rbx+80h]
0x180007132  mov     rdx, rsi; unsigned __int16 *
0x180007135  test    r9, r9
0x180007138  jz      short loc_18000715C
0x18000713a  mov     [rsp+278h+Arguments], rax
0x18000713f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007144  mov     eax, [rbx+40h]
0x180007147  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000714b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007152  mov     rcx, r14; this
0x180007155  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000715a  jmp     short loc_180007173
0x18000715c  mov     [rsp+278h+lpBuffer], rax
0x180007161  mov     r9, rcx; unsigned __int16 *
0x180007164  lea     r8, aHsP; "%hs!%p: "
0x18000716b  mov     rcx, r14; this
0x18000716e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007173  mov     r14, rax
0x180007176  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000717d  test    r9, r9
0x180007180  jz      short loc_180007197
0x180007182  lea     r8, aCallerP; "(caller: %p) "
0x180007189  mov     rdx, rsi; unsigned __int16 *
0x18000718c  mov     rcx, rax; this
0x18000718f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007194  mov     r14, rax
0x180007197  call    cs:__imp_GetCurrentThreadId
0x18000719d  lea     rcx, [rsp+278h+Buffer]
0x1800071a2  mov     [rsp+278h+var_240], rcx
0x1800071a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800071ab  mov     [rsp+278h+nSize], eax
0x1800071af  mov     eax, [rbx+44h]
0x1800071b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800071b6  mov     r9, rdi; unsigned __int16 *
0x1800071b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800071c0  mov     rdx, rsi; unsigned __int16 *
0x1800071c3  mov     rcx, r14; this
0x1800071c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800071cb  cmp     [rbx+18h], r15
0x1800071cf  jnz     short loc_1800071E1
0x1800071d1  cmp     [rbx+48h], r15
0x1800071d5  jnz     short loc_1800071E1
0x1800071d7  cmp     [rbx+30h], r15
0x1800071db  jz      loc_180007271
0x1800071e1  lea     r8, asc_180065928; "    "
0x1800071e8  mov     rdx, rsi; unsigned __int16 *
0x1800071eb  mov     rcx, rax; this
0x1800071ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800071f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800071f7  test    r9, r9
0x1800071fa  jz      short loc_18000720E
0x1800071fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007203  mov     rdx, rsi; unsigned __int16 *
0x180007206  mov     rcx, rax; this
0x180007209  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000720e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007212  test    r9, r9
0x180007215  jz      short loc_180007229
0x180007217  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000721e  mov     rdx, rsi; unsigned __int16 *
0x180007221  mov     rcx, rax; this
0x180007224  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007229  mov     rcx, [rbx+28h]
0x18000722d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007231  mov     rdx, rsi; unsigned __int16 *
0x180007234  test    rcx, rcx
0x180007237  jz      short loc_18000724F
0x180007239  mov     [rsp+278h+lpBuffer], rcx
0x18000723e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007245  mov     rcx, rax; this
0x180007248  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000724d  jmp     short loc_180007271
0x18000724f  mov     rcx, rax; this
0x180007252  test    r9, r9
0x180007255  jz      short loc_180007265
0x180007257  lea     r8, aHs; "[%hs]\n"
0x18000725e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007263  jmp     short loc_180007271
0x180007265  lea     r8, asc_1800659A0; "\n"
0x18000726c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007271  xor     eax, eax
0x180007273  mov     rcx, [rsp+278h+var_38]
0x18000727b  xor     rcx, rsp; StackCookie
0x18000727e  call    __security_check_cookie
0x180007283  mov     rbx, [rsp+278h+arg_18]
0x18000728b  add     rsp, 250h
0x180007292  pop     r15
0x180007294  pop     r14
0x180007296  pop     rdi
0x180007297  pop     rsi
0x180007298  pop     rbp
0x180007299  retn
```
