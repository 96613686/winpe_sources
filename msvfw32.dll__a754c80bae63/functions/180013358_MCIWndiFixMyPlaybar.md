# MCIWndiFixMyPlaybar

- ea: `0x180013358`
- end: `0x1800134cd`
- name: `MCIWndiFixMyPlaybar`
- size: `373`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180012da8`
- `0x180012f08`
- `0x180013edc`

## callees

- `0x180013358`
- `0x1800145dc`

## import_xrefs

- `USER32!SendMessageW` at `0x1800133aa`
- `USER32!SendMessageW` at `0x1800133bc`
- `USER32!SendMessageW` at `0x1800133ce`
- `USER32!SendMessageW` at `0x1800133df`
- `USER32!SendMessageW` at `0x1800133f0`
- `USER32!SendMessageW` at `0x180013407`
- `USER32!SendMessageW` at `0x18001341d`
- `USER32!SendMessageW` at `0x180013433`
- `USER32!SendMessageW` at `0x180013455`
- `USER32!SendMessageW` at `0x18001347a`
- `USER32!SendMessageW` at `0x180013496`
- `USER32!SendMessageW` at `0x1800134af`
- `USER32!SendMessageW` at `0x1800133aa`
- `USER32!SendMessageW` at `0x1800133bc`
- `USER32!SendMessageW` at `0x1800133ce`
- `USER32!SendMessageW` at `0x1800133df`
- `USER32!SendMessageW` at `0x1800133f0`
- `USER32!SendMessageW` at `0x180013407`
- `USER32!SendMessageW` at `0x18001341d`
- `USER32!SendMessageW` at `0x180013433`
- `USER32!SendMessageW` at `0x180013455`
- `USER32!SendMessageW` at `0x18001347a`
- `USER32!SendMessageW` at `0x180013496`
- `USER32!SendMessageW` at `0x1800134af`

## pseudocode

```c
LRESULT __fastcall MCIWndiFixMyPlaybar(__int64 a1)
{
  HWND *v2; // rdi
  LRESULT result; // rax
  LPARAM v4; // r9

  if ( (*(_BYTE *)(a1 + 32) & 2) == 0 )
  {
    v2 = (HWND *)(a1 + 192);
    if ( !*(_DWORD *)(a1 + 20) )
    {
      SendMessageW(*v2, 0x404u, 0x806u, 0);
      SendMessageW(*v2, 0x401u, 0x806u, 0);
      SendMessageW(*v2, 0x404u, 0x808u, 1);
      SendMessageW(*v2, 0x404u, 0x80Fu, 1);
      SendMessageW(*v2, 0x404u, 0x6Cu, 1);
      SendMessageW(*v2, 0x404u, 0x6Bu, *(_DWORD *)(a1 + 32) & 8);
      SendMessageW(*(HWND *)(a1 + 200), 0x405u, 1u, 0);
      result = SendMessageW(*(HWND *)(a1 + 200), 0x406u, 0, 0);
    }
    if ( *(_DWORD *)(a1 + 20) )
    {
      SendMessageW(*v2, 0x404u, 0x806u, *(_DWORD *)(a1 + 72) == 0);
      v4 = !*(_DWORD *)(a1 + 68) || (*(_DWORD *)(a1 + 32) & 0x2000) == 0;
      SendMessageW(*v2, 0x404u, 0x80Fu, v4);
      SendMessageW(*v2, 0x404u, 0x6Cu, *(_DWORD *)(a1 + 80) == 0);
      SendMessageW(*v2, 0x404u, 0x6Bu, *(_DWORD *)(a1 + 32) & 8);
      return MCIWndiPlaybarGraying(a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013358  push    rbx
0x18001335a  push    rsi
0x18001335b  push    rdi
0x18001335c  push    r12
0x18001335e  push    r13
0x180013360  push    r14
0x180013362  push    r15
0x180013364  sub     rsp, 20h
0x180013368  test    byte ptr [rcx+20h], 2
0x18001336c  mov     rbx, rcx
0x18001336f  jnz     loc_1800134BD
0x180013375  cmp     dword ptr [rcx+14h], 0
0x180013379  lea     rdi, [rcx+0C0h]
0x180013380  mov     r15d, 806h
0x180013386  mov     r14d, 1
0x18001338c  mov     esi, 404h
0x180013391  lea     r12d, [r15+9]
0x180013395  lea     r13d, [r14+6Bh]
0x180013399  jnz     loc_180013439
0x18001339f  mov     rcx, [rdi]; hWnd
0x1800133a2  xor     r9d, r9d; lParam
0x1800133a5  mov     r8d, r15d; wParam
0x1800133a8  mov     edx, esi; Msg
0x1800133aa  call    cs:__imp_SendMessageW
0x1800133b0  mov     rcx, [rdi]; hWnd
0x1800133b3  lea     edx, [rsi-3]; Msg
0x1800133b6  xor     r9d, r9d; lParam
0x1800133b9  mov     r8d, r15d; wParam
0x1800133bc  call    cs:__imp_SendMessageW
0x1800133c2  mov     rcx, [rdi]; hWnd
0x1800133c5  lea     r8d, [r15+2]; wParam
0x1800133c9  mov     r9d, r14d; lParam
0x1800133cc  mov     edx, esi; Msg
0x1800133ce  call    cs:__imp_SendMessageW
0x1800133d4  mov     rcx, [rdi]; hWnd
0x1800133d7  mov     r9d, r14d; lParam
0x1800133da  mov     r8d, r12d; wParam
0x1800133dd  mov     edx, esi; Msg
0x1800133df  call    cs:__imp_SendMessageW
0x1800133e5  mov     rcx, [rdi]; hWnd
0x1800133e8  mov     r9d, r14d; lParam
0x1800133eb  mov     r8d, r13d; wParam
0x1800133ee  mov     edx, esi; Msg
0x1800133f0  call    cs:__imp_SendMessageW
0x1800133f6  mov     r9d, [rbx+20h]
0x1800133fa  lea     r8d, [r14+6Ah]; wParam
0x1800133fe  mov     rcx, [rdi]; hWnd
0x180013401  and     r9d, 8; lParam
0x180013405  mov     edx, esi; Msg
0x180013407  call    cs:__imp_SendMessageW
0x18001340d  mov     rcx, [rbx+0C8h]; hWnd
0x180013414  lea     edx, [rsi+1]; Msg
0x180013417  xor     r9d, r9d; lParam
0x18001341a  mov     r8d, r14d; wParam
0x18001341d  call    cs:__imp_SendMessageW
0x180013423  mov     rcx, [rbx+0C8h]; hWnd
0x18001342a  lea     edx, [rsi+2]; Msg
0x18001342d  xor     r9d, r9d; lParam
0x180013430  xor     r8d, r8d; wParam
0x180013433  call    cs:__imp_SendMessageW
0x180013439  cmp     dword ptr [rbx+14h], 0
0x18001343d  jz      short loc_1800134BD
0x18001343f  cmp     dword ptr [rbx+48h], 0
0x180013443  mov     r8, r15; wParam
0x180013446  mov     rcx, [rdi]; hWnd
0x180013449  mov     edx, esi; Msg
0x18001344b  jz      short loc_180013452
0x18001344d  xor     r9d, r9d
0x180013450  jmp     short loc_180013455
0x180013452  mov     r9, r14; lParam
0x180013455  call    cs:__imp_SendMessageW
0x18001345b  cmp     dword ptr [rbx+44h], 0
0x18001345f  jz      short loc_18001346F
0x180013461  test    dword ptr [rbx+20h], 2000h
0x180013468  jz      short loc_18001346F
0x18001346a  xor     r9d, r9d
0x18001346d  jmp     short loc_180013472
0x18001346f  mov     r9, r14; lParam
0x180013472  mov     rcx, [rdi]; hWnd
0x180013475  mov     r8, r12; wParam
0x180013478  mov     edx, esi; Msg
0x18001347a  call    cs:__imp_SendMessageW
0x180013480  cmp     dword ptr [rbx+50h], 0
0x180013484  mov     r8, r13; wParam
0x180013487  mov     rcx, [rdi]; hWnd
0x18001348a  mov     edx, esi; Msg
0x18001348c  jz      short loc_180013493
0x18001348e  xor     r9d, r9d
0x180013491  jmp     short loc_180013496
0x180013493  mov     r9, r14; lParam
0x180013496  call    cs:__imp_SendMessageW
0x18001349c  mov     r9d, [rbx+20h]
0x1800134a0  mov     r8d, 6Bh ; 'k'; wParam
0x1800134a6  mov     rcx, [rdi]; hWnd
0x1800134a9  and     r9d, 8; lParam
0x1800134ad  mov     edx, esi; Msg
0x1800134af  call    cs:__imp_SendMessageW
0x1800134b5  mov     rcx, rbx
0x1800134b8  call    MCIWndiPlaybarGraying
0x1800134bd  add     rsp, 20h
0x1800134c1  pop     r15
0x1800134c3  pop     r14
0x1800134c5  pop     r13
0x1800134c7  pop     r12
0x1800134c9  pop     rdi
0x1800134ca  pop     rsi
0x1800134cb  pop     rbx
0x1800134cc  retn
```
