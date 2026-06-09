# RtlDebugCompactHeap

- ea: `0x18011fbc4`
- end: `0x18011fcc5`
- name: `RtlDebugCompactHeap`
- size: `257`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180100b70`

## callees

- `0x180036f50`
- `0x1800535c0`
- `0x180053ab0`
- `0x1800a95f0`
- `0x1800aa2cc`
- `0x1800aa904`
- `0x1800feaa8`
- `0x180100b70`
- `0x18011fbc4`
- `0x180146148`
- `0x18016f020`

## string_xrefs

- `0x18011fc16`: `RtlCompactHeap`

## pseudocode

```c
__int64 __fastcall RtlDebugCompactHeap(_DWORD *Src, unsigned __int8 a2)
{
  char v5; // si
  __int64 v6; // rbx

  if ( (Src[29] & 0x1000000) != 0 )
    return (unsigned int)((__int64 (*)(void))xmmword_1801C4628)();
  v5 = 0;
  if ( (unsigned __int8)RtlpCheckHeapSignature(Src, "RtlCompactHeap") )
  {
    if ( ((*((_BYTE *)Src + 116) | a2) & 1) == 0 )
    {
      RtlEnterCriticalSection(*((_QWORD *)Src + 44));
      v5 = 1;
    }
    RtlpValidateHeap(Src, 0);
    v6 = RtlCompactHeap(Src);
    RtlpValidateHeapHeaders(Src);
  }
  else
  {
    v6 = 0;
  }
  if ( v5 )
    RtlLeaveCriticalSection(*((_QWORD *)Src + 44));
  return v6;
}

```

## disassembly

```asm
0x18011fbc4  mov     [rsp+arg_10], rbx
0x18011fbc9  mov     [rsp+arg_18], rsi
0x18011fbce  mov     [rsp+arg_0], rcx
0x18011fbd3  push    rdi
0x18011fbd4  sub     rsp, 30h
0x18011fbd8  mov     ebx, edx
0x18011fbda  mov     rdi, rcx
0x18011fbdd  test    dword ptr [rcx+74h], 1000000h
0x18011fbe4  jz      short loc_18011FC05
0x18011fbe6  mov     rax, qword ptr cs:xmmword_1801C4628
0x18011fbed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fbf2  mov     eax, eax
0x18011fbf4  mov     rbx, [rsp+38h+arg_10]
0x18011fbf9  mov     rsi, [rsp+38h+arg_18]
0x18011fbfe  add     rsp, 30h
0x18011fc02  pop     rdi
0x18011fc03  retn
0x18011fc05  xor     sil, sil
0x18011fc08  mov     [rsp+38h+var_18], sil
0x18011fc0d  mov     [rsp+38h+var_10], 0
0x18011fc16  lea     rdx, aRtlcompactheap_0; "RtlCompactHeap"
0x18011fc1d  call    RtlpCheckHeapSignature
0x18011fc22  test    al, al
0x18011fc24  jnz     short loc_18011FC2F
0x18011fc26  xor     ebx, ebx
0x18011fc28  mov     [rsp+38h+var_10], rbx
0x18011fc2d  jmp     short loc_18011FC82
0x18011fc2f  mov     eax, [rdi+74h]
0x18011fc32  bts     eax, 1Ch
0x18011fc36  or      ebx, eax
0x18011fc38  mov     [rsp+38h+arg_8], ebx
0x18011fc3c  test    bl, 1
0x18011fc3f  jnz     short loc_18011FC5C
0x18011fc41  mov     rcx, [rdi+160h]
0x18011fc48  call    RtlEnterCriticalSection
0x18011fc4d  mov     sil, 1
0x18011fc50  mov     [rsp+38h+var_18], sil
0x18011fc55  or      ebx, 1
0x18011fc58  mov     [rsp+38h+arg_8], ebx
0x18011fc5c  xor     edx, edx
0x18011fc5e  mov     rcx, rdi
0x18011fc61  call    RtlpValidateHeap
0x18011fc66  mov     edx, ebx
0x18011fc68  mov     rcx, rdi
0x18011fc6b  call    RtlCompactHeap
0x18011fc70  mov     rbx, rax
0x18011fc73  mov     [rsp+38h+var_10], rax
0x18011fc78  mov     dl, 1
0x18011fc7a  mov     rcx, rdi; Src
0x18011fc7d  call    RtlpValidateHeapHeaders
0x18011fc82  jmp     short loc_18011FCAC
0x18011fc84  mov     rbx, gs:30h
0x18011fc8d  mov     [rbx+1250h], eax
0x18011fc93  mov     ecx, eax
0x18011fc95  call    RtlNtStatusToDosErrorNoTeb
0x18011fc9a  mov     [rbx+68h], eax
0x18011fc9d  mov     rdi, [rsp+38h+arg_0]
0x18011fca2  mov     sil, [rsp+38h+var_18]
0x18011fca7  mov     rbx, [rsp+38h+var_10]
0x18011fcac  test    sil, sil
0x18011fcaf  jz      short loc_18011FCBD
0x18011fcb1  mov     rcx, [rdi+160h]
0x18011fcb8  call    RtlLeaveCriticalSection
0x18011fcbd  mov     rax, rbx
0x18011fcc0  jmp     loc_18011FBF4
0x180168387  push    rbp
0x180168389  sub     rsp, 20h
0x18016838d  mov     rbp, rdx
0x180168390  mov     rdx, rcx
0x180168393  mov     rcx, [rcx]
0x180168396  mov     ecx, [rcx]
0x180168398  call    RtlpHeapExceptionFilter
0x18016839d  nop
0x18016839e  add     rsp, 20h
0x1801683a2  pop     rbp
0x1801683a3  retn
0x1801683a5  push    rbp
0x1801683a7  sub     rsp, 20h
0x1801683ab  mov     rbp, rdx
0x1801683ae  cmp     byte ptr [rbp+20h], 0
0x1801683b2  jz      short loc_1801683C5
0x1801683b4  mov     rcx, [rbp+40h]
0x1801683b8  mov     rcx, [rcx+160h]
0x1801683bf  call    RtlLeaveCriticalSection
0x1801683c4  nop
0x1801683c5  add     rsp, 20h
0x1801683c9  pop     rbp
0x1801683ca  retn
```
