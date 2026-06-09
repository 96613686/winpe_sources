# CheckLauncherCompatibilityStatus(CompatibilityStatus *)

- ea: `0x180005a68`
- end: `0x180005c91`
- name: `?CheckLauncherCompatibilityStatus@@YAHPEAW4CompatibilityStatus@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(enum CompatibilityStatus *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bb80`

## callees

- `0x180005528`
- `0x180005638`
- `0x180005a68`
- `0x1800075fc`
- `0x180008720`
- `0x180008a08`
- `0x180008a40`
- `0x180008a70`
- `0x180008ac8`
- `0x180008af0`
- `0x180008cf0`
- `0x18000fe10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005b0d`
- `KERNEL32!GetLastError` at `0x180005b97`
- `KERNEL32!GetLastError` at `0x180005c38`
- `KERNEL32!GetLastError` at `0x180005b0d`
- `KERNEL32!GetLastError` at `0x180005b97`
- `KERNEL32!GetLastError` at `0x180005c38`
- `KERNEL32!SetLastError` at `0x180005c20`
- `KERNEL32!SetLastError` at `0x180005c20`

## string_xrefs

- `0x180005bc5`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall CheckLauncherCompatibilityStatus(enum CompatibilityStatus *a1)
{
  _QWORD *v2; // rcx
  unsigned int v3; // edi
  DWORD LastError; // eax
  unsigned int v5; // ebx
  DWORD v6; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // r8d
  int v10; // r9d
  const char *v11; // rcx
  char v13; // [rsp+30h] [rbp-58h]
  _FIRMWARE_TYPE v14; // [rsp+40h] [rbp-48h] BYREF
  int v15; // [rsp+44h] [rbp-44h] BYREF
  _BYTE v16[16]; // [rsp+48h] [rbp-40h] BYREF

  v15 = 0;
  v14 = FirmwareTypeUnknown;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( !(unsigned int)LauncherGetFirmwareType(&v14) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          101,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          89,
          LastError);
      goto LABEL_22;
    }
    v5 = 1;
    if ( v14 == FirmwareTypeBios )
    {
      if ( !(unsigned int)AreMultipleInternalBootableDisksFound(&v15) )
      {
        v6 = GetLastError();
        v3 = v6;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
            (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
            96,
            v6);
        goto LABEL_22;
      }
      if ( v15 )
      {
        *(_DWORD *)a1 = 1;
        McGenEventRegister_EventRegister();
        if ( (Microsoft_Windows_WindowsToGo_StartupOptionsEnableBits & 2) != 0 )
          McGenEventWrite_EventWriteTransfer(v7, &LauncherIncompatibleMultipleBootableDisksEvent, v8, 1, v16);
        McGenEventUnregister_EventUnregister();
        goto LABEL_28;
      }
    }
    else if ( v14 != FirmwareTypeUefi )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          103,
          &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)v14);
      *(_DWORD *)a1 = 2;
      goto LABEL_28;
    }
    *(_DWORD *)a1 = 0;
LABEL_28:
    v3 = 0;
    goto LABEL_29;
  }
  v3 = 87;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_sdD(
      v2[2],
      100,
      (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
      (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
      87,
      87);
LABEL_22:
  v5 = 0;
  LogLauncherSetErrorEvent(v3);
LABEL_29:
  SetLastError(v3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v13 = GetLastError();
    v11 = "Success";
    if ( !v5 )
      v11 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, v9, v10, 133, (__int64)v11, v13);
  }
  return v5;
}

```

## disassembly

```asm
0x180005a68  push    rbx
0x180005a6a  push    rbp
0x180005a6b  push    rdi
0x180005a6c  push    r14
0x180005a6e  sub     rsp, 68h
0x180005a72  mov     rax, cs:__security_cookie
0x180005a79  xor     rax, rsp
0x180005a7c  mov     [rsp+88h+var_30], rax
0x180005a81  mov     rdi, rcx
0x180005a84  mov     [rsp+88h+var_44], 0
0x180005a8c  mov     [rsp+88h+var_48], 0
0x180005a94  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a9b  lea     rbp, WPP_GLOBAL_Control
0x180005aa2  lea     r14, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180005aa9  cmp     rcx, rbp
0x180005aac  jz      short loc_180005ACC
0x180005aae  test    byte ptr [rcx+1Ch], 8
0x180005ab2  jz      short loc_180005ACC
0x180005ab4  mov     rcx, [rcx+10h]
0x180005ab8  mov     edx, 63h ; 'c'
0x180005abd  mov     r8, r14
0x180005ac0  call    WPP_SF_
0x180005ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x180005acc  test    rdi, rdi
0x180005acf  jnz     short loc_180005AFF
0x180005ad1  mov     edi, 57h ; 'W'
0x180005ad6  cmp     rcx, rbp
0x180005ad9  jz      loc_180005BD4
0x180005adf  lea     ebx, [rdi-56h]
0x180005ae2  test    [rcx+1Ch], bl
0x180005ae5  jz      loc_180005BD4
0x180005aeb  mov     dword ptr [rsp+88h+var_60], edi
0x180005aef  lea     edx, [rdi+0Dh]
0x180005af2  mov     dword ptr [rsp+88h+var_68], 557h
0x180005afa  jmp     loc_180005BC1
0x180005aff  lea     rcx, [rsp+88h+var_48]; enum _FIRMWARE_TYPE *
0x180005b04  call    ?LauncherGetFirmwareType@@YAHPEAW4_FIRMWARE_TYPE@@@Z; LauncherGetFirmwareType(_FIRMWARE_TYPE *)
0x180005b09  test    eax, eax
0x180005b0b  jnz     short loc_180005B44
0x180005b0d  call    cs:__imp_GetLastError
0x180005b13  mov     edi, eax
0x180005b15  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b1c  cmp     rcx, rbp
0x180005b1f  jz      loc_180005BD4
0x180005b25  mov     ebx, 1
0x180005b2a  test    [rcx+1Ch], bl
0x180005b2d  jz      loc_180005BD4
0x180005b33  mov     dword ptr [rsp+88h+var_60], eax
0x180005b37  lea     edx, [rbx+64h]
0x180005b3a  mov     dword ptr [rsp+88h+var_68], 559h
0x180005b42  jmp     short loc_180005BC1
0x180005b44  mov     r9d, [rsp+88h+var_48]
0x180005b49  mov     ebx, 1
0x180005b4e  mov     ecx, r9d
0x180005b51  sub     ecx, ebx
0x180005b53  jz      short loc_180005B89
0x180005b55  cmp     ecx, ebx
0x180005b57  jz      loc_180005BE6
0x180005b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b64  cmp     rcx, rbp
0x180005b67  jz      short loc_180005B7E
0x180005b69  test    byte ptr [rcx+1Ch], 2
0x180005b6d  jz      short loc_180005B7E
0x180005b6f  mov     rcx, [rcx+10h]
0x180005b73  lea     edx, [rbx+66h]
0x180005b76  mov     r8, r14
0x180005b79  call    WPP_SF_d
0x180005b7e  mov     dword ptr [rdi], 2
0x180005b84  jmp     loc_180005C1C
0x180005b89  lea     rcx, [rsp+88h+var_44]; int *
0x180005b8e  call    ?AreMultipleInternalBootableDisksFound@@YAHPEAH@Z; AreMultipleInternalBootableDisksFound(int *)
0x180005b93  test    eax, eax
0x180005b95  jnz     short loc_180005BDF
0x180005b97  call    cs:__imp_GetLastError
0x180005b9d  mov     edi, eax
0x180005b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ba6  cmp     rcx, rbp
0x180005ba9  jz      short loc_180005BD4
0x180005bab  test    [rcx+1Ch], bl
0x180005bae  jz      short loc_180005BD4
0x180005bb0  mov     dword ptr [rsp+88h+var_60], eax
0x180005bb4  mov     edx, 66h ; 'f'
0x180005bb9  mov     dword ptr [rsp+88h+var_68], 560h
0x180005bc1  mov     rcx, [rcx+10h]
0x180005bc5  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180005bcc  mov     r8, r14
0x180005bcf  call    WPP_SF_sdD
0x180005bd4  xor     ebx, ebx
0x180005bd6  mov     ecx, edi; unsigned int
0x180005bd8  call    ?LogLauncherSetErrorEvent@@YAXI@Z; LogLauncherSetErrorEvent(uint)
0x180005bdd  jmp     short loc_180005C1E
0x180005bdf  cmp     [rsp+88h+var_44], 0
0x180005be4  jnz     short loc_180005BEE
0x180005be6  mov     dword ptr [rdi], 0
0x180005bec  jmp     short loc_180005C1C
0x180005bee  mov     [rdi], ebx
0x180005bf0  call    McGenEventRegister_EventRegister
0x180005bf5  test    cs:Microsoft_Windows_WindowsToGo_StartupOptionsEnableBits, 2
0x180005bfc  jz      short loc_180005C17
0x180005bfe  lea     rax, [rsp+88h+var_40]
0x180005c03  mov     r9d, ebx
0x180005c06  lea     rdx, LauncherIncompatibleMultipleBootableDisksEvent
0x180005c0d  mov     [rsp+88h+var_68], rax
0x180005c12  call    McGenEventWrite_EventWriteTransfer
0x180005c17  call    McGenEventUnregister_EventUnregister
0x180005c1c  xor     edi, edi
0x180005c1e  mov     ecx, edi; dwErrCode
0x180005c20  call    cs:__imp_SetLastError
0x180005c26  mov     rax, cs:WPP_GLOBAL_Control
0x180005c2d  cmp     rax, rbp
0x180005c30  jz      short loc_180005C78
0x180005c32  test    byte ptr [rax+1Ch], 4
0x180005c36  jz      short loc_180005C78
0x180005c38  call    cs:__imp_GetLastError
0x180005c3e  lea     rdx, aFailure; "Failure"
0x180005c45  mov     dword ptr [rsp+88h+var_58], eax
0x180005c49  test    ebx, ebx
0x180005c4b  lea     rcx, aSuccess; "Success"
0x180005c52  cmovz   rcx, rdx
0x180005c56  mov     edx, 68h ; 'h'
0x180005c5b  mov     [rsp+88h+var_60], rcx
0x180005c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c67  mov     dword ptr [rsp+88h+var_68], 585h
0x180005c6f  mov     rcx, [rcx+10h]
0x180005c73  call    WPP_SF_sdsd
0x180005c78  mov     eax, ebx
0x180005c7a  mov     rcx, [rsp+88h+var_30]
0x180005c7f  xor     rcx, rsp; StackCookie
0x180005c82  call    __security_check_cookie
0x180005c87  add     rsp, 68h
0x180005c8b  pop     r14
0x180005c8d  pop     rdi
0x180005c8e  pop     rbp
0x180005c8f  pop     rbx
0x180005c90  retn
```
