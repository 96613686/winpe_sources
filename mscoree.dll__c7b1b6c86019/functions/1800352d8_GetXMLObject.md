# GetXMLObject

- ea: `0x1800352d8`
- end: `0x180035324`
- name: `GetXMLObject`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180025c30`
- `0x18003229c`

## callees

- `0x18003007c`
- `0x1800300c0`
- `0x180030384`
- `0x1800352d8`
- `0x18003532c`

## pseudocode

```c
__int64 __fastcall GetXMLObject(__int64 a1)
{
  unsigned int XMLObject; // ebx
  _DWORD v4[6]; // [rsp+20h] [rbp-18h] BYREF

  SOIntolerantTransitionHandler::SOIntolerantTransitionHandler((SOIntolerantTransitionHandler *)v4);
  if ( SOIntolerantTransitionHandler::RetailStackProbeNoThrowNoThread((SOIntolerantTransitionHandler *)v4) )
    XMLObject = GetXMLObjectEx(a1);
  else
    XMLObject = -2147023895;
  v4[0] = 0;
  SOIntolerantTransitionHandler::~SOIntolerantTransitionHandler((SOIntolerantTransitionHandler *)v4);
  return XMLObject;
}

```

## disassembly

```asm
0x1800352d8  push    rbx
0x1800352da  sub     rsp, 30h
0x1800352de  mov     rbx, rcx
0x1800352e1  lea     rcx, [rsp+38h+var_18]; this
0x1800352e6  call    ??0SOIntolerantTransitionHandler@@QEAA@XZ; SOIntolerantTransitionHandler::SOIntolerantTransitionHandler(void)
0x1800352eb  lea     rcx, [rsp+38h+var_18]; this
0x1800352f0  call    ?RetailStackProbeNoThrowNoThread@SOIntolerantTransitionHandler@@QEAAHI@Z; SOIntolerantTransitionHandler::RetailStackProbeNoThrowNoThread(uint)
0x1800352f5  test    eax, eax
0x1800352f7  jnz     short loc_180035300
0x1800352f9  mov     ebx, 800703E9h
0x1800352fe  jmp     short loc_18003530A
0x180035300  mov     rcx, rbx
0x180035303  call    GetXMLObjectEx
0x180035308  mov     ebx, eax
0x18003530a  lea     rcx, [rsp+38h+var_18]; this
0x18003530f  mov     [rsp+38h+var_18], 0
0x180035317  call    ??1SOIntolerantTransitionHandler@@QEAA@XZ; SOIntolerantTransitionHandler::~SOIntolerantTransitionHandler(void)
0x18003531c  mov     eax, ebx
0x18003531e  add     rsp, 30h
0x180035322  pop     rbx
0x180035323  retn
```
