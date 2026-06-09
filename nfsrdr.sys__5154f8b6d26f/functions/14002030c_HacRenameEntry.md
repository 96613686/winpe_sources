# HacRenameEntry

- ea: `0x14002030c`
- end: `0x140020480`
- name: `HacRenameEntry`
- size: `372`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14001c694`
- `0x140030ef0`

## callees

- `0x140003bd0`
- `0x140009380`
- `0x140014650`
- `0x14002030c`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400203f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400203f5`

## pseudocode

```c
LONG __fastcall HacRenameEntry(__int64 a1, __int64 a2, __int64 a3, void *a4)
{
  int v8; // eax
  void *v9; // rcx
  _WORD *v10; // rsi
  _OWORD v12[3]; // [rsp+20h] [rbp-38h] BYREF

  v12[0] = 0;
  *(_OWORD *)(a2 + 216) = *(_OWORD *)(a3 + 216);
  *(_OWORD *)(a2 + 232) = *(_OWORD *)(a3 + 232);
  *(_OWORD *)(a2 + 248) = *(_OWORD *)(a3 + 248);
  *(_OWORD *)(a2 + 264) = *(_OWORD *)(a3 + 264);
  *(_DWORD *)(a2 + 280) = *(_DWORD *)(a3 + 280);
  v8 = *(unsigned __int16 *)(a2 + 66);
  *(_OWORD *)(a2 + 128) = *(_OWORD *)(a3 + 128);
  *(_OWORD *)(a2 + 144) = *(_OWORD *)(a3 + 144);
  *(_OWORD *)(a2 + 160) = *(_OWORD *)(a3 + 160);
  *(_OWORD *)(a2 + 176) = *(_OWORD *)(a3 + 176);
  *(_OWORD *)(a2 + 192) = *(_OWORD *)(a3 + 192);
  *(_QWORD *)(a2 + 208) = *(_QWORD *)(a3 + 208);
  *(_DWORD *)(*(_QWORD *)(a2 + 40) + 80LL) += -288 - v8;
  HacOrphanEntry(a2);
  v9 = *(void **)(a2 + 96);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  *(_QWORD *)(a2 + 96) = a4;
  v10 = (_WORD *)(a2 + 64);
  if ( *(_QWORD *)(a3 + 72) )
  {
    *(_QWORD *)(a2 + 72) = a4;
    *v10 = *(_WORD *)(a3 + 64);
    *(_WORD *)(a2 + 66) = *(_WORD *)(a3 + 66);
    memmove(a4, *(const void **)(a3 + 72), *(unsigned __int16 *)(a3 + 66));
  }
  else
  {
    *(_QWORD *)(a2 + 72) = 0;
    *(_WORD *)(a2 + 66) = 0;
    *v10 = 0;
  }
  MdaDissectNameTail(a2 + 64, v12, a2 + 80);
  *(_DWORD *)(*(_QWORD *)(a2 + 40) + 80LL) += *(unsigned __int16 *)(a2 + 66) + 288;
  return HacInsertEntry(a1, a2);
}

```

## disassembly

```asm
0x14002030c  push    rbx
0x14002030e  push    rbp
0x14002030f  push    rsi
0x140020310  push    rdi
0x140020311  push    r14
0x140020313  sub     rsp, 30h
0x140020317  xorps   xmm0, xmm0
0x14002031a  mov     rbx, rdx
0x14002031d  movups  [rsp+58h+var_38], xmm0
0x140020322  mov     r14, rcx
0x140020325  mov     ecx, 0FFFFFEE0h
0x14002032a  movups  xmm0, xmmword ptr [r8+0D8h]
0x140020332  mov     rbp, r9
0x140020335  mov     rdi, r8
0x140020338  movups  xmmword ptr [rdx+0D8h], xmm0
0x14002033f  movups  xmm1, xmmword ptr [r8+0E8h]
0x140020347  movups  xmmword ptr [rdx+0E8h], xmm1
0x14002034e  movups  xmm0, xmmword ptr [r8+0F8h]
0x140020356  movups  xmmword ptr [rdx+0F8h], xmm0
0x14002035d  movups  xmm1, xmmword ptr [r8+108h]
0x140020365  movups  xmmword ptr [rdx+108h], xmm1
0x14002036c  mov     eax, [r8+118h]
0x140020373  mov     [rdx+118h], eax
0x140020379  movups  xmm0, xmmword ptr [r8+80h]
0x140020381  movzx   eax, word ptr [rbx+42h]
0x140020385  sub     ecx, eax
0x140020387  movups  xmmword ptr [rdx+80h], xmm0
0x14002038e  movups  xmm1, xmmword ptr [r8+90h]
0x140020396  movups  xmmword ptr [rdx+90h], xmm1
0x14002039d  movups  xmm0, xmmword ptr [r8+0A0h]
0x1400203a5  movups  xmmword ptr [rdx+0A0h], xmm0
0x1400203ac  movups  xmm1, xmmword ptr [r8+0B0h]
0x1400203b4  movups  xmmword ptr [rdx+0B0h], xmm1
0x1400203bb  movups  xmm0, xmmword ptr [r8+0C0h]
0x1400203c3  movups  xmmword ptr [rdx+0C0h], xmm0
0x1400203ca  movsd   xmm1, qword ptr [r8+0D0h]
0x1400203d3  movsd   qword ptr [rdx+0D0h], xmm1
0x1400203db  mov     rdx, [rdx+28h]
0x1400203df  add     [rdx+50h], ecx
0x1400203e2  mov     rcx, rbx
0x1400203e5  call    HacOrphanEntry
0x1400203ea  mov     rcx, [rbx+60h]; P
0x1400203ee  test    rcx, rcx
0x1400203f1  jz      short loc_140020401
0x1400203f3  xor     edx, edx; Tag
0x1400203f5  call    cs:__imp_ExFreePoolWithTag
0x1400203fc  nop     dword ptr [rax+rax+00h]
0x140020401  mov     [rbx+60h], rbp
0x140020405  lea     rsi, [rbx+40h]
0x140020409  cmp     qword ptr [rdi+48h], 0
0x14002040e  jnz     short loc_140020423
0x140020410  xor     eax, eax
0x140020412  mov     qword ptr [rbx+48h], 0
0x14002041a  mov     [rbx+42h], ax
0x14002041e  mov     [rsi], ax
0x140020421  jmp     short loc_140020447
0x140020423  mov     [rbx+48h], rbp
0x140020427  mov     rcx, rbp; void *
0x14002042a  movzx   eax, word ptr [rdi+40h]
0x14002042e  mov     [rsi], ax
0x140020431  movzx   eax, word ptr [rdi+42h]
0x140020435  mov     [rbx+42h], ax
0x140020439  movzx   r8d, word ptr [rdi+42h]; Size
0x14002043e  mov     rdx, [rdi+48h]; Src
0x140020442  call    memmove
0x140020447  lea     r8, [rbx+50h]
0x14002044b  mov     rcx, rsi
0x14002044e  lea     rdx, [rsp+58h+var_38]
0x140020453  call    MdaDissectNameTail
0x140020458  movzx   eax, word ptr [rbx+42h]
0x14002045c  mov     rdx, rbx
0x14002045f  mov     r11, [rbx+28h]
0x140020463  add     eax, 120h
0x140020468  mov     rcx, r14
0x14002046b  add     [r11+50h], eax
0x14002046f  call    HacInsertEntry
0x140020474  add     rsp, 30h
0x140020478  pop     r14
0x14002047a  pop     rdi
0x14002047b  pop     rsi
0x14002047c  pop     rbp
0x14002047d  pop     rbx
0x14002047e  retn
```
