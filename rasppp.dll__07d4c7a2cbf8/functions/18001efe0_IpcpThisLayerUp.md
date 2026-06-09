# IpcpThisLayerUp

- ea: `0x18001efe0`
- end: `0x18001f065`
- name: `IpcpThisLayerUp`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001efe0`
- `0x180033010`

## string_xrefs

- `0x18001f043`: `IPCP: Link already up...ignored.`

## pseudocode

```c
__int64 __fastcall IpcpThisLayerUp(__int64 a1)
{
  __int64 v1; // rdx
  const wchar_t *v3; // r8

  v1 = *((_QWORD *)&xmmword_18004C860 + 1);
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      L"IPCP: IpcpThisLayerUp");
    v1 = *((_QWORD *)&xmmword_18004C860 + 1);
  }
  if ( *(_DWORD *)(a1 + 24) || *(_DWORD *)(a1 + 28) )
  {
    v1 = xmmword_18004C860;
    if ( (_QWORD)xmmword_18004C860 )
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
0x18001efe0  push    rbx
0x18001efe2  sub     rsp, 20h
0x18001efe6  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001efed  mov     rbx, rcx
0x18001eff0  test    rdx, rdx
0x18001eff3  jz      short loc_18001F016
0x18001eff5  mov     rcx, cs:gRasIpcpEtwContext
0x18001effc  lea     r8, aIpcpIpcpthisla_2; "IPCP: IpcpThisLayerUp"
0x18001f003  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f00f  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001f016  cmp     dword ptr [rbx+18h], 0
0x18001f01a  jnz     short loc_18001F037
0x18001f01c  cmp     dword ptr [rbx+1Ch], 0
0x18001f020  jnz     short loc_18001F037
0x18001f022  mov     dword ptr [rbx+1Ch], 1
0x18001f029  test    rdx, rdx
0x18001f02c  jz      short loc_18001F05D
0x18001f02e  lea     r8, aIpcpIpcpthisla_0; "IPCP: IpcpThisLayerUp done"
0x18001f035  jmp     short loc_18001F04A
0x18001f037  mov     rdx, qword ptr cs:xmmword_18004C860
0x18001f03e  test    rdx, rdx
0x18001f041  jz      short loc_18001F05D
0x18001f043  lea     r8, aIpcpLinkAlread; "IPCP: Link already up...ignored."
0x18001f04a  mov     rcx, cs:gRasIpcpEtwContext
0x18001f051  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f05d  xor     eax, eax
0x18001f05f  add     rsp, 20h
0x18001f063  pop     rbx
0x18001f064  retn
```
