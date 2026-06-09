# ReadLoggingStatusInternal(ushort const *,ushort const *,_RSOPEXTSTATUS *,ulong *)

- ea: `0x1800490b0`
- end: `0x1800496f7`
- name: `?ReadLoggingStatusInternal@@YAKPEBG0PEAU_RSOPEXTSTATUS@@PEAK@Z`
- size: `1607`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, struct _RSOPEXTSTATUS *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004906c`
- `0x1800ad5ec`

## callees

- `0x180003770`
- `0x1800490b0`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004929e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049350`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049395`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004929e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049350`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049100`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049388`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049388`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800492ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800492ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004932b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049453`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800494e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049555`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800495ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004967f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004932b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049453`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800494e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049555`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800495ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004967f`

## string_xrefs

- `0x1800491a3`: `Extension-List`
- `0x180049375`: `ReadLoggingStatus: Failed to create state key with %d`
- `0x1800493b6`: `ReadLoggingStatus: Failed to create state key with %d`
- `0x1800493d1`: `ReadLoggingStatus: Failed to set STATUS with %d`
- `0x180049403`: `ReadLoggingStatus: Failed to set STATUS with %d`
- `0x18004947b`: `ReadLoggingStatus: Failed to set STARTTIME1 with %d`
- `0x1800494ad`: `ReadLoggingStatus: Failed to set STARTTIME1 with %d`
- `0x180049510`: `ReadLoggingStatus: Failed to set STARTTIME1 with %d`
- `0x18004957d`: `ReadLoggingStatus: Failed to set ENDTIME1 with %d`
- `0x1800495af`: `ReadLoggingStatus: Failed to set ENDTIME1 with %d`
- `0x180049612`: `ReadLoggingStatus: Failed to set ENDTIME2 with %d`
- `0x180049644`: `ReadLoggingStatus: Failed to set ENDTIME2 with %d`
- `0x1800496ab`: `ReadLoggingStatus: Failed to set LOGSTATUS with %d`
- `0x1800496dd`: `ReadLoggingStatus: Failed to set LOGSTATUS with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadLoggingStatusInternal(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _RSOPEXTSTATUS *a3,
        unsigned int *a4)
{
  DWORD LastError; // ebx
  const wchar_t *v8; // r9
  __int64 v9; // rdi
  int v10; // eax
  __int64 v11; // r11
  __int64 v12; // rax
  WCHAR *v13; // rcx
  __int64 v14; // rcx
  WCHAR *v15; // rax
  int v16; // esi
  __int64 v17; // r8
  __int64 v18; // rdx
  const WCHAR *v19; // r9
  WCHAR *v20; // r10
  WCHAR v21; // ax
  WCHAR *v22; // rax
  const WCHAR *v23; // rcx
  WCHAR *v24; // rdx
  WCHAR v25; // ax
  unsigned int v27; // edi
  unsigned int v28; // ebx
  int v29; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v34; // [rsp+44h] [rbp-BCh]
  WCHAR SubKey[261]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v37[6]; // [rsp+25Ah] [rbp+15Ah] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  LastError = GetLastError();
  v34 = LastError;
  v8 = L"Machine";
  if ( a1 )
    v8 = a1;
  v9 = 261;
  v10 = StringCchPrintfW(SubKey, 0x105u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\State\\%ws", v8);
  if ( v10 < 0 )
  {
    v28 = (unsigned __int16)v10;
    SetLastError((unsigned __int16)v10);
    return v28;
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( SubKey[v12] );
  v13 = &SubKey[v12];
  if ( *(v13 - 1) != 92 )
    *(_DWORD *)v13 = 92;
  v14 = 261;
  v15 = SubKey;
  while ( *v15 )
  {
    ++v15;
    if ( !--v14 )
    {
      LOWORD(v16) = 87;
LABEL_31:
      SetLastError((unsigned __int16)v16);
      return (unsigned __int16)v16;
    }
  }
  v17 = 2147483646;
  v18 = 2147483646;
  v19 = L"Extension-List";
  v20 = (WCHAR *)&v37[-2 * v14];
  v16 = 0;
  while ( v18 )
  {
    v21 = *v19;
    if ( !*v19 )
      break;
    ++v19;
    *v20++ = v21;
    --v18;
    if ( !--v14 )
    {
      --v20;
      v16 = -2147024774;
      break;
    }
  }
  *v20 = 0;
  if ( v16 < 0 )
    goto LABEL_31;
  do
    ++v11;
  while ( SubKey[v11] );
  if ( SubKey[v11 - 1] != 92 )
    *(_DWORD *)&SubKey[v11] = 92;
  v22 = SubKey;
  while ( *v22 )
  {
    ++v22;
    if ( !--v9 )
    {
      LOWORD(v16) = 87;
      goto LABEL_31;
    }
  }
  v23 = L"{00000000-0000-0000-0000-000000000000}";
  v24 = (WCHAR *)&v37[-2 * v9];
  v16 = 0;
  while ( v17 )
  {
    v25 = *v23;
    if ( !*v23 )
      break;
    ++v23;
    *v24++ = v25;
    --v17;
    if ( !--v9 )
    {
      --v24;
      v16 = -2147024774;
      break;
    }
  }
  *v24 = 0;
  if ( v16 < 0 )
    goto LABEL_31;
  v27 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  if ( v27 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ReadLoggingStatus: Failed to create state key with %d", v27);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ReadLoggingStatus: Failed to create state key with %d", v27);
      }
    }
    goto LABEL_35;
  }
  cbData = 4;
  v27 = RegQueryValueExW(hKey, L"Status", 0, &Type, Data, &cbData);
  if ( v27 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ReadLoggingStatus: Failed to set STATUS with %d", v27);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ReadLoggingStatus: Failed to set STATUS with %d", v27);
      }
    }
    goto LABEL_35;
  }
  v29 = *(_DWORD *)Data;
  if ( a4 )
    *a4 = *(_DWORD *)Data;
  if ( !a3 )
    goto LABEL_35;
  *((_DWORD *)a3 + 4) = v29;
  cbData = 4;
  v27 = RegQueryValueExW(hKey, L"StartTimeLo", 0, &Type, (LPBYTE)a3, &cbData);
  if ( v27 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
LABEL_56:
        g_lpDebugMsg(2u, L"ReadLoggingStatus: Failed to set STARTTIME1 with %d", v27);
        goto LABEL_35;
      }
LABEL_57:
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"ReadLoggingStatus: Failed to set STARTTIME1 with %d", v27);
    }
  }
  else
  {
    cbData = 4;
    v27 = RegQueryValueExW(hKey, L"StartTimeHi", 0, &Type, (LPBYTE)a3 + 4, &cbData);
    if ( !v27 )
    {
      cbData = 4;
      v27 = RegQueryValueExW(hKey, L"EndTimeLo", 0, &Type, (LPBYTE)a3 + 8, &cbData);
      if ( v27 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"ReadLoggingStatus: Failed to set ENDTIME1 with %d", v27);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"ReadLoggingStatus: Failed to set ENDTIME1 with %d", v27);
          }
        }
      }
      else
      {
        cbData = 4;
        v27 = RegQueryValueExW(hKey, L"EndTimeHi", 0, &Type, (LPBYTE)a3 + 12, &cbData);
        if ( v27 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"ReadLoggingStatus: Failed to set ENDTIME2 with %d", v27);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"ReadLoggingStatus: Failed to set ENDTIME2 with %d", v27);
            }
          }
        }
        else
        {
          cbData = 4;
          v27 = RegQueryValueExW(hKey, L"LoggingStatus", 0, &Type, (LPBYTE)a3 + 20, &cbData);
          if ( v27 && *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"ReadLoggingStatus: Failed to set LOGSTATUS with %d", v27);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"ReadLoggingStatus: Failed to set LOGSTATUS with %d", v27);
            }
          }
        }
      }
      goto LABEL_35;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
        goto LABEL_56;
      goto LABEL_57;
    }
  }
LABEL_35:
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(LastError);
  return v27;
}

```

## disassembly

```asm
0x1800490b0  mov     [rsp-8+arg_8], rbx
0x1800490b5  push    rbp
0x1800490b6  push    rsi
0x1800490b7  push    rdi
0x1800490b8  push    r12
0x1800490ba  push    r13
0x1800490bc  push    r14
0x1800490be  push    r15
0x1800490c0  lea     rbp, [rsp-170h]
0x1800490c8  sub     rsp, 270h
0x1800490cf  mov     rax, cs:__security_cookie
0x1800490d6  xor     rax, rsp
0x1800490d9  mov     [rbp+1A0h+var_40], rax
0x1800490e0  mov     r15, r9
0x1800490e3  mov     r14, r8
0x1800490e6  mov     rdi, rcx
0x1800490e9  xor     r13d, r13d
0x1800490ec  mov     [rsp+2A0h+hKey], r13
0x1800490f1  mov     [rsp+2A0h+Type], r13d
0x1800490f6  mov     [rsp+2A0h+cbData], r13d
0x1800490fb  mov     dword ptr [rsp+2A0h+Data], r13d
0x180049100  call    cs:__imp_GetLastError
0x180049106  mov     ebx, eax
0x180049108  mov     [rsp+2A0h+var_25C], eax
0x18004910c  lea     r9, aMachine; "Machine"
0x180049113  test    rdi, rdi
0x180049116  cmovnz  r9, rdi
0x18004911a  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180049121  mov     edi, 105h
0x180049126  mov     edx, edi; unsigned __int64
0x180049128  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x18004912d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180049132  test    eax, eax
0x180049134  js      loc_180049390
0x18004913a  lea     rcx, [rsp+2A0h+SubKey]
0x18004913f  mov     r11, 0FFFFFFFFFFFFFFFFh
0x180049146  mov     rax, r11
0x180049149  nop     dword ptr [rax+00000000h]
0x180049150  lea     rax, [rax+1]
0x180049154  cmp     word ptr [rcx+rax*2], 0
0x180049159  jnz     short loc_180049150
0x18004915b  lea     rcx, [rsp+2A0h+SubKey]
0x180049160  lea     rcx, [rcx+rax*2]
0x180049164  cmp     word ptr [rcx-2], 5Ch ; '\'
0x180049169  jz      short loc_180049171
0x18004916b  mov     dword ptr [rcx], 5Ch ; '\'
0x180049171  mov     rcx, rdi
0x180049174  lea     rax, [rsp+2A0h+SubKey]
0x180049179  nop     dword ptr [rax+00000000h]
0x180049180  cmp     word ptr [rax], 0
0x180049184  jz      short loc_18004919A
0x180049186  add     rax, 2
0x18004918a  sub     rcx, 1
0x18004918e  jnz     short loc_180049180
0x180049190  mov     esi, 80070057h
0x180049195  jmp     loc_180049299
0x18004919a  mov     r8d, 7FFFFFFEh
0x1800491a0  mov     edx, r8d
0x1800491a3  lea     r9, aExtensionList; "Extension-List"
0x1800491aa  lea     rax, [rcx+rcx]
0x1800491ae  lea     r10, [rbp+1A0h+var_46]
0x1800491b5  sub     r10, rax
0x1800491b8  mov     esi, r13d
0x1800491bb  test    rcx, rcx
0x1800491be  jz      short loc_1800491E3
0x1800491c0  test    rdx, rdx
0x1800491c3  jz      short loc_1800491F3
0x1800491c5  movzx   eax, word ptr [r9]
0x1800491c9  test    ax, ax
0x1800491cc  jz      short loc_1800491EE
0x1800491ce  add     r9, 2
0x1800491d2  mov     [r10], ax
0x1800491d6  add     r10, 2
0x1800491da  dec     rdx
0x1800491dd  sub     rcx, 1
0x1800491e1  jnz     short loc_1800491C0
0x1800491e3  sub     r10, 2
0x1800491e7  mov     esi, 8007007Ah
0x1800491ec  jmp     short loc_1800491F3
0x1800491ee  test    rcx, rcx
0x1800491f1  jz      short loc_1800491E3
0x1800491f3  mov     [r10], r13w
0x1800491f7  test    esi, esi
0x1800491f9  js      loc_180049299
0x1800491ff  lea     rax, [rsp+2A0h+SubKey]
0x180049204  lea     r11, [r11+1]
0x180049208  cmp     word ptr [rax+r11*2], 0
0x18004920e  jnz     short loc_180049204
0x180049210  cmp     [rsp+r11*2+2A0h+var_252], 5Ch ; '\'
0x180049217  jz      short loc_180049222
0x180049219  mov     dword ptr [rsp+r11*2+2A0h+SubKey], 5Ch ; '\'
0x180049222  lea     rax, [rsp+2A0h+SubKey]
0x180049227  cmp     word ptr [rax], 0
0x18004922b  jz      short loc_18004923E
0x18004922d  add     rax, 2
0x180049231  sub     rdi, 1
0x180049235  jnz     short loc_180049227
0x180049237  mov     esi, 80070057h
0x18004923c  jmp     short loc_180049299
0x18004923e  lea     rcx, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180049245  lea     rax, [rdi+rdi]
0x180049249  lea     rdx, [rbp+1A0h+var_46]
0x180049250  sub     rdx, rax
0x180049253  mov     esi, r13d
0x180049256  test    rdi, rdi
0x180049259  jz      short loc_180049281
0x18004925b  nop     dword ptr [rax+rax+00h]
0x180049260  test    r8, r8
0x180049263  jz      short loc_180049291
0x180049265  movzx   eax, word ptr [rcx]
0x180049268  test    ax, ax
0x18004926b  jz      short loc_18004928C
0x18004926d  add     rcx, 2
0x180049271  mov     [rdx], ax
0x180049274  add     rdx, 2
0x180049278  dec     r8
0x18004927b  sub     rdi, 1
0x18004927f  jnz     short loc_180049260
0x180049281  sub     rdx, 2
0x180049285  mov     esi, 8007007Ah
0x18004928a  jmp     short loc_180049291
0x18004928c  test    rdi, rdi
0x18004928f  jz      short loc_180049281
0x180049291  mov     [rdx], r13w
0x180049295  test    esi, esi
0x180049297  jns     short loc_1800492D0
0x180049299  movzx   ebx, si
0x18004929c  mov     ecx, ebx; dwErrCode
0x18004929e  call    cs:__imp_SetLastError
0x1800492a4  mov     eax, ebx
0x1800492a6  mov     rcx, [rbp+1A0h+var_40]
0x1800492ad  xor     rcx, rsp; StackCookie
0x1800492b0  call    __security_check_cookie
0x1800492b5  mov     rbx, [rsp+2A0h+arg_8]
0x1800492bd  add     rsp, 270h
0x1800492c4  pop     r15
0x1800492c6  pop     r14
0x1800492c8  pop     r13
0x1800492ca  pop     r12
0x1800492cc  pop     rdi
0x1800492cd  pop     rsi
0x1800492ce  pop     rbp
0x1800492cf  retn
0x1800492d0  lea     rax, [rsp+2A0h+hKey]
0x1800492d5  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800492da  mov     r9d, 20019h; samDesired
0x1800492e0  xor     r8d, r8d; ulOptions
0x1800492e3  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800492e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800492ef  call    cs:__imp_RegOpenKeyExW
0x1800492f5  mov     edi, eax
0x1800492f7  test    eax, eax
0x1800492f9  jnz     short loc_18004935D
0x1800492fb  mov     [rsp+2A0h+cbData], 4
0x180049303  lea     rax, [rsp+2A0h+cbData]
0x180049308  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x18004930d  lea     rax, [rsp+2A0h+Data]
0x180049312  mov     [rsp+2A0h+phkResult], rax; lpData
0x180049317  lea     r9, [rsp+2A0h+Type]; lpType
0x18004931c  xor     r8d, r8d; lpReserved
0x18004931f  lea     rdx, aStatus_0; "Status"
0x180049326  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18004932b  call    cs:__imp_RegQueryValueExW
0x180049331  mov     edi, eax
0x180049333  test    eax, eax
0x180049335  jz      loc_18004940F
0x18004933b  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180049342  jnz     short loc_1800493C2
0x180049344  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180049349  test    rcx, rcx
0x18004934c  jnz     short loc_180049388
0x18004934e  mov     ecx, ebx; dwErrCode
0x180049350  call    cs:__imp_SetLastError
0x180049356  mov     eax, edi
0x180049358  jmp     loc_1800492A6
0x18004935d  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180049364  jz      short loc_180049344
0x180049366  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004936d  test    rax, rax
0x180049370  jz      short loc_1800493A2
0x180049372  mov     r8d, edi
0x180049375  lea     rdx, aReadloggingsta_2; "ReadLoggingStatus: Failed to create sta"...
0x18004937c  mov     ecx, 2
0x180049381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049386  jmp     short loc_180049344
0x180049388  call    cs:__imp_RegCloseKey
0x18004938e  jmp     short loc_18004934E
0x180049390  movzx   ebx, ax
0x180049393  mov     ecx, ebx; dwErrCode
0x180049395  call    cs:__imp_SetLastError
0x18004939b  mov     eax, ebx
0x18004939d  jmp     loc_1800492A6
0x1800493a2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800493aa  jz      short loc_180049344
0x1800493ac  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800493b4  jz      short loc_180049344
0x1800493b6  lea     rdx, aReadloggingsta_2; "ReadLoggingStatus: Failed to create sta"...
0x1800493bd  jmp     loc_1800496E4
0x1800493c2  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800493c9  test    rax, rax
0x1800493cc  jz      short loc_1800493E7
0x1800493ce  mov     r8d, edi
0x1800493d1  lea     rdx, aReadloggingsta_0; "ReadLoggingStatus: Failed to set STATUS"...
0x1800493d8  mov     ecx, 2
0x1800493dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800493e2  jmp     loc_180049344
0x1800493e7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800493ef  jz      loc_180049344
0x1800493f5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800493fd  jz      loc_180049344
0x180049403  lea     rdx, aReadloggingsta_0; "ReadLoggingStatus: Failed to set STATUS"...
0x18004940a  jmp     loc_1800496E4
0x18004940f  mov     eax, dword ptr [rsp+2A0h+Data]
0x180049413  test    r15, r15
0x180049416  jz      short loc_18004941B
0x180049418  mov     [r15], eax
0x18004941b  test    r14, r14
0x18004941e  jz      loc_180049344
0x180049424  mov     [r14+10h], eax
0x180049428  mov     [rsp+2A0h+cbData], 4
0x180049430  lea     rax, [rsp+2A0h+cbData]
0x180049435  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x18004943a  mov     [rsp+2A0h+phkResult], r14; lpData
0x18004943f  lea     r9, [rsp+2A0h+Type]; lpType
0x180049444  xor     r8d, r8d; lpReserved
0x180049447  lea     rdx, aStarttimelo; "StartTimeLo"
0x18004944e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180049453  call    cs:__imp_RegQueryValueExW
0x180049459  mov     edi, eax
0x18004945b  test    eax, eax
0x18004945d  jz      short loc_1800494B9
0x18004945f  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180049466  jz      loc_180049344
0x18004946c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180049473  test    rax, rax
0x180049476  jz      short loc_180049491
0x180049478  mov     r8d, edi
0x18004947b  lea     rdx, aReadloggingsta_4; "ReadLoggingStatus: Failed to set STARTT"...
0x180049482  mov     ecx, 2
0x180049487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004948c  jmp     loc_180049344
0x180049491  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180049499  jz      loc_180049344
0x18004949f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800494a7  jz      loc_180049344
0x1800494ad  lea     rdx, aReadloggingsta_4; "ReadLoggingStatus: Failed to set STARTT"...
0x1800494b4  jmp     loc_1800496E4
0x1800494b9  mov     [rsp+2A0h+cbData], 4
0x1800494c1  lea     rax, [r14+4]
0x1800494c5  lea     rcx, [rsp+2A0h+cbData]
0x1800494ca  mov     [rsp+2A0h+lpcbData], rcx; lpcbData
0x1800494cf  mov     [rsp+2A0h+phkResult], rax; lpData
0x1800494d4  lea     r9, [rsp+2A0h+Type]; lpType
0x1800494d9  xor     r8d, r8d; lpReserved
0x1800494dc  lea     rdx, aStarttimehi; "StartTimeHi"
0x1800494e3  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800494e8  call    cs:__imp_RegQueryValueExW
0x1800494ee  mov     edi, eax
0x1800494f0  test    eax, eax
0x1800494f2  jz      short loc_180049526
0x1800494f4  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800494fb  jz      loc_180049344
0x180049501  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180049508  test    rax, rax
0x18004950b  jz      short loc_180049491
0x18004950d  mov     r8d, edi
0x180049510  lea     rdx, aReadloggingsta_4; "ReadLoggingStatus: Failed to set STARTT"...
0x180049517  mov     ecx, 2
0x18004951c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049521  jmp     loc_180049344
0x180049526  mov     [rsp+2A0h+cbData], 4
0x18004952e  lea     rsi, [r14+8]
0x180049532  lea     rax, [rsp+2A0h+cbData]
0x180049537  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x18004953c  mov     [rsp+2A0h+phkResult], rsi; lpData
0x180049541  lea     r9, [rsp+2A0h+Type]; lpType
0x180049546  xor     r8d, r8d; lpReserved
0x180049549  lea     rdx, aEndtimelo; "EndTimeLo"
0x180049550  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180049555  call    cs:__imp_RegQueryValueExW
0x18004955b  mov     edi, eax
0x18004955d  test    eax, eax
0x18004955f  jz      short loc_1800495BB
0x180049561  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180049568  jz      loc_180049344
0x18004956e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180049575  test    rax, rax
0x180049578  jz      short loc_180049593
0x18004957a  mov     r8d, edi
0x18004957d  lea     rdx, aReadloggingsta; "ReadLoggingStatus: Failed to set ENDTIM"...
0x180049584  mov     ecx, 2
0x180049589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004958e  jmp     loc_180049344
0x180049593  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18004959b  jz      loc_180049344
0x1800495a1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800495a9  jz      loc_180049344
0x1800495af  lea     rdx, aReadloggingsta; "ReadLoggingStatus: Failed to set ENDTIM"...
0x1800495b6  jmp     loc_1800496E4
0x1800495bb  mov     [rsp+2A0h+cbData], 4
  ... truncated ...
```
