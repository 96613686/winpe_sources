# wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)

- ea: `0x10006a5c`
- end: `0x10006cc6`
- name: `?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z`
- size: `618`
- prototype: `int(wil *__hidden this, unsigned __int16 *, unsigned int, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x100071c8`
- `0x1000f26f`
- `0x1000f7f1`

## callees

- `0x10006a17`
- `0x10006a5c`
- `0x1002d510`
- `0x1003aba0`
- `0x1003b5e4`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x10006b7e`
- `KERNEL32!FormatMessageW` at `0x10006b7e`
- `KERNEL32!GetCurrentThreadId` at `0x10006bed`
- `KERNEL32!GetCurrentThreadId` at `0x10006bed`

## pseudocode

```c
int __userpurge wil::GetFailureLogString@<eax>(
        int a1@<edx>,
        wil::details *a2@<ecx>,
        const unsigned __int16 *a3@<ebx>,
        wil *this,
        unsigned __int16 *a5,
        unsigned int a6,
        const struct wil::FailureInfo *a7)
{
  CD3DSurfaceAllocator *v8; // ebx
  const char *v9; // ebx
  const char *v10; // eax
  unsigned __int16 *v11; // edi
  unsigned __int16 *v12; // eax
  DWORD CurrentThreadId; // eax
  wil::details *v14; // eax
  unsigned __int16 *v15; // eax
  const unsigned __int16 *v17; // [esp-Ch] [ebp-228h]
  int v18; // [esp-8h] [ebp-224h]
  const unsigned __int16 *v20; // [esp-4h] [ebp-220h]
  DWORD v22; // [esp+10h] [ebp-20Ch]
  wil::details *v24; // [esp+14h] [ebp-208h]
  WCHAR Buffer[256]; // [esp+18h] [ebp-204h] BYREF

  if ( !a1 )
    return 0;
  if ( !a2 )
    return 0;
  v8 = g_pfnResultLoggingCallback;
  *(_WORD *)a2 = 0;
  if ( v8 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      ((void (__thiscall *)(CD3DSurfaceAllocator *, wil *, wil::details *, int))v8)(v8, this, a2, a1);
      if ( *(_WORD *)a2 )
        return 0;
    }
  }
  v9 = (const char *)&word_100032E6;
  if ( *(_DWORD *)this )
  {
    if ( *(_DWORD *)this == 1 )
    {
      v9 = "ReturnHr";
      v10 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)this != 2 )
      {
        if ( *(_DWORD *)this == 3 )
          v9 = "FailFast";
        goto LABEL_17;
      }
      v9 = "LogHr";
      v10 = "LogNt";
    }
    if ( (*((_BYTE *)this + 4) & 8) != 0 )
      v9 = v10;
    goto LABEL_17;
  }
  v9 = "Exception";
LABEL_17:
  memset(Buffer, 0, sizeof(Buffer));
  if ( (*((_BYTE *)this + 4) & 8) != 0 )
  {
    v22 = *((_DWORD *)this + 3);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      ((void (__stdcall *)(_DWORD, WCHAR *, int))wil::details::g_pfnFormatNtStatusMsg)(
        *((_DWORD *)this + 3),
        Buffer,
        256);
  }
  else
  {
    v22 = *((_DWORD *)this + 2);
    FormatMessageW(0x1200u, 0, v22, 0x400u, Buffer, 0x100u, 0);
  }
  v18 = *((_DWORD *)this + 20);
  v17 = (const unsigned __int16 *)*((_DWORD *)this + 19);
  v11 = (unsigned __int16 *)((char *)a2 + 2 * a1);
  if ( *((_DWORD *)this + 9) )
    v12 = wil::details::LogStringPrintf(
            a2,
            v11,
            L"%hs(%u)\\%hs!%p: ",
            *((const unsigned __int16 **)this + 9),
            *((_DWORD *)this + 10),
            v17,
            v18);
  else
    v12 = wil::details::LogStringPrintf(a2, v11, L"%hs!%p: ", v17, v18);
  v24 = (wil::details *)v12;
  if ( *((_DWORD *)this + 21) )
    v24 = (wil::details *)wil::details::LogStringPrintf(
                            (wil::details *)v12,
                            v11,
                            L"(caller: %p) ",
                            *((const unsigned __int16 **)this + 21));
  CurrentThreadId = GetCurrentThreadId();
  v14 = (wil::details *)wil::details::LogStringPrintf(
                          v24,
                          v11,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v9,
                          *((_DWORD *)this + 11),
                          CurrentThreadId,
                          v22,
                          Buffer);
  if ( *((_DWORD *)this + 5) || *((_DWORD *)this + 12) || *((_DWORD *)this + 8) )
  {
    v15 = wil::details::LogStringPrintf(v14, v11, L"    ", a3);
    if ( *((_DWORD *)this + 5) )
      v15 = wil::details::LogStringPrintf(
              (wil::details *)v15,
              v11,
              L"Msg:[%ws] ",
              *((const unsigned __int16 **)this + 5));
    if ( *((_DWORD *)this + 12) )
      v15 = wil::details::LogStringPrintf(
              (wil::details *)v15,
              v11,
              L"CallContext:[%hs] ",
              *((const unsigned __int16 **)this + 12));
    if ( *((_DWORD *)this + 7) )
    {
      wil::details::LogStringPrintf(
        (wil::details *)v15,
        v11,
        L"[%hs(%hs)]\n",
        *((const unsigned __int16 **)this + 8),
        *((_DWORD *)this + 7));
    }
    else if ( *((_DWORD *)this + 8) )
    {
      wil::details::LogStringPrintf((wil::details *)v15, v11, L"[%hs]\n", *((const unsigned __int16 **)this + 8));
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v15, v11, L"\n", v20);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10006a5c  mov     edi, edi
0x10006a5e  push    ebp
0x10006a5f  mov     ebp, esp
0x10006a61  sub     esp, 214h
0x10006a67  mov     eax, ___security_cookie
0x10006a6c  xor     eax, ebp
0x10006a6e  mov     [ebp+var_4], eax
0x10006a71  push    esi
0x10006a72  mov     esi, [ebp+this]
0x10006a75  mov     eax, edx
0x10006a77  mov     [ebp+var_214], eax
0x10006a7d  push    edi
0x10006a7e  mov     edi, ecx
0x10006a80  mov     [ebp+var_208], edi
0x10006a86  test    eax, eax
0x10006a88  jz      loc_10006CB4
0x10006a8e  test    edi, edi
0x10006a90  jz      loc_10006CB4
0x10006a96  push    ebx; unsigned __int16 *
0x10006a97  mov     ebx, _g_pfnResultLoggingCallback
0x10006a9d  xor     ecx, ecx
0x10006a9f  mov     [edi], cx
0x10006aa2  test    ebx, ebx
0x10006aa4  jz      short loc_10006AC6
0x10006aa6  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, cl; bool wil::details::g_resultMessageCallbackSet
0x10006aac  jz      short loc_10006AC6
0x10006aae  push    eax
0x10006aaf  push    edi
0x10006ab0  push    esi
0x10006ab1  mov     ecx, ebx; this
0x10006ab3  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10006ab9  call    ebx ; _g_pfnResultLoggingCallback
0x10006abb  xor     ecx, ecx
0x10006abd  cmp     [edi], cx
0x10006ac0  jnz     loc_10006CB3
0x10006ac6  mov     eax, [esi]
0x10006ac8  mov     ebx, offset word_100032E6
0x10006acd  sub     eax, ecx
0x10006acf  jz      short loc_10006B06
0x10006ad1  sub     eax, 1
0x10006ad4  jz      short loc_10006AF3
0x10006ad6  sub     eax, 1
0x10006ad9  jz      short loc_10006AE7
0x10006adb  sub     eax, 1
0x10006ade  jnz     short loc_10006B0B
0x10006ae0  mov     ebx, offset aFailfast; "FailFast"
0x10006ae5  jmp     short loc_10006B0B
0x10006ae7  mov     ebx, offset aLoghr; "LogHr"
0x10006aec  mov     eax, offset aLognt; "LogNt"
0x10006af1  jmp     short loc_10006AFD
0x10006af3  mov     ebx, offset aReturnhr; "ReturnHr"
0x10006af8  mov     eax, offset aReturnnt; "ReturnNt"
0x10006afd  test    byte ptr [esi+4], 8
0x10006b01  cmovnz  ebx, eax
0x10006b04  jmp     short loc_10006B0B
0x10006b06  mov     ebx, offset aException; "Exception"
0x10006b0b  push    200h; Size
0x10006b10  push    ecx; Val
0x10006b11  lea     eax, [ebp+Buffer]
0x10006b17  push    eax; void *
0x10006b18  call    _memset
0x10006b1d  add     esp, 0Ch
0x10006b20  test    byte ptr [esi+4], 8
0x10006b24  jz      short loc_10006B5A
0x10006b26  mov     ecx, ?g_pfnFormatNtStatusMsg@details@wil@@3P6GXJPAGK@ZA; this
0x10006b2c  mov     eax, [esi+0Ch]
0x10006b2f  mov     [ebp+var_20C], eax
0x10006b35  mov     [ebp+var_210], ecx
0x10006b3b  test    ecx, ecx
0x10006b3d  jz      short loc_10006B84
0x10006b3f  push    100h
0x10006b44  lea     edx, [ebp+Buffer]
0x10006b4a  push    edx
0x10006b4b  push    eax
0x10006b4c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10006b52  call    [ebp+var_210]
0x10006b58  jmp     short loc_10006B84
0x10006b5a  mov     eax, [esi+8]
0x10006b5d  lea     ecx, [ebp+Buffer]
0x10006b63  push    0; Arguments
0x10006b65  push    100h; nSize
0x10006b6a  push    ecx; lpBuffer
0x10006b6b  push    400h; dwLanguageId
0x10006b70  push    eax; dwMessageId
0x10006b71  push    0; lpSource
0x10006b73  push    1200h; dwFlags
0x10006b78  mov     [ebp+var_20C], eax
0x10006b7e  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x10006b84  cmp     dword ptr [esi+24h], 0
0x10006b88  mov     eax, [ebp+var_214]
0x10006b8e  push    dword ptr [esi+50h]
0x10006b91  push    dword ptr [esi+4Ch]; unsigned __int16 *
0x10006b94  lea     edi, [edi+eax*2]
0x10006b97  jz      short loc_10006BB5
0x10006b99  push    dword ptr [esi+28h]
0x10006b9c  push    dword ptr [esi+24h]; unsigned __int16 *
0x10006b9f  push    offset aHsUHsP; "%hs(%u)\\%hs!%p: "
0x10006ba4  push    edi; unsigned __int16 *
0x10006ba5  push    [ebp+var_208]; this
0x10006bab  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10006bb0  add     esp, 1Ch
0x10006bb3  jmp     short loc_10006BC9
0x10006bb5  push    offset aHsP; "%hs!%p: "
0x10006bba  push    edi; unsigned __int16 *
0x10006bbb  push    [ebp+var_208]; this
0x10006bc1  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10006bc6  add     esp, 14h
0x10006bc9  cmp     dword ptr [esi+54h], 0
0x10006bcd  mov     [ebp+var_208], eax
0x10006bd3  jz      short loc_10006BED
0x10006bd5  push    dword ptr [esi+54h]; unsigned __int16 *
0x10006bd8  push    offset aCallerP; "(caller: %p) "
0x10006bdd  push    edi; unsigned __int16 *
0x10006bde  push    eax; this
0x10006bdf  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10006be4  add     esp, 10h
0x10006be7  mov     [ebp+var_208], eax
0x10006bed  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10006bf3  lea     ecx, [ebp+Buffer]
0x10006bf9  push    ecx
0x10006bfa  push    [ebp+var_20C]
0x10006c00  push    eax
0x10006c01  push    dword ptr [esi+2Ch]
0x10006c04  push    ebx; unsigned __int16 *
0x10006c05  push    offset aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x10006c0a  push    edi; unsigned __int16 *
0x10006c0b  push    [ebp+var_208]; this
0x10006c11  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10006c16  xor     ecx, ecx
0x10006c18  add     esp, 20h
0x10006c1b  cmp     [esi+14h], ecx
0x10006c1e  jnz     short loc_10006C2E
0x10006c20  cmp     [esi+30h], ecx
0x10006c23  jnz     short loc_10006C2E
0x10006c25  cmp     [esi+20h], ecx
0x10006c28  jz      loc_10006CB3
0x10006c2e  push    offset asc_100033B0; "    "
0x10006c33  push    edi; unsigned __int16 *
0x10006c34  push    eax; this
0x10006c35  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10006c3a  add     esp, 0Ch
0x10006c3d  cmp     dword ptr [esi+14h], 0
0x10006c41  jz      short loc_10006C55
0x10006c43  push    dword ptr [esi+14h]; unsigned __int16 *
0x10006c46  push    offset aMsgWs; "Msg:[%ws] "
0x10006c4b  push    edi; unsigned __int16 *
0x10006c4c  push    eax; this
0x10006c4d  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10006c52  add     esp, 10h
0x10006c55  cmp     dword ptr [esi+30h], 0
0x10006c59  jz      short loc_10006C6D
0x10006c5b  push    dword ptr [esi+30h]; unsigned __int16 *
0x10006c5e  push    offset aCallcontextHs; "CallContext:[%hs] "
0x10006c63  push    edi; unsigned __int16 *
0x10006c64  push    eax; this
0x10006c65  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10006c6a  add     esp, 10h
0x10006c6d  cmp     dword ptr [esi+1Ch], 0
0x10006c71  jz      short loc_10006C8A
0x10006c73  push    dword ptr [esi+1Ch]
0x10006c76  push    dword ptr [esi+20h]; unsigned __int16 *
0x10006c79  push    offset aHsHs; "[%hs(%hs)]\n"
0x10006c7e  push    edi; unsigned __int16 *
0x10006c7f  push    eax; this
0x10006c80  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10006c85  add     esp, 14h
0x10006c88  jmp     short loc_10006CB3
0x10006c8a  cmp     dword ptr [esi+20h], 0
0x10006c8e  jz      short loc_10006CA4
0x10006c90  push    dword ptr [esi+20h]; unsigned __int16 *
0x10006c93  push    offset aHs; "[%hs]\n"
0x10006c98  push    edi; unsigned __int16 *
0x10006c99  push    eax; this
0x10006c9a  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10006c9f  add     esp, 10h
0x10006ca2  jmp     short loc_10006CB3
0x10006ca4  push    offset asc_10003424; "\n"
0x10006ca9  push    edi; unsigned __int16 *
0x10006caa  push    eax; this
0x10006cab  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10006cb0  add     esp, 0Ch
0x10006cb3  pop     ebx
0x10006cb4  mov     ecx, [ebp+var_4]
0x10006cb7  xor     eax, eax
0x10006cb9  pop     edi
0x10006cba  xor     ecx, ebp; StackCookie
0x10006cbc  pop     esi
0x10006cbd  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10006cc2  leave
0x10006cc3  retn    4
```
