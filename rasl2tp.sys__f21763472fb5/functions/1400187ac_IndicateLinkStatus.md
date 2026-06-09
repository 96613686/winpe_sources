# IndicateLinkStatus

- ea: `0x1400187ac`
- end: `0x14001883e`
- name: `IndicateLinkStatus`
- size: `146`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400109d0`
- `0x1400152b0`
- `0x140017b90`

## callees

- `0x1400047f0`
- `0x140004c00`

## import_xrefs

- `NDIS!NdisMCoIndicateStatusEx` at `0x140018810`
- `NDIS!NdisMCoIndicateStatusEx` at `0x140018810`

## pseudocode

```c
void __fastcall IndicateLinkStatus(__int64 a1, __int64 a2)
{
  void *v3; // rdx
  _NDIS_STATUS_INDICATION StatusIndication; // [rsp+20h] [rbp-88h] BYREF

  memset(&StatusIndication, 0, sizeof(StatusIndication));
  v3 = *(void **)(a2 + 8);
  StatusIndication.SourceHandle = *(NDIS_HANDLE *)a2;
  StatusIndication.StatusBuffer = (PVOID)(a2 + 16);
  StatusIndication.Header = (NDIS_OBJECT_HEADER)7340440;
  StatusIndication.StatusCode = 1073807382;
  StatusIndication.StatusBufferSize = 12;
  NdisMCoIndicateStatusEx(StatusIndication.SourceHandle, v3, &StatusIndication);
}

```

## disassembly

```asm
0x1400187ac  mov     [rsp+arg_0], rbx
0x1400187b1  push    rdi
0x1400187b2  sub     rsp, 0A0h
0x1400187b9  mov     rax, cs:__security_cookie
0x1400187c0  xor     rax, rsp
0x1400187c3  mov     [rsp+0A8h+var_18], rax
0x1400187cb  mov     rbx, rdx
0x1400187ce  lea     rcx, [rsp+0A8h+StatusIndication]; void *
0x1400187d3  xor     edx, edx; Val
0x1400187d5  lea     r8d, [rdx+70h]; Size
0x1400187d9  call    memset
0x1400187de  mov     rcx, [rbx]; MiniportAdapterHandle
0x1400187e1  lea     rax, [rbx+10h]
0x1400187e5  mov     rdx, [rbx+8]; NdisVcHandle
0x1400187e9  lea     r8, [rsp+0A8h+StatusIndication]; StatusIndication
0x1400187ee  mov     [rsp+0A8h+StatusIndication.SourceHandle], rcx
0x1400187f3  mov     [rsp+0A8h+StatusIndication.StatusBuffer], rax
0x1400187f8  mov     dword ptr [rsp+0A8h+StatusIndication.Header.Type], 700198h
0x140018800  mov     [rsp+0A8h+StatusIndication.StatusCode], 40010016h
0x140018808  mov     [rsp+0A8h+StatusIndication.StatusBufferSize], 0Ch
0x140018810  call    cs:__imp_NdisMCoIndicateStatusEx
0x140018817  nop     dword ptr [rax+rax+00h]
0x14001881c  mov     rcx, [rsp+0A8h+var_18]
0x140018824  xor     rcx, rsp; StackCookie
0x140018827  call    __security_check_cookie
0x14001882c  mov     rbx, [rsp+0A8h+arg_0]
0x140018834  add     rsp, 0A0h
0x14001883b  pop     rdi
0x14001883c  retn
```
