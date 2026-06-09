# MCIWndRect

- ea: `0x1800127bc`
- end: `0x18001285a`
- name: `MCIWndRect`
- size: `158`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f704`
- `0x18000fe2c`
- `0x180010cc0`
- `0x180014cc8`

## callees

- `0x1800014b0`
- `0x1800127bc`

## import_xrefs

- `USER32!SetRectEmpty` at `0x1800127f5`
- `USER32!SetRectEmpty` at `0x1800127f5`
- `WINMM!mciSendCommandW` at `0x18001281f`
- `WINMM!mciSendCommandW` at `0x18001281f`

## pseudocode

```c
__int64 __fastcall MCIWndRect(__int64 a1, struct tagRECT *a2, int a3)
{
  MCIDEVICEID v6; // ecx
  __int64 result; // rax
  DWORD_PTR dwParam2[3]; // [rsp+20h] [rbp-28h] BYREF

  memset(dwParam2, 0, sizeof(dwParam2));
  SetRectEmpty(a2);
  v6 = *(_DWORD *)(a1 + 20);
  if ( v6 && !mciSendCommandW(v6, 0x843u, (-(__int64)(a3 != 0) & 0xFFFFFFFFFFFE0000uLL) + 0x40000, (DWORD_PTR)dwParam2) )
    *a2 = *(struct tagRECT *)&dwParam2[1];
  a2->right += a2->left;
  result = (unsigned int)a2->top;
  a2->bottom += result;
  return result;
}

```

## disassembly

```asm
0x1800127bc  mov     [rsp+arg_10], rbx
0x1800127c1  mov     [rsp+arg_18], rsi
0x1800127c6  push    rdi
0x1800127c7  sub     rsp, 40h
0x1800127cb  mov     rax, cs:__security_cookie
0x1800127d2  xor     rax, rsp
0x1800127d5  mov     [rsp+48h+var_10], rax
0x1800127da  mov     rbx, rcx
0x1800127dd  xorps   xmm0, xmm0
0x1800127e0  xor     eax, eax
0x1800127e2  mov     rcx, rdx; lprc
0x1800127e5  movups  xmmword ptr [rsp+48h+dwParam2], xmm0
0x1800127ea  mov     [rsp+48h+var_18], rax
0x1800127ef  mov     esi, r8d
0x1800127f2  mov     rdi, rdx
0x1800127f5  call    cs:__imp_SetRectEmpty
0x1800127fb  mov     ecx, [rbx+14h]; mciId
0x1800127fe  test    ecx, ecx
0x180012800  jz      short loc_180012832
0x180012802  neg     esi
0x180012804  lea     r9, [rsp+48h+dwParam2]; dwParam2
0x180012809  mov     edx, 843h; uMsg
0x18001280e  sbb     r8, r8
0x180012811  and     r8, 0FFFFFFFFFFFE0000h
0x180012818  add     r8, 40000h; dwParam1
0x18001281f  call    cs:__imp_mciSendCommandW
0x180012825  test    eax, eax
0x180012827  jnz     short loc_180012832
0x180012829  movups  xmm0, xmmword ptr [rsp+48h+dwParam2+8]
0x18001282e  movdqu  xmmword ptr [rdi], xmm0
0x180012832  mov     eax, [rdi]
0x180012834  add     [rdi+8], eax
0x180012837  mov     eax, [rdi+4]
0x18001283a  add     [rdi+0Ch], eax
0x18001283d  mov     rcx, [rsp+48h+var_10]
0x180012842  xor     rcx, rsp; StackCookie
0x180012845  call    __security_check_cookie
0x18001284a  mov     rbx, [rsp+48h+arg_10]
0x18001284f  mov     rsi, [rsp+48h+arg_18]
0x180012854  add     rsp, 40h
0x180012858  pop     rdi
0x180012859  retn
```
