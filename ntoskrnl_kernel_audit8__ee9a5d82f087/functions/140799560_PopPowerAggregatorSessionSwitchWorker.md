# PopPowerAggregatorSessionSwitchWorker

- ea: `0x140799560`
- end: `0x140799621`
- name: `PopPowerAggregatorSessionSwitchWorker`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1403111a0`
- `0x140311208`
- `0x140352370`
- `0x140799560`
- `0x140a1936c`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x1407995c1`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x1407995dc`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x1407995c1`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x1407995dc`

## pseudocode

```c
__int64 __fastcall PopPowerAggregatorSessionSwitchWorker(__int64 a1, __int64 a2, __int64 a3)
{
  char v3; // bl
  char v4; // di
  __int64 result; // rax
  __int64 v6; // rdx
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF

  PopAcquireRwLockExclusive(&PopPowerAggregatorLock, a2, a3);
  if ( byte_140EF74B9 )
  {
    v3 = 0;
    *(_WORD *)&byte_140EF74B8 = 0;
    v4 = 1;
    PopPowerAggregatorScheduleWorker(&PopPowerAggregatorContext);
  }
  else
  {
    v4 = 0;
    byte_140EF74B9 = 1;
    v3 = 1;
  }
  result = PopReleaseRwLock((ULONG_PTR)&PopPowerAggregatorLock);
  if ( v4 )
    return PdcTaskClientRequest(PopSleepStudyTaskClientActivator, 0);
  if ( v3 )
  {
    LOBYTE(v6) = 1;
    PdcTaskClientRequest(PopSleepStudyTaskClientActivator, v6);
    v7[0] = 0;
    v7[1] = -1;
    return KeSetTimer2(byte_140EF74E0, -50000000, 0, v7);
  }
  return result;
}

```

## disassembly

```asm
0x140799560  mov     [rsp+arg_0], rbx
0x140799565  push    rdi
0x140799566  sub     rsp, 30h
0x14079956a  lea     rcx, PopPowerAggregatorLock
0x140799571  call    PopAcquireRwLockExclusive
0x140799576  cmp     cs:byte_140EF74B9, 0
0x14079957d  jz      short loc_14079959B
0x14079957f  xor     bl, bl
0x140799581  mov     word ptr cs:byte_140EF74B8, 0
0x14079958a  lea     rcx, PopPowerAggregatorContext
0x140799591  mov     dil, 1
0x140799594  call    PopPowerAggregatorScheduleWorker
0x140799599  jmp     short loc_1407995A7
0x14079959b  xor     dil, dil
0x14079959e  mov     cs:byte_140EF74B9, 1
0x1407995a5  mov     bl, 1
0x1407995a7  lea     rcx, PopPowerAggregatorLock; BugCheckParameter2
0x1407995ae  call    PopReleaseRwLock
0x1407995b3  test    dil, dil
0x1407995b6  jz      short loc_1407995CF
0x1407995b8  mov     rcx, cs:PopSleepStudyTaskClientActivator
0x1407995bf  xor     edx, edx
0x1407995c1  call    cs:__imp_PdcTaskClientRequest
0x1407995c8  nop     dword ptr [rax+rax+00h]
0x1407995cd  jmp     short loc_140799615
0x1407995cf  test    bl, bl
0x1407995d1  jz      short loc_140799615
0x1407995d3  mov     rcx, cs:PopSleepStudyTaskClientActivator
0x1407995da  mov     dl, 1
0x1407995dc  call    cs:__imp_PdcTaskClientRequest
0x1407995e3  nop     dword ptr [rax+rax+00h]
0x1407995e8  lea     r9, [rsp+38h+var_18]
0x1407995ed  mov     [rsp+38h+var_18], 0
0x1407995f6  xor     r8d, r8d
0x1407995f9  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFFh
0x140799602  mov     rdx, 0FFFFFFFFFD050F80h
0x140799609  lea     rcx, byte_140EF74E0
0x140799610  call    KeSetTimer2
0x140799615  mov     rbx, [rsp+38h+arg_0]
0x14079961a  add     rsp, 30h
0x14079961e  pop     rdi
0x14079961f  retn
```
