# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006144`
- end: `0x1800063fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000478c`
- `0x180006ca0`
- `0x1800073fc`
- `0x18000a030`

## callees

- `0x1800025f0`
- `0x180003114`
- `0x180006144`
- `0x180006fa0`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006276`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006276`

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
          v7 = (const char *)&byte_180043ADF;
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
0x180006144  mov     [rsp+arg_18], rbx
0x180006149  push    rbp
0x18000614a  push    rsi
0x18000614b  push    rdi
0x18000614c  push    r14
0x18000614e  push    r15
0x180006150  sub     rsp, 250h
0x180006157  mov     rax, cs:__security_cookie
0x18000615e  xor     rax, rsp
0x180006161  mov     [rsp+278h+var_38], rax
0x180006169  mov     rbx, r8
0x18000616c  mov     rsi, rdx
0x18000616f  mov     r14, rcx
0x180006172  xor     r15d, r15d
0x180006175  test    rdx, rdx
0x180006178  jz      loc_1800063D1
0x18000617e  test    rcx, rcx
0x180006181  jz      loc_1800063D1
0x180006187  mov     [rcx], r15w
0x18000618b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006192  test    rax, rax
0x180006195  jz      short loc_1800061B8
0x180006197  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000619e  jz      short loc_1800061B8
0x1800061a0  mov     r8, rdx
0x1800061a3  mov     rdx, rcx
0x1800061a6  mov     rcx, rbx
0x1800061a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ae  cmp     [r14], r15w
0x1800061b2  jnz     loc_1800063D1
0x1800061b8  mov     ecx, [rbx]
0x1800061ba  mov     bpl, 8
0x1800061bd  test    ecx, ecx
0x1800061bf  jz      short loc_18000620A
0x1800061c1  sub     ecx, 1
0x1800061c4  jz      short loc_1800061F2
0x1800061c6  sub     ecx, 1
0x1800061c9  jz      short loc_1800061E2
0x1800061cb  cmp     ecx, 1
0x1800061ce  jz      short loc_1800061D9
0x1800061d0  lea     rdi, byte_180043ADF
0x1800061d7  jmp     short loc_180006211
0x1800061d9  lea     rdi, aFailfast; "FailFast"
0x1800061e0  jmp     short loc_180006211
0x1800061e2  lea     rax, aLoghr; "LogHr"
0x1800061e9  lea     rdi, aLognt; "LogNt"
0x1800061f0  jmp     short loc_180006200
0x1800061f2  lea     rax, aReturnhr; "ReturnHr"
0x1800061f9  lea     rdi, aReturnnt; "ReturnNt"
0x180006200  test    [rbx+4], bpl
0x180006204  cmovz   rdi, rax
0x180006208  jmp     short loc_180006211
0x18000620a  lea     rdi, aException; "Exception"
0x180006211  xor     edx, edx; Val
0x180006213  mov     r8d, 200h; Size
0x180006219  lea     rcx, [rsp+278h+Buffer]; void *
0x18000621e  call    memset_0
0x180006223  test    [rbx+4], bpl
0x180006227  jz      short loc_18000624C
0x180006229  mov     ebp, [rbx+0Ch]
0x18000622c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006233  test    rax, rax
0x180006236  jz      short loc_18000627C
0x180006238  mov     r8d, 100h
0x18000623e  lea     rdx, [rsp+278h+Buffer]
0x180006243  mov     ecx, ebp
0x180006245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000624a  jmp     short loc_18000627C
0x18000624c  mov     ebp, [rbx+8]
0x18000624f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006254  mov     [rsp+278h+nSize], 100h; nSize
0x18000625c  lea     rax, [rsp+278h+Buffer]
0x180006261  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006266  mov     r9d, 400h; dwLanguageId
0x18000626c  mov     r8d, ebp; dwMessageId
0x18000626f  xor     edx, edx; lpSource
0x180006271  mov     ecx, 1200h; dwFlags
0x180006276  call    cs:__imp_FormatMessageW
0x18000627c  lea     rsi, [r14+rsi*2]
0x180006280  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006284  mov     rax, [rbx+88h]
0x18000628b  mov     rcx, [rbx+80h]
0x180006292  mov     rdx, rsi; unsigned __int16 *
0x180006295  test    r9, r9
0x180006298  jz      short loc_1800062BC
0x18000629a  mov     [rsp+278h+Arguments], rax
0x18000629f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800062a4  mov     eax, [rbx+40h]
0x1800062a7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800062ab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800062b2  mov     rcx, r14; this
0x1800062b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800062ba  jmp     short loc_1800062D3
0x1800062bc  mov     [rsp+278h+lpBuffer], rax
0x1800062c1  mov     r9, rcx; unsigned __int16 *
0x1800062c4  lea     r8, aHsP; "%hs!%p: "
0x1800062cb  mov     rcx, r14; this
0x1800062ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800062d3  mov     r14, rax
0x1800062d6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800062dd  test    r9, r9
0x1800062e0  jz      short loc_1800062F7
0x1800062e2  lea     r8, aCallerP; "(caller: %p) "
0x1800062e9  mov     rdx, rsi; unsigned __int16 *
0x1800062ec  mov     rcx, rax; this
0x1800062ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800062f4  mov     r14, rax
0x1800062f7  call    cs:__imp_GetCurrentThreadId
0x1800062fd  lea     rcx, [rsp+278h+Buffer]
0x180006302  mov     [rsp+278h+var_240], rcx
0x180006307  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000630b  mov     [rsp+278h+nSize], eax
0x18000630f  mov     eax, [rbx+44h]
0x180006312  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006316  mov     r9, rdi; unsigned __int16 *
0x180006319  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006320  mov     rdx, rsi; unsigned __int16 *
0x180006323  mov     rcx, r14; this
0x180006326  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000632b  cmp     [rbx+18h], r15
0x18000632f  jnz     short loc_180006341
0x180006331  cmp     [rbx+48h], r15
0x180006335  jnz     short loc_180006341
0x180006337  cmp     [rbx+30h], r15
0x18000633b  jz      loc_1800063D1
0x180006341  lea     r8, asc_180043BD0; "    "
0x180006348  mov     rdx, rsi; unsigned __int16 *
0x18000634b  mov     rcx, rax; this
0x18000634e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006353  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006357  test    r9, r9
0x18000635a  jz      short loc_18000636E
0x18000635c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006363  mov     rdx, rsi; unsigned __int16 *
0x180006366  mov     rcx, rax; this
0x180006369  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000636e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006372  test    r9, r9
0x180006375  jz      short loc_180006389
0x180006377  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000637e  mov     rdx, rsi; unsigned __int16 *
0x180006381  mov     rcx, rax; this
0x180006384  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006389  mov     rcx, [rbx+28h]
0x18000638d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006391  mov     rdx, rsi; unsigned __int16 *
0x180006394  test    rcx, rcx
0x180006397  jz      short loc_1800063AF
0x180006399  mov     [rsp+278h+lpBuffer], rcx
0x18000639e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800063a5  mov     rcx, rax; this
0x1800063a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800063ad  jmp     short loc_1800063D1
0x1800063af  mov     rcx, rax; this
0x1800063b2  test    r9, r9
0x1800063b5  jz      short loc_1800063C5
0x1800063b7  lea     r8, aHs; "[%hs]\n"
0x1800063be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800063c3  jmp     short loc_1800063D1
0x1800063c5  lea     r8, psz; "\n"
0x1800063cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800063d1  xor     eax, eax
0x1800063d3  mov     rcx, [rsp+278h+var_38]
0x1800063db  xor     rcx, rsp; StackCookie
0x1800063de  call    __security_check_cookie
0x1800063e3  mov     rbx, [rsp+278h+arg_18]
0x1800063eb  add     rsp, 250h
0x1800063f2  pop     r15
0x1800063f4  pop     r14
0x1800063f6  pop     rdi
0x1800063f7  pop     rsi
0x1800063f8  pop     rbp
0x1800063f9  retn
```
