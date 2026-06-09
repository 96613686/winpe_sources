# CSplitButton::accHitTest(long,long,tagVARIANT *)

- ea: `0x180040a30`
- end: `0x180040c22`
- name: `?accHitTest@CSplitButton@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(CSplitButton *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18001e4c0`
- `0x180040a30`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180040b73`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180040b73`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180040af2`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180040af2`
- `USER32!SetRect` at `0x180040bb0`
- `USER32!SetRect` at `0x180040bb0`
- `USER32!ScreenToClient` at `0x180040bbe`
- `USER32!ScreenToClient` at `0x180040bbe`
- `USER32!PtInRect` at `0x180040a95`
- `USER32!PtInRect` at `0x180040bd2`
- `USER32!PtInRect` at `0x180040a95`
- `USER32!PtInRect` at `0x180040bd2`
- `USER32!GetWindowRect` at `0x180040a87`
- `USER32!GetWindowRect` at `0x180040a87`

## pseudocode

```c
__int64 __fastcall CSplitButton::accHitTest(
        CSplitButton *this,
        unsigned int a2,
        unsigned int a3,
        struct tagVARIANT *a4)
{
  HWND v7; // rcx
  void *v8; // rax
  void *v9; // rbx
  unsigned int v10; // edi
  HWND v11; // r8
  int v12; // r12d
  int v13; // r9d
  int v14; // eax
  POINT v15; // rdx
  HANDLE hProcess; // [rsp+40h] [rbp-39h] BYREF
  POINT pt; // [rsp+48h] [rbp-31h] BYREF
  __int128 Buffer; // [rsp+50h] [rbp-29h] BYREF
  __int128 v19; // [rsp+60h] [rbp-19h]
  struct tagRECT Rect; // [rsp+70h] [rbp-9h] BYREF
  struct tagRECT rc; // [rsp+80h] [rbp+7h] BYREF

  hProcess = 0;
  Rect = 0;
  if ( !a4 )
    return 2147942487LL;
  v7 = (HWND)*((_QWORD *)this + 10);
  pt = (POINT)__PAIR64__(a3, a2);
  GetWindowRect(v7, &Rect);
  if ( PtInRect(&Rect, pt) )
  {
    v8 = SharedAlloc(0x20u, *((HWND *)this + 10), &hProcess);
    v9 = v8;
    if ( v8 )
    {
      Buffer = 0;
      LODWORD(Buffer) = 8;
      v10 = -2147467259;
      v19 = 0;
      if ( WriteProcessMemory(hProcess, v8, &Buffer, 0x20u, 0) )
      {
        v11 = (HWND)*((_QWORD *)this + 10);
        *(_QWORD *)&rc.left = 0;
        v12 = CAccessible::AccSendMessageTimeout(this, 0, v11, 0x1608u, 0, (__int64)v9, (__int64 *)&rc.left);
        if ( v12 < 0 )
        {
          SharedFree(v9, hProcess);
          return (unsigned int)v12;
        }
        if ( *(_QWORD *)&rc.left && ReadProcessMemory(hProcess, v9, &Buffer, 0x20u, 0) )
        {
          v13 = 0;
          rc = 0;
          if ( Rect.right - Rect.left >= 0 )
            v13 = Rect.right - Rect.left;
          v14 = 0;
          if ( Rect.bottom - Rect.top >= 0 )
            v14 = Rect.bottom - Rect.top;
          SetRect(&rc, v13 - DWORD1(v19), 0, v13, v14);
          ScreenToClient(*((HWND *)this + 10), &pt);
          v15 = pt;
          a4->vt = 3;
          v10 = 0;
          a4->lVal = PtInRect(&rc, v15);
        }
      }
      SharedFree(v9, hProcess);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    a4->vt = 0;
    return 1;
  }
  return v10;
}

```

## disassembly

```asm
0x180040a30  push    rbp
0x180040a32  push    rbx
0x180040a33  push    rdi
0x180040a34  push    r12
0x180040a36  push    r14
0x180040a38  push    r15
0x180040a3a  lea     rbp, [rsp-2Fh]
0x180040a3f  sub     rsp, 0A8h
0x180040a46  mov     rax, cs:__security_cookie
0x180040a4d  xor     rax, rsp
0x180040a50  mov     [rbp+57h+var_40], rax
0x180040a54  mov     [rbp+57h+hProcess], 0
0x180040a5c  xorps   xmm0, xmm0
0x180040a5f  mov     r15, r9
0x180040a62  mov     r14, rcx
0x180040a65  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180040a69  test    r9, r9
0x180040a6c  jnz     short loc_180040A78
0x180040a6e  mov     eax, 80070057h
0x180040a73  jmp     loc_180040C05
0x180040a78  mov     rcx, [rcx+50h]; hWnd
0x180040a7c  mov     [rbp+57h+pt.x], edx
0x180040a7f  lea     rdx, [rbp+57h+Rect]; lpRect
0x180040a83  mov     [rbp+57h+pt.y], r8d
0x180040a87  call    cs:__imp_GetWindowRect
0x180040a8d  mov     rdx, qword ptr [rbp+57h+pt.x]; pt
0x180040a91  lea     rcx, [rbp+57h+Rect]; lprc
0x180040a95  call    cs:__imp_PtInRect
0x180040a9b  test    eax, eax
0x180040a9d  jz      loc_180040BFA
0x180040aa3  mov     rdx, [r14+50h]; HWND
0x180040aa7  lea     r8, [rbp+57h+hProcess]; void **
0x180040aab  mov     ecx, 20h ; ' '; dwSize
0x180040ab0  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180040ab5  mov     rbx, rax
0x180040ab8  test    rax, rax
0x180040abb  jz      loc_180040BF3
0x180040ac1  mov     rcx, [rbp+57h+hProcess]; hProcess
0x180040ac5  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180040ac9  xorps   xmm0, xmm0
0x180040acc  mov     [rsp+0D0h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180040ad5  movups  [rbp+57h+Buffer], xmm0
0x180040ad9  mov     r9d, 20h ; ' '; nSize
0x180040adf  mov     dword ptr [rbp+57h+Buffer], 8
0x180040ae6  mov     rdx, rax; lpBaseAddress
0x180040ae9  mov     edi, 80004005h
0x180040aee  movups  [rbp+57h+var_70], xmm0
0x180040af2  call    cs:__imp_WriteProcessMemory
0x180040af8  test    eax, eax
0x180040afa  jz      loc_180040BE5
0x180040b00  mov     r8, [r14+50h]; HWND
0x180040b04  lea     rax, [rbp+57h+rc]
0x180040b08  mov     [rsp+0D0h+var_A0], rax; __int64 *
0x180040b0d  mov     r9d, 1608h; unsigned int
0x180040b13  mov     [rsp+0D0h+var_A8], rbx; __int64
0x180040b18  xor     edx, edx; bool
0x180040b1a  mov     rcx, r14; this
0x180040b1d  mov     [rsp+0D0h+lpNumberOfBytesWritten], 0; unsigned __int64
0x180040b26  mov     qword ptr [rbp+57h+rc.left], 0
0x180040b2e  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180040b33  mov     r12d, eax
0x180040b36  test    eax, eax
0x180040b38  jns     short loc_180040B4E
0x180040b3a  mov     rdx, [rbp+57h+hProcess]; hProcess
0x180040b3e  mov     rcx, rbx; lpAddress
0x180040b41  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180040b46  mov     eax, r12d
0x180040b49  jmp     loc_180040C05
0x180040b4e  cmp     qword ptr [rbp+57h+rc.left], 0
0x180040b53  jz      loc_180040BE5
0x180040b59  mov     rcx, [rbp+57h+hProcess]; hProcess
0x180040b5d  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180040b61  mov     r9d, 20h ; ' '; nSize
0x180040b67  mov     [rsp+0D0h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180040b70  mov     rdx, rbx; lpBaseAddress
0x180040b73  call    cs:__imp_ReadProcessMemory
0x180040b79  test    eax, eax
0x180040b7b  jz      short loc_180040BE5
0x180040b7d  mov     ecx, [rbp+57h+Rect.bottom]
0x180040b80  mov     r9d, 0
0x180040b86  mov     eax, [rbp+57h+Rect.right]
0x180040b89  xorps   xmm0, xmm0
0x180040b8c  sub     eax, [rbp+57h+Rect.left]
0x180040b8f  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180040b93  cmovns  r9d, eax; xRight
0x180040b97  xor     eax, eax
0x180040b99  sub     ecx, [rbp+57h+Rect.top]
0x180040b9c  mov     edx, r9d
0x180040b9f  cmovns  eax, ecx
0x180040ba2  sub     edx, dword ptr [rbp+57h+var_70+4]; xLeft
0x180040ba5  xor     r8d, r8d; yTop
0x180040ba8  mov     dword ptr [rsp+0D0h+lpNumberOfBytesWritten], eax; yBottom
0x180040bac  lea     rcx, [rbp+57h+rc]; lprc
0x180040bb0  call    cs:__imp_SetRect
0x180040bb6  mov     rcx, [r14+50h]; hWnd
0x180040bba  lea     rdx, [rbp+57h+pt]; lpPoint
0x180040bbe  call    cs:__imp_ScreenToClient
0x180040bc4  mov     rdx, qword ptr [rbp+57h+pt.x]; pt
0x180040bc8  lea     rcx, [rbp+57h+rc]; lprc
0x180040bcc  mov     word ptr [r15], 3
0x180040bd2  call    cs:__imp_PtInRect
0x180040bd8  xor     ecx, ecx
0x180040bda  test    eax, eax
0x180040bdc  setnz   cl
0x180040bdf  xor     edi, edi
0x180040be1  mov     [r15+8], ecx
0x180040be5  mov     rdx, [rbp+57h+hProcess]; hProcess
0x180040be9  mov     rcx, rbx; lpAddress
0x180040bec  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180040bf1  jmp     short loc_180040C03
0x180040bf3  mov     edi, 8007000Eh
0x180040bf8  jmp     short loc_180040C03
0x180040bfa  xor     eax, eax
0x180040bfc  mov     [r15], ax
0x180040c00  lea     edi, [rax+1]
0x180040c03  mov     eax, edi
0x180040c05  mov     rcx, [rbp+57h+var_40]
0x180040c09  xor     rcx, rsp; StackCookie
0x180040c0c  call    __security_check_cookie
0x180040c11  add     rsp, 0A8h
0x180040c18  pop     r15
0x180040c1a  pop     r14
0x180040c1c  pop     r12
0x180040c1e  pop     rdi
0x180040c1f  pop     rbx
0x180040c20  pop     rbp
0x180040c21  retn
```
