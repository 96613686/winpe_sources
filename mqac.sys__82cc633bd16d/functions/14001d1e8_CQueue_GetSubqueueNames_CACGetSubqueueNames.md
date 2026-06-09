# CQueue::GetSubqueueNames(CACGetSubqueueNames *)

- ea: `0x14001d1e8`
- end: `0x14001d312`
- name: `?GetSubqueueNames@CQueue@@QEBAJPEAUCACGetSubqueueNames@@@Z`
- size: `298`
- prototype: `int(CQueue *__hidden this, struct CACGetSubqueueNames *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006bf0`

## callees

- `0x14000eb60`
- `0x14001d1e8`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14001d208`
- `ntoskrnl!ProbeForWrite` at `0x14001d232`
- `ntoskrnl!ProbeForWrite` at `0x14001d208`
- `ntoskrnl!ProbeForWrite` at `0x14001d232`

## pseudocode

```c
__int64 __fastcall CQueue::GetSubqueueNames(CQueue *this, struct CACGetSubqueueNames *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // r14d
  unsigned int v6; // r15d
  volatile void *v7; // r12
  unsigned int v8; // r8d
  _QWORD **v9; // rsi
  _QWORD *v10; // r11
  _QWORD **v11; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // r9
  _QWORD *i; // rdx
  bool v15; // zf
  __int64 result; // rax
  _QWORD **v17; // r11

  v4 = 0;
  ProbeForWrite(a2, 0x18u, 1u);
  *((_DWORD *)a2 + 2) = 0;
  v5 = *(_DWORD *)a2;
  v6 = *((_DWORD *)a2 + 1);
  v7 = (volatile void *)*((_QWORD *)a2 + 2);
  ProbeForWrite(v7, 64LL * v6, 1u);
  v8 = 0;
  v9 = (_QWORD **)((char *)this + 360);
  v10 = *v9;
  v11 = (_QWORD **)*v9;
  v12 = *v9;
  v13 = *v9;
  for ( i = *v9; ; i = v11 )
  {
    if ( v9 == v11 )
    {
      v12 = 0;
    }
    else
    {
      v13 = v12;
      i = v12;
    }
    v15 = v12 == 0;
    if ( !v12 )
      break;
    if ( v8 >= v5 )
    {
      v15 = v12 == 0;
      break;
    }
    v11 = (_QWORD **)*v10;
    v10 = v11;
    ++v8;
    v12 = v11;
    v13 = v11;
  }
  if ( v15 )
    i = v13;
  if ( v9 == v10 || !i )
  {
    *((_DWORD *)a2 + 2) = 0;
    return 0;
  }
  else
  {
    while ( v9 != v10 && v10 && v4 < v6 )
    {
      result = StringCchCopyW((wchar_t *)v7 + 32 * v4, 0x20u, *(const wchar_t **)(v10[2] + 96LL));
      if ( (int)result < 0 )
      {
        *((_DWORD *)a2 + 2) = v4;
        return result;
      }
      ++v4;
      v10 = *v17;
    }
    *((_DWORD *)a2 + 2) = v4;
    return 0;
  }
}

```

## disassembly

```asm
0x14001d1e8  push    rbx
0x14001d1ea  push    rsi
0x14001d1eb  push    rdi
0x14001d1ec  push    r12
0x14001d1ee  push    r14
0x14001d1f0  push    r15
0x14001d1f2  sub     rsp, 48h
0x14001d1f6  mov     rdi, rdx
0x14001d1f9  mov     rsi, rcx
0x14001d1fc  xor     ebx, ebx
0x14001d1fe  lea     edx, [rbx+18h]; Length
0x14001d201  lea     r8d, [rbx+1]; Alignment
0x14001d205  mov     rcx, rdi; Address
0x14001d208  call    cs:__imp_ProbeForWrite
0x14001d20f  nop     dword ptr [rax+rax+00h]
0x14001d214  mov     [rdi+8], ebx
0x14001d217  mov     r14d, [rdi]
0x14001d21a  mov     r15d, [rdi+4]
0x14001d21e  mov     r12, [rdi+10h]
0x14001d222  mov     edx, r15d
0x14001d225  shl     edx, 5
0x14001d228  add     rdx, rdx; Length
0x14001d22b  lea     r8d, [rbx+1]; Alignment
0x14001d22f  mov     rcx, r12; Address
0x14001d232  call    cs:__imp_ProbeForWrite
0x14001d239  nop     dword ptr [rax+rax+00h]
0x14001d23e  xor     r8d, r8d
0x14001d241  mov     [rsp+78h+var_58], r8d
0x14001d246  add     rsi, 168h
0x14001d24d  mov     [rsp+78h+var_50], rsi
0x14001d252  mov     r11, [rsi]
0x14001d255  mov     [rsp+78h+var_48], r11
0x14001d25a  mov     rax, r11
0x14001d25d  mov     rcx, r11
0x14001d260  mov     r9, r11
0x14001d263  mov     rdx, r11
0x14001d266  cmp     rsi, rax
0x14001d269  jnz     short loc_14001D26F
0x14001d26b  xor     ecx, ecx
0x14001d26d  jmp     short loc_14001D275
0x14001d26f  mov     r9, rcx
0x14001d272  mov     rdx, rcx
0x14001d275  test    rcx, rcx
0x14001d278  jz      short loc_14001D2A0
0x14001d27a  cmp     r8d, r14d
0x14001d27d  jnb     short loc_14001D29D
0x14001d27f  mov     rax, [r11]
0x14001d282  mov     r11, rax
0x14001d285  mov     [rsp+78h+var_48], rax
0x14001d28a  inc     r8d
0x14001d28d  mov     [rsp+78h+var_58], r8d
0x14001d292  mov     rcx, rax
0x14001d295  mov     r9, rax
0x14001d298  mov     rdx, rax
0x14001d29b  jmp     short loc_14001D266
0x14001d29d  test    rcx, rcx
0x14001d2a0  cmovz   rdx, r9
0x14001d2a4  cmp     rsi, r11
0x14001d2a7  jz      short loc_14001D2F8
0x14001d2a9  test    rdx, rdx
0x14001d2ac  jz      short loc_14001D2F8
0x14001d2ae  cmp     rsi, r11
0x14001d2b1  jz      short loc_14001D2F1
0x14001d2b3  test    r11, r11
0x14001d2b6  jz      short loc_14001D2F1
0x14001d2b8  cmp     ebx, r15d
0x14001d2bb  jnb     short loc_14001D2F1
0x14001d2bd  mov     r8, [r11+10h]
0x14001d2c1  mov     eax, ebx
0x14001d2c3  shl     eax, 5
0x14001d2c6  lea     rcx, [r12+rax*2]; wchar_t *
0x14001d2ca  mov     r8, [r8+60h]; wchar_t *
0x14001d2ce  mov     edx, 20h ; ' '; unsigned __int64
0x14001d2d3  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001d2d8  test    eax, eax
0x14001d2da  jns     short loc_14001D2E1
0x14001d2dc  mov     [rdi+8], ebx
0x14001d2df  jmp     short loc_14001D303
0x14001d2e1  inc     ebx
0x14001d2e3  mov     [rsp+78h+var_54], ebx
0x14001d2e7  mov     r11, [r11]
0x14001d2ea  mov     [rsp+78h+var_48], r11
0x14001d2ef  jmp     short loc_14001D2AE
0x14001d2f1  mov     [rdi+8], ebx
0x14001d2f4  xor     eax, eax
0x14001d2f6  jmp     short loc_14001D303
0x14001d2f8  mov     dword ptr [rdi+8], 0
0x14001d2ff  xor     eax, eax
0x14001d301  jmp     short $+2
0x14001d303  add     rsp, 48h
0x14001d307  pop     r15
0x14001d309  pop     r14
0x14001d30b  pop     r12
0x14001d30d  pop     rdi
0x14001d30e  pop     rsi
0x14001d30f  pop     rbx
0x14001d310  retn
```
