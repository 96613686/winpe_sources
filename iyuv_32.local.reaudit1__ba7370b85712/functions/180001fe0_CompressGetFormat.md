# CompressGetFormat

- ea: `0x180001fe0`
- end: `0x18000206a`
- name: `CompressGetFormat`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x180001fe0`
- `0x180002084`

## pseudocode

```c
__int64 __fastcall CompressGetFormat(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  int v6; // eax

  result = CompressQuery(a2, 0);
  if ( !(_DWORD)result )
  {
    if ( a3 )
    {
      *(_OWORD *)a3 = *(_OWORD *)a2;
      *(_OWORD *)(a3 + 16) = *(_OWORD *)(a2 + 16);
      *(_DWORD *)a3 = 40;
      *(_DWORD *)(a3 + 12) = 1572865;
      *(_QWORD *)(a3 + 32) = 0;
      v6 = *(_DWORD *)(a2 + 8) * *(_DWORD *)(a2 + 4);
      *(_DWORD *)(a3 + 16) = 1448433993;
      *(_DWORD *)(a3 + 20) = 3 * v6;
      *(_DWORD *)(a3 + 4) = (((*(int *)(a2 + 4) >> 31) & 3) + *(_DWORD *)(a2 + 4)) & 0xFFFFFFFC;
      *(_DWORD *)(a3 + 8) = (((*(int *)(a2 + 8) >> 31) & 3) + *(_DWORD *)(a2 + 8)) & 0xFFFFFFFC;
      return 0;
    }
    else
    {
      return 40;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001fe0  mov     [rsp+arg_0], rbx
0x180001fe5  push    rdi
0x180001fe6  sub     rsp, 20h
0x180001fea  mov     rdi, rdx
0x180001fed  mov     rbx, r8
0x180001ff0  mov     rcx, rdi
0x180001ff3  xor     edx, edx
0x180001ff5  call    CompressQuery
0x180001ffa  test    eax, eax
0x180001ffc  jnz     short loc_18000205F
0x180001ffe  test    rbx, rbx
0x180002001  jnz     short loc_180002008
0x180002003  lea     eax, [rbx+28h]
0x180002006  jmp     short loc_18000205F
0x180002008  movups  xmm0, xmmword ptr [rdi]
0x18000200b  movups  xmmword ptr [rbx], xmm0
0x18000200e  movups  xmm1, xmmword ptr [rdi+10h]
0x180002012  movups  xmmword ptr [rbx+10h], xmm1
0x180002016  mov     dword ptr [rbx], 28h ; '('
0x18000201c  mov     dword ptr [rbx+0Ch], 180001h
0x180002023  mov     qword ptr [rbx+20h], 0
0x18000202b  mov     eax, [rdi+4]
0x18000202e  imul    eax, [rdi+8]
0x180002032  mov     dword ptr [rbx+10h], 56555949h
0x180002039  lea     eax, [rax+rax*2]
0x18000203c  mov     [rbx+14h], eax
0x18000203f  mov     eax, [rdi+4]
0x180002042  cdq
0x180002043  and     edx, 3
0x180002046  add     eax, edx
0x180002048  and     eax, 0FFFFFFFCh
0x18000204b  mov     [rbx+4], eax
0x18000204e  mov     eax, [rdi+8]
0x180002051  cdq
0x180002052  and     edx, 3
0x180002055  add     eax, edx
0x180002057  and     eax, 0FFFFFFFCh
0x18000205a  mov     [rbx+8], eax
0x18000205d  xor     eax, eax
0x18000205f  mov     rbx, [rsp+28h+arg_0]
0x180002064  add     rsp, 20h
0x180002068  pop     rdi
0x180002069  retn
```
