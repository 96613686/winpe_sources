# HvHostInitializeService(void)

- ea: `0x180004928`
- end: `0x1800049d8`
- name: `?HvHostInitializeService@@YAHXZ`
- size: `176`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180006340`

## callees

- `0x18000195c`
- `0x180002100`
- `0x180004928`
- `0x1800064d0`
- `0x1800084f4`

## pseudocode

```c
_BOOL8 HvHostInitializeService(void)
{
  HvStatsPanel *v0; // rcx
  bool v1; // dl
  HvSysConfigTimer *v2; // rcx
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF

  v4 = 0;
  HviGetHypervisorFeatures(&v4);
  g_IsCpuManager = (v4 & 0x100000000000LL) != 0;
  v4 = 0;
  HviGetHypervisorFeatures(&v4);
  g_IsVmManager = BYTE4(v4) & 1;
  if ( g_IsCpuManager )
  {
    v1 = 1;
  }
  else
  {
    if ( (BYTE4(v4) & 1) == 0 )
      return 1;
    v1 = 0;
  }
  if ( (int)HvStatsPanel::Initialize(v0, v1) >= 0 )
  {
    if ( g_IsCpuManager )
      return (int)HvSysConfigTimer::Initialize(v2) >= 0;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180004928  sub     rsp, 48h
0x18000492c  mov     rax, cs:__security_cookie
0x180004933  xor     rax, rsp
0x180004936  mov     [rsp+48h+var_18], rax
0x18000493b  xorps   xmm0, xmm0
0x18000493e  lea     rcx, [rsp+48h+var_28]
0x180004943  movups  [rsp+48h+var_28], xmm0
0x180004948  call    HviGetHypervisorFeatures
0x18000494d  mov     r11, qword ptr [rsp+48h+var_28]
0x180004952  lea     rcx, [rsp+48h+var_28]
0x180004957  xorps   xmm0, xmm0
0x18000495a  shr     r11, 2Ch
0x18000495e  and     r11b, 1
0x180004962  mov     cs:?g_IsCpuManager@@3EA, r11b; uchar g_IsCpuManager
0x180004969  movups  [rsp+48h+var_28], xmm0
0x18000496e  call    HviGetHypervisorFeatures
0x180004973  mov     r11, qword ptr [rsp+48h+var_28]
0x180004978  shr     r11, 20h
0x18000497c  and     r11b, 1
0x180004980  cmp     cs:?g_IsCpuManager@@3EA, 0; uchar g_IsCpuManager
0x180004987  mov     cs:?g_IsVmManager@@3EA, r11b; uchar g_IsVmManager
0x18000498e  jnz     short loc_180004999
0x180004990  test    r11b, r11b
0x180004993  jz      short loc_1800049BD
0x180004995  xor     edx, edx
0x180004997  jmp     short loc_18000499B
0x180004999  mov     dl, 1; bool
0x18000499b  call    ?Initialize@HvStatsPanel@@QEAAJ_N@Z; HvStatsPanel::Initialize(bool)
0x1800049a0  test    eax, eax
0x1800049a2  js      short loc_1800049C4
0x1800049a4  cmp     cs:?g_IsCpuManager@@3EA, 0; uchar g_IsCpuManager
0x1800049ab  jz      short loc_1800049BD
0x1800049ad  call    ?Initialize@HvSysConfigTimer@@QEAAJXZ; HvSysConfigTimer::Initialize(void)
0x1800049b2  xor     ecx, ecx
0x1800049b4  test    eax, eax
0x1800049b6  setns   cl
0x1800049b9  mov     eax, ecx
0x1800049bb  jmp     short loc_1800049C6
0x1800049bd  mov     eax, 1
0x1800049c2  jmp     short loc_1800049C6
0x1800049c4  xor     eax, eax
0x1800049c6  mov     rcx, [rsp+48h+var_18]
0x1800049cb  xor     rcx, rsp; StackCookie
0x1800049ce  call    __security_check_cookie
0x1800049d3  add     rsp, 48h
0x1800049d7  retn
```
