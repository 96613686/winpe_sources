# IpcpThisLayerUp

- ea: `0x18001fb90`
- end: `0x18001fc16`
- name: `IpcpThisLayerUp`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001fb90`
- `0x180034010`

## string_xrefs

- `0x18001fbf3`: `IPCP: Link already up...ignored.`

## pseudocode

```c
__int64 __fastcall IpcpThisLayerUp(__int64 a1)
{
  __int64 v1; // rdx
  const wchar_t *v3; // r8

  v1 = *((_QWORD *)&xmmword_18004D860 + 1);
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      L"IPCP: IpcpThisLayerUp");
    v1 = *((_QWORD *)&xmmword_18004D860 + 1);
  }
  if ( *(_DWORD *)(a1 + 24) || *(_DWORD *)(a1 + 28) )
  {
    v1 = xmmword_18004D860;
    if ( (_QWORD)xmmword_18004D860 )
    {
      v3 = L"IPCP: Link already up...ignored.";
      goto LABEL_9;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 28) = 1;
    if ( v1 )
    {
      v3 = L"IPCP: IpcpThisLayerUp done";
LABEL_9:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(gRasIpcpEtwContext, v1, v3);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001fb90  push    rbx
0x18001fb92  sub     rsp, 20h
0x18001fb96  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001fb9d  mov     rbx, rcx
0x18001fba0  test    rdx, rdx
0x18001fba3  jz      short loc_18001FBC6
0x18001fba5  mov     rcx, cs:gRasIpcpEtwContext
0x18001fbac  lea     r8, aIpcpIpcpthisla_2; "IPCP: IpcpThisLayerUp"
0x18001fbb3  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbbf  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001fbc6  cmp     dword ptr [rbx+18h], 0
0x18001fbca  jnz     short loc_18001FBE7
0x18001fbcc  cmp     dword ptr [rbx+1Ch], 0
0x18001fbd0  jnz     short loc_18001FBE7
0x18001fbd2  mov     dword ptr [rbx+1Ch], 1
0x18001fbd9  test    rdx, rdx
0x18001fbdc  jz      short loc_18001FC0D
0x18001fbde  lea     r8, aIpcpIpcpthisla_0; "IPCP: IpcpThisLayerUp done"
0x18001fbe5  jmp     short loc_18001FBFA
0x18001fbe7  mov     rdx, qword ptr cs:xmmword_18004D860
0x18001fbee  test    rdx, rdx
0x18001fbf1  jz      short loc_18001FC0D
0x18001fbf3  lea     r8, aIpcpLinkAlread; "IPCP: Link already up...ignored."
0x18001fbfa  mov     rcx, cs:gRasIpcpEtwContext
0x18001fc01  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc0d  xor     eax, eax
0x18001fc0f  add     rsp, 20h
0x18001fc13  pop     rbx
0x18001fc14  retn
```
