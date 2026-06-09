# StdEncoderReset

- ea: `0x180006758`
- end: `0x180006801`
- name: `StdEncoderReset`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003710`

## callees

- `0x180003930`
- `0x180006ad5`

## pseudocode

```c
void *__fastcall StdEncoderReset(__int64 a1)
{
  __int64 v1; // rdi
  void *result; // rax

  v1 = *(_QWORD *)(a1 + 80);
  memset_0((void *)(v1 + 131850), 0, 0x4000u);
  *(_DWORD *)(a1 + 72) = 0x8000;
  *(_DWORD *)(a1 + 32) = 0x8000;
  *(_DWORD *)(a1 + 36) = 0x8000;
  *(_QWORD *)(v1 + 181004) = 0;
  *(_QWORD *)(v1 + 181016) = v1 + 148234;
  DeflateInitRecordingTables(v1 + 192384, (_WORD *)(v1 + 192672), v1 + 181792, (_WORD *)(v1 + 181824));
  memset_0((void *)(v1 + 193248), 0, 0x480u);
  result = memset_0((void *)(v1 + 195264), 0, 0x80u);
  *(_WORD *)(v1 + 193760) = 1;
  return result;
}

```

## disassembly

```asm
0x180006758  mov     [rsp+arg_0], rbx
0x18000675d  push    rdi
0x18000675e  sub     rsp, 20h
0x180006762  mov     rdi, [rcx+50h]
0x180006766  mov     rbx, rcx
0x180006769  xor     edx, edx; Val
0x18000676b  mov     r8d, 4000h; Size
0x180006771  lea     rcx, [rdi+2030Ah]; void *
0x180006778  call    memset_0
0x18000677d  mov     eax, 8000h
0x180006782  lea     r9, [rdi+2C640h]
0x180006789  mov     [rbx+48h], eax
0x18000678c  lea     r8, [rdi+2C620h]
0x180006793  mov     [rbx+20h], eax
0x180006796  lea     rdx, [rdi+2F0A0h]
0x18000679d  mov     [rbx+24h], eax
0x1800067a0  lea     rcx, [rdi+2EF80h]
0x1800067a7  lea     rax, [rdi+2430Ah]
0x1800067ae  mov     qword ptr [rdi+2C30Ch], 0
0x1800067b9  mov     [rdi+2C318h], rax
0x1800067c0  call    DeflateInitRecordingTables
0x1800067c5  lea     rcx, [rdi+2F2E0h]; void *
0x1800067cc  xor     edx, edx; Val
0x1800067ce  mov     r8d, 480h; Size
0x1800067d4  call    memset_0
0x1800067d9  lea     rcx, [rdi+2FAC0h]; void *
0x1800067e0  xor     edx, edx; Val
0x1800067e2  mov     r8d, 80h; Size
0x1800067e8  call    memset_0
0x1800067ed  mov     rbx, [rsp+28h+arg_0]
0x1800067f2  mov     word ptr [rdi+2F4E0h], 1
0x1800067fb  add     rsp, 20h
0x1800067ff  pop     rdi
0x180006800  retn
```
