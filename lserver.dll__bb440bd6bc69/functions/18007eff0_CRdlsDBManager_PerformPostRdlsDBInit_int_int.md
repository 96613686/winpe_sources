# CRdlsDBManager::PerformPostRdlsDBInit(int,int)

- ea: `0x18007eff0`
- end: `0x18007f35f`
- name: `?PerformPostRdlsDBInit@CRdlsDBManager@@QEAAKHH@Z`
- size: `879`
- prototype: `unsigned int __fastcall(CRdlsDBManager *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180020790`

## callees

- `0x18000bb98`
- `0x180022910`
- `0x18002d834`
- `0x180035030`
- `0x1800412b4`
- `0x180042068`
- `0x1800427a0`
- `0x18007da44`
- `0x18007eea0`
- `0x18007ef70`
- `0x18007eff0`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18007f2fd`
- `ADVAPI32!RegOpenKeyExW` at `0x18007f2fd`
- `ADVAPI32!RegCloseKey` at `0x18007f313`
- `ADVAPI32!RegCloseKey` at `0x18007f313`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18007f1ee`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18007f1ee`
- `KERNEL32!LocalFree` at `0x18007f090`
- `KERNEL32!LocalFree` at `0x18007f203`
- `KERNEL32!LocalFree` at `0x18007f090`
- `KERNEL32!LocalFree` at `0x18007f203`

## string_xrefs

- `0x18007f2ef`: `SYSTEM\CurrentControlSet\Services\TermService\Parameters\WhistlerCAL`

## pseudocode

```c
__int64 __fastcall CRdlsDBManager::PerformPostRdlsDBInit(CRdlsDBManager *this, int a2)
{
  LPBYTE v2; // rbx
  unsigned int updated; // eax
  JBError *v5; // rcx
  unsigned int v6; // edi
  unsigned int v7; // ebx
  HLOCAL v8; // rsi
  const wchar_t *v9; // r9
  __int64 v10; // rcx
  int v11; // eax
  char *v12; // rdi
  int v13; // eax
  int v14; // ecx
  struct _FILETIME *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  struct IRdlsDBConnection *v18; // rax
  struct IRdlsDBConnection *v19; // rsi
  int v20; // eax
  HLOCAL hMem[2]; // [rsp+30h] [rbp-40h] BYREF
  int v23; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  __int64 v25; // [rsp+50h] [rbp-20h] BYREF
  int v26; // [rsp+58h] [rbp-18h]
  __int64 v27; // [rsp+5Ch] [rbp-14h]

  v2 = g_RdlsDBManager;
  updated = CRdlsDBManager::UpdateMaxKeyPackAndLicenseId((CRdlsDBManager *)g_RdlsDBManager);
  v6 = updated;
  if ( updated )
  {
    if ( (updated & 0x180000) != 0 )
    {
      hMem[0] = 0;
      v7 = -(updated & 0xFFE7FFFF);
      JBError::GetJBErrString(v5, v7, (unsigned __int16 **)hMem);
      v8 = hMem[0];
      v9 = &pszSrc;
      if ( hMem[0] )
        v9 = (const wchar_t *)hMem[0];
      *(_OWORD *)hMem = TLS_E_SERVICEINIT;
      TLSLogEvent((struct _EVENT_DESCRIPTOR *)hMem, 0xC0180000, v7, v9);
      if ( v8 )
        LocalFree(v8);
    }
    else
    {
      *(_OWORD *)hMem = TLS_E_SERVICEINIT;
      TLSLogEvent((struct _EVENT_DESCRIPTOR *)hMem, updated);
    }
    return v6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids,
      *((unsigned int *)v2 + 653),
      *((_DWORD *)v2 + 654));
  v10 = *((_QWORD *)v2 + 329);
  v23 = 0;
  hMem[0] = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *, HLOCAL *))(*(_QWORD *)v10 + 88LL))(v10, &v23, hMem);
  v12 = (char *)hMem[0];
  if ( v11 )
    goto LABEL_28;
  if ( hMem[0] )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids,
        *((unsigned int *)hMem[0] + 1),
        *((_DWORD *)hMem[0] + 2));
    if ( a2 == 1
      && !*((_DWORD *)v2 + 652)
      && !*((_DWORD *)v2 + 650)
      && (v13 = *((_DWORD *)v12 + 1)) != 0
      && (v14 = *((_DWORD *)v12 + 2)) != 0 )
    {
      if ( (v13 != *((_DWORD *)v2 + 653) || v14 != *((_DWORD *)v2 + 654))
        && !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 328) + 40LL))(*((_QWORD *)v2 + 328)) )
      {
        CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, &TLS_W_INCONSISTENT_STATUS, 0, 0);
        *((_DWORD *)v2 + 650) = 1;
      }
    }
    else
    {
      v15 = (struct _FILETIME *)(v2 + 2640);
      if ( v12 == (char *)-12LL )
        GetSystemTimeAsFileTime(v15);
      else
        *v15 = *(struct _FILETIME *)(v12 + 12);
    }
LABEL_28:
    if ( hMem[0] )
      LocalFree(hMem[0]);
  }
  v16 = *((_QWORD *)v2 + 330);
  v17 = *((_QWORD *)v2 + 329);
  v25 = 0;
  v26 = 0;
  v27 = v16;
  (*(void (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v17 + 96LL))(v17, 20, &v25);
  ++*((_DWORD *)v2 + 653);
  ++*((_DWORD *)v2 + 654);
  v18 = CRdlsDBManager::AcquireRdlsDBConnection((CRdlsDBManager *)v2);
  v19 = v18;
  if ( (*((_DWORD *)v2 + 650) != 1 && *((_DWORD *)v2 + 651) != 1 || (v6 = TLSRemoveLicensesFromInvalidDatabase(v18)) == 0)
    && (!*((_DWORD *)v2 + 649) || (v6 = TLSRemoveLicensesFromInvalidDatabase(v19)) == 0) )
  {
    v20 = TLSAddTermServCertificatePack(v19);
    if ( !v20 || v20 == -1072693246 )
    {
      hKey = 0;
      v6 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\TermService\\Parameters\\WhistlerCAL",
             0,
             0x20019u,
             &hKey);
      if ( v6 )
        v6 = UpgradeKeyPackVersion(v19);
      else
        RegCloseKey(hKey);
    }
    else
    {
      v6 = -1073676281;
      *(_OWORD *)hMem = TLS_E_SERVICEINIT;
      TLSLogEvent((struct _EVENT_DESCRIPTOR *)hMem, 0xC0010007);
    }
  }
  CRdlsDBManager::ReleaseRdlsDBConnection((CRdlsDBManager *)v2, v19);
  return v6;
}

```

## disassembly

```asm
0x18007eff0  mov     rax, rsp
0x18007eff3  mov     [rax+8], rbx
0x18007eff7  mov     [rax+10h], rsi
0x18007effb  mov     [rax+18h], rdi
0x18007efff  mov     [rax+20h], r12
0x18007f003  push    rbp
0x18007f004  mov     rbp, rsp
0x18007f007  sub     rsp, 70h
0x18007f00b  mov     rax, cs:__security_cookie
0x18007f012  xor     rax, rsp
0x18007f015  mov     [rbp+var_8], rax
0x18007f019  mov     rbx, cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA; CRdlsDBManager * g_RdlsDBManager
0x18007f020  mov     esi, edx
0x18007f022  mov     rcx, rbx; this
0x18007f025  call    ?UpdateMaxKeyPackAndLicenseId@CRdlsDBManager@@QEAAKXZ; CRdlsDBManager::UpdateMaxKeyPackAndLicenseId(void)
0x18007f02a  mov     edi, eax
0x18007f02c  test    eax, eax
0x18007f02e  jz      loc_18007F0BD
0x18007f034  test    eax, 180000h
0x18007f039  jz      short loc_18007F0A1
0x18007f03b  and     [rbp+hMem], 0
0x18007f040  lea     r8, [rbp+hMem]; unsigned __int16 **
0x18007f044  mov     ebx, eax
0x18007f046  and     ebx, 0FFE7FFFFh
0x18007f04c  neg     ebx
0x18007f04e  mov     edx, ebx; int
0x18007f050  call    ?GetJBErrString@JBError@@QEAAHJPEAPEAG@Z; JBError::GetJBErrString(long,ushort * *)
0x18007f055  mov     rsi, [rbp+hMem]
0x18007f059  lea     r9, pszSrc
0x18007f060  movups  xmm0, cs:TLS_E_SERVICEINIT
0x18007f067  test    rsi, rsi
0x18007f06a  lea     rcx, [rbp+hMem]; struct _EVENT_DESCRIPTOR
0x18007f06e  mov     r8d, ebx
0x18007f071  mov     edx, 0C0180000h; unsigned int
0x18007f076  cmovnz  r9, rsi
0x18007f07a  movdqu  xmmword ptr [rbp+hMem], xmm0
0x18007f07f  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x18007f084  test    rsi, rsi
0x18007f087  jz      loc_18007F336
0x18007f08d  mov     rcx, rsi; hMem
0x18007f090  call    cs:__imp_LocalFree
0x18007f097  nop     dword ptr [rax+rax+00h]
0x18007f09c  jmp     loc_18007F336
0x18007f0a1  movups  xmm0, cs:TLS_E_SERVICEINIT
0x18007f0a8  mov     edx, eax; unsigned int
0x18007f0aa  lea     rcx, [rbp+hMem]; struct _EVENT_DESCRIPTOR
0x18007f0ae  movdqu  xmmword ptr [rbp+hMem], xmm0
0x18007f0b3  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x18007f0b8  jmp     loc_18007F336
0x18007f0bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f0c4  lea     r12, WPP_GLOBAL_Control
0x18007f0cb  cmp     rcx, r12
0x18007f0ce  jz      short loc_18007F0FC
0x18007f0d0  test    byte ptr [rcx+1Ch], 40h
0x18007f0d4  jz      short loc_18007F0FC
0x18007f0d6  mov     eax, [rbx+0A38h]
0x18007f0dc  lea     r8, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids
0x18007f0e3  mov     r9d, [rbx+0A34h]
0x18007f0ea  mov     edx, 15h
0x18007f0ef  mov     rcx, [rcx+10h]
0x18007f0f3  mov     dword ptr [rsp+70h+phkResult], eax
0x18007f0f7  call    WPP_SF_DD
0x18007f0fc  mov     rcx, [rbx+0A48h]
0x18007f103  lea     r8, [rbp+hMem]
0x18007f107  and     [rbp+var_30], 0
0x18007f10b  lea     rdx, [rbp+var_30]
0x18007f10f  and     [rbp+hMem], 0
0x18007f114  mov     rax, [rcx]
0x18007f117  mov     rax, [rax+58h]
0x18007f11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f120  mov     rdi, [rbp+hMem]
0x18007f124  test    eax, eax
0x18007f126  jnz     loc_18007F1FA
0x18007f12c  test    rdi, rdi
0x18007f12f  jz      loc_18007F20F
0x18007f135  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f13c  cmp     rcx, r12
0x18007f13f  jz      short loc_18007F165
0x18007f141  test    byte ptr [rcx+1Ch], 40h
0x18007f145  jz      short loc_18007F165
0x18007f147  mov     r9d, [rdi+4]
0x18007f14b  lea     edx, [rax+16h]
0x18007f14e  mov     eax, [rdi+8]
0x18007f151  lea     r8, WPP_4505e5d286323dbdfbdc99a364b6b69a_Traceguids
0x18007f158  mov     rcx, [rcx+10h]
0x18007f15c  mov     dword ptr [rsp+70h+phkResult], eax
0x18007f160  call    WPP_SF_DD
0x18007f165  cmp     esi, 1
0x18007f168  jnz     short loc_18007F1D6
0x18007f16a  cmp     dword ptr [rbx+0A30h], 0
0x18007f171  jnz     short loc_18007F1D6
0x18007f173  cmp     dword ptr [rbx+0A28h], 0
0x18007f17a  jnz     short loc_18007F1D6
0x18007f17c  mov     eax, [rdi+4]
0x18007f17f  test    eax, eax
0x18007f181  jz      short loc_18007F1D6
0x18007f183  mov     ecx, [rdi+8]
0x18007f186  test    ecx, ecx
0x18007f188  jz      short loc_18007F1D6
0x18007f18a  cmp     eax, [rbx+0A34h]
0x18007f190  jnz     short loc_18007F19A
0x18007f192  cmp     ecx, [rbx+0A38h]
0x18007f198  jz      short loc_18007F1FA
0x18007f19a  mov     rcx, [rbx+0A40h]
0x18007f1a1  mov     rax, [rcx]
0x18007f1a4  mov     rax, [rax+28h]
0x18007f1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f1ad  test    eax, eax
0x18007f1af  jnz     short loc_18007F1FA
0x18007f1b1  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x18007f1b4  lea     rdx, TLS_W_INCONSISTENT_STATUS; struct _EVENT_DESCRIPTOR *
0x18007f1bb  xor     r8d, r8d; unsigned int
0x18007f1be  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x18007f1c5  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x18007f1ca  mov     dword ptr [rbx+0A28h], 1
0x18007f1d4  jmp     short loc_18007F1FA
0x18007f1d6  lea     rax, [rdi+0Ch]
0x18007f1da  lea     rcx, [rbx+0A50h]; lpSystemTimeAsFileTime
0x18007f1e1  test    rax, rax
0x18007f1e4  jz      short loc_18007F1EE
0x18007f1e6  mov     rax, [rax]
0x18007f1e9  mov     [rcx], rax
0x18007f1ec  jmp     short loc_18007F1FA
0x18007f1ee  call    cs:__imp_GetSystemTimeAsFileTime
0x18007f1f5  nop     dword ptr [rax+rax+00h]
0x18007f1fa  mov     rcx, [rbp+hMem]; hMem
0x18007f1fe  test    rcx, rcx
0x18007f201  jz      short loc_18007F20F
0x18007f203  call    cs:__imp_LocalFree
0x18007f20a  nop     dword ptr [rax+rax+00h]
0x18007f20f  mov     rax, [rbx+0A50h]
0x18007f216  lea     r8, [rbp+var_20]
0x18007f21a  mov     rcx, [rbx+0A48h]
0x18007f221  mov     edx, 14h
0x18007f226  and     [rbp+var_20], 0
0x18007f22b  and     [rbp+var_18], 0
0x18007f22f  mov     [rbp+var_14], rax
0x18007f233  mov     rax, [rcx]
0x18007f236  mov     rax, [rax+60h]
0x18007f23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f23f  inc     dword ptr [rbx+0A34h]
0x18007f245  mov     rcx, rbx; this
0x18007f248  inc     dword ptr [rbx+0A38h]
0x18007f24e  call    ?AcquireRdlsDBConnection@CRdlsDBManager@@QEAAPEAVIRdlsDBConnection@@XZ; CRdlsDBManager::AcquireRdlsDBConnection(void)
0x18007f253  cmp     dword ptr [rbx+0A28h], 1
0x18007f25a  mov     rsi, rax
0x18007f25d  jnz     short loc_18007F263
0x18007f25f  xor     edx, edx
0x18007f261  jmp     short loc_18007F271
0x18007f263  cmp     dword ptr [rbx+0A2Ch], 1
0x18007f26a  jnz     short loc_18007F286
0x18007f26c  mov     edx, 1
0x18007f271  xor     r8d, r8d
0x18007f274  mov     rcx, rsi; struct IRdlsDBConnection *
0x18007f277  call    TLSRemoveLicensesFromInvalidDatabase
0x18007f27c  mov     edi, eax
0x18007f27e  test    eax, eax
0x18007f280  jnz     loc_18007F32B
0x18007f286  cmp     dword ptr [rbx+0A24h], 0
0x18007f28d  jz      short loc_18007F2A7
0x18007f28f  xor     edx, edx
0x18007f291  mov     rcx, rsi; struct IRdlsDBConnection *
0x18007f294  lea     r8d, [rdx+1]
0x18007f298  call    TLSRemoveLicensesFromInvalidDatabase
0x18007f29d  mov     edi, eax
0x18007f29f  test    eax, eax
0x18007f2a1  jnz     loc_18007F32B
0x18007f2a7  mov     rcx, rsi
0x18007f2aa  call    TLSAddTermServCertificatePack
0x18007f2af  test    eax, eax
0x18007f2b1  jz      short loc_18007F2D8
0x18007f2b3  cmp     eax, 0C0100002h
0x18007f2b8  jz      short loc_18007F2D8
0x18007f2ba  movups  xmm0, cs:TLS_E_SERVICEINIT
0x18007f2c1  mov     edi, 0C0010007h
0x18007f2c6  lea     rcx, [rbp+hMem]; struct _EVENT_DESCRIPTOR
0x18007f2ca  mov     edx, edi; unsigned int
0x18007f2cc  movdqu  xmmword ptr [rbp+hMem], xmm0
0x18007f2d1  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x18007f2d6  jmp     short loc_18007F32B
0x18007f2d8  and     [rbp+hKey], 0
0x18007f2dd  lea     rax, [rbp+hKey]
0x18007f2e1  mov     r9d, 20019h; samDesired
0x18007f2e7  mov     [rsp+70h+phkResult], rax; phkResult
0x18007f2ec  xor     r8d, r8d; ulOptions
0x18007f2ef  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x18007f2f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007f2fd  call    cs:__imp_RegOpenKeyExW
0x18007f304  nop     dword ptr [rax+rax+00h]
0x18007f309  mov     edi, eax
0x18007f30b  test    eax, eax
0x18007f30d  jnz     short loc_18007F321
0x18007f30f  mov     rcx, [rbp+hKey]; hKey
0x18007f313  call    cs:__imp_RegCloseKey
0x18007f31a  nop     dword ptr [rax+rax+00h]
0x18007f31f  jmp     short loc_18007F32B
0x18007f321  mov     rcx, rsi
0x18007f324  call    UpgradeKeyPackVersion
0x18007f329  mov     edi, eax
0x18007f32b  mov     rdx, rsi; struct IRdlsDBConnection *
0x18007f32e  mov     rcx, rbx; this
0x18007f331  call    ?ReleaseRdlsDBConnection@CRdlsDBManager@@QEAAKPEAVIRdlsDBConnection@@@Z; CRdlsDBManager::ReleaseRdlsDBConnection(IRdlsDBConnection *)
0x18007f336  mov     eax, edi
0x18007f338  mov     rcx, [rbp+var_8]
0x18007f33c  xor     rcx, rsp; StackCookie
0x18007f33f  call    __security_check_cookie
0x18007f344  lea     r11, [rsp+70h+var_s0]
0x18007f349  mov     rbx, [r11+10h]
0x18007f34d  mov     rsi, [r11+18h]
0x18007f351  mov     rdi, [r11+20h]
0x18007f355  mov     r12, [r11+28h]
0x18007f359  mov     rsp, r11
0x18007f35c  pop     rbp
0x18007f35d  retn
```
