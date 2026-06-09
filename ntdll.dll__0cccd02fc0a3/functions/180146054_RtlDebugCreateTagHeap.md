# RtlDebugCreateTagHeap

- ea: `0x180146054`
- end: `0x180146142`
- name: `RtlDebugCreateTagHeap`
- size: `238`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180040eb0`

## callees

- `0x180036f50`
- `0x180040eb0`
- `0x1800535c0`
- `0x180053ab0`
- `0x1800a95f0`
- `0x1800aa2cc`
- `0x1800aa904`
- `0x1800feaa8`
- `0x180146054`

## string_xrefs

- `0x180146084`: `RtlCreateTagHeap`

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
0x180146054  mov     rax, rsp
0x180146057  mov     [rax+18h], rbx
0x18014605b  mov     [rax+8], rcx
0x18014605f  push    rsi
0x180146060  push    rdi
0x180146061  push    r12
0x180146063  push    r14
0x180146065  push    r15
0x180146067  sub     rsp, 30h
0x18014606b  mov     r15, r9
0x18014606e  mov     r12, r8
0x180146071  mov     edi, edx
0x180146073  mov     rbx, rcx
0x180146076  xor     sil, sil
0x180146079  mov     [rax-38h], sil
0x18014607d  xor     r14d, r14d
0x180146080  mov     [rax-34h], r14d
0x180146084  lea     rdx, aRtlcreatetaghe_0; "RtlCreateTagHeap"
0x18014608b  call    RtlpCheckHeapSignature
0x180146090  test    al, al
0x180146092  jz      short loc_1801460F1
0x180146094  mov     eax, [rbx+74h]
0x180146097  bts     eax, 1Ch
0x18014609b  or      edi, eax
0x18014609d  mov     [rsp+58h+arg_8], edi
0x1801460a1  test    dil, 1
0x1801460a5  jnz     short loc_1801460C2
0x1801460a7  mov     rcx, [rbx+160h]
0x1801460ae  call    RtlEnterCriticalSection
0x1801460b3  mov     sil, 1
0x1801460b6  mov     [rsp+58h+var_38], sil
0x1801460bb  or      edi, 1
0x1801460be  mov     [rsp+58h+arg_8], edi
0x1801460c2  xor     edx, edx
0x1801460c4  mov     rcx, rbx
0x1801460c7  call    RtlpValidateHeap
0x1801460cc  test    al, al
0x1801460ce  jz      short loc_1801460E7
0x1801460d0  mov     r9, r15
0x1801460d3  mov     r8, r12
0x1801460d6  mov     edx, edi
0x1801460d8  mov     rcx, rbx
0x1801460db  call    RtlCreateTagHeap
0x1801460e0  mov     r14d, eax
0x1801460e3  mov     [rsp+58h+var_34], eax
0x1801460e7  mov     dl, 1
0x1801460e9  mov     rcx, rbx; Src
0x1801460ec  call    RtlpValidateHeapHeaders
0x1801460f1  jmp     short loc_18014611B
0x1801460f3  mov     rbx, gs:30h
0x1801460fc  mov     [rbx+1250h], eax
0x180146102  mov     ecx, eax
0x180146104  call    RtlNtStatusToDosErrorNoTeb
0x180146109  mov     [rbx+68h], eax
0x18014610c  mov     rbx, [rsp+58h+arg_0]
0x180146111  mov     sil, [rsp+58h+var_38]
0x180146116  mov     r14d, [rsp+58h+var_34]
0x18014611b  test    sil, sil
0x18014611e  jz      short loc_18014612C
0x180146120  mov     rcx, [rbx+160h]
0x180146127  call    RtlLeaveCriticalSection
0x18014612c  mov     eax, r14d
0x18014612f  mov     rbx, [rsp+58h+arg_10]
0x180146134  add     rsp, 30h
0x180146138  pop     r15
0x18014613a  pop     r14
0x18014613c  pop     r12
0x18014613e  pop     rdi
0x18014613f  pop     rsi
0x180146140  retn
0x1801684d8  push    rbp
0x1801684da  sub     rsp, 20h
0x1801684de  mov     rbp, rdx
0x1801684e1  mov     rdx, rcx
0x1801684e4  mov     rcx, [rcx]
0x1801684e7  mov     ecx, [rcx]
0x1801684e9  call    RtlpHeapExceptionFilter
0x1801684ee  nop
0x1801684ef  add     rsp, 20h
0x1801684f3  pop     rbp
0x1801684f4  retn
0x1801684f6  push    rbp
0x1801684f8  sub     rsp, 20h
0x1801684fc  mov     rbp, rdx
0x1801684ff  cmp     byte ptr [rbp+20h], 0
0x180168503  jz      short loc_180168516
0x180168505  mov     rcx, [rbp+60h]
0x180168509  mov     rcx, [rcx+160h]
0x180168510  call    RtlLeaveCriticalSection
0x180168515  nop
0x180168516  add     rsp, 20h
0x18016851a  pop     rbp
0x18016851b  retn
```
