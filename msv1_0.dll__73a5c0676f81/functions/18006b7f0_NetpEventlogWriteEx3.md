# NetpEventlogWriteEx3

- ea: `0x18006b7f0`
- end: `0x18006bc08`
- name: `NetpEventlogWriteEx3`
- size: `1048`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, __int64, WORD, __int64, size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18005029c`
- `0x180050364`
- `0x180050654`
- `0x180050890`
- `0x180050a24`

## callees

- `0x18002fb50`
- `0x18003082c`
- `0x18006b7f0`
- `0x18006bd68`
- `0x18006bd74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b9f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ba45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b9f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ba45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006b89a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006bb1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006b89a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006bb1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b860`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b860`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bbdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bbdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b8da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b8da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bae6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bae6`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x18006b9e3`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x18006b9e3`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18006ba3b`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18006ba3b`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18006ba50`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18006ba50`

## pseudocode

```c
__int64 __fastcall NetpEventlogWriteEx3(
        struct _RTL_CRITICAL_SECTION *a1,
        int a2,
        int a3,
        DWORD a4,
        int a5,
        int a6,
        int a7,
        LPCWSTR *lpStrings,
        unsigned int wNumStrings,
        void *lpRawData,
        size_t Size)
{
  int v12; // esi
  LPCRITICAL_SECTION v13; // rbx
  LPCRITICAL_SECTION v14; // r14
  struct _RTL_CRITICAL_SECTION_DEBUG *DebugInfo; // rdi
  __int64 OwningThread_low; // rsi
  struct _RTL_CRITICAL_SECTION_DEBUG *v17; // rbp
  struct _LIST_ENTRY *Flink; // rbx
  struct _RTL_CRITICAL_SECTION_DEBUG *v19; // rcx
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rax
  unsigned int v21; // edx
  char *v22; // rcx
  LPCWSTR v23; // r8
  bool v24; // zf
  signed __int64 v25; // r8
  int v26; // eax
  int v27; // r9d
  struct _RTL_CRITICAL_SECTION_DEBUG *v28; // rax
  struct _RTL_CRITICAL_SECTION *v29; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v30; // rax
  DWORD LastError; // ebp
  HANDLE v32; // rbx
  DWORD v33; // edi
  LPCWSTR *v34; // r13
  WORD v35; // r8
  unsigned int v36; // ecx
  signed int v37; // edx
  int v38; // r9d
  unsigned int v39; // r8d
  LPCWSTR v40; // r10
  __int64 v41; // rax
  unsigned int v42; // edx
  __int64 v43; // r13
  HLOCAL v44; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v45; // rbx
  wchar_t *v46; // rsi
  unsigned int v47; // r15d
  __int64 v48; // rdi
  struct _LIST_ENTRY *v49; // rax
  __int64 v50; // rax
  PRTL_CRITICAL_SECTION_DEBUG v51; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-68h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-60h]
  LPCRITICAL_SECTION v58; // [rsp+80h] [rbp-58h]

  v12 = a2;
  v13 = a1;
  lpCriticalSection = a1;
  EnterCriticalSection(a1);
  v14 = v13 + 1;
  DebugInfo = v13[1].DebugInfo;
  v58 = v13 + 1;
  while ( DebugInfo != (struct _RTL_CRITICAL_SECTION_DEBUG *)v14 )
  {
    OwningThread_low = LODWORD(v13[1].OwningThread);
    v17 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&DebugInfo->Type;
    SystemTimeAsFileTime = 0;
    if ( (_DWORD)OwningThread_low != -1 )
    {
      Flink = DebugInfo->ProcessLocksList.Flink;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( (__int64)(*(_QWORD *)&SystemTimeAsFileTime - (_QWORD)Flink) < 0
        || *(_QWORD *)&SystemTimeAsFileTime - (_QWORD)Flink > 10000 * OwningThread_low )
      {
        v19 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&DebugInfo->Type;
        if ( *(struct _RTL_CRITICAL_SECTION_DEBUG **)(*(_QWORD *)&DebugInfo->Type + 8LL) != DebugInfo )
          goto LABEL_68;
        CriticalSection = DebugInfo->CriticalSection;
        if ( CriticalSection->DebugInfo != DebugInfo )
          goto LABEL_68;
        CriticalSection->DebugInfo = v19;
        v19->CriticalSection = CriticalSection;
        LocalFree(DebugInfo);
LABEL_9:
        v12 = a2;
        goto LABEL_10;
      }
    }
    if ( LODWORD(DebugInfo->ProcessLocksList.Blink) != a4 )
      goto LABEL_9;
    v12 = a2;
    if ( HIDWORD(DebugInfo->ProcessLocksList.Blink) == a2
      && DebugInfo->Flags == a3
      && LODWORD(DebugInfo[1].CriticalSection) == (_DWORD)Size
      && LODWORD(DebugInfo[1].ProcessLocksList.Blink) == wNumStrings
      && (!(_DWORD)Size || !memcmp_0(*(const void **)&DebugInfo[1].Type, lpRawData, (unsigned int)Size))
      && !*(_QWORD *)&DebugInfo->EntryCount )
    {
      v21 = 0;
      if ( wNumStrings )
      {
        while ( 1 )
        {
          v22 = (char *)*((_QWORD *)&DebugInfo[1].ProcessLocksList.Flink->Flink + v21);
          v23 = lpStrings[v21];
          if ( v22 )
          {
            if ( !v23 )
              break;
            v25 = (char *)v23 - v22;
            do
            {
              v26 = *(unsigned __int16 *)&v22[v25];
              v27 = *(unsigned __int16 *)v22 - v26;
              if ( v27 )
                break;
              v22 += 2;
            }
            while ( v26 );
            v24 = v27 == 0;
          }
          else
          {
            v24 = v23 == 0;
          }
          if ( !v24 )
            break;
          if ( ++v21 >= wNumStrings )
            goto LABEL_29;
        }
      }
      else
      {
LABEL_29:
        if ( v21 == wNumStrings )
        {
          v28 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&DebugInfo->Type;
          if ( *(struct _RTL_CRITICAL_SECTION_DEBUG **)(*(_QWORD *)&DebugInfo->Type + 8LL) != DebugInfo )
            goto LABEL_68;
          v29 = DebugInfo->CriticalSection;
          if ( v29->DebugInfo != DebugInfo )
            goto LABEL_68;
          v29->DebugInfo = v28;
          v28->CriticalSection = v29;
          v30 = v14->DebugInfo;
          if ( v14->DebugInfo->CriticalSection != v14 )
            goto LABEL_68;
          *(_QWORD *)&DebugInfo->Type = v30;
          LastError = 183;
          DebugInfo->CriticalSection = v14;
          v30->CriticalSection = (struct _RTL_CRITICAL_SECTION *)DebugInfo;
          v14->DebugInfo = DebugInfo;
          ++HIDWORD(DebugInfo[1].ProcessLocksList.Blink);
          goto LABEL_70;
        }
      }
    }
LABEL_10:
    v13 = lpCriticalSection;
    DebugInfo = v17;
  }
  LastError = 0;
  v32 = RegisterEventSourceW(0, (LPCWSTR)v13[1].LockSemaphore);
  if ( v32 )
  {
    v35 = a3;
    v34 = lpStrings;
    v33 = a4;
    if ( !ReportEventW(v32, v12, v35, a4, 0, wNumStrings, Size, lpStrings, lpRawData) )
      LastError = GetLastError();
    DeregisterEventSource(v32);
  }
  else
  {
    v33 = a4;
    LastError = GetLastError();
    v34 = lpStrings;
  }
  if ( LastError )
    goto LABEL_70;
  v36 = Size + 80;
  if ( (unsigned int)Size >= 0xFFFFFFB0 )
    goto LABEL_70;
  v37 = 0;
  v38 = 0;
  if ( !wNumStrings )
    goto LABEL_55;
  while ( 2 )
  {
    if ( v37 < 0 )
      goto LABEL_70;
    v39 = v36 + 8;
    if ( v36 + 8 < v36 )
    {
      v36 = -1;
LABEL_52:
      v37 = -1073741675;
      goto LABEL_53;
    }
    v36 += 8;
    v37 = 0;
    v40 = v34[v38];
    if ( !v40 )
      goto LABEL_53;
    v41 = -1;
    do
      ++v41;
    while ( v40[v41] );
    v42 = v39 + 2 * v41;
    v36 = -1;
    if ( v42 < v39 )
      goto LABEL_52;
    if ( v42 + 2 >= v42 )
      v36 = v42 + 2;
    v37 = v42 + 2 < v42 ? 0xC0000095 : 0;
LABEL_53:
    if ( ++v38 < wNumStrings )
      continue;
    break;
  }
  if ( v37 >= 0 )
  {
LABEL_55:
    v43 = v36;
    v44 = LocalAlloc(0, v36);
    v45 = (struct _RTL_CRITICAL_SECTION_DEBUG *)v44;
    if ( v44 )
    {
      *((_DWORD *)v44 + 6) = v33;
      *((_DWORD *)v44 + 7) = v12;
      *((_QWORD *)v44 + 4) = 0;
      *((_DWORD *)v44 + 10) = a3;
      *((_DWORD *)v44 + 14) = Size;
      *((_DWORD *)v44 + 18) = wNumStrings;
      *((_DWORD *)v44 + 19) = 1;
      GetSystemTimeAsFileTime((LPFILETIME)v44 + 2);
      v45[1].ProcessLocksList.Flink = (struct _LIST_ENTRY *)&v45[1].EntryCount;
      v46 = (wchar_t *)(&v45[1].EntryCount + 2 * wNumStrings);
      v47 = 0;
      if ( wNumStrings )
      {
        v48 = 0;
        do
        {
          v49 = v45[1].ProcessLocksList.Flink;
          if ( lpStrings[v48] )
          {
            *((_QWORD *)&v49->Flink + v48) = v46;
            wcscpy_s(v46, ((unsigned __int64)v45 + v43 - (_QWORD)v46) >> 1, lpStrings[v48]);
            v50 = -1;
            do
              ++v50;
            while ( lpStrings[v48][v50] );
            v46 += v50 + 1;
          }
          else
          {
            *((_QWORD *)&v49->Flink + v48) = 0;
          }
          ++v47;
          ++v48;
        }
        while ( v47 < wNumStrings );
        v14 = v58;
      }
      if ( (_DWORD)Size )
      {
        *(_QWORD *)&v45[1].Type = v46;
        memcpy_0(v46, lpRawData, (unsigned int)Size);
      }
      v51 = v14->DebugInfo;
      if ( v14->DebugInfo->CriticalSection != v14 )
LABEL_68:
        __fastfail(3u);
      *(_QWORD *)&v45->Type = v51;
      v45->CriticalSection = v14;
      v51->CriticalSection = (struct _RTL_CRITICAL_SECTION *)v45;
      v14->DebugInfo = v45;
    }
  }
LABEL_70:
  LeaveCriticalSection(lpCriticalSection);
  return LastError;
}

```

## disassembly

```asm
0x18006b7f0  push    rbx
0x18006b7f2  push    rbp
0x18006b7f3  push    rsi
0x18006b7f4  push    rdi
0x18006b7f5  push    r12
0x18006b7f7  push    r13
0x18006b7f9  push    r14
0x18006b7fb  push    r15
0x18006b7fd  sub     rsp, 98h
0x18006b804  mov     rax, cs:__security_cookie
0x18006b80b  xor     rax, rsp
0x18006b80e  mov     [rsp+0D8h+var_50], rax
0x18006b816  mov     rbp, [rsp+0D8h+arg_38]
0x18006b81e  mov     r13d, r8d
0x18006b821  mov     r15d, dword ptr [rsp+0D8h+Size]
0x18006b829  mov     esi, edx
0x18006b82b  mov     r12d, dword ptr [rsp+0D8h+arg_40]
0x18006b833  mov     rbx, rcx
0x18006b836  mov     [rsp+0D8h+var_80], rbp
0x18006b83b  mov     rbp, [rsp+0D8h+arg_48]
0x18006b843  mov     [rsp+0D8h+var_74+4], rbp
0x18006b848  mov     [rsp+0D8h+dwEventID], r9d
0x18006b84d  mov     [rsp+0D8h+var_78], r8d
0x18006b852  mov     [rsp+0D8h+var_88], edx
0x18006b856  mov     [rsp+0D8h+lpCriticalSection], rcx
0x18006b85b  mov     dword ptr [rsp+0D8h+var_74], r15d
0x18006b860  call    cs:__imp_EnterCriticalSection
0x18006b866  lea     r14, [rbx+28h]
0x18006b86a  mov     rdi, [r14]
0x18006b86d  mov     [rsp+0D8h+var_58], r14
0x18006b875  xor     r11d, r11d
0x18006b878  cmp     rdi, r14
0x18006b87b  jz      loc_18006B9DD
0x18006b881  mov     esi, [rbx+38h]
0x18006b884  mov     rbp, [rdi]
0x18006b887  mov     qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime], r11
0x18006b88c  cmp     esi, 0FFFFFFFFh
0x18006b88f  jz      short loc_18006B8F1
0x18006b891  mov     rbx, [rdi+10h]
0x18006b895  lea     rcx, [rsp+0D8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006b89a  call    cs:__imp_GetSystemTimeAsFileTime
0x18006b8a0  mov     rdx, qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime]
0x18006b8a5  sub     rdx, rbx
0x18006b8a8  js      short loc_18006B8B6
0x18006b8aa  imul    rcx, rsi, 2710h
0x18006b8b1  cmp     rdx, rcx
0x18006b8b4  jle     short loc_18006B8EE
0x18006b8b6  mov     rcx, [rdi]
0x18006b8b9  cmp     [rcx+8], rdi
0x18006b8bd  jnz     loc_18006BBC2
0x18006b8c3  mov     rax, [rdi+8]
0x18006b8c7  cmp     [rax], rdi
0x18006b8ca  jnz     loc_18006BBC2
0x18006b8d0  mov     [rax], rcx
0x18006b8d3  mov     [rcx+8], rax
0x18006b8d7  mov     rcx, rdi; hMem
0x18006b8da  call    cs:__imp_LocalFree
0x18006b8e0  mov     esi, [rsp+0D8h+var_88]
0x18006b8e4  mov     rbx, [rsp+0D8h+lpCriticalSection]
0x18006b8e9  mov     rdi, rbp
0x18006b8ec  jmp     short loc_18006B875
0x18006b8ee  xor     r11d, r11d
0x18006b8f1  mov     eax, [rsp+0D8h+dwEventID]
0x18006b8f5  cmp     [rdi+18h], eax
0x18006b8f8  jnz     short loc_18006B8E0
0x18006b8fa  mov     esi, [rsp+0D8h+var_88]
0x18006b8fe  cmp     [rdi+1Ch], esi
0x18006b901  jnz     short loc_18006B8E4
0x18006b903  cmp     [rdi+28h], r13d
0x18006b907  jnz     short loc_18006B8E4
0x18006b909  cmp     [rdi+38h], r15d
0x18006b90d  jnz     short loc_18006B8E4
0x18006b90f  cmp     [rdi+48h], r12d
0x18006b913  jnz     short loc_18006B8E4
0x18006b915  test    r15d, r15d
0x18006b918  jz      short loc_18006B932
0x18006b91a  mov     rdx, [rsp+0D8h+var_74+4]; Buf2
0x18006b91f  mov     r8, r15; Size
0x18006b922  mov     rcx, [rdi+30h]; Buf1
0x18006b926  call    memcmp_0
0x18006b92b  xor     r11d, r11d
0x18006b92e  test    eax, eax
0x18006b930  jnz     short loc_18006B8E4
0x18006b932  cmp     [rdi+20h], r11
0x18006b936  jnz     short loc_18006B8E4
0x18006b938  mov     edx, r11d
0x18006b93b  test    r12d, r12d
0x18006b93e  jz      short loc_18006B98B
0x18006b940  mov     r10, [rdi+40h]
0x18006b944  mov     r8, [rsp+0D8h+var_80]
0x18006b949  mov     eax, edx
0x18006b94b  mov     rcx, [r10+rax*8]
0x18006b94f  mov     r8, [r8+rax*8]
0x18006b953  test    rcx, rcx
0x18006b956  jnz     short loc_18006B95D
0x18006b958  test    r8, r8
0x18006b95b  jmp     short loc_18006B97E
0x18006b95d  test    r8, r8
0x18006b960  jz      short loc_18006B8E4
0x18006b962  sub     r8, rcx
0x18006b965  movzx   r9d, word ptr [rcx]
0x18006b969  movzx   eax, word ptr [rcx+r8]
0x18006b96e  sub     r9d, eax
0x18006b971  jnz     short loc_18006B97B
0x18006b973  add     rcx, 2
0x18006b977  test    eax, eax
0x18006b979  jnz     short loc_18006B965
0x18006b97b  test    r9d, r9d
0x18006b97e  jnz     loc_18006B8E4
0x18006b984  inc     edx
0x18006b986  cmp     edx, r12d
0x18006b989  jb      short loc_18006B944
0x18006b98b  cmp     edx, r12d
0x18006b98e  jnz     loc_18006B8E4
0x18006b994  mov     rax, [rdi]
0x18006b997  cmp     [rax+8], rdi
0x18006b99b  jnz     loc_18006BBC2
0x18006b9a1  mov     rcx, [rdi+8]
0x18006b9a5  cmp     [rcx], rdi
0x18006b9a8  jnz     loc_18006BBC2
0x18006b9ae  mov     [rcx], rax
0x18006b9b1  mov     [rax+8], rcx
0x18006b9b5  mov     rax, [r14]
0x18006b9b8  cmp     [rax+8], r14
0x18006b9bc  jnz     loc_18006BBC2
0x18006b9c2  mov     [rdi], rax
0x18006b9c5  mov     ebp, 0B7h
0x18006b9ca  mov     [rdi+8], r14
0x18006b9ce  mov     [rax+8], rdi
0x18006b9d2  mov     [r14], rdi
0x18006b9d5  inc     dword ptr [rdi+4Ch]
0x18006b9d8  jmp     loc_18006BBD7
0x18006b9dd  mov     rdx, [rbx+40h]; lpSourceName
0x18006b9e1  xor     ecx, ecx; lpUNCServerName
0x18006b9e3  call    cs:__imp_RegisterEventSourceW
0x18006b9e9  xor     ebp, ebp
0x18006b9eb  mov     rbx, rax
0x18006b9ee  test    rax, rax
0x18006b9f1  jnz     short loc_18006BA06
0x18006b9f3  call    cs:__imp_GetLastError
0x18006b9f9  mov     edi, [rsp+0D8h+dwEventID]
0x18006b9fd  mov     ebp, eax
0x18006b9ff  mov     r13, [rsp+0D8h+var_80]
0x18006ba04  jmp     short loc_18006BA56
0x18006ba06  mov     rax, [rsp+0D8h+var_74+4]
0x18006ba0b  movzx   r8d, r13w; wCategory
0x18006ba0f  mov     r13, [rsp+0D8h+var_80]
0x18006ba14  movzx   edx, si; wType
0x18006ba17  mov     edi, [rsp+0D8h+dwEventID]
0x18006ba1b  mov     rcx, rbx; hEventLog
0x18006ba1e  mov     [rsp+0D8h+lpRawData], rax; lpRawData
0x18006ba23  mov     r9d, edi; dwEventID
0x18006ba26  mov     [rsp+0D8h+lpStrings], r13; lpStrings
0x18006ba2b  mov     [rsp+0D8h+dwDataSize], r15d; dwDataSize
0x18006ba30  mov     [rsp+0D8h+wNumStrings], r12w; wNumStrings
0x18006ba36  mov     [rsp+0D8h+lpUserSid], rbp; lpUserSid
0x18006ba3b  call    cs:__imp_ReportEventW
0x18006ba41  test    eax, eax
0x18006ba43  jnz     short loc_18006BA4D
0x18006ba45  call    cs:__imp_GetLastError
0x18006ba4b  mov     ebp, eax
0x18006ba4d  mov     rcx, rbx; hEventLog
0x18006ba50  call    cs:__imp_DeregisterEventSource
0x18006ba56  xor     r11d, r11d
0x18006ba59  test    ebp, ebp
0x18006ba5b  jnz     loc_18006BBD7
0x18006ba61  lea     ecx, [r15+50h]
0x18006ba65  cmp     ecx, 50h ; 'P'
0x18006ba68  jb      loc_18006BBD7
0x18006ba6e  mov     edx, r11d
0x18006ba71  mov     r9d, r11d
0x18006ba74  test    r12d, r12d
0x18006ba77  jz      short loc_18006BADF
0x18006ba79  mov     ebx, 0C0000095h
0x18006ba7e  test    edx, edx
0x18006ba80  js      loc_18006BBD7
0x18006ba86  lea     r8d, [rcx+8]
0x18006ba8a  cmp     r8d, ecx
0x18006ba8d  jb      short loc_18006BACA
0x18006ba8f  mov     eax, r9d
0x18006ba92  mov     ecx, r8d
0x18006ba95  mov     edx, r11d
0x18006ba98  mov     r10, [r13+rax*8+0]
0x18006ba9d  test    r10, r10
0x18006baa0  jz      short loc_18006BACF
0x18006baa2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006baa6  inc     rax
0x18006baa9  cmp     [r10+rax*2], r11w
0x18006baae  jnz     short loc_18006BAA6
0x18006bab0  lea     edx, [r8+rax*2]
0x18006bab4  or      ecx, 0FFFFFFFFh
0x18006bab7  cmp     edx, r8d
0x18006baba  jb      short loc_18006BACD
0x18006babc  lea     eax, [rdx+2]
0x18006babf  cmp     eax, edx
0x18006bac1  cmovnb  ecx, eax
0x18006bac4  sbb     edx, edx
0x18006bac6  and     edx, ebx
0x18006bac8  jmp     short loc_18006BACF
0x18006baca  or      ecx, 0FFFFFFFFh
0x18006bacd  mov     edx, ebx
0x18006bacf  inc     r9d
0x18006bad2  cmp     r9d, r12d
0x18006bad5  jb      short loc_18006BA7E
0x18006bad7  test    edx, edx
0x18006bad9  js      loc_18006BBD7
0x18006badf  mov     r13d, ecx
0x18006bae2  mov     edx, ecx; uBytes
0x18006bae4  xor     ecx, ecx; uFlags
0x18006bae6  call    cs:__imp_LocalAlloc
0x18006baec  xor     edx, edx
0x18006baee  mov     rbx, rax
0x18006baf1  test    rax, rax
0x18006baf4  jz      loc_18006BBD7
0x18006bafa  mov     [rax+18h], edi
0x18006bafd  lea     rcx, [rbx+10h]; lpSystemTimeAsFileTime
0x18006bb01  mov     [rax+1Ch], esi
0x18006bb04  mov     [rax+20h], rdx
0x18006bb08  mov     eax, [rsp+0D8h+var_78]
0x18006bb0c  mov     [rbx+28h], eax
0x18006bb0f  mov     [rbx+38h], r15d
0x18006bb13  mov     [rbx+48h], r12d
0x18006bb17  mov     dword ptr [rbx+4Ch], 1
0x18006bb1e  call    cs:__imp_GetSystemTimeAsFileTime
0x18006bb24  lea     rcx, [rbx+50h]
0x18006bb28  mov     [rbx+40h], rcx
0x18006bb2c  lea     rsi, [rcx+r12*8]
0x18006bb30  xor     ecx, ecx
0x18006bb32  mov     r15d, ecx
0x18006bb35  test    r12d, r12d
0x18006bb38  jz      short loc_18006BB9D
0x18006bb3a  mov     r14, [rsp+0D8h+var_80]
0x18006bb3f  mov     edi, ecx
0x18006bb41  mov     rax, [rbx+40h]
0x18006bb45  cmp     [r14+rdi*8], rcx
0x18006bb49  jnz     short loc_18006BB51
0x18006bb4b  mov     [rax+rdi*8], rcx
0x18006bb4f  jmp     short loc_18006BB8A
0x18006bb51  mov     [rax+rdi*8], rsi
0x18006bb55  mov     rdx, r13
0x18006bb58  mov     r8, [r14+rdi*8]; Source
0x18006bb5c  sub     rdx, rsi
0x18006bb5f  add     rdx, rbx
0x18006bb62  mov     rcx, rsi; Destination
0x18006bb65  shr     rdx, 1; SizeInWords
0x18006bb68  call    wcscpy_s
0x18006bb6d  mov     rcx, [r14+rdi*8]
0x18006bb71  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006bb75  xor     edx, edx
0x18006bb77  inc     rax
0x18006bb7a  cmp     [rcx+rax*2], dx
0x18006bb7e  jnz     short loc_18006BB77
0x18006bb80  lea     rsi, [rsi+rax*2]
0x18006bb84  add     rsi, 2
0x18006bb88  xor     ecx, ecx
0x18006bb8a  inc     r15d
0x18006bb8d  inc     rdi
0x18006bb90  cmp     r15d, r12d
0x18006bb93  jb      short loc_18006BB41
0x18006bb95  mov     r14, [rsp+0D8h+var_58]
0x18006bb9d  mov     eax, dword ptr [rsp+0D8h+var_74]
0x18006bba1  test    eax, eax
0x18006bba3  jz      short loc_18006BBB9
0x18006bba5  mov     rdx, [rsp+0D8h+var_74+4]; Src
0x18006bbaa  mov     r8d, eax; Size
0x18006bbad  mov     rcx, rsi; void *
0x18006bbb0  mov     [rbx+30h], rsi
0x18006bbb4  call    memcpy_0
0x18006bbb9  mov     rax, [r14]
0x18006bbbc  cmp     [rax+8], r14
0x18006bbc0  jz      short loc_18006BBC9
0x18006bbc2  mov     ecx, 3
0x18006bbc7  int     29h; Win8: RtlFailFast(ecx)
0x18006bbc9  mov     [rbx], rax
0x18006bbcc  mov     [rbx+8], r14
0x18006bbd0  mov     [rax+8], rbx
0x18006bbd4  mov     [r14], rbx
0x18006bbd7  mov     rcx, [rsp+0D8h+lpCriticalSection]; lpCriticalSection
0x18006bbdc  call    cs:__imp_LeaveCriticalSection
0x18006bbe2  mov     eax, ebp
0x18006bbe4  mov     rcx, [rsp+0D8h+var_50]
0x18006bbec  xor     rcx, rsp; StackCookie
0x18006bbef  call    __security_check_cookie
0x18006bbf4  add     rsp, 98h
0x18006bbfb  pop     r15
0x18006bbfd  pop     r14
0x18006bbff  pop     r13
0x18006bc01  pop     r12
0x18006bc03  pop     rdi
0x18006bc04  pop     rsi
0x18006bc05  pop     rbp
0x18006bc06  pop     rbx
0x18006bc07  retn
```
