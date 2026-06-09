# ConvertToWin64HHWinType

- ea: `0x18005d108`
- end: `0x18005d1e5`
- name: `ConvertToWin64HHWinType`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18005e364`

## import_xrefs

- `USER32!CopyRect` at `0x18005d144`
- `USER32!CopyRect` at `0x18005d15e`
- `USER32!CopyRect` at `0x18005d1c8`
- `USER32!CopyRect` at `0x18005d144`
- `USER32!CopyRect` at `0x18005d15e`
- `USER32!CopyRect` at `0x18005d1c8`

## pseudocode

```c
__int64 __fastcall ConvertToWin64HHWinType(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  *(_DWORD *)a1 = 280;
  *(_DWORD *)(a1 + 4) = *(_DWORD *)(a2 + 4);
  *(_DWORD *)(a1 + 16) = *(_DWORD *)(a2 + 12);
  *(_DWORD *)(a1 + 20) = *(_DWORD *)(a2 + 16);
  *(_DWORD *)(a1 + 32) = *(_DWORD *)(a2 + 24);
  *(_DWORD *)(a1 + 36) = *(_DWORD *)(a2 + 28);
  CopyRect((LPRECT)(a1 + 40), (const RECT *)(a2 + 32));
  *(_DWORD *)(a1 + 56) = *(_DWORD *)(a2 + 48);
  *(_DWORD *)(a1 + 112) = *(_DWORD *)(a2 + 76);
  CopyRect((LPRECT)(a1 + 116), (const RECT *)(a2 + 80));
  *(_DWORD *)(a1 + 168) = *(_DWORD *)(a2 + 112);
  *(_DWORD *)(a1 + 172) = *(_DWORD *)(a2 + 116);
  *(_DWORD *)(a1 + 176) = *(_DWORD *)(a2 + 120);
  *(_DWORD *)(a1 + 180) = *(_DWORD *)(a2 + 124);
  *(_DWORD *)(a1 + 184) = *(_DWORD *)(a2 + 128);
  *(_OWORD *)(a1 + 188) = *(_OWORD *)(a2 + 132);
  *(_DWORD *)(a1 + 204) = *(_DWORD *)(a2 + 148);
  *(_DWORD *)(a1 + 208) = *(_DWORD *)(a2 + 152);
  CopyRect((LPRECT)(a1 + 248), (const RECT *)(a2 + 172));
  result = *(unsigned int *)(a2 + 188);
  *(_DWORD *)(a1 + 264) = result;
  return result;
}

```

## disassembly

```asm
0x18005d108  mov     [rsp+arg_0], rbx
0x18005d10d  push    rdi
0x18005d10e  sub     rsp, 20h
0x18005d112  mov     dword ptr [rcx], 118h
0x18005d118  mov     rbx, rdx
0x18005d11b  mov     eax, [rdx+4]
0x18005d11e  mov     rdi, rcx
0x18005d121  mov     [rcx+4], eax
0x18005d124  mov     eax, [rdx+0Ch]
0x18005d127  mov     [rcx+10h], eax
0x18005d12a  mov     eax, [rdx+10h]
0x18005d12d  mov     [rcx+14h], eax
0x18005d130  mov     eax, [rdx+18h]
0x18005d133  mov     [rcx+20h], eax
0x18005d136  mov     eax, [rdx+1Ch]
0x18005d139  add     rdx, 20h ; ' '; lprcSrc
0x18005d13d  mov     [rcx+24h], eax
0x18005d140  add     rcx, 28h ; '('; lprcDst
0x18005d144  call    cs:__imp_CopyRect
0x18005d14a  mov     eax, [rbx+30h]
0x18005d14d  lea     rdx, [rbx+50h]; lprcSrc
0x18005d151  mov     [rdi+38h], eax
0x18005d154  lea     rcx, [rdi+74h]; lprcDst
0x18005d158  mov     eax, [rbx+4Ch]
0x18005d15b  mov     [rdi+70h], eax
0x18005d15e  call    cs:__imp_CopyRect
0x18005d164  mov     eax, [rbx+70h]
0x18005d167  lea     rdx, [rbx+0ACh]; lprcSrc
0x18005d16e  mov     [rdi+0A8h], eax
0x18005d174  lea     rcx, [rdi+0F8h]; lprcDst
0x18005d17b  mov     eax, [rbx+74h]
0x18005d17e  mov     [rdi+0ACh], eax
0x18005d184  mov     eax, [rbx+78h]
0x18005d187  mov     [rdi+0B0h], eax
0x18005d18d  mov     eax, [rbx+7Ch]
0x18005d190  mov     [rdi+0B4h], eax
0x18005d196  mov     eax, [rbx+80h]
0x18005d19c  mov     [rdi+0B8h], eax
0x18005d1a2  movups  xmm0, xmmword ptr [rbx+84h]
0x18005d1a9  movups  xmmword ptr [rdi+0BCh], xmm0
0x18005d1b0  mov     eax, [rbx+94h]
0x18005d1b6  mov     [rdi+0CCh], eax
0x18005d1bc  mov     eax, [rbx+98h]
0x18005d1c2  mov     [rdi+0D0h], eax
0x18005d1c8  call    cs:__imp_CopyRect
0x18005d1ce  mov     eax, [rbx+0BCh]
0x18005d1d4  mov     rbx, [rsp+28h+arg_0]
0x18005d1d9  mov     [rdi+108h], eax
0x18005d1df  add     rsp, 20h
0x18005d1e3  pop     rdi
0x18005d1e4  retn
```
