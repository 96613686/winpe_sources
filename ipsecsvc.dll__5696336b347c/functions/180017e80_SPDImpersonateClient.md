# SPDImpersonateClient

- ea: `0x180017e80`
- end: `0x180017ee8`
- name: `SPDImpersonateClient`
- size: `104`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `64`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000fd90`
- `0x18000ff90`
- `0x1800101a0`
- `0x180010370`
- `0x1800104e0`
- `0x180010660`
- `0x180010860`
- `0x180010a10`
- `0x180010be0`
- `0x180010cb0`
- `0x180010d80`
- `0x180010e50`
- `0x180010f40`
- `0x180011010`
- `0x180011120`
- `0x180011290`
- `0x180011390`
- `0x1800115f0`
- `0x1800116c0`
- `0x1800117b0`
- `0x180011920`
- `0x180011b00`
- `0x180011cd0`
- `0x180011ea0`
- `0x180012000`
- `0x1800122a0`
- `0x180012410`
- `0x1800125b0`
- `0x180012780`
- `0x180012950`
- `0x180012b20`
- `0x180012c60`
- `0x180012dd0`
- `0x180012f00`
- `0x180013030`
- `0x180013150`
- `0x180013280`
- `0x1800133b0`
- `0x1800134f0`
- `0x180013620`
- `0x180013750`
- `0x180013880`
- `0x180013bc0`
- `0x180013ea0`
- `0x180014110`
- `0x180014320`
- `0x180014510`
- `0x180014700`
- `0x1800148a0`
- `0x180014a90`

## callees

- `0x18000e510`
- `0x180017e80`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180017e8f`
- `RPCRT4!RpcImpersonateClient` at `0x180017e8f`

## pseudocode

```c
__int64 __fastcall SPDImpersonateClient(_DWORD *a1)
{
  unsigned int v2; // ebx

  v2 = RpcImpersonateClient(0);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_bb8ad0123c3f3ab26dbf6222817f5839_Traceguids, v2);
    *a1 = 0;
    return v2;
  }
  else
  {
    *a1 = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x180017e80  mov     [rsp+arg_0], rbx
0x180017e85  push    rdi
0x180017e86  sub     rsp, 20h
0x180017e8a  mov     rdi, rcx
0x180017e8d  xor     ecx, ecx; BindingHandle
0x180017e8f  call    cs:__imp_RpcImpersonateClient
0x180017e95  mov     ebx, eax
0x180017e97  test    eax, eax
0x180017e99  jz      short loc_180017ED5
0x180017e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ea2  lea     rax, WPP_GLOBAL_Control
0x180017ea9  cmp     rcx, rax
0x180017eac  jz      short loc_180017ECB
0x180017eae  mov     edx, 10h
0x180017eb3  test    [rcx+1Ch], dl
0x180017eb6  jz      short loc_180017ECB
0x180017eb8  mov     rcx, [rcx+10h]
0x180017ebc  lea     r8, WPP_bb8ad0123c3f3ab26dbf6222817f5839_Traceguids
0x180017ec3  mov     r9d, ebx
0x180017ec6  call    WPP_SF_d
0x180017ecb  mov     dword ptr [rdi], 0
0x180017ed1  mov     eax, ebx
0x180017ed3  jmp     short loc_180017EDD
0x180017ed5  mov     dword ptr [rdi], 1
0x180017edb  xor     eax, eax
0x180017edd  mov     rbx, [rsp+28h+arg_0]
0x180017ee2  add     rsp, 20h
0x180017ee6  pop     rdi
0x180017ee7  retn
```
