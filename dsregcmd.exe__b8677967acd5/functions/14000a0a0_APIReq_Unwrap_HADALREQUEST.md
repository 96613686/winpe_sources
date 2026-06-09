# APIReq::Unwrap(HADALREQUEST__ *)

- ea: `0x14000a0a0`
- end: `0x14000a0e6`
- name: `?Unwrap@APIReq@@SAPEAVTokenRequest@@PEAUHADALREQUEST__@@@Z`
- size: `70`
- prototype: `struct TokenRequest *__fastcall(struct HADALREQUEST__ *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140006ad0`
- `0x140006b54`
- `0x140006c18`
- `0x140006cdc`
- `0x140006f24`
- `0x140006fb8`

## callees

- `0x14000a0a0`
- `0x14000a17c`
- `0x14000e020`
- `0x14002c3e8`

## pseudocode

```c
struct TokenRequest *__fastcall APIReq::Unwrap(struct HADALREQUEST__ *a1)
{
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 || !(unsigned __int8)APIHandle<APIReq,HADALREQUEST__ *,-1440046422>::Validate() )
  {
    InvalidHandleException::InvalidHandleException((InvalidHandleException *)pExceptionObject, 0xCAA1000E);
    throw (InvalidHandleException *)pExceptionObject;
  }
  return *(struct TokenRequest **)(*((_QWORD *)a1 + 1) + 16LL);
}

```

## disassembly

```asm
0x14000a0a0  push    rbx
0x14000a0a2  sub     rsp, 30h
0x14000a0a6  mov     rbx, rcx
0x14000a0a9  test    rcx, rcx
0x14000a0ac  jz      short loc_14000A0C5
0x14000a0ae  call    ?Validate@?$APIHandle@VAPIReq@@PEAUHADALREQUEST__@@$0?FFNFFNFG@@@CA_NPEBV1@@Z; APIHandle<APIReq,HADALREQUEST__ *,-1440046422>::Validate(APIHandle<APIReq,HADALREQUEST__ *,-1440046422> const *)
0x14000a0b3  test    al, al
0x14000a0b5  jz      short loc_14000A0C5
0x14000a0b7  mov     rax, [rbx+8]
0x14000a0bb  mov     rax, [rax+10h]
0x14000a0bf  add     rsp, 30h
0x14000a0c3  pop     rbx
0x14000a0c4  retn
0x14000a0c5  mov     edx, 0CAA1000Eh; unsigned int
0x14000a0ca  lea     rcx, [rsp+38h+pExceptionObject]; this
0x14000a0cf  call    ??0InvalidHandleException@@QEAA@K@Z; InvalidHandleException::InvalidHandleException(ulong)
0x14000a0d4  lea     rdx, _TI4?AVInvalidHandleException@@; pThrowInfo
0x14000a0db  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x14000a0e0  call    _CxxThrowException_0
```
