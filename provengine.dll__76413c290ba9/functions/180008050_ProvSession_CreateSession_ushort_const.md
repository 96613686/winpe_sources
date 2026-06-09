# ProvSession::CreateSession(ushort const *)

- ea: `0x180008050`
- end: `0x180008319`
- name: `?CreateSession@ProvSession@@UEAAJPEBG@Z`
- size: `713`
- prototype: `int __fastcall(ProvSession *this, wchar_t *String1, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800011ac`
- `0x180007cc0`
- `0x180008050`
- `0x1800092dc`
- `0x1800097d0`
- `0x1800098dc`
- `0x180009900`
- `0x180009924`
- `0x180033144`
- `0x18004370e`
- `0x180043750`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180008241`
- `msvcrt!_wcsicmp` at `0x180008255`
- `msvcrt!_wcsicmp` at `0x180008241`
- `msvcrt!_wcsicmp` at `0x180008255`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000811f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008199`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000811f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008199`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800081b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000828e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800081b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000828e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000820c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000820c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800081bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008296`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800081bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008283`

## string_xrefs

- `0x180008237`: `ContinueSessionTask`

## pseudocode

```c
int __fastcall ProvSession::CreateSession(ProvSession *this, wchar_t *String1, __int64 a3, __int64 a4)
{
  _WORD **v7; // rsi
  _WORD *v8; // rcx
  void **v9; // rbx
  void **CurrentTimeString; // r14
  HKEY v11; // r14
  DWORD LastError; // ebx
  bool IsStateSeparationEnabled; // al
  const WCHAR *v14; // rdx
  unsigned int Key; // eax
  HKEY v16; // r14
  DWORD v17; // ebx
  int NewSessionId; // eax
  int v19; // ebx
  int dwOptions; // [rsp+20h] [rbp-88h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-88h]
  __int64 *v22; // [rsp+50h] [rbp-58h] BYREF
  void *v23[4]; // [rsp+58h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( !String1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
      (const char *)0x80004003LL,
      dwOptions);
    return -2147467261;
  }
  if ( (unsigned int)dword_18005A000 > 4 )
  {
    v22 = (__int64 *)String1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18005A000,
      (__int64)byte_18004E30D,
      0,
      a4,
      &v22);
  }
  v7 = (_WORD **)((char *)this + 24);
  if ( *((_QWORD *)this + 6) < 8u )
    v8 = (_WORD *)((char *)this + 24);
  else
    v8 = *v7;
  *((_QWORD *)this + 5) = 0;
  *v8 = 0;
  v9 = (void **)((char *)this + 56);
  CurrentTimeString = (void **)GetCurrentTimeString(v23);
  if ( (void **)((char *)this + 56) != CurrentTimeString )
  {
    if ( *((_QWORD *)this + 10) >= 8u )
      operator delete(*v9);
    *((_QWORD *)this + 10) = 7;
    *((_QWORD *)this + 9) = 0;
    *(_WORD *)v9 = 0;
    if ( (unsigned __int64)CurrentTimeString[3] >= 8 )
    {
      *v9 = *CurrentTimeString;
      *CurrentTimeString = 0;
    }
    else if ( CurrentTimeString[2] != (void *)-1LL )
    {
      memmove_0((char *)this + 56, CurrentTimeString, 2LL * ((_QWORD)CurrentTimeString[2] + 1));
    }
    *((_QWORD *)this + 9) = CurrentTimeString[2];
    *((_QWORD *)this + 10) = CurrentTimeString[3];
    CurrentTimeString[3] = (void *)7;
    CurrentTimeString[2] = 0;
    *(_WORD *)CurrentTimeString = 0;
  }
  if ( v23[3] >= (void *)8 )
    operator delete(v23[0]);
  v11 = (HKEY)*((_QWORD *)this + 11);
  if ( v11 )
  {
    LastError = GetLastError();
    RegCloseKey(v11);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 11) = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v14 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Sessions";
  if ( !IsStateSeparationEnabled )
    v14 = L"SOFTWARE\\Microsoft\\Provisioning\\Sessions";
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v14, 0, 0, 0, 0xFu, 0, (PHKEY)this + 11, 0);
  if ( Key )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x42,
             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
             (const char *)Key,
             dwOptionsa);
  if ( !_wcsicmp(String1, L"ContinueSessionTask") || !_wcsicmp(String1, L"OOBE") )
  {
    if ( (int)ProvSession::ResumeSession(this) >= 0 )
    {
      ProvSession::SaveSession(this);
      return 0;
    }
    *((_DWORD *)this + 4) = 0;
    v16 = (HKEY)*((_QWORD *)this + 12);
    if ( v16 )
    {
      v17 = GetLastError();
      RegCloseKey(v16);
      SetLastError(v17);
    }
    *((_QWORD *)this + 12) = 0;
    *((_DWORD *)this + 5) = 0;
    if ( *((_QWORD *)this + 6) >= 8u )
      v7 = (_WORD **)*v7;
    *((_QWORD *)this + 5) = 0;
    *(_WORD *)v7 = 0;
  }
  NewSessionId = ProvSession::CreateNewSessionId(this);
  v19 = NewSessionId;
  if ( NewSessionId >= 0 )
  {
    *((_BYTE *)this + 112) = 1;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5B,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
    (const char *)(unsigned int)NewSessionId,
    dwOptionsa);
  return v19;
}

```

## disassembly

```asm
0x180008050  mov     [rsp+arg_10], rbx
0x180008055  mov     [rsp+arg_18], rsi
0x18000805a  push    rdi
0x18000805b  push    r12
0x18000805d  push    r13
0x18000805f  push    r14
0x180008061  push    r15
0x180008063  sub     rsp, 80h
0x18000806a  mov     rax, cs:__security_cookie
0x180008071  xor     rax, rsp
0x180008074  mov     [rsp+0A8h+var_30], rax
0x180008079  mov     r15, rdx
0x18000807c  mov     rdi, rcx
0x18000807f  test    rdx, rdx
0x180008082  jnz     short loc_1800080AB
0x180008084  mov     rcx, [rsp+0A8h]; this
0x18000808c  mov     ebx, 80004003h
0x180008091  mov     r9d, ebx; char *
0x180008094  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000809b  lea     edx, [r15+2Dh]; void *
0x18000809f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800080a4  mov     eax, ebx
0x1800080a6  jmp     loc_1800082EE
0x1800080ab  mov     eax, cs:dword_18005A000
0x1800080b1  cmp     eax, 4
0x1800080b4  jbe     short loc_1800080DB
0x1800080b6  mov     [rsp+0A8h+var_58], r15
0x1800080bb  lea     rax, [rsp+0A8h+var_58]
0x1800080c0  mov     qword ptr [rsp+0A8h+dwOptions], rax
0x1800080c5  xor     r8d, r8d
0x1800080c8  lea     rdx, byte_18004E30D
0x1800080cf  lea     rcx, dword_18005A000
0x1800080d6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800080db  lea     rsi, [rdi+18h]
0x1800080df  cmp     qword ptr [rsi+18h], 8
0x1800080e4  jb      short loc_1800080EB
0x1800080e6  mov     rcx, [rsi]
0x1800080e9  jmp     short loc_1800080EE
0x1800080eb  mov     rcx, rsi
0x1800080ee  lea     r13, [rsi+10h]
0x1800080f2  mov     qword ptr [r13+0], 0
0x1800080fa  xor     eax, eax
0x1800080fc  mov     [rcx], ax
0x1800080ff  lea     rbx, [rdi+38h]
0x180008103  lea     rcx, [rsp+0A8h+var_50]; void *
0x180008108  call    ?GetCurrentTimeString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetCurrentTimeString(void)
0x18000810d  mov     r14, rax
0x180008110  cmp     rbx, rax
0x180008113  jz      short loc_18000818A
0x180008115  cmp     qword ptr [rbx+18h], 8
0x18000811a  jb      short loc_180008125
0x18000811c  mov     rcx, [rbx]
0x18000811f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008125  mov     r12d, 7
0x18000812b  mov     [rbx+18h], r12
0x18000812f  mov     qword ptr [rbx+10h], 0
0x180008137  xor     eax, eax
0x180008139  mov     [rbx], ax
0x18000813c  cmp     qword ptr [r14+18h], 8
0x180008141  jnb     short loc_18000815D
0x180008143  mov     r8, [r14+10h]
0x180008147  add     r8, 1
0x18000814b  jz      short loc_18000816A
0x18000814d  add     r8, r8; Size
0x180008150  mov     rdx, r14; Src
0x180008153  mov     rcx, rbx; void *
0x180008156  call    memmove_0
0x18000815b  jmp     short loc_18000816A
0x18000815d  mov     rax, [r14]
0x180008160  mov     [rbx], rax
0x180008163  mov     qword ptr [r14], 0
0x18000816a  mov     rax, [r14+10h]
0x18000816e  mov     [rbx+10h], rax
0x180008172  mov     rax, [r14+18h]
0x180008176  mov     [rbx+18h], rax
0x18000817a  mov     [r14+18h], r12
0x18000817e  xor     ebx, ebx
0x180008180  mov     [r14+10h], rbx
0x180008184  mov     [r14], bx
0x180008188  jmp     short loc_18000818C
0x18000818a  xor     ebx, ebx
0x18000818c  cmp     [rsp+0A8h+var_38], 8
0x180008192  jb      short loc_18000819F
0x180008194  mov     rcx, [rsp+0A8h+var_50]
0x180008199  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000819f  lea     r12, [rdi+58h]
0x1800081a3  mov     r14, [r12]
0x1800081a7  test    r14, r14
0x1800081aa  jz      short loc_1800081C7
0x1800081ac  call    cs:__imp_GetLastError
0x1800081b2  mov     ebx, eax
0x1800081b4  mov     rcx, r14; hKey
0x1800081b7  call    cs:__imp_RegCloseKey
0x1800081bd  mov     ecx, ebx; dwErrCode
0x1800081bf  call    cs:__imp_SetLastError
0x1800081c5  xor     ebx, ebx
0x1800081c7  mov     [r12], rbx
0x1800081cb  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x1800081d0  lea     rcx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\Provisioning\\Sess"...
0x1800081d7  lea     rdx, aOsdataSoftware_12; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800081de  test    al, al
0x1800081e0  cmovz   rdx, rcx; lpSubKey
0x1800081e4  mov     [rsp+0A8h+lpdwDisposition], rbx; lpdwDisposition
0x1800081e9  mov     [rsp+0A8h+phkResult], r12; phkResult
0x1800081ee  mov     [rsp+0A8h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800081f3  mov     [rsp+0A8h+samDesired], 0Fh; samDesired
0x1800081fb  mov     [rsp+0A8h+dwOptions], ebx; int
0x1800081ff  xor     r9d, r9d; lpClass
0x180008202  xor     r8d, r8d; Reserved
0x180008205  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000820c  call    cs:__imp_RegCreateKeyExW
0x180008212  test    eax, eax
0x180008214  jz      short loc_180008237
0x180008216  mov     rcx, [rsp+0A8h]; this
0x18000821e  mov     r9d, eax; char *
0x180008221  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180008228  mov     edx, 42h ; 'B'; void *
0x18000822d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180008232  jmp     loc_1800082EE
0x180008237  lea     rdx, ?gc_sourceContinueSessionTask@@3QBGB; "ContinueSessionTask"
0x18000823e  mov     rcx, r15; String1
0x180008241  call    cs:__imp__wcsicmp
0x180008247  test    eax, eax
0x180008249  jz      short loc_18000825F
0x18000824b  lea     rdx, ?gc_oobeSessionName@@3QBGB; "OOBE"
0x180008252  mov     rcx, r15; String1
0x180008255  call    cs:__imp__wcsicmp
0x18000825b  test    eax, eax
0x18000825d  jnz     short loc_1800082B6
0x18000825f  mov     rcx, rdi; this
0x180008262  call    ?ResumeSession@ProvSession@@AEAAJXZ; ProvSession::ResumeSession(void)
0x180008267  test    eax, eax
0x180008269  js      short loc_180008277
0x18000826b  mov     rcx, rdi; this
0x18000826e  call    ?SaveSession@ProvSession@@AEAAJXZ; ProvSession::SaveSession(void)
0x180008273  xor     eax, eax
0x180008275  jmp     short loc_1800082EE
0x180008277  mov     [rdi+10h], ebx
0x18000827a  mov     r14, [rdi+60h]
0x18000827e  test    r14, r14
0x180008281  jz      short loc_18000829E
0x180008283  call    cs:__imp_GetLastError
0x180008289  mov     ebx, eax
0x18000828b  mov     rcx, r14; hKey
0x18000828e  call    cs:__imp_RegCloseKey
0x180008294  mov     ecx, ebx; dwErrCode
0x180008296  call    cs:__imp_SetLastError
0x18000829c  xor     ebx, ebx
0x18000829e  mov     [rdi+60h], rbx
0x1800082a2  mov     [rdi+14h], ebx
0x1800082a5  cmp     qword ptr [rsi+18h], 8
0x1800082aa  jb      short loc_1800082AF
0x1800082ac  mov     rsi, [rsi]
0x1800082af  mov     [r13+0], rbx
0x1800082b3  mov     [rsi], bx
0x1800082b6  mov     rcx, rdi; this
0x1800082b9  call    ?CreateNewSessionId@ProvSession@@AEAAJXZ; ProvSession::CreateNewSessionId(void)
0x1800082be  mov     ebx, eax
0x1800082c0  test    eax, eax
0x1800082c2  jns     short loc_1800082E4
0x1800082c4  mov     rcx, [rsp+0A8h]; this
0x1800082cc  mov     r9d, eax; char *
0x1800082cf  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800082d6  mov     edx, 5Bh ; '['; void *
0x1800082db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082e0  mov     eax, ebx
0x1800082e2  jmp     short loc_1800082EE
0x1800082e4  mov     byte ptr [rdi+70h], 1
0x1800082e8  jmp     short loc_180008273
0x1800082ea  mov     eax, dword ptr [rsp+0A8h+var_58]
0x1800082ee  mov     rcx, [rsp+0A8h+var_30]
0x1800082f3  xor     rcx, rsp; StackCookie
0x1800082f6  call    __security_check_cookie
0x1800082fb  lea     r11, [rsp+0A8h+var_28]
0x180008303  mov     rbx, [r11+40h]
0x180008307  mov     rsi, [r11+48h]
0x18000830b  mov     rsp, r11
0x18000830e  pop     r15
0x180008310  pop     r14
0x180008312  pop     r13
0x180008314  pop     r12
0x180008316  pop     rdi
0x180008317  retn
```
