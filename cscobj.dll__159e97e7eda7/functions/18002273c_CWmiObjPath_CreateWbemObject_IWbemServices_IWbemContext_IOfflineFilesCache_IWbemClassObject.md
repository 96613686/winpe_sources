# CWmiObjPath::CreateWbemObject(IWbemServices *,IWbemContext *,IOfflineFilesCache *,IWbemClassObject * *)

- ea: `0x18002273c`
- end: `0x1800228d1`
- name: `?CreateWbemObject@CWmiObjPath@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIOfflineFilesCache@@PEAPEAUIWbemClassObject@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(CWmiObjPath *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IOfflineFilesCache *, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024f40`

## callees

- `0x18000b7c0`
- `0x1800167e0`
- `0x180016a74`
- `0x18001d574`
- `0x18002273c`
- `0x1800228d8`
- `0x1800229ac`
- `0x180022a5c`
- `0x180022b0c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800227ad`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800227f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022852`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022890`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800227ad`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800227f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022852`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022890`

## string_xrefs

- `0x1800227dd`: `Win32_OfflineFilesCache`
- `0x18002286f`: `Win32_OfflineFilesMachineConfiguration`
- `0x180022831`: `Win32_OfflineFilesUserConfiguration`

## pseudocode

```c
__int64 __fastcall CWmiObjPath::CreateWbemObject(
        CWmiObjPath *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IOfflineFilesCache *a4,
        struct IWbemClassObject **a5)
{
  int ClassName; // ebx
  CWmiObjPath *v11; // rcx
  struct IOfflineFilesCache *v12; // r9
  CWmiObjPath *v13; // rcx
  struct IOfflineFilesCache *v14; // r9
  _BYTE v16[32]; // [rsp+30h] [rbp-278h] BYREF
  WCHAR String1[264]; // [rsp+50h] [rbp-258h] BYREF

  ClassName = CWmiObjPath::_GetClassName(this, String1, (unsigned int)a3);
  if ( ClassName >= 0 )
  {
    if ( CompareStringW(0x7Fu, 1u, String1, -1, L"Win32_OfflineFilesItem", -1) == 2 )
      return (unsigned int)CWmiObjPath::_CreateCscItemObject(this, a2, a3, a4, a5);
    if ( CompareStringW(0x7Fu, 1u, String1, -1, L"Win32_OfflineFilesCache", -1) == 2 )
    {
      CCscWmiCacheObject::CCscWmiCacheObject((CCscWmiCacheObject *)v16, a4);
      ClassName = CCscWmiObject::CreateWbemClassObject((CCscWmiObject *)v16, a2, a3, a5);
      CCscWmiCacheObject::~CCscWmiCacheObject((CCscWmiCacheObject *)v16);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, String1, -1, L"Win32_OfflineFilesUserConfiguration", -1) == 2 )
        return (unsigned int)CWmiObjPath::_CreateCscUserConfigObject(v11, a2, a3, v12, a5);
      if ( CompareStringW(0x7Fu, 1u, String1, -1, L"Win32_OfflineFilesMachineConfiguration", -1) == 2 )
        return (unsigned int)CWmiObjPath::_CreateCscMachineConfigObject(v13, a2, a3, v14, a5);
    }
  }
  return (unsigned int)ClassName;
}

```

## disassembly

```asm
0x18002273c  push    rbx
0x18002273e  push    rbp
0x18002273f  push    rsi
0x180022740  push    rdi
0x180022741  push    r12
0x180022743  push    r14
0x180022745  push    r15
0x180022747  sub     rsp, 270h
0x18002274e  mov     rax, cs:__security_cookie
0x180022755  xor     rax, rsp
0x180022758  mov     [rsp+2A8h+var_48], rax
0x180022760  mov     rbp, [rsp+2A8h+arg_20]
0x180022768  mov     rdi, rdx
0x18002276b  lea     rdx, [rsp+2A8h+String1]; unsigned __int16 *
0x180022770  mov     r14, r9
0x180022773  mov     rsi, r8
0x180022776  mov     r15, rcx
0x180022779  call    ?_GetClassName@CWmiObjPath@@AEAAJPEAGK@Z; CWmiObjPath::_GetClassName(ushort *,ulong)
0x18002277e  mov     ebx, eax
0x180022780  test    eax, eax
0x180022782  js      loc_1800228AD
0x180022788  or      r12d, 0FFFFFFFFh
0x18002278c  lea     rax, CSCWMI_STR_OFFLINEFILESITEM; "Win32_OfflineFilesItem"
0x180022793  mov     [rsp+2A8h+cchCount2], r12d; cchCount2
0x180022798  lea     r8, [rsp+2A8h+String1]; lpString1
0x18002279d  mov     r9d, r12d; cchCount1
0x1800227a0  mov     [rsp+2A8h+lpString2], rax; lpString2
0x1800227a5  lea     edx, [r12+2]; dwCmpFlags
0x1800227aa  lea     ecx, [rdx+7Eh]; Locale
0x1800227ad  call    cs:__imp_CompareStringW
0x1800227b3  cmp     eax, 2
0x1800227b6  jnz     short loc_1800227D3
0x1800227b8  mov     r9, r14; struct IOfflineFilesCache *
0x1800227bb  mov     [rsp+2A8h+lpString2], rbp; struct IWbemClassObject **
0x1800227c0  mov     r8, rsi; struct IWbemContext *
0x1800227c3  mov     rdx, rdi; struct IWbemServices *
0x1800227c6  mov     rcx, r15; this
0x1800227c9  call    ?_CreateCscItemObject@CWmiObjPath@@AEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIOfflineFilesCache@@PEAPEAUIWbemClassObject@@@Z; CWmiObjPath::_CreateCscItemObject(IWbemServices *,IWbemContext *,IOfflineFilesCache *,IWbemClassObject * *)
0x1800227ce  jmp     loc_1800228AB
0x1800227d3  mov     edx, 1; dwCmpFlags
0x1800227d8  mov     [rsp+2A8h+cchCount2], r12d; cchCount2
0x1800227dd  lea     rax, CSCWMI_STR_OFFLINEFILESCACHE; "Win32_OfflineFilesCache"
0x1800227e4  mov     r9d, r12d; cchCount1
0x1800227e7  lea     r8, [rsp+2A8h+String1]; lpString1
0x1800227ec  mov     [rsp+2A8h+lpString2], rax; lpString2
0x1800227f1  lea     r15d, [rdx+7Eh]
0x1800227f5  mov     ecx, r15d; Locale
0x1800227f8  call    cs:__imp_CompareStringW
0x1800227fe  cmp     eax, 2
0x180022801  jnz     short loc_180022831
0x180022803  mov     rdx, r14; struct IOfflineFilesCache *
0x180022806  lea     rcx, [rsp+2A8h+var_278]; this
0x18002280b  call    ??0CCscWmiCacheObject@@QEAA@PEAUIOfflineFilesCache@@@Z; CCscWmiCacheObject::CCscWmiCacheObject(IOfflineFilesCache *)
0x180022810  mov     r9, rbp; struct IWbemClassObject **
0x180022813  lea     rcx, [rsp+2A8h+var_278]; this
0x180022818  mov     r8, rsi; struct IWbemContext *
0x18002281b  mov     rdx, rdi; struct IWbemServices *
0x18002281e  call    ?CreateWbemClassObject@CCscWmiObject@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z; CCscWmiObject::CreateWbemClassObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)
0x180022823  lea     rcx, [rsp+2A8h+var_278]; this
0x180022828  mov     ebx, eax
0x18002282a  call    ??1CCscWmiCacheObject@@UEAA@XZ; CCscWmiCacheObject::~CCscWmiCacheObject(void)
0x18002282f  jmp     short loc_1800228AD
0x180022831  lea     rax, CSCWMI_STR_OFFLINEFILESUSERCONFIGURATION; "Win32_OfflineFilesUserConfiguration"
0x180022838  mov     [rsp+2A8h+cchCount2], r12d; cchCount2
0x18002283d  mov     r9d, r12d; cchCount1
0x180022840  mov     [rsp+2A8h+lpString2], rax; lpString2
0x180022845  lea     r8, [rsp+2A8h+String1]; lpString1
0x18002284a  mov     edx, 1; dwCmpFlags
0x18002284f  mov     ecx, r15d; Locale
0x180022852  call    cs:__imp_CompareStringW
0x180022858  cmp     eax, 2
0x18002285b  jnz     short loc_18002286F
0x18002285d  mov     r8, rsi; struct IWbemContext *
0x180022860  mov     [rsp+2A8h+lpString2], rbp; struct IWbemClassObject **
0x180022865  mov     rdx, rdi; struct IWbemServices *
0x180022868  call    ?_CreateCscUserConfigObject@CWmiObjPath@@AEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIOfflineFilesCache@@PEAPEAUIWbemClassObject@@@Z; CWmiObjPath::_CreateCscUserConfigObject(IWbemServices *,IWbemContext *,IOfflineFilesCache *,IWbemClassObject * *)
0x18002286d  jmp     short loc_1800228AB
0x18002286f  lea     rax, CSCWMI_STR__OFFLINEFILESMACHINECONFIGURATION; "Win32_OfflineFilesMachineConfiguration"
0x180022876  mov     [rsp+2A8h+cchCount2], r12d; cchCount2
0x18002287b  mov     r9d, r12d; cchCount1
0x18002287e  mov     [rsp+2A8h+lpString2], rax; lpString2
0x180022883  lea     r8, [rsp+2A8h+String1]; lpString1
0x180022888  mov     edx, 1; dwCmpFlags
0x18002288d  mov     ecx, r15d; Locale
0x180022890  call    cs:__imp_CompareStringW
0x180022896  cmp     eax, 2
0x180022899  jnz     short loc_1800228AD
0x18002289b  mov     r8, rsi; struct IWbemContext *
0x18002289e  mov     [rsp+2A8h+lpString2], rbp; struct IWbemClassObject **
0x1800228a3  mov     rdx, rdi; struct IWbemServices *
0x1800228a6  call    ?_CreateCscMachineConfigObject@CWmiObjPath@@AEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIOfflineFilesCache@@PEAPEAUIWbemClassObject@@@Z; CWmiObjPath::_CreateCscMachineConfigObject(IWbemServices *,IWbemContext *,IOfflineFilesCache *,IWbemClassObject * *)
0x1800228ab  mov     ebx, eax
0x1800228ad  mov     eax, ebx
0x1800228af  mov     rcx, [rsp+2A8h+var_48]
0x1800228b7  xor     rcx, rsp; StackCookie
0x1800228ba  call    __security_check_cookie
0x1800228bf  add     rsp, 270h
0x1800228c6  pop     r15
0x1800228c8  pop     r14
0x1800228ca  pop     r12
0x1800228cc  pop     rdi
0x1800228cd  pop     rsi
0x1800228ce  pop     rbp
0x1800228cf  pop     rbx
0x1800228d0  retn
```
