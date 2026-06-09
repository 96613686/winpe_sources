# CAdvanced::UpdateDisplay(void)

- ea: `0x180009de8`
- end: `0x180009fc7`
- name: `?UpdateDisplay@CAdvanced@@AEAAXXZ`
- size: `479`
- prototype: `void __fastcall(CAdvanced *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18000994c`

## callees

- `0x180001fec`
- `0x1800099f0`
- `0x180009de8`
- `0x180009fd0`

## import_xrefs

- `USER32!SendMessageW` at `0x180009e0f`
- `USER32!SendMessageW` at `0x180009e33`
- `USER32!SendMessageW` at `0x180009e68`
- `USER32!SendMessageW` at `0x180009e0f`
- `USER32!SendMessageW` at `0x180009e33`
- `USER32!SendMessageW` at `0x180009e68`
- `USER32!ShowWindow` at `0x180009ed2`
- `USER32!ShowWindow` at `0x180009ee4`
- `USER32!ShowWindow` at `0x180009ef3`
- `USER32!ShowWindow` at `0x180009f02`
- `USER32!ShowWindow` at `0x180009f53`
- `USER32!ShowWindow` at `0x180009f65`
- `USER32!ShowWindow` at `0x180009f84`
- `USER32!ShowWindow` at `0x180009f90`
- `USER32!ShowWindow` at `0x180009fa2`
- `USER32!ShowWindow` at `0x180009ed2`
- `USER32!ShowWindow` at `0x180009ee4`
- `USER32!ShowWindow` at `0x180009ef3`
- `USER32!ShowWindow` at `0x180009f02`
- `USER32!ShowWindow` at `0x180009f53`
- `USER32!ShowWindow` at `0x180009f65`
- `USER32!ShowWindow` at `0x180009f84`
- `USER32!ShowWindow` at `0x180009f90`
- `USER32!ShowWindow` at `0x180009fa2`

## pseudocode

```c
void __fastcall CAdvanced::UpdateDisplay(CAdvanced *this)
{
  int v2; // edi
  int v3; // esi
  void *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  HWND v7; // rcx
  HWND *v8; // rcx
  int v9; // edx
  HWND v10; // rcx
  int v11; // edx

  v2 = 0;
  v3 = SendMessageW(**((HWND **)this + 18), 0x146u, 0, 0);
  if ( v3 > 0 )
  {
    do
    {
      v4 = (void *)SendMessageW(**((HWND **)this + 18), 0x150u, (unsigned int)v2, 0);
      operator delete(v4);
      ++v2;
    }
    while ( v2 < v3 );
  }
  v5 = *((_QWORD *)this + 18);
  *(_DWORD *)(v5 + 8) = 0;
  SendMessageW(*(HWND *)v5, 0x14Bu, 0, 0);
  v6 = *((_QWORD *)this + 3);
  if ( *(_DWORD *)(v6 + 204) != 4 )
  {
    if ( *(_DWORD *)(v6 + 204) == 5 )
    {
      *((_DWORD *)this + 49) = 2;
      goto LABEL_12;
    }
    if ( *(_DWORD *)(v6 + 204) != 6 )
    {
      if ( *(_DWORD *)(v6 + 204) == 7 )
      {
        *((_DWORD *)this + 49) = 4;
        goto LABEL_12;
      }
      goto LABEL_11;
    }
LABEL_10:
    *((_DWORD *)this + 49) = 3;
    goto LABEL_12;
  }
  if ( *(_DWORD *)(v6 + 152) > 0x7FFFFFFFu )
    goto LABEL_10;
LABEL_11:
  *((_DWORD *)this + 49) = 1;
LABEL_12:
  ShowWindow(**((HWND **)this + 17), 0);
  ShowWindow(**((HWND **)this + 18), 0);
  ShowWindow(*((HWND *)this + 21), 0);
  ShowWindow(*((HWND *)this + 22), 0);
  switch ( *((_DWORD *)this + 49) )
  {
    case 1:
      ShowWindow(**((HWND **)this + 17), 5);
      v7 = (HWND)*((_QWORD *)this + 21);
LABEL_21:
      v9 = 1;
      goto LABEL_22;
    case 2:
      v8 = (HWND *)*((_QWORD *)this + 18);
      break;
    case 3:
      v8 = (HWND *)*((_QWORD *)this + 17);
      break;
    case 4:
      v7 = (HWND)*((_QWORD *)this + 22);
      goto LABEL_21;
    default:
      goto LABEL_23;
  }
  v7 = *v8;
  v9 = 5;
LABEL_22:
  ShowWindow(v7, v9);
LABEL_23:
  v10 = (HWND)**((_QWORD **)this + 19);
  if ( *(_DWORD *)(*((_QWORD *)this + 3) + 256LL) )
  {
    ShowWindow(v10, 5);
    v11 = 5;
  }
  else
  {
    ShowWindow(v10, 0);
    v11 = 0;
  }
  ShowWindow(**((HWND **)this + 20), v11);
  CAdvanced::SetParamRange(this);
  CAdvanced::UpdateParamDisplay(this);
}

```

## disassembly

```asm
0x180009de8  mov     [rsp+arg_0], rbx
0x180009ded  mov     [rsp+arg_8], rsi
0x180009df2  push    rdi
0x180009df3  sub     rsp, 20h
0x180009df7  mov     rbx, rcx
0x180009dfa  xor     r9d, r9d; lParam
0x180009dfd  mov     rcx, [rcx+90h]
0x180009e04  xor     r8d, r8d; wParam
0x180009e07  mov     edx, 146h; Msg
0x180009e0c  mov     rcx, [rcx]; hWnd
0x180009e0f  call    cs:__imp_SendMessageW
0x180009e15  xor     edi, edi
0x180009e17  mov     rsi, rax
0x180009e1a  test    eax, eax
0x180009e1c  jle     short loc_180009E4C
0x180009e1e  mov     rcx, [rbx+90h]
0x180009e25  xor     r9d, r9d; lParam
0x180009e28  mov     r8d, edi; wParam
0x180009e2b  mov     edx, 150h; Msg
0x180009e30  mov     rcx, [rcx]; hWnd
0x180009e33  call    cs:__imp_SendMessageW
0x180009e39  mov     rcx, rax; void *
0x180009e3c  mov     edx, 2; unsigned __int64
0x180009e41  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009e46  inc     edi
0x180009e48  cmp     edi, esi
0x180009e4a  jl      short loc_180009E1E
0x180009e4c  mov     rcx, [rbx+90h]
0x180009e53  xor     r9d, r9d; lParam
0x180009e56  xor     r8d, r8d; wParam
0x180009e59  mov     edx, 14Bh; Msg
0x180009e5e  mov     dword ptr [rcx+8], 0
0x180009e65  mov     rcx, [rcx]; hWnd
0x180009e68  call    cs:__imp_SendMessageW
0x180009e6e  mov     rdx, [rbx+18h]
0x180009e72  mov     ecx, [rdx+0CCh]
0x180009e78  sub     ecx, 4
0x180009e7b  jz      short loc_180009EA4
0x180009e7d  sub     ecx, 1
0x180009e80  jz      short loc_180009E98
0x180009e82  sub     ecx, 1
0x180009e85  jz      short loc_180009EB0
0x180009e87  cmp     ecx, 1
0x180009e8a  jnz     short loc_180009EBC
0x180009e8c  mov     dword ptr [rbx+0C4h], 4
0x180009e96  jmp     short loc_180009EC6
0x180009e98  mov     dword ptr [rbx+0C4h], 2
0x180009ea2  jmp     short loc_180009EC6
0x180009ea4  cmp     dword ptr [rdx+98h], 7FFFFFFFh
0x180009eae  jbe     short loc_180009EBC
0x180009eb0  mov     dword ptr [rbx+0C4h], 3
0x180009eba  jmp     short loc_180009EC6
0x180009ebc  mov     dword ptr [rbx+0C4h], 1
0x180009ec6  mov     rcx, [rbx+88h]
0x180009ecd  xor     edx, edx; nCmdShow
0x180009ecf  mov     rcx, [rcx]; hWnd
0x180009ed2  call    cs:__imp_ShowWindow
0x180009ed8  mov     rcx, [rbx+90h]
0x180009edf  xor     edx, edx; nCmdShow
0x180009ee1  mov     rcx, [rcx]; hWnd
0x180009ee4  call    cs:__imp_ShowWindow
0x180009eea  mov     rcx, [rbx+0A8h]; hWnd
0x180009ef1  xor     edx, edx; nCmdShow
0x180009ef3  call    cs:__imp_ShowWindow
0x180009ef9  mov     rcx, [rbx+0B0h]; hWnd
0x180009f00  xor     edx, edx; nCmdShow
0x180009f02  call    cs:__imp_ShowWindow
0x180009f08  mov     ecx, [rbx+0C4h]
0x180009f0e  mov     edi, 5
0x180009f13  sub     ecx, 1
0x180009f16  jz      short loc_180009F47
0x180009f18  sub     ecx, 1
0x180009f1b  jz      short loc_180009F3E
0x180009f1d  sub     ecx, 1
0x180009f20  jz      short loc_180009F30
0x180009f22  cmp     ecx, 1
0x180009f25  jnz     short loc_180009F6B
0x180009f27  mov     rcx, [rbx+0B0h]
0x180009f2e  jmp     short loc_180009F60
0x180009f30  mov     rcx, [rbx+88h]
0x180009f37  mov     rcx, [rcx]
0x180009f3a  mov     edx, edi
0x180009f3c  jmp     short loc_180009F65
0x180009f3e  mov     rcx, [rbx+90h]
0x180009f45  jmp     short loc_180009F37
0x180009f47  mov     rcx, [rbx+88h]
0x180009f4e  mov     edx, edi; nCmdShow
0x180009f50  mov     rcx, [rcx]; hWnd
0x180009f53  call    cs:__imp_ShowWindow
0x180009f59  mov     rcx, [rbx+0A8h]; hWnd
0x180009f60  mov     edx, 1; nCmdShow
0x180009f65  call    cs:__imp_ShowWindow
0x180009f6b  mov     rax, [rbx+98h]
0x180009f72  mov     rcx, [rax]; hWnd
0x180009f75  mov     rax, [rbx+18h]
0x180009f79  cmp     dword ptr [rax+100h], 0
0x180009f80  jz      short loc_180009F8E
0x180009f82  mov     edx, edi; nCmdShow
0x180009f84  call    cs:__imp_ShowWindow
0x180009f8a  mov     edx, edi
0x180009f8c  jmp     short loc_180009F98
0x180009f8e  xor     edx, edx; nCmdShow
0x180009f90  call    cs:__imp_ShowWindow
0x180009f96  xor     edx, edx; nCmdShow
0x180009f98  mov     rcx, [rbx+0A0h]
0x180009f9f  mov     rcx, [rcx]; hWnd
0x180009fa2  call    cs:__imp_ShowWindow
0x180009fa8  mov     rcx, rbx; this
0x180009fab  call    ?SetParamRange@CAdvanced@@AEAAXXZ; CAdvanced::SetParamRange(void)
0x180009fb0  mov     rcx, rbx; this
0x180009fb3  mov     rbx, [rsp+28h+arg_0]
0x180009fb8  mov     rsi, [rsp+28h+arg_8]
0x180009fbd  add     rsp, 20h
0x180009fc1  pop     rdi
0x180009fc2  jmp     ?UpdateParamDisplay@CAdvanced@@AEAAXXZ; CAdvanced::UpdateParamDisplay(void)
```
