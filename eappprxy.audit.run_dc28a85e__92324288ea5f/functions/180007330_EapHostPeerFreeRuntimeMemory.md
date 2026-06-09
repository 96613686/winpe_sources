# EapHostPeerFreeRuntimeMemory

- ea: `0x180007330`
- end: `0x1800075b4`
- name: `EapHostPeerFreeRuntimeMemory`
- size: `644`
- prototype: `void __stdcall(BYTE *pData)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001780`
- `0x180005450`
- `0x180007330`
- `0x18000ace0`
- `0x18000adb4`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800073d6`
- `ntdll!EtwEventEnabled` at `0x1800074a4`
- `ntdll!EtwEventEnabled` at `0x1800073d6`
- `ntdll!EtwEventEnabled` at `0x1800074a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007361`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007361`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007373`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007373`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000748a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000748a`

## pseudocode

```c
void __stdcall EapHostPeerFreeRuntimeMemory(BYTE *pData)
{
  unsigned __int64 v2; // rbx
  DWORD TickCount; // eax
  int v4; // r8d
  unsigned __int64 v5; // rdi
  __int64 v6; // rbx
  int v7; // r8d
  __int64 v8; // rax
  int v9; // r8d
  unsigned __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[16]; // [rsp+38h] [rbp-C8h] BYREF
  char *v12; // [rsp+48h] [rbp-B8h]
  __int64 v13; // [rsp+50h] [rbp-B0h]
  char v14[2048]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = (unsigned __int64)GetCurrentThreadId() << 32;
  TickCount = GetTickCount();
  v5 = v2 | TickCount;
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v10 = v2 | TickCount;
    v12 = (char *)&v10;
    v13 = 8;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)FreeRuntimeMemoryStart,
      v4,
      2,
      (__int64)v11);
  }
  v6 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v14, 0x800u, "EapHostPeerFreeRuntimeMemory Entry") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v14[v8] );
    v13 = (unsigned int)(v8 + 1);
    v12 = v14;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v7,
      2,
      (__int64)v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_e9255469090b376a053f3594056fdc10_Traceguids);
  CoTaskMemFree(pData);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v14, 0x800u, "EapHostPeerFreeRuntimeMemory Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    do
      ++v6;
    while ( v14[v6] );
    v13 = (unsigned int)(v6 + 1);
    v12 = v14;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v9,
      2,
      (__int64)v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_e9255469090b376a053f3594056fdc10_Traceguids);
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v10 = v5;
    v12 = (char *)&v10;
    v13 = 8;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)FreeRuntimeMemoryEnd,
      v9,
      2,
      (__int64)v11);
  }
}

```

## disassembly

```asm
0x180007330  mov     [rsp-8+arg_8], rbx
0x180007335  mov     [rsp-8+arg_10], rsi
0x18000733a  push    rbp
0x18000733b  push    rdi
0x18000733c  push    r15
0x18000733e  lea     rbp, [rsp-770h]
0x180007346  sub     rsp, 870h
0x18000734d  mov     rax, cs:__security_cookie
0x180007354  xor     rax, rsp
0x180007357  mov     [rbp+780h+var_20], rax
0x18000735e  mov     rsi, rcx
0x180007361  call    cs:__imp_GetCurrentThreadId
0x180007368  nop     dword ptr [rax+rax+00h]
0x18000736d  mov     ebx, eax
0x18000736f  shl     rbx, 20h
0x180007373  call    cs:__imp_GetTickCount
0x18000737a  nop     dword ptr [rax+rax+00h]
0x18000737f  mov     edi, eax
0x180007381  or      rdi, rbx
0x180007384  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18000738b  jge     short loc_1800073C8
0x18000738d  lea     rax, [rsp+880h+var_850]
0x180007392  mov     [rsp+880h+var_850], rdi
0x180007397  mov     [rsp+880h+var_838], rax
0x18000739c  lea     rdx, FreeRuntimeMemoryStart
0x1800073a3  lea     rax, [rsp+880h+var_848]
0x1800073a8  mov     [rsp+880h+var_830], 8
0x1800073b1  mov     r9d, 2
0x1800073b7  mov     [rsp+880h+var_860], rax
0x1800073bc  lea     rcx, eaphost_Context
0x1800073c3  call    McGenEventWrite_EtwEventWriteTransfer
0x1800073c8  mov     rcx, cs:eaphost_Context
0x1800073cf  lea     rdx, DebugInfoEvent
0x1800073d6  call    cs:__imp_EtwEventEnabled
0x1800073dd  nop     dword ptr [rax+rax+00h]
0x1800073e2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800073e6  test    al, al
0x1800073e8  jz      short loc_180007459
0x1800073ea  lea     r8, aEaphostpeerfre_3; "EapHostPeerFreeRuntimeMemory Entry"
0x1800073f1  mov     edx, 800h; unsigned __int64
0x1800073f6  lea     rcx, [rsp+880h+var_820]; char *
0x1800073fb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007400  test    eax, eax
0x180007402  js      short loc_180007459
0x180007404  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18000740b  jge     short loc_180007459
0x18000740d  lea     rcx, [rsp+880h+var_820]
0x180007412  mov     rax, rbx
0x180007415  inc     rax
0x180007418  cmp     byte ptr [rcx+rax], 0
0x18000741c  jnz     short loc_180007415
0x18000741e  inc     eax
0x180007420  mov     dword ptr [rsp+880h+var_830+4], 0
0x180007428  lea     rcx, [rsp+880h+var_820]
0x18000742d  mov     dword ptr [rsp+880h+var_830], eax
0x180007431  lea     rax, [rsp+880h+var_848]
0x180007436  mov     [rsp+880h+var_838], rcx
0x18000743b  mov     r9d, 2
0x180007441  mov     [rsp+880h+var_860], rax
0x180007446  lea     rdx, DebugInfoEvent
0x18000744d  lea     rcx, eaphost_Context
0x180007454  call    McGenEventWrite_EtwEventWriteTransfer
0x180007459  mov     rcx, cs:WPP_GLOBAL_Control
0x180007460  lea     r15, WPP_GLOBAL_Control
0x180007467  cmp     rcx, r15
0x18000746a  jz      short loc_180007487
0x18000746c  test    byte ptr [rcx+1Ch], 4
0x180007470  jz      short loc_180007487
0x180007472  mov     rcx, [rcx+10h]
0x180007476  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x18000747d  mov     edx, 36h ; '6'
0x180007482  call    WPP_SF_
0x180007487  mov     rcx, rsi; pv
0x18000748a  call    cs:__imp_CoTaskMemFree
0x180007491  nop     dword ptr [rax+rax+00h]
0x180007496  mov     rcx, cs:eaphost_Context
0x18000749d  lea     rdx, DebugInfoEvent
0x1800074a4  call    cs:__imp_EtwEventEnabled
0x1800074ab  nop     dword ptr [rax+rax+00h]
0x1800074b0  test    al, al
0x1800074b2  jz      short loc_180007521
0x1800074b4  lea     r8, aEaphostpeerfre_1; "EapHostPeerFreeRuntimeMemory Exit"
0x1800074bb  mov     edx, 800h; unsigned __int64
0x1800074c0  lea     rcx, [rsp+880h+var_820]; char *
0x1800074c5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800074ca  test    eax, eax
0x1800074cc  js      short loc_180007521
0x1800074ce  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x1800074d5  jge     short loc_180007521
0x1800074d7  lea     rax, [rsp+880h+var_820]
0x1800074dc  inc     rbx
0x1800074df  cmp     byte ptr [rax+rbx], 0
0x1800074e3  jnz     short loc_1800074DC
0x1800074e5  lea     eax, [rbx+1]
0x1800074e8  mov     dword ptr [rsp+880h+var_830+4], 0
0x1800074f0  lea     rcx, [rsp+880h+var_820]
0x1800074f5  mov     dword ptr [rsp+880h+var_830], eax
0x1800074f9  lea     rax, [rsp+880h+var_848]
0x1800074fe  mov     [rsp+880h+var_838], rcx
0x180007503  mov     r9d, 2
0x180007509  mov     [rsp+880h+var_860], rax
0x18000750e  lea     rdx, DebugInfoEvent
0x180007515  lea     rcx, eaphost_Context
0x18000751c  call    McGenEventWrite_EtwEventWriteTransfer
0x180007521  mov     rcx, cs:WPP_GLOBAL_Control
0x180007528  cmp     rcx, r15
0x18000752b  jz      short loc_180007548
0x18000752d  test    byte ptr [rcx+1Ch], 4
0x180007531  jz      short loc_180007548
0x180007533  mov     rcx, [rcx+10h]
0x180007537  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x18000753e  mov     edx, 37h ; '7'
0x180007543  call    WPP_SF_
0x180007548  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18000754f  jge     short loc_18000758C
0x180007551  lea     rax, [rsp+880h+var_850]
0x180007556  mov     [rsp+880h+var_850], rdi
0x18000755b  mov     [rsp+880h+var_838], rax
0x180007560  lea     rdx, FreeRuntimeMemoryEnd
0x180007567  lea     rax, [rsp+880h+var_848]
0x18000756c  mov     [rsp+880h+var_830], 8
0x180007575  mov     r9d, 2
0x18000757b  mov     [rsp+880h+var_860], rax
0x180007580  lea     rcx, eaphost_Context
0x180007587  call    McGenEventWrite_EtwEventWriteTransfer
0x18000758c  mov     rcx, [rbp+780h+var_20]
0x180007593  xor     rcx, rsp; StackCookie
0x180007596  call    __security_check_cookie
0x18000759b  lea     r11, [rsp+880h+var_10]
0x1800075a3  mov     rbx, [r11+28h]
0x1800075a7  mov     rsi, [r11+30h]
0x1800075ab  mov     rsp, r11
0x1800075ae  pop     r15
0x1800075b0  pop     rdi
0x1800075b1  pop     rbp
0x1800075b2  retn
```
