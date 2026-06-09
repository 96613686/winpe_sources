# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180032fa4`
- end: `0x18003325a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180031988`
- `0x180033b00`

## callees

- `0x180032fa4`
- `0x180033e00`
- `0x1800375ee`
- `0x180037620`
- `0x180039010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800330d6`
- `KERNEL32!FormatMessageW` at `0x1800330d6`
- `KERNEL32!GetCurrentThreadId` at `0x180033157`
- `KERNEL32!GetCurrentThreadId` at `0x180033157`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&qword_18003F308;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180032fa4  mov     [rsp+arg_18], rbx
0x180032fa9  push    rbp
0x180032faa  push    rsi
0x180032fab  push    rdi
0x180032fac  push    r14
0x180032fae  push    r15
0x180032fb0  sub     rsp, 250h
0x180032fb7  mov     rax, cs:__security_cookie
0x180032fbe  xor     rax, rsp
0x180032fc1  mov     [rsp+278h+var_38], rax
0x180032fc9  xor     r15d, r15d
0x180032fcc  mov     rbx, r8
0x180032fcf  mov     rsi, rdx
0x180032fd2  mov     r14, rcx
0x180032fd5  test    rdx, rdx
0x180032fd8  jz      loc_180033231
0x180032fde  test    rcx, rcx
0x180032fe1  jz      loc_180033231
0x180032fe7  mov     rax, cs:g_pfnResultLoggingCallback
0x180032fee  mov     [rcx], r15w
0x180032ff2  test    rax, rax
0x180032ff5  jz      short loc_180033018
0x180032ff7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180032ffe  jz      short loc_180033018
0x180033000  mov     r8, rdx
0x180033003  mov     rdx, rcx
0x180033006  mov     rcx, rbx
0x180033009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003300e  cmp     [r14], r15w
0x180033012  jnz     loc_180033231
0x180033018  mov     ecx, [rbx]
0x18003301a  mov     bpl, 8
0x18003301d  test    ecx, ecx
0x18003301f  jz      short loc_18003306A
0x180033021  sub     ecx, 1
0x180033024  jz      short loc_180033052
0x180033026  sub     ecx, 1
0x180033029  jz      short loc_180033042
0x18003302b  cmp     ecx, 1
0x18003302e  jz      short loc_180033039
0x180033030  lea     rdi, qword_18003F308
0x180033037  jmp     short loc_180033071
0x180033039  lea     rdi, aFailfast; "FailFast"
0x180033040  jmp     short loc_180033071
0x180033042  lea     rax, aLoghr; "LogHr"
0x180033049  lea     rdi, aLognt; "LogNt"
0x180033050  jmp     short loc_180033060
0x180033052  lea     rax, aReturnhr; "ReturnHr"
0x180033059  lea     rdi, aReturnnt; "ReturnNt"
0x180033060  test    [rbx+4], bpl
0x180033064  cmovz   rdi, rax
0x180033068  jmp     short loc_180033071
0x18003306a  lea     rdi, aException; "Exception"
0x180033071  xor     edx, edx; Val
0x180033073  lea     rcx, [rsp+278h+Buffer]; void *
0x180033078  mov     r8d, 200h; Size
0x18003307e  call    memset_0
0x180033083  test    [rbx+4], bpl
0x180033087  jz      short loc_1800330AC
0x180033089  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180033090  mov     ebp, [rbx+0Ch]
0x180033093  test    rax, rax
0x180033096  jz      short loc_1800330DC
0x180033098  mov     r8d, 100h
0x18003309e  lea     rdx, [rsp+278h+Buffer]
0x1800330a3  mov     ecx, ebp
0x1800330a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330aa  jmp     short loc_1800330DC
0x1800330ac  mov     ebp, [rbx+8]
0x1800330af  lea     rax, [rsp+278h+Buffer]
0x1800330b4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800330b9  mov     r8d, ebp; dwMessageId
0x1800330bc  mov     [rsp+278h+nSize], 100h; nSize
0x1800330c4  mov     r9d, 400h; dwLanguageId
0x1800330ca  xor     edx, edx; lpSource
0x1800330cc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800330d1  mov     ecx, 1200h; dwFlags
0x1800330d6  call    cs:__imp_FormatMessageW
0x1800330dc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800330e0  lea     rsi, [r14+rsi*2]
0x1800330e4  mov     rax, [rbx+88h]
0x1800330eb  mov     rdx, rsi; unsigned __int16 *
0x1800330ee  mov     rcx, [rbx+80h]
0x1800330f5  test    r9, r9
0x1800330f8  jz      short loc_18003311C
0x1800330fa  mov     [rsp+278h+Arguments], rax
0x1800330ff  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180033106  mov     eax, [rbx+40h]
0x180033109  mov     qword ptr [rsp+278h+nSize], rcx
0x18003310e  mov     rcx, r14; this
0x180033111  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180033115  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003311a  jmp     short loc_180033133
0x18003311c  mov     r9, rcx; unsigned __int16 *
0x18003311f  mov     [rsp+278h+lpBuffer], rax
0x180033124  mov     rcx, r14; this
0x180033127  lea     r8, aHsP; "%hs!%p: "
0x18003312e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180033133  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003313a  mov     r14, rax
0x18003313d  test    r9, r9
0x180033140  jz      short loc_180033157
0x180033142  lea     r8, aCallerP; "(caller: %p) "
0x180033149  mov     rdx, rsi; unsigned __int16 *
0x18003314c  mov     rcx, rax; this
0x18003314f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180033154  mov     r14, rax
0x180033157  call    cs:__imp_GetCurrentThreadId
0x18003315d  lea     rcx, [rsp+278h+Buffer]
0x180033162  mov     r9, rdi; unsigned __int16 *
0x180033165  mov     [rsp+278h+var_240], rcx
0x18003316a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180033171  mov     dword ptr [rsp+278h+Arguments], ebp
0x180033175  mov     rdx, rsi; unsigned __int16 *
0x180033178  mov     [rsp+278h+nSize], eax
0x18003317c  mov     rcx, r14; this
0x18003317f  mov     eax, [rbx+44h]
0x180033182  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180033186  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003318b  cmp     [rbx+18h], r15
0x18003318f  jnz     short loc_1800331A1
0x180033191  cmp     [rbx+48h], r15
0x180033195  jnz     short loc_1800331A1
0x180033197  cmp     [rbx+30h], r15
0x18003319b  jz      loc_180033231
0x1800331a1  lea     r8, asc_18003F3F8; "    "
0x1800331a8  mov     rdx, rsi; unsigned __int16 *
0x1800331ab  mov     rcx, rax; this
0x1800331ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800331b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800331b7  test    r9, r9
0x1800331ba  jz      short loc_1800331CE
0x1800331bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800331c3  mov     rdx, rsi; unsigned __int16 *
0x1800331c6  mov     rcx, rax; this
0x1800331c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800331ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800331d2  test    r9, r9
0x1800331d5  jz      short loc_1800331E9
0x1800331d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800331de  mov     rdx, rsi; unsigned __int16 *
0x1800331e1  mov     rcx, rax; this
0x1800331e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800331e9  mov     rcx, [rbx+28h]
0x1800331ed  mov     rdx, rsi; unsigned __int16 *
0x1800331f0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800331f4  test    rcx, rcx
0x1800331f7  jz      short loc_18003320F
0x1800331f9  mov     [rsp+278h+lpBuffer], rcx
0x1800331fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180033205  mov     rcx, rax; this
0x180033208  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003320d  jmp     short loc_180033231
0x18003320f  mov     rcx, rax; this
0x180033212  test    r9, r9
0x180033215  jz      short loc_180033225
0x180033217  lea     r8, aHs; "[%hs]\n"
0x18003321e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180033223  jmp     short loc_180033231
0x180033225  lea     r8, asc_18003F470; "\n"
0x18003322c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180033231  xor     eax, eax
0x180033233  mov     rcx, [rsp+278h+var_38]
0x18003323b  xor     rcx, rsp; StackCookie
0x18003323e  call    __security_check_cookie
0x180033243  mov     rbx, [rsp+278h+arg_18]
0x18003324b  add     rsp, 250h
0x180033252  pop     r15
0x180033254  pop     r14
0x180033256  pop     rdi
0x180033257  pop     rsi
0x180033258  pop     rbp
0x180033259  retn
```
