# HintCoconet__CreateInstance(IRdpPipeCompressHintProvider * *)

- ea: `0x180023ac0`
- end: `0x180023b98`
- name: `?HintCoconet__CreateInstance@@YAJPEAPEAVIRdpPipeCompressHintProvider@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct IRdpPipeCompressHintProvider **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f698`

## callees

- `0x180003714`
- `0x180004154`
- `0x18002a010`

## string_xrefs

- `0x180023af5`: `Compress_HintCoconet`

## pseudocode

```c
__int64 __fastcall HintCoconet__CreateInstance(struct IRdpPipeCompressHintProvider **a1)
{
  _DWORD *v2; // rdi

  v2 = operator new(0x8EAE0u);
  *(_QWORD *)v2 = &IRdpPipeCompressHintProvider::`vftable';
  v2[8] = -607474739;
  *((_QWORD *)v2 + 3) = "Compress_HintCoconet";
  v2[9] = 1;
  *((_QWORD *)v2 + 1) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)v2 + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
  v2[12] = 0;
  *((_QWORD *)v2 + 5) = v2 + 2;
  *(_QWORD *)v2 = &HintCoconet::`vftable';
  *((_QWORD *)v2 + 1) = &HintCoconet::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)v2 + 2) = &HintCoconet::`vftable'{for `CTSObject'};
  v2[9026] = 24;
  v2[9027] = 12;
  memset_0(v2 + 9028, 0, 0x80000u);
  v2[16] = 0;
  v2[143102] = 0;
  *a1 = (struct IRdpPipeCompressHintProvider *)v2;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x180023ac0  mov     [rsp+arg_0], rbx
0x180023ac5  push    rdi
0x180023ac6  sub     rsp, 20h
0x180023aca  mov     rbx, rcx
0x180023acd  mov     ecx, 8EAE0h; Size
0x180023ad2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023ad7  mov     rdi, rax
0x180023ada  mov     r8d, 80000h; Size
0x180023ae0  lea     rax, ??_7IRdpPipeCompressHintProvider@@6B@; const IRdpPipeCompressHintProvider::`vftable'
0x180023ae7  mov     [rdi], rax
0x180023aea  lea     rdx, [rdi+8]
0x180023aee  mov     dword ptr [rdx+18h], 0DBCAABCDh
0x180023af5  lea     rax, aCompressHintco; "Compress_HintCoconet"
0x180023afc  mov     [rdx+10h], rax
0x180023b00  lea     rcx, [rdi+8D10h]; void *
0x180023b07  mov     dword ptr [rdx+1Ch], 1
0x180023b0e  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x180023b15  mov     [rdx], rax
0x180023b18  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180023b1f  mov     [rdx+8], rax
0x180023b23  lea     rax, ??_7HintCoconet@@6B@; const HintCoconet::`vftable'
0x180023b2a  mov     dword ptr [rdx+28h], 0
0x180023b31  mov     [rdx+20h], rdx
0x180023b35  mov     [rdi], rax
0x180023b38  lea     rax, ??_7HintCoconet@@6BINonDelegatingUnknown@@@; const HintCoconet::`vftable'{for `INonDelegatingUnknown'}
0x180023b3f  mov     [rdx], rax
0x180023b42  lea     rax, ??_7HintCoconet@@6BCTSObject@@@; const HintCoconet::`vftable'{for `CTSObject'}
0x180023b49  mov     [rdi+10h], rax
0x180023b4d  xor     edx, edx; Val
0x180023b4f  mov     dword ptr [rdi+8D08h], 18h
0x180023b59  mov     dword ptr [rdi+8D0Ch], 0Ch
0x180023b63  call    memset_0
0x180023b68  mov     dword ptr [rdi+40h], 0
0x180023b6f  mov     rcx, rdi
0x180023b72  mov     dword ptr [rdi+8BBF8h], 0
0x180023b7c  mov     [rbx], rdi
0x180023b7f  mov     rax, [rdi]
0x180023b82  mov     rax, [rax+8]
0x180023b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b8b  mov     rbx, [rsp+28h+arg_0]
0x180023b90  xor     eax, eax
0x180023b92  add     rsp, 20h
0x180023b96  pop     rdi
0x180023b97  retn
```
