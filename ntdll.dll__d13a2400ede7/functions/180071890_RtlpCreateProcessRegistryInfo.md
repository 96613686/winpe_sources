# RtlpCreateProcessRegistryInfo

- ea: `0x180071890`
- end: `0x180071959`
- name: `RtlpCreateProcessRegistryInfo`
- size: `201`
- prototype: ``
- caller_count: `15`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007de0`
- `0x18000be70`
- `0x18000c9a0`
- `0x18000ca60`
- `0x18000d0c0`
- `0x18000d3e0`
- `0x18000fd10`
- `0x18007a2c0`
- `0x1800c4750`
- `0x180103c60`
- `0x180125530`
- `0x180142c30`
- `0x180143270`
- `0x180143e00`
- `0x18014d800`

## callees

- `0x180058fb0`
- `0x18006ffa0`
- `0x180070490`
- `0x180071890`
- `0x180071960`
- `0x18015f160`

## pseudocode

```c
__int64 __fastcall RtlpCreateProcessRegistryInfo(__int64 *a1)
{
  __int64 v1; // rdx
  int RegistryInfo; // ebx
  int v4; // eax
  __int64 v5; // rax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = g_RegInfo;
  RegistryInfo = 0;
  if ( !g_RegInfo )
  {
    v7 = -1000000;
    while ( _InterlockedCompareExchange(&InitRegistryInfoCritSect, 1, 0) )
    {
      v4 = InitRegistryInfoCritSect;
      if ( InitRegistryInfoCritSect == 1 )
      {
        ZwDelayExecution(0, &v7);
        v4 = InitRegistryInfoCritSect;
      }
      if ( v4 == 2 )
        goto LABEL_7;
    }
    RtlInitializeCriticalSectionEx(RegistryInfoCritSect, 0, 0);
    InitRegistryInfoCritSect = 2;
LABEL_7:
    RtlEnterCriticalSection(RegistryInfoCritSect);
    RegistryInfo = 0;
    if ( !g_RegInfo )
      RegistryInfo = RtlpMuiRegCreateAndLoadRegistryInfo(&g_RegInfo);
    RtlLeaveCriticalSection(RegistryInfoCritSect);
    v1 = g_RegInfo;
  }
  if ( a1 )
  {
    v5 = 0;
    if ( RegistryInfo >= 0 )
      v5 = v1;
    *a1 = v5;
  }
  return (unsigned int)RegistryInfo;
}

```

## disassembly

```asm
0x180071890  mov     [rsp+arg_8], rbx
0x180071895  push    rdi
0x180071896  sub     rsp, 20h
0x18007189a  mov     rdx, cs:g_RegInfo
0x1800718a1  xor     ebx, ebx
0x1800718a3  mov     rdi, rcx
0x1800718a6  test    rdx, rdx
0x1800718a9  jnz     short loc_18007191E
0x1800718ab  mov     [rsp+28h+arg_0], 0FFFFFFFFFFF0BDC0h
0x1800718b4  mov     ebx, 1
0x1800718b9  xor     eax, eax
0x1800718bb  lock cmpxchg cs:InitRegistryInfoCritSect, ebx
0x1800718c3  jz      short loc_18007193C
0x1800718c5  mov     eax, cs:InitRegistryInfoCritSect
0x1800718cb  cmp     eax, ebx
0x1800718cd  jnz     short loc_1800718E1
0x1800718cf  lea     rdx, [rsp+28h+arg_0]
0x1800718d4  xor     ecx, ecx
0x1800718d6  call    ZwDelayExecution
0x1800718db  mov     eax, cs:InitRegistryInfoCritSect
0x1800718e1  cmp     eax, 2
0x1800718e4  jnz     short loc_1800718B9
0x1800718e6  lea     rcx, RegistryInfoCritSect
0x1800718ed  call    RtlEnterCriticalSection
0x1800718f2  xor     ebx, ebx
0x1800718f4  cmp     cs:g_RegInfo, rbx
0x1800718fb  jnz     short loc_18007190B
0x1800718fd  lea     rcx, g_RegInfo
0x180071904  call    RtlpMuiRegCreateAndLoadRegistryInfo
0x180071909  mov     ebx, eax
0x18007190b  lea     rcx, RegistryInfoCritSect
0x180071912  call    RtlLeaveCriticalSection
0x180071917  mov     rdx, cs:g_RegInfo
0x18007191e  test    rdi, rdi
0x180071921  jz      short loc_18007192E
0x180071923  xor     eax, eax
0x180071925  test    ebx, ebx
0x180071927  cmovns  rax, rdx
0x18007192b  mov     [rdi], rax
0x18007192e  mov     eax, ebx
0x180071930  mov     rbx, [rsp+28h+arg_8]
0x180071935  add     rsp, 20h
0x180071939  pop     rdi
0x18007193a  retn
0x18007193c  xor     r8d, r8d
0x18007193f  lea     rcx, RegistryInfoCritSect
0x180071946  xor     edx, edx
0x180071948  call    RtlInitializeCriticalSectionEx
0x18007194d  mov     cs:InitRegistryInfoCritSect, 2
0x180071957  jmp     short loc_1800718E6
```
