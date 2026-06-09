# FatReadEaSet

- ea: `0x140036a6c`
- end: `0x140036c71`
- name: `FatReadEaSet`
- size: `517`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16, __int64, int, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140036394`
- `0x1400364fc`
- `0x14003abc8`

## callees

- `0x14000c680`
- `0x14003685c`
- `0x140036a6c`
- `0x140036c78`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140036b89`
- `ntoskrnl!ExRaiseStatus` at `0x140036c4d`
- `ntoskrnl!ExRaiseStatus` at `0x140036c64`
- `ntoskrnl!ExRaiseStatus` at `0x140036b89`
- `ntoskrnl!ExRaiseStatus` at `0x140036c4d`
- `ntoskrnl!ExRaiseStatus` at `0x140036c64`

## pseudocode

```c
__int64 __fastcall FatReadEaSet(__int64 a1, __int64 a2, unsigned __int16 a3, __int64 a4, int a5, __int64 a6)
{
  unsigned int v6; // esi
  int v9; // r15d
  __int64 v10; // rcx
  int v11; // ebx
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rcx
  SIZE_T NumberOfBytes; // [rsp+28h] [rbp-100h]
  SIZE_T NumberOfBytesb; // [rsp+28h] [rbp-100h]
  SIZE_T NumberOfBytesa; // [rsp+28h] [rbp-100h]
  int v19[24]; // [rsp+40h] [rbp-E8h] BYREF
  int v20[24]; // [rsp+A0h] [rbp-88h] BYREF
  __int64 v21; // [rsp+148h] [rbp+20h]

  v6 = a3;
  if ( (unsigned __int16)(a3 - 1) > 0x77FEu )
  {
    *(_DWORD *)(a1 + 72) = -1073741743;
    ExRaiseStatus(-1073741743);
  }
  v9 = 1 << *(_BYTE *)(a2 + 378);
  memset(v19, 0, sizeof(v19));
  memset(v20, 0, sizeof(v20));
  LODWORD(NumberOfBytes) = 512;
  FatPinEaRange(
    a1,
    *(struct _FILE_OBJECT **)(a2 + 776),
    *(_QWORD *)(a2 + 784),
    (__int64)v19,
    0,
    NumberOfBytes,
    -1073741743);
  v21 = *(_QWORD *)v19;
  LODWORD(NumberOfBytesb) = 256;
  FatPinEaRange(
    a1,
    *(struct _FILE_OBJECT **)(a2 + 776),
    *(_QWORD *)(a2 + 784),
    (__int64)v20,
    ((2 * v6) & 0xFFFFFF00) + 512,
    NumberOfBytesb,
    -1073741743);
  v10 = *(unsigned __int16 *)(*(_QWORD *)v20 + 2LL * (v6 & 0x7F));
  if ( (_WORD)v10 == 0xFFFF )
  {
    *(_DWORD *)(a1 + 72) = -1073741743;
    ExRaiseStatus(-1073741743);
  }
  v11 = v10 + *(unsigned __int16 *)(v21 + 2 * ((unsigned __int64)v6 >> 7) + 32);
  LOBYTE(v10) = *(_BYTE *)(a2 + 378);
  v12 = v11 << v10;
  FatUnpinEaRange(v10, v19);
  FatUnpinEaRange(v13, v20);
  LODWORD(NumberOfBytesa) = v9;
  FatPinEaRange(a1, *(struct _FILE_OBJECT **)(a2 + 776), *(_QWORD *)(a2 + 784), a6, v12, NumberOfBytesa, -1073741762);
  if ( **(_WORD **)a6 != 16709 || *(_WORD *)(*(_QWORD *)a6 + 2LL) != (_WORD)v6 )
  {
    *(_DWORD *)(a1 + 72) = -1073741762;
    ExRaiseStatus(-1073741762);
  }
  FatUnpinEaRange(16709, v19);
  return FatUnpinEaRange(v14, v20);
}

```

## disassembly

```asm
0x140036a6c  mov     [rsp+arg_0], rbx
0x140036a71  mov     [rsp+arg_8], rsi
0x140036a76  mov     [rsp+arg_18], r9
0x140036a7b  push    rdi
0x140036a7c  push    r12
0x140036a7e  push    r13
0x140036a80  push    r14
0x140036a82  push    r15
0x140036a84  sub     rsp, 100h
0x140036a8b  movzx   esi, r8w
0x140036a8f  mov     r14, rdx
0x140036a92  mov     rdi, rcx
0x140036a95  movzx   eax, si
0x140036a98  mov     r15d, 1
0x140036a9e  sub     ax, r15w
0x140036aa2  mov     ecx, 77FEh
0x140036aa7  cmp     ax, cx
0x140036aaa  ja      loc_140036C5A
0x140036ab0  mov     cl, [rdx+17Ah]
0x140036ab6  shl     r15d, cl
0x140036ab9  mov     r13d, esi
0x140036abc  lea     r12, ds:0[rsi*2]
0x140036ac4  and     r12d, 0FFFFFF00h
0x140036acb  add     r12d, 200h
0x140036ad2  mov     ebx, 60h ; '`'
0x140036ad7  mov     r8d, ebx; Size
0x140036ada  xor     edx, edx; Val
0x140036adc  lea     rcx, [rsp+128h+var_E8]; void *
0x140036ae1  call    memset
0x140036ae6  mov     r8d, ebx; Size
0x140036ae9  xor     edx, edx; Val
0x140036aeb  lea     rcx, [rsp+128h+var_88]; void *
0x140036af3  call    memset
0x140036af8  nop
0x140036af9  mov     ebx, 0C0000051h
0x140036afe  mov     [rsp+128h+Status], ebx; Status
0x140036b02  mov     dword ptr [rsp+128h+NumberOfBytes], 200h; NumberOfBytes
0x140036b0a  mov     [rsp+128h+var_108], 0; int
0x140036b12  lea     r9, [rsp+128h+var_E8]; int
0x140036b17  mov     r8, [r14+310h]; int
0x140036b1e  mov     rdx, [r14+308h]; int
0x140036b25  mov     rcx, rdi; int
0x140036b28  call    FatPinEaRange
0x140036b2d  mov     rax, qword ptr [rsp+128h+var_E8]
0x140036b32  mov     [rsp+128h+arg_18], rax
0x140036b3a  mov     [rsp+128h+Status], ebx; Status
0x140036b3e  mov     dword ptr [rsp+128h+NumberOfBytes], 100h; NumberOfBytes
0x140036b46  mov     [rsp+128h+var_108], r12d; int
0x140036b4b  lea     r9, [rsp+128h+var_88]; int
0x140036b53  mov     r8, [r14+310h]; int
0x140036b5a  mov     rdx, [r14+308h]; int
0x140036b61  mov     rcx, rdi; int
0x140036b64  call    FatPinEaRange
0x140036b69  mov     edx, esi
0x140036b6b  and     edx, 7Fh
0x140036b6e  mov     rax, qword ptr [rsp+128h+var_88]
0x140036b76  movzx   ecx, word ptr [rax+rdx*2]
0x140036b7a  mov     eax, 0FFFFh
0x140036b7f  cmp     cx, ax
0x140036b82  jnz     short loc_140036B95
0x140036b84  mov     [rdi+48h], ebx
0x140036b87  mov     ecx, ebx; Status
0x140036b89  call    cs:__imp_ExRaiseStatus
0x140036b95  shr     r13, 7
0x140036b99  mov     rax, [rsp+128h+arg_18]
0x140036ba1  movzx   ebx, word ptr [rax+r13*2+20h]
0x140036ba7  add     ebx, ecx
0x140036ba9  mov     cl, [r14+17Ah]
0x140036bb0  shl     ebx, cl
0x140036bb2  lea     rdx, [rsp+128h+var_E8]
0x140036bb7  call    FatUnpinEaRange
0x140036bbc  lea     rdx, [rsp+128h+var_88]
0x140036bc4  call    FatUnpinEaRange
0x140036bc9  mov     r12d, 0C000003Eh
0x140036bcf  mov     [rsp+128h+Status], r12d; Status
0x140036bd4  mov     dword ptr [rsp+128h+NumberOfBytes], r15d; NumberOfBytes
0x140036bd9  mov     [rsp+128h+var_108], ebx; int
0x140036bdd  mov     rbx, qword ptr [rsp+128h+arg_28]
0x140036be5  mov     r9, rbx; int
0x140036be8  mov     r8, [r14+310h]; int
0x140036bef  mov     rdx, [r14+308h]; int
0x140036bf6  mov     rcx, rdi; int
0x140036bf9  call    FatPinEaRange
0x140036bfe  mov     rax, [rbx]
0x140036c01  mov     ecx, 4145h
0x140036c06  cmp     [rax], cx
0x140036c09  jnz     short loc_140036C46
0x140036c0b  cmp     [rax+2], si
0x140036c0f  jnz     short loc_140036C46
0x140036c11  lea     rdx, [rsp+128h+var_E8]
0x140036c16  call    FatUnpinEaRange
0x140036c1b  lea     rdx, [rsp+128h+var_88]
0x140036c23  call    FatUnpinEaRange
0x140036c28  lea     r11, [rsp+128h+var_28]
0x140036c30  mov     rbx, [r11+30h]
0x140036c34  mov     rsi, [r11+38h]
0x140036c38  mov     rsp, r11
0x140036c3b  pop     r15
0x140036c3d  pop     r14
0x140036c3f  pop     r13
0x140036c41  pop     r12
0x140036c43  pop     rdi
0x140036c44  retn
0x140036c46  mov     [rdi+48h], r12d
0x140036c4a  mov     ecx, r12d; Status
0x140036c4d  call    cs:__imp_ExRaiseStatus
0x140036c5a  mov     ebx, 0C0000051h
0x140036c5f  mov     [rdi+48h], ebx
0x140036c62  mov     ecx, ebx; Status
0x140036c64  call    cs:__imp_ExRaiseStatus
0x14005da68  push    rbp
0x14005da6a  sub     rsp, 40h
0x14005da6e  mov     rbp, rdx
0x14005da71  lea     rdx, [rbp+40h]
0x14005da75  call    FatUnpinEaRange
0x14005da7a  lea     rdx, [rbp+0A0h]
0x14005da81  call    FatUnpinEaRange
0x14005da86  nop
0x14005da87  add     rsp, 40h
0x14005da8b  pop     rbp
0x14005da8c  retn
```
