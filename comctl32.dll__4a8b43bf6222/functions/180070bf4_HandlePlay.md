# HandlePlay

- ea: `0x180070bf4`
- end: `0x180070d27`
- name: `HandlePlay`
- size: `307`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180070360`

## callees

- `0x180070bf4`
- `0x180070d30`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180070c96`
- `KERNEL32!CreateEventW` at `0x180070c96`
- `KERNEL32!CreateThread` at `0x180070cc3`
- `KERNEL32!CreateThread` at `0x180070cc3`
- `USER32!InvalidateRect` at `0x180070c6f`
- `USER32!InvalidateRect` at `0x180070d0f`
- `USER32!InvalidateRect` at `0x180070c6f`
- `USER32!InvalidateRect` at `0x180070d0f`
- `USER32!UpdateWindow` at `0x180070c78`
- `USER32!UpdateWindow` at `0x180070c78`
- `USER32!PostMessageW` at `0x180070ce6`
- `USER32!PostMessageW` at `0x180070ce6`
- `USER32!SetTimer` at `0x180070cfa`
- `USER32!SetTimer` at `0x180070cfa`

## pseudocode

```c
__int64 __fastcall HandlePlay(unsigned __int16 *lpParameter, int a2, int a3, int a4)
{
  int v8; // r10d
  int v9; // ecx
  int v10; // eax
  UINT_PTR v11; // rax
  HWND v12; // rcx
  DWORD ThreadId; // [rsp+60h] [rbp+8h] BYREF

  if ( !lpParameter || !*((_QWORD *)lpParameter + 4) )
    return 0;
  HandleStop(lpParameter);
  v8 = *((_DWORD *)lpParameter + 24);
  *((_DWORD *)lpParameter + 27) = a4;
  v9 = v8 - 1;
  if ( a2 >= v8 )
    a2 = v8 - 1;
  if ( a3 == -1 )
    a3 = v8 - 1;
  v10 = 0;
  if ( a3 >= 0 )
    v10 = a3;
  if ( v10 < v8 )
    v9 = v10;
  *((_DWORD *)lpParameter + 29) = v9;
  if ( a2 < 0 )
  {
    a2 = *((_DWORD *)lpParameter + 28);
  }
  else
  {
    *((_DWORD *)lpParameter + 26) = a2;
    *((_DWORD *)lpParameter + 28) = a2;
  }
  if ( a2 == v9 || !a4 )
  {
    InvalidateRect(*(HWND *)lpParameter, 0, 1);
  }
  else
  {
    InvalidateRect(*(HWND *)lpParameter, 0, 0);
    UpdateWindow(*(HWND *)lpParameter);
    if ( (lpParameter[12] & 8) != 0 )
    {
      v12 = (HWND)*((_QWORD *)lpParameter + 2);
      if ( v12 )
        PostMessageW(v12, 0x111u, lpParameter[4] | 0x10000LL, *(_QWORD *)lpParameter);
      v11 = SetTimer(*(HWND *)lpParameter, 0x2Au, *((_DWORD *)lpParameter + 25), 0);
    }
    else
    {
      ThreadId = 0;
      *((_QWORD *)lpParameter + 16) = CreateEventW(0, 0, 0, 0);
      v11 = (UINT_PTR)CreateThread(0, 0, PlayThread, lpParameter, 0, &ThreadId);
    }
    *((_QWORD *)lpParameter + 15) = v11;
  }
  return 1;
}

```

## disassembly

```asm
0x180070bf4  push    rbx
0x180070bf6  push    rbp
0x180070bf7  push    rsi
0x180070bf8  push    rdi
0x180070bf9  sub     rsp, 38h
0x180070bfd  mov     esi, r9d
0x180070c00  mov     ebp, r8d
0x180070c03  mov     edi, edx
0x180070c05  mov     rbx, rcx
0x180070c08  test    rcx, rcx
0x180070c0b  jz      loc_180070D1C
0x180070c11  cmp     qword ptr [rcx+20h], 0
0x180070c16  jz      loc_180070D1C
0x180070c1c  call    HandleStop
0x180070c21  mov     r10d, [rbx+60h]
0x180070c25  cmp     edi, r10d
0x180070c28  mov     [rbx+6Ch], esi
0x180070c2b  lea     ecx, [r10-1]
0x180070c2f  cmovge  edi, ecx
0x180070c32  cmp     ebp, 0FFFFFFFFh
0x180070c35  cmovz   ebp, ecx
0x180070c38  xor     eax, eax
0x180070c3a  test    ebp, ebp
0x180070c3c  cmovns  eax, ebp
0x180070c3f  cmp     eax, r10d
0x180070c42  cmovl   ecx, eax
0x180070c45  mov     [rbx+74h], ecx
0x180070c48  test    edi, edi
0x180070c4a  js      short loc_180070C54
0x180070c4c  mov     [rbx+68h], edi
0x180070c4f  mov     [rbx+70h], edi
0x180070c52  jmp     short loc_180070C57
0x180070c54  mov     edi, [rbx+70h]
0x180070c57  cmp     edi, ecx
0x180070c59  jz      loc_180070D06
0x180070c5f  test    esi, esi
0x180070c61  jz      loc_180070D06
0x180070c67  mov     rcx, [rbx]; hWnd
0x180070c6a  xor     r8d, r8d; bErase
0x180070c6d  xor     edx, edx; lpRect
0x180070c6f  call    cs:__imp_InvalidateRect
0x180070c75  mov     rcx, [rbx]; hWnd
0x180070c78  call    cs:__imp_UpdateWindow
0x180070c7e  test    byte ptr [rbx+18h], 8
0x180070c82  jnz     short loc_180070CCB
0x180070c84  xor     r9d, r9d; lpName
0x180070c87  mov     [rsp+58h+ThreadId], 0
0x180070c8f  xor     r8d, r8d; bInitialState
0x180070c92  xor     edx, edx; bManualReset
0x180070c94  xor     ecx, ecx; lpEventAttributes
0x180070c96  call    cs:__imp_CreateEventW
0x180070c9c  mov     [rbx+80h], rax
0x180070ca3  mov     r9, rbx; lpParameter
0x180070ca6  lea     r8, PlayThread; lpStartAddress
0x180070cad  xor     edx, edx; dwStackSize
0x180070caf  lea     rax, [rsp+58h+ThreadId]
0x180070cb4  xor     ecx, ecx; lpThreadAttributes
0x180070cb6  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180070cbb  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180070cc3  call    cs:__imp_CreateThread
0x180070cc9  jmp     short loc_180070D00
0x180070ccb  mov     rcx, [rbx+10h]; hWnd
0x180070ccf  test    rcx, rcx
0x180070cd2  jz      short loc_180070CEC
0x180070cd4  movzx   r8d, word ptr [rbx+8]
0x180070cd9  mov     edx, 111h; Msg
0x180070cde  mov     r9, [rbx]; lParam
0x180070ce1  bts     r8, 10h; wParam
0x180070ce6  call    cs:__imp_PostMessageW
0x180070cec  mov     r8d, [rbx+64h]; uElapse
0x180070cf0  xor     r9d, r9d; lpTimerFunc
0x180070cf3  mov     rcx, [rbx]; hWnd
0x180070cf6  lea     edx, [r9+2Ah]; nIDEvent
0x180070cfa  call    cs:__imp_SetTimer
0x180070d00  mov     [rbx+78h], rax
0x180070d04  jmp     short loc_180070D15
0x180070d06  mov     rcx, [rbx]; hWnd
0x180070d09  xor     edx, edx; lpRect
0x180070d0b  lea     r8d, [rdx+1]; bErase
0x180070d0f  call    cs:__imp_InvalidateRect
0x180070d15  mov     eax, 1
0x180070d1a  jmp     short loc_180070D1E
0x180070d1c  xor     eax, eax
0x180070d1e  add     rsp, 38h
0x180070d22  pop     rdi
0x180070d23  pop     rsi
0x180070d24  pop     rbp
0x180070d25  pop     rbx
0x180070d26  retn
```
