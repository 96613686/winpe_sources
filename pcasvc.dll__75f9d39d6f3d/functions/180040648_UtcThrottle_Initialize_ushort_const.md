# UtcThrottle::Initialize(ushort const *)

- ea: `0x180040648`
- end: `0x180040932`
- name: `?Initialize@UtcThrottle@@QEAAKPEBG@Z`
- size: `746`
- prototype: `__int64 __fastcall(UtcThrottle *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180040af8`

## callees

- `0x18000c018`
- `0x180012920`
- `0x180040648`
- `0x180041980`
- `0x18007a9cf`
- `0x1800a1c68`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x180040860`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x180040860`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004090e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004090e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040772`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040772`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800406cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800406cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004086f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004086f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800408f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800408f7`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180040831`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1800408b6`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180040831`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1800408b6`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800407b4`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800407f3`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800407b4`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800407f3`

## string_xrefs

- `0x180040789`: `Failed to create event [%d]`
- `0x1800407cc`: `Failed to create named semaphore [%d]`
- `0x180040809`: `Failed to create semaphore [%d]`
- `0x180040875`: `Failed to open named timer [%d]`
- `0x180040889`: `Failed to create named timer [%d]`
- `0x180040738`: `Failed to initialize security descriptor [%d]`
- `0x1800408cd`: `Failed to create timer [%d]`

## pseudocode

```c
__int64 __fastcall UtcThrottle::Initialize(UtcThrottle *this, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // r11
  DWORD LastError; // ebx
  UtcThrottle *v5; // rcx
  const char *v6; // r9
  int v7; // r8d
  HANDLE EventW; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  HANDLE v11; // rax
  DWORD v12; // eax
  int v13; // r8d
  HANDLE v14; // rax
  const char *v15; // r9
  int v16; // ecx
  HANDLE v17; // rax
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES SemaphoreAttributes; // [rsp+38h] [rbp-C8h] BYREF
  char *v21; // [rsp+50h] [rbp-B0h]
  _SECURITY_DESCRIPTOR v22; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR TimerName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+290h] [rbp+190h] BYREF

  memset(&v22, 0, sizeof(v22));
  *(_QWORD *)&SemaphoreAttributes.nLength = 24;
  *(_QWORD *)&SemaphoreAttributes.bInheritHandle = 0;
  hMem = 0;
  memset_0(Name, 0, 0x208u);
  memset_0(TimerName, 0, 0x208u);
  SemaphoreAttributes.lpSecurityDescriptor = &v22;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v21 = (char *)this + 24;
  if ( *((_BYTE *)this + 64) )
    goto LABEL_27;
  if ( (int)StringCchCopyW(Name, 0x104u, L"Global\\AmiUtcThrottlingSemaphore") < 0
    || (int)StringCchCopyW(TimerName, v3, L"Global\\AmiUtcThrottlingTimer2") < 0 )
  {
    LastError = 14;
    goto LABEL_28;
  }
  LastError = UtcThrottle::InitializeSecurityDesc(v5, &v22, (struct _ACL **)&hMem);
  if ( LastError )
  {
    v6 = "Failed to initialize security descriptor [%d]";
    v7 = 123;
LABEL_7:
    AslLogCallPrintf(1, (unsigned int)"UtcThrottle::Initialize", v7, (_DWORD)v6);
    goto LABEL_28;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 2) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v6 = "Failed to create event [%d]";
      v7 = 133;
      goto LABEL_7;
    }
  }
  if ( !*(_QWORD *)this )
  {
    v9 = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, Name);
    *(_QWORD *)this = v9;
    if ( !v9 )
    {
      GetLastError();
      AslLogCallPrintf(
        3,
        (unsigned int)"UtcThrottle::Initialize",
        144,
        (unsigned int)"Failed to create named semaphore [%d]");
      v10 = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, 0);
      *(_QWORD *)this = v10;
      if ( !v10 )
      {
        LastError = GetLastError();
        v6 = "Failed to create semaphore [%d]";
        v7 = 150;
        goto LABEL_7;
      }
    }
  }
  if ( *((_QWORD *)this + 1) )
    goto LABEL_26;
  v11 = CreateWaitableTimerW(&SemaphoreAttributes, 0, TimerName);
  *((_QWORD *)this + 1) = v11;
  if ( v11 )
  {
LABEL_25:
    UtcThrottle::SetTimer(this);
    goto LABEL_26;
  }
  v12 = GetLastError();
  v13 = 183;
  if ( v12 == 183 )
  {
    v14 = OpenWaitableTimerW(0x100000u, 0, TimerName);
    *((_QWORD *)this + 1) = v14;
    if ( v14 )
      goto LABEL_22;
    GetLastError();
    v15 = "Failed to open named timer [%d]";
    v13 = 178;
    v16 = 1;
  }
  else
  {
    v15 = "Failed to create named timer [%d]";
    v16 = 3;
  }
  AslLogCallPrintf(v16, (unsigned int)"UtcThrottle::Initialize", v13, (_DWORD)v15);
LABEL_22:
  if ( !*((_QWORD *)this + 1) )
  {
    v17 = CreateWaitableTimerW(&SemaphoreAttributes, 0, 0);
    *((_QWORD *)this + 1) = v17;
    if ( !v17 )
    {
      LastError = GetLastError();
      v6 = "Failed to create timer [%d]";
      v7 = 197;
      goto LABEL_7;
    }
    goto LABEL_25;
  }
LABEL_26:
  *((_BYTE *)this + 64) = 1;
LABEL_27:
  LastError = 0;
LABEL_28:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( this != (UtcThrottle *)-24LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return LastError;
}

```

## disassembly

```asm
0x180040648  push    rbp
0x18004064a  push    rbx
0x18004064b  push    rdi
0x18004064c  push    r15
0x18004064e  lea     rbp, [rsp-3B8h]
0x180040656  sub     rsp, 4B8h
0x18004065d  mov     rax, cs:__security_cookie
0x180040664  xor     rax, rsp
0x180040667  mov     [rbp+3D0h+var_30], rax
0x18004066e  mov     rdi, rcx
0x180040671  xorps   xmm0, xmm0
0x180040674  xor     eax, eax
0x180040676  movups  xmmword ptr [rsp+4D0h+var_478.Revision], xmm0
0x18004067b  movups  xmmword ptr [rsp+4D0h+var_478.Group], xmm0
0x180040680  mov     [rsp+4D0h+var_478.Dacl], rax
0x180040685  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.nLength], 18h
0x18004068e  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.bInheritHandle], rax
0x180040693  mov     [rsp+4D0h+hMem], rax
0x180040698  mov     ebx, 208h
0x18004069d  mov     r8d, ebx; Size
0x1800406a0  xor     edx, edx; Val
0x1800406a2  lea     rcx, [rbp+3D0h+Name]; void *
0x1800406a9  call    memset_0
0x1800406ae  mov     r8d, ebx; Size
0x1800406b1  xor     edx, edx; Val
0x1800406b3  lea     rcx, [rbp+3D0h+TimerName]; void *
0x1800406b7  call    memset_0
0x1800406bc  lea     rax, [rsp+4D0h+var_478]
0x1800406c1  mov     [rsp+4D0h+SemaphoreAttributes.lpSecurityDescriptor], rax
0x1800406c6  lea     r15, [rdi+18h]
0x1800406ca  mov     rcx, r15; lpCriticalSection
0x1800406cd  call    cs:__imp_EnterCriticalSection
0x1800406d3  mov     [rsp+4D0h+var_480], r15
0x1800406d8  cmp     byte ptr [rdi+40h], 0
0x1800406dc  jnz     loc_1800408EB
0x1800406e2  lea     r8, aGlobalAmiutcth_0; "Global\\AmiUtcThrottlingSemaphore"
0x1800406e9  mov     r11d, 104h
0x1800406ef  mov     edx, r11d; unsigned __int64
0x1800406f2  lea     rcx, [rbp+3D0h+Name]; unsigned __int16 *
0x1800406f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800406fe  test    eax, eax
0x180040700  jns     short loc_18004070C
0x180040702  mov     ebx, 0Eh
0x180040707  jmp     loc_1800408ED
0x18004070c  lea     r8, aGlobalAmiutcth; "Global\\AmiUtcThrottlingTimer2"
0x180040713  mov     rdx, r11; unsigned __int64
0x180040716  lea     rcx, [rbp+3D0h+TimerName]; unsigned __int16 *
0x18004071a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004071f  test    eax, eax
0x180040721  js      short loc_180040702
0x180040723  lea     r8, [rsp+4D0h+hMem]; struct _ACL **
0x180040728  lea     rdx, [rsp+4D0h+var_478]; struct _SECURITY_DESCRIPTOR *
0x18004072d  call    ?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)
0x180040732  mov     ebx, eax
0x180040734  test    eax, eax
0x180040736  jz      short loc_18004075F
0x180040738  lea     r9, aFailedToInitia_0; "Failed to initialize security descripto"...
0x18004073f  mov     r8d, 7Bh ; '{'
0x180040745  mov     [rsp+4D0h+var_4B0], eax
0x180040749  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180040750  mov     ecx, 1
0x180040755  call    AslLogCallPrintf
0x18004075a  jmp     loc_1800408ED
0x18004075f  cmp     qword ptr [rdi+10h], 0
0x180040764  jnz     short loc_180040798
0x180040766  xor     r9d, r9d; lpName
0x180040769  xor     r8d, r8d; bInitialState
0x18004076c  lea     edx, [r9+1]; bManualReset
0x180040770  xor     ecx, ecx; lpEventAttributes
0x180040772  call    cs:__imp_CreateEventW
0x180040778  mov     [rdi+10h], rax
0x18004077c  test    rax, rax
0x18004077f  jnz     short loc_180040798
0x180040781  call    cs:__imp_GetLastError
0x180040787  mov     ebx, eax
0x180040789  lea     r9, aFailedToCreate_60; "Failed to create event [%d]"
0x180040790  mov     r8d, 85h
0x180040796  jmp     short loc_180040745
0x180040798  cmp     qword ptr [rdi], 0
0x18004079c  jnz     short loc_18004081B
0x18004079e  lea     r9, [rbp+3D0h+Name]; lpName
0x1800407a5  mov     ebx, 14h
0x1800407aa  mov     r8d, ebx; lMaximumCount
0x1800407ad  mov     edx, ebx; lInitialCount
0x1800407af  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x1800407b4  call    cs:__imp_CreateSemaphoreW
0x1800407ba  mov     [rdi], rax
0x1800407bd  test    rax, rax
0x1800407c0  jnz     short loc_18004081B
0x1800407c2  call    cs:__imp_GetLastError
0x1800407c8  mov     [rsp+4D0h+var_4B0], eax
0x1800407cc  lea     r9, aFailedToCreate_90; "Failed to create named semaphore [%d]"
0x1800407d3  lea     r8d, [rbx+7Ch]
0x1800407d7  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x1800407de  lea     ecx, [rbx-11h]
0x1800407e1  call    AslLogCallPrintf
0x1800407e6  xor     r9d, r9d; lpName
0x1800407e9  mov     r8d, ebx; lMaximumCount
0x1800407ec  mov     edx, ebx; lInitialCount
0x1800407ee  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x1800407f3  call    cs:__imp_CreateSemaphoreW
0x1800407f9  mov     [rdi], rax
0x1800407fc  test    rax, rax
0x1800407ff  jnz     short loc_18004081B
0x180040801  call    cs:__imp_GetLastError
0x180040807  mov     ebx, eax
0x180040809  lea     r9, aFailedToCreate_86; "Failed to create semaphore [%d]"
0x180040810  mov     r8d, 96h
0x180040816  jmp     loc_180040745
0x18004081b  cmp     qword ptr [rdi+8], 0
0x180040820  jnz     loc_1800408E7
0x180040826  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x18004082a  xor     edx, edx; bManualReset
0x18004082c  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x180040831  call    cs:__imp_CreateWaitableTimerW
0x180040837  mov     [rdi+8], rax
0x18004083b  test    rax, rax
0x18004083e  jnz     loc_1800408DF
0x180040844  call    cs:__imp_GetLastError
0x18004084a  mov     r8d, 0B7h
0x180040850  cmp     eax, r8d
0x180040853  jnz     short loc_180040889
0x180040855  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x180040859  xor     edx, edx; bInheritHandle
0x18004085b  mov     ecx, 100000h; dwDesiredAccess
0x180040860  call    cs:__imp_OpenWaitableTimerW
0x180040866  mov     [rdi+8], rax
0x18004086a  test    rax, rax
0x18004086d  jnz     short loc_1800408A5
0x18004086f  call    cs:__imp_GetLastError
0x180040875  lea     r9, aFailedToOpenNa; "Failed to open named timer [%d]"
0x18004087c  mov     r8d, 0B2h
0x180040882  mov     ecx, 1
0x180040887  jmp     short loc_180040895
0x180040889  lea     r9, aFailedToCreate_97; "Failed to create named timer [%d]"
0x180040890  mov     ecx, 3
0x180040895  mov     [rsp+4D0h+var_4B0], eax
0x180040899  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x1800408a0  call    AslLogCallPrintf
0x1800408a5  cmp     qword ptr [rdi+8], 0
0x1800408aa  jnz     short loc_1800408E7
0x1800408ac  xor     r8d, r8d; lpTimerName
0x1800408af  xor     edx, edx; bManualReset
0x1800408b1  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x1800408b6  call    cs:__imp_CreateWaitableTimerW
0x1800408bc  mov     [rdi+8], rax
0x1800408c0  test    rax, rax
0x1800408c3  jnz     short loc_1800408DF
0x1800408c5  call    cs:__imp_GetLastError
0x1800408cb  mov     ebx, eax
0x1800408cd  lea     r9, aFailedToCreate_41; "Failed to create timer [%d]"
0x1800408d4  mov     r8d, 0C5h
0x1800408da  jmp     loc_180040745
0x1800408df  mov     rcx, rdi; this
0x1800408e2  call    ?SetTimer@UtcThrottle@@AEAAXXZ; UtcThrottle::SetTimer(void)
0x1800408e7  mov     byte ptr [rdi+40h], 1
0x1800408eb  xor     ebx, ebx
0x1800408ed  mov     rcx, [rsp+4D0h+hMem]; hMem
0x1800408f2  test    rcx, rcx
0x1800408f5  jz      short loc_180040906
0x1800408f7  call    cs:__imp_LocalFree
0x1800408fd  mov     [rsp+4D0h+hMem], 0
0x180040906  test    r15, r15
0x180040909  jz      short loc_180040914
0x18004090b  mov     rcx, r15; lpCriticalSection
0x18004090e  call    cs:__imp_LeaveCriticalSection
0x180040914  mov     eax, ebx
0x180040916  mov     rcx, [rbp+3D0h+var_30]
0x18004091d  xor     rcx, rsp; StackCookie
0x180040920  call    __security_check_cookie
0x180040925  add     rsp, 4B8h
0x18004092c  pop     r15
0x18004092e  pop     rdi
0x18004092f  pop     rbx
0x180040930  pop     rbp
0x180040931  retn
```
