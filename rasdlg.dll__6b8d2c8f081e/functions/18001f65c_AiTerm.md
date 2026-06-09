# AiTerm

- ea: `0x18001f65c`
- end: `0x18001f71f`
- name: `AiTerm`
- size: `195`
- prototype: `HANDLE __fastcall(HWND hWnd)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800205c0`
- `0x180021810`

## callees

- `0x180015a3c`
- `0x18001c088`
- `0x18001f65c`
- `0x18003b6b8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001f6d8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001f6d8`
- `GDI32!DeleteObject` at `0x18001f6a2`
- `GDI32!DeleteObject` at `0x18001f6a2`
- `USER32!RemovePropW` at `0x18001f718`
- `USER32!GetParent` at `0x18001f6fe`
- `USER32!GetParent` at `0x18001f6fe`
- `rtutils!TracePrintfExA` at `0x18001f680`
- `rtutils!TracePrintfExA` at `0x18001f6f5`
- `rtutils!TracePrintfExA` at `0x18001f680`
- `rtutils!TracePrintfExA` at `0x18001f6f5`

## pseudocode

```c
HANDLE __fastcall AiTerm(HWND hWnd)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  void *v4; // rcx
  void *v5; // rcx
  HWND Parent; // rax

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "AiTerm");
  v2 = AiContext(hWnd);
  v3 = v2;
  if ( v2 )
  {
    v4 = (void *)v2[75];
    if ( v4 )
      DeleteObject(v4);
    v5 = (void *)v3[58];
    if ( v5 )
      DtlDestroyList(v5);
    if ( *((_DWORD *)v3 + 148) )
      SuFree(v3 + 65);
    GlobalFree(v3);
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Context freed");
  }
  Parent = GetParent(hWnd);
  return RemovePropW(Parent, g_contextId);
}

```

## disassembly

```asm
0x18001f65c  mov     [rsp+arg_0], rbx
0x18001f661  push    rdi
0x18001f662  sub     rsp, 20h
0x18001f666  mov     rdi, rcx
0x18001f669  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f66f  cmp     ecx, 0FFFFFFFFh
0x18001f672  jz      short loc_18001F686
0x18001f674  lea     r8, aAiterm; "AiTerm"
0x18001f67b  mov     edx, 0Ch; dwFlags
0x18001f680  call    cs:__imp_TracePrintfExA
0x18001f686  mov     rcx, rdi
0x18001f689  call    AiContext
0x18001f68e  mov     rbx, rax
0x18001f691  test    rax, rax
0x18001f694  jz      short loc_18001F6FB
0x18001f696  mov     rcx, [rax+258h]; ho
0x18001f69d  test    rcx, rcx
0x18001f6a0  jz      short loc_18001F6A8
0x18001f6a2  call    cs:__imp_DeleteObject
0x18001f6a8  mov     rcx, [rbx+1D0h]; hMem
0x18001f6af  test    rcx, rcx
0x18001f6b2  jz      short loc_18001F6C0
0x18001f6b4  lea     rdx, DestroyPszNode
0x18001f6bb  call    DtlDestroyList
0x18001f6c0  cmp     dword ptr [rbx+250h], 0
0x18001f6c7  jz      short loc_18001F6D5
0x18001f6c9  lea     rcx, [rbx+208h]
0x18001f6d0  call    SuFree
0x18001f6d5  mov     rcx, rbx; hMem
0x18001f6d8  call    cs:__imp_GlobalFree
0x18001f6de  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f6e4  cmp     ecx, 0FFFFFFFFh
0x18001f6e7  jz      short loc_18001F6FB
0x18001f6e9  lea     r8, aContextFreed; "Context freed"
0x18001f6f0  mov     edx, 0Ch; dwFlags
0x18001f6f5  call    cs:__imp_TracePrintfExA
0x18001f6fb  mov     rcx, rdi; hWnd
0x18001f6fe  call    cs:__imp_GetParent
0x18001f704  mov     rdx, cs:g_contextId
0x18001f70b  mov     rcx, rax
0x18001f70e  mov     rbx, [rsp+28h+arg_0]
0x18001f713  add     rsp, 20h
0x18001f717  pop     rdi
0x18001f718  jmp     cs:__imp_RemovePropW
```
