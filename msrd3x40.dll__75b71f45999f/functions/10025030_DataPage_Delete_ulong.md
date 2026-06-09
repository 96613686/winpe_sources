# DataPage::Delete(ulong)

- ea: `0x10025030`
- end: `0x100250d0`
- name: `?Delete@DataPage@@QAEXK@Z`
- size: `160`
- prototype: `void __thiscall(DataPage *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1001c3d0`
- `0x1001cf90`
- `0x1003f180`
- `0x10048100`

## callees

- `0x10025030`
- `0x10025300`

## pseudocode

```c
void __thiscall DataPage::Delete(DataPage *this, unsigned __int8 a2)
{
  int v2; // ebx
  int v3; // esi
  __int16 v4; // di
  int v5; // eax
  int v6; // eax

  v2 = *((_DWORD *)this + 1);
  v3 = v2 + 2 * a2;
  v4 = *(_WORD *)(v3 + 10);
  if ( (v4 & 0xC000) != 0xC000 )
  {
    if ( a2 )
      v5 = *(_WORD *)(v2 + 2 * a2 + 8) & 0x3FFF;
    else
      v5 = 2048;
    v6 = v5 - (*(_WORD *)(v3 + 10) & 0x3FFF);
    if ( a2 == *(unsigned __int16 *)(v2 + 8) - 1 )
    {
      *(_WORD *)(v3 + 10) = v4 ^ (v4 ^ (v6 + v4)) & 0x3FFF;
      *(_WORD *)(v2 + 2) += v6;
    }
    else
    {
      DataPage::AdjustGap(this, a2, 0, -v6);
    }
    *(_WORD *)(v3 + 10) |= 0xC000u;
  }
}

```

## disassembly

```asm
0x10025030  mov     edi, edi
0x10025032  push    ebp
0x10025033  mov     ebp, esp
0x10025035  sub     esp, 8
0x10025038  movzx   edx, byte ptr [ebp+arg_0]
0x1002503c  mov     eax, ecx
0x1002503e  push    ebx
0x1002503f  push    esi
0x10025040  mov     [ebp+var_8], eax
0x10025043  mov     ebx, [eax+4]
0x10025046  lea     esi, [ebx+edx*2]
0x10025049  push    edi
0x1002504a  movzx   edi, word ptr [esi+0Ah]
0x1002504e  movzx   ecx, word ptr [ebx+8]
0x10025052  mov     eax, edi
0x10025054  and     eax, 3FFFh
0x10025059  dec     ecx
0x1002505a  mov     [ebp+var_4], eax
0x1002505d  mov     eax, edi
0x1002505f  and     eax, 0C000h
0x10025064  cmp     eax, 0C000h
0x10025069  jz      short loc_100250C7
0x1002506b  test    edx, edx
0x1002506d  jnz     short loc_10025076
0x1002506f  mov     eax, 800h
0x10025074  jmp     short loc_10025080
0x10025076  movzx   eax, word ptr [ebx+edx*2+8]
0x1002507b  and     eax, 3FFFh
0x10025080  sub     eax, [ebp+var_4]
0x10025083  cmp     edx, ecx
0x10025085  jnz     short loc_100250B0
0x10025087  movzx   ecx, ax
0x1002508a  lea     eax, [ecx+edi]
0x1002508d  xor     eax, edi
0x1002508f  and     eax, 3FFFh
0x10025094  xor     eax, edi
0x10025096  mov     [esi+0Ah], ax
0x1002509a  mov     eax, 0C000h
0x1002509f  add     [ebx+2], cx
0x100250a3  or      [esi+0Ah], ax
0x100250a7  pop     edi
0x100250a8  pop     esi
0x100250a9  pop     ebx
0x100250aa  mov     esp, ebp
0x100250ac  pop     ebp
0x100250ad  retn    4
0x100250b0  mov     ecx, [ebp+var_8]
0x100250b3  neg     eax
0x100250b5  push    eax
0x100250b6  push    0
0x100250b8  push    edx
0x100250b9  call    ?AdjustGap@DataPage@@AAEXIW4DPBool@@H@Z; DataPage::AdjustGap(uint,DPBool,int)
0x100250be  mov     eax, 0C000h
0x100250c3  or      [esi+0Ah], ax
0x100250c7  pop     edi
0x100250c8  pop     esi
0x100250c9  pop     ebx
0x100250ca  mov     esp, ebp
0x100250cc  pop     ebp
0x100250cd  retn    4
```
