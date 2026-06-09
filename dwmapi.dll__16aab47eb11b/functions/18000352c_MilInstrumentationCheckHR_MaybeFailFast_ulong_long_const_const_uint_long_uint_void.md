# MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)

- ea: `0x18000352c`
- end: `0x1800035c4`
- name: `?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z`
- size: `152`
- prototype: `void __usercall(unsigned int@<ecx>, const int *const@<rdx>, unsigned int@<r8d>, int@<r9d>, unsigned int, void *)`
- caller_count: `47`
- callee_count: `5`
- tags: ``

## callers

- `0x180001060`
- `0x180001450`
- `0x180001570`
- `0x180001690`
- `0x180001a10`
- `0x180001c10`
- `0x180001ce0`
- `0x180002920`
- `0x1800035f0`
- `0x180003a90`
- `0x180005060`
- `0x1800052c0`
- `0x180007310`
- `0x180007ae0`
- `0x180007c50`
- `0x1800080e0`
- `0x1800084b0`
- `0x180008cc0`
- `0x180009098`
- `0x180009340`
- `0x180009690`
- `0x180009f50`
- `0x18000a240`
- `0x18000a3c0`
- `0x18000a8e0`
- `0x18000ade0`
- `0x18000aebc`
- `0x18000af44`
- `0x18000b05c`
- `0x18000b2e0`
- `0x18000b560`
- `0x18000b990`
- `0x1800111c0`
- `0x180011240`
- `0x1800112c0`
- `0x180011340`
- `0x180011410`
- `0x1800115c0`
- `0x180011650`
- `0x180013800`
- `0x180013910`
- `0x180013bd0`
- `0x180013ca0`
- `0x180013ed0`
- `0x180014190`
- `0x1800143c0`
- `0x180014950`

## callees

- `0x180003380`
- `0x18000352c`
- `0x180005238`
- `0x180005298`
- `0x180009a0c`

## pseudocode

```c
void __fastcall MilInstrumentationCheckHR_MaybeFailFast(
        unsigned int a1,
        const int *const a2,
        __int64 a3,
        int a4,
        unsigned int a5)
{
  bool v7; // al
  int v8; // ecx
  const int *v9; // r10
  unsigned int v10; // r11d
  bool v11; // si
  void *retaddr; // [rsp+48h] [rbp+0h]

  v7 = IsOOM(a4);
  v11 = v7;
  if ( (a1 & 0x10) != 0 && v7 )
  {
    if ( !v9 || !v10 )
      goto LABEL_5;
  }
  else if ( !v9 || !v10 )
  {
    v9 = &qword_1800192B0;
    v10 = 9;
  }
  if ( !IsHRInList(v8, v9, v10) )
  {
LABEL_5:
    MilInstrumentationHandleFailure_MaybeFailFast(a4, a1, a5, retaddr);
    return;
  }
  if ( (a1 & 4) != 0 && v11 )
    DoStackCapture(a4, a5, retaddr);
}

```

## disassembly

```asm
0x18000352c  push    rbx
0x18000352e  push    rbp
0x18000352f  push    rsi
0x180003530  push    rdi
0x180003531  sub     rsp, 28h
0x180003535  mov     rbp, [rsp+48h]
0x18000353a  mov     edi, ecx
0x18000353c  mov     ecx, r9d; int
0x18000353f  mov     ebx, r9d
0x180003542  mov     r11d, r8d
0x180003545  mov     r10, rdx
0x180003548  call    ?IsOOM@@YA_NJ@Z; IsOOM(long)
0x18000354d  mov     sil, al
0x180003550  test    dil, 10h
0x180003554  jnz     short loc_180003591
0x180003556  test    r10, r10
0x180003559  jnz     short loc_1800035A2
0x18000355b  lea     r10, qword_1800192B0
0x180003562  mov     r11d, 9
0x180003568  mov     r8d, r11d; unsigned int
0x18000356b  mov     rdx, r10; int *
0x18000356e  call    ?IsHRInList@@YA_NJQEBJI@Z; IsHRInList(long,long const * const,uint)
0x180003573  test    al, al
0x180003575  jnz     short loc_1800035A9
0x180003577  mov     r8d, [rsp+48h+arg_20]; unsigned int
0x18000357c  mov     r9, rbp; void *
0x18000357f  mov     edx, edi; unsigned int
0x180003581  mov     ecx, ebx; int
0x180003583  call    ?MilInstrumentationHandleFailure_MaybeFailFast@@YAXJKIPEAX@Z; MilInstrumentationHandleFailure_MaybeFailFast(long,ulong,uint,void *)
0x180003588  add     rsp, 28h
0x18000358c  pop     rdi
0x18000358d  pop     rsi
0x18000358e  pop     rbp
0x18000358f  pop     rbx
0x180003590  retn
0x180003591  test    sil, sil
0x180003594  jz      short loc_180003556
0x180003596  test    r10, r10
0x180003599  jz      short loc_180003577
0x18000359b  test    r11d, r11d
0x18000359e  jz      short loc_180003577
0x1800035a0  jmp     short loc_180003568
0x1800035a2  test    r11d, r11d
0x1800035a5  jnz     short loc_180003568
0x1800035a7  jmp     short loc_18000355B
0x1800035a9  test    dil, 4
0x1800035ad  jz      short loc_180003588
0x1800035af  test    sil, sil
0x1800035b2  jz      short loc_180003588
0x1800035b4  mov     edx, [rsp+48h+arg_20]; unsigned int
0x1800035b8  mov     r8, rbp; void *
0x1800035bb  mov     ecx, ebx; int
0x1800035bd  call    ?DoStackCapture@@YAXJIPEAX@Z; DoStackCapture(long,uint,void *)
0x1800035c2  jmp     short loc_180003588
```
