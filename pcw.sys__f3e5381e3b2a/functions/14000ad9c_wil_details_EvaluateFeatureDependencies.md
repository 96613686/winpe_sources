# wil_details_EvaluateFeatureDependencies

- ea: `0x14000ad9c`
- end: `0x14000aea8`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b280`
- `0x140012354`

## callees

- `0x14000ad9c`
- `0x14000aeec`

## pseudocode

```c
void wil_details_EvaluateFeatureDependencies()
{
  ;
}

```

## disassembly

```asm
0x14000ad9c  mov     [rsp+arg_8], rbx
0x14000ada1  push    rsi
0x14000ada2  sub     rsp, 20h
0x14000ada6  lea     rbx, wil_details_featureDescriptors_a
0x14000adad  mov     [rsp+28h+arg_0], 0
0x14000adb6  lea     rsi, wil_details_featureDescriptors_a
0x14000adbd  mov     rcx, rbx
0x14000adc0  cmp     rbx, rsi
0x14000adc3  jnb     loc_14000AE9C
0x14000adc9  cmp     qword ptr [rcx], 0
0x14000adcd  jnz     short loc_14000ADDA
0x14000adcf  add     rcx, 8
0x14000add3  cmp     rcx, rsi
0x14000add6  jb      short loc_14000ADC9
0x14000add8  jmp     short loc_14000AE54
0x14000adda  test    rcx, rcx
0x14000addd  jz      short loc_14000AE54
0x14000addf  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14000ade4  mov     rax, [rcx]
0x14000ade7  mov     edx, [rax]
0x14000ade9  bt      edx, 9
0x14000aded  jnb     short loc_14000AE2C
0x14000adef  mov     r8d, edx
0x14000adf2  and     r8d, 180h
0x14000adf9  jnz     short loc_14000AE05
0x14000adfb  xor     eax, eax
0x14000adfd  cmp     [rcx+1Fh], al
0x14000ae00  setnz   al
0x14000ae03  jmp     short loc_14000AE11
0x14000ae05  xor     eax, eax
0x14000ae07  cmp     r8d, 100h
0x14000ae0e  setz    al
0x14000ae11  shl     eax, 6
0x14000ae14  and     edx, 40h
0x14000ae17  xor     edx, eax
0x14000ae19  mov     eax, r9d
0x14000ae1c  and     eax, 0FFFFFFBFh
0x14000ae1f  mov     r9d, edx
0x14000ae22  or      r9d, eax
0x14000ae25  mov     rax, [rcx]
0x14000ae28  lock xor [rax], r9d
0x14000ae2c  add     rcx, 38h ; '8'
0x14000ae30  jmp     short loc_14000AE3C
0x14000ae32  cmp     qword ptr [rcx], 0
0x14000ae36  jnz     short loc_14000AE43
0x14000ae38  add     rcx, 8
0x14000ae3c  cmp     rcx, rsi
0x14000ae3f  jb      short loc_14000AE32
0x14000ae41  jmp     short loc_14000AE54
0x14000ae43  test    rcx, rcx
0x14000ae46  jnz     short loc_14000ADE4
0x14000ae48  jmp     short loc_14000AE54
0x14000ae4a  cmp     qword ptr [rbx], 0
0x14000ae4e  jnz     short loc_14000AE97
0x14000ae50  add     rbx, 8
0x14000ae54  cmp     rbx, rsi
0x14000ae57  jb      short loc_14000AE4A
0x14000ae59  jmp     short loc_14000AE9C
0x14000ae5b  mov     rcx, [rbx]
0x14000ae5e  mov     [rsp+28h+arg_0], 0
0x14000ae67  mov     eax, [rcx]
0x14000ae69  mov     dword ptr [rsp+28h+arg_0], eax
0x14000ae6d  bt      eax, 9
0x14000ae71  jnb     short loc_14000AE80
0x14000ae73  mov     rdx, [rsp+28h+arg_0]
0x14000ae78  mov     r8, rbx
0x14000ae7b  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14000ae80  add     rbx, 38h ; '8'
0x14000ae84  jmp     short loc_14000AE90
0x14000ae86  cmp     qword ptr [rbx], 0
0x14000ae8a  jnz     short loc_14000AE97
0x14000ae8c  add     rbx, 8
0x14000ae90  cmp     rbx, rsi
0x14000ae93  jb      short loc_14000AE86
0x14000ae95  jmp     short loc_14000AE9C
0x14000ae97  test    rbx, rbx
0x14000ae9a  jnz     short loc_14000AE5B
0x14000ae9c  mov     rbx, [rsp+28h+arg_8]
0x14000aea1  add     rsp, 20h
0x14000aea5  pop     rsi
0x14000aea6  retn
```
