# CNetDiagHelperImpl::GetCacheTime(_FILETIME *)

- ea: `0x180017ea0`
- end: `0x180017ee1`
- name: `?GetCacheTime@CNetDiagHelperImpl@@UEAAJPEAU_FILETIME@@@Z`
- size: `65`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, struct _FILETIME *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180017ea0`
- `0x18001a178`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetCacheTime(CNetDiagHelperImpl *this, struct _FILETIME *a2, __int64 a3)
{
  struct _FILETIME *v3; // rbx
  __int64 result; // rax

  v3 = a2;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3);
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  result = 8;
  do
  {
    LOBYTE(v3->dwLowDateTime) = 0;
    v3 = (struct _FILETIME *)((char *)v3 + 1);
    --result;
  }
  while ( result );
  return result;
}

```

## disassembly

```asm
0x180017ea0  mov     [rsp+arg_0], rbx
0x180017ea5  push    rdi
0x180017ea6  sub     rsp, 20h
0x180017eaa  mov     rbx, rdx
0x180017ead  mov     rdi, rcx
0x180017eb0  test    rdx, rdx
0x180017eb3  jnz     short loc_180017EBA
0x180017eb5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180017eba  cmp     dword ptr [rdi+10h], 1
0x180017ebe  jz      short loc_180017EC5
0x180017ec0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180017ec5  mov     eax, 8
0x180017eca  mov     byte ptr [rbx], 0
0x180017ecd  inc     rbx
0x180017ed0  sub     rax, 1
0x180017ed4  jnz     short loc_180017ECA
0x180017ed6  mov     rbx, [rsp+28h+arg_0]
0x180017edb  add     rsp, 20h
0x180017edf  pop     rdi
0x180017ee0  retn
```
