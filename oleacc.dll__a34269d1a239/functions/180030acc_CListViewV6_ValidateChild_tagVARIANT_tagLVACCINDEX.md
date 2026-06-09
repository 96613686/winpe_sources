# CListViewV6::_ValidateChild(tagVARIANT *,tagLVACCINDEX *)

- ea: `0x180030acc`
- end: `0x180030ba2`
- name: `?_ValidateChild@CListViewV6@@AEAAJPEAUtagVARIANT@@PEAUtagLVACCINDEX@@@Z`
- size: `214`
- prototype: `int(CListViewV6 *__hidden this, struct tagVARIANT *, struct tagLVACCINDEX *)`
- caller_count: `15`
- callee_count: `4`
- tags: ``

## callers

- `0x180030bb0`
- `0x180030ff0`
- `0x1800311c0`
- `0x1800312b0`
- `0x1800313a0`
- `0x1800314f0`
- `0x1800316c0`
- `0x180031810`
- `0x1800318d0`
- `0x1800319a0`
- `0x180031a60`
- `0x180031ca0`
- `0x180031e30`
- `0x180031f70`
- `0x180032030`

## callees

- `0x180006c58`
- `0x18000771c`
- `0x180030a5c`
- `0x180030acc`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180030b73`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180030b73`
- `USER32!SendMessageW` at `0x180030b53`
- `USER32!SendMessageW` at `0x180030b53`

## pseudocode

```c
__int64 __fastcall CListViewV6::_ValidateChild(CListViewV6 *this, struct tagVARIANT *a2, struct tagLVACCINDEX *a3)
{
  int v6; // ebx
  LONG v7; // ecx
  HWND v8; // rdx
  LPVOID v9; // rax
  void *v10; // rsi
  HANDLE hProcess; // [rsp+60h] [rbp+18h] BYREF

  *(_DWORD *)a3 = -1;
  *((_DWORD *)a3 + 1) = -1;
  *((_DWORD *)a3 + 2) = -1;
  v6 = _ValidateAccChild(a2);
  if ( v6 >= 0 )
  {
    if ( a2->lVal || (v7 = *((_DWORD *)this + 34), (a2->lVal = v7) != 0) )
    {
      v8 = (HWND)*((_QWORD *)this + 10);
      hProcess = 0;
      v6 = -2147024882;
      v9 = SharedAlloc(0xCu, v8, &hProcess);
      v10 = v9;
      if ( v9 )
      {
        if ( (unsigned int)SendMessageW(*((HWND *)this + 10), 0x10C2u, a2->lVal, (LPARAM)v9) )
        {
          v6 = 0;
          ReadProcessMemory(hProcess, v10, a3, 0xCu, 0);
        }
        else
        {
          v6 = -2147024809;
        }
        SharedFree(v10, hProcess);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180030acc  mov     [rsp+arg_0], rbx
0x180030ad1  mov     [rsp+arg_8], rbp
0x180030ad6  push    rsi
0x180030ad7  push    rdi
0x180030ad8  push    r14
0x180030ada  sub     rsp, 30h
0x180030ade  or      eax, 0FFFFFFFFh
0x180030ae1  mov     rbp, rcx
0x180030ae4  mov     rcx, rdx; struct tagVARIANT *
0x180030ae7  mov     [r8], eax
0x180030aea  mov     [r8+4], eax
0x180030aee  mov     r14, r8
0x180030af1  mov     [r8+8], eax
0x180030af5  mov     rdi, rdx
0x180030af8  call    ?_ValidateAccChild@@YAJPEAUtagVARIANT@@@Z; _ValidateAccChild(tagVARIANT *)
0x180030afd  mov     ebx, eax
0x180030aff  test    eax, eax
0x180030b01  js      loc_180030B8D
0x180030b07  cmp     dword ptr [rdi+8], 0
0x180030b0b  jnz     short loc_180030B1A
0x180030b0d  mov     ecx, [rbp+88h]
0x180030b13  mov     [rdi+8], ecx
0x180030b16  test    ecx, ecx
0x180030b18  jz      short loc_180030B8D
0x180030b1a  mov     rdx, [rbp+50h]; HWND
0x180030b1e  lea     r8, [rsp+48h+hProcess]; void **
0x180030b23  mov     ecx, 0Ch; dwSize
0x180030b28  mov     [rsp+48h+hProcess], 0
0x180030b31  mov     ebx, 8007000Eh
0x180030b36  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180030b3b  mov     rsi, rax
0x180030b3e  test    rax, rax
0x180030b41  jz      short loc_180030B8D
0x180030b43  movsxd  r8, dword ptr [rdi+8]; wParam
0x180030b47  mov     r9, rax; lParam
0x180030b4a  mov     rcx, [rbp+50h]; hWnd
0x180030b4e  mov     edx, 10C2h; Msg
0x180030b53  call    cs:__imp_SendMessageW
0x180030b59  test    eax, eax
0x180030b5b  jz      short loc_180030B7B
0x180030b5d  mov     rcx, [rsp+48h+hProcess]; hProcess
0x180030b62  xor     ebx, ebx
0x180030b64  mov     r8, r14; lpBuffer
0x180030b67  mov     [rsp+48h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x180030b6c  mov     rdx, rsi; lpBaseAddress
0x180030b6f  lea     r9d, [rbx+0Ch]; nSize
0x180030b73  call    cs:__imp_ReadProcessMemory
0x180030b79  jmp     short loc_180030B80
0x180030b7b  mov     ebx, 80070057h
0x180030b80  mov     rdx, [rsp+48h+hProcess]; hProcess
0x180030b85  mov     rcx, rsi; lpAddress
0x180030b88  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180030b8d  mov     rbp, [rsp+48h+arg_8]
0x180030b92  mov     eax, ebx
0x180030b94  mov     rbx, [rsp+48h+arg_0]
0x180030b99  add     rsp, 30h
0x180030b9d  pop     r14
0x180030b9f  pop     rdi
0x180030ba0  pop     rsi
0x180030ba1  retn
```
