# FindNextLink(HWND__ *,__int64,long,long *,long *,ushort * *)

- ea: `0x180009ec8`
- end: `0x18000a00c`
- name: `?FindNextLink@@YA_NPEAUHWND__@@_JJPEAJ2PEAPEAG@Z`
- size: `324`
- prototype: `bool __usercall@<al>(HWND hWnd@<rcx>, __int64@<rdx>, int@<r8d>, int *@<r9>, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bb38`

## callees

- `0x180009ec8`
- `0x18000a6b0`
- `0x180022292`
- `0x1800222d0`

## import_xrefs

- `USER32!SendMessageW` at `0x180009f6a`
- `USER32!SendMessageW` at `0x180009f9b`
- `USER32!SendMessageW` at `0x180009f6a`
- `USER32!SendMessageW` at `0x180009f9b`

## pseudocode

```c
char __fastcall FindNextLink(HWND hWnd, __int64 a2, int a3, int *a4, int *a5, unsigned __int16 **a6)
{
  int v8; // edi
  int v10; // ebx
  int v11; // r13d
  int v12; // r8d
  _DWORD lParam[4]; // [rsp+20h] [rbp-E8h] BYREF
  int v15; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v16[124]; // [rsp+34h] [rbp-D4h] BYREF

  v8 = a3;
  if ( a4 && a5 && a2 >= a3 && a6 )
  {
    v10 = -1;
    memset_0(&v15, 0, 0x74u);
    while ( v8 < a2 )
    {
      v11 = v8 + 1;
      lParam[0] = v8;
      lParam[1] = v8 + 1;
      SendMessageW(hWnd, 0x437u, 0, (LPARAM)lParam);
      memset_0(v16, 0, 0x70u);
      v15 = 116;
      SendMessageW(hWnd, 0x43Au, 1u, (LPARAM)&v15);
      if ( (v16[4] & 0x20) != 0 )
      {
        if ( v10 != -1 )
          v8 = v10;
        v10 = v8;
      }
      else if ( v10 != -1 )
      {
        *a4 = v10;
        v12 = v8;
        *a5 = v8;
LABEL_14:
        *a6 = RetrieveRicheditText(hWnd, v10, v12);
        return 1;
      }
      v8 = v11;
    }
    if ( v10 != -1 )
    {
      *a4 = v10;
      v12 = a2;
      *a5 = a2;
      goto LABEL_14;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009ec8  push    rbx
0x180009eca  push    rbp
0x180009ecb  push    rsi
0x180009ecc  push    rdi
0x180009ecd  push    r12
0x180009ecf  push    r13
0x180009ed1  push    r14
0x180009ed3  push    r15
0x180009ed5  sub     rsp, 0C8h
0x180009edc  mov     rax, cs:__security_cookie
0x180009ee3  xor     rax, rsp
0x180009ee6  mov     [rsp+108h+var_58], rax
0x180009eee  mov     r14, [rsp+108h+arg_20]
0x180009ef6  mov     rbp, r9
0x180009ef9  mov     r15, [rsp+108h+arg_28]
0x180009f01  mov     rsi, rdx
0x180009f04  movsxd  rdi, r8d
0x180009f07  mov     r12, rcx
0x180009f0a  test    r9, r9
0x180009f0d  jz      loc_180009FE6
0x180009f13  test    r14, r14
0x180009f16  jz      loc_180009FE6
0x180009f1c  cmp     rdx, rdi
0x180009f1f  jl      loc_180009FE6
0x180009f25  test    r15, r15
0x180009f28  jz      loc_180009FE6
0x180009f2e  or      ebx, 0FFFFFFFFh
0x180009f31  lea     rcx, [rsp+108h+var_D8]; void *
0x180009f36  xor     edx, edx; Val
0x180009f38  lea     r8d, [rbx+75h]; Size
0x180009f3c  call    memset_0
0x180009f41  movsxd  rax, edi
0x180009f44  cmp     rax, rsi
0x180009f47  jge     loc_180009FD6
0x180009f4d  lea     r13d, [rdi+1]
0x180009f51  mov     [rsp+108h+lParam], edi
0x180009f55  lea     r9, [rsp+108h+lParam]; lParam
0x180009f5a  mov     [rsp+108h+lParam+4], r13d
0x180009f5f  xor     r8d, r8d; wParam
0x180009f62  mov     edx, 437h; Msg
0x180009f67  mov     rcx, r12; hWnd
0x180009f6a  call    cs:__imp_SendMessageW
0x180009f70  xor     edx, edx; Val
0x180009f72  lea     rcx, [rsp+108h+var_D8+4]; void *
0x180009f77  lea     r8d, [rdx+70h]; Size
0x180009f7b  call    memset_0
0x180009f80  lea     r9, [rsp+108h+var_D8]; lParam
0x180009f85  mov     dword ptr [rsp+108h+var_D8], 74h ; 't'
0x180009f8d  mov     edx, 43Ah; Msg
0x180009f92  mov     r8d, 1; wParam
0x180009f98  mov     rcx, r12; hWnd
0x180009f9b  call    cs:__imp_SendMessageW
0x180009fa1  test    [rsp+108h+var_D0], 20h
0x180009fa6  jz      short loc_180009FB2
0x180009fa8  cmp     ebx, 0FFFFFFFFh
0x180009fab  cmovnz  edi, ebx
0x180009fae  mov     ebx, edi
0x180009fb0  jmp     short loc_180009FB7
0x180009fb2  cmp     ebx, 0FFFFFFFFh
0x180009fb5  jnz     short loc_180009FBC
0x180009fb7  mov     edi, r13d
0x180009fba  jmp     short loc_180009F41
0x180009fbc  mov     [rbp+0], ebx
0x180009fbf  mov     r8d, edi; int
0x180009fc2  mov     [r14], edi
0x180009fc5  mov     edx, ebx; int
0x180009fc7  mov     rcx, r12; hWnd
0x180009fca  call    ?RetrieveRicheditText@@YAPEAGPEAUHWND__@@JJ@Z; RetrieveRicheditText(HWND__ *,long,long)
0x180009fcf  mov     [r15], rax
0x180009fd2  mov     al, 1
0x180009fd4  jmp     short loc_180009FE8
0x180009fd6  cmp     ebx, 0FFFFFFFFh
0x180009fd9  jz      short loc_180009FE6
0x180009fdb  mov     [rbp+0], ebx
0x180009fde  mov     r8d, esi
0x180009fe1  mov     [r14], esi
0x180009fe4  jmp     short loc_180009FC5
0x180009fe6  xor     al, al
0x180009fe8  mov     rcx, [rsp+108h+var_58]
0x180009ff0  xor     rcx, rsp; StackCookie
0x180009ff3  call    __security_check_cookie
0x180009ff8  add     rsp, 0C8h
0x180009fff  pop     r15
0x18000a001  pop     r14
0x18000a003  pop     r13
0x18000a005  pop     r12
0x18000a007  pop     rdi
0x18000a008  pop     rsi
0x18000a009  pop     rbp
0x18000a00a  pop     rbx
0x18000a00b  retn
```
