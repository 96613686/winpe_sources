# InitBootLoggingIfSet

- ea: `0x14000e2e0`
- end: `0x14000e5e2`
- name: `InitBootLoggingIfSet`
- size: `770`
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
- `0x14000e2e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e5b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e658`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e5b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e658`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e42e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e42e`
- `ntoskrnl!ExAllocatePool2` at `0x14000e325`
- `ntoskrnl!ExAllocatePool2` at `0x14000e325`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000e3f2`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000e520`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e5a1`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e5a1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e3e3`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e511`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e3e3`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e511`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e3d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e500`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e3d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e500`

## string_xrefs

- `0x14000e3c6`: `RtlQueryRegistryValuesEx`
- `0x14000e4f4`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
void InitBootLoggingIfSet()
{
  wchar_t *Pool2; // rax
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
  Pool2 = (wchar_t *)ExAllocatePool2(64, 108, 1920224326);
  v1 = Pool2;
  v14 = Pool2;
  if ( Pool2 && RtlStringCbPrintfW(Pool2, 0x6Cu, L"%ws", L"WMI\\GlobalLogger\\") >= 0 )
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
0x14000e2e0  push    rbx
0x14000e2e2  push    rsi
0x14000e2e3  push    rdi
0x14000e2e4  push    r14
0x14000e2e6  sub     rsp, 138h
0x14000e2ed  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x14000e2f4  xor     rax, rsp
0x14000e2f7  mov     [rsp+158h+var_38], rax
0x14000e2ff  xor     r14d, r14d
0x14000e302  mov     [rsp+158h+var_118], r14
0x14000e307  mov     [rsp+158h+var_128], r14d
0x14000e30c  mov     [rsp+158h+var_124], r14d
0x14000e311  mov     [rsp+158h+var_120], r14d
0x14000e316  lea     edi, [r14+6Ch]
0x14000e31a  mov     r8d, 72744C46h
0x14000e320  mov     edx, edi
0x14000e322  lea     ecx, [rdi-2Ch]
0x14000e325  call    cs:__imp_ExAllocatePool2
0x14000e32c  nop     dword ptr [rax+rax+00h]
0x14000e331  mov     rbx, rax
0x14000e334  mov     [rsp+158h+var_118], rax
0x14000e339  test    rax, rax
0x14000e33c  jz      loc_14000E5AE
0x14000e342  lea     r9, aWmiGloballogge; "WMI\\GlobalLogger\\"
0x14000e349  lea     r8, aWs; "%ws"
0x14000e350  mov     edx, edi; cbDest
0x14000e352  mov     rcx, rax; pszDest
0x14000e355  call    RtlStringCbPrintfW
0x14000e35a  test    eax, eax
0x14000e35c  js      loc_14000E5AE
0x14000e362  mov     [rsp+158h+var_E8], r14
0x14000e367  mov     [rsp+158h+var_E0], 20h ; ' '
0x14000e36f  lea     rax, aStart; "Start"
0x14000e376  mov     [rsp+158h+var_D8], rax
0x14000e37e  lea     rax, [rsp+158h+var_124]
0x14000e383  mov     [rsp+158h+var_D0], rax
0x14000e38b  mov     [rsp+158h+var_C8], 4
0x14000e396  lea     rax, [rsp+158h+var_120]
0x14000e39b  mov     [rsp+158h+var_C0], rax
0x14000e3a3  mov     [rsp+158h+var_B8], 4
0x14000e3ae  mov     [rsp+158h+var_B0], r14
0x14000e3b6  mov     [rsp+158h+var_A8], r14d
0x14000e3be  xorps   xmm0, xmm0
0x14000e3c1  movups  xmmword ptr [rsp+158h+DestinationString.Length], xmm0
0x14000e3c6  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14000e3cd  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x14000e3d2  call    cs:__imp_RtlInitUnicodeString
0x14000e3d9  nop     dword ptr [rax+rax+00h]
0x14000e3de  lea     rcx, [rsp+158h+DestinationString]; SystemRoutineName
0x14000e3e3  call    cs:__imp_MmGetSystemRoutineAddress
0x14000e3ea  nop     dword ptr [rax+rax+00h]
0x14000e3ef  test    rax, rax
0x14000e3f2  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000e3fa  mov     [rsp+158h+var_138], r14
0x14000e3ff  xor     r9d, r9d
0x14000e402  lea     r8, [rsp+158h+var_E8]
0x14000e407  mov     rdx, rbx
0x14000e40a  mov     ecx, 80000002h
0x14000e40f  call    _guard_dispatch_icall
0x14000e414  test    eax, eax
0x14000e416  js      loc_14000E5AE
0x14000e41c  cmp     [rsp+158h+var_124], r14d
0x14000e421  jz      loc_14000E5AE
0x14000e427  lea     rcx, SessionLock; FastMutex
0x14000e42e  call    cs:__imp_ExAcquireFastMutex
0x14000e435  nop     dword ptr [rax+rax+00h]
0x14000e43a  mov     rax, cs:LogSessions
0x14000e441  cmp     [rax], r14
0x14000e444  jnz     loc_14000E59A
0x14000e44a  mov     edi, r14d
0x14000e44d  mov     [rsp+158h+var_11C], r14d
0x14000e452  cmp     edi, 4
0x14000e455  jge     loc_14000E59A
0x14000e45b  movsxd  rsi, edi
0x14000e45e  lea     rax, ControlGuidStrings
0x14000e465  mov     rax, [rax+rsi*8]
0x14000e469  movups  xmm0, xmmword ptr [rax]
0x14000e46c  movups  xmmword ptr [rbx+22h], xmm0
0x14000e470  movups  xmm1, xmmword ptr [rax+10h]
0x14000e474  movups  xmmword ptr [rbx+32h], xmm1
0x14000e478  movups  xmm0, xmmword ptr [rax+20h]
0x14000e47c  movups  xmmword ptr [rbx+42h], xmm0
0x14000e480  movups  xmm1, xmmword ptr [rax+30h]
0x14000e484  movups  xmmword ptr [rbx+52h], xmm1
0x14000e488  movups  xmm0, xmmword ptr [rax+3Ah]
0x14000e48c  movups  xmmword ptr [rbx+5Ch], xmm0
0x14000e490  mov     [rsp+158h+var_E8], r14
0x14000e495  mov     [rsp+158h+var_E0], 20h ; ' '
0x14000e49d  lea     rax, aFlags; "Flags"
0x14000e4a4  mov     [rsp+158h+var_D8], rax
0x14000e4ac  lea     rax, [rsp+158h+var_128]
0x14000e4b1  mov     [rsp+158h+var_D0], rax
0x14000e4b9  mov     [rsp+158h+var_C8], 4
0x14000e4c4  lea     rax, [rsp+158h+var_120]
0x14000e4c9  mov     [rsp+158h+var_C0], rax
0x14000e4d1  mov     [rsp+158h+var_B8], 4
0x14000e4dc  mov     [rsp+158h+var_B0], r14
0x14000e4e4  mov     [rsp+158h+var_A8], r14d
0x14000e4ec  xorps   xmm0, xmm0
0x14000e4ef  movups  xmmword ptr [rsp+158h+SystemRoutineName.Length], xmm0
0x14000e4f4  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14000e4fb  lea     rcx, [rsp+158h+SystemRoutineName]; DestinationString
0x14000e500  call    cs:__imp_RtlInitUnicodeString
0x14000e507  nop     dword ptr [rax+rax+00h]
0x14000e50c  lea     rcx, [rsp+158h+SystemRoutineName]; SystemRoutineName
0x14000e511  call    cs:__imp_MmGetSystemRoutineAddress
0x14000e518  nop     dword ptr [rax+rax+00h]
0x14000e51d  test    rax, rax
0x14000e520  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000e528  mov     [rsp+158h+var_138], r14
0x14000e52d  xor     r9d, r9d
0x14000e530  lea     r8, [rsp+158h+var_E8]
0x14000e535  mov     rdx, rbx
0x14000e538  mov     ecx, 80000002h
0x14000e53d  call    _guard_dispatch_icall
0x14000e542  test    eax, eax
0x14000e544  js      short loc_14000E58F
0x14000e546  mov     ecx, [rsp+158h+var_128]
0x14000e54a  test    ecx, ecx
0x14000e54c  jz      short loc_14000E58F
0x14000e54e  mov     rax, cs:LogSessions
0x14000e555  cmp     [rax], r14
0x14000e558  jnz     short loc_14000E58B
0x14000e55a  mov     ecx, cs:SessionSerialNumber
0x14000e560  add     ecx, 1
0x14000e563  mov     cs:SessionSerialNumber, ecx
0x14000e569  jnz     short loc_14000E57A
0x14000e56b  mov     cs:SessionSerialNumber, 1
0x14000e575  mov     ecx, 1
0x14000e57a  mov     [rax+0Ch], ecx
0x14000e57d  inc     dword ptr [rax+8]
0x14000e580  mov     qword ptr [rax], 1
0x14000e587  mov     ecx, [rsp+158h+var_128]
0x14000e58b  mov     [rax+rsi*4+14h], ecx
0x14000e58f  inc     edi
0x14000e591  mov     [rsp+158h+var_11C], edi
0x14000e595  jmp     loc_14000E452
0x14000e59a  lea     rcx, SessionLock; FastMutex
0x14000e5a1  call    cs:__imp_ExReleaseFastMutex
0x14000e5a8  nop     dword ptr [rax+rax+00h]
0x14000e5ad  nop
0x14000e5ae  test    rbx, rbx
0x14000e5b1  jz      short loc_14000E5C4
0x14000e5b3  xor     edx, edx; Tag
0x14000e5b5  mov     rcx, rbx; P
0x14000e5b8  call    cs:__imp_ExFreePoolWithTag
0x14000e5bf  nop     dword ptr [rax+rax+00h]
0x14000e5c4  mov     rcx, [rsp+158h+var_38]
0x14000e5cc  xor     rcx, rsp; StackCookie
0x14000e5cf  call    __security_check_cookie
0x14000e5d4  add     rsp, 138h
0x14000e5db  pop     r14
0x14000e5dd  pop     rdi
0x14000e5de  pop     rsi
0x14000e5df  pop     rbx
0x14000e5e0  retn
0x14000e644  push    rbp
0x14000e646  sub     rsp, 30h
0x14000e64a  mov     rbp, rdx
0x14000e64d  mov     rcx, [rbp+40h]; P
0x14000e651  test    rcx, rcx
0x14000e654  jz      short loc_14000E665
0x14000e656  xor     edx, edx; Tag
0x14000e658  call    cs:__imp_ExFreePoolWithTag
0x14000e65f  nop     dword ptr [rax+rax+00h]
0x14000e664  nop
0x14000e665  add     rsp, 30h
0x14000e669  pop     rbp
0x14000e66a  retn
```
