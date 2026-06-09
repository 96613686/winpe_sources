# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005fa4`
- end: `0x18000625a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800044c0`
- `0x180004740`
- `0x1800049ec`
- `0x180008980`
- `0x18000b3d8`
- `0x180034378`
- `0x1800344ac`

## callees

- `0x180005fa4`
- `0x180006c8c`
- `0x180033e9a`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006157`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006157`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800060d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800060d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
          v7 = (const char *)&byte_18003A3A0;
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
0x180005fa4  mov     [rsp+arg_18], rbx
0x180005fa9  push    rbp
0x180005faa  push    rsi
0x180005fab  push    rdi
0x180005fac  push    r14
0x180005fae  push    r15
0x180005fb0  sub     rsp, 250h
0x180005fb7  mov     rax, cs:__security_cookie
0x180005fbe  xor     rax, rsp
0x180005fc1  mov     [rsp+278h+var_38], rax
0x180005fc9  mov     rbx, r8
0x180005fcc  mov     rsi, rdx
0x180005fcf  mov     r14, rcx
0x180005fd2  xor     r15d, r15d
0x180005fd5  test    rdx, rdx
0x180005fd8  jz      loc_180006231
0x180005fde  test    rcx, rcx
0x180005fe1  jz      loc_180006231
0x180005fe7  mov     [rcx], r15w
0x180005feb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ff2  test    rax, rax
0x180005ff5  jz      short loc_180006018
0x180005ff7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005ffe  jz      short loc_180006018
0x180006000  mov     r8, rdx
0x180006003  mov     rdx, rcx
0x180006006  mov     rcx, rbx
0x180006009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000600e  cmp     [r14], r15w
0x180006012  jnz     loc_180006231
0x180006018  mov     ecx, [rbx]
0x18000601a  mov     bpl, 8
0x18000601d  test    ecx, ecx
0x18000601f  jz      short loc_18000606A
0x180006021  sub     ecx, 1
0x180006024  jz      short loc_180006052
0x180006026  sub     ecx, 1
0x180006029  jz      short loc_180006042
0x18000602b  cmp     ecx, 1
0x18000602e  jz      short loc_180006039
0x180006030  lea     rdi, byte_18003A3A0
0x180006037  jmp     short loc_180006071
0x180006039  lea     rdi, aFailfast; "FailFast"
0x180006040  jmp     short loc_180006071
0x180006042  lea     rax, aLoghr; "LogHr"
0x180006049  lea     rdi, aLognt; "LogNt"
0x180006050  jmp     short loc_180006060
0x180006052  lea     rax, aReturnhr; "ReturnHr"
0x180006059  lea     rdi, aReturnnt; "ReturnNt"
0x180006060  test    [rbx+4], bpl
0x180006064  cmovz   rdi, rax
0x180006068  jmp     short loc_180006071
0x18000606a  lea     rdi, aException; "Exception"
0x180006071  xor     edx, edx; Val
0x180006073  mov     r8d, 200h; Size
0x180006079  lea     rcx, [rsp+278h+Buffer]; void *
0x18000607e  call    memset_0
0x180006083  test    [rbx+4], bpl
0x180006087  jz      short loc_1800060AC
0x180006089  mov     ebp, [rbx+0Ch]
0x18000608c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006093  test    rax, rax
0x180006096  jz      short loc_1800060DC
0x180006098  mov     r8d, 100h
0x18000609e  lea     rdx, [rsp+278h+Buffer]
0x1800060a3  mov     ecx, ebp
0x1800060a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060aa  jmp     short loc_1800060DC
0x1800060ac  mov     ebp, [rbx+8]
0x1800060af  mov     [rsp+278h+Arguments], r15; Arguments
0x1800060b4  mov     [rsp+278h+nSize], 100h; nSize
0x1800060bc  lea     rax, [rsp+278h+Buffer]
0x1800060c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800060c6  mov     r9d, 400h; dwLanguageId
0x1800060cc  mov     r8d, ebp; dwMessageId
0x1800060cf  xor     edx, edx; lpSource
0x1800060d1  mov     ecx, 1200h; dwFlags
0x1800060d6  call    cs:__imp_FormatMessageW
0x1800060dc  lea     rsi, [r14+rsi*2]
0x1800060e0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800060e4  mov     rax, [rbx+88h]
0x1800060eb  mov     rcx, [rbx+80h]
0x1800060f2  mov     rdx, rsi; unsigned __int16 *
0x1800060f5  test    r9, r9
0x1800060f8  jz      short loc_18000611C
0x1800060fa  mov     [rsp+278h+Arguments], rax
0x1800060ff  mov     qword ptr [rsp+278h+nSize], rcx
0x180006104  mov     eax, [rbx+40h]
0x180006107  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000610b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006112  mov     rcx, r14; this
0x180006115  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000611a  jmp     short loc_180006133
0x18000611c  mov     [rsp+278h+lpBuffer], rax
0x180006121  mov     r9, rcx; unsigned __int16 *
0x180006124  lea     r8, aHsP; "%hs!%p: "
0x18000612b  mov     rcx, r14; this
0x18000612e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006133  mov     r14, rax
0x180006136  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000613d  test    r9, r9
0x180006140  jz      short loc_180006157
0x180006142  lea     r8, aCallerP; "(caller: %p) "
0x180006149  mov     rdx, rsi; unsigned __int16 *
0x18000614c  mov     rcx, rax; this
0x18000614f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006154  mov     r14, rax
0x180006157  call    cs:__imp_GetCurrentThreadId
0x18000615d  lea     rcx, [rsp+278h+Buffer]
0x180006162  mov     [rsp+278h+var_240], rcx
0x180006167  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000616b  mov     [rsp+278h+nSize], eax
0x18000616f  mov     eax, [rbx+44h]
0x180006172  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006176  mov     r9, rdi; unsigned __int16 *
0x180006179  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006180  mov     rdx, rsi; unsigned __int16 *
0x180006183  mov     rcx, r14; this
0x180006186  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000618b  cmp     [rbx+18h], r15
0x18000618f  jnz     short loc_1800061A1
0x180006191  cmp     [rbx+48h], r15
0x180006195  jnz     short loc_1800061A1
0x180006197  cmp     [rbx+30h], r15
0x18000619b  jz      loc_180006231
0x1800061a1  lea     r8, asc_18003A490; "    "
0x1800061a8  mov     rdx, rsi; unsigned __int16 *
0x1800061ab  mov     rcx, rax; this
0x1800061ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800061b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800061b7  test    r9, r9
0x1800061ba  jz      short loc_1800061CE
0x1800061bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800061c3  mov     rdx, rsi; unsigned __int16 *
0x1800061c6  mov     rcx, rax; this
0x1800061c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800061ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800061d2  test    r9, r9
0x1800061d5  jz      short loc_1800061E9
0x1800061d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800061de  mov     rdx, rsi; unsigned __int16 *
0x1800061e1  mov     rcx, rax; this
0x1800061e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800061e9  mov     rcx, [rbx+28h]
0x1800061ed  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800061f1  mov     rdx, rsi; unsigned __int16 *
0x1800061f4  test    rcx, rcx
0x1800061f7  jz      short loc_18000620F
0x1800061f9  mov     [rsp+278h+lpBuffer], rcx
0x1800061fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006205  mov     rcx, rax; this
0x180006208  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000620d  jmp     short loc_180006231
0x18000620f  mov     rcx, rax; this
0x180006212  test    r9, r9
0x180006215  jz      short loc_180006225
0x180006217  lea     r8, aHs; "[%hs]\n"
0x18000621e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006223  jmp     short loc_180006231
0x180006225  lea     r8, asc_18003A508; "\n"
0x18000622c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006231  xor     eax, eax
0x180006233  mov     rcx, [rsp+278h+var_38]
0x18000623b  xor     rcx, rsp; StackCookie
0x18000623e  call    __security_check_cookie
0x180006243  mov     rbx, [rsp+278h+arg_18]
0x18000624b  add     rsp, 250h
0x180006252  pop     r15
0x180006254  pop     r14
0x180006256  pop     rdi
0x180006257  pop     rsi
0x180006258  pop     rbp
0x180006259  retn
```
