# _DllEntryPoint

- ea: `0x18003d904`
- end: `0x18003d943`
- name: `_DllEntryPoint`
- size: `63`
- prototype: `__int64 __fastcall(HMODULE, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180025830`

## callees

- `0x180017ea0`
- `0x18003d904`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x18003d916`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18003d916`

## pseudocode

```c
__int64 __fastcall DllEntryPoint(HMODULE a1, int a2)
{
  unsigned int v3; // ecx

  if ( !a2 )
  {
    v3 = 0;
    goto LABEL_5;
  }
  if ( a2 == 1 )
  {
    DisableThreadLibraryCalls(a1);
    v3 = 1;
    g_hInst = a1;
LABEL_5:
    DllInitClasses(v3);
  }
  return 1;
}

```

## disassembly

```asm
0x18003d904  push    rbx
0x18003d906  sub     rsp, 20h
0x18003d90a  mov     rbx, rcx
0x18003d90d  test    edx, edx
0x18003d90f  jz      short loc_18003D930
0x18003d911  cmp     edx, 1
0x18003d914  jnz     short loc_18003D937
0x18003d916  call    cs:__imp_DisableThreadLibraryCalls
0x18003d91d  nop     dword ptr [rax+rax+00h]
0x18003d922  mov     ecx, 1
0x18003d927  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInst
0x18003d92e  jmp     short loc_18003D932
0x18003d930  xor     ecx, ecx; int
0x18003d932  call    ?DllInitClasses@@YAXH@Z; DllInitClasses(int)
0x18003d937  mov     eax, 1
0x18003d93c  add     rsp, 20h
0x18003d940  pop     rbx
0x18003d941  retn
```
