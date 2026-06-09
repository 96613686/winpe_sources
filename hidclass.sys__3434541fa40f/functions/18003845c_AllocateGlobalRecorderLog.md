# AllocateGlobalRecorderLog

- ea: `0x18003845c`
- end: `0x180038550`
- name: `AllocateGlobalRecorderLog`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800385f0`

## callees

- `0x18001cb48`
- `0x18001d630`
- `0x180027ba0`
- `0x18003845c`

## import_xrefs

- `WppRecorder!imp_WppRecorderConfigure` at `0x1800384b2`
- `WppRecorder!imp_WppRecorderConfigure` at `0x1800384b2`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x18003851b`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x18003851b`

## pseudocode

```c
__int64 AllocateGlobalRecorderLog()
{
  size_t v0; // rdx
  __int64 result; // rax
  _QWORD v2[2]; // [rsp+20h] [rbp-50h] BYREF
  __int128 v3; // [rsp+30h] [rbp-40h] BYREF
  __int128 v4; // [rsp+40h] [rbp-30h]
  char pszDest[16]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v6; // [rsp+60h] [rbp-10h]

  v6 = 0;
  v2[0] = 16;
  v2[1] = 0x200000002LL;
  v3 = 0;
  v4 = 0;
  *(_OWORD *)pszDest = 0;
  imp_WppRecorderConfigure(WPP_GLOBAL_Control, v2);
  *(_QWORD *)&v3 = 56;
  pszDest[0] = 0;
  HIDWORD(v4) = 16;
  *(_QWORD *)&v4 = 0;
  BYTE8(v4) = 0;
  *((_QWORD *)&v3 + 1) = 0xC800000200LL;
  v6 = 0x200000001LL;
  RtlStringCchCopyA(pszDest, v0, "DriverGlobal");
  result = imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v3, &g_RecorderLog);
  if ( (int)result < 0 )
  {
    result = TraceLoggingWppRecorderFailed((unsigned int)result);
    g_RecorderLog = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003845c  push    rbp
0x18003845e  mov     rbp, rsp
0x180038461  sub     rsp, 70h
0x180038465  mov     rax, cs:__security_cookie
0x18003846c  xor     rax, rsp
0x18003846f  mov     [rbp+var_8], rax
0x180038473  mov     rcx, cs:WPP_GLOBAL_Control
0x18003847a  lea     rdx, [rbp+var_50]
0x18003847e  xorps   xmm1, xmm1
0x180038481  xor     eax, eax
0x180038483  xorps   xmm0, xmm0
0x180038486  mov     [rbp+var_10], rax
0x18003848a  movups  [rbp+var_50], xmm0
0x18003848e  mov     dword ptr [rbp+var_50], 10h
0x180038495  mov     dword ptr [rbp+var_50+8], 2
0x18003849c  mov     dword ptr [rbp+var_50+0Ch], 2
0x1800384a3  mov     byte ptr [rbp+var_50+4], al
0x1800384a6  movups  [rbp+var_40], xmm1
0x1800384aa  movups  [rbp+var_30], xmm1
0x1800384ae  movups  xmmword ptr [rbp+pszDest], xmm1
0x1800384b2  call    cs:__imp_imp_WppRecorderConfigure
0x1800384b9  nop     dword ptr [rax+rax+00h]
0x1800384be  lea     r8, pszSrc; "DriverGlobal"
0x1800384c5  mov     qword ptr [rbp+var_40], 38h ; '8'
0x1800384cd  lea     rcx, [rbp+pszDest]; pszDest
0x1800384d1  mov     dword ptr [rbp+var_40+0Ch], 0C8h
0x1800384d8  mov     [rbp+pszDest], 0
0x1800384dc  mov     dword ptr [rbp+var_30+0Ch], 10h
0x1800384e3  mov     qword ptr [rbp+var_30], 0
0x1800384eb  mov     byte ptr [rbp+var_30+8], 0
0x1800384ef  mov     dword ptr [rbp+var_10+4], 2
0x1800384f6  mov     dword ptr [rbp+var_40+8], 200h
0x1800384fd  mov     dword ptr [rbp+var_10], 1
0x180038504  call    RtlStringCchCopyA
0x180038509  mov     rcx, cs:WPP_GLOBAL_Control
0x180038510  lea     r8, g_RecorderLog
0x180038517  lea     rdx, [rbp+var_40]
0x18003851b  call    cs:__imp_imp_WppRecorderLogCreate
0x180038522  nop     dword ptr [rax+rax+00h]
0x180038527  test    eax, eax
0x180038529  jns     short loc_18003853D
0x18003852b  mov     ecx, eax
0x18003852d  call    TraceLoggingWppRecorderFailed
0x180038532  mov     cs:g_RecorderLog, 0
0x18003853d  mov     rcx, [rbp+var_8]
0x180038541  xor     rcx, rsp; StackCookie
0x180038544  call    __security_check_cookie
0x180038549  add     rsp, 70h
0x18003854d  pop     rbp
0x18003854e  retn
```
