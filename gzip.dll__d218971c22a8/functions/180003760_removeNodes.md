# removeNodes

- ea: `0x180003760`
- end: `0x180003853`
- name: `removeNodes`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002da0`

## callees

- `0x180003760`

## pseudocode

```c
__int64 __fastcall removeNodes(__int64 a1)
{
  __int64 result; // rax
  int v3; // r9d
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r11
  unsigned int v7; // ecx
  unsigned __int16 *v8; // r11
  unsigned int v9; // r9d
  __int64 v10; // rsi
  __int64 v11; // rdi
  __int64 v12; // rbx
  unsigned int v13; // r8d
  unsigned int v14; // edx
  unsigned __int16 v15; // cx

  result = 0;
  do
  {
    v3 = *(_DWORD *)(a1 + 32);
    v4 = (unsigned int)(v3 + ~(_DWORD)result);
    if ( (int)v4 < 0x8000 )
      break;
    v5 = *(_QWORD *)(a1 + 88);
    v6 = *(unsigned __int16 *)((int)v4 + v5) + 172278LL;
    v7 = *(unsigned __int16 *)(v5 + 2 * v6);
    v8 = (unsigned __int16 *)(v5 + 2 * v6);
    if ( v7 == (_DWORD)v4 )
    {
      v9 = v3 - 32718;
      v10 = v5 + 82412;
      v11 = v5 + 213484;
      if ( v7 > v9 )
      {
        v12 = 2 * v4;
        v13 = *(unsigned __int16 *)(2 * v4 + v10);
        if ( v13 <= v9 )
        {
          *(_WORD *)(v12 + v10) = 0;
          v13 = 0;
        }
        v14 = *(unsigned __int16 *)(v12 + v11);
        if ( v14 <= v9 )
        {
          *(_WORD *)(v12 + v11) = 0;
          v14 = 0;
        }
        while ( 1 )
        {
          while ( 1 )
          {
            v15 = 0;
            if ( v13 <= v14 )
              break;
            if ( v13 > v9 )
              v15 = v13;
            *v8 = v15;
            if ( !v15 )
              goto LABEL_4;
            v13 = *(unsigned __int16 *)(v11 + 2LL * v15);
            v8 = (unsigned __int16 *)(v11 + 2LL * v15);
          }
          if ( v14 > v9 )
            v15 = v14;
          *v8 = v15;
          if ( !v15 )
            break;
          v14 = *(unsigned __int16 *)(v10 + 2LL * v15);
          v8 = (unsigned __int16 *)(v10 + 2LL * v15);
        }
      }
      else
      {
        *v8 = 0;
        *(_WORD *)(v11 + 2LL * (int)v4) = 0;
        *(_WORD *)(v10 + 2LL * (int)v4) = 0;
      }
    }
LABEL_4:
    result = (unsigned int)(result + 1);
  }
  while ( (int)result <= 50 );
  return result;
}

```

## disassembly

```asm
0x180003760  mov     [rsp+arg_8], rsi
0x180003765  push    rdi
0x180003766  mov     r10, rcx
0x180003769  mov     [rsp+8+arg_0], rbx
0x18000376e  xor     eax, eax
0x180003770  mov     r9d, [r10+20h]
0x180003774  mov     r8d, eax
0x180003777  not     r8d
0x18000377a  add     r8d, r9d
0x18000377d  cmp     r8d, 8000h
0x180003784  jl      short loc_1800037AE
0x180003786  mov     rdx, [r10+58h]
0x18000378a  movsxd  rbx, r8d
0x18000378d  movzx   r11d, word ptr [rbx+rdx]
0x180003792  add     r11, 2A0F6h
0x180003799  movzx   ecx, word ptr [rdx+r11*2]
0x18000379e  lea     r11, [rdx+r11*2]
0x1800037a2  cmp     ecx, r8d
0x1800037a5  jz      short loc_1800037BA
0x1800037a7  inc     eax
0x1800037a9  cmp     eax, 32h ; '2'
0x1800037ac  jle     short loc_180003770
0x1800037ae  mov     rbx, [rsp+8+arg_0]
0x1800037b3  mov     rsi, [rsp+8+arg_8]
0x1800037b8  pop     rdi
0x1800037b9  retn
0x1800037ba  add     r9d, 0FFFF8032h
0x1800037c1  lea     rsi, [rdx+141ECh]
0x1800037c8  lea     rdi, [rdx+341ECh]
0x1800037cf  cmp     ecx, r9d
0x1800037d2  ja      short loc_1800037E4
0x1800037d4  xor     ecx, ecx
0x1800037d6  mov     [r11], cx
0x1800037da  mov     [rdi+rbx*2], cx
0x1800037de  mov     [rsi+rbx*2], cx
0x1800037e2  jmp     short loc_1800037A7
0x1800037e4  lea     rbx, [r8+r8]
0x1800037e8  movzx   r8d, word ptr [rbx+rsi]
0x1800037ed  cmp     r8d, r9d
0x1800037f0  ja      short loc_1800037FB
0x1800037f2  xor     ecx, ecx
0x1800037f4  mov     [rbx+rsi], cx
0x1800037f8  xor     r8d, r8d
0x1800037fb  movzx   edx, word ptr [rbx+rdi]
0x1800037ff  cmp     edx, r9d
0x180003802  ja      short loc_18000380C
0x180003804  xor     ecx, ecx
0x180003806  mov     [rbx+rdi], cx
0x18000380a  xor     edx, edx
0x18000380c  xor     ecx, ecx
0x18000380e  cmp     r8d, edx
0x180003811  jbe     short loc_180003832
0x180003813  cmp     r8d, r9d
0x180003816  cmova   cx, r8w
0x18000381b  mov     [r11], cx
0x18000381f  test    cx, cx
0x180003822  jz      short loc_1800037A7
0x180003824  movzx   ecx, cx
0x180003827  movzx   r8d, word ptr [rdi+rcx*2]
0x18000382c  lea     r11, [rdi+rcx*2]
0x180003830  jmp     short loc_18000380C
0x180003832  cmp     edx, r9d
0x180003835  cmova   cx, dx
0x180003839  mov     [r11], cx
0x18000383d  test    cx, cx
0x180003840  jz      loc_1800037A7
0x180003846  movzx   ecx, cx
0x180003849  movzx   edx, word ptr [rsi+rcx*2]
0x18000384d  lea     r11, [rsi+rcx*2]
0x180003851  jmp     short loc_18000380C
```
