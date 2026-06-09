# BitsHelper::SetCallbackExeOnJob(IBackgroundCopyJob5 *,_GUID const &,ushort const *)

- ea: `0x140011804`
- end: `0x1400119af`
- name: `?SetCallbackExeOnJob@BitsHelper@@AEAAJPEAUIBackgroundCopyJob5@@AEBU_GUID@@PEBG@Z`
- size: `427`
- prototype: `__int64 __fastcall(BitsHelper *this, struct IBackgroundCopyJob5 *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140010ce8`

## callees

- `0x140002f40`
- `0x14000a4bc`
- `0x14000cbc8`
- `0x14000cc54`
- `0x140011804`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14001183e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14001183e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001187e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001187e`

## string_xrefs

- `0x14001185a`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x1400118a6`: `-DatabaseComplete`

## pseudocode

```c
__int64 __fastcall BitsHelper::SetCallbackExeOnJob(
        BitsHelper *this,
        struct IBackgroundCopyJob5 *a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4)
{
  __int64 v6; // rdx
  int v7; // ebx
  const wchar_t *v9; // [rsp+20h] [rbp-B18h]
  OLECHAR sz[104]; // [rsp+30h] [rbp-B08h] BYREF
  WCHAR Filename[264]; // [rsp+100h] [rbp-A38h] BYREF
  unsigned __int16 v12[1032]; // [rsp+310h] [rbp-828h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B38h] [rbp+0h]

  if ( !GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v6 = 300;
LABEL_3:
    v7 = -2147467259;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
      (const char *)(unsigned int)v7,
      (int)v9);
    return (unsigned int)v7;
  }
  if ( !StringFromGUID2(a3, sz, 100) )
  {
    v6 = 306;
    goto LABEL_3;
  }
  v9 = L"-DatabaseComplete";
  v7 = StringCchPrintfW(v12, 0x401u, L"%ws %ws %ws", Filename);
  if ( v7 < 0 )
  {
    v6 = 311;
    goto LABEL_4;
  }
  if ( g_bForceWeekly )
  {
    v7 = StringCchCatW(v12, 0x401u, L" ");
    if ( v7 < 0 )
    {
      v6 = 314;
      goto LABEL_4;
    }
    v7 = StringCchCatW(v12, 0x401u, L"-ForceWeekly");
    if ( v7 < 0 )
    {
      v6 = 315;
      goto LABEL_4;
    }
  }
  v7 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob5 *, WCHAR *, unsigned __int16 *))a2->lpVtbl->SetNotifyCmdLine)(
         a2,
         Filename,
         v12);
  if ( v7 < 0 )
  {
    v6 = 317;
    goto LABEL_4;
  }
  v7 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob5 *, __int64))a2->lpVtbl->SetNotifyFlags)(a2, 3);
  if ( v7 < 0 )
  {
    v6 = 319;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x140011804  mov     [rsp+arg_0], rbx
0x140011809  mov     [rsp+arg_18], rsi
0x14001180e  push    rdi
0x14001180f  sub     rsp, 0B30h
0x140011816  mov     rax, cs:__security_cookie
0x14001181d  xor     rax, rsp
0x140011820  mov     [rsp+0B38h+var_18], rax
0x140011828  mov     rbx, r8
0x14001182b  mov     rdi, rdx
0x14001182e  mov     r8d, 104h; nSize
0x140011834  lea     rdx, [rsp+0B38h+Filename]; lpFilename
0x14001183c  xor     ecx, ecx; hModule
0x14001183e  call    cs:__imp_GetModuleFileNameW
0x140011844  test    eax, eax
0x140011846  jnz     short loc_140011870
0x140011848  mov     edx, 12Ch; void *
0x14001184d  mov     ebx, 80004005h
0x140011852  mov     rcx, [rsp+0B38h]; this
0x14001185a  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140011861  mov     r9d, ebx; char *
0x140011864  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011869  mov     eax, ebx
0x14001186b  jmp     loc_14001198A
0x140011870  mov     r8d, 64h ; 'd'; cchMax
0x140011876  lea     rdx, [rsp+0B38h+sz]; lpsz
0x14001187b  mov     rcx, rbx; rguid
0x14001187e  call    cs:__imp_StringFromGUID2
0x140011884  test    eax, eax
0x140011886  jnz     short loc_14001188F
0x140011888  mov     edx, 132h
0x14001188d  jmp     short loc_14001184D
0x14001188f  lea     rax, [rsp+0B38h+sz]
0x140011894  mov     esi, 401h
0x140011899  mov     [rsp+0B38h+var_B10], rax
0x14001189e  lea     r9, [rsp+0B38h+Filename]
0x1400118a6  lea     rax, aDatabasecomple_0; "-DatabaseComplete"
0x1400118ad  mov     edx, esi; unsigned __int64
0x1400118af  lea     r8, aWsWsWs; "%ws %ws %ws"
0x1400118b6  mov     [rsp+0B38h+var_B18], rax
0x1400118bb  lea     rcx, [rsp+0B38h+var_828]; unsigned __int16 *
0x1400118c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400118c8  mov     ebx, eax
0x1400118ca  test    eax, eax
0x1400118cc  jns     short loc_1400118D8
0x1400118ce  mov     edx, 137h
0x1400118d3  jmp     loc_140011852
0x1400118d8  cmp     cs:?g_bForceWeekly@@3_NA, 0; bool g_bForceWeekly
0x1400118df  jz      short loc_14001192F
0x1400118e1  lea     r8, asc_14001CD90; " "
0x1400118e8  mov     rdx, rsi; unsigned __int64
0x1400118eb  lea     rcx, [rsp+0B38h+var_828]; unsigned __int16 *
0x1400118f3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400118f8  mov     ebx, eax
0x1400118fa  test    eax, eax
0x1400118fc  jns     short loc_140011908
0x1400118fe  mov     edx, 13Ah
0x140011903  jmp     loc_140011852
0x140011908  lea     r8, aForceweekly_0; "-ForceWeekly"
0x14001190f  mov     rdx, rsi; unsigned __int64
0x140011912  lea     rcx, [rsp+0B38h+var_828]; unsigned __int16 *
0x14001191a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001191f  mov     ebx, eax
0x140011921  test    eax, eax
0x140011923  jns     short loc_14001192F
0x140011925  mov     edx, 13Bh
0x14001192a  jmp     loc_140011852
0x14001192f  mov     rax, [rdi]
0x140011932  lea     r8, [rsp+0B38h+var_828]
0x14001193a  lea     rdx, [rsp+0B38h+Filename]
0x140011942  mov     rcx, rdi
0x140011945  mov     rax, [rax+118h]
0x14001194c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011951  mov     ebx, eax
0x140011953  test    eax, eax
0x140011955  jns     short loc_140011961
0x140011957  mov     edx, 13Dh
0x14001195c  jmp     loc_140011852
0x140011961  mov     rax, [rdi]
0x140011964  mov     edx, 3
0x140011969  mov     rcx, rdi
0x14001196c  mov     rax, [rax+0B8h]
0x140011973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011978  mov     ebx, eax
0x14001197a  test    eax, eax
0x14001197c  jns     short loc_140011988
0x14001197e  mov     edx, 13Fh
0x140011983  jmp     loc_140011852
0x140011988  xor     eax, eax
0x14001198a  mov     rcx, [rsp+0B38h+var_18]
0x140011992  xor     rcx, rsp; StackCookie
0x140011995  call    __security_check_cookie
0x14001199a  lea     r11, [rsp+0B38h+var_8]
0x1400119a2  mov     rbx, [r11+10h]
0x1400119a6  mov     rsi, [r11+28h]
0x1400119aa  mov     rsp, r11
0x1400119ad  pop     rdi
0x1400119ae  retn
```
