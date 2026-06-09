# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180038f94`
- end: `0x18003924a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f928`
- `0x180039acc`
- `0x18003be50`

## callees

- `0x180035680`
- `0x180036254`
- `0x180038f94`
- `0x1800397bc`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039147`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039147`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800390c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800390c6`

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
          v7 = (const char *)&dword_180081A9C;
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
0x180038f94  mov     [rsp+arg_18], rbx
0x180038f99  push    rbp
0x180038f9a  push    rsi
0x180038f9b  push    rdi
0x180038f9c  push    r14
0x180038f9e  push    r15
0x180038fa0  sub     rsp, 250h
0x180038fa7  mov     rax, cs:__security_cookie
0x180038fae  xor     rax, rsp
0x180038fb1  mov     [rsp+278h+var_38], rax
0x180038fb9  mov     rbx, r8
0x180038fbc  mov     rsi, rdx
0x180038fbf  mov     r14, rcx
0x180038fc2  xor     r15d, r15d
0x180038fc5  test    rdx, rdx
0x180038fc8  jz      loc_180039221
0x180038fce  test    rcx, rcx
0x180038fd1  jz      loc_180039221
0x180038fd7  mov     [rcx], r15w
0x180038fdb  mov     rax, cs:g_pfnResultLoggingCallback
0x180038fe2  test    rax, rax
0x180038fe5  jz      short loc_180039008
0x180038fe7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180038fee  jz      short loc_180039008
0x180038ff0  mov     r8, rdx
0x180038ff3  mov     rdx, rcx
0x180038ff6  mov     rcx, rbx
0x180038ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ffe  cmp     [r14], r15w
0x180039002  jnz     loc_180039221
0x180039008  mov     ecx, [rbx]
0x18003900a  mov     bpl, 8
0x18003900d  test    ecx, ecx
0x18003900f  jz      short loc_18003905A
0x180039011  sub     ecx, 1
0x180039014  jz      short loc_180039042
0x180039016  sub     ecx, 1
0x180039019  jz      short loc_180039032
0x18003901b  cmp     ecx, 1
0x18003901e  jz      short loc_180039029
0x180039020  lea     rdi, dword_180081A9C
0x180039027  jmp     short loc_180039061
0x180039029  lea     rdi, aFailfast; "FailFast"
0x180039030  jmp     short loc_180039061
0x180039032  lea     rax, aLoghr; "LogHr"
0x180039039  lea     rdi, aLognt; "LogNt"
0x180039040  jmp     short loc_180039050
0x180039042  lea     rax, aReturnhr; "ReturnHr"
0x180039049  lea     rdi, aReturnnt; "ReturnNt"
0x180039050  test    [rbx+4], bpl
0x180039054  cmovz   rdi, rax
0x180039058  jmp     short loc_180039061
0x18003905a  lea     rdi, aException; "Exception"
0x180039061  xor     edx, edx; Val
0x180039063  mov     r8d, 200h; Size
0x180039069  lea     rcx, [rsp+278h+Buffer]; void *
0x18003906e  call    memset_0
0x180039073  test    [rbx+4], bpl
0x180039077  jz      short loc_18003909C
0x180039079  mov     ebp, [rbx+0Ch]
0x18003907c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180039083  test    rax, rax
0x180039086  jz      short loc_1800390CC
0x180039088  mov     r8d, 100h
0x18003908e  lea     rdx, [rsp+278h+Buffer]
0x180039093  mov     ecx, ebp
0x180039095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003909a  jmp     short loc_1800390CC
0x18003909c  mov     ebp, [rbx+8]
0x18003909f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800390a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800390ac  lea     rax, [rsp+278h+Buffer]
0x1800390b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800390b6  mov     r9d, 400h; dwLanguageId
0x1800390bc  mov     r8d, ebp; dwMessageId
0x1800390bf  xor     edx, edx; lpSource
0x1800390c1  mov     ecx, 1200h; dwFlags
0x1800390c6  call    cs:__imp_FormatMessageW
0x1800390cc  lea     rsi, [r14+rsi*2]
0x1800390d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800390d4  mov     rax, [rbx+88h]
0x1800390db  mov     rcx, [rbx+80h]
0x1800390e2  mov     rdx, rsi; unsigned __int16 *
0x1800390e5  test    r9, r9
0x1800390e8  jz      short loc_18003910C
0x1800390ea  mov     [rsp+278h+Arguments], rax
0x1800390ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800390f4  mov     eax, [rbx+40h]
0x1800390f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800390fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180039102  mov     rcx, r14; this
0x180039105  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003910a  jmp     short loc_180039123
0x18003910c  mov     [rsp+278h+lpBuffer], rax
0x180039111  mov     r9, rcx; unsigned __int16 *
0x180039114  lea     r8, aHsP; "%hs!%p: "
0x18003911b  mov     rcx, r14; this
0x18003911e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180039123  mov     r14, rax
0x180039126  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003912d  test    r9, r9
0x180039130  jz      short loc_180039147
0x180039132  lea     r8, aCallerP; "(caller: %p) "
0x180039139  mov     rdx, rsi; unsigned __int16 *
0x18003913c  mov     rcx, rax; this
0x18003913f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180039144  mov     r14, rax
0x180039147  call    cs:__imp_GetCurrentThreadId
0x18003914d  lea     rcx, [rsp+278h+Buffer]
0x180039152  mov     [rsp+278h+var_240], rcx
0x180039157  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003915b  mov     [rsp+278h+nSize], eax
0x18003915f  mov     eax, [rbx+44h]
0x180039162  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180039166  mov     r9, rdi; unsigned __int16 *
0x180039169  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180039170  mov     rdx, rsi; unsigned __int16 *
0x180039173  mov     rcx, r14; this
0x180039176  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003917b  cmp     [rbx+18h], r15
0x18003917f  jnz     short loc_180039191
0x180039181  cmp     [rbx+48h], r15
0x180039185  jnz     short loc_180039191
0x180039187  cmp     [rbx+30h], r15
0x18003918b  jz      loc_180039221
0x180039191  lea     r8, asc_1800831A0; "    "
0x180039198  mov     rdx, rsi; unsigned __int16 *
0x18003919b  mov     rcx, rax; this
0x18003919e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800391a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800391a7  test    r9, r9
0x1800391aa  jz      short loc_1800391BE
0x1800391ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800391b3  mov     rdx, rsi; unsigned __int16 *
0x1800391b6  mov     rcx, rax; this
0x1800391b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800391be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800391c2  test    r9, r9
0x1800391c5  jz      short loc_1800391D9
0x1800391c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800391ce  mov     rdx, rsi; unsigned __int16 *
0x1800391d1  mov     rcx, rax; this
0x1800391d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800391d9  mov     rcx, [rbx+28h]
0x1800391dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800391e1  mov     rdx, rsi; unsigned __int16 *
0x1800391e4  test    rcx, rcx
0x1800391e7  jz      short loc_1800391FF
0x1800391e9  mov     [rsp+278h+lpBuffer], rcx
0x1800391ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800391f5  mov     rcx, rax; this
0x1800391f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800391fd  jmp     short loc_180039221
0x1800391ff  mov     rcx, rax; this
0x180039202  test    r9, r9
0x180039205  jz      short loc_180039215
0x180039207  lea     r8, aHs; "[%hs]\n"
0x18003920e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180039213  jmp     short loc_180039221
0x180039215  lea     r8, asc_180083218; "\n"
0x18003921c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180039221  xor     eax, eax
0x180039223  mov     rcx, [rsp+278h+var_38]
0x18003922b  xor     rcx, rsp; StackCookie
0x18003922e  call    __security_check_cookie
0x180039233  mov     rbx, [rsp+278h+arg_18]
0x18003923b  add     rsp, 250h
0x180039242  pop     r15
0x180039244  pop     r14
0x180039246  pop     rdi
0x180039247  pop     rsi
0x180039248  pop     rbp
0x180039249  retn
```
