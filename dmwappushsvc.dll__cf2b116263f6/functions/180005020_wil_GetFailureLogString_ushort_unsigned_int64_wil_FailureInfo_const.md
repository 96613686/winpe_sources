# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005020`
- end: `0x1800052d6`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180005ea0`
- `0x18000941c`

## callees

- `0x180001a70`
- `0x180002554`
- `0x180005020`
- `0x180005588`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051d3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005152`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005152`

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
          v7 = (const char *)&byte_180014871;
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
0x180005020  mov     [rsp+arg_18], rbx
0x180005025  push    rbp
0x180005026  push    rsi
0x180005027  push    rdi
0x180005028  push    r14
0x18000502a  push    r15
0x18000502c  sub     rsp, 250h
0x180005033  mov     rax, cs:__security_cookie
0x18000503a  xor     rax, rsp
0x18000503d  mov     [rsp+278h+var_38], rax
0x180005045  mov     rbx, r8
0x180005048  mov     rsi, rdx
0x18000504b  mov     r14, rcx
0x18000504e  xor     r15d, r15d
0x180005051  test    rdx, rdx
0x180005054  jz      loc_1800052AD
0x18000505a  test    rcx, rcx
0x18000505d  jz      loc_1800052AD
0x180005063  mov     [rcx], r15w
0x180005067  mov     rax, cs:g_pfnResultLoggingCallback
0x18000506e  test    rax, rax
0x180005071  jz      short loc_180005094
0x180005073  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000507a  jz      short loc_180005094
0x18000507c  mov     r8, rdx
0x18000507f  mov     rdx, rcx
0x180005082  mov     rcx, rbx
0x180005085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000508a  cmp     [r14], r15w
0x18000508e  jnz     loc_1800052AD
0x180005094  mov     ecx, [rbx]
0x180005096  mov     bpl, 8
0x180005099  test    ecx, ecx
0x18000509b  jz      short loc_1800050E6
0x18000509d  sub     ecx, 1
0x1800050a0  jz      short loc_1800050CE
0x1800050a2  sub     ecx, 1
0x1800050a5  jz      short loc_1800050BE
0x1800050a7  cmp     ecx, 1
0x1800050aa  jz      short loc_1800050B5
0x1800050ac  lea     rdi, byte_180014871
0x1800050b3  jmp     short loc_1800050ED
0x1800050b5  lea     rdi, aFailfast; "FailFast"
0x1800050bc  jmp     short loc_1800050ED
0x1800050be  lea     rax, aLoghr; "LogHr"
0x1800050c5  lea     rdi, aLognt; "LogNt"
0x1800050cc  jmp     short loc_1800050DC
0x1800050ce  lea     rax, aReturnhr; "ReturnHr"
0x1800050d5  lea     rdi, aReturnnt; "ReturnNt"
0x1800050dc  test    [rbx+4], bpl
0x1800050e0  cmovz   rdi, rax
0x1800050e4  jmp     short loc_1800050ED
0x1800050e6  lea     rdi, aException; "Exception"
0x1800050ed  xor     edx, edx; Val
0x1800050ef  mov     r8d, 200h; Size
0x1800050f5  lea     rcx, [rsp+278h+Buffer]; void *
0x1800050fa  call    memset_0
0x1800050ff  test    [rbx+4], bpl
0x180005103  jz      short loc_180005128
0x180005105  mov     ebp, [rbx+0Ch]
0x180005108  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000510f  test    rax, rax
0x180005112  jz      short loc_180005158
0x180005114  mov     r8d, 100h
0x18000511a  lea     rdx, [rsp+278h+Buffer]
0x18000511f  mov     ecx, ebp
0x180005121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005126  jmp     short loc_180005158
0x180005128  mov     ebp, [rbx+8]
0x18000512b  mov     [rsp+278h+Arguments], r15; Arguments
0x180005130  mov     [rsp+278h+nSize], 100h; nSize
0x180005138  lea     rax, [rsp+278h+Buffer]
0x18000513d  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005142  mov     r9d, 400h; dwLanguageId
0x180005148  mov     r8d, ebp; dwMessageId
0x18000514b  xor     edx, edx; lpSource
0x18000514d  mov     ecx, 1200h; dwFlags
0x180005152  call    cs:__imp_FormatMessageW
0x180005158  lea     rsi, [r14+rsi*2]
0x18000515c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005160  mov     rax, [rbx+88h]
0x180005167  mov     rcx, [rbx+80h]
0x18000516e  mov     rdx, rsi; unsigned __int16 *
0x180005171  test    r9, r9
0x180005174  jz      short loc_180005198
0x180005176  mov     [rsp+278h+Arguments], rax
0x18000517b  mov     qword ptr [rsp+278h+nSize], rcx
0x180005180  mov     eax, [rbx+40h]
0x180005183  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005187  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000518e  mov     rcx, r14; this
0x180005191  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005196  jmp     short loc_1800051AF
0x180005198  mov     [rsp+278h+lpBuffer], rax
0x18000519d  mov     r9, rcx; unsigned __int16 *
0x1800051a0  lea     r8, aHsP; "%hs!%p: "
0x1800051a7  mov     rcx, r14; this
0x1800051aa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051af  mov     r14, rax
0x1800051b2  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800051b9  test    r9, r9
0x1800051bc  jz      short loc_1800051D3
0x1800051be  lea     r8, aCallerP; "(caller: %p) "
0x1800051c5  mov     rdx, rsi; unsigned __int16 *
0x1800051c8  mov     rcx, rax; this
0x1800051cb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051d0  mov     r14, rax
0x1800051d3  call    cs:__imp_GetCurrentThreadId
0x1800051d9  lea     rcx, [rsp+278h+Buffer]
0x1800051de  mov     [rsp+278h+var_240], rcx
0x1800051e3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800051e7  mov     [rsp+278h+nSize], eax
0x1800051eb  mov     eax, [rbx+44h]
0x1800051ee  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800051f2  mov     r9, rdi; unsigned __int16 *
0x1800051f5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800051fc  mov     rdx, rsi; unsigned __int16 *
0x1800051ff  mov     rcx, r14; this
0x180005202  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005207  cmp     [rbx+18h], r15
0x18000520b  jnz     short loc_18000521D
0x18000520d  cmp     [rbx+48h], r15
0x180005211  jnz     short loc_18000521D
0x180005213  cmp     [rbx+30h], r15
0x180005217  jz      loc_1800052AD
0x18000521d  lea     r8, asc_180014738; "    "
0x180005224  mov     rdx, rsi; unsigned __int16 *
0x180005227  mov     rcx, rax; this
0x18000522a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000522f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005233  test    r9, r9
0x180005236  jz      short loc_18000524A
0x180005238  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000523f  mov     rdx, rsi; unsigned __int16 *
0x180005242  mov     rcx, rax; this
0x180005245  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000524a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000524e  test    r9, r9
0x180005251  jz      short loc_180005265
0x180005253  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000525a  mov     rdx, rsi; unsigned __int16 *
0x18000525d  mov     rcx, rax; this
0x180005260  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005265  mov     rcx, [rbx+28h]
0x180005269  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000526d  mov     rdx, rsi; unsigned __int16 *
0x180005270  test    rcx, rcx
0x180005273  jz      short loc_18000528B
0x180005275  mov     [rsp+278h+lpBuffer], rcx
0x18000527a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005281  mov     rcx, rax; this
0x180005284  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005289  jmp     short loc_1800052AD
0x18000528b  mov     rcx, rax; this
0x18000528e  test    r9, r9
0x180005291  jz      short loc_1800052A1
0x180005293  lea     r8, aHs; "[%hs]\n"
0x18000529a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000529f  jmp     short loc_1800052AD
0x1800052a1  lea     r8, asc_1800147B0; "\n"
0x1800052a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800052ad  xor     eax, eax
0x1800052af  mov     rcx, [rsp+278h+var_38]
0x1800052b7  xor     rcx, rsp; StackCookie
0x1800052ba  call    __security_check_cookie
0x1800052bf  mov     rbx, [rsp+278h+arg_18]
0x1800052c7  add     rsp, 250h
0x1800052ce  pop     r15
0x1800052d0  pop     r14
0x1800052d2  pop     rdi
0x1800052d3  pop     rsi
0x1800052d4  pop     rbp
0x1800052d5  retn
```
