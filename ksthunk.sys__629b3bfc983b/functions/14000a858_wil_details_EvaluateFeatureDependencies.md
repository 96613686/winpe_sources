# wil_details_EvaluateFeatureDependencies

- ea: `0x14000a858`
- end: `0x14000a964`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ab60`
- `0x14000d15c`

## callees

- `0x14000a858`
- `0x14000a9a8`

## pseudocode

```c
void wil_details_EvaluateFeatureDependencies()
{
  ;
}

```

## disassembly

```asm
0x14000a858  mov     [rsp+arg_8], rbx
0x14000a85d  push    rsi
0x14000a85e  sub     rsp, 20h
0x14000a862  lea     rbx, wil_details_featureDescriptors_a
0x14000a869  mov     [rsp+28h+arg_0], 0
0x14000a872  lea     rsi, wil_details_featureDescriptors_a
0x14000a879  mov     rcx, rbx
0x14000a87c  cmp     rbx, rsi
0x14000a87f  jnb     loc_14000A958
0x14000a885  cmp     qword ptr [rcx], 0
0x14000a889  jnz     short loc_14000A896
0x14000a88b  add     rcx, 8
0x14000a88f  cmp     rcx, rsi
0x14000a892  jb      short loc_14000A885
0x14000a894  jmp     short loc_14000A910
0x14000a896  test    rcx, rcx
0x14000a899  jz      short loc_14000A910
0x14000a89b  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14000a8a0  mov     rax, [rcx]
0x14000a8a3  mov     edx, [rax]
0x14000a8a5  bt      edx, 9
0x14000a8a9  jnb     short loc_14000A8E8
0x14000a8ab  mov     r8d, edx
0x14000a8ae  and     r8d, 180h
0x14000a8b5  jnz     short loc_14000A8C1
0x14000a8b7  xor     eax, eax
0x14000a8b9  cmp     [rcx+1Fh], al
0x14000a8bc  setnz   al
0x14000a8bf  jmp     short loc_14000A8CD
0x14000a8c1  xor     eax, eax
0x14000a8c3  cmp     r8d, 100h
0x14000a8ca  setz    al
0x14000a8cd  shl     eax, 6
0x14000a8d0  and     edx, 40h
0x14000a8d3  xor     edx, eax
0x14000a8d5  mov     eax, r9d
0x14000a8d8  and     eax, 0FFFFFFBFh
0x14000a8db  mov     r9d, edx
0x14000a8de  or      r9d, eax
0x14000a8e1  mov     rax, [rcx]
0x14000a8e4  lock xor [rax], r9d
0x14000a8e8  add     rcx, 38h ; '8'
0x14000a8ec  jmp     short loc_14000A8F8
0x14000a8ee  cmp     qword ptr [rcx], 0
0x14000a8f2  jnz     short loc_14000A8FF
0x14000a8f4  add     rcx, 8
0x14000a8f8  cmp     rcx, rsi
0x14000a8fb  jb      short loc_14000A8EE
0x14000a8fd  jmp     short loc_14000A910
0x14000a8ff  test    rcx, rcx
0x14000a902  jnz     short loc_14000A8A0
0x14000a904  jmp     short loc_14000A910
0x14000a906  cmp     qword ptr [rbx], 0
0x14000a90a  jnz     short loc_14000A953
0x14000a90c  add     rbx, 8
0x14000a910  cmp     rbx, rsi
0x14000a913  jb      short loc_14000A906
0x14000a915  jmp     short loc_14000A958
0x14000a917  mov     rcx, [rbx]
0x14000a91a  mov     [rsp+28h+arg_0], 0
0x14000a923  mov     eax, [rcx]
0x14000a925  mov     dword ptr [rsp+28h+arg_0], eax
0x14000a929  bt      eax, 9
0x14000a92d  jnb     short loc_14000A93C
0x14000a92f  mov     rdx, [rsp+28h+arg_0]
0x14000a934  mov     r8, rbx
0x14000a937  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14000a93c  add     rbx, 38h ; '8'
0x14000a940  jmp     short loc_14000A94C
0x14000a942  cmp     qword ptr [rbx], 0
0x14000a946  jnz     short loc_14000A953
0x14000a948  add     rbx, 8
0x14000a94c  cmp     rbx, rsi
0x14000a94f  jb      short loc_14000A942
0x14000a951  jmp     short loc_14000A958
0x14000a953  test    rbx, rbx
0x14000a956  jnz     short loc_14000A917
0x14000a958  mov     rbx, [rsp+28h+arg_8]
0x14000a95d  add     rsp, 20h
0x14000a961  pop     rsi
0x14000a962  retn
```
