# DetermineSel2

- ea: `0x18001463c`
- end: `0x1800147ab`
- name: `DetermineSel2`
- size: `367`
- prototype: `__int64 __fastcall(HWND hWnd, __int64, int, __int64, int, __int64, int, _QWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e10`
- `0x180005530`
- `0x18000b9c0`
- `0x18000c440`
- `0x180010a4c`

## callees

- `0x18001463c`
- `0x180014aae`

## import_xrefs

- `USER32!SendMessageW` at `0x180014694`
- `USER32!SendMessageW` at `0x1800146d8`
- `USER32!SendMessageW` at `0x18001471a`
- `USER32!SendMessageW` at `0x180014760`
- `USER32!SendMessageW` at `0x180014785`
- `USER32!SendMessageW` at `0x180014694`
- `USER32!SendMessageW` at `0x1800146d8`
- `USER32!SendMessageW` at `0x18001471a`
- `USER32!SendMessageW` at `0x180014760`
- `USER32!SendMessageW` at `0x180014785`

## pseudocode

```c
__int64 __fastcall DetermineSel2(HWND hWnd, __int64 a2, int a3, __int64 a4, int a5, __int64 a6, int a7, _QWORD *a8)
{
  int v12; // ebx
  LPARAM lParam; // [rsp+20h] [rbp-B9h] BYREF
  int v15; // [rsp+28h] [rbp-B1h]
  __int64 v16; // [rsp+38h] [rbp-A1h]
  int v17; // [rsp+40h] [rbp-99h]
  int v18; // [rsp+80h] [rbp-59h] BYREF
  int v19; // [rsp+84h] [rbp-55h]
  int v20; // [rsp+88h] [rbp-51h]
  __int64 v21; // [rsp+98h] [rbp-41h]
  int v22; // [rsp+A0h] [rbp-39h]
  __int64 v23; // [rsp+A8h] [rbp-31h]

  memset_0(&v18, 0, 0x58u);
  v18 = 1;
  v21 = a2;
  v22 = a3;
  v20 = 0;
  v12 = SendMessageW(hWnd, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
  v19 = v12;
  if ( v12 <= -1 )
    return 0;
  if ( a2 )
  {
    memset_0(&lParam, 0, 0x58u);
    v17 = a3;
    v16 = a2;
    SendMessageW(hWnd, 0x1073u, v12, (LPARAM)&lParam);
    v12 = v19;
  }
  if ( a4 )
  {
    memset_0(&lParam, 0, 0x58u);
    v17 = a5;
    v15 = 1;
    v16 = a4;
    SendMessageW(hWnd, 0x1073u, v12, (LPARAM)&lParam);
    v12 = v19;
  }
  if ( a6 )
  {
    memset_0(&lParam, 0, 0x58u);
    v17 = a7;
    v15 = 2;
    v16 = a6;
    SendMessageW(hWnd, 0x1073u, v12, (LPARAM)&lParam);
  }
  if ( a8 )
  {
    v18 = 4;
    SendMessageW(hWnd, 0x104Bu, 0, (LPARAM)&v18);
    *a8 = v23;
  }
  return 1;
}

```

## disassembly

```asm
0x18001463c  push    rbp
0x18001463e  push    rbx
0x18001463f  push    rsi
0x180014640  push    rdi
0x180014641  push    r14
0x180014643  push    r15
0x180014645  lea     rbp, [rsp-0Fh]
0x18001464a  sub     rsp, 0E8h
0x180014651  mov     rsi, rdx
0x180014654  mov     r15d, r8d
0x180014657  xor     edx, edx; Val
0x180014659  mov     rdi, rcx
0x18001465c  lea     rcx, [rbp+37h+var_90]; void *
0x180014660  mov     r14, r9
0x180014663  lea     r8d, [rdx+58h]; Size
0x180014667  call    memset_0
0x18001466c  mov     r9d, 2; lParam
0x180014672  mov     dword ptr [rbp+37h+var_90], 1
0x180014679  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18001467d  mov     [rbp+37h+var_78], rsi
0x180014681  mov     edx, 100Ch; Msg
0x180014686  mov     [rbp+37h+var_70], r15d
0x18001468a  mov     rcx, rdi; hWnd
0x18001468d  mov     [rbp+37h+var_88], 0
0x180014694  call    cs:__imp_SendMessageW
0x18001469a  mov     rbx, rax
0x18001469d  mov     dword ptr [rbp+37h+var_90+4], ebx
0x1800146a0  cmp     eax, 0FFFFFFFFh
0x1800146a3  jle     loc_180014799
0x1800146a9  test    rsi, rsi
0x1800146ac  jz      short loc_1800146E1
0x1800146ae  xor     edx, edx; Val
0x1800146b0  lea     rcx, [rsp+110h+lParam]; void *
0x1800146b5  lea     r8d, [rdx+58h]; Size
0x1800146b9  call    memset_0
0x1800146be  movsxd  r8, ebx; wParam
0x1800146c1  lea     r9, [rsp+110h+lParam]; lParam
0x1800146c6  mov     edx, 1073h; Msg
0x1800146cb  mov     [rsp+110h+var_D0], r15d
0x1800146d0  mov     rcx, rdi; hWnd
0x1800146d3  mov     [rsp+110h+var_D8], rsi
0x1800146d8  call    cs:__imp_SendMessageW
0x1800146de  mov     ebx, dword ptr [rbp+37h+var_90+4]
0x1800146e1  test    r14, r14
0x1800146e4  jz      short loc_180014723
0x1800146e6  xor     edx, edx; Val
0x1800146e8  lea     rcx, [rsp+110h+lParam]; void *
0x1800146ed  lea     r8d, [rdx+58h]; Size
0x1800146f1  call    memset_0
0x1800146f6  mov     eax, [rbp+37h+arg_20]
0x1800146f9  lea     r9, [rsp+110h+lParam]; lParam
0x1800146fe  movsxd  r8, ebx; wParam
0x180014701  mov     edx, 1073h; Msg
0x180014706  mov     rcx, rdi; hWnd
0x180014709  mov     [rsp+110h+var_D0], eax
0x18001470d  mov     [rsp+110h+var_E8], 1
0x180014715  mov     [rsp+110h+var_D8], r14
0x18001471a  call    cs:__imp_SendMessageW
0x180014720  mov     ebx, dword ptr [rbp+37h+var_90+4]
0x180014723  mov     rsi, [rbp+37h+arg_28]
0x180014727  test    rsi, rsi
0x18001472a  jz      short loc_180014766
0x18001472c  xor     edx, edx; Val
0x18001472e  lea     rcx, [rsp+110h+lParam]; void *
0x180014733  lea     r8d, [rdx+58h]; Size
0x180014737  call    memset_0
0x18001473c  mov     eax, [rbp+37h+arg_30]
0x18001473f  lea     r9, [rsp+110h+lParam]; lParam
0x180014744  movsxd  r8, ebx; wParam
0x180014747  mov     edx, 1073h; Msg
0x18001474c  mov     rcx, rdi; hWnd
0x18001474f  mov     [rsp+110h+var_D0], eax
0x180014753  mov     [rsp+110h+var_E8], 2
0x18001475b  mov     [rsp+110h+var_D8], rsi
0x180014760  call    cs:__imp_SendMessageW
0x180014766  mov     rbx, [rbp+37h+arg_38]
0x18001476a  test    rbx, rbx
0x18001476d  jz      short loc_180014792
0x18001476f  lea     r9, [rbp+37h+var_90]; lParam
0x180014773  mov     dword ptr [rbp+37h+var_90], 4
0x18001477a  xor     r8d, r8d; wParam
0x18001477d  mov     edx, 104Bh; Msg
0x180014782  mov     rcx, rdi; hWnd
0x180014785  call    cs:__imp_SendMessageW
0x18001478b  mov     rcx, [rbp+37h+var_68]
0x18001478f  mov     [rbx], rcx
0x180014792  mov     eax, 1
0x180014797  jmp     short loc_18001479B
0x180014799  xor     eax, eax
0x18001479b  add     rsp, 0E8h
0x1800147a2  pop     r15
0x1800147a4  pop     r14
0x1800147a6  pop     rdi
0x1800147a7  pop     rsi
0x1800147a8  pop     rbx
0x1800147a9  pop     rbp
0x1800147aa  retn
```
