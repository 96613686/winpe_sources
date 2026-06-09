# CNetDiagHelperImpl::GetCacheTime(_FILETIME *)

- ea: `0x18000d4b0`
- end: `0x18000d4f2`
- name: `?GetCacheTime@CNetDiagHelperImpl@@UEAAJPEAU_FILETIME@@@Z`
- size: `66`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, struct _FILETIME *, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d4b0`
- `0x18000dd64`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetCacheTime(
        CNetDiagHelperImpl *this,
        struct _FILETIME *a2,
        __int64 a3,
        __int64 a4)
{
  struct _FILETIME *v4; // rbx
  __int64 result; // rax

  v4 = a2;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3, a4);
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  result = 8;
  do
  {
    LOBYTE(v4->dwLowDateTime) = 0;
    v4 = (struct _FILETIME *)((char *)v4 + 1);
    --result;
  }
  while ( result );
  return result;
}

```

## disassembly

```asm
0x18000d4b0  mov     [rsp+arg_0], rbx
0x18000d4b5  push    rdi
0x18000d4b6  sub     rsp, 20h
0x18000d4ba  mov     rbx, rdx
0x18000d4bd  mov     rdi, rcx
0x18000d4c0  test    rdx, rdx
0x18000d4c3  jnz     short loc_18000D4CA
0x18000d4c5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d4ca  cmp     dword ptr [rdi+10h], 1
0x18000d4ce  jz      short loc_18000D4D5
0x18000d4d0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d4d5  mov     eax, 8
0x18000d4da  mov     byte ptr [rbx], 0
0x18000d4dd  inc     rbx
0x18000d4e0  sub     rax, 1
0x18000d4e4  jnz     short loc_18000D4DA
0x18000d4e6  mov     rbx, [rsp+28h+arg_0]
0x18000d4eb  add     rsp, 20h
0x18000d4ef  pop     rdi
0x18000d4f0  retn
```
