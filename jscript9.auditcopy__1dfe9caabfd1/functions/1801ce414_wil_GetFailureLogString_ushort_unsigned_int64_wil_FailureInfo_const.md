# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1801ce414`
- end: `0x1801ce6ee`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `730`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1801cc7e0`
- `0x1801cf740`
- `0x1801cfe64`
- `0x1801d2d00`

## callees

- `0x1801cc26b`
- `0x1801ce414`
- `0x1801cfaa8`
- `0x1803481f0`
- `0x180364010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801ce5e4`
- `KERNEL32!GetCurrentThreadId` at `0x1801ce5e4`
- `KERNEL32!FormatMessageW` at `0x1801ce55d`
- `KERNEL32!FormatMessageW` at `0x1801ce55d`

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
  char *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r14
  const unsigned __int16 *v16; // r9
  unsigned __int16 *v17; // rax
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&dword_1803C23D4;
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
  v10 = (char *)this + 2 * (_QWORD)a2;
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
  v15 = v14;
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          (wil::details *)v15,
          v10,
          L"%hs(%d) tid(%x) %08X %ws",
          (const unsigned __int16 *)v7,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer,
          -2);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf((wil::details *)v17, v10, L"    ", v18);
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
0x1801ce414  mov     r11, rsp
0x1801ce417  mov     [r11+18h], r8
0x1801ce41b  mov     [r11+10h], rdx
0x1801ce41f  mov     [r11+8], rcx
0x1801ce423  push    rbp
0x1801ce424  push    rsi
0x1801ce425  push    rdi
0x1801ce426  push    r14
0x1801ce428  push    r15
0x1801ce42a  sub     rsp, 260h
0x1801ce431  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x1801ce43a  mov     [r11+20h], rbx
0x1801ce43e  mov     rax, cs:__security_cookie
0x1801ce445  xor     rax, rsp
0x1801ce448  mov     [rsp+288h+var_38], rax
0x1801ce450  mov     rbx, r8
0x1801ce453  mov     r14, rcx
0x1801ce456  mov     rsi, rdx
0x1801ce459  xor     r15d, r15d
0x1801ce45c  test    rdx, rdx
0x1801ce45f  jz      loc_1801CE6C4
0x1801ce465  test    rcx, rcx
0x1801ce468  jz      loc_1801CE6C4
0x1801ce46e  mov     [rcx], r15w
0x1801ce472  mov     rax, cs:g_pfnResultLoggingCallback
0x1801ce479  test    rax, rax
0x1801ce47c  jz      short loc_1801CE49F
0x1801ce47e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1801ce485  jz      short loc_1801CE49F
0x1801ce487  mov     r8, rdx
0x1801ce48a  mov     rdx, rcx
0x1801ce48d  mov     rcx, rbx
0x1801ce490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce495  cmp     [r14], r15w
0x1801ce499  jnz     loc_1801CE6C4
0x1801ce49f  mov     ecx, [rbx]
0x1801ce4a1  mov     bpl, 8
0x1801ce4a4  test    ecx, ecx
0x1801ce4a6  jz      short loc_1801CE4F1
0x1801ce4a8  sub     ecx, 1
0x1801ce4ab  jz      short loc_1801CE4D9
0x1801ce4ad  sub     ecx, 1
0x1801ce4b0  jz      short loc_1801CE4C9
0x1801ce4b2  cmp     ecx, 1
0x1801ce4b5  jz      short loc_1801CE4C0
0x1801ce4b7  lea     rdi, dword_1803C23D4
0x1801ce4be  jmp     short loc_1801CE4F8
0x1801ce4c0  lea     rdi, aFailfast; "FailFast"
0x1801ce4c7  jmp     short loc_1801CE4F8
0x1801ce4c9  lea     rax, aLoghr; "LogHr"
0x1801ce4d0  lea     rdi, aLognt; "LogNt"
0x1801ce4d7  jmp     short loc_1801CE4E7
0x1801ce4d9  lea     rax, aReturnhr; "ReturnHr"
0x1801ce4e0  lea     rdi, aReturnnt; "ReturnNt"
0x1801ce4e7  test    [rbx+4], bpl
0x1801ce4eb  cmovz   rdi, rax
0x1801ce4ef  jmp     short loc_1801CE4F8
0x1801ce4f1  lea     rdi, aException; "Exception"
0x1801ce4f8  xor     edx, edx; Val
0x1801ce4fa  mov     r8d, 200h; Size
0x1801ce500  lea     rcx, [rsp+288h+Buffer]; void *
0x1801ce505  call    memset_0
0x1801ce50a  test    [rbx+4], bpl
0x1801ce50e  jz      short loc_1801CE533
0x1801ce510  mov     ebp, [rbx+0Ch]
0x1801ce513  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1801ce51a  test    rax, rax
0x1801ce51d  jz      short loc_1801CE569
0x1801ce51f  mov     r8d, 100h
0x1801ce525  lea     rdx, [rsp+288h+Buffer]
0x1801ce52a  mov     ecx, ebp
0x1801ce52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce531  jmp     short loc_1801CE569
0x1801ce533  mov     ebp, [rbx+8]
0x1801ce536  mov     [rsp+288h+Arguments], r15; Arguments
0x1801ce53b  mov     [rsp+288h+nSize], 100h; nSize
0x1801ce543  lea     rax, [rsp+288h+Buffer]
0x1801ce548  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x1801ce54d  mov     r9d, 400h; dwLanguageId
0x1801ce553  mov     r8d, ebp; dwMessageId
0x1801ce556  xor     edx, edx; lpSource
0x1801ce558  mov     ecx, 1200h; dwFlags
0x1801ce55d  call    cs:__imp_FormatMessageW
0x1801ce564  nop     dword ptr [rax+rax+00h]
0x1801ce569  lea     rsi, [r14+rsi*2]
0x1801ce56d  mov     r9, [rbx+38h]; unsigned __int16 *
0x1801ce571  mov     rax, [rbx+88h]
0x1801ce578  mov     rcx, [rbx+80h]
0x1801ce57f  mov     rdx, rsi; unsigned __int16 *
0x1801ce582  test    r9, r9
0x1801ce585  jz      short loc_1801CE5A9
0x1801ce587  mov     [rsp+288h+Arguments], rax
0x1801ce58c  mov     qword ptr [rsp+288h+nSize], rcx
0x1801ce591  mov     eax, [rbx+40h]
0x1801ce594  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1801ce598  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1801ce59f  mov     rcx, r14; this
0x1801ce5a2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801ce5a7  jmp     short loc_1801CE5C0
0x1801ce5a9  mov     [rsp+288h+lpBuffer], rax
0x1801ce5ae  mov     r9, rcx; unsigned __int16 *
0x1801ce5b1  lea     r8, aHsP; "%hs!%p: "
0x1801ce5b8  mov     rcx, r14; this
0x1801ce5bb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801ce5c0  mov     r14, rax
0x1801ce5c3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1801ce5ca  test    r9, r9
0x1801ce5cd  jz      short loc_1801CE5E4
0x1801ce5cf  lea     r8, aCallerP; "(caller: %p) "
0x1801ce5d6  mov     rdx, rsi; unsigned __int16 *
0x1801ce5d9  mov     rcx, rax; this
0x1801ce5dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801ce5e1  mov     r14, rax
0x1801ce5e4  call    cs:__imp_GetCurrentThreadId
0x1801ce5eb  nop     dword ptr [rax+rax+00h]
0x1801ce5f0  lea     rcx, [rsp+288h+Buffer]
0x1801ce5f5  mov     [rsp+288h+var_250], rcx
0x1801ce5fa  mov     dword ptr [rsp+288h+Arguments], ebp
0x1801ce5fe  mov     [rsp+288h+nSize], eax
0x1801ce602  mov     eax, [rbx+44h]
0x1801ce605  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1801ce609  mov     r9, rdi; unsigned __int16 *
0x1801ce60c  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1801ce613  mov     rdx, rsi; unsigned __int16 *
0x1801ce616  mov     rcx, r14; this
0x1801ce619  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801ce61e  cmp     [rbx+18h], r15
0x1801ce622  jnz     short loc_1801CE634
0x1801ce624  cmp     [rbx+48h], r15
0x1801ce628  jnz     short loc_1801CE634
0x1801ce62a  cmp     [rbx+30h], r15
0x1801ce62e  jz      loc_1801CE6C4
0x1801ce634  lea     r8, asc_1803C24C0; "    "
0x1801ce63b  mov     rdx, rsi; unsigned __int16 *
0x1801ce63e  mov     rcx, rax; this
0x1801ce641  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801ce646  mov     r9, [rbx+18h]; unsigned __int16 *
0x1801ce64a  test    r9, r9
0x1801ce64d  jz      short loc_1801CE661
0x1801ce64f  lea     r8, aMsgWs; "Msg:[%ws] "
0x1801ce656  mov     rdx, rsi; unsigned __int16 *
0x1801ce659  mov     rcx, rax; this
0x1801ce65c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801ce661  mov     r9, [rbx+48h]; unsigned __int16 *
0x1801ce665  test    r9, r9
0x1801ce668  jz      short loc_1801CE67C
0x1801ce66a  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1801ce671  mov     rdx, rsi; unsigned __int16 *
0x1801ce674  mov     rcx, rax; this
0x1801ce677  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801ce67c  mov     rcx, [rbx+28h]
0x1801ce680  mov     r9, [rbx+30h]; unsigned __int16 *
0x1801ce684  mov     rdx, rsi; unsigned __int16 *
0x1801ce687  test    rcx, rcx
0x1801ce68a  jz      short loc_1801CE6A2
0x1801ce68c  mov     [rsp+288h+lpBuffer], rcx
0x1801ce691  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1801ce698  mov     rcx, rax; this
0x1801ce69b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801ce6a0  jmp     short loc_1801CE6C4
0x1801ce6a2  mov     rcx, rax; this
0x1801ce6a5  test    r9, r9
0x1801ce6a8  jz      short loc_1801CE6B8
0x1801ce6aa  lea     r8, aHs; "[%hs]\n"
0x1801ce6b1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801ce6b6  jmp     short loc_1801CE6C4
0x1801ce6b8  lea     r8, asc_1803C23D0; "\n"
0x1801ce6bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801ce6c4  xor     eax, eax
0x1801ce6c6  mov     rcx, [rsp+288h+var_38]
0x1801ce6ce  xor     rcx, rsp; StackCookie
0x1801ce6d1  call    __security_check_cookie
0x1801ce6d6  mov     rbx, [rsp+288h+arg_18]
0x1801ce6de  add     rsp, 260h
0x1801ce6e5  pop     r15
0x1801ce6e7  pop     r14
0x1801ce6e9  pop     rdi
0x1801ce6ea  pop     rsi
0x1801ce6eb  pop     rbp
0x1801ce6ec  retn
```
