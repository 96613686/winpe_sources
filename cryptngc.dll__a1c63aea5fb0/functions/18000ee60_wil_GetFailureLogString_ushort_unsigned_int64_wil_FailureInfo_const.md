# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000ee60`
- end: `0x18000f112`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `690`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18001b090`
- `0x1800307d8`
- `0x180031a30`
- `0x180031fa0`

## callees

- `0x18000ee60`
- `0x18000f120`
- `0x18002e850`
- `0x180046ce0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f015`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f015`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ef94`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ef94`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  __int64 result; // rax
  const char *v8; // r14
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  wil::details *v15; // rdi
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

  result = 0;
  if ( a2 && this )
  {
    *(_WORD *)this = 0;
    if ( !g_pfnResultLoggingCallback
      || !wil::details::g_resultMessageCallbackSet
      || (g_pfnResultLoggingCallback(a3, this, a2), !*(_WORD *)this) )
    {
      if ( *(_DWORD *)a3 )
      {
        switch ( *(_DWORD *)a3 )
        {
          case 1:
            v8 = "ReturnNt";
            if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
              v8 = "ReturnHr";
            break;
          case 2:
            v8 = "LogNt";
            if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
              v8 = "LogHr";
            break;
          case 3:
            v8 = "FailFast";
            break;
          default:
            v8 = (const char *)&qword_180054030;
            break;
        }
      }
      else
      {
        v8 = "Exception";
      }
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
                              (const unsigned __int16 *)v8,
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
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ee60  push    rbx
0x18000ee62  push    rbp
0x18000ee63  push    rsi
0x18000ee64  push    rdi
0x18000ee65  push    r14
0x18000ee67  sub     rsp, 250h
0x18000ee6e  mov     rax, cs:__security_cookie
0x18000ee75  xor     rax, rsp
0x18000ee78  mov     [rsp+278h+var_38], rax
0x18000ee80  mov     rbx, r8
0x18000ee83  mov     rsi, rdx
0x18000ee86  mov     rdi, rcx
0x18000ee89  xor     eax, eax
0x18000ee8b  test    rdx, rdx
0x18000ee8e  jz      loc_18000F0F4
0x18000ee94  test    rcx, rcx
0x18000ee97  jz      loc_18000F0F4
0x18000ee9d  mov     [rcx], ax
0x18000eea0  mov     rax, cs:g_pfnResultLoggingCallback
0x18000eea7  test    rax, rax
0x18000eeaa  jz      short loc_18000EECD
0x18000eeac  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18000eeb3  jz      short loc_18000EECD
0x18000eeb5  mov     r8, rdx
0x18000eeb8  mov     rdx, rcx
0x18000eebb  mov     rcx, rbx
0x18000eebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eec3  cmp     word ptr [rdi], 0
0x18000eec7  jnz     loc_18000F0F2
0x18000eecd  mov     ecx, [rbx]
0x18000eecf  test    ecx, ecx
0x18000eed1  jz      short loc_18000EF24
0x18000eed3  sub     ecx, 1
0x18000eed6  jz      short loc_18000EF0C
0x18000eed8  sub     ecx, 1
0x18000eedb  jz      short loc_18000EEF4
0x18000eedd  cmp     ecx, 1
0x18000eee0  jz      short loc_18000EEEB
0x18000eee2  lea     r14, qword_180054030
0x18000eee9  jmp     short loc_18000EF2B
0x18000eeeb  lea     r14, aFailfast; "FailFast"
0x18000eef2  jmp     short loc_18000EF2B
0x18000eef4  test    byte ptr [rbx+4], 8
0x18000eef8  lea     rax, aLoghr; "LogHr"
0x18000eeff  lea     r14, aLognt; "LogNt"
0x18000ef06  cmovz   r14, rax
0x18000ef0a  jmp     short loc_18000EF2B
0x18000ef0c  test    byte ptr [rbx+4], 8
0x18000ef10  lea     rax, aReturnhr; "ReturnHr"
0x18000ef17  lea     r14, aReturnnt; "ReturnNt"
0x18000ef1e  cmovz   r14, rax
0x18000ef22  jmp     short loc_18000EF2B
0x18000ef24  lea     r14, aException; "Exception"
0x18000ef2b  xor     edx, edx; Val
0x18000ef2d  mov     r8d, 200h; Size
0x18000ef33  lea     rcx, [rsp+278h+Buffer]; void *
0x18000ef38  call    memset_0
0x18000ef3d  test    byte ptr [rbx+4], 8
0x18000ef41  jz      short loc_18000EF66
0x18000ef43  mov     ebp, [rbx+0Ch]
0x18000ef46  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000ef4d  test    rax, rax
0x18000ef50  jz      short loc_18000EF9A
0x18000ef52  mov     r8d, 100h
0x18000ef58  lea     rdx, [rsp+278h+Buffer]
0x18000ef5d  mov     ecx, ebp
0x18000ef5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef64  jmp     short loc_18000EF9A
0x18000ef66  mov     ebp, [rbx+8]
0x18000ef69  mov     [rsp+278h+Arguments], 0; Arguments
0x18000ef72  mov     [rsp+278h+nSize], 100h; nSize
0x18000ef7a  lea     rax, [rsp+278h+Buffer]
0x18000ef7f  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000ef84  mov     r9d, 400h; dwLanguageId
0x18000ef8a  mov     r8d, ebp; dwMessageId
0x18000ef8d  xor     edx, edx; lpSource
0x18000ef8f  mov     ecx, 1200h; dwFlags
0x18000ef94  call    cs:__imp_FormatMessageW
0x18000ef9a  lea     rsi, [rdi+rsi*2]
0x18000ef9e  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000efa2  mov     rax, [rbx+88h]
0x18000efa9  mov     rcx, [rbx+80h]
0x18000efb0  mov     rdx, rsi; unsigned __int16 *
0x18000efb3  test    r9, r9
0x18000efb6  jz      short loc_18000EFDA
0x18000efb8  mov     [rsp+278h+Arguments], rax
0x18000efbd  mov     qword ptr [rsp+278h+nSize], rcx
0x18000efc2  mov     eax, [rbx+40h]
0x18000efc5  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000efc9  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000efd0  mov     rcx, rdi; this
0x18000efd3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000efd8  jmp     short loc_18000EFF1
0x18000efda  mov     [rsp+278h+lpBuffer], rax
0x18000efdf  mov     r9, rcx; unsigned __int16 *
0x18000efe2  lea     r8, aHsP; "%hs!%p: "
0x18000efe9  mov     rcx, rdi; this
0x18000efec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000eff1  mov     rdi, rax
0x18000eff4  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000effb  test    r9, r9
0x18000effe  jz      short loc_18000F015
0x18000f000  lea     r8, aCallerP; "(caller: %p) "
0x18000f007  mov     rdx, rsi; unsigned __int16 *
0x18000f00a  mov     rcx, rax; this
0x18000f00d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f012  mov     rdi, rax
0x18000f015  call    cs:__imp_GetCurrentThreadId
0x18000f01b  lea     rcx, [rsp+278h+Buffer]
0x18000f020  mov     [rsp+278h+var_240], rcx
0x18000f025  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000f029  mov     [rsp+278h+nSize], eax
0x18000f02d  mov     eax, [rbx+44h]
0x18000f030  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f034  mov     r9, r14; unsigned __int16 *
0x18000f037  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000f03e  mov     rdx, rsi; unsigned __int16 *
0x18000f041  mov     rcx, rdi; this
0x18000f044  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f049  cmp     qword ptr [rbx+18h], 0
0x18000f04e  jnz     short loc_18000F062
0x18000f050  cmp     qword ptr [rbx+48h], 0
0x18000f055  jnz     short loc_18000F062
0x18000f057  cmp     qword ptr [rbx+30h], 0
0x18000f05c  jz      loc_18000F0F2
0x18000f062  lea     r8, asc_180056B08; "    "
0x18000f069  mov     rdx, rsi; unsigned __int16 *
0x18000f06c  mov     rcx, rax; this
0x18000f06f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f074  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000f078  test    r9, r9
0x18000f07b  jz      short loc_18000F08F
0x18000f07d  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000f084  mov     rdx, rsi; unsigned __int16 *
0x18000f087  mov     rcx, rax; this
0x18000f08a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f08f  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000f093  test    r9, r9
0x18000f096  jz      short loc_18000F0AA
0x18000f098  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000f09f  mov     rdx, rsi; unsigned __int16 *
0x18000f0a2  mov     rcx, rax; this
0x18000f0a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f0aa  mov     rcx, [rbx+28h]
0x18000f0ae  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000f0b2  mov     rdx, rsi; unsigned __int16 *
0x18000f0b5  test    rcx, rcx
0x18000f0b8  jz      short loc_18000F0D0
0x18000f0ba  mov     [rsp+278h+lpBuffer], rcx
0x18000f0bf  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000f0c6  mov     rcx, rax; this
0x18000f0c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f0ce  jmp     short loc_18000F0F2
0x18000f0d0  mov     rcx, rax; this
0x18000f0d3  test    r9, r9
0x18000f0d6  jz      short loc_18000F0E6
0x18000f0d8  lea     r8, aHs; "[%hs]\n"
0x18000f0df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f0e4  jmp     short loc_18000F0F2
0x18000f0e6  lea     r8, asc_180056B80; "\n"
0x18000f0ed  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f0f2  xor     eax, eax
0x18000f0f4  mov     rcx, [rsp+278h+var_38]
0x18000f0fc  xor     rcx, rsp; StackCookie
0x18000f0ff  call    __security_check_cookie
0x18000f104  add     rsp, 250h
0x18000f10b  pop     r14
0x18000f10d  pop     rdi
0x18000f10e  pop     rsi
0x18000f10f  pop     rbp
0x18000f110  pop     rbx
0x18000f111  retn
```
