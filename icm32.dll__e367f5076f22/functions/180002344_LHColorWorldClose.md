# LHColorWorldClose

- ea: `0x180002344`
- end: `0x1800023c2`
- name: `LHColorWorldClose`
- size: `126`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002290`
- `0x180006770`
- `0x180006964`
- `0x18001d680`
- `0x18001d7a0`

## callees

- `0x180002344`
- `0x1800042e0`

## pseudocode

```c
__int64 __fastcall LHColorWorldClose(void **a1)
{
  if ( a1 )
  {
    DisposeIfPtr(a1[2]);
    DisposeIfPtr(a1[3]);
    DisposeIfPtr(a1[5]);
    DisposeIfPtr(a1[8]);
    DisposeIfPtr(a1[20]);
    DisposeIfPtr(a1[21]);
    DisposeIfPtr(a1[23]);
    DisposeIfPtr(a1[26]);
    DisposeIfPtr(a1[43]);
    DisposeIfPtr(a1);
  }
  return 0;
}

```

## disassembly

```asm
0x180002344  push    rbx
0x180002346  sub     rsp, 20h
0x18000234a  mov     rbx, rcx
0x18000234d  test    rcx, rcx
0x180002350  jz      short loc_1800023BA
0x180002352  mov     rcx, [rcx+10h]
0x180002356  call    DisposeIfPtr
0x18000235b  mov     rcx, [rbx+18h]
0x18000235f  call    DisposeIfPtr
0x180002364  mov     rcx, [rbx+28h]
0x180002368  call    DisposeIfPtr
0x18000236d  mov     rcx, [rbx+40h]
0x180002371  call    DisposeIfPtr
0x180002376  mov     rcx, [rbx+0A0h]
0x18000237d  call    DisposeIfPtr
0x180002382  mov     rcx, [rbx+0A8h]
0x180002389  call    DisposeIfPtr
0x18000238e  mov     rcx, [rbx+0B8h]
0x180002395  call    DisposeIfPtr
0x18000239a  mov     rcx, [rbx+0D0h]
0x1800023a1  call    DisposeIfPtr
0x1800023a6  mov     rcx, [rbx+158h]
0x1800023ad  call    DisposeIfPtr
0x1800023b2  mov     rcx, rbx
0x1800023b5  call    DisposeIfPtr
0x1800023ba  xor     eax, eax
0x1800023bc  add     rsp, 20h
0x1800023c0  pop     rbx
0x1800023c1  retn
```
