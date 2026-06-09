# DiscpDoRefreshSendTargetPortal

- ea: `0x180004ee8`
- end: `0x180005090`
- name: `DiscpDoRefreshSendTargetPortal`
- size: `424`
- prototype: `__int64 __fastcall(__int64, int *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004980`
- `0x180011df0`

## callees

- `0x180001cfe`
- `0x180002cbc`
- `0x180002f9c`
- `0x180004ee8`
- `0x180016de8`

## import_xrefs

- `ISCSIUM!DiscpGetRegistryValue` at `0x180004f7d`
- `ISCSIUM!DiscpGetRegistryValue` at `0x180004fdb`
- `ISCSIUM!DiscpGetRegistryValue` at `0x180004f7d`
- `ISCSIUM!DiscpGetRegistryValue` at `0x180004fdb`
- `ISCSIUM!DiscpFreeMemory` at `0x180004f89`
- `ISCSIUM!DiscpFreeMemory` at `0x180004fe7`
- `ISCSIUM!DiscpFreeMemory` at `0x180005070`
- `ISCSIUM!DiscpFreeMemory` at `0x180004f89`
- `ISCSIUM!DiscpFreeMemory` at `0x180004fe7`
- `ISCSIUM!DiscpFreeMemory` at `0x180005070`

## pseudocode

```c
__int64 __fastcall DiscpDoRefreshSendTargetPortal(__int64 a1, int *a2, unsigned int a3)
{
  unsigned int refreshed; // ebx
  int RegistryValue; // ebx
  int v8; // r9d
  int v9; // ebx
  __int64 v10; // rax
  int v12; // [rsp+20h] [rbp-29h]
  int v13; // [rsp+20h] [rbp-29h]
  void *v14; // [rsp+40h] [rbp-9h] BYREF
  wchar_t *v15; // [rsp+48h] [rbp-1h] BYREF
  _BYTE v16[64]; // [rsp+50h] [rbp+7h] BYREF
  size_t Size; // [rsp+C8h] [rbp+7Fh] BYREF

  memset_0(v16, 0, sizeof(v16));
  LODWORD(Size) = 0;
  v14 = 0;
  v15 = 0;
  refreshed = DiscpCreatePortalName(a1, a2, a3, 0, &v15);
  if ( !refreshed )
  {
    LOBYTE(v12) = 1;
    RegistryValue = DiscpGetRegistryValue(
                      0,
                      L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Send Targets",
                      v15,
                      3,
                      v12,
                      &v14,
                      &Size);
    DiscpFreeMemory(v15);
    if ( RegistryValue
      && ((unsigned int)DiscpCreatePortalName(a1, a2, a3, 1, &v15)
       || (LOBYTE(v13) = 1,
           v9 = DiscpGetRegistryValue(
                  0,
                  L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Send Targets",
                  v15,
                  3,
                  v13,
                  &v14,
                  &Size),
           DiscpFreeMemory(v15),
           v9)) )
    {
      v10 = 0;
      v14 = 0;
    }
    else
    {
      if ( (unsigned int)DiscpUnbuildLoginOptions((char *)v14 + 1552, 0, (unsigned int)(Size - 1552), v16) )
        memset_0(v16, 0, sizeof(v16));
      v10 = *((_QWORD *)v14 + 193);
    }
    LOBYTE(v8) = 1;
    refreshed = DiscpRefreshSendTargetsPortal((_DWORD)a2, a3, a1, v8, (__int64)v16, v10);
    if ( v14 )
    {
      memset_0(v14, 0, (unsigned int)Size);
      DiscpFreeMemory(v14);
    }
  }
  return refreshed;
}

```

## disassembly

```asm
0x180004ee8  mov     [rsp-8+arg_0], rbx
0x180004eed  mov     [rsp-8+arg_8], rsi
0x180004ef2  push    rbp
0x180004ef3  push    rdi
0x180004ef4  push    r14
0x180004ef6  lea     rbp, [rsp-47h]
0x180004efb  sub     rsp, 90h
0x180004f02  mov     rsi, rdx
0x180004f05  mov     edi, r8d
0x180004f08  xor     edx, edx; Val
0x180004f0a  mov     r14, rcx
0x180004f0d  lea     rcx, [rbp+57h+var_50]; void *
0x180004f11  lea     r8d, [rdx+40h]; Size
0x180004f15  call    memset_0
0x180004f1a  lea     rax, [rbp+57h+var_58]
0x180004f1e  mov     dword ptr [rbp+57h+Size], 0
0x180004f25  xor     r9d, r9d
0x180004f28  mov     [rsp+0A0h+var_80], rax
0x180004f2d  mov     r8d, edi
0x180004f30  mov     [rbp+57h+var_60], 0
0x180004f38  mov     rdx, rsi
0x180004f3b  mov     [rbp+57h+var_58], 0
0x180004f43  mov     rcx, r14
0x180004f46  call    DiscpCreatePortalName
0x180004f4b  mov     ebx, eax
0x180004f4d  test    eax, eax
0x180004f4f  jnz     loc_180005076
0x180004f55  mov     r8, [rbp+57h+var_58]
0x180004f59  lea     rax, [rbp+57h+Size]
0x180004f5d  mov     [rsp+0A0h+var_70], rax
0x180004f62  lea     r9d, [rbx+3]
0x180004f66  lea     rax, [rbp+57h+var_60]
0x180004f6a  xor     ecx, ecx
0x180004f6c  mov     [rsp+0A0h+var_78], rax
0x180004f71  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180004f78  mov     byte ptr [rsp+0A0h+var_80], 1
0x180004f7d  call    cs:__imp_DiscpGetRegistryValue
0x180004f83  mov     rcx, [rbp+57h+var_58]
0x180004f87  mov     ebx, eax
0x180004f89  call    cs:__imp_DiscpFreeMemory
0x180004f8f  test    ebx, ebx
0x180004f91  jz      short loc_180004FF9
0x180004f93  lea     rax, [rbp+57h+var_58]
0x180004f97  mov     r9b, 1
0x180004f9a  mov     r8d, edi
0x180004f9d  mov     [rsp+0A0h+var_80], rax
0x180004fa2  mov     rdx, rsi
0x180004fa5  mov     rcx, r14
0x180004fa8  call    DiscpCreatePortalName
0x180004fad  test    eax, eax
0x180004faf  jnz     short loc_180004FF1
0x180004fb1  mov     r8, [rbp+57h+var_58]
0x180004fb5  lea     rax, [rbp+57h+Size]
0x180004fb9  mov     [rsp+0A0h+var_70], rax
0x180004fbe  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180004fc5  lea     rax, [rbp+57h+var_60]
0x180004fc9  mov     r9d, 3
0x180004fcf  mov     [rsp+0A0h+var_78], rax
0x180004fd4  xor     ecx, ecx
0x180004fd6  mov     byte ptr [rsp+0A0h+var_80], 1
0x180004fdb  call    cs:__imp_DiscpGetRegistryValue
0x180004fe1  mov     rcx, [rbp+57h+var_58]
0x180004fe5  mov     ebx, eax
0x180004fe7  call    cs:__imp_DiscpFreeMemory
0x180004fed  test    ebx, ebx
0x180004fef  jz      short loc_180004FF9
0x180004ff1  xor     eax, eax
0x180004ff3  mov     [rbp+57h+var_60], rax
0x180004ff7  jmp     short loc_180005038
0x180004ff9  mov     r8d, dword ptr [rbp+57h+Size]
0x180004ffd  lea     r9, [rbp+57h+var_50]
0x180005001  mov     rcx, [rbp+57h+var_60]
0x180005005  add     r8d, 0FFFFF9F0h
0x18000500c  add     rcx, 610h
0x180005013  xor     edx, edx
0x180005015  call    DiscpUnbuildLoginOptions
0x18000501a  test    eax, eax
0x18000501c  jz      short loc_18000502D
0x18000501e  xor     edx, edx; Val
0x180005020  lea     rcx, [rbp+57h+var_50]; void *
0x180005024  lea     r8d, [rdx+40h]; Size
0x180005028  call    memset_0
0x18000502d  mov     rax, [rbp+57h+var_60]
0x180005031  mov     rax, [rax+608h]
0x180005038  mov     [rsp+0A0h+var_78], rax
0x18000503d  mov     r9b, 1
0x180005040  lea     rax, [rbp+57h+var_50]
0x180005044  mov     r8, r14
0x180005047  mov     edx, edi
0x180005049  mov     [rsp+0A0h+var_80], rax
0x18000504e  mov     rcx, rsi
0x180005051  call    DiscpRefreshSendTargetsPortal
0x180005056  mov     rcx, [rbp+57h+var_60]; void *
0x18000505a  mov     ebx, eax
0x18000505c  test    rcx, rcx
0x18000505f  jz      short loc_180005076
0x180005061  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180005065  xor     edx, edx; Val
0x180005067  call    memset_0
0x18000506c  mov     rcx, [rbp+57h+var_60]
0x180005070  call    cs:__imp_DiscpFreeMemory
0x180005076  lea     r11, [rsp+0A0h+var_10]
0x18000507e  mov     eax, ebx
0x180005080  mov     rbx, [r11+20h]
0x180005084  mov     rsi, [r11+28h]
0x180005088  mov     rsp, r11
0x18000508b  pop     r14
0x18000508d  pop     rdi
0x18000508e  pop     rbp
0x18000508f  retn
```
