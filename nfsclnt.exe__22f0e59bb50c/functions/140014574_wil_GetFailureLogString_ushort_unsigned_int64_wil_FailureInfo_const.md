# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140014574`
- end: `0x14001482a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140012660`
- `0x1400128c8`
- `0x140014ed0`

## callees

- `0x140014574`
- `0x1400151d0`
- `0x14001830e`
- `0x140018350`
- `0x140019010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140014727`
- `KERNEL32!GetCurrentThreadId` at `0x140014727`
- `KERNEL32!FormatMessageW` at `0x1400146a6`
- `KERNEL32!FormatMessageW` at `0x1400146a6`

## pseudocode

```c
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
          v8 = (const char *)&word_14001C69E;
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
0x140014574  mov     [rsp+arg_18], rbx
0x140014579  push    rbp
0x14001457a  push    rsi
0x14001457b  push    rdi
0x14001457c  push    r14
0x14001457e  push    r15
0x140014580  sub     rsp, 250h
0x140014587  mov     rax, cs:__security_cookie
0x14001458e  xor     rax, rsp
0x140014591  mov     [rsp+278h+var_38], rax
0x140014599  xor     r15d, r15d
0x14001459c  mov     rbx, r8
0x14001459f  mov     rsi, rdx
0x1400145a2  mov     r14, rcx
0x1400145a5  test    rdx, rdx
0x1400145a8  jz      loc_140014801
0x1400145ae  test    rcx, rcx
0x1400145b1  jz      loc_140014801
0x1400145b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400145be  mov     [rcx], r15w
0x1400145c2  test    rax, rax
0x1400145c5  jz      short loc_1400145E8
0x1400145c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400145ce  jz      short loc_1400145E8
0x1400145d0  mov     r8, rdx
0x1400145d3  mov     rdx, rcx
0x1400145d6  mov     rcx, rbx
0x1400145d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400145de  cmp     [r14], r15w
0x1400145e2  jnz     loc_140014801
0x1400145e8  mov     ecx, [rbx]
0x1400145ea  mov     bpl, 8
0x1400145ed  test    ecx, ecx
0x1400145ef  jz      short loc_14001463A
0x1400145f1  sub     ecx, 1
0x1400145f4  jz      short loc_140014622
0x1400145f6  sub     ecx, 1
0x1400145f9  jz      short loc_140014612
0x1400145fb  cmp     ecx, 1
0x1400145fe  jz      short loc_140014609
0x140014600  lea     rdi, word_14001C69E
0x140014607  jmp     short loc_140014641
0x140014609  lea     rdi, aFailfast; "FailFast"
0x140014610  jmp     short loc_140014641
0x140014612  lea     rax, aLoghr; "LogHr"
0x140014619  lea     rdi, aLognt; "LogNt"
0x140014620  jmp     short loc_140014630
0x140014622  lea     rax, aReturnhr; "ReturnHr"
0x140014629  lea     rdi, aReturnnt; "ReturnNt"
0x140014630  test    [rbx+4], bpl
0x140014634  cmovz   rdi, rax
0x140014638  jmp     short loc_140014641
0x14001463a  lea     rdi, aException; "Exception"
0x140014641  xor     edx, edx; Val
0x140014643  lea     rcx, [rsp+278h+Buffer]; void *
0x140014648  mov     r8d, 200h; Size
0x14001464e  call    memset_0
0x140014653  test    [rbx+4], bpl
0x140014657  jz      short loc_14001467C
0x140014659  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140014660  mov     ebp, [rbx+0Ch]
0x140014663  test    rax, rax
0x140014666  jz      short loc_1400146AC
0x140014668  mov     r8d, 100h
0x14001466e  lea     rdx, [rsp+278h+Buffer]
0x140014673  mov     ecx, ebp
0x140014675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001467a  jmp     short loc_1400146AC
0x14001467c  mov     ebp, [rbx+8]
0x14001467f  lea     rax, [rsp+278h+Buffer]
0x140014684  mov     [rsp+278h+Arguments], r15; Arguments
0x140014689  mov     r8d, ebp; dwMessageId
0x14001468c  mov     [rsp+278h+nSize], 100h; nSize
0x140014694  mov     r9d, 400h; dwLanguageId
0x14001469a  xor     edx, edx; lpSource
0x14001469c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400146a1  mov     ecx, 1200h; dwFlags
0x1400146a6  call    cs:__imp_FormatMessageW
0x1400146ac  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400146b0  lea     rsi, [r14+rsi*2]
0x1400146b4  mov     rax, [rbx+88h]
0x1400146bb  mov     rdx, rsi; unsigned __int16 *
0x1400146be  mov     rcx, [rbx+80h]
0x1400146c5  test    r9, r9
0x1400146c8  jz      short loc_1400146EC
0x1400146ca  mov     [rsp+278h+Arguments], rax
0x1400146cf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400146d6  mov     eax, [rbx+40h]
0x1400146d9  mov     qword ptr [rsp+278h+nSize], rcx
0x1400146de  mov     rcx, r14; this
0x1400146e1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400146e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400146ea  jmp     short loc_140014703
0x1400146ec  mov     r9, rcx; unsigned __int16 *
0x1400146ef  mov     [rsp+278h+lpBuffer], rax
0x1400146f4  mov     rcx, r14; this
0x1400146f7  lea     r8, aHsP; "%hs!%p: "
0x1400146fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140014703  mov     r9, [rbx+90h]; unsigned __int16 *
0x14001470a  mov     r14, rax
0x14001470d  test    r9, r9
0x140014710  jz      short loc_140014727
0x140014712  lea     r8, aCallerP; "(caller: %p) "
0x140014719  mov     rdx, rsi; unsigned __int16 *
0x14001471c  mov     rcx, rax; this
0x14001471f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140014724  mov     r14, rax
0x140014727  call    cs:__imp_GetCurrentThreadId
0x14001472d  lea     rcx, [rsp+278h+Buffer]
0x140014732  mov     r9, rdi; unsigned __int16 *
0x140014735  mov     [rsp+278h+var_240], rcx
0x14001473a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140014741  mov     dword ptr [rsp+278h+Arguments], ebp
0x140014745  mov     rdx, rsi; unsigned __int16 *
0x140014748  mov     [rsp+278h+nSize], eax
0x14001474c  mov     rcx, r14; this
0x14001474f  mov     eax, [rbx+44h]
0x140014752  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140014756  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001475b  cmp     [rbx+18h], r15
0x14001475f  jnz     short loc_140014771
0x140014761  cmp     [rbx+48h], r15
0x140014765  jnz     short loc_140014771
0x140014767  cmp     [rbx+30h], r15
0x14001476b  jz      loc_140014801
0x140014771  lea     r8, asc_14001CA38; "    "
0x140014778  mov     rdx, rsi; unsigned __int16 *
0x14001477b  mov     rcx, rax; this
0x14001477e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140014783  mov     r9, [rbx+18h]; unsigned __int16 *
0x140014787  test    r9, r9
0x14001478a  jz      short loc_14001479E
0x14001478c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140014793  mov     rdx, rsi; unsigned __int16 *
0x140014796  mov     rcx, rax; this
0x140014799  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001479e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400147a2  test    r9, r9
0x1400147a5  jz      short loc_1400147B9
0x1400147a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400147ae  mov     rdx, rsi; unsigned __int16 *
0x1400147b1  mov     rcx, rax; this
0x1400147b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400147b9  mov     rcx, [rbx+28h]
0x1400147bd  mov     rdx, rsi; unsigned __int16 *
0x1400147c0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400147c4  test    rcx, rcx
0x1400147c7  jz      short loc_1400147DF
0x1400147c9  mov     [rsp+278h+lpBuffer], rcx
0x1400147ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400147d5  mov     rcx, rax; this
0x1400147d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400147dd  jmp     short loc_140014801
0x1400147df  mov     rcx, rax; this
0x1400147e2  test    r9, r9
0x1400147e5  jz      short loc_1400147F5
0x1400147e7  lea     r8, aHs; "[%hs]\n"
0x1400147ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400147f3  jmp     short loc_140014801
0x1400147f5  lea     r8, asc_14001CAB0; "\n"
0x1400147fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140014801  xor     eax, eax
0x140014803  mov     rcx, [rsp+278h+var_38]
0x14001480b  xor     rcx, rsp; StackCookie
0x14001480e  call    __security_check_cookie
0x140014813  mov     rbx, [rsp+278h+arg_18]
0x14001481b  add     rsp, 250h
0x140014822  pop     r15
0x140014824  pop     r14
0x140014826  pop     rdi
0x140014827  pop     rsi
0x140014828  pop     rbp
0x140014829  retn
```
