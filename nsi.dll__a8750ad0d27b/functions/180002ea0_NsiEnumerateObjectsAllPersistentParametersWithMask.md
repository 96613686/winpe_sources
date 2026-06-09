# NsiEnumerateObjectsAllPersistentParametersWithMask

- ea: `0x180002ea0`
- end: `0x180002f4b`
- name: `NsiEnumerateObjectsAllPersistentParametersWithMask`
- size: `171`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD BytesReturned, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002bd0`

## callees

- `0x1800013b0`
- `0x1800030e1`

## pseudocode

```c
DWORD __fastcall NsiEnumerateObjectsAllPersistentParametersWithMask(
        int a1,
        __int64 a2,
        int a3,
        __int64 a4,
        DWORD BytesReturned,
        __int64 a6,
        __int64 a7,
        int a8,
        _DWORD *a9)
{
  _DWORD *v13; // rbx
  DWORD result; // eax
  _BYTE InBuffer[8]; // [rsp+30h] [rbp-51h] BYREF
  int v16; // [rsp+38h] [rbp-49h]
  __int64 v17; // [rsp+40h] [rbp-41h]
  int v18; // [rsp+48h] [rbp-39h]
  int v19; // [rsp+50h] [rbp-31h]
  __int64 v20; // [rsp+58h] [rbp-29h]
  DWORD v21; // [rsp+60h] [rbp-21h]
  __int64 v22; // [rsp+68h] [rbp-19h]
  __int64 v23; // [rsp+70h] [rbp-11h]
  int v24; // [rsp+78h] [rbp-9h]
  int v25; // [rsp+80h] [rbp-1h]

  memset_0(InBuffer, 0, 0x58u);
  v19 = a1;
  v13 = a9;
  v16 = 0;
  v17 = a2;
  v25 = *a9;
  v21 = BytesReturned;
  v23 = a7;
  v22 = a6;
  v24 = a8;
  v18 = a3;
  v20 = a4;
  BytesReturned = 88;
  result = NsiIoctl(0x120047u, InBuffer, 0x58u, InBuffer, &BytesReturned, 0);
  *v13 = v25;
  return result;
}

```

## disassembly

```asm
0x180002ea0  push    rbp
0x180002ea2  push    rbx
0x180002ea3  push    rsi
0x180002ea4  push    rdi
0x180002ea5  push    r14
0x180002ea7  lea     rbp, [rsp-0Fh]
0x180002eac  sub     rsp, 90h
0x180002eb3  mov     rdi, rdx
0x180002eb6  mov     esi, r8d
0x180002eb9  xor     edx, edx; Val
0x180002ebb  mov     ebx, ecx
0x180002ebd  lea     rcx, [rbp+2Fh+InBuffer]; void *
0x180002ec1  mov     r14, r9
0x180002ec4  lea     r8d, [rdx+58h]; Size
0x180002ec8  call    memset_0
0x180002ecd  mov     [rbp+2Fh+var_60], ebx
0x180002ed0  lea     r9, [rbp+2Fh+InBuffer]; lpOutBuffer
0x180002ed4  mov     rbx, [rbp+2Fh+arg_40]
0x180002ed8  lea     rdx, [rbp+2Fh+InBuffer]; lpInBuffer
0x180002edc  mov     [rsp+0B0h+lpOverlapped], 0; lpOverlapped
0x180002ee5  mov     r8d, 58h ; 'X'; nInBufferSize
0x180002eeb  mov     ecx, 120047h; dwIoControlCode
0x180002ef0  mov     [rbp+2Fh+var_78], 0
0x180002ef7  mov     [rbp+2Fh+var_70], rdi
0x180002efb  mov     eax, [rbx]
0x180002efd  mov     [rbp+2Fh+var_30], eax
0x180002f00  mov     eax, [rbp+2Fh+BytesReturned]
0x180002f03  mov     [rbp+2Fh+var_50], eax
0x180002f06  mov     rax, [rbp+2Fh+arg_30]
0x180002f0a  mov     [rbp+2Fh+var_40], rax
0x180002f0e  mov     rax, [rbp+2Fh+arg_28]
0x180002f12  mov     [rbp+2Fh+var_48], rax
0x180002f16  mov     eax, [rbp+2Fh+arg_38]
0x180002f19  mov     [rbp+2Fh+var_38], eax
0x180002f1c  lea     rax, [rbp+2Fh+BytesReturned]
0x180002f20  mov     [rsp+0B0h+lpBytesReturned], rax; lpBytesReturned
0x180002f25  mov     [rbp+2Fh+var_68], esi
0x180002f28  mov     [rbp+2Fh+var_58], r14
0x180002f2c  mov     [rbp+2Fh+BytesReturned], 58h ; 'X'
0x180002f33  call    NsiIoctl
0x180002f38  mov     ecx, [rbp+2Fh+var_30]
0x180002f3b  mov     [rbx], ecx
0x180002f3d  add     rsp, 90h
0x180002f44  pop     r14
0x180002f46  pop     rdi
0x180002f47  pop     rsi
0x180002f48  pop     rbx
0x180002f49  pop     rbp
0x180002f4a  retn
```
