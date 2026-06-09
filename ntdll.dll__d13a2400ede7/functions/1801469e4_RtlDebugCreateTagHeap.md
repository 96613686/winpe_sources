# RtlDebugCreateTagHeap

- ea: `0x1801469e4`
- end: `0x180146ad2`
- name: `RtlDebugCreateTagHeap`
- size: `238`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004e790`

## callees

- `0x180047480`
- `0x18004e790`
- `0x18006ffa0`
- `0x180070490`
- `0x1800b1fc0`
- `0x1800b2c9c`
- `0x1800b32d4`
- `0x1800ff0c8`
- `0x1801469e4`

## string_xrefs

- `0x180146a14`: `RtlCreateTagHeap`

## pseudocode

```c
__int64 __fastcall RtlDebugCreateTagHeap(_QWORD *Src, unsigned __int8 a2)
{
  char v4; // si
  unsigned int TagHeap; // r14d

  v4 = 0;
  TagHeap = 0;
  if ( (unsigned __int8)RtlpCheckHeapSignature(Src, "RtlCreateTagHeap") )
  {
    if ( ((*((_BYTE *)Src + 116) | a2) & 1) == 0 )
    {
      RtlEnterCriticalSection(Src[44]);
      v4 = 1;
    }
    if ( (unsigned __int8)RtlpValidateHeap(Src, 0) )
      TagHeap = RtlCreateTagHeap(Src);
    RtlpValidateHeapHeaders(Src);
  }
  if ( v4 )
    RtlLeaveCriticalSection(Src[44]);
  return TagHeap;
}

```

## disassembly

```asm
0x1801469e4  mov     rax, rsp
0x1801469e7  mov     [rax+18h], rbx
0x1801469eb  mov     [rax+8], rcx
0x1801469ef  push    rsi
0x1801469f0  push    rdi
0x1801469f1  push    r12
0x1801469f3  push    r14
0x1801469f5  push    r15
0x1801469f7  sub     rsp, 30h
0x1801469fb  mov     r15, r9
0x1801469fe  mov     r12, r8
0x180146a01  mov     edi, edx
0x180146a03  mov     rbx, rcx
0x180146a06  xor     sil, sil
0x180146a09  mov     [rax-38h], sil
0x180146a0d  xor     r14d, r14d
0x180146a10  mov     [rax-34h], r14d
0x180146a14  lea     rdx, aRtlcreatetaghe_0; "RtlCreateTagHeap"
0x180146a1b  call    RtlpCheckHeapSignature
0x180146a20  test    al, al
0x180146a22  jz      short loc_180146A81
0x180146a24  mov     eax, [rbx+74h]
0x180146a27  bts     eax, 1Ch
0x180146a2b  or      edi, eax
0x180146a2d  mov     [rsp+58h+arg_8], edi
0x180146a31  test    dil, 1
0x180146a35  jnz     short loc_180146A52
0x180146a37  mov     rcx, [rbx+160h]
0x180146a3e  call    RtlEnterCriticalSection
0x180146a43  mov     sil, 1
0x180146a46  mov     [rsp+58h+var_38], sil
0x180146a4b  or      edi, 1
0x180146a4e  mov     [rsp+58h+arg_8], edi
0x180146a52  xor     edx, edx
0x180146a54  mov     rcx, rbx
0x180146a57  call    RtlpValidateHeap
0x180146a5c  test    al, al
0x180146a5e  jz      short loc_180146A77
0x180146a60  mov     r9, r15
0x180146a63  mov     r8, r12
0x180146a66  mov     edx, edi
0x180146a68  mov     rcx, rbx
0x180146a6b  call    RtlCreateTagHeap
0x180146a70  mov     r14d, eax
0x180146a73  mov     [rsp+58h+var_34], eax
0x180146a77  mov     dl, 1
0x180146a79  mov     rcx, rbx; Src
0x180146a7c  call    RtlpValidateHeapHeaders
0x180146a81  jmp     short loc_180146AAB
0x180146a83  mov     rbx, gs:30h
0x180146a8c  mov     [rbx+1250h], eax
0x180146a92  mov     ecx, eax
0x180146a94  call    RtlNtStatusToDosErrorNoTeb
0x180146a99  mov     [rbx+68h], eax
0x180146a9c  mov     rbx, [rsp+58h+arg_0]
0x180146aa1  mov     sil, [rsp+58h+var_38]
0x180146aa6  mov     r14d, [rsp+58h+var_34]
0x180146aab  test    sil, sil
0x180146aae  jz      short loc_180146ABC
0x180146ab0  mov     rcx, [rbx+160h]
0x180146ab7  call    RtlLeaveCriticalSection
0x180146abc  mov     eax, r14d
0x180146abf  mov     rbx, [rsp+58h+arg_10]
0x180146ac4  add     rsp, 30h
0x180146ac8  pop     r15
0x180146aca  pop     r14
0x180146acc  pop     r12
0x180146ace  pop     rdi
0x180146acf  pop     rsi
0x180146ad0  retn
0x180168cf8  push    rbp
0x180168cfa  sub     rsp, 20h
0x180168cfe  mov     rbp, rdx
0x180168d01  mov     rdx, rcx
0x180168d04  mov     rcx, [rcx]
0x180168d07  mov     ecx, [rcx]
0x180168d09  call    RtlpHeapExceptionFilter
0x180168d0e  nop
0x180168d0f  add     rsp, 20h
0x180168d13  pop     rbp
0x180168d14  retn
0x180168d16  push    rbp
0x180168d18  sub     rsp, 20h
0x180168d1c  mov     rbp, rdx
0x180168d1f  cmp     byte ptr [rbp+20h], 0
0x180168d23  jz      short loc_180168D36
0x180168d25  mov     rcx, [rbp+60h]
0x180168d29  mov     rcx, [rcx+160h]
0x180168d30  call    RtlLeaveCriticalSection
0x180168d35  nop
0x180168d36  add     rsp, 20h
0x180168d3a  pop     rbp
0x180168d3b  retn
```
