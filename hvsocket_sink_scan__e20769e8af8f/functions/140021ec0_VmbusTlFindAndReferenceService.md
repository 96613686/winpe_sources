# VmbusTlFindAndReferenceService

- ea: `0x140021ec0`
- end: `0x140021f55`
- name: `VmbusTlFindAndReferenceService`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140004f2c`
- `0x14000695c`
- `0x14001daa0`
- `0x14001dcf8`
- `0x14001e1c0`
- `0x14001e5ac`
- `0x14001f5e4`
- `0x140022634`

## callees

- `0x14000a048`
- `0x14000c0a0`
- `0x140021ec0`

## string_xrefs

- `0x140021f2c`: `VmbusTlFindAndReferenceService`

## pseudocode

```c
_QWORD *__fastcall VmbusTlFindAndReferenceService(__int64 a1, const void *a2)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rdi
  _QWORD *v5; // rbx

  v2 = (_QWORD *)(a1 + 360);
  for ( i = *(_QWORD **)(a1 + 360); ; i = (_QWORD *)*i )
  {
    if ( i == v2 )
      return 0;
    v5 = i - 12;
    if ( !memcmp(i + 2, a2, 0x10u) )
      break;
  }
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlFindAndReferenceService",
      457,
      (_DWORD)i - 96,
      v5[1],
      (__int64)"Reference object");
  if ( _InterlockedIncrement64(v5 + 1) <= 1 )
    __fastfail(0xEu);
  return v5;
}

```

## disassembly

```asm
0x140021ec0  push    rbx
0x140021ec2  push    rbp
0x140021ec3  push    rsi
0x140021ec4  push    rdi
0x140021ec5  sub     rsp, 38h
0x140021ec9  lea     rsi, [rcx+168h]
0x140021ed0  mov     rbp, rdx
0x140021ed3  mov     rdi, [rsi]
0x140021ed6  jmp     short loc_140021EF5
0x140021ed8  lea     rbx, [rdi-60h]
0x140021edc  mov     r8d, 10h; Size
0x140021ee2  lea     rcx, [rbx+70h]; Buf1
0x140021ee6  mov     rdx, rbp; Buf2
0x140021ee9  call    memcmp
0x140021eee  test    eax, eax
0x140021ef0  jz      short loc_140021F09
0x140021ef2  mov     rdi, [rdi]
0x140021ef5  cmp     rdi, rsi
0x140021ef8  jnz     short loc_140021ED8
0x140021efa  xor     ebx, ebx
0x140021efc  mov     rax, rbx
0x140021eff  add     rsp, 38h
0x140021f03  pop     rdi
0x140021f04  pop     rsi
0x140021f05  pop     rbp
0x140021f06  pop     rbx
0x140021f07  retn
0x140021f09  mov     eax, cs:dword_140013058
0x140021f0f  cmp     eax, 5
0x140021f12  jbe     short loc_140021F38
0x140021f14  mov     r9, [rbx+8]
0x140021f18  lea     rax, aReferenceObjec; "Reference object"
0x140021f1f  mov     r8, rbx
0x140021f22  mov     [rsp+58h+var_38], rax
0x140021f27  mov     edx, 1C9h
0x140021f2c  lea     rcx, aVmbustlfindand_4; "VmbusTlFindAndReferenceService"
0x140021f33  call    HvsocketTraceReferenceCount
0x140021f38  mov     eax, 1
0x140021f3d  lock xadd [rbx+8], rax
0x140021f43  inc     rax
0x140021f46  cmp     rax, 1
0x140021f4a  jg      short loc_140021EFC
0x140021f4c  mov     ecx, 0Eh
0x140021f51  int     29h; Win8: RtlFailFast(ecx)
0x140021f53  jmp     short loc_140021EFC
```
