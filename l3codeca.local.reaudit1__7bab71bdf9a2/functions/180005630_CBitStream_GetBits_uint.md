# CBitStream::GetBits(uint)

- ea: `0x180005630`
- end: `0x1800056d4`
- name: `?GetBits@CBitStream@@QEAAII@Z`
- size: `164`
- prototype: `unsigned int __fastcall(CBitStream *__hidden this, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800055f0`
- `0x1800058e0`
- `0x180005a40`
- `0x1800078d0`
- `0x18000a590`
- `0x18000b870`
- `0x18000bad0`

## callees

- `0x180005630`

## pseudocode

```c
__int64 __fastcall CBitStream::GetBits(CBitStream *this, unsigned int a2)
{
  int v2; // edi
  __int64 v4; // rsi
  unsigned __int16 v5; // r11
  unsigned int v6; // ecx
  unsigned __int16 v7; // r8
  int v8; // eax

  v2 = *((_DWORD *)this + 9);
  v4 = *((_QWORD *)this + 6);
  v5 = (*(unsigned __int8 *)(((v2 >> 3) & 0xFFFFFFFE) + 1 + v4)
      | (unsigned __int16)(*(unsigned __int8 *)(v4 + ((v2 >> 3) & 0xFFFFFFFE)) << 8)) << (*((_BYTE *)this + 36) & 0xF);
  v6 = 16 - (v2 & 0xF);
  if ( a2 <= v6 )
    v7 = v5;
  else
    v7 = v5
       | ((unsigned __int16)(*(unsigned __int8 *)(((((v2 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)this + 4) - 1)) + 1 + v4)
                           | (*(unsigned __int8 *)(((((v2 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)this + 4) - 1)) + v4) << 8)) >> v6);
  v8 = *((_DWORD *)this + 5);
  *((_DWORD *)this + 8) += a2;
  *((_DWORD *)this + 6) -= a2;
  *((_DWORD *)this + 9) = (v8 - 1) & (v2 + a2);
  return v7 >> (16 - a2);
}

```

## disassembly

```asm
0x180005630  push    rbx
0x180005632  push    rbp
0x180005633  push    rsi
0x180005634  push    rdi
0x180005635  mov     edi, [rcx+24h]
0x180005638  mov     r9, rcx
0x18000563b  mov     rsi, [rcx+30h]
0x18000563f  mov     eax, edi
0x180005641  sar     eax, 3
0x180005644  mov     r8d, edi
0x180005647  and     eax, 0FFFFFFFEh
0x18000564a  and     r8d, 0Fh
0x18000564e  mov     ebp, eax
0x180005650  mov     ecx, r8d
0x180005653  mov     ebx, 10h
0x180005658  mov     r10d, edx
0x18000565b  movzx   r11d, byte ptr [rsi+rax]
0x180005660  inc     eax
0x180005662  shl     r11w, 8
0x180005667  movzx   eax, byte ptr [rax+rsi]
0x18000566b  or      r11w, ax
0x18000566f  shl     r11w, cl
0x180005673  mov     ecx, ebx
0x180005675  sub     ecx, r8d
0x180005678  cmp     edx, ecx
0x18000567a  jbe     short loc_1800056A7
0x18000567c  mov     edx, [r9+10h]
0x180005680  lea     eax, [rbp+2]
0x180005683  dec     edx
0x180005685  and     edx, eax
0x180005687  mov     eax, edx
0x180005689  movzx   r8d, byte ptr [rdx+rsi]
0x18000568e  shl     r8w, 8
0x180005693  inc     eax
0x180005695  movzx   eax, byte ptr [rax+rsi]
0x180005699  or      r8w, ax
0x18000569d  shr     r8w, cl
0x1800056a1  or      r8w, r11w
0x1800056a5  jmp     short loc_1800056AB
0x1800056a7  movzx   r8d, r11w
0x1800056ab  mov     eax, [r9+14h]
0x1800056af  lea     edx, [rdi+r10]
0x1800056b3  add     [r9+20h], r10d
0x1800056b7  dec     eax
0x1800056b9  sub     [r9+18h], r10d
0x1800056bd  and     edx, eax
0x1800056bf  sub     bl, r10b
0x1800056c2  movzx   eax, r8w
0x1800056c6  movzx   ecx, bl
0x1800056c9  mov     [r9+24h], edx
0x1800056cd  shr     eax, cl
0x1800056cf  pop     rdi
0x1800056d0  pop     rsi
0x1800056d1  pop     rbp
0x1800056d2  pop     rbx
0x1800056d3  retn
```
