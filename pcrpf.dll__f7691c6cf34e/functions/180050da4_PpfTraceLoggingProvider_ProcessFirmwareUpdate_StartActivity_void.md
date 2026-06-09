# PpfTraceLoggingProvider::ProcessFirmwareUpdate::StartActivity(void)

- ea: `0x180050da4`
- end: `0x180050f06`
- name: `?StartActivity@ProcessFirmwareUpdate@PpfTraceLoggingProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(PpfTraceLoggingProvider::ProcessFirmwareUpdate *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18004fe98`

## callees

- `0x180001640`
- `0x180003270`
- `0x1800070e0`
- `0x18000de98`
- `0x18000e680`
- `0x180050da4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050e08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050ecc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050e08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050ecc`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::ProcessFirmwareUpdate::StartActivity(
        PpfTraceLoggingProvider::ProcessFirmwareUpdate *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // rbx
  _QWORD *Local; // rax
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v11; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v13; // [rsp+60h] [rbp-38h]
  __int64 v14; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v16; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = PpfTraceLoggingProvider::Provider();
  v4 = v2;
  if ( *(_DWORD *)v2 > 5u )
  {
    v5 = *((_QWORD *)v2 + 3);
    if ( (*((_QWORD *)v4 + 2) & 0x400000000000LL) != 0 )
    {
      v3 = v5 & 0x400000000000LL;
      if ( (v5 & 0x400000000000LL) == v5 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v11 = 0x1000000;
        v6 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v6 + 4)
          || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
          && !*(_DWORD *)(v6 + 28)
          && !*(_DWORD *)(v6 + 32)
          && !*(_DWORD *)(v6 + 36) )
        {
          v7 = 0;
        }
        p_CurrentThreadId = &CurrentThreadId;
        v16 = 4;
        v13 = &v11;
        v14 = 8;
        tlgWriteTransfer_EventWriteTransfer(v4, &unk_180069838, v6 + 8, v7, 4, v12);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v8 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v3,
                          1);
      *(_QWORD *)v8 = Local;
      if ( Local )
      {
        *((_QWORD *)v8 + 2) = *Local;
        *Local = v8;
        *((_DWORD *)v8 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v8 = 0;
    }
  }
}

```

## disassembly

```asm
0x180050da4  mov     [rsp+arg_8], rbx
0x180050da9  push    rdi
0x180050daa  sub     rsp, 90h
0x180050db1  mov     rax, cs:__security_cookie
0x180050db8  xor     rax, rsp
0x180050dbb  mov     [rsp+98h+var_18], rax
0x180050dc3  mov     rbx, rcx
0x180050dc6  call    ?zInternalStart@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180050dcb  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180050dd0  mov     rdi, rax
0x180050dd3  mov     edx, [rax]
0x180050dd5  cmp     edx, 5
0x180050dd8  jbe     loc_180050E99
0x180050dde  mov     rax, [rax+18h]
0x180050de2  mov     rdx, [rdi+10h]
0x180050de6  mov     r8, 400000000000h
0x180050df0  test    r8, rdx
0x180050df3  jz      loc_180050E99
0x180050df9  mov     rcx, rax
0x180050dfc  and     rcx, r8
0x180050dff  cmp     rcx, rax
0x180050e02  jnz     loc_180050E99
0x180050e08  call    cs:__imp_GetCurrentThreadId
0x180050e0f  nop     dword ptr [rax+rax+00h]
0x180050e14  mov     [rsp+98h+var_68], eax
0x180050e18  mov     [rsp+98h+var_60], 1000000h
0x180050e21  mov     r8, [rbx+110h]
0x180050e28  cmp     byte ptr [r8+4], 0
0x180050e2d  jz      short loc_180050E4E
0x180050e2f  lea     r9, [r8+18h]
0x180050e33  cmp     dword ptr [r9], 0
0x180050e37  jnz     short loc_180050E51
0x180050e39  cmp     dword ptr [r9+4], 0
0x180050e3e  jnz     short loc_180050E51
0x180050e40  cmp     dword ptr [r9+8], 0
0x180050e45  jnz     short loc_180050E51
0x180050e47  cmp     dword ptr [r9+0Ch], 0
0x180050e4c  jnz     short loc_180050E51
0x180050e4e  xor     r9d, r9d
0x180050e51  lea     rax, [rsp+98h+var_68]
0x180050e56  mov     [rsp+98h+var_28], rax
0x180050e5b  mov     ecx, 4
0x180050e60  mov     [rsp+98h+var_20], rcx
0x180050e65  lea     rax, [rsp+98h+var_60]
0x180050e6a  mov     [rsp+98h+var_38], rax
0x180050e6f  mov     [rsp+98h+var_30], 8
0x180050e78  add     r8, 8
0x180050e7c  lea     rax, [rsp+98h+var_58]
0x180050e81  mov     [rsp+98h+var_70], rax
0x180050e86  mov     [rsp+98h+var_78], ecx
0x180050e8a  lea     rdx, unk_180069838
0x180050e91  mov     rcx, rdi
0x180050e94  call    _tlgWriteTransfer_EventWriteTransfer
0x180050e99  cmp     dword ptr [rbx+138h], 0
0x180050ea0  jnz     short loc_180050EE4
0x180050ea2  add     rbx, 120h
0x180050ea9  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180050eb1  jz      short loc_180050EDD
0x180050eb3  mov     dl, 1
0x180050eb5  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180050eba  mov     [rbx], rax
0x180050ebd  test    rax, rax
0x180050ec0  jz      short loc_180050EE4
0x180050ec2  mov     rcx, [rax]
0x180050ec5  mov     [rbx+10h], rcx
0x180050ec9  mov     [rax], rbx
0x180050ecc  call    cs:__imp_GetCurrentThreadId
0x180050ed3  nop     dword ptr [rax+rax+00h]
0x180050ed8  mov     [rbx+18h], eax
0x180050edb  jmp     short loc_180050EE4
0x180050edd  mov     qword ptr [rbx], 0
0x180050ee4  mov     rcx, [rsp+98h+var_18]
0x180050eec  xor     rcx, rsp; StackCookie
0x180050eef  call    __security_check_cookie
0x180050ef4  mov     rbx, [rsp+98h+arg_8]
0x180050efc  add     rsp, 90h
0x180050f03  pop     rdi
0x180050f04  retn
```
