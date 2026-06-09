# DpspUpdateRejectedConnectionCount

- ea: `0x1800128e0`
- end: `0x18001292b`
- name: `DpspUpdateRejectedConnectionCount`
- size: `75`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x180003498`
- `0x180004b18`
- `0x180005db4`
- `0x18000fbb4`

## import_xrefs

- `ntdll!NtAlpcDisconnectPort` at `0x1800128f3`
- `ntdll!NtAlpcDisconnectPort` at `0x1800128f3`
- `ntdll!NtAlpcQueryInformation` at `0x180012912`
- `ntdll!NtAlpcQueryInformation` at `0x180012912`

## pseudocode

```c
__int64 __fastcall DpspUpdateRejectedConnectionCount(__int64 a1)
{
  __int128 v3; // [rsp+30h] [rbp-18h] BYREF

  v3 = 0;
  NtAlpcDisconnectPort(a1, 0);
  NtAlpcQueryInformation(a1, 0, &v3);
  _InterlockedAdd(&g_lExpectedRejectionMessageCount, DWORD1(v3));
  return 0;
}

```

## disassembly

```asm
0x1800128e0  push    rbx
0x1800128e2  sub     rsp, 40h
0x1800128e6  xorps   xmm0, xmm0
0x1800128e9  xor     edx, edx
0x1800128eb  movups  [rsp+48h+var_18], xmm0
0x1800128f0  mov     rbx, rcx
0x1800128f3  call    cs:__imp_NtAlpcDisconnectPort
0x1800128f9  mov     r9d, 10h
0x1800128ff  mov     [rsp+48h+var_28], 0
0x180012908  lea     r8, [rsp+48h+var_18]
0x18001290d  xor     edx, edx
0x18001290f  mov     rcx, rbx
0x180012912  call    cs:__imp_NtAlpcQueryInformation
0x180012918  mov     eax, dword ptr [rsp+48h+var_18+4]
0x18001291c  lock add cs:g_lExpectedRejectionMessageCount, eax
0x180012923  xor     eax, eax
0x180012925  add     rsp, 40h
0x180012929  pop     rbx
0x18001292a  retn
```
