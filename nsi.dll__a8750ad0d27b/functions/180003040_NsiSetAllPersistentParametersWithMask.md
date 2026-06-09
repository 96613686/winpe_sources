# NsiSetAllPersistentParametersWithMask

- ea: `0x180003040`
- end: `0x1800030db`
- name: `NsiSetAllPersistentParametersWithMask`
- size: `155`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD BytesReturned, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800013b0`
- `0x1800030e1`

## pseudocode

```c
DWORD __fastcall NsiSetAllPersistentParametersWithMask(
        int a1,
        __int64 a2,
        int a3,
        __int64 a4,
        DWORD BytesReturned,
        __int64 a6,
        __int64 a7,
        int a8)
{
  _BYTE InBuffer[8]; // [rsp+30h] [rbp-50h] BYREF
  int v14; // [rsp+38h] [rbp-48h]
  __int64 v15; // [rsp+40h] [rbp-40h]
  int v16; // [rsp+48h] [rbp-38h]
  int v17; // [rsp+50h] [rbp-30h]
  __int64 v18; // [rsp+58h] [rbp-28h]
  DWORD v19; // [rsp+60h] [rbp-20h]
  __int64 v20; // [rsp+68h] [rbp-18h]
  __int64 v21; // [rsp+70h] [rbp-10h]
  int v22; // [rsp+78h] [rbp-8h]

  memset_0(InBuffer, 0, 0x50u);
  v19 = BytesReturned;
  v21 = a7;
  v20 = a6;
  v22 = a8;
  v17 = a1;
  v14 = 0;
  v15 = a2;
  v16 = a3;
  v18 = a4;
  BytesReturned = 80;
  return NsiIoctl(0x12004Fu, InBuffer, 0x50u, InBuffer, &BytesReturned, 0);
}

```

## disassembly

```asm
0x180003040  push    rbp
0x180003042  push    rbx
0x180003043  push    rsi
0x180003044  push    rdi
0x180003045  push    r14
0x180003047  mov     rbp, rsp
0x18000304a  sub     rsp, 80h
0x180003051  mov     rdi, rdx
0x180003054  mov     esi, r8d
0x180003057  xor     edx, edx; Val
0x180003059  mov     ebx, ecx
0x18000305b  lea     rcx, [rbp+InBuffer]; void *
0x18000305f  mov     r14, r9
0x180003062  lea     r8d, [rdx+50h]; Size
0x180003066  call    memset_0
0x18000306b  mov     eax, [rbp+BytesReturned]
0x18000306e  lea     r9, [rbp+InBuffer]; lpOutBuffer
0x180003072  mov     [rbp+var_20], eax
0x180003075  lea     rdx, [rbp+InBuffer]; lpInBuffer
0x180003079  mov     rax, [rbp+arg_30]
0x18000307d  mov     r8d, 50h ; 'P'; nInBufferSize
0x180003083  mov     [rbp+var_10], rax
0x180003087  mov     ecx, 12004Fh; dwIoControlCode
0x18000308c  mov     rax, [rbp+arg_28]
0x180003090  mov     [rbp+var_18], rax
0x180003094  mov     eax, [rbp+arg_38]
0x180003097  mov     [rbp+var_8], eax
0x18000309a  lea     rax, [rbp+BytesReturned]
0x18000309e  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x1800030a7  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x1800030ac  mov     [rbp+var_30], ebx
0x1800030af  mov     [rbp+var_48], 0
0x1800030b6  mov     [rbp+var_40], rdi
0x1800030ba  mov     [rbp+var_38], esi
0x1800030bd  mov     [rbp+var_28], r14
0x1800030c1  mov     [rbp+BytesReturned], 50h ; 'P'
0x1800030c8  call    NsiIoctl
0x1800030cd  add     rsp, 80h
0x1800030d4  pop     r14
0x1800030d6  pop     rdi
0x1800030d7  pop     rsi
0x1800030d8  pop     rbx
0x1800030d9  pop     rbp
0x1800030da  retn
```
