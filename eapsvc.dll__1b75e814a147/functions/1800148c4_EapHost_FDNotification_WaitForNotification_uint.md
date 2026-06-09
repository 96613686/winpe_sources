# EapHost::FDNotification::WaitForNotification(uint)

- ea: `0x1800148c4`
- end: `0x180014c80`
- name: `?WaitForNotification@FDNotification@EapHost@@QEAAXI@Z`
- size: `956`
- prototype: `void __fastcall(HANDLE *this, DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011cb0`

## callees

- `0x180001f60`
- `0x18000a5ac`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c1a8`
- `0x18000c39c`
- `0x18000c40c`
- `0x18000db80`
- `0x180010f18`
- `0x1800147b4`
- `0x1800148c4`
- `0x180014e74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800149da`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800149da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014acf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014acf`
- `ntdll!EtwEventEnabled` at `0x180014915`
- `ntdll!EtwEventEnabled` at `0x180014a09`
- `ntdll!EtwEventEnabled` at `0x180014ae5`
- `ntdll!EtwEventEnabled` at `0x180014b85`
- `ntdll!EtwEventEnabled` at `0x180014c0d`
- `ntdll!EtwEventEnabled` at `0x180014915`
- `ntdll!EtwEventEnabled` at `0x180014a09`
- `ntdll!EtwEventEnabled` at `0x180014ae5`
- `ntdll!EtwEventEnabled` at `0x180014b85`
- `ntdll!EtwEventEnabled` at `0x180014c0d`

## string_xrefs

- `0x180014b8f`: `Detected service shutdown while waiting for FD notification`

## pseudocode

```c
void __fastcall EapHost::FDNotification::WaitForNotification(HANDLE *this, DWORD dwMilliseconds)
{
  __int64 v4; // rbx
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rax
  DWORD v8; // edi
  int v9; // r8d
  int v10; // r9d
  signed int LastError; // ebx
  const wchar_t *v12; // rcx
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handles[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[16]; // [rsp+48h] [rbp-B8h] BYREF
  char *v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+64h] [rbp-9Ch]
  char v19[2048]; // [rsp+70h] [rbp-90h] BYREF

  Handles[0] = this[1];
  Handles[1] = this[3];
  v4 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v19, 0x800u, "Waiting for FD notification for max %u milliseconds ...", dwMilliseconds) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v19[v7] );
    v18 = 0;
    v17 = v7 + 1;
    v16 = v19;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v5,
      v6,
      (__int64)v15);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids, dwMilliseconds);
  v8 = WaitForMultipleObjectsEx(2u, Handles, 0, dwMilliseconds, 0);
  EapHost::FDNotification::StopWaiting((EapHost::FDNotification *)this);
  if ( !v8 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v19, 0x800u, "Detected service shutdown while waiting for FD notification") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v19);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids);
    throw (EapHost::ECPShutdownException *)&pExceptionObject;
  }
  if ( v8 != 1 )
  {
    if ( v8 != 258 )
    {
      LastError = GetLastError();
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
        && (int)StringCchPrintfA(
                  v19,
                  0x800u,
                  "Waiting for FD notification failed, wait result is %u, win err is 0x%x",
                  v8,
                  LastError) >= 0
        && (byte_180020AC1 & 8) != 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v19);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids,
          v8,
          LastError);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      SystemError::Throw<long>((__int64)&byte_180018CBC, LastError);
    }
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v19, 0x800u, "Waiting for FD notification timed out") >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v19);
    }
    v12 = (const wchar_t *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids);
    ApplicationError::Throw(v12, -2147023436);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v19, 0x800u, "Wait for FD notification succeeded") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    do
      ++v4;
    while ( v19[v4] );
    v18 = 0;
    v17 = v4 + 1;
    v16 = v19;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v9,
      v10,
      (__int64)v15);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids);
}

```

## disassembly

```asm
0x1800148c4  mov     [rsp-8+arg_10], rbx
0x1800148c9  push    rbp
0x1800148ca  push    rsi
0x1800148cb  push    rdi
0x1800148cc  push    r12
0x1800148ce  push    r15
0x1800148d0  lea     rbp, [rsp-780h]
0x1800148d8  sub     rsp, 880h
0x1800148df  mov     rax, cs:__security_cookie
0x1800148e6  xor     rax, rsp
0x1800148e9  mov     [rbp+7A0h+var_30], rax
0x1800148f0  mov     rax, [rcx+8]
0x1800148f4  mov     edi, edx
0x1800148f6  mov     [rsp+8A0h+Handles], rax
0x1800148fb  lea     rdx, DebugInfoEvent
0x180014902  mov     rax, [rcx+18h]
0x180014906  mov     rsi, rcx
0x180014909  mov     rcx, cs:eaphost_Context
0x180014910  mov     [rsp+8A0h+var_860], rax
0x180014915  call    cs:__imp_EtwEventEnabled
0x18001491b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001491f  test    al, al
0x180014921  jz      short loc_18001498F
0x180014923  mov     r9d, edi
0x180014926  lea     r8, aWaitingForFdNo_1; "Waiting for FD notification for max %u "...
0x18001492d  mov     edx, 800h; unsigned __int64
0x180014932  lea     rcx, [rsp+8A0h+var_830]; char *
0x180014937  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001493c  test    eax, eax
0x18001493e  js      short loc_18001498F
0x180014940  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180014947  jge     short loc_18001498F
0x180014949  lea     rcx, [rsp+8A0h+var_830]
0x18001494e  mov     rax, rbx
0x180014951  inc     rax
0x180014954  cmp     byte ptr [rcx+rax], 0
0x180014958  jnz     short loc_180014951
0x18001495a  inc     eax
0x18001495c  mov     [rsp+8A0h+var_83C], 0
0x180014964  lea     rcx, [rsp+8A0h+var_830]
0x180014969  mov     [rsp+8A0h+var_840], eax
0x18001496d  lea     rax, [rsp+8A0h+var_858]
0x180014972  mov     [rsp+8A0h+var_848], rcx
0x180014977  lea     rdx, DebugInfoEvent
0x18001497e  mov     qword ptr [rsp+8A0h+bAlertable], rax
0x180014983  lea     rcx, eaphost_Context
0x18001498a  call    McGenEventWrite_EtwEventWriteTransfer
0x18001498f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014996  lea     r15, WPP_GLOBAL_Control
0x18001499d  lea     r12, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x1800149a4  cmp     rcx, r15
0x1800149a7  jz      short loc_1800149C3
0x1800149a9  test    byte ptr [rcx+1Ch], 4
0x1800149ad  jz      short loc_1800149C3
0x1800149af  mov     rcx, [rcx+10h]
0x1800149b3  mov     edx, 10h
0x1800149b8  mov     r9d, edi
0x1800149bb  mov     r8, r12
0x1800149be  call    WPP_SF_d
0x1800149c3  xor     r8d, r8d; bWaitAll
0x1800149c6  mov     [rsp+8A0h+bAlertable], 0; bAlertable
0x1800149ce  mov     r9d, edi; dwMilliseconds
0x1800149d1  lea     rdx, [rsp+8A0h+Handles]; lpHandles
0x1800149d6  lea     ecx, [r8+2]; nCount
0x1800149da  call    cs:__imp_WaitForMultipleObjectsEx
0x1800149e0  mov     rcx, rsi; this
0x1800149e3  mov     edi, eax
0x1800149e5  call    ?StopWaiting@FDNotification@EapHost@@QEAAXXZ; EapHost::FDNotification::StopWaiting(void)
0x1800149ea  test    edi, edi
0x1800149ec  jz      loc_180014B77
0x1800149f2  cmp     edi, 1
0x1800149f5  jnz     loc_180014AC3
0x1800149fb  mov     rcx, cs:eaphost_Context
0x180014a02  lea     rdx, DebugInfoEvent
0x180014a09  call    cs:__imp_EtwEventEnabled
0x180014a0f  test    al, al
0x180014a11  jz      short loc_180014A7A
0x180014a13  lea     r8, aWaitForFdNotif; "Wait for FD notification succeeded"
0x180014a1a  mov     edx, 800h; unsigned __int64
0x180014a1f  lea     rcx, [rsp+8A0h+var_830]; char *
0x180014a24  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180014a29  test    eax, eax
0x180014a2b  js      short loc_180014A7A
0x180014a2d  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180014a34  jge     short loc_180014A7A
0x180014a36  lea     rax, [rsp+8A0h+var_830]
0x180014a3b  inc     rbx
0x180014a3e  cmp     byte ptr [rax+rbx], 0
0x180014a42  jnz     short loc_180014A3B
0x180014a44  lea     eax, [rbx+1]
0x180014a47  mov     [rsp+8A0h+var_83C], 0
0x180014a4f  lea     rcx, [rsp+8A0h+var_830]
0x180014a54  mov     [rsp+8A0h+var_840], eax
0x180014a58  lea     rax, [rsp+8A0h+var_858]
0x180014a5d  mov     [rsp+8A0h+var_848], rcx
0x180014a62  lea     rdx, DebugInfoEvent
0x180014a69  mov     qword ptr [rsp+8A0h+bAlertable], rax
0x180014a6e  lea     rcx, eaphost_Context
0x180014a75  call    McGenEventWrite_EtwEventWriteTransfer
0x180014a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a81  cmp     rcx, r15
0x180014a84  jz      short loc_180014A9D
0x180014a86  test    byte ptr [rcx+1Ch], 4
0x180014a8a  jz      short loc_180014A9D
0x180014a8c  mov     rcx, [rcx+10h]
0x180014a90  mov     edx, 12h
0x180014a95  mov     r8, r12
0x180014a98  call    WPP_SF_
0x180014a9d  mov     rcx, [rbp+7A0h+var_30]
0x180014aa4  xor     rcx, rsp; StackCookie
0x180014aa7  call    __security_check_cookie
0x180014aac  mov     rbx, [rsp+8A0h+arg_10]
0x180014ab4  add     rsp, 880h
0x180014abb  pop     r15
0x180014abd  pop     r12
0x180014abf  pop     rdi
0x180014ac0  pop     rsi
0x180014ac1  pop     rbp
0x180014ac2  retn
0x180014ac3  cmp     edi, 102h
0x180014ac9  jz      loc_180014BFF
0x180014acf  call    cs:__imp_GetLastError
0x180014ad5  mov     rcx, cs:eaphost_Context
0x180014adc  lea     rdx, DebugErrorEvent
0x180014ae3  mov     ebx, eax
0x180014ae5  call    cs:__imp_EtwEventEnabled
0x180014aeb  test    al, al
0x180014aed  jz      short loc_180014B31
0x180014aef  mov     r9d, edi
0x180014af2  mov     [rsp+8A0h+bAlertable], ebx
0x180014af6  lea     r8, aWaitingForFdNo_0; "Waiting for FD notification failed, wai"...
0x180014afd  mov     edx, 800h; unsigned __int64
0x180014b02  lea     rcx, [rsp+8A0h+var_830]; char *
0x180014b07  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180014b0c  test    eax, eax
0x180014b0e  js      short loc_180014B31
0x180014b10  test    cs:byte_180020AC1, 8
0x180014b17  jz      short loc_180014B31
0x180014b19  lea     r8, [rsp+8A0h+var_830]
0x180014b1e  lea     rdx, DebugErrorEvent
0x180014b25  lea     rcx, eaphost_Context
0x180014b2c  call    McTemplateU0s_EtwEventWriteTransfer
0x180014b31  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b38  cmp     rcx, r15
0x180014b3b  jz      short loc_180014B5B
0x180014b3d  test    byte ptr [rcx+1Ch], 1
0x180014b41  jz      short loc_180014B5B
0x180014b43  mov     rcx, [rcx+10h]
0x180014b47  mov     edx, 14h
0x180014b4c  mov     r9d, edi
0x180014b4f  mov     [rsp+8A0h+bAlertable], ebx
0x180014b53  mov     r8, r12
0x180014b56  call    WPP_SF_DD
0x180014b5b  test    ebx, ebx
0x180014b5d  jle     short loc_180014B68
0x180014b5f  movzx   ebx, bx
0x180014b62  or      ebx, 80070000h
0x180014b68  mov     edx, ebx
0x180014b6a  lea     rcx, byte_180018CBC
0x180014b71  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
0x180014b77  mov     rcx, cs:eaphost_Context
0x180014b7e  lea     rdx, DebugInfoEvent
0x180014b85  call    cs:__imp_EtwEventEnabled
0x180014b8b  test    al, al
0x180014b8d  jz      short loc_180014BCA
0x180014b8f  lea     r8, aDetectedServic_0; "Detected service shutdown while waiting"...
0x180014b96  mov     edx, 800h; unsigned __int64
0x180014b9b  lea     rcx, [rsp+8A0h+var_830]; char *
0x180014ba0  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180014ba5  test    eax, eax
0x180014ba7  js      short loc_180014BCA
0x180014ba9  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180014bb0  jge     short loc_180014BCA
0x180014bb2  lea     r8, [rsp+8A0h+var_830]
0x180014bb7  lea     rdx, DebugInfoEvent
0x180014bbe  lea     rcx, eaphost_Context
0x180014bc5  call    McTemplateU0s_EtwEventWriteTransfer
0x180014bca  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bd1  cmp     rcx, r15
0x180014bd4  jz      short loc_180014BED
0x180014bd6  test    byte ptr [rcx+1Ch], 4
0x180014bda  jz      short loc_180014BED
0x180014bdc  mov     rcx, [rcx+10h]
0x180014be0  mov     edx, 11h
0x180014be5  mov     r8, r12
0x180014be8  call    WPP_SF_
0x180014bed  lea     rdx, _TI1?AVECPShutdownException@EapHost@@; pThrowInfo
0x180014bf4  lea     rcx, [rsp+8A0h+pExceptionObject]; pExceptionObject
0x180014bf9  call    _CxxThrowException_0
0x180014bff  mov     rcx, cs:eaphost_Context
0x180014c06  lea     rdx, DebugErrorEvent
0x180014c0d  call    cs:__imp_EtwEventEnabled
0x180014c13  test    al, al
0x180014c15  jz      short loc_180014C52
0x180014c17  lea     r8, aWaitingForFdNo; "Waiting for FD notification timed out"
0x180014c1e  mov     edx, 800h; unsigned __int64
0x180014c23  lea     rcx, [rsp+8A0h+var_830]; char *
0x180014c28  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180014c2d  test    eax, eax
0x180014c2f  js      short loc_180014C52
0x180014c31  test    cs:byte_180020AC1, 8
0x180014c38  jz      short loc_180014C52
0x180014c3a  lea     r8, [rsp+8A0h+var_830]
0x180014c3f  lea     rdx, DebugErrorEvent
0x180014c46  lea     rcx, eaphost_Context
0x180014c4d  call    McTemplateU0s_EtwEventWriteTransfer
0x180014c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c59  cmp     rcx, r15
0x180014c5c  jz      short loc_180014C75
0x180014c5e  test    byte ptr [rcx+1Ch], 1
0x180014c62  jz      short loc_180014C75
0x180014c64  mov     rcx, [rcx+10h]
0x180014c68  mov     edx, 13h
0x180014c6d  mov     r8, r12
0x180014c70  call    WPP_SF_
0x180014c75  mov     edx, 800705B4h; int
0x180014c7a  call    ?Throw@ApplicationError@@SAXPEB_WJ@Z; ApplicationError::Throw(wchar_t const *,long)
```
