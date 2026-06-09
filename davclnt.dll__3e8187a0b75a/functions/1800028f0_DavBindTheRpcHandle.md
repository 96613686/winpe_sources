# DavBindTheRpcHandle

- ea: `0x1800028f0`
- end: `0x180002966`
- name: `DavBindTheRpcHandle`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `12`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001310`
- `0x180001600`
- `0x180004340`
- `0x180007ad0`
- `0x18000b4f0`
- `0x18000c170`
- `0x18000c7e0`
- `0x18000cb10`
- `0x18000ceb0`
- `0x18000e494`
- `0x18000f2d0`
- `0x18000fd30`

## callees

- `0x1800028f0`
- `0x180003540`
- `0x180010be8`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180002912`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180002912`

## pseudocode

```c
__int64 __fastcall DavBindTheRpcHandle(_QWORD *a1, __int64 a2, __int64 a3)
{
  NTSTATUS v4; // eax
  ULONG v5; // ebx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v4 = RpcpBindRpc(a1, a2, a3, &v7);
  v5 = RtlNtStatusToDosErrorNoTeb(v4);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v5);
  }
  else
  {
    *a1 = v7;
  }
  return v5;
}

```

## disassembly

```asm
0x1800028f0  mov     [rsp+arg_0], rbx
0x1800028f5  push    rdi
0x1800028f6  sub     rsp, 20h
0x1800028fa  lea     r9, [rsp+28h+arg_8]
0x1800028ff  mov     [rsp+28h+arg_8], 0
0x180002908  mov     rdi, rcx
0x18000290b  call    RpcpBindRpc
0x180002910  mov     ecx, eax; Status
0x180002912  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180002918  mov     ebx, eax
0x18000291a  test    eax, eax
0x18000291c  jnz     short loc_180002933
0x18000291e  mov     rax, [rsp+28h+arg_8]
0x180002923  mov     [rdi], rax
0x180002926  mov     eax, ebx
0x180002928  mov     rbx, [rsp+28h+arg_0]
0x18000292d  add     rsp, 20h
0x180002931  pop     rdi
0x180002932  retn
0x180002933  mov     rcx, cs:WPP_GLOBAL_Control
0x18000293a  lea     rax, WPP_GLOBAL_Control
0x180002941  cmp     rcx, rax
0x180002944  jz      short loc_180002926
0x180002946  test    byte ptr [rcx+1Ch], 1
0x18000294a  jz      short loc_180002926
0x18000294c  mov     rcx, [rcx+10h]
0x180002950  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180002957  mov     edx, 0CAh
0x18000295c  mov     r9d, ebx
0x18000295f  call    WPP_SF_d
0x180002964  jmp     short loc_180002926
```
