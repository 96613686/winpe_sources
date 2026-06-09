# FveConfigSubscriberBaseInit

- ea: `0x1400847a0`
- end: `0x14008487b`
- name: `FveConfigSubscriberBaseInit`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140023040`
- `0x1400847a0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140084850`
- `ntoskrnl!ObfDereferenceObject` at `0x140084850`
- `ntoskrnl!ObfReferenceObject` at `0x1400847e0`
- `ntoskrnl!ObfReferenceObject` at `0x1400847e0`
- `ntoskrnl!ExInitializeResourceLite` at `0x14008481c`
- `ntoskrnl!ExInitializeResourceLite` at `0x14008481c`
- `ntoskrnl!ExDeleteResourceLite` at `0x14008483c`
- `ntoskrnl!ExDeleteResourceLite` at `0x14008483c`

## pseudocode

```c
__int64 __fastcall FveConfigSubscriberBaseInit(__int64 a1, int a2, __int64 a3, void *a4, __int64 a5, _QWORD *a6)
{
  __int64 v8; // rbp
  NTSTATUS v9; // esi

  v8 = a1 + 8 + 264LL * a2;
  memset(a6, 0, *(unsigned int *)(v8 + 132));
  if ( a4 )
    ObfReferenceObject(a4);
  *((_DWORD *)a6 + 10) = *(_DWORD *)(v8 + 132);
  a6[4] = a5;
  *((_DWORD *)a6 + 11) = 1;
  a6[2] = v8;
  a6[7] = a3;
  a6[3] = a4;
  a6[1] = a6;
  *a6 = a6;
  v9 = ExInitializeResourceLite((PERESOURCE)(a6 + 8));
  if ( v9 < 0 )
  {
    if ( a4 )
      ObfDereferenceObject(a4);
    memset(a6, 0, *(unsigned int *)(v8 + 132));
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400847a0  push    rbx
0x1400847a2  push    rbp
0x1400847a3  push    rsi
0x1400847a4  push    rdi
0x1400847a5  push    r14
0x1400847a7  sub     rsp, 20h
0x1400847ab  mov     rbx, [rsp+48h+arg_28]
0x1400847b0  add     rcx, 8
0x1400847b4  movsxd  rax, edx
0x1400847b7  mov     rsi, r8
0x1400847ba  imul    rbp, rax, 108h
0x1400847c1  xor     edx, edx; Val
0x1400847c3  mov     rdi, r9
0x1400847c6  add     rbp, rcx
0x1400847c9  mov     rcx, rbx; void *
0x1400847cc  mov     r8d, [rbp+84h]; Size
0x1400847d3  call    memset
0x1400847d8  test    rdi, rdi
0x1400847db  jz      short loc_1400847EC
0x1400847dd  mov     rcx, rdi; Object
0x1400847e0  call    cs:__imp_ObfReferenceObject
0x1400847e7  nop     dword ptr [rax+rax+00h]
0x1400847ec  mov     eax, [rbp+84h]
0x1400847f2  lea     rcx, [rbx+40h]; Resource
0x1400847f6  mov     [rbx+28h], eax
0x1400847f9  mov     rax, [rsp+48h+arg_20]
0x1400847fe  mov     [rbx+20h], rax
0x140084802  mov     dword ptr [rbx+2Ch], 1
0x140084809  mov     [rbx+10h], rbp
0x14008480d  mov     [rbx+38h], rsi
0x140084811  mov     [rbx+18h], rdi
0x140084815  mov     [rbx+8], rbx
0x140084819  mov     [rbx], rbx
0x14008481c  call    cs:__imp_ExInitializeResourceLite
0x140084823  nop     dword ptr [rax+rax+00h]
0x140084828  mov     esi, eax
0x14008482a  test    eax, eax
0x14008482c  jns     short loc_14008486D
0x14008482e  mov     edx, eax
0x140084830  shr     edx, 1Fh
0x140084833  xor     dl, 1
0x140084836  jz      short loc_140084848
0x140084838  lea     rcx, [rbx+40h]; Resource
0x14008483c  call    cs:__imp_ExDeleteResourceLite
0x140084843  nop     dword ptr [rax+rax+00h]
0x140084848  test    rdi, rdi
0x14008484b  jz      short loc_14008485C
0x14008484d  mov     rcx, rdi; Object
0x140084850  call    cs:__imp_ObfDereferenceObject
0x140084857  nop     dword ptr [rax+rax+00h]
0x14008485c  mov     r8d, [rbp+84h]; Size
0x140084863  xor     edx, edx; Val
0x140084865  mov     rcx, rbx; void *
0x140084868  call    memset
0x14008486d  mov     eax, esi
0x14008486f  add     rsp, 20h
0x140084873  pop     r14
0x140084875  pop     rdi
0x140084876  pop     rsi
0x140084877  pop     rbp
0x140084878  pop     rbx
0x140084879  retn
```
