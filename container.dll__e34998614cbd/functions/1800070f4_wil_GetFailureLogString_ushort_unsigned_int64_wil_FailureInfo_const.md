# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800070f4`
- end: `0x1800073b7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180004034`
- `0x1800042c8`
- `0x180004618`
- `0x180007e84`
- `0x18000c180`
- `0x1800320a0`
- `0x1800321d4`

## callees

- `0x180002ad0`
- `0x18000362c`
- `0x1800070f4`
- `0x180008198`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072ad`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007226`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007226`

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
          v7 = (const char *)&byte_180037E05;
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
0x1800070f4  mov     [rsp+arg_18], rbx
0x1800070f9  push    rbp
0x1800070fa  push    rsi
0x1800070fb  push    rdi
0x1800070fc  push    r14
0x1800070fe  push    r15
0x180007100  sub     rsp, 250h
0x180007107  mov     rax, cs:__security_cookie
0x18000710e  xor     rax, rsp
0x180007111  mov     [rsp+278h+var_38], rax
0x180007119  mov     rbx, r8
0x18000711c  mov     rsi, rdx
0x18000711f  mov     r14, rcx
0x180007122  xor     r15d, r15d
0x180007125  test    rdx, rdx
0x180007128  jz      loc_18000738D
0x18000712e  test    rcx, rcx
0x180007131  jz      loc_18000738D
0x180007137  mov     [rcx], r15w
0x18000713b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007142  test    rax, rax
0x180007145  jz      short loc_180007168
0x180007147  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000714e  jz      short loc_180007168
0x180007150  mov     r8, rdx
0x180007153  mov     rdx, rcx
0x180007156  mov     rcx, rbx
0x180007159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000715e  cmp     [r14], r15w
0x180007162  jnz     loc_18000738D
0x180007168  mov     ecx, [rbx]
0x18000716a  mov     bpl, 8
0x18000716d  test    ecx, ecx
0x18000716f  jz      short loc_1800071BA
0x180007171  sub     ecx, 1
0x180007174  jz      short loc_1800071A2
0x180007176  sub     ecx, 1
0x180007179  jz      short loc_180007192
0x18000717b  cmp     ecx, 1
0x18000717e  jz      short loc_180007189
0x180007180  lea     rdi, byte_180037E05
0x180007187  jmp     short loc_1800071C1
0x180007189  lea     rdi, aFailfast; "FailFast"
0x180007190  jmp     short loc_1800071C1
0x180007192  lea     rax, aLoghr; "LogHr"
0x180007199  lea     rdi, aLognt; "LogNt"
0x1800071a0  jmp     short loc_1800071B0
0x1800071a2  lea     rax, aReturnhr; "ReturnHr"
0x1800071a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800071b0  test    [rbx+4], bpl
0x1800071b4  cmovz   rdi, rax
0x1800071b8  jmp     short loc_1800071C1
0x1800071ba  lea     rdi, aException; "Exception"
0x1800071c1  xor     edx, edx; Val
0x1800071c3  mov     r8d, 200h; Size
0x1800071c9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800071ce  call    memset_0
0x1800071d3  test    [rbx+4], bpl
0x1800071d7  jz      short loc_1800071FC
0x1800071d9  mov     ebp, [rbx+0Ch]
0x1800071dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800071e3  test    rax, rax
0x1800071e6  jz      short loc_180007232
0x1800071e8  mov     r8d, 100h
0x1800071ee  lea     rdx, [rsp+278h+Buffer]
0x1800071f3  mov     ecx, ebp
0x1800071f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071fa  jmp     short loc_180007232
0x1800071fc  mov     ebp, [rbx+8]
0x1800071ff  mov     [rsp+278h+Arguments], r15; Arguments
0x180007204  mov     [rsp+278h+nSize], 100h; nSize
0x18000720c  lea     rax, [rsp+278h+Buffer]
0x180007211  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007216  mov     r9d, 400h; dwLanguageId
0x18000721c  mov     r8d, ebp; dwMessageId
0x18000721f  xor     edx, edx; lpSource
0x180007221  mov     ecx, 1200h; dwFlags
0x180007226  call    cs:__imp_FormatMessageW
0x18000722d  nop     dword ptr [rax+rax+00h]
0x180007232  lea     rsi, [r14+rsi*2]
0x180007236  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000723a  mov     rax, [rbx+88h]
0x180007241  mov     rcx, [rbx+80h]
0x180007248  mov     rdx, rsi; unsigned __int16 *
0x18000724b  test    r9, r9
0x18000724e  jz      short loc_180007272
0x180007250  mov     [rsp+278h+Arguments], rax
0x180007255  mov     qword ptr [rsp+278h+nSize], rcx
0x18000725a  mov     eax, [rbx+40h]
0x18000725d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007261  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007268  mov     rcx, r14; this
0x18000726b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007270  jmp     short loc_180007289
0x180007272  mov     [rsp+278h+lpBuffer], rax
0x180007277  mov     r9, rcx; unsigned __int16 *
0x18000727a  lea     r8, aHsP; "%hs!%p: "
0x180007281  mov     rcx, r14; this
0x180007284  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007289  mov     r14, rax
0x18000728c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007293  test    r9, r9
0x180007296  jz      short loc_1800072AD
0x180007298  lea     r8, aCallerP; "(caller: %p) "
0x18000729f  mov     rdx, rsi; unsigned __int16 *
0x1800072a2  mov     rcx, rax; this
0x1800072a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800072aa  mov     r14, rax
0x1800072ad  call    cs:__imp_GetCurrentThreadId
0x1800072b4  nop     dword ptr [rax+rax+00h]
0x1800072b9  lea     rcx, [rsp+278h+Buffer]
0x1800072be  mov     [rsp+278h+var_240], rcx
0x1800072c3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800072c7  mov     [rsp+278h+nSize], eax
0x1800072cb  mov     eax, [rbx+44h]
0x1800072ce  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800072d2  mov     r9, rdi; unsigned __int16 *
0x1800072d5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800072dc  mov     rdx, rsi; unsigned __int16 *
0x1800072df  mov     rcx, r14; this
0x1800072e2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800072e7  cmp     [rbx+18h], r15
0x1800072eb  jnz     short loc_1800072FD
0x1800072ed  cmp     [rbx+48h], r15
0x1800072f1  jnz     short loc_1800072FD
0x1800072f3  cmp     [rbx+30h], r15
0x1800072f7  jz      loc_18000738D
0x1800072fd  lea     r8, asc_180037EF8; "    "
0x180007304  mov     rdx, rsi; unsigned __int16 *
0x180007307  mov     rcx, rax; this
0x18000730a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000730f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007313  test    r9, r9
0x180007316  jz      short loc_18000732A
0x180007318  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000731f  mov     rdx, rsi; unsigned __int16 *
0x180007322  mov     rcx, rax; this
0x180007325  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000732a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000732e  test    r9, r9
0x180007331  jz      short loc_180007345
0x180007333  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000733a  mov     rdx, rsi; unsigned __int16 *
0x18000733d  mov     rcx, rax; this
0x180007340  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007345  mov     rcx, [rbx+28h]
0x180007349  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000734d  mov     rdx, rsi; unsigned __int16 *
0x180007350  test    rcx, rcx
0x180007353  jz      short loc_18000736B
0x180007355  mov     [rsp+278h+lpBuffer], rcx
0x18000735a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007361  mov     rcx, rax; this
0x180007364  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007369  jmp     short loc_18000738D
0x18000736b  mov     rcx, rax; this
0x18000736e  test    r9, r9
0x180007371  jz      short loc_180007381
0x180007373  lea     r8, aHs; "[%hs]\n"
0x18000737a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000737f  jmp     short loc_18000738D
0x180007381  lea     r8, asc_180037F70; "\n"
0x180007388  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000738d  xor     eax, eax
0x18000738f  mov     rcx, [rsp+278h+var_38]
0x180007397  xor     rcx, rsp; StackCookie
0x18000739a  call    __security_check_cookie
0x18000739f  mov     rbx, [rsp+278h+arg_18]
0x1800073a7  add     rsp, 250h
0x1800073ae  pop     r15
0x1800073b0  pop     r14
0x1800073b2  pop     rdi
0x1800073b3  pop     rsi
0x1800073b4  pop     rbp
0x1800073b5  retn
```
