# LcpMakeConfigRequest

- ea: `0x180007370`
- end: `0x1800073bf`
- name: `LcpMakeConfigRequest`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800060b4`
- `0x180007370`

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
0x180007370  push    rbx
0x180007372  sub     rsp, 20h
0x180007376  add     r8d, 0FFFFFFFCh
0x18000737a  mov     rbx, rdx
0x18000737d  mov     [rsp+28h+arg_10], r8d
0x180007382  lea     r8, [rcx+4B8h]
0x180007389  mov     r9d, [r8]
0x18000738c  lea     rcx, [rdx+4]
0x180007390  lea     rdx, [rsp+28h+arg_10]
0x180007395  call    BuildOptionList
0x18000739a  test    eax, eax
0x18000739c  jnz     short loc_1800073B9
0x18000739e  movzx   ecx, word ptr [rsp+28h+arg_10]
0x1800073a3  add     cx, 4
0x1800073a7  mov     byte ptr [rbx], 1
0x1800073aa  movzx   eax, cx
0x1800073ad  mov     [rbx+3], cl
0x1800073b0  shr     ax, 8
0x1800073b4  mov     [rbx+2], al
0x1800073b7  xor     eax, eax
0x1800073b9  add     rsp, 20h
0x1800073bd  pop     rbx
0x1800073be  retn
```
