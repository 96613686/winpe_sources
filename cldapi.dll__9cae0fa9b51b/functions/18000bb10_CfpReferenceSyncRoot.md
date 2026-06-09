# CfpReferenceSyncRoot

- ea: `0x18000bb10`
- end: `0x18000bb88`
- name: `CfpReferenceSyncRoot`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1800032a0`
- `0x180005b20`
- `0x180006010`
- `0x180006390`
- `0x1800082b0`
- `0x18000c2a0`
- `0x18000f690`
- `0x1800192a4`

## callees

- `0x18000bb10`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000bb72`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000bb72`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000bb23`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000bb23`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000bb3b`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000bb3b`

## pseudocode

```c
volatile signed __int64 *__fastcall CfpReferenceSyncRoot(volatile signed __int64 *a1)
{
  volatile signed __int64 *v1; // rbx
  volatile signed __int64 *Buffer; // [rsp+30h] [rbp+8h] BYREF

  Buffer = a1;
  v1 = 0;
  RtlAcquireSRWLockShared(&qword_18002ACF8);
  if ( RtlLookupElementGenericTableAvl(&stru_18002AC90, &Buffer) )
  {
    v1 = Buffer;
    if ( _InterlockedIncrement64(Buffer) <= 1 )
      __fastfail(0xEu);
  }
  RtlReleaseSRWLockShared(&qword_18002ACF8);
  return v1;
}

```

## disassembly

```asm
0x18000bb10  mov     [rsp+Buffer], rcx
0x18000bb15  push    rbx
0x18000bb16  sub     rsp, 20h
0x18000bb1a  lea     rcx, qword_18002ACF8
0x18000bb21  xor     ebx, ebx
0x18000bb23  call    cs:__imp_RtlAcquireSRWLockShared
0x18000bb2a  nop     dword ptr [rax+rax+00h]
0x18000bb2f  lea     rdx, [rsp+28h+Buffer]; Buffer
0x18000bb34  lea     rcx, stru_18002AC90; Table
0x18000bb3b  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000bb42  nop     dword ptr [rax+rax+00h]
0x18000bb47  test    rax, rax
0x18000bb4a  jz      short loc_18000BB6B
0x18000bb4c  mov     rbx, [rsp+28h+Buffer]
0x18000bb51  mov     edx, 1
0x18000bb56  lock xadd [rbx], rdx
0x18000bb5b  inc     rdx
0x18000bb5e  cmp     rdx, 1
0x18000bb62  jg      short loc_18000BB6B
0x18000bb64  mov     ecx, 0Eh
0x18000bb69  int     29h; Win8: RtlFailFast(ecx)
0x18000bb6b  lea     rcx, qword_18002ACF8
0x18000bb72  call    cs:__imp_RtlReleaseSRWLockShared
0x18000bb79  nop     dword ptr [rax+rax+00h]
0x18000bb7e  mov     rax, rbx
0x18000bb81  add     rsp, 20h
0x18000bb85  pop     rbx
0x18000bb86  retn
```
