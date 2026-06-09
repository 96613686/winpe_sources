# EnsurePushRouterCreated(void)

- ea: `0x18000f694`
- end: `0x18000f78f`
- name: `?EnsurePushRouterCreated@@YAJXZ`
- size: `251`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f9f0`
- `0x18000fac0`
- `0x1800105a0`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x18000dc6c`
- `0x18000ea20`
- `0x18000f694`
- `0x180013f64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f767`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f767`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f6dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f6dc`

## pseudocode

```c
__int64 EnsurePushRouterCreated(void)
{
  int v0; // ebx
  unsigned int v1; // edx
  struct _RTL_CRITICAL_SECTION *v2; // r8
  const unsigned __int16 *v3; // rdx
  struct PushRouter **v4; // r9
  __int64 *v5; // rdx
  int v7; // [rsp+30h] [rbp-D0h] BYREF
  int *v8; // [rsp+48h] [rbp-B8h]
  __int64 v9; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v10; // [rsp+60h] [rbp-A0h] BYREF
  char v11[526]; // [rsp+62h] [rbp-9Eh] BYREF

  v10 = 0;
  v0 = 0;
  memset_0(v11, 0, 0x206u);
  EnterCriticalSection(&g_csPushRouter);
  if ( g_pPushRouter
    || (v0 = BuildMsgQueueVolumePath(&v10, v1), v0 >= 0) && (v0 = PushRouter::CreateInstance(&v10, v3, v2, v4), v0 >= 0) )
  {
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    {
      v5 = PushRouterPushRouterCreationVerificationSucceeded;
      goto LABEL_8;
    }
  }
  else if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
  {
    v5 = PushRouterPushRouterCreationVerificationFailed;
LABEL_8:
    v7 = v0;
    v8 = &v7;
    v9 = 4;
    McGenEventWrite_EventWriteTransfer(MDM_PUSHROUTER_Context, v5, v2, 2);
  }
  LeaveCriticalSection(&g_csPushRouter);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18000f694  mov     [rsp-8+arg_0], rbx
0x18000f699  push    rbp
0x18000f69a  lea     rbp, [rsp-180h]
0x18000f6a2  sub     rsp, 280h
0x18000f6a9  mov     rax, cs:__security_cookie
0x18000f6b0  xor     rax, rsp
0x18000f6b3  mov     [rbp+180h+var_10], rax
0x18000f6ba  xor     eax, eax
0x18000f6bc  lea     rcx, [rsp+280h+var_21E]; void *
0x18000f6c1  xor     edx, edx; Val
0x18000f6c3  mov     [rsp+280h+var_220], ax
0x18000f6c8  mov     r8d, 206h; Size
0x18000f6ce  xor     ebx, ebx
0x18000f6d0  call    memset_0
0x18000f6d5  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000f6dc  call    cs:__imp_EnterCriticalSection
0x18000f6e2  cmp     cs:?g_pPushRouter@@3PEAVPushRouter@@EA, rbx; PushRouter * g_pPushRouter
0x18000f6e9  jnz     short loc_18000F71D
0x18000f6eb  lea     rcx, [rsp+280h+var_220]; unsigned __int16 *
0x18000f6f0  call    ?BuildMsgQueueVolumePath@@YAJPEAGK@Z; BuildMsgQueueVolumePath(ushort *,ulong)
0x18000f6f5  mov     ebx, eax
0x18000f6f7  test    eax, eax
0x18000f6f9  js      short loc_18000F70B
0x18000f6fb  lea     rcx, [rsp+280h+var_220]; unsigned __int16 *
0x18000f700  call    ?CreateInstance@PushRouter@@SAJPEBG0PEAU_RTL_CRITICAL_SECTION@@PEAPEAV1@@Z; PushRouter::CreateInstance(ushort const *,ushort const *,_RTL_CRITICAL_SECTION *,PushRouter * *)
0x18000f705  mov     ebx, eax
0x18000f707  test    eax, eax
0x18000f709  jns     short loc_18000F71D
0x18000f70b  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x18000f712  jz      short loc_18000F760
0x18000f714  lea     rdx, PushRouterPushRouterCreationVerificationFailed
0x18000f71b  jmp     short loc_18000F72D
0x18000f71d  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x18000f724  jz      short loc_18000F760
0x18000f726  lea     rdx, PushRouterPushRouterCreationVerificationSucceeded
0x18000f72d  lea     rax, [rsp+280h+var_250]
0x18000f732  mov     [rsp+280h+var_250], ebx
0x18000f736  mov     [rsp+280h+var_238], rax
0x18000f73b  lea     rcx, MDM_PUSHROUTER_Context
0x18000f742  lea     rax, [rsp+280h+var_248]
0x18000f747  mov     [rsp+280h+var_230], 4
0x18000f750  mov     r9d, 2
0x18000f756  mov     [rsp+280h+var_260], rax
0x18000f75b  call    McGenEventWrite_EventWriteTransfer
0x18000f760  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000f767  call    cs:__imp_LeaveCriticalSection
0x18000f76d  mov     eax, ebx
0x18000f76f  mov     rcx, [rbp+180h+var_10]
0x18000f776  xor     rcx, rsp; StackCookie
0x18000f779  call    __security_check_cookie
0x18000f77e  mov     rbx, [rsp+280h+arg_0]
0x18000f786  add     rsp, 280h
0x18000f78d  pop     rbp
0x18000f78e  retn
```
