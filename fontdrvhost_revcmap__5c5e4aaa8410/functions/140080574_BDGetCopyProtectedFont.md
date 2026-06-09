# BDGetCopyProtectedFont

- ea: `0x140080574`
- end: `0x1400805de`
- name: `BDGetCopyProtectedFont`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14007da08`

## callees

- `0x1400392ac`
- `0x140076ef6`
- `0x140080574`

## pseudocode

```c
__int64 __fastcall BDGetCopyProtectedFont(__int64 a1)
{
  __int64 result; // rax
  _QWORD *v3; // rbx
  _QWORD *v4; // [rsp+38h] [rbp+10h] BYREF

  result = 4294967073LL;
  if ( *(_DWORD *)a1 <= 1u )
  {
    v3 = waitingList;
    if ( waitingList )
    {
      memmove_0((void *)(a1 + 8), waitingList, 0x460u);
      *(_QWORD *)(a1 + 1120) = 0;
      v4 = v3;
      waitingList = (void *)v3[139];
      EnhancedFree(&v4);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140080574  mov     [rsp+arg_0], rbx
0x140080579  push    rdi
0x14008057a  sub     rsp, 20h
0x14008057e  mov     rdi, rcx
0x140080581  mov     eax, 0FFFFFF21h
0x140080586  cmp     dword ptr [rcx], 1
0x140080589  ja      short loc_1400805D3
0x14008058b  mov     rbx, cs:waitingList
0x140080592  test    rbx, rbx
0x140080595  jz      short loc_1400805D3
0x140080597  add     rcx, 8; void *
0x14008059b  mov     r8d, 460h; Size
0x1400805a1  mov     rdx, rbx; Src
0x1400805a4  call    memmove_0
0x1400805a9  mov     qword ptr [rdi+460h], 0
0x1400805b4  mov     [rsp+28h+arg_8], rbx
0x1400805b9  mov     rax, [rbx+458h]
0x1400805c0  mov     cs:waitingList, rax
0x1400805c7  lea     rcx, [rsp+28h+arg_8]
0x1400805cc  call    EnhancedFree
0x1400805d1  xor     eax, eax
0x1400805d3  mov     rbx, [rsp+28h+arg_0]
0x1400805d8  add     rsp, 20h
0x1400805dc  pop     rdi
0x1400805dd  retn
0x140097687  push    rbp
0x140097689  sub     rsp, 20h
0x14009768d  mov     rbp, rdx
0x140097690  add     rsp, 20h
0x140097694  pop     rbp
0x140097695  retn
```
