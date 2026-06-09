# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400035e4`
- end: `0x1400038a7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140002504`
- `0x140002788`
- `0x140003fac`
- `0x1400058a0`

## callees

- `0x140001500`
- `0x14000215c`
- `0x1400035e4`
- `0x1400042c0`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000379d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000379d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003716`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003716`

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
          v7 = (const char *)&word_14000BB6A;
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
0x1400035e4  mov     [rsp+arg_18], rbx
0x1400035e9  push    rbp
0x1400035ea  push    rsi
0x1400035eb  push    rdi
0x1400035ec  push    r14
0x1400035ee  push    r15
0x1400035f0  sub     rsp, 250h
0x1400035f7  mov     rax, cs:__security_cookie
0x1400035fe  xor     rax, rsp
0x140003601  mov     [rsp+278h+var_38], rax
0x140003609  mov     rbx, r8
0x14000360c  mov     rsi, rdx
0x14000360f  mov     r14, rcx
0x140003612  xor     r15d, r15d
0x140003615  test    rdx, rdx
0x140003618  jz      loc_14000387D
0x14000361e  test    rcx, rcx
0x140003621  jz      loc_14000387D
0x140003627  mov     [rcx], r15w
0x14000362b  mov     rax, cs:g_pfnResultLoggingCallback
0x140003632  test    rax, rax
0x140003635  jz      short loc_140003658
0x140003637  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000363e  jz      short loc_140003658
0x140003640  mov     r8, rdx
0x140003643  mov     rdx, rcx
0x140003646  mov     rcx, rbx
0x140003649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000364e  cmp     [r14], r15w
0x140003652  jnz     loc_14000387D
0x140003658  mov     ecx, [rbx]
0x14000365a  mov     bpl, 8
0x14000365d  test    ecx, ecx
0x14000365f  jz      short loc_1400036AA
0x140003661  sub     ecx, 1
0x140003664  jz      short loc_140003692
0x140003666  sub     ecx, 1
0x140003669  jz      short loc_140003682
0x14000366b  cmp     ecx, 1
0x14000366e  jz      short loc_140003679
0x140003670  lea     rdi, word_14000BB6A
0x140003677  jmp     short loc_1400036B1
0x140003679  lea     rdi, aFailfast; "FailFast"
0x140003680  jmp     short loc_1400036B1
0x140003682  lea     rax, aLoghr; "LogHr"
0x140003689  lea     rdi, aLognt; "LogNt"
0x140003690  jmp     short loc_1400036A0
0x140003692  lea     rax, aReturnhr; "ReturnHr"
0x140003699  lea     rdi, aReturnnt; "ReturnNt"
0x1400036a0  test    [rbx+4], bpl
0x1400036a4  cmovz   rdi, rax
0x1400036a8  jmp     short loc_1400036B1
0x1400036aa  lea     rdi, aException; "Exception"
0x1400036b1  xor     edx, edx; Val
0x1400036b3  mov     r8d, 200h; Size
0x1400036b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400036be  call    memset_0
0x1400036c3  test    [rbx+4], bpl
0x1400036c7  jz      short loc_1400036EC
0x1400036c9  mov     ebp, [rbx+0Ch]
0x1400036cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400036d3  test    rax, rax
0x1400036d6  jz      short loc_140003722
0x1400036d8  mov     r8d, 100h
0x1400036de  lea     rdx, [rsp+278h+Buffer]
0x1400036e3  mov     ecx, ebp
0x1400036e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036ea  jmp     short loc_140003722
0x1400036ec  mov     ebp, [rbx+8]
0x1400036ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1400036f4  mov     [rsp+278h+nSize], 100h; nSize
0x1400036fc  lea     rax, [rsp+278h+Buffer]
0x140003701  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140003706  mov     r9d, 400h; dwLanguageId
0x14000370c  mov     r8d, ebp; dwMessageId
0x14000370f  xor     edx, edx; lpSource
0x140003711  mov     ecx, 1200h; dwFlags
0x140003716  call    cs:__imp_FormatMessageW
0x14000371d  nop     dword ptr [rax+rax+00h]
0x140003722  lea     rsi, [r14+rsi*2]
0x140003726  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000372a  mov     rax, [rbx+88h]
0x140003731  mov     rcx, [rbx+80h]
0x140003738  mov     rdx, rsi; unsigned __int16 *
0x14000373b  test    r9, r9
0x14000373e  jz      short loc_140003762
0x140003740  mov     [rsp+278h+Arguments], rax
0x140003745  mov     qword ptr [rsp+278h+nSize], rcx
0x14000374a  mov     eax, [rbx+40h]
0x14000374d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003751  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140003758  mov     rcx, r14; this
0x14000375b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003760  jmp     short loc_140003779
0x140003762  mov     [rsp+278h+lpBuffer], rax
0x140003767  mov     r9, rcx; unsigned __int16 *
0x14000376a  lea     r8, aHsP; "%hs!%p: "
0x140003771  mov     rcx, r14; this
0x140003774  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003779  mov     r14, rax
0x14000377c  mov     r9, [rbx+90h]; unsigned __int16 *
0x140003783  test    r9, r9
0x140003786  jz      short loc_14000379D
0x140003788  lea     r8, aCallerP; "(caller: %p) "
0x14000378f  mov     rdx, rsi; unsigned __int16 *
0x140003792  mov     rcx, rax; this
0x140003795  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000379a  mov     r14, rax
0x14000379d  call    cs:__imp_GetCurrentThreadId
0x1400037a4  nop     dword ptr [rax+rax+00h]
0x1400037a9  lea     rcx, [rsp+278h+Buffer]
0x1400037ae  mov     [rsp+278h+var_240], rcx
0x1400037b3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400037b7  mov     [rsp+278h+nSize], eax
0x1400037bb  mov     eax, [rbx+44h]
0x1400037be  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400037c2  mov     r9, rdi; unsigned __int16 *
0x1400037c5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400037cc  mov     rdx, rsi; unsigned __int16 *
0x1400037cf  mov     rcx, r14; this
0x1400037d2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400037d7  cmp     [rbx+18h], r15
0x1400037db  jnz     short loc_1400037ED
0x1400037dd  cmp     [rbx+48h], r15
0x1400037e1  jnz     short loc_1400037ED
0x1400037e3  cmp     [rbx+30h], r15
0x1400037e7  jz      loc_14000387D
0x1400037ed  lea     r8, asc_14000BC58; "    "
0x1400037f4  mov     rdx, rsi; unsigned __int16 *
0x1400037f7  mov     rcx, rax; this
0x1400037fa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400037ff  mov     r9, [rbx+18h]; unsigned __int16 *
0x140003803  test    r9, r9
0x140003806  jz      short loc_14000381A
0x140003808  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000380f  mov     rdx, rsi; unsigned __int16 *
0x140003812  mov     rcx, rax; this
0x140003815  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000381a  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000381e  test    r9, r9
0x140003821  jz      short loc_140003835
0x140003823  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000382a  mov     rdx, rsi; unsigned __int16 *
0x14000382d  mov     rcx, rax; this
0x140003830  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003835  mov     rcx, [rbx+28h]
0x140003839  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000383d  mov     rdx, rsi; unsigned __int16 *
0x140003840  test    rcx, rcx
0x140003843  jz      short loc_14000385B
0x140003845  mov     [rsp+278h+lpBuffer], rcx
0x14000384a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140003851  mov     rcx, rax; this
0x140003854  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003859  jmp     short loc_14000387D
0x14000385b  mov     rcx, rax; this
0x14000385e  test    r9, r9
0x140003861  jz      short loc_140003871
0x140003863  lea     r8, aHs; "[%hs]\n"
0x14000386a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000386f  jmp     short loc_14000387D
0x140003871  lea     r8, asc_14000BCD0; "\n"
0x140003878  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000387d  xor     eax, eax
0x14000387f  mov     rcx, [rsp+278h+var_38]
0x140003887  xor     rcx, rsp; StackCookie
0x14000388a  call    __security_check_cookie
0x14000388f  mov     rbx, [rsp+278h+arg_18]
0x140003897  add     rsp, 250h
0x14000389e  pop     r15
0x1400038a0  pop     r14
0x1400038a2  pop     rdi
0x1400038a3  pop     rsi
0x1400038a4  pop     rbp
0x1400038a5  retn
```
