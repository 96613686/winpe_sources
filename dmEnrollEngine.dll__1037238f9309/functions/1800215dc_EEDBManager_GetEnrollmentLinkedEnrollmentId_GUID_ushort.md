# EEDBManager::GetEnrollmentLinkedEnrollmentId(_GUID,ushort * *)

- ea: `0x1800215dc`
- end: `0x1800217cf`
- name: `?GetEnrollmentLinkedEnrollmentId@EEDBManager@@SAJU_GUID@@PEAPEAG@Z`
- size: `499`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800408b0`

## callees

- `0x180005cf0`
- `0x1800071c0`
- `0x18000de50`
- `0x180011938`
- `0x1800215dc`
- `0x1800217d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800216ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800216ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800216db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800216db`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002169d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021744`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002169d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021744`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021654`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021793`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800217ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021654`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021793`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800217ba`

## string_xrefs

- `0x18002168f`: `LinkedEnrollment`
- `0x180021731`: `LinkedEnrollment`
- `0x18002166e`: `LinkedEnrollmentId`
- `0x180021725`: `LinkedEnrollmentId`
- `0x1800216b6`: `Failed to query LinkedEnrollmentId value size`
- `0x180021627`: `Failed to open enrollment key`
- `0x180021761`: `Failed to query LinkedEnrollmentId value`

## pseudocode

```c
__int64 __fastcall EEDBManager::GetEnrollmentLinkedEnrollmentId(struct _GUID *a1, unsigned __int16 **a2)
{
  int v4; // ebx
  const char *v5; // rax
  __int64 v6; // rdx
  LSTATUS ValueW; // eax
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v11; // rbx
  LSTATUS v12; // eax
  unsigned int v13; // edi
  int pdwType; // [rsp+20h] [rbp-30h]
  const char *pvData; // [rsp+28h] [rbp-28h]
  const char *pvDataa; // [rsp+28h] [rbp-28h]
  struct _GUID v17; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD pcbData; // [rsp+70h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int16 *v21; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v17 = *a1;
  v4 = EEDBManager::OpenEnrollmentKey(&v17, 131097, 0, &hKey);
  if ( v4 < 0 )
  {
    v5 = "Failed to open enrollment key";
    v6 = 3708;
LABEL_3:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\database\\src\\dbmanager.cpp",
      (const char *)(unsigned int)v4,
      (int)v5,
      pvData);
LABEL_4:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v4;
  }
  pcbData = 0;
  ValueW = RegGetValueW(hKey, L"LinkedEnrollment", L"LinkedEnrollmentId", 2u, 0, 0, &pcbData);
  v4 = ValueW;
  if ( ValueW > 0 )
    v4 = (unsigned __int16)ValueW | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = "Failed to query LinkedEnrollmentId value size";
    v6 = 3720;
    goto LABEL_3;
  }
  v9 = pcbData;
  ProcessHeap = GetProcessHeap();
  v21 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v9);
  v11 = v21;
  if ( !v21 )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\database\\src\\dbmanager.cpp",
      (const char *)0x8007000ELL,
      pdwType);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v21);
    goto LABEL_4;
  }
  v12 = RegGetValueW(hKey, L"LinkedEnrollment", L"LinkedEnrollmentId", 2u, 0, v21, &pcbData);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( (v13 & 0x80000000) == 0 )
  {
    v21 = 0;
    *a2 = v11;
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v21);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xE96,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\database\\src\\dbmanager.cpp",
      (const char *)v13,
      (int)"Failed to query LinkedEnrollmentId value",
      pvDataa);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v21);
    if ( hKey )
      RegCloseKey(hKey);
    return v13;
  }
}

```

## disassembly

```asm
0x1800215dc  mov     [rsp-18h+arg_8], rbx
0x1800215e1  push    rbp
0x1800215e2  push    rsi
0x1800215e3  push    rdi
0x1800215e4  mov     rbp, rsp
0x1800215e7  sub     rsp, 50h
0x1800215eb  mov     rsi, rdx
0x1800215ee  mov     [rbp+hKey], 0
0x1800215f6  mov     rbx, rcx
0x1800215f9  xor     edx, edx
0x1800215fb  lea     rcx, [rbp+hKey]
0x1800215ff  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180021604  movaps  xmm0, xmmword ptr [rbx]
0x180021607  lea     r9, [rbp+hKey]; HKEY *
0x18002160b  xor     r8d, r8d; unsigned __int16 *
0x18002160e  movdqa  xmmword ptr [rbp+var_10.Data1], xmm0
0x180021613  mov     edx, 20019h; unsigned int
0x180021618  lea     rcx, [rbp+var_10]; struct _GUID
0x18002161c  call    ?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)
0x180021621  mov     ebx, eax
0x180021623  test    eax, eax
0x180021625  jns     short loc_180021661
0x180021627  lea     rax, aFailedToOpenEn; "Failed to open enrollment key"
0x18002162e  mov     edx, 0E7Ch; void *
0x180021633  mov     rcx, [rbp+18h]; this
0x180021637  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002163e  mov     r9d, ebx; char *
0x180021641  mov     [rsp+50h+pdwType], rax; int
0x180021646  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002164b  mov     rcx, [rbp+hKey]; hKey
0x18002164f  test    rcx, rcx
0x180021652  jz      short loc_18002165A
0x180021654  call    cs:__imp_RegCloseKey
0x18002165a  mov     eax, ebx
0x18002165c  jmp     loc_1800217C2
0x180021661  mov     rcx, [rbp+hKey]; hkey
0x180021665  lea     rax, [rbp+arg_0]
0x180021669  mov     [rsp+50h+pcbData], rax; pcbData
0x18002166e  lea     r8, aLinkedenrollme_0; "LinkedEnrollmentId"
0x180021675  mov     edi, 2
0x18002167a  mov     [rsp+50h+pvData], 0; pvData
0x180021683  mov     r9d, edi; dwFlags
0x180021686  mov     [rsp+50h+pdwType], 0; int
0x18002168f  lea     rdx, aLinkedenrollme; "LinkedEnrollment"
0x180021696  mov     [rbp+arg_0], 0
0x18002169d  call    cs:__imp_RegGetValueW
0x1800216a3  mov     ebx, eax
0x1800216a5  test    eax, eax
0x1800216a7  jle     short loc_1800216B2
0x1800216a9  movzx   ebx, ax
0x1800216ac  or      ebx, 80070000h
0x1800216b2  test    ebx, ebx
0x1800216b4  jns     short loc_1800216C7
0x1800216b6  lea     rax, aFailedToQueryL; "Failed to query LinkedEnrollmentId valu"...
0x1800216bd  mov     edx, 0E88h
0x1800216c2  jmp     loc_180021633
0x1800216c7  mov     ebx, [rbp+arg_0]
0x1800216ca  call    cs:__imp_GetProcessHeap
0x1800216d0  mov     r8d, ebx; dwBytes
0x1800216d3  mov     edx, 8; dwFlags
0x1800216d8  mov     rcx, rax; hHeap
0x1800216db  call    cs:__imp_HeapAlloc
0x1800216e1  mov     [rbp+arg_18], rax
0x1800216e5  mov     rbx, rax
0x1800216e8  test    rax, rax
0x1800216eb  jnz     short loc_180021718
0x1800216ed  mov     rcx, [rbp+18h]; this
0x1800216f1  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800216f8  mov     ebx, 8007000Eh
0x1800216fd  mov     edx, 0E8Ch; void *
0x180021702  mov     r9d, ebx; char *
0x180021705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002170a  lea     rcx, [rbp+arg_18]
0x18002170e  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180021713  jmp     loc_18002164B
0x180021718  mov     rcx, [rbp+hKey]; hkey
0x18002171c  lea     rax, [rbp+arg_0]
0x180021720  mov     [rsp+50h+pcbData], rax; pcbData
0x180021725  lea     r8, aLinkedenrollme_0; "LinkedEnrollmentId"
0x18002172c  mov     [rsp+50h+pvData], rbx; char *
0x180021731  lea     rdx, aLinkedenrollme; "LinkedEnrollment"
0x180021738  mov     r9d, edi; dwFlags
0x18002173b  mov     [rsp+50h+pdwType], 0; pdwType
0x180021744  call    cs:__imp_RegGetValueW
0x18002174a  mov     edi, eax
0x18002174c  test    eax, eax
0x18002174e  jle     short loc_180021759
0x180021750  movzx   edi, ax
0x180021753  or      edi, 80070000h
0x180021759  test    edi, edi
0x18002175b  jns     short loc_18002179D
0x18002175d  mov     rcx, [rbp+18h]; this
0x180021761  lea     rax, aFailedToQueryL_0; "Failed to query LinkedEnrollmentId valu"...
0x180021768  mov     r9d, edi; char *
0x18002176b  mov     [rsp+50h+pdwType], rax; int
0x180021770  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180021777  mov     edx, 0E96h; void *
0x18002177c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180021781  lea     rcx, [rbp+arg_18]
0x180021785  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18002178a  mov     rcx, [rbp+hKey]; hKey
0x18002178e  test    rcx, rcx
0x180021791  jz      short loc_180021799
0x180021793  call    cs:__imp_RegCloseKey
0x180021799  mov     eax, edi
0x18002179b  jmp     short loc_1800217C2
0x18002179d  lea     rcx, [rbp+arg_18]
0x1800217a1  mov     [rbp+arg_18], 0
0x1800217a9  mov     [rsi], rbx
0x1800217ac  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800217b1  mov     rcx, [rbp+hKey]; hKey
0x1800217b5  test    rcx, rcx
0x1800217b8  jz      short loc_1800217C0
0x1800217ba  call    cs:__imp_RegCloseKey
0x1800217c0  xor     eax, eax
0x1800217c2  mov     rbx, [rsp+50h+arg_8]
0x1800217c7  add     rsp, 50h
0x1800217cb  pop     rdi
0x1800217cc  pop     rsi
0x1800217cd  pop     rbp
0x1800217ce  retn
```
