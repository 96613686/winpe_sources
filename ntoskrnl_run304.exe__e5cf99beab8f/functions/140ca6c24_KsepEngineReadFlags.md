# KsepEngineReadFlags

- ea: `0x140ca6c24`
- end: `0x140ca6f6b`
- name: `KsepEngineReadFlags`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140c6e944`

## callees

- `0x1404965c0`
- `0x1404965f8`
- `0x1404df6b0`
- `0x140613770`
- `0x14077e28c`
- `0x1409791e8`
- `0x140979e20`
- `0x140ca6c24`

## string_xrefs

- `0x140ca6c95`: `minkernel\ntos\kshim\kseregistry.c`
- `0x140ca6cb0`: `\Registry\Machine\System\CurrentControlSet\Policies\Microsoft\Compatibility`
- `0x140ca6e63`: `KSE: Error reading compatibility value [%ws]: status: %08x\n`
- `0x140ca6e7b`: `KSE: Error reading compatibility value [%ws]: status: %08x\n`
- `0x140ca6edb`: `KSE: Engine initialized with registry flags: %08x\n`
- `0x140ca6eec`: `KSE: Engine initialized with registry flags: %08x\n`
- `0x140ca6de5`: `KSE: Error reading compatibility key: status: %08x\n`
- `0x140ca6df6`: `KSE: Error reading compatibility key: status: %08x\n`
- `0x140ca6d8f`: `\Registry\Machine\System\CurrentControlSet\Control\Compatibility`
- `0x140ca6f33`: `KSE: Engine flags (after registry/group policy): %08x\n`
- `0x140ca6f44`: `KSE: Engine flags (after registry/group policy): %08x\n`

## pseudocode

```c
__int64 __fastcall KsepEngineReadFlags(_DWORD *a1)
{
  __int64 v2; // rax
  int v3; // eax
  HANDLE v4; // rdi
  __int64 v5; // rax
  unsigned int v6; // edi
  __int64 v7; // rax
  int DWORD; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  HANDLE KeyHandle; // [rsp+78h] [rbp+50h] BYREF

  KeyHandle = 0;
  if ( !a1 )
  {
    v2 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u) + 1)
       & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v2) = -1073740768;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v2) = 262242;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("Engine != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x62u, 0);
  }
  *a1 = 0;
  v3 = KsepRegistryOpenKey(
         L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies\\Microsoft\\Compatibility",
         0,
         &KeyHandle);
  if ( v3 )
  {
    if ( v3 == -1073741772 )
      a1[2] |= 2u;
  }
  else
  {
    v4 = KeyHandle;
    KsepRegistryQueryDWORD(KeyHandle, L"DisableDeviceFlags");
    KsepRegistryQueryDWORD(v4, L"DisableDriverShims");
    v5 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryMessagesIndex, 1u) + 1) & 0x3F;
    *(_DWORD *)&AlpcpMessageLogLock.PriorityFloorCounts[8 * v5 + 4] = 0;
    *(_DWORD *)&AlpcpMessageLogLock.PriorityFloorCounts[8 * v5] = 262273;
    if ( ((__int64)stru_140E4CF30.StackBase & 1) != 0 )
      KsepDebugPrint(0, "KSE: Engine has group policy flags: %08x\n", 0);
    KsepLogInfo(0, "KSE: Engine has group policy flags: %08x\n", 0);
    KsepRegistryCloseKey(v4);
    KeyHandle = 0;
  }
  v6 = KsepRegistryOpenKey(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Compatibility", 0, &KeyHandle);
  if ( v6 == -1073741772 )
  {
    a1[2] |= 1u;
LABEL_12:
    v6 = 0;
    goto LABEL_25;
  }
  if ( (v6 & 0x80000000) == 0 )
  {
    DWORD = KsepRegistryQueryDWORD(KeyHandle, L"DisableFlags");
    v6 = DWORD;
    if ( DWORD == -1073741772 )
      goto LABEL_12;
    if ( DWORD >= 0 )
    {
      *a1 = 0;
      v10 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryMessagesIndex, 1u) + 1) & 0x3F;
      *(_DWORD *)&AlpcpMessageLogLock.PriorityFloorCounts[8 * v10 + 4] = 0;
      *(_DWORD *)&AlpcpMessageLogLock.PriorityFloorCounts[8 * v10] = 262341;
      if ( ((__int64)stru_140E4CF30.StackBase & 1) != 0 )
        KsepDebugPrint(0, "KSE: Engine initialized with registry flags: %08x\n", *a1);
      KsepLogInfo(0, "KSE: Engine initialized with registry flags: %08x\n", *a1);
    }
    else
    {
      v9 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u)
          + 1)
         & 0x3F;
      *(&AlpcpMessageLogLock.Timer.Period + 2 * v9) = v6;
      *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v9) = 262324;
      if ( ((__int64)stru_140E4CF30.StackBase & 2) != 0 )
        KsepDebugPrint(0, "KSE: Error reading compatibility value [%ws]: status: %08x\n", L"DisableFlags", v6);
      KsepLogError(0, "KSE: Error reading compatibility value [%ws]: status: %08x\n", L"DisableFlags", v6);
    }
  }
  else
  {
    v7 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u) + 1)
       & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v7) = v6;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v7) = 262302;
    if ( ((__int64)stru_140E4CF30.StackBase & 2) != 0 )
      KsepDebugPrint(0, "KSE: Error reading compatibility key: status: %08x\n", v6);
    KsepLogError(0, "KSE: Error reading compatibility key: status: %08x\n", v6);
  }
LABEL_25:
  *a1 = *a1;
  v11 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryMessagesIndex, 1u) + 1) & 0x3F;
  *(_DWORD *)&AlpcpMessageLogLock.PriorityFloorCounts[8 * v11 + 4] = 0;
  *(_DWORD *)&AlpcpMessageLogLock.PriorityFloorCounts[8 * v11] = 262352;
  if ( ((__int64)stru_140E4CF30.StackBase & 1) != 0 )
    KsepDebugPrint(0, "KSE: Engine flags (after registry/group policy): %08x\n", *a1);
  KsepLogInfo(0, "KSE: Engine flags (after registry/group policy): %08x\n", *a1);
  KsepRegistryCloseKey(KeyHandle);
  return v6;
}

```

## disassembly

```asm
0x140ca6c24  push    rbp
0x140ca6c26  push    rbx
0x140ca6c27  push    rsi
0x140ca6c28  push    rdi
0x140ca6c29  push    r12
0x140ca6c2b  push    r15
0x140ca6c2d  mov     rbp, rsp
0x140ca6c30  sub     rsp, 28h
0x140ca6c34  xor     esi, esi
0x140ca6c36  mov     [rbp+KeyHandle], 0
0x140ca6c3e  mov     [rbp+arg_10], 0
0x140ca6c45  mov     rbx, rcx
0x140ca6c48  lea     r12, cs:140000000h
0x140ca6c4f  lea     r15d, [rsi+1]
0x140ca6c53  lea     edx, [rsi+4]
0x140ca6c56  test    rcx, rcx
0x140ca6c59  jnz     short loc_140CA6CA8
0x140ca6c5b  mov     eax, r15d
0x140ca6c5e  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x140ca6c66  add     eax, r15d
0x140ca6c69  lea     r8d, [rcx+62h]; LineNumber
0x140ca6c6d  and     eax, 3Fh
0x140ca6c70  mov     rva AlpcpMessageLogLock.Timer.Period[r12+rax*8], 0C0000420h
0x140ca6c7c  mov     dword ptr rva AlpcpMessageLogLock.Timer.Processor[r12+rax*8], 40062h
0x140ca6c88  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x140ca6c8e  test    dl, al
0x140ca6c90  jz      short loc_140CA6CA8
0x140ca6c92  xor     r9d, r9d; MutableMessage
0x140ca6c95  lea     rdx, aMinkernelNtosK_4; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140ca6c9c  lea     rcx, aEngineNull; "Engine != NULL"
0x140ca6ca3  call    RtlAssert
0x140ca6ca8  lea     r8, [rbp+KeyHandle]
0x140ca6cac  mov     [rbx], esi
0x140ca6cae  xor     edx, edx
0x140ca6cb0  lea     rcx, aRegistryMachin_138; "\\Registry\\Machine\\System\\CurrentCon"...
0x140ca6cb7  call    KsepRegistryOpenKey
0x140ca6cbc  test    eax, eax
0x140ca6cbe  jnz     loc_140CA6D7E
0x140ca6cc4  mov     rdi, [rbp+KeyHandle]
0x140ca6cc8  lea     r8, [rbp+arg_0]
0x140ca6ccc  mov     rcx, rdi; KeyHandle
0x140ca6ccf  mov     [rbp+arg_0], esi
0x140ca6cd2  lea     rdx, aDisabledevicef; "DisableDeviceFlags"
0x140ca6cd9  mov     [rbp+arg_8], esi
0x140ca6cdc  call    KsepRegistryQueryDWORD
0x140ca6ce1  test    eax, eax
0x140ca6ce3  jnz     short loc_140CA6CF2
0x140ca6ce5  cmp     [rbp+arg_0], r15d
0x140ca6ce9  jnz     short loc_140CA6CF2
0x140ca6ceb  or      dword ptr [rbx+8], 4
0x140ca6cef  lea     esi, [rax+2]
0x140ca6cf2  lea     r8, [rbp+arg_8]
0x140ca6cf6  mov     rcx, rdi; KeyHandle
0x140ca6cf9  lea     rdx, aDisabledrivers; "DisableDriverShims"
0x140ca6d00  call    KsepRegistryQueryDWORD
0x140ca6d05  test    eax, eax
0x140ca6d07  jnz     short loc_140CA6D16
0x140ca6d09  cmp     [rbp+arg_8], r15d
0x140ca6d0d  jnz     short loc_140CA6D16
0x140ca6d0f  or      esi, r15d
0x140ca6d12  or      dword ptr [rbx+8], 8
0x140ca6d16  mov     eax, r15d
0x140ca6d19  lock xadd cs:KsepHistoryMessagesIndex, eax
0x140ca6d21  add     eax, r15d
0x140ca6d24  and     eax, 3Fh
0x140ca6d27  mov     dword ptr (rva AlpcpMessageLogLock.PriorityFloorCounts+4)[r12+rax*8], 0
0x140ca6d33  mov     dword ptr rva AlpcpMessageLogLock.PriorityFloorCounts[r12+rax*8], 40081h
0x140ca6d3f  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x140ca6d45  test    r15b, al
0x140ca6d48  jz      short loc_140CA6D5B
0x140ca6d4a  mov     r8d, esi
0x140ca6d4d  lea     rdx, aKseEngineHasGr; "KSE: Engine has group policy flags: %08"...
0x140ca6d54  xor     ecx, ecx
0x140ca6d56  call    KsepDebugPrint
0x140ca6d5b  mov     r8d, esi
0x140ca6d5e  lea     rdx, aKseEngineHasGr; "KSE: Engine has group policy flags: %08"...
0x140ca6d65  xor     ecx, ecx
0x140ca6d67  call    KsepLogInfo
0x140ca6d6c  mov     rcx, rdi
0x140ca6d6f  call    KsepRegistryCloseKey
0x140ca6d74  mov     [rbp+KeyHandle], 0
0x140ca6d7c  jmp     short loc_140CA6D89
0x140ca6d7e  cmp     eax, 0C0000034h
0x140ca6d83  jnz     short loc_140CA6D89
0x140ca6d85  or      dword ptr [rbx+8], 2
0x140ca6d89  lea     r8, [rbp+KeyHandle]
0x140ca6d8d  xor     edx, edx
0x140ca6d8f  lea     rcx, aRegistryMachin_30; "\\Registry\\Machine\\System\\CurrentCon"...
0x140ca6d96  call    KsepRegistryOpenKey
0x140ca6d9b  mov     edi, eax
0x140ca6d9d  cmp     eax, 0C0000034h
0x140ca6da2  jnz     short loc_140CA6DAF
0x140ca6da4  or      [rbx+8], r15d
0x140ca6da8  xor     edi, edi
0x140ca6daa  jmp     loc_140CA6EFA
0x140ca6daf  test    edi, edi
0x140ca6db1  jns     short loc_140CA6E09
0x140ca6db3  mov     eax, r15d
0x140ca6db6  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x140ca6dbe  add     eax, r15d
0x140ca6dc1  and     eax, 3Fh
0x140ca6dc4  mov     rva AlpcpMessageLogLock.Timer.Period[r12+rax*8], edi
0x140ca6dcc  mov     dword ptr rva AlpcpMessageLogLock.Timer.Processor[r12+rax*8], 4009Eh
0x140ca6dd8  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x140ca6dde  test    al, 2
0x140ca6de0  jz      short loc_140CA6DF3
0x140ca6de2  mov     r8d, edi
0x140ca6de5  lea     rdx, aKseErrorReadin; "KSE: Error reading compatibility key: s"...
0x140ca6dec  xor     ecx, ecx
0x140ca6dee  call    KsepDebugPrint
0x140ca6df3  mov     r8d, edi
0x140ca6df6  lea     rdx, aKseErrorReadin; "KSE: Error reading compatibility key: s"...
0x140ca6dfd  xor     ecx, ecx
0x140ca6dff  call    KsepLogError
0x140ca6e04  jmp     loc_140CA6EFA
0x140ca6e09  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140ca6e0d  lea     r8, [rbp+arg_10]
0x140ca6e11  lea     rdx, aDisableflags; "DisableFlags"
0x140ca6e18  call    KsepRegistryQueryDWORD
0x140ca6e1d  mov     edi, eax
0x140ca6e1f  cmp     eax, 0C0000034h
0x140ca6e24  jz      short loc_140CA6DA8
0x140ca6e26  test    eax, eax
0x140ca6e28  jns     short loc_140CA6E8B
0x140ca6e2a  mov     eax, r15d
0x140ca6e2d  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x140ca6e35  add     eax, r15d
0x140ca6e38  and     eax, 3Fh
0x140ca6e3b  mov     rva AlpcpMessageLogLock.Timer.Period[r12+rax*8], edi
0x140ca6e43  mov     dword ptr rva AlpcpMessageLogLock.Timer.Processor[r12+rax*8], 400B4h
0x140ca6e4f  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x140ca6e55  test    al, 2
0x140ca6e57  jz      short loc_140CA6E71
0x140ca6e59  mov     r9d, edi
0x140ca6e5c  lea     r8, aDisableflags; "DisableFlags"
0x140ca6e63  lea     rdx, aKseErrorReadin_0; "KSE: Error reading compatibility value "...
0x140ca6e6a  xor     ecx, ecx
0x140ca6e6c  call    KsepDebugPrint
0x140ca6e71  mov     r9d, edi
0x140ca6e74  lea     r8, aDisableflags; "DisableFlags"
0x140ca6e7b  lea     rdx, aKseErrorReadin_0; "KSE: Error reading compatibility value "...
0x140ca6e82  xor     ecx, ecx
0x140ca6e84  call    KsepLogError
0x140ca6e89  jmp     short loc_140CA6EFA
0x140ca6e8b  mov     eax, [rbp+arg_10]
0x140ca6e8e  and     eax, 3
0x140ca6e91  mov     [rbx], eax
0x140ca6e93  test    r15b, al
0x140ca6e96  jz      short loc_140CA6E9C
0x140ca6e98  or      dword ptr [rbx+8], 20h
0x140ca6e9c  test    al, 2
0x140ca6e9e  jz      short loc_140CA6EA4
0x140ca6ea0  or      dword ptr [rbx+8], 10h
0x140ca6ea4  mov     eax, r15d
0x140ca6ea7  lock xadd cs:KsepHistoryMessagesIndex, eax
0x140ca6eaf  add     eax, r15d
0x140ca6eb2  and     eax, 3Fh
0x140ca6eb5  mov     dword ptr (rva AlpcpMessageLogLock.PriorityFloorCounts+4)[r12+rax*8], 0
0x140ca6ec1  mov     dword ptr rva AlpcpMessageLogLock.PriorityFloorCounts[r12+rax*8], 400C5h
0x140ca6ecd  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x140ca6ed3  test    r15b, al
0x140ca6ed6  jz      short loc_140CA6EE9
0x140ca6ed8  mov     r8d, [rbx]
0x140ca6edb  lea     rdx, aKseEngineIniti; "KSE: Engine initialized with registry f"...
0x140ca6ee2  xor     ecx, ecx
0x140ca6ee4  call    KsepDebugPrint
0x140ca6ee9  mov     r8d, [rbx]
0x140ca6eec  lea     rdx, aKseEngineIniti; "KSE: Engine initialized with registry f"...
0x140ca6ef3  xor     ecx, ecx
0x140ca6ef5  call    KsepLogInfo
0x140ca6efa  or      [rbx], esi
0x140ca6efc  mov     eax, r15d
0x140ca6eff  lock xadd cs:KsepHistoryMessagesIndex, eax
0x140ca6f07  add     eax, r15d
0x140ca6f0a  and     eax, 3Fh
0x140ca6f0d  mov     dword ptr (rva AlpcpMessageLogLock.PriorityFloorCounts+4)[r12+rax*8], 0
0x140ca6f19  mov     dword ptr rva AlpcpMessageLogLock.PriorityFloorCounts[r12+rax*8], 400D0h
0x140ca6f25  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x140ca6f2b  test    r15b, al
0x140ca6f2e  jz      short loc_140CA6F41
0x140ca6f30  mov     r8d, [rbx]
0x140ca6f33  lea     rdx, aKseEngineFlags; "KSE: Engine flags (after registry/group"...
0x140ca6f3a  xor     ecx, ecx
0x140ca6f3c  call    KsepDebugPrint
0x140ca6f41  mov     r8d, [rbx]
0x140ca6f44  lea     rdx, aKseEngineFlags; "KSE: Engine flags (after registry/group"...
0x140ca6f4b  xor     ecx, ecx
0x140ca6f4d  call    KsepLogInfo
0x140ca6f52  mov     rcx, [rbp+KeyHandle]
0x140ca6f56  call    KsepRegistryCloseKey
0x140ca6f5b  mov     eax, edi
0x140ca6f5d  add     rsp, 28h
0x140ca6f61  pop     r15
0x140ca6f63  pop     r12
0x140ca6f65  pop     rdi
0x140ca6f66  pop     rsi
0x140ca6f67  pop     rbx
0x140ca6f68  pop     rbp
0x140ca6f69  retn
```
