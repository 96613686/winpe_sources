# WaitForRemoteDatabaseSemaphore

- ea: `0x140010e70`
- end: `0x140010ee0`
- name: `WaitForRemoteDatabaseSemaphore`
- size: `112`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d494`
- `0x14000ebe4`
- `0x14000f440`
- `0x1400119a0`

## callees

- `0x140001ae0`
- `0x140010e70`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140010e93`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010e93`

## pseudocode

```c
NTSTATUS __fastcall WaitForRemoteDatabaseSemaphore(__int64 a1)
{
  NTSTATUS result; // eax
  __int64 v2; // r8
  union _LARGE_INTEGER Timeout; // [rsp+40h] [rbp+8h] BYREF

  Timeout.QuadPart = -100000000;
  result = KeWaitForSingleObject((PVOID)(a1 + 112), Executive, 0, 0, &Timeout);
  if ( result == 258 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L((__int64)WPP_GLOBAL_Control->AttachedDevice, 0x4Au, v2, -1073741643);
    return -1073741643;
  }
  return result;
}

```

## disassembly

```asm
0x140010e70  sub     rsp, 38h
0x140010e74  lea     rax, [rsp+38h+arg_0]
0x140010e79  mov     qword ptr [rsp+38h+arg_0], 0FFFFFFFFFA0A1F00h
0x140010e82  add     rcx, 70h ; 'p'; Object
0x140010e86  mov     [rsp+38h+Timeout], rax; Timeout
0x140010e8b  xor     r9d, r9d; Alertable
0x140010e8e  xor     r8d, r8d; WaitMode
0x140010e91  xor     edx, edx; WaitReason
0x140010e93  call    cs:__imp_KeWaitForSingleObject
0x140010e9a  nop     dword ptr [rax+rax+00h]
0x140010e9f  cmp     eax, 102h
0x140010ea4  jnz     short loc_140010EDA
0x140010ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ead  lea     rdx, WPP_GLOBAL_Control
0x140010eb4  cmp     rcx, rdx
0x140010eb7  jz      short loc_140010ED5
0x140010eb9  mov     edx, [rcx+2Ch]
0x140010ebc  test    dl, 1
0x140010ebf  jz      short loc_140010ED5
0x140010ec1  mov     rcx, [rcx+18h]
0x140010ec5  mov     edx, 4Ah ; 'J'
0x140010eca  mov     r9d, 0C00000B5h
0x140010ed0  call    WPP_SF_L
0x140010ed5  mov     eax, 0C00000B5h
0x140010eda  add     rsp, 38h
0x140010ede  retn
```
