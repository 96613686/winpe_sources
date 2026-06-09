# SockOpenKeyEx

- ea: `0x18000170c`
- end: `0x180001753`
- name: `SockOpenKeyEx`
- size: `71`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800011d8`

## callees

- `0x18000170c`
- `0x18000175c`

## string_xrefs

- `0x18000172c`: `\Registry\Machine\System\CurrentControlSet\Services\Tcp\Parameters`
- `0x180001712`: `\Registry\Machine\System\CurrentControlSet\Services\Tcp\VParameters`
- `0x18000173f`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 __fastcall SockOpenKeyEx(PHANDLE KeyHandle)
{
  __int64 result; // rax

  result = SockOpenKey(KeyHandle, VTCPPARM);
  if ( (int)result < 0 )
  {
    result = SockOpenKey(KeyHandle, NTCPPARM);
    if ( (int)result < 0 )
      return SockOpenKey(KeyHandle, TCPPARM);
  }
  return result;
}

```

## disassembly

```asm
0x18000170c  push    rbx
0x18000170e  sub     rsp, 20h
0x180001712  lea     rdx, VTCPPARM; "\\Registry\\Machine\\System\\CurrentCon"...
0x180001719  mov     rbx, rcx
0x18000171c  call    SockOpenKey
0x180001721  test    eax, eax
0x180001723  js      short loc_18000172C
0x180001725  add     rsp, 20h
0x180001729  pop     rbx
0x18000172a  retn
0x18000172c  lea     rdx, NTCPPARM; "\\Registry\\Machine\\System\\CurrentCon"...
0x180001733  mov     rcx, rbx; KeyHandle
0x180001736  call    SockOpenKey
0x18000173b  test    eax, eax
0x18000173d  jns     short loc_180001725
0x18000173f  lea     rdx, TCPPARM; "\\Registry\\Machine\\System\\CurrentCon"...
0x180001746  mov     rcx, rbx; KeyHandle
0x180001749  add     rsp, 20h
0x18000174d  pop     rbx
0x18000174e  jmp     SockOpenKey
```
