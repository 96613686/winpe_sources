# CMultiplexPropertyStore::GetAt(ulong,_tagpropertykey *)

- ea: `0x180031880`
- end: `0x180031ace`
- name: `?GetAt@CMultiplexPropertyStore@@UEAAJKPEAU_tagpropertykey@@@Z`
- size: `590`
- prototype: `__int64 __fastcall(CMultiplexPropertyStore *__hidden this, INT_PTR i, struct _tagpropertykey *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002f9e0`
- `0x180031880`
- `0x180031ae0`
- `0x180048880`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180031a13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180031a13`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180031a71`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180031a71`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180031964`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180031964`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800319bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800319bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800319ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800319ef`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180031915`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180031915`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180031a95`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180031a95`

## string_xrefs

- `0x180031a34`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMultiplexPropertyStore::GetAt(HDPA *this, INT_PTR i, struct _tagpropertykey *a3)
{
  INT_PTR v4; // r15
  char *v6; // rdi
  int v7; // ebx
  int v8; // eax
  DWORD CurrentThreadId; // esi
  HRESULT ApartmentType; // ebx
  int v11; // esi
  GUID *Ptr; // rax
  int v14; // ecx
  int cchValue; // [rsp+20h] [rbp-278h]
  APTTYPE pAptType; // [rsp+30h] [rbp-268h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+34h] [rbp-264h] BYREF
  char *v18; // [rsp+38h] [rbp-260h]
  HRESULT v19; // [rsp+40h] [rbp-258h]
  WCHAR Filename[264]; // [rsp+50h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v4 = (unsigned int)i;
  *a3 = PKEY_Null;
  if ( this )
    v6 = (char *)(this + 8);
  else
    v6 = 0;
  v18 = v6;
  v7 = *((_DWORD *)v6 + 11);
  if ( v7 == 2 )
    goto LABEL_8;
  v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    goto LABEL_5;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v14 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
    `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v14;
  }
  else
  {
    v14 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  }
  if ( v14 != 1 )
    goto LABEL_17;
  if ( v7 == 1 )
  {
    if ( (unsigned int)IsAppCompatModeEnabled(16) )
    {
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_17;
    }
    v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_5:
    if ( v8 != 1 )
      goto LABEL_17;
  }
LABEL_8:
  if ( *((_DWORD *)v6 + 10) == -3 )
    goto LABEL_17;
  CurrentThreadId = 0;
  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_16;
  if ( pAptType == APTTYPE_STA )
  {
LABEL_27:
    CurrentThreadId = GetCurrentThreadId();
    goto LABEL_14;
  }
  if ( pAptType == APTTYPE_MTA )
    goto LABEL_14;
  if ( pAptType != APTTYPE_NA )
  {
    if ( pAptType != APTTYPE_MAINSTA )
      goto LABEL_14;
    goto LABEL_27;
  }
  CurrentThreadId = -1;
LABEL_14:
  if ( CurrentThreadId != *((_DWORD *)v6 + 10) )
    ApartmentType = -2147417842;
LABEL_16:
  if ( ApartmentType < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
      (const char *)(unsigned int)ApartmentType,
      cchValue);
    goto LABEL_19;
  }
LABEL_17:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v6) )
    ApartmentType = 0;
LABEL_19:
  v19 = ApartmentType;
  if ( ApartmentType < 0 )
  {
    v11 = ApartmentType;
  }
  else
  {
    v11 = CMultiplexPropertyStore::_EnsureKeysAndNames((CMultiplexPropertyStore *)this);
    if ( v11 >= 0 )
    {
      Ptr = (GUID *)g_pfn_DPA_GetPtr(this[16], v4);
      if ( Ptr )
      {
        a3->fmtid = *Ptr;
        a3->pid = Ptr[1].Data1;
        v11 = 0;
      }
      else
      {
        v11 = -2147467259;
      }
    }
  }
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180031880  mov     [rsp+arg_18], rbx
0x180031885  push    rbp
0x180031886  push    rsi
0x180031887  push    rdi
0x180031888  push    r14
0x18003188a  push    r15
0x18003188c  sub     rsp, 270h
0x180031893  mov     rax, cs:__security_cookie
0x18003189a  xor     rax, rsp
0x18003189d  mov     [rsp+298h+var_38], rax
0x1800318a5  mov     r14, r8
0x1800318a8  mov     r15d, edx
0x1800318ab  mov     rbp, rcx
0x1800318ae  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x1800318b5  movups  xmmword ptr [r8], xmm0
0x1800318b9  mov     eax, cs:PKEY_Null.pid
0x1800318bf  mov     [r8+10h], eax
0x1800318c3  test    rcx, rcx
0x1800318c6  jz      loc_180031A89
0x1800318cc  lea     rdi, [rcx+40h]
0x1800318d0  mov     [rsp+298h+var_260], rdi
0x1800318d5  mov     ebx, [rdi+2Ch]
0x1800318d8  cmp     ebx, 2
0x1800318db  jz      short loc_1800318FB
0x1800318dd  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800318e3  test    eax, eax
0x1800318e5  jz      loc_180031A06
0x1800318eb  cmp     eax, 1
0x1800318ee  jnz     short loc_180031961
0x1800318f0  jmp     short loc_1800318FB
0x1800318f2  cmp     ebx, 1
0x1800318f5  jz      loc_180031A90
0x1800318fb  cmp     dword ptr [rdi+28h], 0FFFFFFFDh
0x1800318ff  jz      short loc_180031961
0x180031901  xor     esi, esi
0x180031903  mov     [rsp+298h+pAptType], esi
0x180031907  mov     [rsp+298h+pAptQualifier], esi
0x18003190b  lea     rdx, [rsp+298h+pAptQualifier]; pAptQualifier
0x180031910  lea     rcx, [rsp+298h+pAptType]; pAptType
0x180031915  call    cs:__imp_CoGetApartmentType
0x18003191b  mov     ebx, eax
0x18003191d  test    eax, eax
0x18003191f  js      short loc_180031951
0x180031921  mov     ecx, [rsp+298h+pAptType]
0x180031925  test    ecx, ecx
0x180031927  jz      loc_1800319EF
0x18003192d  sub     ecx, 1
0x180031930  jz      short loc_180031948
0x180031932  sub     ecx, 1
0x180031935  jz      loc_1800319FC
0x18003193b  cmp     ecx, 1
0x18003193e  jz      loc_1800319EF
0x180031944  test    eax, eax
0x180031946  js      short loc_180031951
0x180031948  cmp     esi, [rdi+28h]
0x18003194b  jnz     loc_180031AB9
0x180031951  mov     rcx, [rsp+298h]; this
0x180031959  test    ebx, ebx
0x18003195b  js      loc_180031A31
0x180031961  mov     rcx, rdi; lpCriticalSection
0x180031964  call    cs:__imp_TryEnterCriticalSection
0x18003196a  xor     ecx, ecx
0x18003196c  mov     ebx, 8001010Eh
0x180031971  test    eax, eax
0x180031973  cmovnz  ebx, ecx
0x180031976  mov     [rsp+298h+var_258], ebx
0x18003197a  test    ebx, ebx
0x18003197c  js      short loc_1800319EB
0x18003197e  mov     rcx, rbp; this
0x180031981  call    ?_EnsureKeysAndNames@CMultiplexPropertyStore@@AEAAJXZ; CMultiplexPropertyStore::_EnsureKeysAndNames(void)
0x180031986  mov     esi, eax
0x180031988  test    eax, eax
0x18003198a  js      short loc_1800319B5
0x18003198c  mov     rdx, r15; i
0x18003198f  mov     rcx, [rbp+80h]; hdpa
0x180031996  call    cs:g_pfn_DPA_GetPtr
0x18003199c  test    rax, rax
0x18003199f  jz      loc_180031AC3
0x1800319a5  movups  xmm0, xmmword ptr [rax]
0x1800319a8  movups  xmmword ptr [r14], xmm0
0x1800319ac  mov     eax, [rax+10h]
0x1800319af  mov     [r14+10h], eax
0x1800319b3  xor     esi, esi
0x1800319b5  test    ebx, ebx
0x1800319b7  js      short loc_1800319C2
0x1800319b9  mov     rcx, rdi; lpCriticalSection
0x1800319bc  call    cs:__imp_LeaveCriticalSection
0x1800319c2  mov     eax, esi
0x1800319c4  mov     rcx, [rsp+298h+var_38]
0x1800319cc  xor     rcx, rsp; StackCookie
0x1800319cf  call    __security_check_cookie
0x1800319d4  mov     rbx, [rsp+298h+arg_18]
0x1800319dc  add     rsp, 270h
0x1800319e3  pop     r15
0x1800319e5  pop     r14
0x1800319e7  pop     rdi
0x1800319e8  pop     rsi
0x1800319e9  pop     rbp
0x1800319ea  retn
0x1800319eb  mov     esi, ebx
0x1800319ed  jmp     short loc_1800319B5
0x1800319ef  call    cs:__imp_GetCurrentThreadId
0x1800319f5  mov     esi, eax
0x1800319f7  jmp     loc_180031948
0x1800319fc  mov     esi, 0FFFFFFFFh
0x180031a01  jmp     loc_180031948
0x180031a06  mov     r8d, 104h; nSize
0x180031a0c  lea     rdx, [rsp+298h+Filename]; lpFilename
0x180031a11  xor     ecx, ecx; hModule
0x180031a13  call    cs:__imp_GetModuleFileNameW
0x180031a19  test    eax, eax
0x180031a1b  jnz     short loc_180031A4A
0x180031a1d  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180031a23  cmp     ecx, 1
0x180031a26  jnz     loc_180031961
0x180031a2c  jmp     loc_1800318F2
0x180031a31  mov     r9d, ebx; char *
0x180031a34  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180031a3b  mov     edx, 0C8h; void *
0x180031a40  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031a45  jmp     loc_180031976
0x180031a4a  mov     [rsp+298h+bIgnoreCase], 1; bIgnoreCase
0x180031a52  mov     [rsp+298h+cchValue], 0FFFFFFFFh; cchValue
0x180031a5a  lea     r9, StringValue; "\\EXPLORER.EXE"
0x180031a61  mov     r8d, 0FFFFFFFFh; cchSource
0x180031a67  lea     rdx, [rsp+298h+Filename]; lpStringSource
0x180031a6c  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180031a71  call    cs:__imp_FindStringOrdinal
0x180031a77  xor     ecx, ecx
0x180031a79  cmp     eax, 0FFFFFFFFh
0x180031a7c  setnz   cl
0x180031a7f  inc     ecx
0x180031a81  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180031a87  jmp     short loc_180031A23
0x180031a89  xor     edi, edi
0x180031a8b  jmp     loc_1800318D0
0x180031a90  mov     ecx, 10h
0x180031a95  call    cs:__imp_IsAppCompatModeEnabled
0x180031a9b  test    eax, eax
0x180031a9d  jz      short loc_180031AAE
0x180031a9f  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180031aa9  jmp     loc_180031961
0x180031aae  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180031ab4  jmp     loc_1800318EB
0x180031ab9  mov     ebx, 8001010Eh
0x180031abe  jmp     loc_180031951
0x180031ac3  mov     esi, 80004005h
0x180031ac8  jmp     loc_1800319B5
```
