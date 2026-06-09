# ImageList_Create

- ea: `0x18001ca18`
- end: `0x18001ca7a`
- name: `ImageList_Create`
- size: `98`
- prototype: `HIMAGELIST __stdcall(int cx, int cy, UINT flags, int cInitial, int cGrow)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000946c`
- `0x180009b34`

## callees

- `0x18001ca18`
- `0x18001cc10`
- `0x18001f010`

## string_xrefs

- `0x18001ca38`: `ImageList_Create`

## pseudocode

```c
HIMAGELIST __stdcall ImageList_Create(int cx, int cy, UINT flags, int cInitial, int cGrow)
{
  HIMAGELIST result; // rax

  result = (HIMAGELIST)qword_1800282D0;
  if ( qword_1800282D0 == -1 )
  {
    GetProcFromComCtl32(&qword_1800282D0, "ImageList_Create");
    result = (HIMAGELIST)qword_1800282D0;
  }
  if ( result )
    return (HIMAGELIST)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, int))result)(
                         (unsigned int)cx,
                         (unsigned int)cy,
                         flags,
                         (unsigned int)cInitial,
                         cGrow);
  return result;
}

```

## disassembly

```asm
0x18001ca18  push    rbx
0x18001ca1a  push    rbp
0x18001ca1b  push    rsi
0x18001ca1c  push    rdi
0x18001ca1d  sub     rsp, 38h
0x18001ca21  mov     rax, cs:qword_1800282D0
0x18001ca28  mov     ebx, r9d
0x18001ca2b  mov     edi, r8d
0x18001ca2e  mov     esi, edx
0x18001ca30  mov     ebp, ecx
0x18001ca32  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ca36  jnz     short loc_18001CA52
0x18001ca38  lea     rdx, aImagelistCreat; "ImageList_Create"
0x18001ca3f  lea     rcx, qword_1800282D0
0x18001ca46  call    _GetProcFromComCtl32
0x18001ca4b  mov     rax, cs:qword_1800282D0
0x18001ca52  test    rax, rax
0x18001ca55  jz      short loc_18001CA71
0x18001ca57  mov     ecx, [rsp+58h+cGrow]
0x18001ca5e  mov     r9d, ebx
0x18001ca61  mov     [rsp+58h+var_38], ecx
0x18001ca65  mov     r8d, edi
0x18001ca68  mov     ecx, ebp
0x18001ca6a  mov     edx, esi
0x18001ca6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca71  add     rsp, 38h
0x18001ca75  pop     rdi
0x18001ca76  pop     rsi
0x18001ca77  pop     rbp
0x18001ca78  pop     rbx
0x18001ca79  retn
```
