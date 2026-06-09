# RTSecurityContextBase::InitializeUserInfo(void)

- ea: `0x18001753c`
- end: `0x1800175ba`
- name: `?InitializeUserInfo@RTSecurityContextBase@@QEAAJXZ`
- size: `126`
- prototype: `__int64 __fastcall(RTSecurityContextBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800165d0`
- `0x180017728`

## callees

- `0x180013c74`
- `0x18001753c`
- `0x180018164`

## pseudocode

```c
__int64 __fastcall RTSecurityContextBase::InitializeUserInfo(RTSecurityContextBase *this)
{
  int ThreadUserSid; // eax
  int v3; // ecx
  unsigned int v4; // edi
  int v6; // [rsp+40h] [rbp+20h] BYREF
  int v7; // [rsp+48h] [rbp+28h] BYREF
  unsigned int v8; // [rsp+50h] [rbp+30h] BYREF
  unsigned __int8 *v9; // [rsp+58h] [rbp+38h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  ThreadUserSid = RTpGetThreadUserSid(&v6, &v7, &v9, &v8);
  v3 = v7;
  v4 = ThreadUserSid;
  *((_DWORD *)this + 9) = v6;
  *((_DWORD *)this + 10) = v3;
  *((_QWORD *)this + 1) = v9;
  *((_DWORD *)this + 11) = v8;
  if ( ThreadUserSid < 0 )
    LogMsgHR(ThreadUserSid, (wchar_t *)L"rt/rtsecctx", 0xAu);
  return v4;
}

```

## disassembly

```asm
0x18001753c  push    rbp
0x18001753e  push    rbx
0x18001753f  push    rdi
0x180017540  mov     rbp, rsp
0x180017543  sub     rsp, 20h
0x180017547  mov     rbx, rcx
0x18001754a  mov     [rbp+arg_0], 0
0x180017551  lea     rcx, [rbp+arg_0]; int *
0x180017555  mov     [rbp+arg_8], 0
0x18001755c  lea     r9, [rbp+arg_10]; unsigned int *
0x180017560  mov     [rbp+arg_10], 0
0x180017567  lea     r8, [rbp+arg_18]; unsigned __int8 **
0x18001756b  mov     [rbp+arg_18], 0
0x180017573  lea     rdx, [rbp+arg_8]; int *
0x180017577  call    ?RTpGetThreadUserSid@@YAJPEAH0PEAPEAEPEAK@Z; RTpGetThreadUserSid(int *,int *,uchar * *,ulong *)
0x18001757c  mov     ecx, [rbp+arg_8]
0x18001757f  mov     edi, eax
0x180017581  mov     edx, [rbp+arg_0]
0x180017584  mov     [rbx+24h], edx
0x180017587  mov     [rbx+28h], ecx
0x18001758a  mov     rcx, [rbp+arg_18]
0x18001758e  mov     [rbx+8], rcx
0x180017592  mov     ecx, [rbp+arg_10]
0x180017595  mov     [rbx+2Ch], ecx
0x180017598  test    eax, eax
0x18001759a  jns     short loc_1800175B0
0x18001759c  mov     r8d, 0Ah; unsigned __int16
0x1800175a2  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x1800175a9  mov     ecx, eax; int
0x1800175ab  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800175b0  mov     eax, edi
0x1800175b2  add     rsp, 20h
0x1800175b6  pop     rdi
0x1800175b7  pop     rbx
0x1800175b8  pop     rbp
0x1800175b9  retn
```
