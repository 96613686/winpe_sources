# WTL::CString::AssignCopy(int,ushort const *)

- ea: `0x180013b2c`
- end: `0x180013b84`
- name: `?AssignCopy@CString@WTL@@IEAAXHPEBG@Z`
- size: `88`
- prototype: `void(WTL::CString *__hidden this, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800134d8`
- `0x180013544`

## callees

- `0x180005980`
- `0x180013a30`
- `0x180013b2c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013b5f`
- `msvcrt!memcpy_s` at `0x180013b5f`

## pseudocode

```c
void __fastcall WTL::CString::AssignCopy(void **this, int a2, const unsigned __int16 *a3)
{
  __int64 v3; // rdi
  errno_t v6; // eax

  v3 = a2;
  if ( (unsigned int)WTL::CString::AllocBeforeWrite((WTL::CString *)this, a2) )
  {
    v6 = memcpy_s(*this, 2LL * ((int)v3 + 1), a3, 2 * v3);
    ATL::AtlCrtErrorCheck(v6);
    *((_DWORD *)*this - 2) = v3;
    *((_WORD *)*this + v3) = 0;
  }
}

```

## disassembly

```asm
0x180013b2c  push    rbx
0x180013b2e  push    rbp
0x180013b2f  push    rsi
0x180013b30  push    rdi
0x180013b31  sub     rsp, 28h
0x180013b35  movsxd  rdi, edx
0x180013b38  mov     rbp, r8
0x180013b3b  mov     edx, edi; int
0x180013b3d  mov     rsi, rcx
0x180013b40  call    ?AllocBeforeWrite@CString@WTL@@IEAAHH@Z; WTL::CString::AllocBeforeWrite(int)
0x180013b45  test    eax, eax
0x180013b47  jz      short loc_180013B7B
0x180013b49  mov     rcx, [rsi]; Destination
0x180013b4c  lea     eax, [rdi+1]
0x180013b4f  movsxd  rdx, eax
0x180013b52  lea     rbx, [rdi+rdi]
0x180013b56  add     rdx, rdx; DestinationSize
0x180013b59  mov     r9, rbx; SourceSize
0x180013b5c  mov     r8, rbp; Source
0x180013b5f  call    cs:__imp_memcpy_s
0x180013b65  mov     ecx, eax; int
0x180013b67  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180013b6c  mov     rax, [rsi]
0x180013b6f  mov     [rax-8], edi
0x180013b72  xor     eax, eax
0x180013b74  mov     rcx, [rsi]
0x180013b77  mov     [rbx+rcx], ax
0x180013b7b  add     rsp, 28h
0x180013b7f  pop     rdi
0x180013b80  pop     rsi
0x180013b81  pop     rbp
0x180013b82  pop     rbx
0x180013b83  retn
```
