# QuicDatagramWriteFrame

- ea: `0x140045ccc`
- end: `0x140045e2b`
- name: `QuicDatagramWriteFrame`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140019040`

## callees

- `0x140029104`
- `0x14004572c`
- `0x140045ccc`
- `0x140046dcc`

## pseudocode

```c
char __fastcall QuicDatagramWriteFrame(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rdi
  char v5; // si
  _QWORD *v6; // rdx
  __int64 v7; // rax

  v2 = *a1;
  v5 = 0;
  while ( v2 )
  {
    if ( (*(_BYTE *)(*(_QWORD *)(a2 + 408) + 88LL) & 3) == 1 && (*(_DWORD *)(v2 + 20) & 1) == 0 )
      goto LABEL_14;
    if ( !(unsigned __int8)QuicDatagramFrameEncodeEx(
                             *(_QWORD *)(v2 + 8),
                             *(_DWORD *)(v2 + 16),
                             *(_QWORD *)(v2 + 32),
                             (int)a2 + 378,
                             **(_WORD **)(a2 + 32) - *(unsigned __int8 *)(a2 + 370),
                             *(_QWORD *)(*(_QWORD *)(a2 + 32) + 8LL)) )
      goto LABEL_13;
    if ( a1[1] == v2 )
      a1[1] = a1;
    if ( a1[2] == v2 )
      a1[2] = a1;
    *a1 = *(_QWORD *)v2;
    *(_BYTE *)(*(_QWORD *)(a2 + 408) + 88LL) |= 4u;
    *(_WORD *)(*(_QWORD *)(a2 + 408) + 24LL * *(unsigned __int8 *)(*(_QWORD *)(a2 + 408) + 90LL) + 114) = 48;
    *(_QWORD *)(*(_QWORD *)(a2 + 408) + 24 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 408) + 90LL) + 4LL)) = *(_QWORD *)(v2 + 56);
    v6 = (_QWORD *)(*(_QWORD *)(a2 + 408) + 24 * (*(unsigned __int8 *)(*(_QWORD *)(a2 + 408) + 90LL) + 4LL));
    *v6 = *(_QWORD *)(v2 + 56);
    QuicDatagramIndicateSendStateChange(a1 - 444, v6, 1);
    CxPlatPoolFree(v2);
    v7 = *(_QWORD *)(a2 + 408);
    if ( ++*(_BYTE *)(v7 + 90) == 12 )
    {
LABEL_13:
      v5 = 1;
LABEL_14:
      if ( *a1 )
        return v5;
      break;
    }
    v2 = *a1;
  }
  *((_DWORD *)a1 - 16) &= ~0x4000u;
  return v5;
}

```

## disassembly

```asm
0x140045ccc  mov     rax, rsp
0x140045ccf  mov     [rax+8], rbx
0x140045cd3  mov     [rax+10h], rbp
0x140045cd7  mov     [rax+18h], rsi
0x140045cdb  mov     [rax+20h], rdi
0x140045cdf  push    r14
0x140045ce1  sub     rsp, 30h
0x140045ce5  mov     rdi, [rcx]
0x140045ce8  mov     rbp, rdx
0x140045ceb  mov     rbx, rcx
0x140045cee  xor     sil, sil
0x140045cf1  jmp     loc_140045DF3
0x140045cf6  mov     rax, [rbp+198h]
0x140045cfd  mov     cl, [rax+58h]
0x140045d00  and     cl, 3
0x140045d03  cmp     cl, 1
0x140045d06  jnz     short loc_140045D13
0x140045d08  mov     eax, [rdi+14h]
0x140045d0b  test    cl, al
0x140045d0d  jz      loc_140045E01
0x140045d13  mov     rcx, [rbp+20h]
0x140045d17  lea     r9, [rbp+17Ah]
0x140045d1e  movzx   eax, byte ptr [rbp+172h]
0x140045d25  mov     r8, [rdi+20h]
0x140045d29  movzx   edx, word ptr [rcx]
0x140045d2c  sub     dx, ax
0x140045d2f  mov     rax, [rcx+8]
0x140045d33  mov     rcx, [rdi+8]
0x140045d37  mov     [rsp+38h+var_10], rax
0x140045d3c  mov     [rsp+38h+var_18], dx
0x140045d41  mov     edx, [rdi+10h]
0x140045d44  call    QuicDatagramFrameEncodeEx
0x140045d49  test    al, al
0x140045d4b  jz      loc_140045DFE
0x140045d51  cmp     [rbx+8], rdi
0x140045d55  jnz     short loc_140045D5B
0x140045d57  mov     [rbx+8], rbx
0x140045d5b  cmp     [rbx+10h], rdi
0x140045d5f  jnz     short loc_140045D65
0x140045d61  mov     [rbx+10h], rbx
0x140045d65  mov     rax, [rdi]
0x140045d68  mov     [rbx], rax
0x140045d6b  mov     rax, [rbp+198h]
0x140045d72  or      byte ptr [rax+58h], 4
0x140045d76  mov     rdx, [rbp+198h]
0x140045d7d  movzx   eax, byte ptr [rdx+5Ah]
0x140045d81  lea     rcx, [rax+rax*2]
0x140045d85  mov     word ptr [rdx+rcx*8+72h], 30h ; '0'
0x140045d8c  lea     rcx, [rbx-0DE0h]
0x140045d93  mov     r8, [rbp+198h]
0x140045d9a  movzx   eax, byte ptr [r8+5Ah]
0x140045d9f  add     rax, 4
0x140045da3  lea     rdx, [rax+rax*2]
0x140045da7  mov     rax, [rdi+38h]
0x140045dab  mov     [r8+rdx*8], rax
0x140045daf  mov     r8d, 1
0x140045db5  mov     rdx, [rbp+198h]
0x140045dbc  movzx   eax, byte ptr [rdx+5Ah]
0x140045dc0  add     rax, 4
0x140045dc4  lea     rax, [rax+rax*2]
0x140045dc8  lea     rdx, [rdx+rax*8]
0x140045dcc  mov     rax, [rdi+38h]
0x140045dd0  mov     [rdx], rax
0x140045dd3  call    QuicDatagramIndicateSendStateChange
0x140045dd8  mov     rcx, rdi
0x140045ddb  call    CxPlatPoolFree
0x140045de0  mov     rax, [rbp+198h]
0x140045de7  inc     byte ptr [rax+5Ah]
0x140045dea  cmp     byte ptr [rax+5Ah], 0Ch
0x140045dee  jz      short loc_140045DFE
0x140045df0  mov     rdi, [rbx]
0x140045df3  test    rdi, rdi
0x140045df6  jnz     loc_140045CF6
0x140045dfc  jmp     short loc_140045E07
0x140045dfe  mov     sil, 1
0x140045e01  cmp     qword ptr [rbx], 0
0x140045e05  jnz     short loc_140045E0C
0x140045e07  btr     dword ptr [rbx-40h], 0Eh
0x140045e0c  mov     rbx, [rsp+38h+arg_0]
0x140045e11  mov     al, sil
0x140045e14  mov     rsi, [rsp+38h+arg_10]
0x140045e19  mov     rbp, [rsp+38h+arg_8]
0x140045e1e  mov     rdi, [rsp+38h+arg_18]
0x140045e23  add     rsp, 30h
0x140045e27  pop     r14
0x140045e29  retn
```
