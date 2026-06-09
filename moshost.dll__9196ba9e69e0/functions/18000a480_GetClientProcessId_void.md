# GetClientProcessId(void)

- ea: `0x18000a480`
- end: `0x18000a507`
- name: `?GetClientProcessId@@YAKXZ`
- size: `135`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180007350`
- `0x1800082d0`
- `0x180008ce0`
- `0x180008f90`
- `0x180009250`

## callees

- `0x180001d00`
- `0x180002722`
- `0x18000a480`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000a4c2`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000a4c2`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000a4e0`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000a4e0`

## string_xrefs

- `0x18000a4ce`: `GetClientProcessId`

## pseudocode

```c
__int64 GetClientProcessId(void)
{
  RPC_STATUS v0; // eax
  unsigned int v1; // ebx
  _DWORD RpcCallAttributes[2]; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v4[56]; // [rsp+28h] [rbp-90h] BYREF
  unsigned int v5; // [rsp+60h] [rbp-58h]

  memset_0(v4, 0, 0x70u);
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 16;
  v0 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v0 )
  {
    v1 = 0;
    ZTraceReportOriginationNoThis(v0 | 0x80010000, "GetClientProcessId", 32);
  }
  else
  {
    return v5;
  }
  return v1;
}

```

## disassembly

```asm
0x18000a480  push    rbx
0x18000a482  sub     rsp, 0B0h
0x18000a489  mov     rax, cs:__security_cookie
0x18000a490  xor     rax, rsp
0x18000a493  mov     [rsp+0B8h+var_18], rax
0x18000a49b  xor     edx, edx; Val
0x18000a49d  lea     rcx, [rsp+0B8h+var_90]; void *
0x18000a4a2  lea     r8d, [rdx+70h]; Size
0x18000a4a6  call    memset_0
0x18000a4ab  lea     rdx, [rsp+0B8h+RpcCallAttributes]; RpcCallAttributes
0x18000a4b0  mov     [rsp+0B8h+RpcCallAttributes], 3
0x18000a4b8  xor     ecx, ecx; ClientBinding
0x18000a4ba  mov     [rsp+0B8h+var_94], 10h
0x18000a4c2  call    cs:__imp_RpcServerInqCallAttributesW
0x18000a4c8  test    eax, eax
0x18000a4ca  jz      short loc_18000A4E8
0x18000a4cc  xor     ebx, ebx
0x18000a4ce  lea     rdx, aGetclientproce; "GetClientProcessId"
0x18000a4d5  or      eax, 80010000h
0x18000a4da  mov     ecx, eax
0x18000a4dc  lea     r8d, [rbx+20h]
0x18000a4e0  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000a4e6  jmp     short loc_18000A4EC
0x18000a4e8  mov     ebx, [rsp+0B8h+var_58]
0x18000a4ec  mov     eax, ebx
0x18000a4ee  mov     rcx, [rsp+0B8h+var_18]
0x18000a4f6  xor     rcx, rsp; StackCookie
0x18000a4f9  call    __security_check_cookie
0x18000a4fe  add     rsp, 0B0h
0x18000a505  pop     rbx
0x18000a506  retn
```
