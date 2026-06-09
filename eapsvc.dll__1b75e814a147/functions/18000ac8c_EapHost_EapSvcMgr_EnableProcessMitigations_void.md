# EapHost::EapSvcMgr::EnableProcessMitigations(void)

- ea: `0x18000ac8c`
- end: `0x18000af48`
- name: `?EnableProcessMitigations@EapSvcMgr@EapHost@@AEAAXXZ`
- size: `700`
- prototype: `void __fastcall(EapHost::EapSvcMgr *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b5c0`

## callees

- `0x180001f60`
- `0x18000ac8c`
- `0x18000bbd8`
- `0x18000be00`
- `0x18000c150`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ae0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ae0c`
- `ntdll!EtwEventEnabled` at `0x18000aeb4`
- `ntdll!EtwEventEnabled` at `0x18000aeb4`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000acc9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000acf9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ad29`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ad59`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ad89`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000adb9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ade9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ae5e`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ae8b`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000acc9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000acf9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ad29`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ad59`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ad89`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000adb9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ade9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ae5e`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ae8b`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18000ae22`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18000ae22`
- `api-ms-win-core-sysinfo-l1-2-6!IsUserCetAvailableInEnvironment` at `0x18000ae35`
- `api-ms-win-core-sysinfo-l1-2-6!IsUserCetAvailableInEnvironment` at `0x18000ae35`

## string_xrefs

- `0x18000aebe`: `Process exploit mitigations enabled for EAPHost service.`

## pseudocode

```c
void __fastcall EapHost::EapSvcMgr::EnableProcessMitigations(EapHost::EapSvcMgr *this)
{
  unsigned int v1; // r8d
  const char *v2; // r9
  unsigned int v3; // r8d
  const char *v4; // r9
  unsigned int v5; // r8d
  const char *v6; // r9
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int v9; // r8d
  const char *v10; // r9
  unsigned int v11; // r8d
  const char *v12; // r9
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE CurrentProcess; // rax
  unsigned int v16; // r8d
  const char *v17; // r9
  __int64 v18; // rdx
  bool v19; // zf
  int v20; // eax
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rax
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+34h] [rbp-CCh] BYREF
  int v26; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+3Ch] [rbp-C4h] BYREF
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29; // [rsp+44h] [rbp-BCh] BYREF
  int v30; // [rsp+48h] [rbp-B8h] BYREF
  int v31; // [rsp+4Ch] [rbp-B4h] BYREF
  _BYTE v32[16]; // [rsp+50h] [rbp-B0h] BYREF
  char *v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  char v36[2048]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+888h] [rbp+788h]

  v25 = 5;
  if ( !(unsigned int)SetProcessMitigationPolicy(4, &v25, 4) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xF3, v1, v2);
  v26 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(6, &v26, 4) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xF8, v3, v4);
  v27 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(2, &v27, 4) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xFC, v5, v6);
  v28 = 5;
  if ( !(unsigned int)SetProcessMitigationPolicy(7, &v28, 4) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x101, v7, v8);
  v29 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(8, &v29, 4) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x105, v9, v10);
  v30 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(9, &v30, 4) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x109, v11, v12);
  v31 = 7;
  if ( !(unsigned int)SetProcessMitigationPolicy(10, &v31, 4) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x10F, v13, v14);
  v24 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !(unsigned int)GetProcessMitigationPolicy(CurrentProcess, 15, &v24, 4) )
  {
    v18 = 282;
LABEL_26:
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)v18, v16, v17);
    goto LABEL_27;
  }
  v19 = (unsigned int)IsUserCetAvailableInEnvironment(0) == 0;
  v20 = v24;
  if ( v19 )
  {
    if ( (v24 & 0x20) != 0 && (v24 & 0x40) != 0 )
      goto LABEL_27;
    v24 |= 0x60u;
    if ( (unsigned int)SetProcessMitigationPolicy(15, &v24, 4) )
      goto LABEL_27;
    v18 = 313;
    goto LABEL_26;
  }
  if ( (v24 & 1) != 0 )
    v20 = v24 | 0x14;
  v24 = v20 | 0x60;
  if ( !(unsigned int)SetProcessMitigationPolicy(15, &v24, 4) )
  {
    v18 = 304;
    goto LABEL_26;
  }
LABEL_27:
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v36, 0x800u, "Process exploit mitigations enabled for EAPHost service.") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v23 = -1;
    do
      ++v23;
    while ( v36[v23] );
    v35 = 0;
    v34 = v23 + 1;
    v33 = v36;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v21,
      v22,
      (__int64)v32);
  }
}

```

## disassembly

```asm
0x18000ac8c  mov     [rsp-8+arg_0], rdi
0x18000ac91  push    rbp
0x18000ac92  lea     rbp, [rsp-780h]
0x18000ac9a  sub     rsp, 880h
0x18000aca1  mov     rax, cs:__security_cookie
0x18000aca8  xor     rax, rsp
0x18000acab  mov     [rbp+780h+var_10], rax
0x18000acb2  mov     edi, 4
0x18000acb7  mov     [rsp+880h+var_84C], 5
0x18000acbf  mov     r8d, edi
0x18000acc2  lea     rdx, [rsp+880h+var_84C]
0x18000acc7  mov     ecx, edi
0x18000acc9  call    cs:__imp_SetProcessMitigationPolicy
0x18000accf  test    eax, eax
0x18000acd1  jnz     short loc_18000ACE4
0x18000acd3  mov     rcx, [rbp+788h]; this
0x18000acda  mov     edx, 0F3h; void *
0x18000acdf  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000ace4  mov     r8, rdi
0x18000ace7  mov     [rsp+880h+var_848], 1
0x18000acef  lea     rdx, [rsp+880h+var_848]
0x18000acf4  mov     ecx, 6
0x18000acf9  call    cs:__imp_SetProcessMitigationPolicy
0x18000acff  test    eax, eax
0x18000ad01  jnz     short loc_18000AD14
0x18000ad03  mov     rcx, [rbp+788h]; this
0x18000ad0a  mov     edx, 0F8h; void *
0x18000ad0f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000ad14  mov     r8, rdi
0x18000ad17  mov     [rsp+880h+var_844], 1
0x18000ad1f  lea     rdx, [rsp+880h+var_844]
0x18000ad24  mov     ecx, 2
0x18000ad29  call    cs:__imp_SetProcessMitigationPolicy
0x18000ad2f  test    eax, eax
0x18000ad31  jnz     short loc_18000AD44
0x18000ad33  mov     rcx, [rbp+788h]; this
0x18000ad3a  mov     edx, 0FCh; void *
0x18000ad3f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000ad44  mov     r8, rdi
0x18000ad47  mov     [rsp+880h+var_840], 5
0x18000ad4f  lea     rdx, [rsp+880h+var_840]
0x18000ad54  mov     ecx, 7
0x18000ad59  call    cs:__imp_SetProcessMitigationPolicy
0x18000ad5f  test    eax, eax
0x18000ad61  jnz     short loc_18000AD74
0x18000ad63  mov     rcx, [rbp+788h]; this
0x18000ad6a  mov     edx, 101h; void *
0x18000ad6f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000ad74  mov     r8, rdi
0x18000ad77  mov     [rsp+880h+var_83C], 1
0x18000ad7f  lea     rdx, [rsp+880h+var_83C]
0x18000ad84  mov     ecx, 8
0x18000ad89  call    cs:__imp_SetProcessMitigationPolicy
0x18000ad8f  test    eax, eax
0x18000ad91  jnz     short loc_18000ADA4
0x18000ad93  mov     rcx, [rbp+788h]; this
0x18000ad9a  mov     edx, 105h; void *
0x18000ad9f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000ada4  mov     r8, rdi
0x18000ada7  mov     [rsp+880h+var_838], 1
0x18000adaf  lea     rdx, [rsp+880h+var_838]
0x18000adb4  mov     ecx, 9
0x18000adb9  call    cs:__imp_SetProcessMitigationPolicy
0x18000adbf  test    eax, eax
0x18000adc1  jnz     short loc_18000ADD4
0x18000adc3  mov     rcx, [rbp+788h]; this
0x18000adca  mov     edx, 109h; void *
0x18000adcf  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000add4  mov     r8, rdi
0x18000add7  mov     [rsp+880h+var_834], 7
0x18000addf  lea     rdx, [rsp+880h+var_834]
0x18000ade4  mov     ecx, 0Ah
0x18000ade9  call    cs:__imp_SetProcessMitigationPolicy
0x18000adef  test    eax, eax
0x18000adf1  jnz     short loc_18000AE04
0x18000adf3  mov     rcx, [rbp+788h]; this
0x18000adfa  mov     edx, 10Fh; void *
0x18000adff  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000ae04  mov     [rsp+880h+var_850], 0
0x18000ae0c  call    cs:__imp_GetCurrentProcess
0x18000ae12  mov     r9, rdi
0x18000ae15  lea     r8, [rsp+880h+var_850]
0x18000ae1a  mov     rcx, rax
0x18000ae1d  mov     edx, 0Fh
0x18000ae22  call    cs:__imp_GetProcessMitigationPolicy
0x18000ae28  test    eax, eax
0x18000ae2a  jnz     short loc_18000AE33
0x18000ae2c  mov     edx, 11Ah
0x18000ae31  jmp     short loc_18000AE9A
0x18000ae33  xor     ecx, ecx
0x18000ae35  call    cs:__imp_IsUserCetAvailableInEnvironment
0x18000ae3b  test    eax, eax
0x18000ae3d  mov     eax, [rsp+880h+var_850]
0x18000ae41  jz      short loc_18000AE6F
0x18000ae43  test    al, 1
0x18000ae45  jz      short loc_18000AE4A
0x18000ae47  or      eax, 14h
0x18000ae4a  or      eax, 60h
0x18000ae4d  lea     rdx, [rsp+880h+var_850]
0x18000ae52  mov     r8, rdi
0x18000ae55  mov     [rsp+880h+var_850], eax
0x18000ae59  mov     ecx, 0Fh
0x18000ae5e  call    cs:__imp_SetProcessMitigationPolicy
0x18000ae64  test    eax, eax
0x18000ae66  jnz     short loc_18000AEA6
0x18000ae68  mov     edx, 130h
0x18000ae6d  jmp     short loc_18000AE9A
0x18000ae6f  test    al, 20h
0x18000ae71  jz      short loc_18000AE77
0x18000ae73  test    al, 40h
0x18000ae75  jnz     short loc_18000AEA6
0x18000ae77  or      eax, 60h
0x18000ae7a  lea     rdx, [rsp+880h+var_850]
0x18000ae7f  mov     r8, rdi
0x18000ae82  mov     [rsp+880h+var_850], eax
0x18000ae86  mov     ecx, 0Fh
0x18000ae8b  call    cs:__imp_SetProcessMitigationPolicy
0x18000ae91  test    eax, eax
0x18000ae93  jnz     short loc_18000AEA6
0x18000ae95  mov     edx, 139h; void *
0x18000ae9a  mov     rcx, [rbp+788h]; this
0x18000aea1  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000aea6  mov     rcx, cs:eaphost_Context
0x18000aead  lea     rdx, DebugInfoEvent
0x18000aeb4  call    cs:__imp_EtwEventEnabled
0x18000aeba  test    al, al
0x18000aebc  jz      short loc_18000AF28
0x18000aebe  lea     r8, aProcessExploit; "Process exploit mitigations enabled for"...
0x18000aec5  mov     edx, 800h; unsigned __int64
0x18000aeca  lea     rcx, [rsp+880h+var_810]; char *
0x18000aecf  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000aed4  test    eax, eax
0x18000aed6  js      short loc_18000AF28
0x18000aed8  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18000aedf  jge     short loc_18000AF28
0x18000aee1  lea     rcx, [rsp+880h+var_810]
0x18000aee6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000aeea  inc     rax
0x18000aeed  cmp     byte ptr [rcx+rax], 0
0x18000aef1  jnz     short loc_18000AEEA
0x18000aef3  inc     eax
0x18000aef5  mov     [rsp+880h+var_814], 0
0x18000aefd  lea     rcx, [rsp+880h+var_810]
0x18000af02  mov     [rsp+880h+var_818], eax
0x18000af06  lea     rax, [rsp+880h+var_830]
0x18000af0b  mov     [rsp+880h+var_820], rcx
0x18000af10  lea     rdx, DebugInfoEvent
0x18000af17  mov     [rsp+880h+var_860], rax
0x18000af1c  lea     rcx, eaphost_Context
0x18000af23  call    McGenEventWrite_EtwEventWriteTransfer
0x18000af28  mov     rcx, [rbp+780h+var_10]
0x18000af2f  xor     rcx, rsp; StackCookie
0x18000af32  call    __security_check_cookie
0x18000af37  mov     rdi, [rsp+880h+arg_0]
0x18000af3f  add     rsp, 880h
0x18000af46  pop     rbp
0x18000af47  retn
```
