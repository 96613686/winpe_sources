# EapHostPeerFreeEapError

- ea: `0x180007090`
- end: `0x180007321`
- name: `EapHostPeerFreeEapError`
- size: `657`
- prototype: `void __stdcall(EAP_ERROR *pEapError)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006100`

## callees

- `0x180001780`
- `0x1800022a8`
- `0x180005450`
- `0x180007090`
- `0x18000ace0`
- `0x18000adb4`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180007136`
- `ntdll!EtwEventEnabled` at `0x180007211`
- `ntdll!EtwEventEnabled` at `0x180007136`
- `ntdll!EtwEventEnabled` at `0x180007211`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800070d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800070d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071f7`

## pseudocode

```c
void __stdcall EapHostPeerFreeEapError(EAP_ERROR *pEapError)
{
  unsigned __int64 v2; // rbx
  DWORD TickCount; // eax
  int v4; // r8d
  unsigned __int64 v5; // rsi
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
      (unsigned int)FreeEapErrorStart,
      v4,
      2,
      (__int64)v11);
  }
  v6 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v14, 0x800u, "EapHostPeerFreeEapError Entry") >= 0
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_e9255469090b376a053f3594056fdc10_Traceguids);
  if ( pEapError )
  {
    Free<TaskAllocator>((LPVOID *)pEapError);
    CoTaskMemFree(pEapError);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v14, 0x800u, "EapHostPeerFreeEapError Exit") >= 0
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_e9255469090b376a053f3594056fdc10_Traceguids);
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v10 = v5;
    v12 = (char *)&v10;
    v13 = 8;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)FreeEapErrorEnd,
      v9,
      2,
      (__int64)v11);
  }
}

```

## disassembly

```asm
0x180007090  mov     [rsp-8+arg_8], rbx
0x180007095  mov     [rsp-8+arg_10], rsi
0x18000709a  push    rbp
0x18000709b  push    rdi
0x18000709c  push    r15
0x18000709e  lea     rbp, [rsp-770h]
0x1800070a6  sub     rsp, 870h
0x1800070ad  mov     rax, cs:__security_cookie
0x1800070b4  xor     rax, rsp
0x1800070b7  mov     [rbp+780h+var_20], rax
0x1800070be  mov     rdi, rcx
0x1800070c1  call    cs:__imp_GetCurrentThreadId
0x1800070c8  nop     dword ptr [rax+rax+00h]
0x1800070cd  mov     ebx, eax
0x1800070cf  shl     rbx, 20h
0x1800070d3  call    cs:__imp_GetTickCount
0x1800070da  nop     dword ptr [rax+rax+00h]
0x1800070df  mov     esi, eax
0x1800070e1  or      rsi, rbx
0x1800070e4  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x1800070eb  jge     short loc_180007128
0x1800070ed  lea     rax, [rsp+880h+var_850]
0x1800070f2  mov     [rsp+880h+var_850], rsi
0x1800070f7  mov     [rsp+880h+var_838], rax
0x1800070fc  lea     rdx, FreeEapErrorStart
0x180007103  lea     rax, [rsp+880h+var_848]
0x180007108  mov     [rsp+880h+var_830], 8
0x180007111  mov     r9d, 2
0x180007117  mov     [rsp+880h+var_860], rax
0x18000711c  lea     rcx, eaphost_Context
0x180007123  call    McGenEventWrite_EtwEventWriteTransfer
0x180007128  mov     rcx, cs:eaphost_Context
0x18000712f  lea     rdx, DebugInfoEvent
0x180007136  call    cs:__imp_EtwEventEnabled
0x18000713d  nop     dword ptr [rax+rax+00h]
0x180007142  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007146  test    al, al
0x180007148  jz      short loc_1800071B9
0x18000714a  lea     r8, aEaphostpeerfre_2; "EapHostPeerFreeEapError Entry"
0x180007151  mov     edx, 800h; unsigned __int64
0x180007156  lea     rcx, [rsp+880h+var_820]; char *
0x18000715b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007160  test    eax, eax
0x180007162  js      short loc_1800071B9
0x180007164  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18000716b  jge     short loc_1800071B9
0x18000716d  lea     rcx, [rsp+880h+var_820]
0x180007172  mov     rax, rbx
0x180007175  inc     rax
0x180007178  cmp     byte ptr [rcx+rax], 0
0x18000717c  jnz     short loc_180007175
0x18000717e  inc     eax
0x180007180  mov     dword ptr [rsp+880h+var_830+4], 0
0x180007188  lea     rcx, [rsp+880h+var_820]
0x18000718d  mov     dword ptr [rsp+880h+var_830], eax
0x180007191  lea     rax, [rsp+880h+var_848]
0x180007196  mov     [rsp+880h+var_838], rcx
0x18000719b  mov     r9d, 2
0x1800071a1  mov     [rsp+880h+var_860], rax
0x1800071a6  lea     rdx, DebugInfoEvent
0x1800071ad  lea     rcx, eaphost_Context
0x1800071b4  call    McGenEventWrite_EtwEventWriteTransfer
0x1800071b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071c0  lea     r15, WPP_GLOBAL_Control
0x1800071c7  cmp     rcx, r15
0x1800071ca  jz      short loc_1800071E7
0x1800071cc  test    byte ptr [rcx+1Ch], 4
0x1800071d0  jz      short loc_1800071E7
0x1800071d2  mov     rcx, [rcx+10h]
0x1800071d6  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x1800071dd  mov     edx, 34h ; '4'
0x1800071e2  call    WPP_SF_
0x1800071e7  test    rdi, rdi
0x1800071ea  jz      short loc_180007203
0x1800071ec  mov     rcx, rdi; void *
0x1800071ef  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x1800071f4  mov     rcx, rdi; pv
0x1800071f7  call    cs:__imp_CoTaskMemFree
0x1800071fe  nop     dword ptr [rax+rax+00h]
0x180007203  mov     rcx, cs:eaphost_Context
0x18000720a  lea     rdx, DebugInfoEvent
0x180007211  call    cs:__imp_EtwEventEnabled
0x180007218  nop     dword ptr [rax+rax+00h]
0x18000721d  test    al, al
0x18000721f  jz      short loc_18000728E
0x180007221  lea     r8, aEaphostpeerfre_4; "EapHostPeerFreeEapError Exit"
0x180007228  mov     edx, 800h; unsigned __int64
0x18000722d  lea     rcx, [rsp+880h+var_820]; char *
0x180007232  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007237  test    eax, eax
0x180007239  js      short loc_18000728E
0x18000723b  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180007242  jge     short loc_18000728E
0x180007244  lea     rax, [rsp+880h+var_820]
0x180007249  inc     rbx
0x18000724c  cmp     byte ptr [rax+rbx], 0
0x180007250  jnz     short loc_180007249
0x180007252  lea     eax, [rbx+1]
0x180007255  mov     dword ptr [rsp+880h+var_830+4], 0
0x18000725d  lea     rcx, [rsp+880h+var_820]
0x180007262  mov     dword ptr [rsp+880h+var_830], eax
0x180007266  lea     rax, [rsp+880h+var_848]
0x18000726b  mov     [rsp+880h+var_838], rcx
0x180007270  mov     r9d, 2
0x180007276  mov     [rsp+880h+var_860], rax
0x18000727b  lea     rdx, DebugInfoEvent
0x180007282  lea     rcx, eaphost_Context
0x180007289  call    McGenEventWrite_EtwEventWriteTransfer
0x18000728e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007295  cmp     rcx, r15
0x180007298  jz      short loc_1800072B5
0x18000729a  test    byte ptr [rcx+1Ch], 4
0x18000729e  jz      short loc_1800072B5
0x1800072a0  mov     rcx, [rcx+10h]
0x1800072a4  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x1800072ab  mov     edx, 35h ; '5'
0x1800072b0  call    WPP_SF_
0x1800072b5  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x1800072bc  jge     short loc_1800072F9
0x1800072be  lea     rax, [rsp+880h+var_850]
0x1800072c3  mov     [rsp+880h+var_850], rsi
0x1800072c8  mov     [rsp+880h+var_838], rax
0x1800072cd  lea     rdx, FreeEapErrorEnd
0x1800072d4  lea     rax, [rsp+880h+var_848]
0x1800072d9  mov     [rsp+880h+var_830], 8
0x1800072e2  mov     r9d, 2
0x1800072e8  mov     [rsp+880h+var_860], rax
0x1800072ed  lea     rcx, eaphost_Context
0x1800072f4  call    McGenEventWrite_EtwEventWriteTransfer
0x1800072f9  mov     rcx, [rbp+780h+var_20]
0x180007300  xor     rcx, rsp; StackCookie
0x180007303  call    __security_check_cookie
0x180007308  lea     r11, [rsp+880h+var_10]
0x180007310  mov     rbx, [r11+28h]
0x180007314  mov     rsi, [r11+30h]
0x180007318  mov     rsp, r11
0x18000731b  pop     r15
0x18000731d  pop     rdi
0x18000731e  pop     rbp
0x18000731f  retn
```
