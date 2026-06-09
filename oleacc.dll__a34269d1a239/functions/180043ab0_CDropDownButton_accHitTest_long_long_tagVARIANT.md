# CDropDownButton::accHitTest(long,long,tagVARIANT *)

- ea: `0x180043ab0`
- end: `0x180043bf0`
- name: `?accHitTest@CDropDownButton@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(CDropDownButton *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18001e4c0`
- `0x180043ab0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180043b8e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180043b8e`
- `USER32!ScreenToClient` at `0x180043ba7`
- `USER32!ScreenToClient` at `0x180043ba7`
- `USER32!PtInRect` at `0x180043bb5`
- `USER32!PtInRect` at `0x180043bb5`

## pseudocode

```c
__int64 __fastcall CDropDownButton::accHitTest(
        CDropDownButton *this,
        unsigned int a2,
        unsigned int a3,
        struct tagVARIANT *a4)
{
  HWND v6; // rdx
  void *v9; // rbx
  HWND v10; // r8
  int v11; // edi
  HWND v13; // rcx
  unsigned __int64 lpNumberOfBytesRead; // [rsp+20h] [rbp-50h]
  struct tagPOINT Point; // [rsp+40h] [rbp-30h] BYREF
  HANDLE hProcess; // [rsp+48h] [rbp-28h] BYREF
  RECT Buffer; // [rsp+50h] [rbp-20h] BYREF

  a4->lVal = 0;
  a4->vt = 3;
  v6 = (HWND)*((_QWORD *)this + 18);
  hProcess = 0;
  v9 = SharedAlloc(0x10u, v6, &hProcess);
  if ( v9 )
  {
    v10 = (HWND)*((_QWORD *)this + 18);
    lpNumberOfBytesRead = *((_DWORD *)this + 32) - 1;
    Point = 0;
    v11 = CAccessible::AccSendMessageTimeout(this, 0, v10, 0x467u, lpNumberOfBytesRead, (__int64)v9, (__int64 *)&Point);
    if ( v11 < 0 )
    {
      SharedFree(v9, hProcess);
      return (unsigned int)v11;
    }
    if ( Point )
    {
      Buffer = 0;
      ReadProcessMemory(hProcess, v9, &Buffer, 0x10u, 0);
      v13 = (HWND)*((_QWORD *)this + 18);
      Point = (struct tagPOINT)__PAIR64__(a3, a2);
      ScreenToClient(v13, &Point);
      if ( PtInRect(&Buffer, Point) )
        a4->lVal = 1;
    }
    SharedFree(v9, hProcess);
  }
  return 0;
}

```

## disassembly

```asm
0x180043ab0  push    rbp
0x180043ab2  push    rbx
0x180043ab3  push    rsi
0x180043ab4  push    rdi
0x180043ab5  push    r12
0x180043ab7  push    r14
0x180043ab9  push    r15
0x180043abb  mov     rbp, rsp
0x180043abe  sub     rsp, 70h
0x180043ac2  mov     rax, cs:__security_cookie
0x180043ac9  xor     rax, rsp
0x180043acc  mov     [rbp+var_10], rax
0x180043ad0  mov     r15d, edx
0x180043ad3  mov     dword ptr [r9+8], 0
0x180043adb  mov     word ptr [r9], 3
0x180043ae1  mov     r12d, r8d
0x180043ae4  mov     rdx, [rcx+90h]; HWND
0x180043aeb  lea     r8, [rbp+hProcess]; void **
0x180043aef  mov     rsi, rcx
0x180043af2  mov     [rbp+hProcess], 0
0x180043afa  mov     ecx, 10h; dwSize
0x180043aff  mov     r14, r9
0x180043b02  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180043b07  mov     rbx, rax
0x180043b0a  test    rax, rax
0x180043b0d  jz      loc_180043BD3
0x180043b13  mov     ecx, [rsi+80h]
0x180043b19  lea     rax, [rbp+Point]
0x180043b1d  mov     r8, [rsi+90h]; HWND
0x180043b24  dec     ecx
0x180043b26  movsxd  rdx, ecx
0x180043b29  mov     r9d, 467h; unsigned int
0x180043b2f  mov     [rsp+70h+var_40], rax; __int64 *
0x180043b34  mov     rcx, rsi; this
0x180043b37  mov     [rsp+70h+var_48], rbx; __int64
0x180043b3c  mov     [rsp+70h+lpNumberOfBytesRead], rdx; unsigned __int64
0x180043b41  xor     edx, edx; bool
0x180043b43  mov     qword ptr [rbp+Point.x], 0
0x180043b4b  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180043b50  mov     edi, eax
0x180043b52  test    eax, eax
0x180043b54  jns     short loc_180043B66
0x180043b56  mov     rdx, [rbp+hProcess]; hProcess
0x180043b5a  mov     rcx, rbx; lpAddress
0x180043b5d  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180043b62  mov     eax, edi
0x180043b64  jmp     short loc_180043BD5
0x180043b66  cmp     qword ptr [rbp+Point.x], 0
0x180043b6b  jz      short loc_180043BC7
0x180043b6d  mov     rcx, [rbp+hProcess]; hProcess
0x180043b71  lea     r8, [rbp+Buffer]; lpBuffer
0x180043b75  xorps   xmm0, xmm0
0x180043b78  mov     [rsp+70h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x180043b81  mov     r9d, 10h; nSize
0x180043b87  mov     rdx, rbx; lpBaseAddress
0x180043b8a  movups  [rbp+Buffer], xmm0
0x180043b8e  call    cs:__imp_ReadProcessMemory
0x180043b94  mov     rcx, [rsi+90h]; hWnd
0x180043b9b  lea     rdx, [rbp+Point]; lpPoint
0x180043b9f  mov     [rbp+Point.x], r15d
0x180043ba3  mov     [rbp+Point.y], r12d
0x180043ba7  call    cs:__imp_ScreenToClient
0x180043bad  mov     rdx, qword ptr [rbp+Point.x]; pt
0x180043bb1  lea     rcx, [rbp+Buffer]; lprc
0x180043bb5  call    cs:__imp_PtInRect
0x180043bbb  test    eax, eax
0x180043bbd  jz      short loc_180043BC7
0x180043bbf  mov     dword ptr [r14+8], 1
0x180043bc7  mov     rdx, [rbp+hProcess]; hProcess
0x180043bcb  mov     rcx, rbx; lpAddress
0x180043bce  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180043bd3  xor     eax, eax
0x180043bd5  mov     rcx, [rbp+var_10]
0x180043bd9  xor     rcx, rsp; StackCookie
0x180043bdc  call    __security_check_cookie
0x180043be1  add     rsp, 70h
0x180043be5  pop     r15
0x180043be7  pop     r14
0x180043be9  pop     r12
0x180043beb  pop     rdi
0x180043bec  pop     rsi
0x180043bed  pop     rbx
0x180043bee  pop     rbp
0x180043bef  retn
```
