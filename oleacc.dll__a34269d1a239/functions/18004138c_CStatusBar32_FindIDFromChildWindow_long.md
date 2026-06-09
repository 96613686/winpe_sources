# CStatusBar32::FindIDFromChildWindow(long)

- ea: `0x18004138c`
- end: `0x18004151a`
- name: `?FindIDFromChildWindow@CStatusBar32@@QEAAJJ@Z`
- size: `398`
- prototype: `__int64 __fastcall(CStatusBar32 *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180041900`

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x180015ac0`
- `0x18001e4c0`
- `0x18004138c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180041498`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180041498`
- `USER32!MapWindowPoints` at `0x1800414ae`
- `USER32!MapWindowPoints` at `0x1800414ae`
- `USER32!GetWindowRect` at `0x1800413f8`
- `USER32!GetWindowRect` at `0x1800413f8`

## pseudocode

```c
__int64 __fastcall CStatusBar32::FindIDFromChildWindow(CStatusBar32 *this, unsigned int a2)
{
  HWND v3; // rdx
  void *v5; // rbx
  HWND v6; // rax
  HWND v7; // r8
  int i; // edi
  HANDLE hProcess; // [rsp+40h] [rbp-40h] BYREF
  __int64 v11; // [rsp+48h] [rbp-38h] BYREF
  __int128 Buffer; // [rsp+50h] [rbp-30h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp-20h] BYREF

  hProcess = 0;
  v3 = (HWND)*((_QWORD *)this + 10);
  Buffer = 0;
  Rect = 0;
  v5 = SharedAlloc(0x10u, v3, &hProcess);
  if ( v5 )
  {
    v6 = HwndFromHWNDID(*((HWND *)this + 10), a2);
    if ( GetWindowRect(v6, &Rect) )
    {
      v7 = (HWND)*((_QWORD *)this + 10);
      v11 = 0;
      if ( CAccessible::AccSendMessageTimeout(this, 0, v7, 0x406u, 0, 0, &v11) >= 0 )
      {
        for ( i = 0;
              i < (int)v11
           && CAccessible::AccSendMessageTimeout(this, 0, *((HWND *)this + 10), 0x40Au, i, (__int64)v5, 0) >= 0;
              ++i )
        {
          ReadProcessMemory(hProcess, v5, &Buffer, 0x10u, 0);
          MapWindowPoints(*((HWND *)this + 10), 0, (LPPOINT)&Buffer, 2u);
          if ( Rect.left >= (int)Buffer
            && Rect.right <= SDWORD2(Buffer)
            && Rect.top >= SDWORD1(Buffer)
            && Rect.bottom <= SHIDWORD(Buffer) )
          {
            SharedFree(v5, hProcess);
            return (unsigned int)(i + 1);
          }
        }
      }
    }
    SharedFree(v5, hProcess);
  }
  return 0;
}

```

## disassembly

```asm
0x18004138c  mov     [rsp-18h+arg_10], rbx
0x180041391  push    rbp
0x180041392  push    rdi
0x180041393  push    r14
0x180041395  mov     rbp, rsp
0x180041398  sub     rsp, 80h
0x18004139f  mov     rax, cs:__security_cookie
0x1800413a6  xor     rax, rsp
0x1800413a9  mov     [rbp+var_10], rax
0x1800413ad  mov     edi, edx
0x1800413af  mov     [rbp+hProcess], 0
0x1800413b7  mov     rdx, [rcx+50h]; HWND
0x1800413bb  lea     r8, [rbp+hProcess]; void **
0x1800413bf  mov     r14, rcx
0x1800413c2  xorps   xmm0, xmm0
0x1800413c5  xorps   xmm1, xmm1
0x1800413c8  mov     ecx, 10h; dwSize
0x1800413cd  movups  [rbp+Buffer], xmm0
0x1800413d1  movups  xmmword ptr [rbp+Rect.left], xmm1
0x1800413d5  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x1800413da  mov     rbx, rax
0x1800413dd  test    rax, rax
0x1800413e0  jz      loc_1800414F8
0x1800413e6  mov     rcx, [r14+50h]; HWND
0x1800413ea  mov     edx, edi; unsigned int
0x1800413ec  call    ?HwndFromHWNDID@@YAPEAUHWND__@@PEAU1@K@Z; HwndFromHWNDID(HWND__ *,ulong)
0x1800413f1  mov     rcx, rax; hWnd
0x1800413f4  lea     rdx, [rbp+Rect]; lpRect
0x1800413f8  call    cs:__imp_GetWindowRect
0x1800413fe  test    eax, eax
0x180041400  jz      loc_1800414EC
0x180041406  mov     r8, [r14+50h]; HWND
0x18004140a  lea     rax, [rbp+var_38]
0x18004140e  mov     [rsp+80h+var_50], rax; __int64 *
0x180041413  mov     r9d, 406h; unsigned int
0x180041419  mov     [rsp+80h+var_58], 0; __int64
0x180041422  xor     edx, edx; bool
0x180041424  mov     rcx, r14; this
0x180041427  mov     [rsp+80h+lpNumberOfBytesRead], 0; unsigned __int64
0x180041430  mov     [rbp+var_38], 0
0x180041438  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18004143d  test    eax, eax
0x18004143f  js      loc_1800414EC
0x180041445  xor     edi, edi
0x180041447  cmp     edi, dword ptr [rbp+var_38]
0x18004144a  jge     loc_1800414EC
0x180041450  mov     r8, [r14+50h]; HWND
0x180041454  mov     r9d, 40Ah; unsigned int
0x18004145a  movsxd  rax, edi
0x18004145d  xor     edx, edx; bool
0x18004145f  mov     [rsp+80h+var_50], 0; __int64 *
0x180041468  mov     rcx, r14; this
0x18004146b  mov     [rsp+80h+var_58], rbx; __int64
0x180041470  mov     [rsp+80h+lpNumberOfBytesRead], rax; unsigned __int64
0x180041475  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18004147a  test    eax, eax
0x18004147c  js      short loc_1800414EC
0x18004147e  mov     rcx, [rbp+hProcess]; hProcess
0x180041482  lea     r8, [rbp+Buffer]; lpBuffer
0x180041486  mov     r9d, 10h; nSize
0x18004148c  mov     [rsp+80h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x180041495  mov     rdx, rbx; lpBaseAddress
0x180041498  call    cs:__imp_ReadProcessMemory
0x18004149e  mov     rcx, [r14+50h]; hWndFrom
0x1800414a2  lea     r8, [rbp+Buffer]; lpPoints
0x1800414a6  mov     r9d, 2; cPoints
0x1800414ac  xor     edx, edx; hWndTo
0x1800414ae  call    cs:__imp_MapWindowPoints
0x1800414b4  mov     eax, dword ptr [rbp+Buffer]
0x1800414b7  cmp     [rbp+Rect.left], eax
0x1800414ba  jl      short loc_1800414D4
0x1800414bc  mov     eax, dword ptr [rbp+Buffer+8]
0x1800414bf  cmp     [rbp+Rect.right], eax
0x1800414c2  jg      short loc_1800414D4
0x1800414c4  mov     eax, dword ptr [rbp+Buffer+4]
0x1800414c7  cmp     [rbp+Rect.top], eax
0x1800414ca  jl      short loc_1800414D4
0x1800414cc  mov     eax, dword ptr [rbp+Buffer+0Ch]
0x1800414cf  cmp     [rbp+Rect.bottom], eax
0x1800414d2  jle     short loc_1800414DB
0x1800414d4  inc     edi
0x1800414d6  jmp     loc_180041447
0x1800414db  mov     rdx, [rbp+hProcess]; hProcess
0x1800414df  mov     rcx, rbx; lpAddress
0x1800414e2  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800414e7  lea     eax, [rdi+1]
0x1800414ea  jmp     short loc_1800414FA
0x1800414ec  mov     rdx, [rbp+hProcess]; hProcess
0x1800414f0  mov     rcx, rbx; lpAddress
0x1800414f3  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800414f8  xor     eax, eax
0x1800414fa  mov     rcx, [rbp+var_10]
0x1800414fe  xor     rcx, rsp; StackCookie
0x180041501  call    __security_check_cookie
0x180041506  mov     rbx, [rsp+80h+arg_10]
0x18004150e  add     rsp, 80h
0x180041515  pop     r14
0x180041517  pop     rdi
0x180041518  pop     rbp
0x180041519  retn
```
