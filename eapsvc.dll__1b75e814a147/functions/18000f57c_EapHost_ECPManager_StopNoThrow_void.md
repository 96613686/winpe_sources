# EapHost::ECPManager::StopNoThrow(void)

- ea: `0x18000f57c`
- end: `0x18000f775`
- name: `?StopNoThrow@ECPManager@EapHost@@QEAA_NXZ`
- size: `505`
- prototype: `char __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b690`

## callees

- `0x180001f60`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c39c`
- `0x18000d338`
- `0x18000f57c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f664`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f664`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f679`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f679`
- `ntdll!EtwEventEnabled` at `0x18000f5b2`
- `ntdll!EtwEventEnabled` at `0x18000f696`
- `ntdll!EtwEventEnabled` at `0x18000f5b2`
- `ntdll!EtwEventEnabled` at `0x18000f696`

## string_xrefs

- `0x18000f5bc`: `Trying to stop the ECP thread`
- `0x18000f6a0`: `ECP thread stopped successfully`

## pseudocode

```c
char __fastcall EapHost::ECPManager::StopNoThrow(HANDLE *this)
{
  int v2; // r8d
  int v3; // r9d
  __int64 v4; // rbx
  __int64 v5; // rax
  int v6; // r8d
  int v7; // r9d
  char; // al
  __int64 *v9; // rbp
  int v10; // r8d
  int v11; // r9d
  _QWORD *v12; // rcx
  __int64 v13; // rax
  _QWORD *v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-868h] BYREF
  _BYTE v17[16]; // [rsp+30h] [rbp-838h] BYREF
  char *v18; // [rsp+40h] [rbp-828h]
  int v19; // [rsp+48h] [rbp-820h]
  int v20; // [rsp+4Ch] [rbp-81Ch]
  char v21[2048]; // [rsp+50h] [rbp-818h] BYREF

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v21, 0x800u, "Trying to stop the ECP thread") >= 0 )
  {
    v4 = -1;
    if ( Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v5 = -1;
      do
        ++v5;
      while ( v21[v5] );
      v18 = v21;
      v19 = v5 + 1;
      v20 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (_QWORD *)(unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v2,
        v3,
        (__int64)v17);
    }
  }
  else
  {
    v4 = -1;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13u, (__int64)WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  *(_BYTE *)this = 1;
  if ( !SetEvent(this[2]) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      SystemError::Throw(L"SetEvent");
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &Exception `RTTI Type Descriptor', 0) )
      {
        v15 = &v16;
        v9 = v15;
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
          && (int)StringCchPrintfA((char *)v9 + 80, 0x800u, "Caught Foundation exception while stopping ECP thread") >= 0
          && (byte_180020AC1 & 8) != 0 )
        {
          v12 = v9 + 10;
          v13 = -1;
          do
            ++v13;
          while ( *((_BYTE *)v12 + v13) );
          v9[8] = (__int64)(v9 + 10);
          *((_DWORD *)v9 + 18) = v13 + 1;
          *((_DWORD *)v9 + 19) = 0;
          McGenEventWrite_EtwEventWriteTransfer(
            (_QWORD *)(unsigned int)&eaphost_Context,
            (unsigned int)DebugErrorEvent,
            v10,
            v11,
            (__int64)(v9 + 6));
        }
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
          WPP_SF_(v14[2], 15u, (__int64)WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
         = 0;
        __eh34_try_continuation(0, &Exception `RTTI Type Descriptor', &loc_18000F733);
LABEL_39:
        ;
      }
    }
  }
  if ( WaitForSingleObject(this[5], 0xFFFFFFFF) == -1 )
    SystemError::Throw(L"WaitForSingleObject");
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v21, 0x800u, "ECP thread stopped successfully") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    do
      ++v4;
    while ( v21[v4] );
    v18 = v21;
    v19 = v4 + 1;
    v20 = 0;
    McGenEventWrite_EtwEventWriteTransfer(
      (_QWORD *)(unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v6,
      v7,
      (__int64)v17);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14u, (__int64)WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
   = 1;
  goto LABEL_39;
}

```

## disassembly

```asm
0x18000f57c  mov     [rsp+arg_8], rbx
0x18000f581  mov     [rsp+arg_10], rdi
0x18000f586  push    r15
0x18000f588  sub     rsp, 860h
0x18000f58f  mov     rax, cs:__security_cookie
0x18000f596  xor     rax, rsp
0x18000f599  mov     [rsp+868h+var_18], rax
0x18000f5a1  mov     rdi, rcx
0x18000f5a4  lea     rdx, DebugInfoEvent
0x18000f5ab  mov     rcx, cs:eaphost_Context
0x18000f5b2  call    cs:__imp_EtwEventEnabled
0x18000f5b8  test    al, al
0x18000f5ba  jz      short loc_18000F62B
0x18000f5bc  lea     r8, aTryingToStopTh; "Trying to stop the ECP thread"
0x18000f5c3  mov     edx, 800h; unsigned __int64
0x18000f5c8  lea     rcx, [rsp+868h+var_818]; char *
0x18000f5cd  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000f5d2  test    eax, eax
0x18000f5d4  js      short loc_18000F62B
0x18000f5d6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f5da  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x18000f5e1  jz      short loc_18000F62F
0x18000f5e3  lea     rcx, [rsp+868h+var_818]
0x18000f5e8  mov     rax, rbx
0x18000f5eb  inc     rax
0x18000f5ee  cmp     byte ptr [rcx+rax], 0
0x18000f5f2  jnz     short loc_18000F5EB
0x18000f5f4  inc     eax
0x18000f5f6  lea     rcx, [rsp+868h+var_818]
0x18000f5fb  mov     [rsp+868h+var_828], rcx
0x18000f600  mov     [rsp+868h+var_820], eax
0x18000f604  mov     [rsp+868h+var_81C], 0
0x18000f60c  lea     rax, [rsp+868h+var_838]
0x18000f611  mov     [rsp+868h+var_848], rax
0x18000f616  lea     rdx, DebugInfoEvent
0x18000f61d  lea     rcx, eaphost_Context
0x18000f624  call    McGenEventWrite_EtwEventWriteTransfer
0x18000f629  jmp     short loc_18000F62F
0x18000f62b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f62f  lea     r15, WPP_GLOBAL_Control
0x18000f636  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f63d  cmp     rcx, r15
0x18000f640  jz      short loc_18000F65D
0x18000f642  test    byte ptr [rcx+1Ch], 4
0x18000f646  jz      short loc_18000F65D
0x18000f648  mov     edx, 0Dh
0x18000f64d  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x18000f654  mov     rcx, [rcx+10h]
0x18000f658  call    WPP_SF_
0x18000f65d  mov     byte ptr [rdi], 1
0x18000f660  mov     rcx, [rdi+10h]; hEvent
0x18000f664  call    cs:__imp_SetEvent
0x18000f66a  test    eax, eax
0x18000f66c  jz      loc_18000F75B
0x18000f672  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f675  mov     rcx, [rdi+28h]; hHandle
0x18000f679  call    cs:__imp_WaitForSingleObject
0x18000f67f  cmp     eax, 0FFFFFFFFh
0x18000f682  jz      loc_18000F767
0x18000f688  lea     rdx, DebugInfoEvent
0x18000f68f  mov     rcx, cs:eaphost_Context
0x18000f696  call    cs:__imp_EtwEventEnabled
0x18000f69c  test    al, al
0x18000f69e  jz      short loc_18000F707
0x18000f6a0  lea     r8, aEcpThreadStopp; "ECP thread stopped successfully"
0x18000f6a7  mov     edx, 800h; unsigned __int64
0x18000f6ac  lea     rcx, [rsp+868h+var_818]; char *
0x18000f6b1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000f6b6  test    eax, eax
0x18000f6b8  js      short loc_18000F707
0x18000f6ba  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x18000f6c1  jz      short loc_18000F707
0x18000f6c3  lea     rax, [rsp+868h+var_818]
0x18000f6c8  inc     rbx
0x18000f6cb  cmp     byte ptr [rax+rbx], 0
0x18000f6cf  jnz     short loc_18000F6C8
0x18000f6d1  lea     eax, [rbx+1]
0x18000f6d4  lea     rcx, [rsp+868h+var_818]
0x18000f6d9  mov     [rsp+868h+var_828], rcx
0x18000f6de  mov     [rsp+868h+var_820], eax
0x18000f6e2  mov     [rsp+868h+var_81C], 0
0x18000f6ea  lea     rax, [rsp+868h+var_838]
0x18000f6ef  mov     [rsp+868h+var_848], rax
0x18000f6f4  lea     rdx, DebugInfoEvent
0x18000f6fb  lea     rcx, eaphost_Context
0x18000f702  call    McGenEventWrite_EtwEventWriteTransfer
0x18000f707  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f70e  cmp     rcx, r15
0x18000f711  jz      short loc_18000F72F
0x18000f713  test    byte ptr [rcx+1Ch], 4
0x18000f717  jz      short loc_18000F72F
0x18000f719  mov     edx, 0Eh
0x18000f71e  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x18000f725  mov     rcx, [rcx+10h]
0x18000f729  call    WPP_SF_
0x18000f72e  nop
0x18000f72f  mov     al, 1
0x18000f731  jmp     short loc_18000F735
0x18000f733  xor     al, al
0x18000f735  mov     rcx, [rsp+868h+var_18]
0x18000f73d  xor     rcx, rsp; StackCookie
0x18000f740  call    __security_check_cookie
0x18000f745  lea     r11, [rsp+868h+var_8]
0x18000f74d  mov     rbx, [r11+18h]
0x18000f751  mov     rdi, [r11+20h]
0x18000f755  mov     rsp, r11
0x18000f758  pop     r15
0x18000f75a  retn
0x18000f75b  lea     rcx, aSetevent; "SetEvent"
0x18000f762  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x18000f767  lea     rcx, aWaitforsingleo; "WaitForSingleObject"
0x18000f76e  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
```
