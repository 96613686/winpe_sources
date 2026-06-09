# ImageList_ReplaceIcon

- ea: `0x18001ca80`
- end: `0x18001cae5`
- name: `ImageList_ReplaceIcon`
- size: `101`
- prototype: `int __stdcall(HIMAGELIST himl, int i, HICON hicon)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000946c`

## callees

- `0x18001ca80`
- `0x18001cc10`
- `0x18001f010`

## string_xrefs

- `0x18001caa4`: `ImageList_ReplaceIcon`

## pseudocode

```c
int __stdcall ImageList_ReplaceIcon(HIMAGELIST himl, int i, HICON hicon)
{
  __int64 (__fastcall *v3)(HIMAGELIST, _QWORD, HICON); // rax

  v3 = (__int64 (__fastcall *)(HIMAGELIST, _QWORD, HICON))qword_1800282C8;
  if ( qword_1800282C8 == -1 )
  {
    GetProcFromComCtl32(&qword_1800282C8, "ImageList_ReplaceIcon");
    v3 = (__int64 (__fastcall *)(HIMAGELIST, _QWORD, HICON))qword_1800282C8;
  }
  if ( v3 )
    return v3(himl, (unsigned int)i, hicon);
  else
    return -1;
}

```

## disassembly

```asm
0x18001ca80  mov     [rsp+arg_0], rbx
0x18001ca85  mov     [rsp+arg_8], rsi
0x18001ca8a  push    rdi
0x18001ca8b  sub     rsp, 20h
0x18001ca8f  mov     rax, cs:qword_1800282C8
0x18001ca96  mov     rbx, r8
0x18001ca99  mov     edi, edx
0x18001ca9b  mov     rsi, rcx
0x18001ca9e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001caa2  jnz     short loc_18001CABE
0x18001caa4  lea     rdx, aImagelistRepla; "ImageList_ReplaceIcon"
0x18001caab  lea     rcx, qword_1800282C8
0x18001cab2  call    _GetProcFromComCtl32
0x18001cab7  mov     rax, cs:qword_1800282C8
0x18001cabe  test    rax, rax
0x18001cac1  jz      short loc_18001CAD2
0x18001cac3  mov     r8, rbx
0x18001cac6  mov     edx, edi
0x18001cac8  mov     rcx, rsi
0x18001cacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cad0  jmp     short loc_18001CAD5
0x18001cad2  or      eax, 0FFFFFFFFh
0x18001cad5  mov     rbx, [rsp+28h+arg_0]
0x18001cada  mov     rsi, [rsp+28h+arg_8]
0x18001cadf  add     rsp, 20h
0x18001cae3  pop     rdi
0x18001cae4  retn
```
