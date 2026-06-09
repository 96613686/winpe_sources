# UserSecurityContext::ImportPrivateKeyIfNeeded(void)

- ea: `0x1800171b0`
- end: `0x180017459`
- name: `?ImportPrivateKeyIfNeeded@UserSecurityContext@@UEAAJXZ`
- size: `681`
- prototype: `__int64 __fastcall(UserSecurityContext *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007014`
- `0x1800087f8`
- `0x18000a33c`
- `0x180013bbc`
- `0x180013c74`
- `0x180013d20`
- `0x1800171b0`
- `0x180026010`

## import_xrefs

- `ADVAPI32!CryptImportKey` at `0x18001739d`
- `ADVAPI32!CryptImportKey` at `0x18001739d`
- `ADVAPI32!CryptAcquireContextW` at `0x1800172af`
- `ADVAPI32!CryptAcquireContextW` at `0x1800172cc`
- `ADVAPI32!CryptAcquireContextW` at `0x1800172af`
- `ADVAPI32!CryptAcquireContextW` at `0x1800172cc`
- `ADVAPI32!CryptDestroyKey` at `0x180017436`
- `ADVAPI32!CryptDestroyKey` at `0x180017436`
- `KERNEL32!GetLastError` at `0x1800171f0`
- `KERNEL32!GetLastError` at `0x1800172da`
- `KERNEL32!GetLastError` at `0x1800172e2`
- `KERNEL32!GetLastError` at `0x1800173ab`
- `KERNEL32!GetLastError` at `0x1800173b3`
- `KERNEL32!GetLastError` at `0x1800171f0`
- `KERNEL32!GetLastError` at `0x1800172da`
- `KERNEL32!GetLastError` at `0x1800172e2`
- `KERNEL32!GetLastError` at `0x1800173ab`
- `KERNEL32!GetLastError` at `0x1800173b3`
- `KERNEL32!GetCurrentProcessId` at `0x180017271`
- `KERNEL32!GetCurrentProcessId` at `0x180017271`
- `KERNEL32!LeaveCriticalSection` at `0x1800171dd`
- `KERNEL32!LeaveCriticalSection` at `0x18001725f`
- `KERNEL32!LeaveCriticalSection` at `0x180017354`
- `KERNEL32!LeaveCriticalSection` at `0x180017425`
- `KERNEL32!LeaveCriticalSection` at `0x180017443`
- `KERNEL32!LeaveCriticalSection` at `0x1800171dd`
- `KERNEL32!LeaveCriticalSection` at `0x18001725f`
- `KERNEL32!LeaveCriticalSection` at `0x180017354`
- `KERNEL32!LeaveCriticalSection` at `0x180017425`
- `KERNEL32!LeaveCriticalSection` at `0x180017443`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserSecurityContext::ImportPrivateKeyIfNeeded(UserSecurityContext *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  DWORD v3; // eax
  DWORD CurrentProcessId; // eax
  DWORD v6; // ebx
  DWORD v7; // eax
  DWORD v8; // ebx
  const BYTE *v9; // rdi
  HCRYPTPROV v10; // rax
  DWORD LastError; // ebx
  DWORD v12; // eax
  HCRYPTKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  HCRYPTPROV phProv; // [rsp+58h] [rbp+10h] BYREF
  char *v15; // [rsp+60h] [rbp+18h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 160);
  v15 = (char *)this + 160;
  CCriticalSection::Lock((UserSecurityContext *)((char *)this + 160));
  if ( *((_BYTE *)this + 80) )
  {
    if ( *((_QWORD *)this + 11) )
    {
      CurrentProcessId = GetCurrentProcessId();
      StringCchPrintfW((wchar_t *)this + 50, 0x1Cu, L"P-%lu-MSMQ", CurrentProcessId);
      phProv = 0;
      CryptAcquireContextW(&phProv, (LPCWSTR)this + 50, *((LPCWSTR *)this + 3), *((_DWORD *)this + 14), 0x10u);
      if ( CryptAcquireContextW(
             (HCRYPTPROV *)this + 9,
             (LPCWSTR)this + 50,
             *((LPCWSTR *)this + 3),
             *((_DWORD *)this + 14),
             8u) )
      {
        hKey = 0;
        v8 = *((_DWORD *)this + 24);
        v9 = (const BYTE *)*((_QWORD *)this + 11);
        v10 = (*(__int64 (__fastcall **)(UserSecurityContext *))(*(_QWORD *)this + 16LL))(this);
        if ( CryptImportKey(v10, v9, v8, 0, 0, &hKey) )
        {
          CryptDestroyKey(hKey);
          *((_BYTE *)this + 80) = 0;
          LeaveCriticalSection(v2);
          return 0;
        }
        LastError = GetLastError();
        v12 = GetLastError();
        if ( v12 )
          LogMsgNTStatus(v12, (wchar_t *)L"rt/rtsecctx", 0x1AEu);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 14, WPP_4429bf9cee813cde9fee94052f370384_Traceguids, LastError);
        LogMsgHR(-1072824272, (wchar_t *)L"rt/rtsecctx", 0x1B8u);
        LeaveCriticalSection(v2);
      }
      else
      {
        v6 = GetLastError();
        v7 = GetLastError();
        if ( v7 )
          LogMsgNTStatus(v7, (wchar_t *)L"rt/rtsecctx", 0x19Au);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 13, WPP_4429bf9cee813cde9fee94052f370384_Traceguids, v6);
        LogMsgHR(-1072824272, (wchar_t *)L"rt/rtsecctx", 0x1A4u);
        LeaveCriticalSection(v2);
      }
    }
    else
    {
      v3 = GetLastError();
      if ( v3 )
        LogMsgNTStatus(v3, (wchar_t *)L"rt/rtsecctx", 0x1Du);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 12, WPP_4429bf9cee813cde9fee94052f370384_Traceguids);
      LogMsgHR(-1072824272, (wchar_t *)L"rt/rtsecctx", 0x190u);
      LeaveCriticalSection(v2);
    }
    return 3222143024LL;
  }
  LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x1800171b0  mov     [rsp+arg_18], rbx
0x1800171b5  push    rbp
0x1800171b6  push    rsi
0x1800171b7  push    rdi
0x1800171b8  sub     rsp, 30h
0x1800171bc  mov     rsi, rcx
0x1800171bf  lea     rbp, [rcx+0A0h]
0x1800171c6  mov     [rsp+48h+arg_10], rbp
0x1800171cb  mov     rcx, rbp; this
0x1800171ce  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x1800171d3  nop
0x1800171d4  cmp     byte ptr [rsi+50h], 0
0x1800171d8  jnz     short loc_1800171E9
0x1800171da  mov     rcx, rbp; lpCriticalSection
0x1800171dd  call    cs:__imp_LeaveCriticalSection
0x1800171e3  nop
0x1800171e4  jmp     loc_18001744A
0x1800171e9  cmp     qword ptr [rsi+58h], 0
0x1800171ee  jnz     short loc_18001726D
0x1800171f0  call    cs:__imp_GetLastError
0x1800171f6  test    eax, eax
0x1800171f8  jz      short loc_18001720E
0x1800171fa  mov     r8d, 1Dh; unsigned __int16
0x180017200  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180017207  mov     ecx, eax; int
0x180017209  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18001720e  lea     rax, WPP_GLOBAL_Control
0x180017215  mov     rcx, cs:WPP_GLOBAL_Control
0x18001721c  cmp     rcx, rax
0x18001721f  jz      short loc_180017242
0x180017221  test    byte ptr [rcx+10Ch], 1
0x180017228  jz      short loc_180017242
0x18001722a  mov     edx, 0Ch
0x18001722f  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x180017236  mov     rcx, [rcx+100h]
0x18001723d  call    WPP_SF_
0x180017242  mov     r8d, 190h; unsigned __int16
0x180017248  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x18001724f  mov     ebx, 0C00E0030h
0x180017254  mov     ecx, ebx; int
0x180017256  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001725b  nop
0x18001725c  mov     rcx, rbp; lpCriticalSection
0x18001725f  call    cs:__imp_LeaveCriticalSection
0x180017265  nop
0x180017266  mov     eax, ebx
0x180017268  jmp     loc_18001744C
0x18001726d  lea     rbx, [rsi+64h]
0x180017271  call    cs:__imp_GetCurrentProcessId
0x180017277  mov     r9d, eax
0x18001727a  lea     r8, aPLuMsmq; "P-%lu-MSMQ"
0x180017281  mov     edx, 1Ch; unsigned __int64
0x180017286  mov     rcx, rbx; wchar_t *
0x180017289  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001728e  mov     [rsp+48h+phProv], 0
0x180017297  mov     [rsp+48h+dwFlags], 10h; dwFlags
0x18001729f  mov     r9d, [rsi+38h]; dwProvType
0x1800172a3  mov     r8, [rsi+18h]; szProvider
0x1800172a7  mov     rdx, rbx; szContainer
0x1800172aa  lea     rcx, [rsp+48h+phProv]; phProv
0x1800172af  call    cs:__imp_CryptAcquireContextW
0x1800172b5  lea     rcx, [rsi+48h]; phProv
0x1800172b9  mov     [rsp+48h+dwFlags], 8; dwFlags
0x1800172c1  mov     r9d, [rsi+38h]; dwProvType
0x1800172c5  mov     r8, [rsi+18h]; szProvider
0x1800172c9  mov     rdx, rbx; szContainer
0x1800172cc  call    cs:__imp_CryptAcquireContextW
0x1800172d2  test    eax, eax
0x1800172d4  jnz     loc_180017360
0x1800172da  call    cs:__imp_GetLastError
0x1800172e0  mov     ebx, eax
0x1800172e2  call    cs:__imp_GetLastError
0x1800172e8  test    eax, eax
0x1800172ea  jz      short loc_180017300
0x1800172ec  mov     r8d, 19Ah; unsigned __int16
0x1800172f2  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x1800172f9  mov     ecx, eax; int
0x1800172fb  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180017300  lea     rax, WPP_GLOBAL_Control
0x180017307  mov     rcx, cs:WPP_GLOBAL_Control
0x18001730e  cmp     rcx, rax
0x180017311  jz      short loc_180017337
0x180017313  test    byte ptr [rcx+10Ch], 1
0x18001731a  jz      short loc_180017337
0x18001731c  mov     edx, 0Dh
0x180017321  mov     r9d, ebx
0x180017324  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x18001732b  mov     rcx, [rcx+100h]
0x180017332  call    WPP_SF_d
0x180017337  mov     r8d, 1A4h; unsigned __int16
0x18001733d  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180017344  mov     ebx, 0C00E0030h
0x180017349  mov     ecx, ebx; int
0x18001734b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180017350  nop
0x180017351  mov     rcx, rbp; lpCriticalSection
0x180017354  call    cs:__imp_LeaveCriticalSection
0x18001735a  nop
0x18001735b  jmp     loc_180017266
0x180017360  mov     [rsp+48h+hKey], 0
0x180017369  mov     ebx, [rsi+60h]
0x18001736c  mov     rdi, [rsi+58h]
0x180017370  mov     rax, [rsi]
0x180017373  mov     rcx, rsi
0x180017376  mov     rax, [rax+10h]
0x18001737a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001737f  lea     rcx, [rsp+48h+hKey]
0x180017384  mov     [rsp+48h+phKey], rcx; phKey
0x180017389  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180017391  xor     r9d, r9d; hPubKey
0x180017394  mov     r8d, ebx; dwDataLen
0x180017397  mov     rdx, rdi; pbData
0x18001739a  mov     rcx, rax; hProv
0x18001739d  call    cs:__imp_CryptImportKey
0x1800173a3  test    eax, eax
0x1800173a5  jnz     loc_180017431
0x1800173ab  call    cs:__imp_GetLastError
0x1800173b1  mov     ebx, eax
0x1800173b3  call    cs:__imp_GetLastError
0x1800173b9  test    eax, eax
0x1800173bb  jz      short loc_1800173D1
0x1800173bd  mov     r8d, 1AEh; unsigned __int16
0x1800173c3  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x1800173ca  mov     ecx, eax; int
0x1800173cc  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x1800173d1  lea     rax, WPP_GLOBAL_Control
0x1800173d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173df  cmp     rcx, rax
0x1800173e2  jz      short loc_180017408
0x1800173e4  test    byte ptr [rcx+10Ch], 1
0x1800173eb  jz      short loc_180017408
0x1800173ed  mov     edx, 0Eh
0x1800173f2  mov     r9d, ebx
0x1800173f5  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x1800173fc  mov     rcx, [rcx+100h]
0x180017403  call    WPP_SF_d
0x180017408  mov     r8d, 1B8h; unsigned __int16
0x18001740e  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180017415  mov     ebx, 0C00E0030h
0x18001741a  mov     ecx, ebx; int
0x18001741c  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180017421  nop
0x180017422  mov     rcx, rbp; lpCriticalSection
0x180017425  call    cs:__imp_LeaveCriticalSection
0x18001742b  nop
0x18001742c  jmp     loc_180017266
0x180017431  mov     rcx, [rsp+48h+hKey]; hKey
0x180017436  call    cs:__imp_CryptDestroyKey
0x18001743c  mov     byte ptr [rsi+50h], 0
0x180017440  mov     rcx, rbp; lpCriticalSection
0x180017443  call    cs:__imp_LeaveCriticalSection
0x180017449  nop
0x18001744a  xor     eax, eax
0x18001744c  mov     rbx, [rsp+48h+arg_18]
0x180017451  add     rsp, 30h
0x180017455  pop     rdi
0x180017456  pop     rsi
0x180017457  pop     rbp
0x180017458  retn
```
