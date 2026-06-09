# CuipCheckActiveDesktop(ushort const *,ActiveDesktopType *)

- ea: `0x140005260`
- end: `0x140005697`
- name: `?CuipCheckActiveDesktop@@YAKPEBGPEAW4ActiveDesktopType@@@Z`
- size: `1079`
- prototype: `unsigned int __fastcall(wchar_t *String2, enum ActiveDesktopType *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140005040`
- `0x14001adb0`

## callees

- `0x140005260`
- `0x14000fbec`
- `0x140013928`
- `0x1400195d4`
- `0x14001baa0`
- `0x14001bb44`

## import_xrefs

- `USER32!CloseDesktop` at `0x1400054b8`
- `USER32!CloseDesktop` at `0x1400054b8`
- `USER32!GetUserObjectInformationW` at `0x1400053db`
- `USER32!GetUserObjectInformationW` at `0x140005468`
- `USER32!GetUserObjectInformationW` at `0x1400053db`
- `USER32!GetUserObjectInformationW` at `0x140005468`
- `USER32!OpenInputDesktop` at `0x1400053ac`
- `USER32!OpenInputDesktop` at `0x1400053ac`
- `msvcrt!_wcsicmp` at `0x1400054eb`
- `msvcrt!_wcsicmp` at `0x140005539`
- `msvcrt!_wcsicmp` at `0x14000558e`
- `msvcrt!_wcsicmp` at `0x1400054eb`
- `msvcrt!_wcsicmp` at `0x140005539`
- `msvcrt!_wcsicmp` at `0x14000558e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400052da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400052ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400053e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000561b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400052da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400052ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400053e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000561b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005671`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400054ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005577`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400055f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400054ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005577`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400055f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005440`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005440`
- `ntdll!EtwEventWrite` at `0x140005295`
- `ntdll!EtwEventWrite` at `0x140005329`
- `ntdll!EtwEventWrite` at `0x14000539c`
- `ntdll!EtwEventWrite` at `0x1400054db`
- `ntdll!EtwEventWrite` at `0x140005295`
- `ntdll!EtwEventWrite` at `0x140005329`
- `ntdll!EtwEventWrite` at `0x14000539c`
- `ntdll!EtwEventWrite` at `0x1400054db`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400052b7`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400052b7`
- `WTSAPI32!WTSFreeMemory` at `0x140005336`
- `WTSAPI32!WTSFreeMemory` at `0x140005336`

## pseudocode

```c
unsigned int __fastcall CuipCheckActiveDesktop(wchar_t *String2, enum ActiveDesktopType *a2)
{
  DWORD LastError; // eax
  unsigned int result; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  HDESK v8; // rdi
  HLOCAL v9; // rbx
  DWORD v10; // eax
  DWORD v11; // eax
  int v12; // edx
  int v13; // r8d
  __int64 v14; // rcx
  DWORD v15; // eax
  DWORD nLengthNeeded; // [rsp+68h] [rbp+10h] BYREF
  DWORD pBytesReturned; // [rsp+70h] [rbp+18h] BYREF
  LPWSTR ppBuffer; // [rsp+78h] [rbp+20h] BYREF

  *(_DWORD *)a2 = 0;
  ppBuffer = 0;
  pBytesReturned = 0;
  EtwEventWrite(g_ConsentPerfRegHandle, ConsentUI_QuerySessionInfo_Start, 0, 0);
  if ( !WTSQuerySessionInformationW(0, 0xFFFFFFFF, WTSConnectState, &ppBuffer, &pBytesReturned) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, LastError);
    }
    return GetLastError();
  }
  EtwEventWrite(g_ConsentPerfRegHandle, ConsentUI_QuerySessionInfo_Stop, 0, 0);
  v6 = *(_DWORD *)ppBuffer;
  WTSFreeMemory(ppBuffer);
  if ( v6 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, v7, v6);
    result = 0;
    *(_DWORD *)a2 = 5;
    return result;
  }
  EtwEventWrite(g_ConsentPerfRegHandle, ConsentUI_GetActiveDesktopName_Start, 0, 0);
  v8 = OpenInputDesktop(0, 0, 1u);
  if ( !v8 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    {
LABEL_50:
      if ( GetLastError() )
        return GetLastError();
      else
        return 14;
    }
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
    {
LABEL_47:
      if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(v14 + 16), 16, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
      goto LABEL_50;
    }
    v15 = GetLastError();
    WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v15);
LABEL_46:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_47;
  }
  nLengthNeeded = 0;
  GetUserObjectInformationW(v8, 2, 0, 0, &nLengthNeeded);
  if ( GetLastError() == 122 )
  {
    v9 = LocalAlloc(0x40u, nLengthNeeded);
    if ( v9 && !GetUserObjectInformationW(v8, 2, v9, nLengthNeeded, &nLengthNeeded) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v11 = GetLastError();
        WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v11);
      }
      LocalFree(v9);
      v9 = 0;
    }
  }
  else
  {
    v9 = 0;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v10 = GetLastError();
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v10);
    }
  }
  CloseDesktop(v8);
  if ( !v9 )
    goto LABEL_46;
  EtwEventWrite(g_ConsentPerfRegHandle, ConsentUI_GetActiveDesktopName_Stop, 0, 0);
  if ( _wcsicmp((const wchar_t *)v9, L"winlogon") )
  {
    if ( _wcsicmp((const wchar_t *)v9, String2) )
    {
      if ( _wcsicmp((const wchar_t *)v9, L"Screen-saver") )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_SS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v12, v13, (_DWORD)v9, (__int64)String2);
        *(_DWORD *)a2 = 1;
      }
      else
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
        *(_DWORD *)a2 = 4;
      }
      LocalFree(v9);
      return 0;
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, String2);
      *(_DWORD *)a2 = 2;
      LocalFree(v9);
      return 0;
    }
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
    *(_DWORD *)a2 = 3;
    LocalFree(v9);
    return 0;
  }
}

```

## disassembly

```asm
0x140005260  push    rbp
0x140005262  push    rsi
0x140005263  push    r14
0x140005265  push    r15
0x140005267  sub     rsp, 38h
0x14000526b  xor     r15d, r15d
0x14000526e  mov     r14, rdx
0x140005271  mov     [rdx], r15d
0x140005274  mov     rbp, rcx
0x140005277  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x14000527e  lea     rdx, ConsentUI_QuerySessionInfo_Start
0x140005285  xor     r9d, r9d
0x140005288  mov     [rsp+58h+ppBuffer], r15
0x14000528d  xor     r8d, r8d
0x140005290  mov     [rsp+58h+arg_10], r15d
0x140005295  call    cs:__imp_EtwEventWrite
0x14000529b  lea     rax, [rsp+58h+arg_10]
0x1400052a0  mov     edx, 0FFFFFFFFh; SessionId
0x1400052a5  lea     r9, [rsp+58h+ppBuffer]; ppBuffer
0x1400052aa  mov     [rsp+58h+pBytesReturned], rax; pBytesReturned
0x1400052af  xor     ecx, ecx; hServer
0x1400052b1  mov     r8d, 8; WTSInfoClass
0x1400052b7  call    cs:__imp_WTSQuerySessionInformationW
0x1400052bd  test    eax, eax
0x1400052bf  jnz     short loc_140005310
0x1400052c1  mov     rax, cs:WPP_GLOBAL_Control
0x1400052c8  lea     rsi, WPP_GLOBAL_Control
0x1400052cf  cmp     rax, rsi
0x1400052d2  jz      short loc_1400052FF
0x1400052d4  test    byte ptr [rax+1Ch], 4
0x1400052d8  jz      short loc_1400052FF
0x1400052da  call    cs:__imp_GetLastError
0x1400052e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400052e7  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x1400052ee  mov     edx, 0Eh
0x1400052f3  mov     r9d, eax
0x1400052f6  mov     rcx, [rcx+10h]
0x1400052fa  call    WPP_SF_D
0x1400052ff  call    cs:__imp_GetLastError
0x140005305  add     rsp, 38h
0x140005309  pop     r15
0x14000530b  pop     r14
0x14000530d  pop     rsi
0x14000530e  pop     rbp
0x14000530f  retn
0x140005310  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x140005317  lea     rdx, ConsentUI_QuerySessionInfo_Stop
0x14000531e  xor     r9d, r9d
0x140005321  mov     [rsp+58h+arg_0], rbx
0x140005326  xor     r8d, r8d
0x140005329  call    cs:__imp_EtwEventWrite
0x14000532f  mov     rcx, [rsp+58h+ppBuffer]; pMemory
0x140005334  mov     ebx, [rcx]
0x140005336  call    cs:__imp_WTSFreeMemory
0x14000533c  test    ebx, ebx
0x14000533e  jz      short loc_140005383
0x140005340  mov     rcx, cs:WPP_GLOBAL_Control
0x140005347  lea     rsi, WPP_GLOBAL_Control
0x14000534e  cmp     rcx, rsi
0x140005351  jz      short loc_14000536A
0x140005353  test    byte ptr [rcx+1Ch], 4
0x140005357  jz      short loc_14000536A
0x140005359  mov     rcx, [rcx+10h]
0x14000535d  mov     edx, 0Fh
0x140005362  mov     r9d, ebx
0x140005365  call    WPP_SF_l
0x14000536a  mov     rbx, [rsp+58h+arg_0]
0x14000536f  xor     eax, eax
0x140005371  mov     dword ptr [r14], 5
0x140005378  add     rsp, 38h
0x14000537c  pop     r15
0x14000537e  pop     r14
0x140005380  pop     rsi
0x140005381  pop     rbp
0x140005382  retn
0x140005383  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x14000538a  lea     rdx, ConsentUI_GetActiveDesktopName_Start
0x140005391  xor     r9d, r9d
0x140005394  mov     [rsp+58h+var_28], rdi
0x140005399  xor     r8d, r8d
0x14000539c  call    cs:__imp_EtwEventWrite
0x1400053a2  xor     edx, edx; fInherit
0x1400053a4  xor     ecx, ecx; dwFlags
0x1400053a6  mov     r8d, 1; dwDesiredAccess
0x1400053ac  call    cs:__imp_OpenInputDesktop
0x1400053b2  mov     rdi, rax
0x1400053b5  test    rax, rax
0x1400053b8  jz      loc_140005602
0x1400053be  lea     rax, [rsp+58h+nLengthNeeded]
0x1400053c3  mov     [rsp+58h+nLengthNeeded], r15d
0x1400053c8  xor     r9d, r9d; nLength
0x1400053cb  mov     [rsp+58h+pBytesReturned], rax; lpnLengthNeeded
0x1400053d0  xor     r8d, r8d; pvInfo
0x1400053d3  mov     edx, 2; nIndex
0x1400053d8  mov     rcx, rdi; hObj
0x1400053db  call    cs:__imp_GetUserObjectInformationW
0x1400053e1  call    cs:__imp_GetLastError
0x1400053e7  lea     rsi, WPP_GLOBAL_Control
0x1400053ee  cmp     eax, 7Ah ; 'z'
0x1400053f1  jz      short loc_140005437
0x1400053f3  mov     rbx, r15
0x1400053f6  mov     rax, cs:WPP_GLOBAL_Control
0x1400053fd  cmp     rax, rsi
0x140005400  jz      loc_1400054B5
0x140005406  test    byte ptr [rax+1Ch], 4
0x14000540a  jz      loc_1400054B5
0x140005410  call    cs:__imp_GetLastError
0x140005416  mov     rcx, cs:WPP_GLOBAL_Control
0x14000541d  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140005424  mov     edx, 0Ah
0x140005429  mov     r9d, eax
0x14000542c  mov     rcx, [rcx+10h]
0x140005430  call    WPP_SF_D
0x140005435  jmp     short loc_1400054B5
0x140005437  mov     edx, [rsp+58h+nLengthNeeded]; uBytes
0x14000543b  mov     ecx, 40h ; '@'; uFlags
0x140005440  call    cs:__imp_LocalAlloc
0x140005446  mov     rbx, rax
0x140005449  test    rax, rax
0x14000544c  jz      short loc_1400054B5
0x14000544e  mov     r9d, [rsp+58h+nLengthNeeded]; nLength
0x140005453  lea     rax, [rsp+58h+nLengthNeeded]
0x140005458  mov     r8, rbx; pvInfo
0x14000545b  mov     [rsp+58h+pBytesReturned], rax; lpnLengthNeeded
0x140005460  mov     edx, 2; nIndex
0x140005465  mov     rcx, rdi; hObj
0x140005468  call    cs:__imp_GetUserObjectInformationW
0x14000546e  test    eax, eax
0x140005470  jnz     short loc_1400054B5
0x140005472  mov     rax, cs:WPP_GLOBAL_Control
0x140005479  cmp     rax, rsi
0x14000547c  jz      short loc_1400054A9
0x14000547e  test    byte ptr [rax+1Ch], 4
0x140005482  jz      short loc_1400054A9
0x140005484  call    cs:__imp_GetLastError
0x14000548a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005491  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140005498  mov     edx, 0Bh
0x14000549d  mov     r9d, eax
0x1400054a0  mov     rcx, [rcx+10h]
0x1400054a4  call    WPP_SF_D
0x1400054a9  mov     rcx, rbx; hMem
0x1400054ac  call    cs:__imp_LocalFree
0x1400054b2  mov     rbx, r15
0x1400054b5  mov     rcx, rdi; hDesktop
0x1400054b8  call    cs:__imp_CloseDesktop
0x1400054be  test    rbx, rbx
0x1400054c1  jz      loc_140005640
0x1400054c7  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x1400054ce  lea     rdx, ConsentUI_GetActiveDesktopName_Stop
0x1400054d5  xor     r9d, r9d
0x1400054d8  xor     r8d, r8d
0x1400054db  call    cs:__imp_EtwEventWrite
0x1400054e1  lea     rdx, aWinlogon_0; "winlogon"
0x1400054e8  mov     rcx, rbx; String1
0x1400054eb  call    cs:__imp__wcsicmp
0x1400054f1  test    eax, eax
0x1400054f3  jnz     short loc_140005533
0x1400054f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400054fc  cmp     rcx, rsi
0x1400054ff  jz      short loc_14000551C
0x140005501  test    byte ptr [rcx+1Ch], 4
0x140005505  jz      short loc_14000551C
0x140005507  mov     rcx, [rcx+10h]
0x14000550b  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140005512  mov     edx, 11h
0x140005517  call    WPP_SF_
0x14000551c  mov     rcx, rbx; hMem
0x14000551f  mov     dword ptr [r14], 3
0x140005526  call    cs:__imp_LocalFree
0x14000552c  xor     eax, eax
0x14000552e  jmp     loc_140005682
0x140005533  mov     rdx, rbp; String2
0x140005536  mov     rcx, rbx; String1
0x140005539  call    cs:__imp__wcsicmp
0x14000553f  test    eax, eax
0x140005541  jnz     short loc_140005584
0x140005543  mov     rcx, cs:WPP_GLOBAL_Control
0x14000554a  cmp     rcx, rsi
0x14000554d  jz      short loc_14000556D
0x14000554f  test    byte ptr [rcx+1Ch], 4
0x140005553  jz      short loc_14000556D
0x140005555  mov     rcx, [rcx+10h]
0x140005559  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140005560  mov     edx, 12h
0x140005565  mov     r9, rbp
0x140005568  call    WPP_SF_S
0x14000556d  mov     rcx, rbx; hMem
0x140005570  mov     dword ptr [r14], 2
0x140005577  call    cs:__imp_LocalFree
0x14000557d  xor     eax, eax
0x14000557f  jmp     loc_140005682
0x140005584  lea     rdx, aScreenSaver; "Screen-saver"
0x14000558b  mov     rcx, rbx; String1
0x14000558e  call    cs:__imp__wcsicmp
0x140005594  test    eax, eax
0x140005596  jnz     short loc_1400055C8
0x140005598  mov     rcx, cs:WPP_GLOBAL_Control
0x14000559f  cmp     rcx, rsi
0x1400055a2  jz      short loc_1400055BF
0x1400055a4  test    byte ptr [rcx+1Ch], 4
0x1400055a8  jz      short loc_1400055BF
0x1400055aa  mov     rcx, [rcx+10h]
0x1400055ae  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x1400055b5  mov     edx, 13h
0x1400055ba  call    WPP_SF_
0x1400055bf  mov     dword ptr [r14], 4
0x1400055c6  jmp     short loc_1400055F2
0x1400055c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400055cf  cmp     rcx, rsi
0x1400055d2  jz      short loc_1400055EB
0x1400055d4  test    byte ptr [rcx+1Ch], 4
0x1400055d8  jz      short loc_1400055EB
0x1400055da  mov     rcx, [rcx+10h]
0x1400055de  mov     r9, rbx
0x1400055e1  mov     [rsp+58h+pBytesReturned], rbp
0x1400055e6  call    WPP_SF_SS
0x1400055eb  mov     dword ptr [r14], 1
0x1400055f2  mov     rcx, rbx; hMem
0x1400055f5  call    cs:__imp_LocalFree
0x1400055fb  xor     eax, eax
0x1400055fd  jmp     loc_140005682
0x140005602  mov     rcx, cs:WPP_GLOBAL_Control
0x140005609  lea     rsi, WPP_GLOBAL_Control
0x140005610  cmp     rcx, rsi
0x140005613  jz      short loc_140005667
0x140005615  test    byte ptr [rcx+1Ch], 4
0x140005619  jz      short loc_140005647
0x14000561b  call    cs:__imp_GetLastError
0x140005621  mov     rcx, cs:WPP_GLOBAL_Control
0x140005628  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000562f  mov     edx, 0Ch
0x140005634  mov     r9d, eax
0x140005637  mov     rcx, [rcx+10h]
0x14000563b  call    WPP_SF_D
0x140005640  mov     rcx, cs:WPP_GLOBAL_Control
0x140005647  cmp     rcx, rsi
0x14000564a  jz      short loc_140005667
0x14000564c  test    byte ptr [rcx+1Ch], 4
0x140005650  jz      short loc_140005667
0x140005652  mov     rcx, [rcx+10h]
0x140005656  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000565d  mov     edx, 10h
0x140005662  call    WPP_SF_
0x140005667  call    cs:__imp_GetLastError
0x14000566d  test    eax, eax
0x14000566f  jz      short loc_14000567B
0x140005671  call    cs:__imp_GetLastError
0x140005677  mov     ecx, eax
0x140005679  jmp     short loc_140005680
0x14000567b  mov     ecx, 0Eh
0x140005680  mov     eax, ecx
0x140005682  mov     rdi, [rsp+58h+var_28]
0x140005687  mov     rbx, [rsp+58h+arg_0]
0x14000568c  add     rsp, 38h
0x140005690  pop     r15
0x140005692  pop     r14
0x140005694  pop     rsi
0x140005695  pop     rbp
0x140005696  retn
```
