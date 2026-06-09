# CString::CString(void)

- ea: `0x180019dd0`
- end: `0x180019e32`
- name: `??0CString@@QEAA@XZ`
- size: `98`
- prototype: `CString *__fastcall(CString *__hidden this)`
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x18000729c`
- `0x180008c30`
- `0x18000b090`
- `0x18000c8c4`
- `0x18000fc54`
- `0x1800113c0`
- `0x180011500`
- `0x18001230c`
- `0x18001270c`
- `0x180012b10`
- `0x18001387c`
- `0x180013b8c`
- `0x180013d44`
- `0x180014220`
- `0x180014980`
- `0x180014ca8`
- `0x180014e68`
- `0x1800151c0`
- `0x180015380`
- `0x180016340`
- `0x180016470`
- `0x1800184c0`
- `0x1800190e4`
- `0x18001bec8`

## callees

- `0x180006ec0`
- `0x180019dd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CString *__fastcall CString::CString(CString *this)
{
  char *v2; // rbx
  _WORD *v3; // rax

  *(_QWORD *)this = &CString::`vftable';
  v2 = (char *)operator new(0x18u);
  if ( v2 )
  {
    v3 = operator new(2u);
    *(_QWORD *)v2 = v3;
    *((_DWORD *)v2 + 2) = 1;
    *(_QWORD *)(v2 + 12) = 1;
    *v3 = 0;
  }
  else
  {
    v2 = 0;
  }
  *((_QWORD *)this + 1) = v2;
  return this;
}

```

## disassembly

```asm
0x180019dd0  mov     [rsp+arg_8], rbx
0x180019dd5  push    rdi
0x180019dd6  sub     rsp, 20h
0x180019dda  mov     rdi, rcx
0x180019ddd  lea     rax, ??_7CString@@6B@; const CString::`vftable'
0x180019de4  mov     [rcx], rax
0x180019de7  mov     ecx, 18h; uBytes
0x180019dec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019df1  mov     rbx, rax
0x180019df4  mov     [rsp+28h+arg_0], rax
0x180019df9  test    rax, rax
0x180019dfc  jz      short loc_180019E1E
0x180019dfe  mov     ecx, 2; uBytes
0x180019e03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019e08  mov     [rbx], rax
0x180019e0b  mov     ecx, 1
0x180019e10  mov     [rbx+8], ecx
0x180019e13  mov     [rbx+0Ch], rcx
0x180019e17  xor     ecx, ecx
0x180019e19  mov     [rax], cx
0x180019e1c  jmp     short loc_180019E20
0x180019e1e  xor     ebx, ebx
0x180019e20  mov     [rdi+8], rbx
0x180019e24  mov     rax, rdi
0x180019e27  mov     rbx, [rsp+28h+arg_8]
0x180019e2c  add     rsp, 20h
0x180019e30  pop     rdi
0x180019e31  retn
```
