# PsmpApplyApplicationTcUpdate

- ea: `0x180023948`
- end: `0x180023a0f`
- name: `PsmpApplyApplicationTcUpdate`
- size: `199`
- prototype: `__int64 __fastcall(__int64, char, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18002377c`
- `0x180023e00`

## callees

- `0x1800179d8`
- `0x180023948`
- `0x180023a18`

## import_xrefs

- `ntdll!NtUpdateWnfStateData` at `0x1800239c1`
- `ntdll!NtUpdateWnfStateData` at `0x1800239c1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002396b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002396b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800239fe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800239fe`

## pseudocode

```c
__int64 __fastcall PsmpApplyApplicationTcUpdate(__int64 a1, char a2, unsigned int a3)
{
  __int64 v3; // rbp
  __int64 v7; // r8
  int v8; // ebx
  int v10; // [rsp+70h] [rbp+8h] BYREF

  v3 = a1 + 328;
  v10 = 0;
  RtlAcquireSRWLockExclusive(a1 + 328);
  LOBYTE(v7) = a2;
  v8 = PsmpApplySingleTcUpdate(a1 + 40, a3, v7, &v10);
  if ( v8 >= 0 )
  {
    if ( v10 )
    {
      v10 = *(_DWORD *)(a1 + 44);
      NtUpdateWnfStateData(a1 + 80, &v10, 4);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_iD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_2676a593e7783fc6fea2dce701a66333_Traceguids,
          *(_QWORD *)(a1 + 96),
          v10);
    }
  }
  RtlReleaseSRWLockExclusive(v3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180023948  push    rbx
0x18002394a  push    rbp
0x18002394b  push    rsi
0x18002394c  push    rdi
0x18002394d  sub     rsp, 48h
0x180023951  lea     rbp, [rcx+148h]
0x180023958  mov     [rsp+68h+arg_0], 0
0x180023960  mov     rsi, rcx
0x180023963  mov     edi, r8d
0x180023966  mov     rcx, rbp
0x180023969  mov     bl, dl
0x18002396b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180023971  lea     rcx, [rsi+28h]
0x180023975  mov     r8b, bl
0x180023978  lea     r9, [rsp+68h+arg_0]
0x18002397d  mov     edx, edi
0x18002397f  call    PsmpApplySingleTcUpdate
0x180023984  mov     ebx, eax
0x180023986  test    eax, eax
0x180023988  js      short loc_1800239FB
0x18002398a  cmp     [rsp+68h+arg_0], 0
0x18002398f  jz      short loc_1800239FB
0x180023991  mov     ecx, [rsi+2Ch]
0x180023994  lea     rdx, [rsp+68h+arg_0]
0x180023999  xor     r9d, r9d
0x18002399c  mov     [rsp+68h+arg_0], ecx
0x1800239a0  mov     [rsp+68h+var_38], 0
0x1800239a8  lea     rcx, [rsi+50h]
0x1800239ac  mov     [rsp+68h+var_40], 0
0x1800239b4  mov     [rsp+68h+var_48], 0
0x1800239bd  lea     r8d, [r9+4]
0x1800239c1  call    cs:__imp_NtUpdateWnfStateData
0x1800239c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239ce  test    byte ptr [rcx+1Ch], 10h
0x1800239d2  jz      short loc_1800239FB
0x1800239d4  cmp     byte ptr [rcx+19h], 4
0x1800239d8  jb      short loc_1800239FB
0x1800239da  mov     eax, [rsp+68h+arg_0]
0x1800239de  lea     r8, WPP_2676a593e7783fc6fea2dce701a66333_Traceguids
0x1800239e5  mov     r9, [rsi+60h]
0x1800239e9  mov     edx, 0Ah
0x1800239ee  mov     rcx, [rcx+10h]
0x1800239f2  mov     dword ptr [rsp+68h+var_48], eax
0x1800239f6  call    WPP_SF_iD
0x1800239fb  mov     rcx, rbp
0x1800239fe  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180023a04  mov     eax, ebx
0x180023a06  add     rsp, 48h
0x180023a0a  pop     rdi
0x180023a0b  pop     rsi
0x180023a0c  pop     rbp
0x180023a0d  pop     rbx
0x180023a0e  retn
```
