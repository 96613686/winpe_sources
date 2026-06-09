# MCIWndiValidateMedia

- ea: `0x180015124`
- end: `0x18001522e`
- name: `MCIWndiValidateMedia`
- size: `266`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180010cc0`
- `0x180013c60`
- `0x180013edc`
- `0x180014fbc`

## callees

- `0x180012cdc`
- `0x180013e48`
- `0x180015124`

## import_xrefs

- `USER32!SendMessageW` at `0x180015164`
- `USER32!SendMessageW` at `0x18001517e`
- `USER32!SendMessageW` at `0x1800151af`
- `USER32!SendMessageW` at `0x1800151ce`
- `USER32!SendMessageW` at `0x1800151ea`
- `USER32!SendMessageW` at `0x18001520d`
- `USER32!SendMessageW` at `0x180015164`
- `USER32!SendMessageW` at `0x18001517e`
- `USER32!SendMessageW` at `0x1800151af`
- `USER32!SendMessageW` at `0x1800151ce`
- `USER32!SendMessageW` at `0x1800151ea`
- `USER32!SendMessageW` at `0x18001520d`

## pseudocode

```c
void __fastcall MCIWndiValidateMedia(__int64 a1)
{
  int v2; // ebx
  int v3; // eax
  HWND v4; // rcx
  int v5; // eax

  if ( *(_DWORD *)(a1 + 20) )
  {
    v2 = *(_DWORD *)(a1 + 212);
    *(_DWORD *)(a1 + 136) = 1;
    v3 = SendMessageW(*(HWND *)a1, 0x467u, 0, 0);
    v4 = *(HWND *)a1;
    *(_DWORD *)(a1 + 208) = v3;
    v5 = SendMessageW(v4, 0x468u, 0, 0);
    *(_DWORD *)(a1 + 212) = v5;
    if ( v2 != v5 && (*(_BYTE *)(a1 + 32) & 2) == 0 )
    {
      SendMessageW(*(HWND *)(a1 + 200), 0x409u, 1u, 0);
      SendMessageW(*(HWND *)(a1 + 200), 0x405u, 1u, *(unsigned int *)(a1 + 208));
      SendMessageW(*(HWND *)(a1 + 200), 0x407u, 0, *(unsigned int *)(a1 + 208));
      SendMessageW(*(HWND *)(a1 + 200), 0x408u, 0, (unsigned int)(*(_DWORD *)(a1 + 212) + *(_DWORD *)(a1 + 208)));
      MCIWndiCalcTracks(a1);
      MCIWndiMarkTics(a1);
    }
  }
  else
  {
    *(_DWORD *)(a1 + 136) = 0;
  }
}

```

## disassembly

```asm
0x180015124  mov     [rsp+arg_0], rbx
0x180015129  push    rdi
0x18001512a  sub     rsp, 20h
0x18001512e  cmp     dword ptr [rcx+14h], 0
0x180015132  mov     rdi, rcx
0x180015135  jnz     short loc_180015146
0x180015137  mov     dword ptr [rcx+88h], 0
0x180015141  jmp     loc_180015223
0x180015146  mov     ebx, [rcx+0D4h]
0x18001514c  xor     r9d, r9d; lParam
0x18001514f  mov     dword ptr [rcx+88h], 1
0x180015159  xor     r8d, r8d; wParam
0x18001515c  mov     rcx, [rcx]; hWnd
0x18001515f  mov     edx, 467h; Msg
0x180015164  call    cs:__imp_SendMessageW
0x18001516a  mov     rcx, [rdi]; hWnd
0x18001516d  xor     r9d, r9d; lParam
0x180015170  xor     r8d, r8d; wParam
0x180015173  mov     [rdi+0D0h], eax
0x180015179  mov     edx, 468h; Msg
0x18001517e  call    cs:__imp_SendMessageW
0x180015184  mov     [rdi+0D4h], eax
0x18001518a  cmp     ebx, eax
0x18001518c  jz      loc_180015223
0x180015192  test    byte ptr [rdi+20h], 2
0x180015196  jnz     loc_180015223
0x18001519c  mov     rcx, [rdi+0C8h]; hWnd
0x1800151a3  xor     r9d, r9d; lParam
0x1800151a6  mov     edx, 409h; Msg
0x1800151ab  lea     r8d, [r9+1]; wParam
0x1800151af  call    cs:__imp_SendMessageW
0x1800151b5  mov     r9d, [rdi+0D0h]; lParam
0x1800151bc  mov     edx, 405h; Msg
0x1800151c1  mov     rcx, [rdi+0C8h]; hWnd
0x1800151c8  mov     r8d, 1; wParam
0x1800151ce  call    cs:__imp_SendMessageW
0x1800151d4  mov     r9d, [rdi+0D0h]; lParam
0x1800151db  xor     r8d, r8d; wParam
0x1800151de  mov     rcx, [rdi+0C8h]; hWnd
0x1800151e5  mov     edx, 407h; Msg
0x1800151ea  call    cs:__imp_SendMessageW
0x1800151f0  mov     r9d, [rdi+0D0h]
0x1800151f7  xor     r8d, r8d; wParam
0x1800151fa  add     r9d, [rdi+0D4h]; lParam
0x180015201  mov     edx, 408h; Msg
0x180015206  mov     rcx, [rdi+0C8h]; hWnd
0x18001520d  call    cs:__imp_SendMessageW
0x180015213  mov     rcx, rdi
0x180015216  call    MCIWndiCalcTracks
0x18001521b  mov     rcx, rdi
0x18001521e  call    MCIWndiMarkTics
0x180015223  mov     rbx, [rsp+28h+arg_0]
0x180015228  add     rsp, 20h
0x18001522c  pop     rdi
0x18001522d  retn
```
