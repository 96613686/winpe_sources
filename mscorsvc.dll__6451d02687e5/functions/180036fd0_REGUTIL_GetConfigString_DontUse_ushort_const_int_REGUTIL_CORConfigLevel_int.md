# REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)

- ea: `0x180036fd0`
- end: `0x180037340`
- name: `?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z`
- size: `880`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800064a8`
- `0x18001a9d8`
- `0x18002e940`
- `0x18003691c`
- `0x180037c10`

## callees

- `0x180005af8`
- `0x180030530`
- `0x180036ca0`
- `0x180036fd0`
- `0x180037470`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800372ea`
- `ADVAPI32!RegCloseKey` at `0x1800372fe`
- `ADVAPI32!RegCloseKey` at `0x180037312`
- `ADVAPI32!RegCloseKey` at `0x1800372ea`
- `ADVAPI32!RegCloseKey` at `0x1800372fe`
- `ADVAPI32!RegCloseKey` at `0x180037312`
- `ADVAPI32!RegQueryValueExW` at `0x180037120`
- `ADVAPI32!RegQueryValueExW` at `0x1800371d6`
- `ADVAPI32!RegQueryValueExW` at `0x180037267`
- `ADVAPI32!RegQueryValueExW` at `0x1800372d1`
- `ADVAPI32!RegQueryValueExW` at `0x180037120`
- `ADVAPI32!RegQueryValueExW` at `0x1800371d6`
- `ADVAPI32!RegQueryValueExW` at `0x180037267`
- `ADVAPI32!RegQueryValueExW` at `0x1800372d1`
- `ADVAPI32!RegOpenKeyExW` at `0x1800370df`
- `ADVAPI32!RegOpenKeyExW` at `0x180037192`
- `ADVAPI32!RegOpenKeyExW` at `0x180037241`
- `ADVAPI32!RegOpenKeyExW` at `0x1800370df`
- `ADVAPI32!RegOpenKeyExW` at `0x180037192`
- `ADVAPI32!RegOpenKeyExW` at `0x180037241`
- `KERNEL32!HeapFree` at `0x180037072`
- `KERNEL32!HeapFree` at `0x180037072`
- `KERNEL32!GetProcessHeap` at `0x18003705d`
- `KERNEL32!GetProcessHeap` at `0x18003705d`

## pseudocode

```c
// Hidden C++ exception states: #wind=80
unsigned __int16 *__fastcall REGUTIL::GetConfigString_DontUse_(wchar_t *a1, int a2, char a3, int a4)
{
  unsigned __int16 *v7; // rbx
  unsigned __int16 *String; // rax
  HANDLE ProcessHeap; // rax
  PHKEY *v10; // rax
  bool v11; // cl
  const struct NoThrow *v12; // rdx
  unsigned __int16 *v13; // rax
  HKEY v14; // rcx
  PHKEY *v15; // rax
  bool v16; // cl
  const struct NoThrow *v17; // rdx
  unsigned __int16 *v18; // rax
  PHKEY *v19; // rax
  const struct NoThrow *v20; // rdx
  char v21; // cl
  unsigned __int16 *v22; // rax
  DWORD Type; // [rsp+34h] [rbp-4Ch] BYREF
  __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-40h]
  int v27; // [rsp+48h] [rbp-38h]
  HKEY v28; // [rsp+50h] [rbp-30h] BYREF
  int v29; // [rsp+58h] [rbp-28h]
  HKEY v30; // [rsp+60h] [rbp-20h] BYREF
  int v31; // [rsp+68h] [rbp-18h]
  HKEY hKey; // [rsp+70h] [rbp-10h] BYREF
  int v33; // [rsp+78h] [rbp-8h]
  DWORD cbData; // [rsp+C0h] [rbp+40h] BYREF

  hKey = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v29 = 0;
  v7 = 0;
  v26 = 0;
  v27 = 0;
  if ( (a3 & 1) != 0 )
  {
    String = REGUTIL::EnvGetString(a1, a2);
    v7 = String;
    v26 = String;
    if ( String )
    {
      v27 = 1;
      if ( *String )
      {
LABEL_37:
        v27 = 0;
        goto LABEL_39;
      }
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v7);
      v27 = 0;
      v7 = 0;
      v26 = 0;
    }
  }
  if ( (a3 & 0xE) != 0 && (!a4 || (unsigned int)REGUTIL::RegCacheValueNameSeenPerhaps(a1)) )
  {
    if ( (a3 & 2) != 0 )
    {
      v10 = (PHKEY *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                       (__int64)&hKey,
                       &v25);
      v11 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, *v10) == 0;
      if ( *(_QWORD *)v25 )
        *(_DWORD *)(v25 + 8) = 1;
      if ( v11 && !RegQueryValueExW(hKey, a1, 0, &Type, 0, &cbData) && Type == 1 )
      {
        v13 = (unsigned __int16 *)operator new(cbData, v12);
        v7 = v13;
        v26 = v13;
        if ( !v13 )
          goto LABEL_39;
        *v13 = 0;
        v14 = hKey;
        goto LABEL_36;
      }
    }
    if ( (a3 & 4) != 0 )
    {
      v15 = (PHKEY *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                       (__int64)&v30,
                       &v25);
      v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, *v15) == 0;
      if ( *(_QWORD *)v25 )
        *(_DWORD *)(v25 + 8) = 1;
      if ( v16 && !RegQueryValueExW(v30, a1, 0, &Type, 0, &cbData) && Type == 1 )
      {
        v18 = (unsigned __int16 *)operator new(cbData, v17);
        v7 = v18;
        v26 = v18;
        if ( !v18 )
          goto LABEL_39;
        *v18 = 0;
        v14 = v30;
        goto LABEL_36;
      }
    }
    if ( (a3 & 8) != 0 )
    {
      v19 = (PHKEY *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                       (__int64)&v28,
                       &v25);
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fusion", 0, 0x20019u, *v19)
        || RegQueryValueExW(v28, a1, 0, &Type, 0, &cbData)
        || (v21 = 1, Type != 1) )
      {
        v21 = 0;
      }
      if ( *(_QWORD *)v25 )
        *(_DWORD *)(v25 + 8) = 1;
      if ( v21 )
      {
        v22 = (unsigned __int16 *)operator new(cbData, v20);
        v7 = v22;
        v26 = v22;
        if ( v22 )
        {
          *v22 = 0;
          v14 = v28;
LABEL_36:
          v27 = 1;
          RegQueryValueExW(v14, a1, 0, 0, (LPBYTE)v7, &cbData);
          goto LABEL_37;
        }
      }
    }
    v7 = 0;
  }
LABEL_39:
  if ( v29 )
  {
    RegCloseKey(v28);
    v29 = 0;
  }
  if ( v31 )
  {
    RegCloseKey(v30);
    v31 = 0;
  }
  if ( v33 )
  {
    RegCloseKey(hKey);
    v33 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180036fd0  mov     [rsp-28h+arg_0], rbx
0x180036fd5  mov     [rsp-28h+arg_8], rsi
0x180036fda  mov     [rsp-28h+arg_18], rdi
0x180036fdf  push    rbp
0x180036fe0  push    r12
0x180036fe2  push    r13
0x180036fe4  push    r14
0x180036fe6  push    r15
0x180036fe8  mov     rbp, rsp
0x180036feb  sub     rsp, 80h
0x180036ff2  mov     r15d, r9d
0x180036ff5  mov     r14d, r8d
0x180036ff8  mov     rsi, rcx
0x180036ffb  xor     r12d, r12d
0x180036ffe  mov     edi, r12d
0x180037001  mov     [rbp+var_50], r12d
0x180037005  mov     [rbp+hKey], r12
0x180037009  mov     [rbp+var_8], r12d
0x18003700d  mov     [rbp+var_20], r12
0x180037011  mov     [rbp+var_18], r12d
0x180037015  mov     [rbp+var_30], r12
0x180037019  mov     [rbp+var_28], r12d
0x18003701d  mov     ebx, r12d
0x180037020  mov     [rbp+var_40], rbx
0x180037024  mov     [rbp+var_38], r12d
0x180037028  lea     r13d, [r12+1]
0x18003702d  test    r13b, r8b
0x180037030  jz      short loc_180037083
0x180037032  call    ?EnvGetString@REGUTIL@@SAPEAGPEBGH@Z; REGUTIL::EnvGetString(ushort const *,int)
0x180037037  mov     rbx, rax
0x18003703a  mov     [rbp+var_40], rax
0x18003703e  test    rax, rax
0x180037041  jz      short loc_180037083
0x180037043  mov     [rbp+var_38], r13d
0x180037047  cmp     [rax], r12w
0x18003704b  jnz     loc_1800372D7
0x180037051  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037058  test    rax, rax
0x18003705b  jnz     short loc_18003706A
0x18003705d  call    cs:__imp_GetProcessHeap
0x180037063  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003706a  mov     r8, rbx; lpMem
0x18003706d  xor     edx, edx; dwFlags
0x18003706f  mov     rcx, rax; hHeap
0x180037072  call    cs:__imp_HeapFree
0x180037078  mov     [rbp+var_38], r12d
0x18003707c  mov     rbx, r12
0x18003707f  mov     [rbp+var_40], rbx
0x180037083  test    r14b, 0Eh
0x180037087  jz      loc_1800372E0
0x18003708d  test    r15d, r15d
0x180037090  jz      short loc_1800370A2
0x180037092  mov     rcx, rsi; unsigned __int16 *
0x180037095  call    ?RegCacheValueNameSeenPerhaps@REGUTIL@@CAHPEBG@Z; REGUTIL::RegCacheValueNameSeenPerhaps(ushort const *)
0x18003709a  test    eax, eax
0x18003709c  jz      loc_1800372E0
0x1800370a2  mov     ebx, 20019h
0x1800370a7  test    r14b, 2
0x1800370ab  jz      loc_180037155
0x1800370b1  lea     rdx, [rbp+var_48]
0x1800370b5  lea     rcx, [rbp+hKey]
0x1800370b9  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x1800370be  nop
0x1800370bf  mov     [rbp+var_50], r13d
0x1800370c3  mov     rax, [rax]
0x1800370c6  mov     [rsp+80h+phkResult], rax; phkResult
0x1800370cb  mov     r9d, ebx; samDesired
0x1800370ce  xor     r8d, r8d; ulOptions
0x1800370d1  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\.NETFramework"
0x1800370d8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800370df  call    cs:__imp_RegOpenKeyExW
0x1800370e5  test    eax, eax
0x1800370e7  setz    cl
0x1800370ea  mov     edi, r13d
0x1800370ed  and     edi, 0FFFFFFFEh
0x1800370f0  mov     [rbp+var_50], edi
0x1800370f3  mov     rax, [rbp+var_48]
0x1800370f7  cmp     [rax], r12
0x1800370fa  jz      short loc_180037100
0x1800370fc  mov     [rax+8], r13d
0x180037100  test    cl, cl
0x180037102  jz      short loc_180037155
0x180037104  lea     rax, [rbp+cbData]
0x180037108  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18003710d  mov     [rsp+80h+phkResult], r12; lpData
0x180037112  lea     r9, [rbp+Type]; lpType
0x180037116  xor     r8d, r8d; lpReserved
0x180037119  mov     rdx, rsi; lpValueName
0x18003711c  mov     rcx, [rbp+hKey]; hKey
0x180037120  call    cs:__imp_RegQueryValueExW
0x180037126  test    eax, eax
0x180037128  jnz     short loc_180037155
0x18003712a  cmp     [rbp+Type], r13d
0x18003712e  jnz     short loc_180037155
0x180037130  mov     ecx, [rbp+cbData]; dwBytes
0x180037133  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180037138  mov     rbx, rax
0x18003713b  mov     [rbp+var_40], rax
0x18003713f  test    rax, rax
0x180037142  jz      loc_1800372E0
0x180037148  mov     [rax], r12w
0x18003714c  mov     rcx, [rbp+hKey]
0x180037150  jmp     loc_1800372B6
0x180037155  mov     r15, 0FFFFFFFF80000002h
0x18003715c  test    r14b, 4
0x180037160  jz      loc_18003720B
0x180037166  lea     rdx, [rbp+var_48]
0x18003716a  lea     rcx, [rbp+var_20]
0x18003716e  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x180037173  nop
0x180037174  or      edi, 2
0x180037177  mov     [rbp+var_50], edi
0x18003717a  mov     rax, [rax]
0x18003717d  mov     [rsp+80h+phkResult], rax; phkResult
0x180037182  mov     r9d, ebx; samDesired
0x180037185  xor     r8d, r8d; ulOptions
0x180037188  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\.NETFramework"
0x18003718f  mov     rcx, r15; hKey
0x180037192  call    cs:__imp_RegOpenKeyExW
0x180037198  test    eax, eax
0x18003719a  setz    cl
0x18003719d  test    dil, 2
0x1800371a1  jz      short loc_1800371B6
0x1800371a3  and     edi, 0FFFFFFFDh
0x1800371a6  mov     [rbp+var_50], edi
0x1800371a9  mov     rax, [rbp+var_48]
0x1800371ad  cmp     [rax], r12
0x1800371b0  jz      short loc_1800371B6
0x1800371b2  mov     [rax+8], r13d
0x1800371b6  test    cl, cl
0x1800371b8  jz      short loc_18003720B
0x1800371ba  lea     rax, [rbp+cbData]
0x1800371be  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800371c3  mov     [rsp+80h+phkResult], r12; lpData
0x1800371c8  lea     r9, [rbp+Type]; lpType
0x1800371cc  xor     r8d, r8d; lpReserved
0x1800371cf  mov     rdx, rsi; lpValueName
0x1800371d2  mov     rcx, [rbp+var_20]; hKey
0x1800371d6  call    cs:__imp_RegQueryValueExW
0x1800371dc  test    eax, eax
0x1800371de  jnz     short loc_18003720B
0x1800371e0  cmp     [rbp+Type], r13d
0x1800371e4  jnz     short loc_18003720B
0x1800371e6  mov     ecx, [rbp+cbData]; dwBytes
0x1800371e9  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x1800371ee  mov     rbx, rax
0x1800371f1  mov     [rbp+var_40], rax
0x1800371f5  test    rax, rax
0x1800371f8  jz      loc_1800372E0
0x1800371fe  mov     [rax], r12w
0x180037202  mov     rcx, [rbp+var_20]
0x180037206  jmp     loc_1800372B6
0x18003720b  test    r14b, 8
0x18003720f  jz      loc_1800372DD
0x180037215  lea     rdx, [rbp+var_48]
0x180037219  lea     rcx, [rbp+var_30]
0x18003721d  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x180037222  nop
0x180037223  or      edi, 4
0x180037226  mov     [rbp+var_50], edi
0x180037229  mov     rax, [rax]
0x18003722c  mov     [rsp+80h+phkResult], rax; phkResult
0x180037231  mov     r9d, ebx; samDesired
0x180037234  xor     r8d, r8d; ulOptions
0x180037237  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Fusion"
0x18003723e  mov     rcx, r15; hKey
0x180037241  call    cs:__imp_RegOpenKeyExW
0x180037247  test    eax, eax
0x180037249  jnz     short loc_18003727A
0x18003724b  lea     rax, [rbp+cbData]
0x18003724f  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180037254  mov     [rsp+80h+phkResult], r12; lpData
0x180037259  lea     r9, [rbp+Type]; lpType
0x18003725d  xor     r8d, r8d; lpReserved
0x180037260  mov     rdx, rsi; lpValueName
0x180037263  mov     rcx, [rbp+var_30]; hKey
0x180037267  call    cs:__imp_RegQueryValueExW
0x18003726d  test    eax, eax
0x18003726f  jnz     short loc_18003727A
0x180037271  cmp     [rbp+Type], r13d
0x180037275  mov     cl, r13b
0x180037278  jz      short loc_18003727D
0x18003727a  mov     cl, r12b
0x18003727d  test    dil, 4
0x180037281  jz      short loc_180037296
0x180037283  and     edi, 0FFFFFFFBh
0x180037286  mov     [rbp+var_50], edi
0x180037289  mov     rax, [rbp+var_48]
0x18003728d  cmp     [rax], r12
0x180037290  jz      short loc_180037296
0x180037292  mov     [rax+8], r13d
0x180037296  test    cl, cl
0x180037298  jz      short loc_1800372DD
0x18003729a  mov     ecx, [rbp+cbData]; dwBytes
0x18003729d  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x1800372a2  mov     rbx, rax
0x1800372a5  mov     [rbp+var_40], rax
0x1800372a9  test    rax, rax
0x1800372ac  jz      short loc_1800372DD
0x1800372ae  mov     [rax], r12w
0x1800372b2  mov     rcx, [rbp+var_30]; hKey
0x1800372b6  lea     rax, [rbp+cbData]
0x1800372ba  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800372bf  xor     r9d, r9d; lpType
0x1800372c2  mov     [rbp+var_38], r13d
0x1800372c6  mov     [rsp+80h+phkResult], rbx; lpData
0x1800372cb  xor     r8d, r8d; lpReserved
0x1800372ce  mov     rdx, rsi; lpValueName
0x1800372d1  call    cs:__imp_RegQueryValueExW
0x1800372d7  mov     [rbp+var_38], r12d
0x1800372db  jmp     short loc_1800372E0
0x1800372dd  mov     rbx, r12
0x1800372e0  cmp     [rbp+var_28], r12d
0x1800372e4  jz      short loc_1800372F4
0x1800372e6  mov     rcx, [rbp+var_30]; hKey
0x1800372ea  call    cs:__imp_RegCloseKey
0x1800372f0  mov     [rbp+var_28], r12d
0x1800372f4  cmp     [rbp+var_18], r12d
0x1800372f8  jz      short loc_180037308
0x1800372fa  mov     rcx, [rbp+var_20]; hKey
0x1800372fe  call    cs:__imp_RegCloseKey
0x180037304  mov     [rbp+var_18], r12d
0x180037308  cmp     [rbp+var_8], r12d
0x18003730c  jz      short loc_18003731C
0x18003730e  mov     rcx, [rbp+hKey]; hKey
0x180037312  call    cs:__imp_RegCloseKey
0x180037318  mov     [rbp+var_8], r12d
0x18003731c  mov     rax, rbx
0x18003731f  lea     r11, [rsp+80h+var_s0]
0x180037327  mov     rbx, [r11+30h]
0x18003732b  mov     rsi, [r11+38h]
0x18003732f  mov     rdi, [r11+48h]
0x180037333  mov     rsp, r11
0x180037336  pop     r15
0x180037338  pop     r14
0x18003733a  pop     r13
0x18003733c  pop     r12
0x18003733e  pop     rbp
0x18003733f  retn
```
