# GetValueKey(wchar_t const *,wchar_t const * *,HKEY__ * *)

- ea: `0x18000da54`
- end: `0x18000ddd9`
- name: `?GetValueKey@@YAJPEB_WPEAPEB_WPEAPEAUHKEY__@@@Z`
- size: `901`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, const wchar_t **, HKEY *)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000d500`
- `0x18000d5c0`
- `0x18000d650`
- `0x18000e130`

## callees

- `0x180004074`
- `0x1800049ac`
- `0x18000b95c`
- `0x18000cfe4`
- `0x18000d544`
- `0x18000da54`
- `0x18000e244`
- `0x18000e9c4`
- `0x18001722c`
- `0x180017430`

## import_xrefs

- `msvcrt!wcschr` at `0x18000db61`
- `msvcrt!wcschr` at `0x18000db61`
- `msvcrt!free` at `0x18000dd25`
- `msvcrt!free` at `0x18000ddc1`
- `msvcrt!free` at `0x18000dd25`
- `msvcrt!free` at `0x18000ddc1`
- `ADVAPI32!RegCreateKeyExW` at `0x18000dc73`
- `ADVAPI32!RegCreateKeyExW` at `0x18000dcb7`
- `ADVAPI32!RegCreateKeyExW` at `0x18000dc73`
- `ADVAPI32!RegCreateKeyExW` at `0x18000dcb7`
- `KERNEL32!LeaveCriticalSection` at `0x18000db39`
- `KERNEL32!LeaveCriticalSection` at `0x18000db48`
- `KERNEL32!LeaveCriticalSection` at `0x18000dc2b`
- `KERNEL32!LeaveCriticalSection` at `0x18000dd19`
- `KERNEL32!LeaveCriticalSection` at `0x18000db39`
- `KERNEL32!LeaveCriticalSection` at `0x18000db48`
- `KERNEL32!LeaveCriticalSection` at `0x18000dc2b`
- `KERNEL32!LeaveCriticalSection` at `0x18000dd19`
- `KERNEL32!GetLastError` at `0x18000dcc3`
- `KERNEL32!GetLastError` at `0x18000dcc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetValueKey(STRSAFE_PCNZWCH pszSrc, const wchar_t **a2, HKEY *a3)
{
  unsigned int v6; // esi
  HKEY v7; // rax
  signed int v8; // eax
  unsigned int v9; // eax
  wchar_t *v10; // rax
  __int64 v11; // rdi
  wchar_t *v12; // rbx
  size_t *v13; // r8
  __int64 v14; // rcx
  __int64 AssocAt; // rax
  int v16; // r15d
  DWORD LastError; // eax
  HKEY v18; // rdi
  __int64 v19; // rcx
  unsigned int v20; // eax
  _RTL_CRITICAL_SECTION *v22; // [rsp+B0h] [rbp+40h] BYREF
  DWORD dwDisposition; // [rsp+B8h] [rbp+48h] BYREF
  _RTL_CRITICAL_SECTION *v24; // [rsp+C8h] [rbp+58h] BYREF

  *a2 = pszSrc;
  v6 = 0;
  v7 = g_hKeyFalcon;
  if ( g_hKeyFalcon )
  {
LABEL_9:
    *a3 = v7;
    v10 = wcschr(pszSrc, 0x5Cu);
    if ( !v10 )
      return v6;
    dwDisposition = 0;
    *a2 = v10 + 1;
    v11 = v10 - pszSrc;
    v12 = (wchar_t *)MmAllocate(saturated_mul((unsigned int)(v11 + 1), 2u));
    if ( (_DWORD)v11 == -1 )
    {
      v6 = -2147024809;
    }
    else if ( (unsigned int)(v11 + 1) > 0x7FFFFFFFuLL || (unsigned int)v11 > 0x7FFFFFFE )
    {
      v6 = -2147024809;
      *v12 = 0;
    }
    else
    {
      v6 = StringCopyWorkerW_0(v12, (unsigned int)(v11 + 1), v13, pszSrc, (unsigned int)v11);
      if ( (v6 & 0x80000000) == 0 )
      {
        CCriticalSection::Lock((CCriticalSection *)&stru_180042568);
        LODWORD(v22) = 0;
        AssocAt = CMap<wchar_t const *,wchar_t const *,HKEY__ *,HKEY__ * &>::GetAssocAt(v14, v12, &v22);
        if ( AssocAt )
        {
          *a3 = *(HKEY *)(AssocAt + 24);
          v16 = 1;
        }
        else
        {
          v16 = 0;
        }
        LeaveCriticalSection(&stru_180042568);
        if ( !v16 )
        {
          v6 = RegCreateKeyExW(g_hKeyFalcon, v12, 0, (LPWSTR)&Class, 0, 0x2001Fu, 0, a3, &dwDisposition);
          if ( v6
            && (v6 = RegCreateKeyExW(g_hKeyFalcon, v12, 0, (LPWSTR)&Class, 0, 0x20019u, 0, a3, &dwDisposition)) != 0 )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_28869cbb6516334b80149a365c8c3084_Traceguids,
                LastError);
          }
          else
          {
            v22 = &stru_180042568;
            CCriticalSection::Lock((CCriticalSection *)&stru_180042568);
            v18 = *a3;
            *(_QWORD *)CMap<wchar_t const *,wchar_t const *,HKEY__ *,HKEY__ * &>::operator[](v19, v12) = v18;
            LeaveCriticalSection(&stru_180042568);
            v12 = 0;
          }
        }
LABEL_29:
        free(v12);
        return v6;
      }
    }
    LOWORD(v22) = 420;
    LODWORD(v24) = v6;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v20 = mqwcslen(L"mqsec/register");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v20 + 1),
        L"mqsec/register",
        2,
        &v22,
        4,
        &v24,
        0,
        0);
    }
    goto LABEL_29;
  }
  v24 = &stru_180042568;
  CCriticalSection::Lock((CCriticalSection *)&stru_180042568);
  if ( g_hKeyFalcon || (v8 = _OpenFalconKey(), (v6 = v8) == 0) )
  {
    LeaveCriticalSection(&stru_180042568);
    v7 = g_hKeyFalcon;
    goto LABEL_9;
  }
  if ( v8 < 0 )
  {
    LOWORD(v22) = 400;
    dwDisposition = v8;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v9 = mqwcslen(L"mqsec/register");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v9 + 1),
        L"mqsec/register",
        2,
        &v22,
        4,
        &dwDisposition,
        0,
        0);
    }
  }
  LeaveCriticalSection(&stru_180042568);
  return v6;
}

```

## disassembly

```asm
0x18000da54  push    rbp
0x18000da56  push    rbx
0x18000da57  push    rsi
0x18000da58  push    rdi
0x18000da59  push    r12
0x18000da5b  push    r14
0x18000da5d  push    r15
0x18000da5f  mov     rbp, rsp
0x18000da62  sub     rsp, 70h
0x18000da66  mov     r14, r8
0x18000da69  mov     rbx, rdx
0x18000da6c  mov     r12, rcx
0x18000da6f  mov     [rdx], rcx
0x18000da72  xor     r15d, r15d
0x18000da75  mov     esi, r15d
0x18000da78  lea     rdi, stru_180042568
0x18000da7f  mov     rax, cs:?g_hKeyFalcon@@3VCAutoCloseRegHandle@@A; CAutoCloseRegHandle g_hKeyFalcon
0x18000da86  test    rax, rax
0x18000da89  jnz     loc_18000DB56
0x18000da8f  mov     [rbp+arg_18], rdi
0x18000da93  mov     rcx, rdi; this
0x18000da96  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18000da9b  nop
0x18000da9c  cmp     cs:?g_hKeyFalcon@@3VCAutoCloseRegHandle@@A, r15; CAutoCloseRegHandle g_hKeyFalcon
0x18000daa3  jnz     loc_18000DB45
0x18000daa9  call    ?_OpenFalconKey@@YAJXZ; _OpenFalconKey(void)
0x18000daae  mov     esi, eax
0x18000dab0  test    eax, eax
0x18000dab2  jz      loc_18000DB45
0x18000dab8  test    eax, eax
0x18000daba  jns     short loc_18000DB36
0x18000dabc  mov     eax, 190h
0x18000dac1  mov     word ptr [rbp+arg_0], ax
0x18000dac5  mov     [rbp+dwDisposition], esi
0x18000dac8  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r15; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000dacf  jz      short loc_18000DB36
0x18000dad1  lea     r14, aMqsecRegister; "mqsec/register"
0x18000dad8  mov     rcx, r14; wchar_t *
0x18000dadb  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000dae0  lea     edi, [r15+1]
0x18000dae4  lea     r9d, [rdi+rax]
0x18000dae8  add     r9, r9
0x18000daeb  mov     [rsp+70h+var_20], r15
0x18000daf0  mov     [rsp+70h+var_28], r15
0x18000daf5  lea     rax, [rbp+dwDisposition]
0x18000daf9  mov     [rsp+70h+lpdwDisposition], rax
0x18000dafe  mov     [rsp+70h+phkResult], 4
0x18000db07  lea     rax, [rbp+arg_0]
0x18000db0b  mov     [rsp+70h+lpSecurityAttributes], rax
0x18000db10  mov     qword ptr [rsp+70h+samDesired], 2
0x18000db19  mov     [rsp+70h+cchToCopy], r14
0x18000db1e  mov     r8d, edi
0x18000db21  mov     edx, edi
0x18000db23  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000db2a  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000db2f  lea     rdi, stru_180042568
0x18000db36  mov     rcx, rdi; lpCriticalSection
0x18000db39  call    cs:__imp_LeaveCriticalSection
0x18000db3f  nop
0x18000db40  jmp     loc_18000DDC8
0x18000db45  mov     rcx, rdi; lpCriticalSection
0x18000db48  call    cs:__imp_LeaveCriticalSection
0x18000db4e  nop
0x18000db4f  mov     rax, cs:?g_hKeyFalcon@@3VCAutoCloseRegHandle@@A; CAutoCloseRegHandle g_hKeyFalcon
0x18000db56  mov     [r14], rax
0x18000db59  mov     edx, 5Ch ; '\'; Ch
0x18000db5e  mov     rcx, r12; Str
0x18000db61  call    cs:__imp_wcschr
0x18000db67  mov     rdi, rax
0x18000db6a  test    rax, rax
0x18000db6d  jz      loc_18000DDC8
0x18000db73  mov     [rbp+dwDisposition], r15d
0x18000db77  lea     rcx, [rax+2]
0x18000db7b  mov     [rbx], rcx
0x18000db7e  sub     rdi, r12
0x18000db81  sar     rdi, 1
0x18000db84  lea     r15d, [rdi+1]
0x18000db88  mov     eax, 2
0x18000db8d  mul     r15
0x18000db90  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000db97  cmovb   rax, rcx
0x18000db9b  mov     rcx, rax; unsigned __int64
0x18000db9e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000dba3  mov     rbx, rax
0x18000dba6  mov     [rbp+var_10], rax
0x18000dbaa  test    r15, r15
0x18000dbad  jz      loc_18000DD31
0x18000dbb3  cmp     r15, 7FFFFFFFh
0x18000dbba  jbe     short loc_18000DBC6
0x18000dbbc  mov     esi, 80070057h
0x18000dbc1  jmp     loc_18000DD3B
0x18000dbc6  cmp     edi, 7FFFFFFEh
0x18000dbcc  ja      short loc_18000DBBC
0x18000dbce  mov     eax, edi
0x18000dbd0  mov     [rsp+70h+cchToCopy], rax; cchToCopy
0x18000dbd5  mov     r9, r12; pszSrc
0x18000dbd8  mov     rdx, r15; cchDest
0x18000dbdb  mov     rcx, rbx; pszDest
0x18000dbde  call    StringCopyWorkerW_0
0x18000dbe3  mov     esi, eax
0x18000dbe5  test    eax, eax
0x18000dbe7  js      loc_18000DD40
0x18000dbed  lea     r12, stru_180042568
0x18000dbf4  mov     rcx, r12; this
0x18000dbf7  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18000dbfc  mov     dword ptr [rbp+arg_0], 0
0x18000dc03  lea     r8, [rbp+arg_0]
0x18000dc07  mov     rdx, rbx
0x18000dc0a  call    ?GetAssocAt@?$CMap@PEB_WPEB_WPEAUHKEY__@@AEAPEAU1@@@IEBAPEAUCAssoc@1@PEB_WAEAI@Z; CMap<wchar_t const *,wchar_t const *,HKEY__ *,HKEY__ * &>::GetAssocAt(wchar_t const *,uint &)
0x18000dc0f  mov     edi, 1
0x18000dc14  test    rax, rax
0x18000dc17  jnz     short loc_18000DC1E
0x18000dc19  xor     r15d, r15d
0x18000dc1c  jmp     short loc_18000DC28
0x18000dc1e  mov     rax, [rax+18h]
0x18000dc22  mov     [r14], rax
0x18000dc25  mov     r15d, edi
0x18000dc28  mov     rcx, r12; lpCriticalSection
0x18000dc2b  call    cs:__imp_LeaveCriticalSection
0x18000dc31  nop
0x18000dc32  test    r15d, r15d
0x18000dc35  jnz     loc_18000DD22
0x18000dc3b  lea     rax, [rbp+dwDisposition]
0x18000dc3f  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18000dc44  mov     [rsp+70h+phkResult], r14; phkResult
0x18000dc49  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000dc52  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x18000dc5a  mov     dword ptr [rsp+70h+cchToCopy], r15d; dwOptions
0x18000dc5f  lea     r9, Class; lpClass
0x18000dc66  xor     r8d, r8d; Reserved
0x18000dc69  mov     rdx, rbx; lpSubKey
0x18000dc6c  mov     rcx, cs:?g_hKeyFalcon@@3VCAutoCloseRegHandle@@A; hKey
0x18000dc73  call    cs:__imp_RegCreateKeyExW
0x18000dc79  mov     esi, eax
0x18000dc7b  test    eax, eax
0x18000dc7d  jz      short loc_18000DCFB
0x18000dc7f  lea     rax, [rbp+dwDisposition]
0x18000dc83  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18000dc88  mov     [rsp+70h+phkResult], r14; phkResult
0x18000dc8d  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000dc96  mov     [rsp+70h+samDesired], 20019h; samDesired
0x18000dc9e  mov     dword ptr [rsp+70h+cchToCopy], r15d; dwOptions
0x18000dca3  lea     r9, Class; lpClass
0x18000dcaa  xor     r8d, r8d; Reserved
0x18000dcad  mov     rdx, rbx; lpSubKey
0x18000dcb0  mov     rcx, cs:?g_hKeyFalcon@@3VCAutoCloseRegHandle@@A; hKey
0x18000dcb7  call    cs:__imp_RegCreateKeyExW
0x18000dcbd  mov     esi, eax
0x18000dcbf  test    eax, eax
0x18000dcc1  jz      short loc_18000DCFB
0x18000dcc3  call    cs:__imp_GetLastError
0x18000dcc9  lea     rdx, WPP_GLOBAL_Control
0x18000dcd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcd7  cmp     rcx, rdx
0x18000dcda  jz      short loc_18000DD22
0x18000dcdc  test    [rcx+1Ch], dil
0x18000dce0  jz      short loc_18000DD22
0x18000dce2  lea     edx, [r15+0Ah]
0x18000dce6  mov     r9d, eax
0x18000dce9  lea     r8, WPP_28869cbb6516334b80149a365c8c3084_Traceguids
0x18000dcf0  mov     rcx, [rcx+10h]
0x18000dcf4  call    WPP_SF_d
0x18000dcf9  jmp     short loc_18000DD22
0x18000dcfb  mov     [rbp+arg_0], r12
0x18000dcff  mov     rcx, r12; this
0x18000dd02  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18000dd07  nop
0x18000dd08  mov     rdi, [r14]
0x18000dd0b  mov     rdx, rbx
0x18000dd0e  call    ??A?$CMap@PEB_WPEB_WPEAUHKEY__@@AEAPEAU1@@@QEAAAEAPEAUHKEY__@@PEB_W@Z; CMap<wchar_t const *,wchar_t const *,HKEY__ *,HKEY__ * &>::operator[](wchar_t const *)
0x18000dd13  mov     [rax], rdi
0x18000dd16  mov     rcx, r12; lpCriticalSection
0x18000dd19  call    cs:__imp_LeaveCriticalSection
0x18000dd1f  nop
0x18000dd20  xor     ebx, ebx
0x18000dd22  mov     rcx, rbx; Block
0x18000dd25  call    cs:__imp_free
0x18000dd2b  nop
0x18000dd2c  jmp     loc_18000DDC8
0x18000dd31  mov     esi, 80070057h
0x18000dd36  test    r15, r15
0x18000dd39  jz      short loc_18000DD40
0x18000dd3b  xor     eax, eax
0x18000dd3d  mov     [rbx], ax
0x18000dd40  mov     eax, 1A4h
0x18000dd45  mov     word ptr [rbp+arg_0], ax
0x18000dd49  mov     dword ptr [rbp+arg_18], esi
0x18000dd4c  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000dd54  jz      short loc_18000DDBE
0x18000dd56  lea     r14, aMqsecRegister; "mqsec/register"
0x18000dd5d  mov     rcx, r14; wchar_t *
0x18000dd60  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000dd65  mov     edi, 1
0x18000dd6a  lea     r9d, [rdi+rax]
0x18000dd6e  add     r9, r9
0x18000dd71  mov     [rsp+70h+var_20], 0
0x18000dd7a  mov     [rsp+70h+var_28], 0
0x18000dd83  lea     rax, [rbp+arg_18]
0x18000dd87  mov     [rsp+70h+lpdwDisposition], rax
0x18000dd8c  mov     [rsp+70h+phkResult], 4
0x18000dd95  lea     rax, [rbp+arg_0]
0x18000dd99  mov     [rsp+70h+lpSecurityAttributes], rax
0x18000dd9e  mov     qword ptr [rsp+70h+samDesired], 2
0x18000dda7  mov     [rsp+70h+cchToCopy], r14
0x18000ddac  mov     r8d, edi
0x18000ddaf  mov     edx, edi
0x18000ddb1  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000ddb8  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000ddbd  nop
0x18000ddbe  mov     rcx, rbx; Block
0x18000ddc1  call    cs:__imp_free
0x18000ddc7  nop
0x18000ddc8  mov     eax, esi
0x18000ddca  add     rsp, 70h
0x18000ddce  pop     r15
0x18000ddd0  pop     r14
0x18000ddd2  pop     r12
0x18000ddd4  pop     rdi
0x18000ddd5  pop     rsi
0x18000ddd6  pop     rbx
0x18000ddd7  pop     rbp
0x18000ddd8  retn
```
