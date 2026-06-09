# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005ed4`
- end: `0x18000618a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003ad4`
- `0x180003d54`
- `0x180006908`
- `0x180008ae0`
- `0x18000f210`
- `0x18003beb1`
- `0x18003bfe5`

## callees

- `0x180005ed4`
- `0x180006c08`
- `0x18003b96a`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006087`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006087`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006006`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006006`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
          v7 = (const char *)&qword_1800420B8;
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
0x180005ed4  mov     [rsp+arg_18], rbx
0x180005ed9  push    rbp
0x180005eda  push    rsi
0x180005edb  push    rdi
0x180005edc  push    r14
0x180005ede  push    r15
0x180005ee0  sub     rsp, 250h
0x180005ee7  mov     rax, cs:__security_cookie
0x180005eee  xor     rax, rsp
0x180005ef1  mov     [rsp+278h+var_38], rax
0x180005ef9  mov     rbx, r8
0x180005efc  mov     rsi, rdx
0x180005eff  mov     r14, rcx
0x180005f02  xor     r15d, r15d
0x180005f05  test    rdx, rdx
0x180005f08  jz      loc_180006161
0x180005f0e  test    rcx, rcx
0x180005f11  jz      loc_180006161
0x180005f17  mov     [rcx], r15w
0x180005f1b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005f22  test    rax, rax
0x180005f25  jz      short loc_180005F48
0x180005f27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005f2e  jz      short loc_180005F48
0x180005f30  mov     r8, rdx
0x180005f33  mov     rdx, rcx
0x180005f36  mov     rcx, rbx
0x180005f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f3e  cmp     [r14], r15w
0x180005f42  jnz     loc_180006161
0x180005f48  mov     ecx, [rbx]
0x180005f4a  mov     bpl, 8
0x180005f4d  test    ecx, ecx
0x180005f4f  jz      short loc_180005F9A
0x180005f51  sub     ecx, 1
0x180005f54  jz      short loc_180005F82
0x180005f56  sub     ecx, 1
0x180005f59  jz      short loc_180005F72
0x180005f5b  cmp     ecx, 1
0x180005f5e  jz      short loc_180005F69
0x180005f60  lea     rdi, qword_1800420B8
0x180005f67  jmp     short loc_180005FA1
0x180005f69  lea     rdi, aFailfast; "FailFast"
0x180005f70  jmp     short loc_180005FA1
0x180005f72  lea     rax, aLoghr; "LogHr"
0x180005f79  lea     rdi, aLognt; "LogNt"
0x180005f80  jmp     short loc_180005F90
0x180005f82  lea     rax, aReturnhr; "ReturnHr"
0x180005f89  lea     rdi, aReturnnt; "ReturnNt"
0x180005f90  test    [rbx+4], bpl
0x180005f94  cmovz   rdi, rax
0x180005f98  jmp     short loc_180005FA1
0x180005f9a  lea     rdi, aException; "Exception"
0x180005fa1  xor     edx, edx; Val
0x180005fa3  mov     r8d, 200h; Size
0x180005fa9  lea     rcx, [rsp+278h+Buffer]; void *
0x180005fae  call    memset_0
0x180005fb3  test    [rbx+4], bpl
0x180005fb7  jz      short loc_180005FDC
0x180005fb9  mov     ebp, [rbx+0Ch]
0x180005fbc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005fc3  test    rax, rax
0x180005fc6  jz      short loc_18000600C
0x180005fc8  mov     r8d, 100h
0x180005fce  lea     rdx, [rsp+278h+Buffer]
0x180005fd3  mov     ecx, ebp
0x180005fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fda  jmp     short loc_18000600C
0x180005fdc  mov     ebp, [rbx+8]
0x180005fdf  mov     [rsp+278h+Arguments], r15; Arguments
0x180005fe4  mov     [rsp+278h+nSize], 100h; nSize
0x180005fec  lea     rax, [rsp+278h+Buffer]
0x180005ff1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005ff6  mov     r9d, 400h; dwLanguageId
0x180005ffc  mov     r8d, ebp; dwMessageId
0x180005fff  xor     edx, edx; lpSource
0x180006001  mov     ecx, 1200h; dwFlags
0x180006006  call    cs:__imp_FormatMessageW
0x18000600c  lea     rsi, [r14+rsi*2]
0x180006010  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006014  mov     rax, [rbx+88h]
0x18000601b  mov     rcx, [rbx+80h]
0x180006022  mov     rdx, rsi; unsigned __int16 *
0x180006025  test    r9, r9
0x180006028  jz      short loc_18000604C
0x18000602a  mov     [rsp+278h+Arguments], rax
0x18000602f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006034  mov     eax, [rbx+40h]
0x180006037  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000603b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006042  mov     rcx, r14; this
0x180006045  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000604a  jmp     short loc_180006063
0x18000604c  mov     [rsp+278h+lpBuffer], rax
0x180006051  mov     r9, rcx; unsigned __int16 *
0x180006054  lea     r8, aHsP; "%hs!%p: "
0x18000605b  mov     rcx, r14; this
0x18000605e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006063  mov     r14, rax
0x180006066  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000606d  test    r9, r9
0x180006070  jz      short loc_180006087
0x180006072  lea     r8, aCallerP; "(caller: %p) "
0x180006079  mov     rdx, rsi; unsigned __int16 *
0x18000607c  mov     rcx, rax; this
0x18000607f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006084  mov     r14, rax
0x180006087  call    cs:__imp_GetCurrentThreadId
0x18000608d  lea     rcx, [rsp+278h+Buffer]
0x180006092  mov     [rsp+278h+var_240], rcx
0x180006097  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000609b  mov     [rsp+278h+nSize], eax
0x18000609f  mov     eax, [rbx+44h]
0x1800060a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800060a6  mov     r9, rdi; unsigned __int16 *
0x1800060a9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800060b0  mov     rdx, rsi; unsigned __int16 *
0x1800060b3  mov     rcx, r14; this
0x1800060b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800060bb  cmp     [rbx+18h], r15
0x1800060bf  jnz     short loc_1800060D1
0x1800060c1  cmp     [rbx+48h], r15
0x1800060c5  jnz     short loc_1800060D1
0x1800060c7  cmp     [rbx+30h], r15
0x1800060cb  jz      loc_180006161
0x1800060d1  lea     r8, asc_1800421A8; "    "
0x1800060d8  mov     rdx, rsi; unsigned __int16 *
0x1800060db  mov     rcx, rax; this
0x1800060de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800060e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800060e7  test    r9, r9
0x1800060ea  jz      short loc_1800060FE
0x1800060ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800060f3  mov     rdx, rsi; unsigned __int16 *
0x1800060f6  mov     rcx, rax; this
0x1800060f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800060fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006102  test    r9, r9
0x180006105  jz      short loc_180006119
0x180006107  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000610e  mov     rdx, rsi; unsigned __int16 *
0x180006111  mov     rcx, rax; this
0x180006114  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006119  mov     rcx, [rbx+28h]
0x18000611d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006121  mov     rdx, rsi; unsigned __int16 *
0x180006124  test    rcx, rcx
0x180006127  jz      short loc_18000613F
0x180006129  mov     [rsp+278h+lpBuffer], rcx
0x18000612e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006135  mov     rcx, rax; this
0x180006138  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000613d  jmp     short loc_180006161
0x18000613f  mov     rcx, rax; this
0x180006142  test    r9, r9
0x180006145  jz      short loc_180006155
0x180006147  lea     r8, aHs; "[%hs]\n"
0x18000614e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006153  jmp     short loc_180006161
0x180006155  lea     r8, asc_180042220; "\n"
0x18000615c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006161  xor     eax, eax
0x180006163  mov     rcx, [rsp+278h+var_38]
0x18000616b  xor     rcx, rsp; StackCookie
0x18000616e  call    __security_check_cookie
0x180006173  mov     rbx, [rsp+278h+arg_18]
0x18000617b  add     rsp, 250h
0x180006182  pop     r15
0x180006184  pop     r14
0x180006186  pop     rdi
0x180006187  pop     rsi
0x180006188  pop     rbp
0x180006189  retn
```
