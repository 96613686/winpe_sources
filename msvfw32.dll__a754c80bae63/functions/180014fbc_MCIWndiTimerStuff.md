# MCIWndiTimerStuff

- ea: `0x180014fbc`
- end: `0x18001511e`
- name: `MCIWndiTimerStuff`
- size: `354`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180010194`
- `0x180010cc0`
- `0x180016050`

## callees

- `0x1800145dc`
- `0x180014adc`
- `0x180014fbc`
- `0x180015124`

## import_xrefs

- `USER32!SendMessageW` at `0x180014fe8`
- `USER32!SendMessageW` at `0x180015055`
- `USER32!SendMessageW` at `0x180015090`
- `USER32!SendMessageW` at `0x1800150cc`
- `USER32!SendMessageW` at `0x18001510d`
- `USER32!SendMessageW` at `0x180014fe8`
- `USER32!SendMessageW` at `0x180015055`
- `USER32!SendMessageW` at `0x180015090`
- `USER32!SendMessageW` at `0x1800150cc`
- `USER32!SendMessageW` at `0x18001510d`
- `USER32!KillTimer` at `0x180015024`
- `USER32!KillTimer` at `0x180015024`

## pseudocode

```c
void __fastcall MCIWndiTimerStuff(__int64 a1)
{
  unsigned int v2; // edi
  int v3; // ecx
  bool v4; // zf
  HWND v5; // rcx
  unsigned int v6; // edi
  HWND v7; // rcx

  if ( (*(_DWORD *)(a1 + 32) & 0x142) != 2 )
  {
    v2 = SendMessageW(*(HWND *)a1, 0x4CEu, 0, 0);
    if ( v2 - 524 > 6 || (v3 = 73, !_bittest(&v3, v2 - 524)) )
    {
      if ( !*(_DWORD *)(a1 + 136) )
        MCIWndiValidateMedia(a1);
    }
    if ( !*(_DWORD *)(a1 + 20) )
      KillTimer(*(HWND *)a1, 0x2Au);
    if ( v2 != *(_DWORD *)(a1 + 224) )
    {
      v4 = (*(_DWORD *)(a1 + 32) & 0x100) == 0;
      *(_DWORD *)(a1 + 224) = v2;
      if ( !v4 )
      {
        v5 = *(HWND *)(a1 + 8);
        if ( v5 )
          SendMessageW(v5, 0x4C8u, *(_QWORD *)a1, v2);
      }
      if ( (*(_BYTE *)(a1 + 32) & 0x40) != 0 )
        MCIWndiSetCaption(a1);
      MCIWndiPlaybarGraying(a1);
    }
  }
  if ( (*(_DWORD *)(a1 + 32) & 0x222) != 2 )
  {
    v6 = SendMessageW(*(HWND *)a1, 0x4CAu, 0, 0);
    if ( v6 != *(_DWORD *)(a1 + 228) )
    {
      MCIWndiValidateMedia(a1);
      v4 = (*(_DWORD *)(a1 + 32) & 0x200) == 0;
      *(_DWORD *)(a1 + 228) = v6;
      if ( !v4 )
      {
        v7 = *(HWND *)(a1 + 8);
        if ( v7 )
          SendMessageW(v7, 0x4C9u, *(_QWORD *)a1, v6);
      }
      if ( (*(_BYTE *)(a1 + 32) & 0x20) != 0 )
        MCIWndiSetCaption(a1);
      if ( (*(_BYTE *)(a1 + 32) & 2) == 0 && !*(_DWORD *)(a1 + 108) && *(_DWORD *)(a1 + 224) != 528 )
        SendMessageW(*(HWND *)(a1 + 200), 0x405u, 1u, v6);
    }
  }
}

```

## disassembly

```asm
0x180014fbc  mov     [rsp+arg_0], rbx
0x180014fc1  push    rdi
0x180014fc2  sub     rsp, 20h
0x180014fc6  mov     eax, [rcx+20h]
0x180014fc9  mov     rbx, rcx
0x180014fcc  and     eax, 142h
0x180014fd1  cmp     eax, 2
0x180014fd4  jz      loc_180015071
0x180014fda  mov     rcx, [rcx]; hWnd
0x180014fdd  xor     r9d, r9d; lParam
0x180014fe0  xor     r8d, r8d; wParam
0x180014fe3  mov     edx, 4CEh; Msg
0x180014fe8  call    cs:__imp_SendMessageW
0x180014fee  mov     rdi, rax
0x180014ff1  add     eax, 0FFFFFDF4h
0x180014ff6  cmp     eax, 6
0x180014ff9  ja      short loc_180015005
0x180014ffb  mov     ecx, 49h ; 'I'
0x180015000  bt      ecx, eax
0x180015003  jb      short loc_180015016
0x180015005  cmp     dword ptr [rbx+88h], 0
0x18001500c  jnz     short loc_180015016
0x18001500e  mov     rcx, rbx
0x180015011  call    MCIWndiValidateMedia
0x180015016  cmp     dword ptr [rbx+14h], 0
0x18001501a  jnz     short loc_18001502A
0x18001501c  mov     rcx, [rbx]; hWnd
0x18001501f  mov     edx, 2Ah ; '*'; uIDEvent
0x180015024  call    cs:__imp_KillTimer
0x18001502a  cmp     edi, [rbx+0E0h]
0x180015030  jz      short loc_180015071
0x180015032  test    dword ptr [rbx+20h], 100h
0x180015039  mov     [rbx+0E0h], edi
0x18001503f  jz      short loc_18001505B
0x180015041  mov     rcx, [rbx+8]; hWnd
0x180015045  test    rcx, rcx
0x180015048  jz      short loc_18001505B
0x18001504a  mov     r8, [rbx]; wParam
0x18001504d  mov     edx, 4C8h; Msg
0x180015052  mov     r9d, edi; lParam
0x180015055  call    cs:__imp_SendMessageW
0x18001505b  test    byte ptr [rbx+20h], 40h
0x18001505f  jz      short loc_180015069
0x180015061  mov     rcx, rbx
0x180015064  call    MCIWndiSetCaption
0x180015069  mov     rcx, rbx
0x18001506c  call    MCIWndiPlaybarGraying
0x180015071  mov     eax, [rbx+20h]
0x180015074  and     eax, 222h
0x180015079  cmp     eax, 2
0x18001507c  jz      loc_180015113
0x180015082  mov     rcx, [rbx]; hWnd
0x180015085  xor     r9d, r9d; lParam
0x180015088  xor     r8d, r8d; wParam
0x18001508b  mov     edx, 4CAh; Msg
0x180015090  call    cs:__imp_SendMessageW
0x180015096  mov     rdi, rax
0x180015099  cmp     eax, [rbx+0E4h]
0x18001509f  jz      short loc_180015113
0x1800150a1  mov     rcx, rbx
0x1800150a4  call    MCIWndiValidateMedia
0x1800150a9  test    dword ptr [rbx+20h], 200h
0x1800150b0  mov     [rbx+0E4h], edi
0x1800150b6  jz      short loc_1800150D2
0x1800150b8  mov     rcx, [rbx+8]; hWnd
0x1800150bc  test    rcx, rcx
0x1800150bf  jz      short loc_1800150D2
0x1800150c1  mov     r8, [rbx]; wParam
0x1800150c4  mov     edx, 4C9h; Msg
0x1800150c9  mov     r9d, edi; lParam
0x1800150cc  call    cs:__imp_SendMessageW
0x1800150d2  test    byte ptr [rbx+20h], 20h
0x1800150d6  jz      short loc_1800150E0
0x1800150d8  mov     rcx, rbx
0x1800150db  call    MCIWndiSetCaption
0x1800150e0  test    byte ptr [rbx+20h], 2
0x1800150e4  jnz     short loc_180015113
0x1800150e6  cmp     dword ptr [rbx+6Ch], 0
0x1800150ea  jnz     short loc_180015113
0x1800150ec  cmp     dword ptr [rbx+0E0h], 210h
0x1800150f6  jz      short loc_180015113
0x1800150f8  mov     rcx, [rbx+0C8h]; hWnd
0x1800150ff  mov     edx, 405h; Msg
0x180015104  mov     r9d, edi; lParam
0x180015107  mov     r8d, 1; wParam
0x18001510d  call    cs:__imp_SendMessageW
0x180015113  mov     rbx, [rsp+28h+arg_0]
0x180015118  add     rsp, 20h
0x18001511c  pop     rdi
0x18001511d  retn
```
