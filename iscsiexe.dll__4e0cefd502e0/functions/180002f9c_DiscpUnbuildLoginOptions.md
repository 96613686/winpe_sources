# DiscpUnbuildLoginOptions

- ea: `0x180002f9c`
- end: `0x18000304d`
- name: `DiscpUnbuildLoginOptions`
- size: `177`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002bc0`
- `0x180003054`
- `0x180004ee8`
- `0x180005290`

## callees

- `0x180002f9c`

## pseudocode

```c
__int64 __fastcall DiscpUnbuildLoginOptions(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  unsigned int v5; // edi
  unsigned int v6; // r9d
  __int64 v7; // r9
  unsigned int v8; // r9d
  __int64 v9; // rdx

  v5 = 11;
  if ( a2 <= a3 && (unsigned __int64)a2 + 52 <= a3 )
  {
    *(_OWORD *)a4 = *(_OWORD *)(a2 + a1);
    *(_OWORD *)(a4 + 16) = *(_OWORD *)(a2 + a1 + 16);
    *(_OWORD *)(a4 + 32) = *(_OWORD *)(a2 + a1 + 32);
    v6 = *(_DWORD *)(a2 + a1 + 44);
    if ( v6 )
    {
      if ( v6 > a3 || a2 + v6 + *(_DWORD *)(a2 + a1 + 36) > a3 )
        return v5;
      v7 = a1 + a2 + v6;
    }
    else
    {
      v7 = 0;
    }
    *(_QWORD *)(a4 + 48) = v7;
    v8 = *(_DWORD *)(a2 + a1 + 48);
    if ( !v8 )
    {
      v9 = 0;
      goto LABEL_13;
    }
    if ( v8 <= a3 && a2 + v8 + *(_DWORD *)(a2 + a1 + 40) <= a3 )
    {
      v9 = a1 + v8 + a2;
LABEL_13:
      *(_QWORD *)(a4 + 56) = v9;
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180002f9c  mov     [rsp+arg_0], rbx
0x180002fa1  mov     [rsp+arg_8], rdi
0x180002fa6  mov     rbx, r9
0x180002fa9  mov     edi, 0Bh
0x180002fae  cmp     edx, r8d
0x180002fb1  ja      loc_180003040
0x180002fb7  mov     r11d, edx
0x180002fba  mov     eax, r8d
0x180002fbd  lea     r10, [r11+34h]
0x180002fc1  cmp     r10, rax
0x180002fc4  ja      short loc_180003040
0x180002fc6  movups  xmm0, xmmword ptr [r11+rcx]
0x180002fcb  movaps  xmmword ptr [r9], xmm0
0x180002fcf  movups  xmm1, xmmword ptr [r11+rcx+10h]
0x180002fd5  movaps  xmmword ptr [r9+10h], xmm1
0x180002fda  movups  xmm0, xmmword ptr [r11+rcx+20h]
0x180002fe0  movaps  xmmword ptr [r9+20h], xmm0
0x180002fe5  mov     r9d, [r11+rcx+2Ch]
0x180002fea  test    r9d, r9d
0x180002fed  jz      short loc_18000300B
0x180002fef  cmp     r9d, r8d
0x180002ff2  ja      short loc_180003040
0x180002ff4  mov     eax, [r11+rcx+24h]
0x180002ff9  add     eax, r9d
0x180002ffc  add     eax, edx
0x180002ffe  cmp     eax, r8d
0x180003001  ja      short loc_180003040
0x180003003  add     r9d, edx
0x180003006  add     r9, rcx
0x180003009  jmp     short loc_18000300E
0x18000300b  xor     r9d, r9d
0x18000300e  mov     [rbx+30h], r9
0x180003012  mov     r9d, [r11+rcx+30h]
0x180003017  test    r9d, r9d
0x18000301a  jz      short loc_180003038
0x18000301c  cmp     r9d, r8d
0x18000301f  ja      short loc_180003040
0x180003021  mov     eax, [r11+rcx+28h]
0x180003026  add     eax, r9d
0x180003029  add     eax, edx
0x18000302b  cmp     eax, r8d
0x18000302e  ja      short loc_180003040
0x180003030  add     edx, r9d
0x180003033  add     rdx, rcx
0x180003036  jmp     short loc_18000303A
0x180003038  xor     edx, edx
0x18000303a  mov     [rbx+38h], rdx
0x18000303e  xor     edi, edi
0x180003040  mov     rbx, [rsp+arg_0]
0x180003045  mov     eax, edi
0x180003047  mov     rdi, [rsp+arg_8]
0x18000304c  retn
```
