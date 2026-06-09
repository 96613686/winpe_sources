# COfflineFilesSetting::SetPreferenceInternal(tagVARIANT const *,ulong)

- ea: `0x1800275a0`
- end: `0x18002789b`
- name: `?SetPreferenceInternal@COfflineFilesSetting@@UEAAJPEBUtagVARIANT@@K@Z`
- size: `763`
- prototype: `int(COfflineFilesSetting *__hidden this, const struct tagVARIANT *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800275a0`
- `0x18002f10c`
- `0x180033ddc`
- `0x180035368`
- `0x1800391b8`
- `0x180039610`
- `0x18003c5ec`
- `0x180080d34`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800277c2`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800277c2`
- `ntdll!RtlReleaseResource` at `0x1800277e9`
- `ntdll!RtlReleaseResource` at `0x1800277e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027868`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027868`
- `ADVAPI32!SetThreadToken` at `0x180027854`
- `ADVAPI32!SetThreadToken` at `0x180027854`

## string_xrefs

- `0x1800276fd`: `Software\Microsoft\Windows\CurrentVersion\NetCache`
- `0x180027759`: `Software\Microsoft\Windows\CurrentVersion\NetCache`

## pseudocode

```c
__int64 __fastcall COfflineFilesSetting::SetPreferenceInternal(
        COfflineFilesSetting *this,
        const struct tagVARIANT *a2,
        int a3)
{
  CSettingAccessor *v3; // rbx
  __int64 **v4; // r14
  int v8; // ecx
  int v9; // edi
  __int64 v10; // rbp
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  signed int v14; // edi
  CSettingAccessor *v15; // rax
  void **v16; // rax
  CSettingAccessor *v17; // rax
  CSettingAccessor *v18; // rax
  __int64 *v19; // rsi
  int v20; // ecx
  __int64 v21; // r15
  int v22; // ebp
  int v23; // r12d
  const WCHAR *v24; // r9
  __int64 v25; // rcx
  unsigned __int16 *v26; // rax
  __int64 v27; // rdx
  unsigned __int16 *v28; // rcx
  const unsigned __int16 *v29; // rsi
  const wchar_t *v30; // r9
  HANDLE Token[2]; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int16 v33[264]; // [rsp+40h] [rbp-258h] BYREF

  v3 = (CSettingAccessor *)*((_QWORD *)this + 2);
  v4 = (__int64 **)((char *)this + 24);
  if ( v3 )
  {
    v14 = 0;
    goto LABEL_20;
  }
  v8 = *((_DWORD *)*v4 + 4);
  v9 = *((_DWORD *)*v4 + 3);
  v10 = (*v4)[5];
  *((_QWORD *)this + 2) = 0;
  if ( !v8 )
    goto LABEL_12;
  v11 = v8 - 1;
  if ( !v11 )
    goto LABEL_10;
  v12 = v11 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 != 1 )
      {
        v14 = -2147467259;
        v3 = 0;
        goto LABEL_20;
      }
LABEL_10:
      v17 = (CSettingAccessor *)operator new(0x18u);
      v3 = v17;
      if ( v17 )
      {
        *((_QWORD *)v17 + 1) = v10;
        *((_DWORD *)v17 + 4) = v9;
        v16 = &CSettingAccessor_SZ::`vftable';
        goto LABEL_14;
      }
      goto LABEL_15;
    }
LABEL_12:
    v18 = (CSettingAccessor *)operator new(0x18u);
    v3 = v18;
    if ( v18 )
    {
      *((_QWORD *)v18 + 1) = v10;
      *((_DWORD *)v18 + 4) = v9;
      v16 = &CSettingAccessor_DWORD::`vftable';
      goto LABEL_14;
    }
    goto LABEL_15;
  }
  v15 = (CSettingAccessor *)operator new(0x18u);
  v3 = v15;
  if ( v15 )
  {
    *((_QWORD *)v15 + 1) = v10;
    *((_DWORD *)v15 + 4) = v9;
    v16 = &CSettingAccessor_MULTISZ::`vftable';
LABEL_14:
    *(_QWORD *)v3 = v16;
    goto LABEL_16;
  }
LABEL_15:
  v3 = 0;
LABEL_16:
  *((_QWORD *)this + 2) = v3;
  v14 = 0;
  if ( !v3 )
    v14 = -2147024882;
LABEL_20:
  if ( v14 < 0 )
    return (unsigned int)v14;
  v19 = *v4;
  v20 = *((_DWORD *)*v4 + 5);
  if ( a3 != 1 )
  {
    if ( (v20 & 6) != 0 )
    {
      v21 = -2147483646;
      v22 = 1;
      if ( (v20 & 4) != 0 )
        goto LABEL_28;
      goto LABEL_27;
    }
    return (unsigned int)-2147024846;
  }
  if ( (v20 & 1) == 0 )
    return (unsigned int)-2147024846;
  v21 = -2147483647;
LABEL_27:
  v22 = 0;
LABEL_28:
  if ( *((_DWORD *)v19 + 4) == 3 || *((_DWORD *)v19 + 4) == 4 )
  {
    v14 = StringCchPrintfW(v33, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Windows\\CurrentVersion\\NetCache", v19[3]);
    v23 = 1;
  }
  else
  {
    v23 = 0;
    v24 = L"Software\\Microsoft\\Windows\\CurrentVersion\\NetCache";
    v25 = 2147483646;
    v26 = v33;
    v27 = 260;
    do
    {
      if ( !v25 )
        break;
      if ( !*v24 )
        break;
      *v26++ = *v24++;
      --v25;
      --v27;
    }
    while ( v27 );
    v28 = v26 - 1;
    if ( v27 )
      v28 = v26;
    v14 = v27 == 0 ? 0x8007007A : 0;
    *v28 = 0;
  }
  if ( v14 >= 0 )
  {
    v29 = (const unsigned __int16 *)v19[3];
    Token[0] = 0;
    if ( !v22 || (v14 = CComTemporaryRevertToSelf::RevertToSelf((CComTemporaryRevertToSelf *)Token), v14 >= 0) )
    {
      if ( v23 )
        v29 = 0;
      RtlAcquireResourceExclusive(&g_swmrSettingsLock, 1u);
      v14 = CSettingAccessor::Write(v3, (HKEY)v21, v33, v29, a2);
      RtlReleaseResource(&g_swmrSettingsLock);
      if ( v14 >= 0
        && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
      {
        v30 = L"Machine";
        if ( v21 != -2147483646 )
          v30 = L"User";
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_8efcffa2381534b4e0c94c54ca70b20c_Traceguids,
          (_DWORD)v30,
          **v4);
      }
    }
    if ( Token[0] )
    {
      if ( !SetThreadToken(0, Token[0]) )
        ResultFromLastError();
      CloseHandle(Token[0]);
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800275a0  mov     [rsp+arg_10], rbx
0x1800275a5  push    rbp
0x1800275a6  push    rsi
0x1800275a7  push    rdi
0x1800275a8  push    r12
0x1800275aa  push    r13
0x1800275ac  push    r14
0x1800275ae  push    r15
0x1800275b0  sub     rsp, 260h
0x1800275b7  mov     rax, cs:__security_cookie
0x1800275be  xor     rax, rsp
0x1800275c1  mov     [rsp+298h+var_48], rax
0x1800275c9  mov     rbx, [rcx+10h]
0x1800275cd  lea     r14, [rcx+18h]
0x1800275d1  xor     r10d, r10d
0x1800275d4  mov     r15d, r8d
0x1800275d7  mov     r13, rdx
0x1800275da  mov     rsi, rcx
0x1800275dd  test    rbx, rbx
0x1800275e0  jnz     loc_1800276A5
0x1800275e6  mov     rax, [r14]
0x1800275e9  mov     ecx, [rax+10h]
0x1800275ec  mov     edi, [rax+0Ch]
0x1800275ef  mov     rbp, [rax+28h]
0x1800275f3  mov     [rsi+10h], r10
0x1800275f7  test    ecx, ecx
0x1800275f9  jz      short loc_180027666
0x1800275fb  sub     ecx, 1
0x1800275fe  jz      short loc_180027641
0x180027600  sub     ecx, 1
0x180027603  jz      short loc_18002761C
0x180027605  sub     ecx, 1
0x180027608  jz      short loc_180027666
0x18002760a  cmp     ecx, 1
0x18002760d  jz      short loc_180027641
0x18002760f  mov     edi, 80004005h
0x180027614  mov     ebx, r10d
0x180027617  jmp     loc_1800276A8
0x18002761c  mov     ecx, 18h; Size
0x180027621  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027626  xor     r10d, r10d
0x180027629  mov     rbx, rax
0x18002762c  test    rax, rax
0x18002762f  jz      short loc_18002768E
0x180027631  mov     [rax+8], rbp
0x180027635  mov     [rax+10h], edi
0x180027638  lea     rax, ??_7CSettingAccessor_MULTISZ@@6B@; const CSettingAccessor_MULTISZ::`vftable'
0x18002763f  jmp     short loc_180027689
0x180027641  mov     ecx, 18h; Size
0x180027646  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002764b  xor     r10d, r10d
0x18002764e  mov     rbx, rax
0x180027651  test    rax, rax
0x180027654  jz      short loc_18002768E
0x180027656  mov     [rax+8], rbp
0x18002765a  mov     [rax+10h], edi
0x18002765d  lea     rax, ??_7CSettingAccessor_SZ@@6B@; const CSettingAccessor_SZ::`vftable'
0x180027664  jmp     short loc_180027689
0x180027666  mov     ecx, 18h; Size
0x18002766b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027670  xor     r10d, r10d
0x180027673  mov     rbx, rax
0x180027676  test    rax, rax
0x180027679  jz      short loc_18002768E
0x18002767b  mov     [rax+8], rbp
0x18002767f  mov     [rax+10h], edi
0x180027682  lea     rax, ??_7CSettingAccessor_DWORD@@6B@; const CSettingAccessor_DWORD::`vftable'
0x180027689  mov     [rbx], rax
0x18002768c  jmp     short loc_180027691
0x18002768e  mov     rbx, r10
0x180027691  test    rbx, rbx
0x180027694  mov     [rsi+10h], rbx
0x180027698  mov     edi, r10d
0x18002769b  mov     eax, 8007000Eh
0x1800276a0  cmovz   edi, eax
0x1800276a3  jmp     short loc_1800276A8
0x1800276a5  mov     edi, r10d
0x1800276a8  test    edi, edi
0x1800276aa  js      loc_18002786E
0x1800276b0  mov     rsi, [r14]
0x1800276b3  mov     ecx, [rsi+14h]
0x1800276b6  cmp     r15d, 1
0x1800276ba  jnz     short loc_1800276CA
0x1800276bc  test    r15b, cl
0x1800276bf  jz      short loc_1800276CF
0x1800276c1  mov     r15, 0FFFFFFFF80000001h
0x1800276c8  jmp     short loc_1800276EA
0x1800276ca  test    cl, 6
0x1800276cd  jnz     short loc_1800276D9
0x1800276cf  mov     edi, 80070032h
0x1800276d4  jmp     loc_18002786E
0x1800276d9  mov     r15, 0FFFFFFFF80000002h
0x1800276e0  mov     ebp, 1
0x1800276e5  test    cl, 4
0x1800276e8  jnz     short loc_1800276ED
0x1800276ea  mov     ebp, r10d
0x1800276ed  mov     ecx, [rsi+10h]
0x1800276f0  sub     ecx, 3
0x1800276f3  jz      short loc_180027755
0x1800276f5  cmp     ecx, 1
0x1800276f8  jz      short loc_180027755
0x1800276fa  mov     r12d, r10d
0x1800276fd  lea     r9, REGSTR_KEY_OFFLINEFILES; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180027704  mov     ecx, 7FFFFFFEh
0x180027709  lea     rax, [rsp+298h+var_258]
0x18002770e  mov     edx, 104h
0x180027713  test    rcx, rcx
0x180027716  jz      short loc_180027737
0x180027718  movzx   r8d, word ptr [r9]
0x18002771c  test    r8w, r8w
0x180027720  jz      short loc_180027737
0x180027722  mov     [rax], r8w
0x180027726  add     r9, 2
0x18002772a  add     rax, 2
0x18002772e  dec     rcx
0x180027731  sub     rdx, 1
0x180027735  jnz     short loc_180027713
0x180027737  test    rdx, rdx
0x18002773a  lea     rcx, [rax-2]
0x18002773e  cmovnz  rcx, rax
0x180027742  neg     rdx
0x180027745  sbb     edi, edi
0x180027747  not     edi
0x180027749  and     edi, 8007007Ah
0x18002774f  mov     [rcx], r10w
0x180027753  jmp     short loc_180027786
0x180027755  mov     rax, [rsi+18h]
0x180027759  lea     r9, REGSTR_KEY_OFFLINEFILES; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180027760  lea     r8, aSS; "%s\\%s"
0x180027767  mov     [rsp+298h+var_278], rax
0x18002776c  mov     edx, 104h; unsigned __int64
0x180027771  lea     rcx, [rsp+298h+var_258]; unsigned __int16 *
0x180027776  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002777b  mov     edi, eax
0x18002777d  xor     r10d, r10d
0x180027780  mov     r12d, 1
0x180027786  test    edi, edi
0x180027788  js      loc_18002786E
0x18002778e  mov     rsi, [rsi+18h]
0x180027792  mov     [rsp+298h+Token], r10
0x180027797  test    ebp, ebp
0x180027799  jz      short loc_1800277B2
0x18002779b  lea     rcx, [rsp+298h+Token]; this
0x1800277a0  call    ?RevertToSelf@CComTemporaryRevertToSelf@@QEAAJXZ; CComTemporaryRevertToSelf::RevertToSelf(void)
0x1800277a5  xor     r10d, r10d
0x1800277a8  mov     edi, eax
0x1800277aa  test    eax, eax
0x1800277ac  js      loc_180027848
0x1800277b2  test    r12d, r12d
0x1800277b5  lea     rcx, ?g_swmrSettingsLock@@3VCSingleWriterMultiReaderLock@@A; Resource
0x1800277bc  mov     dl, 1; Wait
0x1800277be  cmovnz  rsi, r10
0x1800277c2  call    cs:__imp_RtlAcquireResourceExclusive
0x1800277c8  mov     r9, rsi; unsigned __int16 *
0x1800277cb  mov     [rsp+298h+var_278], r13; struct tagVARIANT *
0x1800277d0  lea     r8, [rsp+298h+var_258]; unsigned __int16 *
0x1800277d5  mov     rdx, r15; HKEY
0x1800277d8  mov     rcx, rbx; this
0x1800277db  call    ?Write@CSettingAccessor@@QEAAJPEAUHKEY__@@PEBG1AEBUtagVARIANT@@@Z; CSettingAccessor::Write(HKEY__ *,ushort const *,ushort const *,tagVARIANT const &)
0x1800277e0  lea     rcx, ?g_swmrSettingsLock@@3VCSingleWriterMultiReaderLock@@A; Resource
0x1800277e7  mov     edi, eax
0x1800277e9  call    cs:__imp_RtlReleaseResource
0x1800277ef  test    edi, edi
0x1800277f1  js      short loc_180027848
0x1800277f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277fa  lea     rax, WPP_GLOBAL_Control
0x180027801  cmp     rcx, rax
0x180027804  jz      short loc_180027848
0x180027806  test    dword ptr [rcx+1Ch], 10000h
0x18002780d  jz      short loc_180027848
0x18002780f  mov     rax, [r14]
0x180027812  lea     rdx, aUser_1; "User"
0x180027819  mov     rcx, [rcx+10h]
0x18002781d  lea     r9, aMachine; "Machine"
0x180027824  cmp     r15, 0FFFFFFFF80000002h
0x18002782b  lea     r8, WPP_8efcffa2381534b4e0c94c54ca70b20c_Traceguids
0x180027832  mov     rax, [rax]
0x180027835  cmovnz  r9, rdx
0x180027839  mov     edx, 13h
0x18002783e  mov     [rsp+298h+var_278], rax
0x180027843  call    WPP_SF_SS
0x180027848  mov     rdx, [rsp+298h+Token]; Token
0x18002784d  test    rdx, rdx
0x180027850  jz      short loc_18002786E
0x180027852  xor     ecx, ecx; Thread
0x180027854  call    cs:__imp_SetThreadToken
0x18002785a  test    eax, eax
0x18002785c  jnz     short loc_180027863
0x18002785e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180027863  mov     rcx, [rsp+298h+Token]; hObject
0x180027868  call    cs:__imp_CloseHandle
0x18002786e  mov     eax, edi
0x180027870  mov     rcx, [rsp+298h+var_48]
0x180027878  xor     rcx, rsp; StackCookie
0x18002787b  call    __security_check_cookie
0x180027880  mov     rbx, [rsp+298h+arg_10]
0x180027888  add     rsp, 260h
0x18002788f  pop     r15
0x180027891  pop     r14
0x180027893  pop     r13
0x180027895  pop     r12
0x180027897  pop     rdi
0x180027898  pop     rsi
0x180027899  pop     rbp
0x18002789a  retn
```
