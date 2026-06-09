# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400086f8`
- end: `0x140008760`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `104`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140003ffc`
- `0x140004ca8`
- `0x14000953c`

## callees

- `0x1400086f8`
- `0x14000894c`
- `0x1400089a4`

## pseudocode

```c
int __fastcall StringCchCatW(unsigned __int16 *a1, size_t a2, const unsigned __int16 *a3)
{
  int result; // eax
  size_t *v6; // r8
  __int64 v7; // r11
  size_t pcchLength; // [rsp+48h] [rbp+10h] BYREF

  pcchLength = 0;
  if ( a2 - 1 > 0x7FFFFFFE )
    return -2147024809;
  result = StringLengthWorkerW(a1, a2, &pcchLength);
  if ( result >= 0 )
    return StringCopyWorkerW(&a1[pcchLength], v7 - pcchLength, v6, a3, 0x7FFFFFFEu);
  return result;
}

```

## disassembly

```asm
0x1400086f8  mov     [rsp+arg_0], rbx
0x1400086fd  push    rdi
0x1400086fe  sub     rsp, 30h
0x140008702  lea     rax, [rdx-1]
0x140008706  mov     [rsp+38h+pcchLength], 0
0x14000870f  mov     rdi, r8
0x140008712  mov     r11, rdx
0x140008715  mov     rbx, rcx
0x140008718  cmp     rax, 7FFFFFFEh
0x14000871e  ja      short loc_140008750
0x140008720  lea     r8, [rsp+38h+pcchLength]; pcchLength
0x140008725  call    StringLengthWorkerW
0x14000872a  test    eax, eax
0x14000872c  js      short loc_140008755
0x14000872e  mov     rax, [rsp+38h+pcchLength]
0x140008733  mov     r9, rdi; pszSrc
0x140008736  sub     r11, rax
0x140008739  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x140008742  mov     rdx, r11; cchDest
0x140008745  lea     rcx, [rbx+rax*2]; pszDest
0x140008749  call    StringCopyWorkerW
0x14000874e  jmp     short loc_140008755
0x140008750  mov     eax, 80070057h
0x140008755  mov     rbx, [rsp+38h+arg_0]
0x14000875a  add     rsp, 30h
0x14000875e  pop     rdi
0x14000875f  retn
```
