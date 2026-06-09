# CNetDiagHelperImpl::GetCacheTime(_FILETIME *)

- ea: `0x18000a850`
- end: `0x18000a891`
- name: `?GetCacheTime@CNetDiagHelperImpl@@UEAAJPEAU_FILETIME@@@Z`
- size: `65`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a850`
- `0x18000edb8`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetCacheTime(CNetDiagHelperImpl *this, struct _FILETIME *a2)
{
  struct _FILETIME *v2; // rbx
  __int64 result; // rax

  v2 = a2;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = 8;
  do
  {
    LOBYTE(v2->dwLowDateTime) = 0;
    v2 = (struct _FILETIME *)((char *)v2 + 1);
    --result;
  }
  while ( result );
  return result;
}

```

## disassembly

```asm
0x18000a850  mov     [rsp+arg_0], rbx
0x18000a855  push    rdi
0x18000a856  sub     rsp, 20h
0x18000a85a  mov     rbx, rdx
0x18000a85d  mov     rdi, rcx
0x18000a860  test    rdx, rdx
0x18000a863  jnz     short loc_18000A86A
0x18000a865  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a86a  cmp     dword ptr [rdi+10h], 1
0x18000a86e  jz      short loc_18000A875
0x18000a870  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a875  mov     eax, 8
0x18000a87a  mov     byte ptr [rbx], 0
0x18000a87d  inc     rbx
0x18000a880  sub     rax, 1
0x18000a884  jnz     short loc_18000A87A
0x18000a886  mov     rbx, [rsp+28h+arg_0]
0x18000a88b  add     rsp, 20h
0x18000a88f  pop     rdi
0x18000a890  retn
```
