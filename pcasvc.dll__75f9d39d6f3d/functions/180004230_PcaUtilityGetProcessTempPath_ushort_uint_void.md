# PcaUtilityGetProcessTempPath(ushort *,uint,void *)

- ea: `0x180004230`
- end: `0x18000449c`
- name: `?PcaUtilityGetProcessTempPath@@YAKPEAGIPEAX@Z`
- size: `620`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003af4`

## callees

- `0x180004230`
- `0x18000dc08`
- `0x180012920`
- `0x180013334`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000445d`
- `ntdll!RtlFreeHeap` at `0x18000445d`
- `ntdll!RtlAllocateHeap` at `0x1800042e3`
- `ntdll!RtlAllocateHeap` at `0x1800042e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000429c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000436a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000429c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000436a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800043e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800043e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004290`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004440`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004440`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000432e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000432e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000446d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000446d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004360`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004360`

## string_xrefs

- `0x1800042b8`: `PcaUtilityGetProcessTempPath`
- `0x1800042fe`: `PcaUtilityGetProcessTempPath`
- `0x1800042a6`: `Failed to open process token [%u]`
- `0x1800043c4`: `ProfileImagePath`
- `0x18000433e`: `GetTokenInformation failed [%u]`
- `0x180004403`: `\AppData\Local\Temp`
- `0x18000441e`: `Failed to cat temp path [%u]`
- `0x180004370`: `Failed to get sid string [%u]`
- `0x1800043a1`: `Failed to make path for temp directory [%u]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PcaUtilityGetProcessTempPath(unsigned __int16 *a1, __int64 a2, void *a3)
{
  PSID *Heap; // rsi
  const char *v5; // r9
  int v6; // r8d
  unsigned int ValueW; // ebx
  DWORD LastError; // eax
  int v9; // eax
  int v10; // eax
  DWORD ReturnLength; // [rsp+20h] [rbp-E0h]
  DWORD v13; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  v13 = 0;
  *a1 = 0;
  pcbData = 520;
  TokenHandle = 0;
  StringSid = 0;
  if ( !OpenProcessToken(a3, 0x2000Au, &TokenHandle) )
  {
    Heap = 0;
    ReturnLength = GetLastError();
    v5 = "Failed to open process token [%u]";
    v6 = 1615;
    ValueW = ReturnLength;
LABEL_3:
    AslLogCallPrintf(1, (unsigned int)"PcaUtilityGetProcessTempPath", v6, (_DWORD)v5);
    goto LABEL_18;
  }
  ValueW = 8;
  Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x5Cu);
  if ( !Heap )
  {
    AslLogCallPrintf(1, (unsigned int)"PcaUtilityGetProcessTempPath", 1627, (unsigned int)"Out of memory");
    goto LABEL_18;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, Heap, 0x5Cu, &v13) )
  {
    LastError = GetLastError();
    v5 = "GetTokenInformation failed [%u]";
    v6 = 1641;
LABEL_8:
    ValueW = LastError;
    goto LABEL_3;
  }
  if ( !ConvertSidToStringSidW(*Heap, &StringSid) )
  {
    LastError = GetLastError();
    v5 = "Failed to get sid string [%u]";
    v6 = 1647;
    goto LABEL_8;
  }
  v9 = StringCchPrintfW(SubKey, 0x104u, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\%s", StringSid);
  if ( v9 < 0 )
  {
    ValueW = (unsigned __int16)v9;
    v5 = "Failed to make path for temp directory [%u]";
    v6 = 1658;
    goto LABEL_3;
  }
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"ProfileImagePath", 0x10000004u, 0, a1, &pcbData);
  if ( ValueW )
  {
    v5 = "Error querying value [%u]";
    v6 = 1670;
    goto LABEL_3;
  }
  v10 = StringCchCatW(a1, 0x104u, L"\\AppData\\Local\\Temp");
  if ( v10 < 0 )
  {
    ValueW = (unsigned __int16)v10;
    v5 = "Failed to cat temp path [%u]";
    v6 = 1681;
    goto LABEL_3;
  }
  ValueW = 0;
LABEL_18:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( StringSid )
    LocalFree(StringSid);
  return ValueW;
}

```

## disassembly

```asm
0x180004230  mov     [rsp-8+arg_8], rbx
0x180004235  mov     [rsp-8+arg_18], rsi
0x18000423a  push    rbp
0x18000423b  push    rdi
0x18000423c  push    r14
0x18000423e  lea     rbp, [rsp-180h]
0x180004246  sub     rsp, 280h
0x18000424d  mov     rax, cs:__security_cookie
0x180004254  xor     rax, rsp
0x180004257  mov     [rbp+190h+var_20], rax
0x18000425e  xor     eax, eax
0x180004260  mov     [rsp+290h+var_250], 0
0x180004268  mov     r9, r8
0x18000426b  mov     [rcx], ax
0x18000426e  mov     r14, rcx
0x180004271  mov     [rsp+290h+var_24C], 208h
0x180004279  mov     rcx, r9; ProcessHandle
0x18000427c  mov     [rsp+290h+TokenHandle], rax
0x180004281  lea     r8, [rsp+290h+TokenHandle]; TokenHandle
0x180004286  mov     [rsp+290h+StringSid], rax
0x18000428b  mov     edx, 2000Ah; DesiredAccess
0x180004290  call    cs:__imp_OpenProcessToken
0x180004296  test    eax, eax
0x180004298  jnz     short loc_1800042C9
0x18000429a  xor     esi, esi
0x18000429c  call    cs:__imp_GetLastError
0x1800042a2  mov     dword ptr [rsp+290h+ReturnLength], eax
0x1800042a6  lea     r9, aFailedToOpenPr_0; "Failed to open process token [%u]"
0x1800042ad  mov     r8d, 64Fh
0x1800042b3  lea     ecx, [rsi+1]
0x1800042b6  mov     ebx, eax
0x1800042b8  lea     rdx, aPcautilitygetp_0; "PcaUtilityGetProcessTempPath"
0x1800042bf  call    AslLogCallPrintf
0x1800042c4  jmp     loc_180004436
0x1800042c9  mov     rcx, gs:60h
0x1800042d2  mov     edi, 5Ch ; '\'
0x1800042d7  mov     r8d, edi; Size
0x1800042da  mov     rcx, [rcx+30h]; HeapHandle
0x1800042de  lea     ebx, [rdi-54h]
0x1800042e1  mov     edx, ebx; Flags
0x1800042e3  call    cs:__imp_RtlAllocateHeap
0x1800042e9  mov     rsi, rax
0x1800042ec  test    rax, rax
0x1800042ef  jnz     short loc_180004312
0x1800042f1  lea     r9, aOutOfMemory; "Out of memory"
0x1800042f8  mov     r8d, 65Bh
0x1800042fe  lea     rdx, aPcautilitygetp_0; "PcaUtilityGetProcessTempPath"
0x180004305  lea     ecx, [rdi-5Bh]
0x180004308  call    AslLogCallPrintf
0x18000430d  jmp     loc_180004436
0x180004312  mov     rcx, [rsp+290h+TokenHandle]; TokenHandle
0x180004317  lea     rax, [rsp+290h+var_250]
0x18000431c  mov     r9d, edi; TokenInformationLength
0x18000431f  mov     [rsp+290h+ReturnLength], rax; ReturnLength
0x180004324  mov     edi, 1
0x180004329  mov     r8, rsi; TokenInformation
0x18000432c  mov     edx, edi; TokenInformationClass
0x18000432e  call    cs:__imp_GetTokenInformation
0x180004334  test    eax, eax
0x180004336  jnz     short loc_180004358
0x180004338  call    cs:__imp_GetLastError
0x18000433e  lea     r9, aGettokeninform_1; "GetTokenInformation failed [%u]"
0x180004345  mov     r8d, 669h
0x18000434b  mov     ebx, eax
0x18000434d  mov     dword ptr [rsp+290h+ReturnLength], eax
0x180004351  mov     ecx, edi
0x180004353  jmp     loc_1800042B8
0x180004358  mov     rcx, [rsi]; Sid
0x18000435b  lea     rdx, [rsp+290h+StringSid]; StringSid
0x180004360  call    cs:__imp_ConvertSidToStringSidW
0x180004366  test    eax, eax
0x180004368  jnz     short loc_18000437F
0x18000436a  call    cs:__imp_GetLastError
0x180004370  lea     r9, aFailedToGetSid_0; "Failed to get sid string [%u]"
0x180004377  mov     r8d, 66Fh
0x18000437d  jmp     short loc_18000434B
0x18000437f  mov     r9, [rsp+290h+StringSid]
0x180004384  lea     r8, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000438b  mov     edx, 104h; unsigned __int64
0x180004390  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x180004395  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000439a  test    eax, eax
0x18000439c  jns     short loc_1800043B4
0x18000439e  movzx   ebx, ax
0x1800043a1  lea     r9, aFailedToMakePa; "Failed to make path for temp directory "...
0x1800043a8  mov     dword ptr [rsp+290h+ReturnLength], ebx
0x1800043ac  mov     r8d, 67Ah
0x1800043b2  jmp     short loc_180004351
0x1800043b4  lea     rax, [rsp+290h+var_24C]
0x1800043b9  mov     r9d, 10000004h; dwFlags
0x1800043bf  mov     [rsp+290h+pcbData], rax; pcbData
0x1800043c4  lea     r8, Value; "ProfileImagePath"
0x1800043cb  mov     [rsp+290h+pvData], r14; pvData
0x1800043d0  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1800043d5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800043dc  mov     [rsp+290h+ReturnLength], 0; pdwType
0x1800043e5  call    cs:__imp_RegGetValueW
0x1800043eb  mov     ebx, eax
0x1800043ed  test    eax, eax
0x1800043ef  jz      short loc_180004403
0x1800043f1  lea     r9, aErrorQueryingV; "Error querying value [%u]"
0x1800043f8  mov     r8d, 686h
0x1800043fe  jmp     loc_18000434D
0x180004403  lea     r8, aAppdataLocalTe; "\\AppData\\Local\\Temp"
0x18000440a  mov     edx, 104h; unsigned __int64
0x18000440f  mov     rcx, r14; unsigned __int16 *
0x180004412  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004417  test    eax, eax
0x180004419  jns     short loc_180004434
0x18000441b  movzx   ebx, ax
0x18000441e  lea     r9, aFailedToCatTem; "Failed to cat temp path [%u]"
0x180004425  mov     dword ptr [rsp+290h+ReturnLength], ebx
0x180004429  mov     r8d, 691h
0x18000442f  jmp     loc_180004351
0x180004434  xor     ebx, ebx
0x180004436  mov     rcx, [rsp+290h+TokenHandle]; hObject
0x18000443b  test    rcx, rcx
0x18000443e  jz      short loc_180004446
0x180004440  call    cs:__imp_CloseHandle
0x180004446  test    rsi, rsi
0x180004449  jz      short loc_180004463
0x18000444b  mov     rcx, gs:60h
0x180004454  mov     r8, rsi; P
0x180004457  xor     edx, edx; Flags
0x180004459  mov     rcx, [rcx+30h]; HeapHandle
0x18000445d  call    cs:__imp_RtlFreeHeap
0x180004463  mov     rcx, [rsp+290h+StringSid]; hMem
0x180004468  test    rcx, rcx
0x18000446b  jz      short loc_180004473
0x18000446d  call    cs:__imp_LocalFree
0x180004473  mov     eax, ebx
0x180004475  mov     rcx, [rbp+190h+var_20]
0x18000447c  xor     rcx, rsp; StackCookie
0x18000447f  call    __security_check_cookie
0x180004484  lea     r11, [rsp+290h+var_10]
0x18000448c  mov     rbx, [r11+28h]
0x180004490  mov     rsi, [r11+38h]
0x180004494  mov     rsp, r11
0x180004497  pop     r14
0x180004499  pop     rdi
0x18000449a  pop     rbp
0x18000449b  retn
```
