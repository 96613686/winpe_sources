# DataStoreComServer::GetSystemInfo(ushort *)

- ea: `0x180006db0`
- end: `0x180006df2`
- name: `?GetSystemInfo@DataStoreComServer@@UEAAJPEAG@Z`
- size: `66`
- prototype: `__int64 __fastcall(DataStoreComServer *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006db0`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x180006ddc`
- `KERNEL32!GetSystemInfo` at `0x180006ddc`

## pseudocode

```c
__int64 __fastcall DataStoreComServer::GetSystemInfo(DataStoreComServer *this, unsigned __int16 *a2)
{
  _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-38h] BYREF

  if ( !a2 )
    return 2147500035LL;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  *a2 = SystemInfo.wProcessorArchitecture;
  return 0;
}

```

## disassembly

```asm
0x180006db0  push    rbx
0x180006db2  sub     rsp, 50h
0x180006db6  mov     rbx, rdx
0x180006db9  test    rdx, rdx
0x180006dbc  jnz     short loc_180006DC5
0x180006dbe  mov     eax, 80004003h
0x180006dc3  jmp     short loc_180006DEC
0x180006dc5  xorps   xmm0, xmm0
0x180006dc8  lea     rcx, [rsp+58h+SystemInfo]; lpSystemInfo
0x180006dcd  movups  xmmword ptr [rsp+58h+SystemInfo], xmm0
0x180006dd2  movups  xmmword ptr [rsp+58h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180006dd7  movups  xmmword ptr [rsp+58h+SystemInfo.dwNumberOfProcessors], xmm0
0x180006ddc  call    cs:__imp_GetSystemInfo
0x180006de2  movzx   eax, word ptr [rsp+58h+SystemInfo]
0x180006de7  mov     [rbx], ax
0x180006dea  xor     eax, eax
0x180006dec  add     rsp, 50h
0x180006df0  pop     rbx
0x180006df1  retn
```
