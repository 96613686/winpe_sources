# CcpMakeConfigRequest

- ea: `0x180025460`
- end: `0x1800254af`
- name: `CcpMakeConfigRequest`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180024a6c`
- `0x180025460`

## pseudocode

```c
__int64 __fastcall CcpMakeConfigRequest(__int64 a1, _BYTE *a2, int a3)
{
  __int64 result; // rax
  __int16 v5; // cx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = a3 - 4;
  result = CcpBuildOptionList(a2 + 4, &v6, a1 + 404, *(unsigned int *)(a1 + 404));
  if ( !(_DWORD)result )
  {
    v5 = v6 + 4;
    *a2 = 1;
    a2[3] = v5;
    a2[2] = HIBYTE(v5);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180025460  push    rbx
0x180025462  sub     rsp, 20h
0x180025466  add     r8d, 0FFFFFFFCh
0x18002546a  mov     rbx, rdx
0x18002546d  mov     [rsp+28h+arg_10], r8d
0x180025472  lea     r8, [rcx+194h]
0x180025479  mov     r9d, [r8]
0x18002547c  lea     rcx, [rdx+4]
0x180025480  lea     rdx, [rsp+28h+arg_10]
0x180025485  call    CcpBuildOptionList
0x18002548a  test    eax, eax
0x18002548c  jnz     short loc_1800254A9
0x18002548e  movzx   ecx, word ptr [rsp+28h+arg_10]
0x180025493  add     cx, 4
0x180025497  mov     byte ptr [rbx], 1
0x18002549a  movzx   eax, cx
0x18002549d  mov     [rbx+3], cl
0x1800254a0  shr     ax, 8
0x1800254a4  mov     [rbx+2], al
0x1800254a7  xor     eax, eax
0x1800254a9  add     rsp, 20h
0x1800254ad  pop     rbx
0x1800254ae  retn
```
