# CcpMakeConfigRequest

- ea: `0x180026210`
- end: `0x180026260`
- name: `CcpMakeConfigRequest`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180025814`
- `0x180026210`

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
0x180026210  push    rbx
0x180026212  sub     rsp, 20h
0x180026216  add     r8d, 0FFFFFFFCh
0x18002621a  mov     rbx, rdx
0x18002621d  mov     [rsp+28h+arg_10], r8d
0x180026222  lea     r8, [rcx+194h]
0x180026229  mov     r9d, [r8]
0x18002622c  lea     rcx, [rdx+4]
0x180026230  lea     rdx, [rsp+28h+arg_10]
0x180026235  call    CcpBuildOptionList
0x18002623a  test    eax, eax
0x18002623c  jnz     short loc_180026259
0x18002623e  movzx   ecx, word ptr [rsp+28h+arg_10]
0x180026243  add     cx, 4
0x180026247  mov     byte ptr [rbx], 1
0x18002624a  movzx   eax, cx
0x18002624d  mov     [rbx+3], cl
0x180026250  shr     ax, 8
0x180026254  mov     [rbx+2], al
0x180026257  xor     eax, eax
0x180026259  add     rsp, 20h
0x18002625d  pop     rbx
0x18002625e  retn
```
