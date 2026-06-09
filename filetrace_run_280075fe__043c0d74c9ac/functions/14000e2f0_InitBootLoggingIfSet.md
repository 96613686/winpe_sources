# InitBootLoggingIfSet

- ea: `0x14000e2f0`
- end: `0x14000e5f4`
- name: `InitBootLoggingIfSet`
- size: `772`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000e078`

## callees

- `0x140001030`
- `0x140003510`
- `0x140003550`
- `0x14000e2f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e5ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e66a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e5ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e66a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e337`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e337`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e440`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e440`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000e404`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000e532`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e5b3`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e5b3`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e3f5`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e523`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e3f5`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e523`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e3e4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e512`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e3e4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e512`

## string_xrefs

- `0x14000e3d8`: `RtlQueryRegistryValuesEx`
- `0x14000e506`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
void InitBootLoggingIfSet()
{
  wchar_t *PoolWithTag; // rax
  wchar_t *v1; // rbx
  PVOID SystemRoutineAddress; // rax
  int v3; // edi
  wchar_t *v4; // rax
  PVOID v5; // rax
  int v6; // ecx
  _DWORD *v7; // rax
  bool v8; // zf
  int v9; // ecx
  int v10; // [rsp+30h] [rbp-128h] BYREF
  int v11; // [rsp+34h] [rbp-124h] BYREF
  int v12; // [rsp+38h] [rbp-120h] BYREF
  int v13; // [rsp+3Ch] [rbp-11Ch]
  wchar_t *v14; // [rsp+40h] [rbp-118h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-110h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+58h] [rbp-100h] BYREF
  __int64 v17; // [rsp+70h] [rbp-E8h] BYREF
  int v18; // [rsp+78h] [rbp-E0h]
  const wchar_t *v19; // [rsp+80h] [rbp-D8h]
  int *v20; // [rsp+88h] [rbp-D0h]
  int v21; // [rsp+90h] [rbp-C8h]
  int *v22; // [rsp+98h] [rbp-C0h]
  int v23; // [rsp+A0h] [rbp-B8h]
  __int64 v24; // [rsp+A8h] [rbp-B0h]
  int v25; // [rsp+B0h] [rbp-A8h]

  v10 = 0;
  v11 = 0;
  v12 = 0;
  PoolWithTag = (wchar_t *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x6Cu, 0x72744C46u);
  v1 = PoolWithTag;
  v14 = PoolWithTag;
  if ( PoolWithTag && RtlStringCbPrintfW(PoolWithTag, 0x6Cu, L"%ws", L"WMI\\GlobalLogger\\") >= 0 )
  {
    v17 = 0;
    v18 = 32;
    v19 = L"Start";
    v20 = &v11;
    v21 = 4;
    v22 = &v12;
    v23 = 4;
    v24 = 0;
    v25 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
    SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
    if ( !SystemRoutineAddress )
      SystemRoutineAddress = RtlQueryRegistryValues;
    if ( ((int (__fastcall *)(__int64, wchar_t *, __int64 *, _QWORD, _QWORD))SystemRoutineAddress)(
           2147483650LL,
           v1,
           &v17,
           0,
           0) >= 0
      && v11 )
    {
      ExAcquireFastMutex(&SessionLock);
      if ( !*(_QWORD *)LogSessions )
      {
        v3 = 0;
        v13 = 0;
        while ( v3 < 4 )
        {
          v4 = ControlGuidStrings[v3];
          *(_OWORD *)(v1 + 17) = *(_OWORD *)v4;
          *(_OWORD *)(v1 + 25) = *((_OWORD *)v4 + 1);
          *(_OWORD *)(v1 + 33) = *((_OWORD *)v4 + 2);
          *(_OWORD *)(v1 + 41) = *((_OWORD *)v4 + 3);
          *(_OWORD *)(v1 + 46) = *(_OWORD *)(v4 + 29);
          v17 = 0;
          v18 = 32;
          v19 = L"Flags";
          v20 = &v10;
          v21 = 4;
          v22 = &v12;
          v23 = 4;
          v24 = 0;
          v25 = 0;
          SystemRoutineName = 0;
          RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
          v5 = MmGetSystemRoutineAddress(&SystemRoutineName);
          if ( !v5 )
            v5 = RtlQueryRegistryValues;
          if ( ((int (__fastcall *)(__int64, wchar_t *, __int64 *, _QWORD, _QWORD))v5)(2147483650LL, v1, &v17, 0, 0) >= 0 )
          {
            v6 = v10;
            if ( v10 )
            {
              v7 = LogSessions;
              if ( !*(_QWORD *)LogSessions )
              {
                v8 = SessionSerialNumber == -1;
                v9 = ++SessionSerialNumber;
                if ( v8 )
                {
                  SessionSerialNumber = 1;
                  v9 = 1;
                }
                *((_DWORD *)LogSessions + 3) = v9;
                ++v7[2];
                *(_QWORD *)v7 = 1;
                v6 = v10;
              }
              v7[v3 + 5] = v6;
            }
          }
          v13 = ++v3;
        }
      }
      ExReleaseFastMutex(&SessionLock);
    }
  }
  if ( v1 )
    ExFreePoolWithTag(v1, 0);
}

```

## disassembly

```asm
0x14000e2f0  push    rbx
0x14000e2f2  push    rsi
0x14000e2f3  push    rdi
0x14000e2f4  push    r14
0x14000e2f6  sub     rsp, 138h
0x14000e2fd  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x14000e304  xor     rax, rsp
0x14000e307  mov     [rsp+158h+var_38], rax
0x14000e30f  xor     r14d, r14d
0x14000e312  mov     [rsp+158h+var_118], r14
0x14000e317  mov     [rsp+158h+var_128], r14d
0x14000e31c  mov     [rsp+158h+var_124], r14d
0x14000e321  mov     [rsp+158h+var_120], r14d
0x14000e326  lea     edi, [r14+6Ch]
0x14000e32a  mov     r8d, 72744C46h; Tag
0x14000e330  mov     edx, edi; NumberOfBytes
0x14000e332  mov     ecx, 200h; PoolType
0x14000e337  call    cs:__imp_ExAllocatePoolWithTag
0x14000e33e  nop     dword ptr [rax+rax+00h]
0x14000e343  mov     rbx, rax
0x14000e346  mov     [rsp+158h+var_118], rax
0x14000e34b  test    rax, rax
0x14000e34e  jz      loc_14000E5C0
0x14000e354  lea     r9, aWmiGloballogge; "WMI\\GlobalLogger\\"
0x14000e35b  lea     r8, aWs; "%ws"
0x14000e362  mov     edx, edi; cbDest
0x14000e364  mov     rcx, rax; pszDest
0x14000e367  call    RtlStringCbPrintfW
0x14000e36c  test    eax, eax
0x14000e36e  js      loc_14000E5C0
0x14000e374  mov     [rsp+158h+var_E8], r14
0x14000e379  mov     [rsp+158h+var_E0], 20h ; ' '
0x14000e381  lea     rax, aStart; "Start"
0x14000e388  mov     [rsp+158h+var_D8], rax
0x14000e390  lea     rax, [rsp+158h+var_124]
0x14000e395  mov     [rsp+158h+var_D0], rax
0x14000e39d  mov     [rsp+158h+var_C8], 4
0x14000e3a8  lea     rax, [rsp+158h+var_120]
0x14000e3ad  mov     [rsp+158h+var_C0], rax
0x14000e3b5  mov     [rsp+158h+var_B8], 4
0x14000e3c0  mov     [rsp+158h+var_B0], r14
0x14000e3c8  mov     [rsp+158h+var_A8], r14d
0x14000e3d0  xorps   xmm0, xmm0
0x14000e3d3  movups  xmmword ptr [rsp+158h+DestinationString.Length], xmm0
0x14000e3d8  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14000e3df  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x14000e3e4  call    cs:__imp_RtlInitUnicodeString
0x14000e3eb  nop     dword ptr [rax+rax+00h]
0x14000e3f0  lea     rcx, [rsp+158h+DestinationString]; SystemRoutineName
0x14000e3f5  call    cs:__imp_MmGetSystemRoutineAddress
0x14000e3fc  nop     dword ptr [rax+rax+00h]
0x14000e401  test    rax, rax
0x14000e404  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000e40c  mov     [rsp+158h+var_138], r14
0x14000e411  xor     r9d, r9d
0x14000e414  lea     r8, [rsp+158h+var_E8]
0x14000e419  mov     rdx, rbx
0x14000e41c  mov     ecx, 80000002h
0x14000e421  call    _guard_dispatch_icall
0x14000e426  test    eax, eax
0x14000e428  js      loc_14000E5C0
0x14000e42e  cmp     [rsp+158h+var_124], r14d
0x14000e433  jz      loc_14000E5C0
0x14000e439  lea     rcx, SessionLock; FastMutex
0x14000e440  call    cs:__imp_ExAcquireFastMutex
0x14000e447  nop     dword ptr [rax+rax+00h]
0x14000e44c  mov     rax, cs:LogSessions
0x14000e453  cmp     [rax], r14
0x14000e456  jnz     loc_14000E5AC
0x14000e45c  mov     edi, r14d
0x14000e45f  mov     [rsp+158h+var_11C], r14d
0x14000e464  cmp     edi, 4
0x14000e467  jge     loc_14000E5AC
0x14000e46d  movsxd  rsi, edi
0x14000e470  lea     rax, ControlGuidStrings
0x14000e477  mov     rax, [rax+rsi*8]
0x14000e47b  movups  xmm0, xmmword ptr [rax]
0x14000e47e  movups  xmmword ptr [rbx+22h], xmm0
0x14000e482  movups  xmm1, xmmword ptr [rax+10h]
0x14000e486  movups  xmmword ptr [rbx+32h], xmm1
0x14000e48a  movups  xmm0, xmmword ptr [rax+20h]
0x14000e48e  movups  xmmword ptr [rbx+42h], xmm0
0x14000e492  movups  xmm1, xmmword ptr [rax+30h]
0x14000e496  movups  xmmword ptr [rbx+52h], xmm1
0x14000e49a  movups  xmm0, xmmword ptr [rax+3Ah]
0x14000e49e  movups  xmmword ptr [rbx+5Ch], xmm0
0x14000e4a2  mov     [rsp+158h+var_E8], r14
0x14000e4a7  mov     [rsp+158h+var_E0], 20h ; ' '
0x14000e4af  lea     rax, aFlags; "Flags"
0x14000e4b6  mov     [rsp+158h+var_D8], rax
0x14000e4be  lea     rax, [rsp+158h+var_128]
0x14000e4c3  mov     [rsp+158h+var_D0], rax
0x14000e4cb  mov     [rsp+158h+var_C8], 4
0x14000e4d6  lea     rax, [rsp+158h+var_120]
0x14000e4db  mov     [rsp+158h+var_C0], rax
0x14000e4e3  mov     [rsp+158h+var_B8], 4
0x14000e4ee  mov     [rsp+158h+var_B0], r14
0x14000e4f6  mov     [rsp+158h+var_A8], r14d
0x14000e4fe  xorps   xmm0, xmm0
0x14000e501  movups  xmmword ptr [rsp+158h+SystemRoutineName.Length], xmm0
0x14000e506  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14000e50d  lea     rcx, [rsp+158h+SystemRoutineName]; DestinationString
0x14000e512  call    cs:__imp_RtlInitUnicodeString
0x14000e519  nop     dword ptr [rax+rax+00h]
0x14000e51e  lea     rcx, [rsp+158h+SystemRoutineName]; SystemRoutineName
0x14000e523  call    cs:__imp_MmGetSystemRoutineAddress
0x14000e52a  nop     dword ptr [rax+rax+00h]
0x14000e52f  test    rax, rax
0x14000e532  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000e53a  mov     [rsp+158h+var_138], r14
0x14000e53f  xor     r9d, r9d
0x14000e542  lea     r8, [rsp+158h+var_E8]
0x14000e547  mov     rdx, rbx
0x14000e54a  mov     ecx, 80000002h
0x14000e54f  call    _guard_dispatch_icall
0x14000e554  test    eax, eax
0x14000e556  js      short loc_14000E5A1
0x14000e558  mov     ecx, [rsp+158h+var_128]
0x14000e55c  test    ecx, ecx
0x14000e55e  jz      short loc_14000E5A1
0x14000e560  mov     rax, cs:LogSessions
0x14000e567  cmp     [rax], r14
0x14000e56a  jnz     short loc_14000E59D
0x14000e56c  mov     ecx, cs:SessionSerialNumber
0x14000e572  add     ecx, 1
0x14000e575  mov     cs:SessionSerialNumber, ecx
0x14000e57b  jnz     short loc_14000E58C
0x14000e57d  mov     cs:SessionSerialNumber, 1
0x14000e587  mov     ecx, 1
0x14000e58c  mov     [rax+0Ch], ecx
0x14000e58f  inc     dword ptr [rax+8]
0x14000e592  mov     qword ptr [rax], 1
0x14000e599  mov     ecx, [rsp+158h+var_128]
0x14000e59d  mov     [rax+rsi*4+14h], ecx
0x14000e5a1  inc     edi
0x14000e5a3  mov     [rsp+158h+var_11C], edi
0x14000e5a7  jmp     loc_14000E464
0x14000e5ac  lea     rcx, SessionLock; FastMutex
0x14000e5b3  call    cs:__imp_ExReleaseFastMutex
0x14000e5ba  nop     dword ptr [rax+rax+00h]
0x14000e5bf  nop
0x14000e5c0  test    rbx, rbx
0x14000e5c3  jz      short loc_14000E5D6
0x14000e5c5  xor     edx, edx; Tag
0x14000e5c7  mov     rcx, rbx; P
0x14000e5ca  call    cs:__imp_ExFreePoolWithTag
0x14000e5d1  nop     dword ptr [rax+rax+00h]
0x14000e5d6  mov     rcx, [rsp+158h+var_38]
0x14000e5de  xor     rcx, rsp; StackCookie
0x14000e5e1  call    __security_check_cookie
0x14000e5e6  add     rsp, 138h
0x14000e5ed  pop     r14
0x14000e5ef  pop     rdi
0x14000e5f0  pop     rsi
0x14000e5f1  pop     rbx
0x14000e5f2  retn
0x14000e656  push    rbp
0x14000e658  sub     rsp, 30h
0x14000e65c  mov     rbp, rdx
0x14000e65f  mov     rcx, [rbp+40h]; P
0x14000e663  test    rcx, rcx
0x14000e666  jz      short loc_14000E677
0x14000e668  xor     edx, edx; Tag
0x14000e66a  call    cs:__imp_ExFreePoolWithTag
0x14000e671  nop     dword ptr [rax+rax+00h]
0x14000e676  nop
0x14000e677  add     rsp, 30h
0x14000e67b  pop     rbp
0x14000e67c  retn
```
