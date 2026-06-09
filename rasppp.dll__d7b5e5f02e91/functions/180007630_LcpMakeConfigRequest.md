# LcpMakeConfigRequest

- ea: `0x180007630`
- end: `0x180007680`
- name: `LcpMakeConfigRequest`
- size: `80`
- prototype: `__int64 __fastcall(__int64, _BYTE *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180006328`
- `0x180007630`

## pseudocode

```c
__int64 __fastcall LcpMakeConfigRequest(__int64 a1, _BYTE *a2, int a3)
{
  __int64 result; // rax
  __int16 v5; // cx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = a3 - 4;
  result = BuildOptionList(a2 + 4, &v6, a1 + 1208, *(unsigned int *)(a1 + 1208));
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
0x180007630  push    rbx
0x180007632  sub     rsp, 20h
0x180007636  add     r8d, 0FFFFFFFCh
0x18000763a  mov     rbx, rdx
0x18000763d  mov     [rsp+28h+arg_10], r8d
0x180007642  lea     r8, [rcx+4B8h]
0x180007649  mov     r9d, [r8]
0x18000764c  lea     rcx, [rdx+4]
0x180007650  lea     rdx, [rsp+28h+arg_10]
0x180007655  call    BuildOptionList
0x18000765a  test    eax, eax
0x18000765c  jnz     short loc_180007679
0x18000765e  movzx   ecx, word ptr [rsp+28h+arg_10]
0x180007663  add     cx, 4
0x180007667  mov     byte ptr [rbx], 1
0x18000766a  movzx   eax, cx
0x18000766d  mov     [rbx+3], cl
0x180007670  shr     ax, 8
0x180007674  mov     [rbx+2], al
0x180007677  xor     eax, eax
0x180007679  add     rsp, 20h
0x18000767d  pop     rbx
0x18000767e  retn
```
