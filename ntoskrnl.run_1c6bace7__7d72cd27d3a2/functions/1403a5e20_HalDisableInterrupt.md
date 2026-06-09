# HalDisableInterrupt

- ea: `0x1403a5e20`
- end: `0x1403a5fd2`
- name: `HalDisableInterrupt`
- size: `434`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1403a5cf4`
- `0x1403a5fd8`

## callees

- `0x1403374a4`
- `0x140337544`
- `0x1403a3d20`
- `0x1403a4754`
- `0x1403a47e0`
- `0x1403a4a2c`
- `0x1403a5e20`
- `0x1403a8678`
- `0x14047e334`
- `0x1406eb0e0`

## string_xrefs

- `0x1403a5e79`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x1403a5f87`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x1403a5fb2`: `minkernel\hals\lib\interrupts\common\connect.c`

## pseudocode

```c
__int64 __fastcall HalDisableInterrupt(_DWORD *a1)
{
  bool v1; // zf
  int v3; // eax
  unsigned int v4; // edi
  unsigned int v6; // edi
  _DWORD *LinesForGsiRange; // rax
  __int64 v8; // r8
  _DWORD *v9; // rsi
  __int64 v10; // rdi
  char v11; // bl
  __int64 v12; // r8
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // [rsp+40h] [rbp+8h] BYREF

  v1 = *a1 == 1;
  v17 = 0;
  if ( !v1 )
  {
    HalpInterruptLastProblem = 19;
    HalpInterruptLastProblemLine = 375;
LABEL_7:
    HalpInterruptLastProblemProcessor = -1;
    HalpInterruptLastProblemFile = (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c";
    HalpInterruptLastProblemStatus = 0;
    HalpInterruptLastProblemController = 0;
    return (unsigned int)-1073741811;
  }
  v3 = a1[2];
  if ( v3 )
  {
    if ( v3 == 3 )
      return 0;
    HalpInterruptSetProblemEx(0, 19, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 436);
    return (unsigned int)-1073741811;
  }
  v6 = a1[16];
  LinesForGsiRange = (_DWORD *)HalpInterruptFindLinesForGsiRange(v6, v6 + 1);
  v9 = LinesForGsiRange;
  if ( !LinesForGsiRange )
  {
    if ( (unsigned __int8)guard_dispatch_icall_no_overrides(0, v6, v8) )
      return (unsigned int)HalpDisableSecondaryInterrupt(a1);
    HalpInterruptLastProblem = 18;
    HalpInterruptLastProblemLine = 421;
    goto LABEL_7;
  }
  LODWORD(v17) = LinesForGsiRange[4];
  HIDWORD(v17) = v6 + LinesForGsiRange[5] - LinesForGsiRange[7];
  HalpInterruptApplyOverrides(&v17, 0, 0);
  v10 = HalpInterruptLookupController((unsigned int)v17);
  if ( !v10 )
    HalpInterruptSetProblemEx(0, 17, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 460);
  v11 = HalpAcquireHighLevelLock(&HalpInterruptLock);
  v12 = *((_QWORD *)v9 + 5) + 56LL * (HIDWORD(v17) - v9[5]);
  *(_DWORD *)(v12 + 12) &= ~0x10u;
  v13 = HalpInterruptSetLineStateInternal(v10, &v17, v12);
  LOBYTE(v14) = v11;
  v4 = v13;
  HalpReleaseHighLevelLock(&HalpInterruptLock, v14, v15, v16);
  return v4;
}

```

## disassembly

```asm
0x1403a5e20  mov     [rsp+arg_8], rbx
0x1403a5e25  mov     [rsp+arg_10], rsi
0x1403a5e2a  push    rdi
0x1403a5e2b  sub     rsp, 30h
0x1403a5e2f  cmp     dword ptr [rcx], 1
0x1403a5e32  mov     rbx, rcx
0x1403a5e35  mov     [rsp+38h+arg_0], 0
0x1403a5e3e  jnz     short loc_1403A5E65
0x1403a5e40  mov     eax, [rcx+8]
0x1403a5e43  test    eax, eax
0x1403a5e45  jz      short loc_1403A5EAD
0x1403a5e47  cmp     eax, 3
0x1403a5e4a  jnz     loc_1403A5F7C
0x1403a5e50  xor     edi, edi
0x1403a5e52  mov     rbx, [rsp+38h+arg_8]
0x1403a5e57  mov     eax, edi
0x1403a5e59  mov     rsi, [rsp+38h+arg_10]
0x1403a5e5e  add     rsp, 30h
0x1403a5e62  pop     rdi
0x1403a5e63  retn
0x1403a5e65  mov     cs:HalpInterruptLastProblem, 13h
0x1403a5e6f  mov     cs:HalpInterruptLastProblemLine, 177h
0x1403a5e79  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1403a5e80  mov     cs:HalpInterruptLastProblemProcessor, 0FFFFFFFFh
0x1403a5e8a  mov     cs:HalpInterruptLastProblemFile, rax
0x1403a5e91  mov     cs:HalpInterruptLastProblemStatus, 0
0x1403a5e9b  mov     cs:HalpInterruptLastProblemController, 0
0x1403a5ea6  mov     edi, 0C000000Dh
0x1403a5eab  jmp     short loc_1403A5E52
0x1403a5ead  mov     edi, [rcx+40h]
0x1403a5eb0  mov     ecx, edi
0x1403a5eb2  lea     edx, [rdi+1]
0x1403a5eb5  call    HalpInterruptFindLinesForGsiRange
0x1403a5eba  mov     rsi, rax
0x1403a5ebd  test    rax, rax
0x1403a5ec0  jz      short loc_1403A5F40
0x1403a5ec2  mov     eax, [rax+10h]
0x1403a5ec5  xor     r8d, r8d
0x1403a5ec8  mov     dword ptr [rsp+38h+arg_0], eax
0x1403a5ecc  xor     edx, edx
0x1403a5ece  mov     ecx, [rsi+14h]
0x1403a5ed1  sub     ecx, [rsi+1Ch]
0x1403a5ed4  add     ecx, edi
0x1403a5ed6  mov     dword ptr [rsp+38h+arg_0+4], ecx
0x1403a5eda  lea     rcx, [rsp+38h+arg_0]
0x1403a5edf  call    HalpInterruptApplyOverrides
0x1403a5ee4  mov     ecx, dword ptr [rsp+38h+arg_0]
0x1403a5ee8  call    HalpInterruptLookupController
0x1403a5eed  mov     rdi, rax
0x1403a5ef0  test    rax, rax
0x1403a5ef3  jz      loc_1403A5FA7
0x1403a5ef9  lea     rcx, HalpInterruptLock; SpinLock
0x1403a5f00  call    HalpAcquireHighLevelLock
0x1403a5f05  mov     edx, dword ptr [rsp+38h+arg_0+4]
0x1403a5f09  mov     rcx, rdi
0x1403a5f0c  sub     edx, [rsi+14h]
0x1403a5f0f  mov     bl, al
0x1403a5f11  movsxd  rdx, edx
0x1403a5f14  imul    r8, rdx, 38h ; '8'
0x1403a5f18  lea     rdx, [rsp+38h+arg_0]
0x1403a5f1d  add     r8, [rsi+28h]
0x1403a5f21  and     dword ptr [r8+0Ch], 0FFFFFFEFh
0x1403a5f26  call    HalpInterruptSetLineStateInternal
0x1403a5f2b  mov     dl, bl
0x1403a5f2d  lea     rcx, HalpInterruptLock
0x1403a5f34  mov     edi, eax
0x1403a5f36  call    HalpReleaseHighLevelLock
0x1403a5f3b  jmp     loc_1403A5E52
0x1403a5f40  mov     rax, cs:off_140E009E0
0x1403a5f47  mov     edx, edi
0x1403a5f49  xor     ecx, ecx
0x1403a5f4b  call    _guard_dispatch_icall_no_overrides
0x1403a5f50  test    al, al
0x1403a5f52  jz      short loc_1403A5F63
0x1403a5f54  mov     rcx, rbx
0x1403a5f57  call    HalpDisableSecondaryInterrupt
0x1403a5f5c  mov     edi, eax
0x1403a5f5e  jmp     loc_1403A5E52
0x1403a5f63  mov     cs:HalpInterruptLastProblem, 12h
0x1403a5f6d  mov     cs:HalpInterruptLastProblemLine, 1A5h
0x1403a5f77  jmp     loc_1403A5E79
0x1403a5f7c  xor     r8d, r8d
0x1403a5f7f  mov     [rsp+38h+var_10], 1B4h
0x1403a5f87  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1403a5f8e  or      r9d, 0FFFFFFFFh
0x1403a5f92  xor     ecx, ecx
0x1403a5f94  mov     [rsp+38h+var_18], rax
0x1403a5f99  lea     edx, [r8+13h]
0x1403a5f9d  call    HalpInterruptSetProblemEx
0x1403a5fa2  jmp     loc_1403A5EA6
0x1403a5fa7  xor     r8d, r8d
0x1403a5faa  mov     [rsp+38h+var_10], 1CCh
0x1403a5fb2  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1403a5fb9  or      r9d, 0FFFFFFFFh
0x1403a5fbd  xor     ecx, ecx
0x1403a5fbf  mov     [rsp+38h+var_18], rax
0x1403a5fc4  lea     edx, [r8+11h]
0x1403a5fc8  call    HalpInterruptSetProblemEx
0x1403a5fcd  jmp     loc_1403A5EF9
```
