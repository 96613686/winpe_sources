# CDLPFileFilterClipboardPlugin::QuerySessionData(void)

- ea: `0x140040ba0`
- end: `0x140040d2f`
- name: `?QuerySessionData@CDLPFileFilterClipboardPlugin@@IEAAXXZ`
- size: `399`
- prototype: `void __fastcall(CDLPFileFilterClipboardPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140040804`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140014d64`
- `0x14002e4b8`
- `0x14002e590`
- `0x140040194`
- `0x1400402d4`
- `0x140040ba0`
- `0x140040ebc`
- `0x140040ee4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040ccf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140040bb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140040bb0`
- `WTSAPI32!WTSFreeMemory` at `0x140040cc7`
- `WTSAPI32!WTSFreeMemory` at `0x140040cc7`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140040bfa`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140040bfa`

## pseudocode

```c
void __fastcall CDLPFileFilterClipboardPlugin::QuerySessionData(CDLPFileFilterClipboardPlugin *this)
{
  _QWORD *v2; // rdi
  _WORD *v3; // rdx
  char *v4; // r14
  _WORD *v5; // rcx
  LPWSTR v6; // rbx
  DWORD v7; // esi
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  DWORD LastError; // ebx
  unsigned int v14; // eax
  _BYTE v15[56]; // [rsp+30h] [rbp-38h] BYREF
  DWORD pBytesReturned; // [rsp+70h] [rbp+8h] BYREF
  LPWSTR ppBuffer; // [rsp+78h] [rbp+10h] BYREF

  *((_DWORD *)this + 8) = GetCurrentProcessId();
  v2 = (_QWORD *)((char *)this + 40);
  v3 = (_WORD *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 6) = v3;
  v4 = (char *)this + 72;
  *v3 = 0;
  v5 = (_WORD *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 10) = v5;
  *v5 = 0;
  ppBuffer = 0;
  pBytesReturned = 0;
  if ( WTSQuerySessionInformationW(0, 0xFFFFFFFF, WTSClientInfo, &ppBuffer, &pBytesReturned) )
  {
    v6 = ppBuffer;
    v7 = pBytesReturned;
    if ( ppBuffer && pBytesReturned >= 0x900 )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
        v2,
        ppBuffer + 21);
      if ( *v2 != v2[1] )
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          v2,
          L"\\",
          1);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(v2, v6);
      v9 = CDLPFileFilterClipboardPlugin::ConvertAddress2String(v8, v15, *((unsigned int *)v6 + 292), v6 + 586);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        v4,
        v9);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v15);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, CurrentThreadActivityIdPrefix, v6, v7);
    }
    WTSFreeMemory(ppBuffer);
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        &WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids,
        v14,
        LastError);
    }
  }
}

```

## disassembly

```asm
0x140040ba0  mov     [rsp+arg_10], rbx
0x140040ba5  push    rsi
0x140040ba6  push    rdi
0x140040ba7  push    r14
0x140040ba9  sub     rsp, 50h
0x140040bad  mov     rbx, rcx
0x140040bb0  call    cs:__imp_GetCurrentProcessId
0x140040bb6  mov     [rbx+20h], eax
0x140040bb9  lea     rdi, [rbx+28h]
0x140040bbd  mov     rdx, [rdi]
0x140040bc0  mov     r8d, 17h; WTSInfoClass
0x140040bc6  xor     eax, eax
0x140040bc8  mov     [rdi+8], rdx
0x140040bcc  lea     r14, [rbx+48h]
0x140040bd0  lea     r9, [rsp+68h+ppBuffer]; ppBuffer
0x140040bd5  mov     [rdx], ax
0x140040bd8  or      edx, 0FFFFFFFFh; SessionId
0x140040bdb  mov     rcx, [r14]
0x140040bde  mov     [r14+8], rcx
0x140040be2  mov     [rcx], ax
0x140040be5  xor     ecx, ecx; hServer
0x140040be7  mov     [rsp+68h+ppBuffer], rax
0x140040bec  mov     [rsp+68h+arg_0], eax
0x140040bf0  lea     rax, [rsp+68h+arg_0]
0x140040bf5  mov     [rsp+68h+pBytesReturned], rax; pBytesReturned
0x140040bfa  call    cs:__imp_WTSQuerySessionInformationW
0x140040c00  test    eax, eax
0x140040c02  jz      loc_140040CCF
0x140040c08  mov     rbx, [rsp+68h+ppBuffer]
0x140040c0d  mov     esi, [rsp+68h+arg_0]
0x140040c11  test    rbx, rbx
0x140040c14  jz      short loc_140040C82
0x140040c16  cmp     esi, 900h
0x140040c1c  jb      short loc_140040C82
0x140040c1e  lea     rdx, [rbx+2Ah]
0x140040c22  mov     rcx, rdi
0x140040c25  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x140040c2a  mov     rax, [rdi+8]
0x140040c2e  cmp     [rdi], rax
0x140040c31  jz      short loc_140040C48
0x140040c33  mov     r8d, 1
0x140040c39  lea     rdx, asc_140070908; "\\"
0x140040c40  mov     rcx, rdi
0x140040c43  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x140040c48  mov     rdx, rbx
0x140040c4b  mov     rcx, rdi
0x140040c4e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x140040c53  mov     r8d, [rbx+490h]
0x140040c5a  lea     r9, [rbx+494h]
0x140040c61  lea     rdx, [rsp+68h+var_38]
0x140040c66  call    ?ConvertAddress2String@CDLPFileFilterClipboardPlugin@@IEAA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KQEAG@Z; CDLPFileFilterClipboardPlugin::ConvertAddress2String(ulong,ushort * const)
0x140040c6b  mov     rdx, rax
0x140040c6e  mov     rcx, r14
0x140040c71  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x140040c76  lea     rcx, [rsp+68h+var_38]
0x140040c7b  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x140040c80  jmp     short loc_140040CC2
0x140040c82  mov     rax, cs:WPP_GLOBAL_Control
0x140040c89  lea     rdx, WPP_GLOBAL_Control
0x140040c90  cmp     rax, rdx
0x140040c93  jz      short loc_140040CC2
0x140040c95  test    byte ptr [rax+1Ch], 1
0x140040c99  jz      short loc_140040CC2
0x140040c9b  cmp     byte ptr [rax+19h], 2
0x140040c9f  jb      short loc_140040CC2
0x140040ca1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140040ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x140040cad  mov     r9d, eax
0x140040cb0  mov     [rsp+68h+var_40], esi
0x140040cb4  mov     [rsp+68h+pBytesReturned], rbx
0x140040cb9  mov     rcx, [rcx+10h]
0x140040cbd  call    WPP_SF_Dqd
0x140040cc2  mov     rcx, [rsp+68h+ppBuffer]; pMemory
0x140040cc7  call    cs:__imp_WTSFreeMemory
0x140040ccd  jmp     short loc_140040D1E
0x140040ccf  call    cs:__imp_GetLastError
0x140040cd5  mov     ebx, eax
0x140040cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140040cde  lea     rdx, WPP_GLOBAL_Control
0x140040ce5  cmp     rcx, rdx
0x140040ce8  jz      short loc_140040D1E
0x140040cea  test    byte ptr [rcx+1Ch], 1
0x140040cee  jz      short loc_140040D1E
0x140040cf0  cmp     byte ptr [rcx+19h], 2
0x140040cf4  jb      short loc_140040D1E
0x140040cf6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140040cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140040d02  lea     r8, WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids
0x140040d09  mov     edx, 19h
0x140040d0e  mov     dword ptr [rsp+68h+pBytesReturned], ebx
0x140040d12  mov     r9d, eax
0x140040d15  mov     rcx, [rcx+10h]
0x140040d19  call    WPP_SF_Dd
0x140040d1e  mov     rbx, [rsp+68h+arg_10]
0x140040d26  add     rsp, 50h
0x140040d2a  pop     r14
0x140040d2c  pop     rdi
0x140040d2d  pop     rsi
0x140040d2e  retn
```
