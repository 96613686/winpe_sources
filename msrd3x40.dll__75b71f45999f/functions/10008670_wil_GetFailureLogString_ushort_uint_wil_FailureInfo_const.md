# wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)

- ea: `0x10008670`
- end: `0x100088fc`
- name: `?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z`
- size: `652`
- prototype: `int __stdcall(wil *__hidden this, unsigned __int16 *, unsigned int, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x10009540`
- `0x10009850`
- `0x1000dcc0`
- `0x1000e820`

## callees

- `0x100085f0`
- `0x10008670`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f180`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x100087aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x100087aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10008819`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10008819`

## pseudocode

```c
int __userpurge wil::GetFailureLogString@<eax>(
        int a1@<edx>,
        wchar_t *a2@<ecx>,
        wil *this,
        unsigned __int16 *a4,
        unsigned int a5,
        const struct wil::FailureInfo *a6)
{
  void (__thiscall *v7)(_DWORD, wil *, wchar_t *, int); // ebx
  const char *v8; // ebx
  const unsigned __int16 *v9; // edx
  unsigned __int16 *v10; // edi
  wchar_t *v11; // eax
  const unsigned __int16 *v12; // ecx
  DWORD CurrentThreadId; // eax
  wchar_t *v14; // eax
  wchar_t *v15; // eax
  const unsigned __int16 *v17; // [esp-8h] [ebp-238h]
  int v18; // [esp-4h] [ebp-234h]
  const unsigned __int16 *v19; // [esp+0h] [ebp-230h]
  const unsigned __int16 *v20; // [esp+0h] [ebp-230h]
  DWORD v22; // [esp+18h] [ebp-218h]
  unsigned __int16 *v24; // [esp+1Ch] [ebp-214h]
  WCHAR Buffer[256]; // [esp+20h] [ebp-210h] BYREF

  if ( a1 )
  {
    if ( a2 )
    {
      v7 = (void (__thiscall *)(_DWORD, wil *, wchar_t *, int))g_pfnResultLoggingCallback;
      *a2 = 0;
      if ( !v7 || !wil::details::g_resultMessageCallbackSet || (v7(v7, this, a2, a1), !*a2) )
      {
        v8 = (const char *)&Args;
        switch ( *(_DWORD *)this )
        {
          case 0:
            v8 = "Exception";
            break;
          case 1:
            v8 = "ReturnHr";
            if ( (*((_BYTE *)this + 4) & 8) != 0 )
              v8 = "ReturnNt";
            break;
          case 2:
            v8 = "LogHr";
            if ( (*((_BYTE *)this + 4) & 8) != 0 )
              v8 = "LogNt";
            break;
          case 3:
            v8 = "FailFast";
            break;
          default:
            break;
        }
        memset(Buffer, 0, sizeof(Buffer));
        if ( (*((_BYTE *)this + 4) & 8) != 0 )
        {
          v22 = *((_DWORD *)this + 3);
          if ( wil::details::g_pfnFormatNtStatusMsg )
            wil::details::g_pfnFormatNtStatusMsg(*((_DWORD *)this + 3), Buffer, 256u);
        }
        else
        {
          v22 = *((_DWORD *)this + 2);
          FormatMessageW(0x1200u, 0, v22, 0x400u, Buffer, 0x100u, 0);
        }
        v9 = (const unsigned __int16 *)*((_DWORD *)this + 9);
        v10 = &a2[a1];
        v18 = *((_DWORD *)this + 20);
        v17 = (const unsigned __int16 *)*((_DWORD *)this + 19);
        if ( v9 )
          v11 = wil::details::LogStringPrintf(
                  a2,
                  v10,
                  (wchar_t *)L"%hs(%u)\\%hs!%p: ",
                  v9,
                  *((_DWORD *)this + 10),
                  v17,
                  v18);
        else
          v11 = wil::details::LogStringPrintf(a2, v10, (wchar_t *)L"%hs!%p: ", v17, v18);
        v12 = (const unsigned __int16 *)*((_DWORD *)this + 21);
        v24 = v11;
        if ( v12 )
          v24 = wil::details::LogStringPrintf(v11, v10, (wchar_t *)L"(caller: %p) ", v12);
        CurrentThreadId = GetCurrentThreadId();
        v14 = wil::details::LogStringPrintf(
                v24,
                v10,
                (wchar_t *)L"%hs(%d) tid(%x) %08X %ws",
                (const unsigned __int16 *)v8,
                *((_DWORD *)this + 11),
                CurrentThreadId,
                v22,
                Buffer);
        if ( *((_DWORD *)this + 5) || *((_DWORD *)this + 12) || *((_DWORD *)this + 8) )
        {
          v15 = wil::details::LogStringPrintf(v14, v10, (wchar_t *)L"    ", v19);
          if ( *((_DWORD *)this + 5) )
            v15 = wil::details::LogStringPrintf(
                    v15,
                    v10,
                    (wchar_t *)L"Msg:[%ws] ",
                    *((const unsigned __int16 **)this + 5));
          if ( *((_DWORD *)this + 12) )
            v15 = wil::details::LogStringPrintf(
                    v15,
                    v10,
                    (wchar_t *)L"CallContext:[%hs] ",
                    *((const unsigned __int16 **)this + 12));
          if ( *((_DWORD *)this + 7) )
          {
            wil::details::LogStringPrintf(
              v15,
              v10,
              (wchar_t *)L"[%hs(%hs)]\n",
              *((const unsigned __int16 **)this + 8),
              *((_DWORD *)this + 7));
          }
          else if ( *((_DWORD *)this + 8) )
          {
            wil::details::LogStringPrintf(v15, v10, (wchar_t *)L"[%hs]\n", *((const unsigned __int16 **)this + 8));
          }
          else
          {
            wil::details::LogStringPrintf(v15, v10, (wchar_t *)L"\n", v20);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10008670  mov     edi, edi
0x10008672  push    ebp
0x10008673  mov     ebp, esp
0x10008675  push    0FFFFFFFFh
0x10008677  push    offset ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z_SEH
0x1000867c  mov     eax, large fs:0
0x10008682  push    eax
0x10008683  sub     esp, 214h
0x10008689  mov     eax, ___security_cookie
0x1000868e  xor     eax, ebp
0x10008690  mov     [ebp+var_10], eax
0x10008693  push    ebx
0x10008694  push    esi
0x10008695  push    edi
0x10008696  push    eax; Args
0x10008697  lea     eax, [ebp+var_C]
0x1000869a  mov     large fs:0, eax
0x100086a0  mov     eax, edx
0x100086a2  mov     [ebp+var_220], eax
0x100086a8  mov     edi, ecx
0x100086aa  mov     [ebp+var_214], edi
0x100086b0  mov     esi, [ebp+this]
0x100086b3  test    eax, eax
0x100086b5  jz      loc_100088DC
0x100086bb  test    edi, edi
0x100086bd  jz      loc_100088DC
0x100086c3  mov     ebx, _g_pfnResultLoggingCallback
0x100086c9  xor     ecx, ecx
0x100086cb  mov     [edi], cx
0x100086ce  test    ebx, ebx
0x100086d0  jz      short loc_100086F1
0x100086d2  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, cl; bool wil::details::g_resultMessageCallbackSet
0x100086d8  jz      short loc_100086F1
0x100086da  push    eax
0x100086db  push    edi; unsigned int
0x100086dc  push    esi; void *
0x100086dd  mov     ecx, ebx
0x100086df  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100086e5  call    ebx ; _g_pfnResultLoggingCallback
0x100086e7  cmp     word ptr [edi], 0
0x100086eb  jnz     loc_100088DC
0x100086f1  mov     eax, [esi]
0x100086f3  mov     ebx, offset Args
0x100086f8  cmp     eax, 3; switch 4 cases
0x100086fb  ja      short def_100086FD; jumptable 100086FD default case
0x100086fd  jmp     ds:jpt_100086FD[eax*4]; switch jump
0x10008704  mov     ebx, offset aException; jumptable 100086FD case 0
0x10008709  jmp     short def_100086FD; jumptable 100086FD default case
0x1000870b  test    byte ptr [esi+4], 8; jumptable 100086FD case 1
0x1000870f  mov     ebx, offset aReturnhr; "ReturnHr"
0x10008714  mov     eax, offset aReturnnt; "ReturnNt"
0x10008719  cmovnz  ebx, eax
0x1000871c  jmp     short def_100086FD; jumptable 100086FD default case
0x1000871e  test    byte ptr [esi+4], 8; jumptable 100086FD case 2
0x10008722  mov     ebx, offset aLoghr; "LogHr"
0x10008727  mov     eax, offset aLognt; "LogNt"
0x1000872c  cmovnz  ebx, eax
0x1000872f  jmp     short def_100086FD; jumptable 100086FD default case
0x10008731  mov     ebx, offset aFailfast; jumptable 100086FD case 3
0x10008736  push    200h; jumptable 100086FD default case
0x1000873b  lea     eax, [ebp+Buffer]
0x10008741  push    0; Val
0x10008743  push    eax; void *
0x10008744  call    _memset
0x10008749  add     esp, 0Ch
0x1000874c  test    byte ptr [esi+4], 8
0x10008750  jz      short loc_10008786
0x10008752  mov     ecx, ?g_pfnFormatNtStatusMsg@details@wil@@3P6GXJPAGK@ZA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x10008758  mov     eax, [esi+0Ch]
0x1000875b  mov     [ebp+var_218], eax
0x10008761  mov     [ebp+var_21C], ecx
0x10008767  test    ecx, ecx
0x10008769  jz      short loc_100087B0
0x1000876b  push    100h
0x10008770  lea     edx, [ebp+Buffer]
0x10008776  push    edx; unsigned int
0x10008777  push    eax; void *
0x10008778  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000877e  call    [ebp+var_21C]
0x10008784  jmp     short loc_100087B0
0x10008786  mov     eax, [esi+8]
0x10008789  lea     ecx, [ebp+Buffer]
0x1000878f  push    0; Arguments
0x10008791  push    100h; nSize
0x10008796  push    ecx; lpBuffer
0x10008797  push    400h; dwLanguageId
0x1000879c  push    eax; dwMessageId
0x1000879d  push    0; lpSource
0x1000879f  push    1200h; dwFlags
0x100087a4  mov     [ebp+var_218], eax
0x100087aa  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x100087b0  mov     eax, [ebp+var_220]
0x100087b6  mov     edx, [esi+24h]
0x100087b9  mov     ecx, [esi+4Ch]
0x100087bc  lea     edi, [edi+eax*2]
0x100087bf  mov     eax, [esi+50h]
0x100087c2  push    eax
0x100087c3  push    ecx; Args
0x100087c4  test    edx, edx
0x100087c6  jz      short loc_100087E2
0x100087c8  push    dword ptr [esi+28h]
0x100087cb  push    edx; Args
0x100087cc  push    offset aHsUHsP; "%hs(%u)\\%hs!%p: "
0x100087d1  push    edi; unsigned __int16 *
0x100087d2  push    [ebp+var_214]; Buffer
0x100087d8  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x100087dd  add     esp, 1Ch
0x100087e0  jmp     short loc_100087F6
0x100087e2  push    offset aHsP; "%hs!%p: "
0x100087e7  push    edi; unsigned __int16 *
0x100087e8  push    [ebp+var_214]; Buffer
0x100087ee  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x100087f3  add     esp, 14h
0x100087f6  mov     ecx, [esi+54h]
0x100087f9  mov     [ebp+var_214], eax
0x100087ff  test    ecx, ecx
0x10008801  jz      short loc_10008819
0x10008803  push    ecx; Args
0x10008804  push    offset aCallerP; "(caller: %p) "
0x10008809  push    edi; unsigned __int16 *
0x1000880a  push    eax; Buffer
0x1000880b  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10008810  add     esp, 10h
0x10008813  mov     [ebp+var_214], eax
0x10008819  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000881f  lea     ecx, [ebp+Buffer]
0x10008825  push    ecx
0x10008826  push    [ebp+var_218]
0x1000882c  push    eax
0x1000882d  push    dword ptr [esi+2Ch]
0x10008830  push    ebx; Args
0x10008831  push    offset aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x10008836  push    edi; unsigned __int16 *
0x10008837  push    [ebp+var_214]; Buffer
0x1000883d  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10008842  add     esp, 20h
0x10008845  cmp     dword ptr [esi+14h], 0
0x10008849  jnz     short loc_1000885B
0x1000884b  cmp     dword ptr [esi+30h], 0
0x1000884f  jnz     short loc_1000885B
0x10008851  cmp     dword ptr [esi+20h], 0
0x10008855  jz      loc_100088DC
0x1000885b  push    offset asc_1000329C; "    "
0x10008860  push    edi; unsigned __int16 *
0x10008861  push    eax; Buffer
0x10008862  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10008867  mov     ecx, [esi+14h]
0x1000886a  add     esp, 0Ch
0x1000886d  test    ecx, ecx
0x1000886f  jz      short loc_10008881
0x10008871  push    ecx; Args
0x10008872  push    offset aMsgWs; "Msg:[%ws] "
0x10008877  push    edi; unsigned __int16 *
0x10008878  push    eax; Buffer
0x10008879  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1000887e  add     esp, 10h
0x10008881  mov     ecx, [esi+30h]
0x10008884  test    ecx, ecx
0x10008886  jz      short loc_10008898
0x10008888  push    ecx; Args
0x10008889  push    offset aCallcontextHs; "CallContext:[%hs] "
0x1000888e  push    edi; unsigned __int16 *
0x1000888f  push    eax; Buffer
0x10008890  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x10008895  add     esp, 10h
0x10008898  mov     ecx, [esi+1Ch]
0x1000889b  test    ecx, ecx
0x1000889d  jz      short loc_100088B4
0x1000889f  push    ecx
0x100088a0  push    dword ptr [esi+20h]; Args
0x100088a3  push    offset aHsHs; "[%hs(%hs)]\n"
0x100088a8  push    edi; unsigned __int16 *
0x100088a9  push    eax; Buffer
0x100088aa  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x100088af  add     esp, 14h
0x100088b2  jmp     short loc_100088DC
0x100088b4  mov     ecx, [esi+20h]
0x100088b7  test    ecx, ecx
0x100088b9  jz      short loc_100088CD
0x100088bb  push    ecx; Args
0x100088bc  push    offset aHs; "[%hs]\n"
0x100088c1  push    edi; unsigned __int16 *
0x100088c2  push    eax; Buffer
0x100088c3  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x100088c8  add     esp, 10h
0x100088cb  jmp     short loc_100088DC
0x100088cd  push    offset asc_10003310; "\n"
0x100088d2  push    edi; unsigned __int16 *
0x100088d3  push    eax; Buffer
0x100088d4  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x100088d9  add     esp, 0Ch
0x100088dc  xor     eax, eax
0x100088de  mov     ecx, [ebp+var_C]
0x100088e1  mov     large fs:0, ecx
0x100088e8  pop     ecx
0x100088e9  pop     edi
0x100088ea  pop     esi
0x100088eb  pop     ebx
0x100088ec  mov     ecx, [ebp+var_10]
0x100088ef  xor     ecx, ebp; StackCookie
0x100088f1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100088f6  mov     esp, ebp
0x100088f8  pop     ebp
0x100088f9  retn    4
0x1005f4e0  nop
0x1005f4e1  nop
0x1005f4e2  mov     edx, [esp-4+arg_4]
0x1005f4e6  lea     eax, [edx+0Ch]
0x1005f4e9  mov     ecx, [edx-224h]
0x1005f4ef  xor     ecx, eax; StackCookie
0x1005f4f1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f4f6  mov     ecx, [edx-4]
0x1005f4f9  xor     ecx, eax; StackCookie
0x1005f4fb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f500  mov     eax, offset stru_10062AB0
0x1005f505  jmp     ___CxxFrameHandler3
```
