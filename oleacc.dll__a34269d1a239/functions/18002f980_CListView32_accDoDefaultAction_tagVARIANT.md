# CListView32::accDoDefaultAction(tagVARIANT)

- ea: `0x18002f980`
- end: `0x18002fb22`
- name: `?accDoDefaultAction@CListView32@@UEAAJUtagVARIANT@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(CListView32 *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18001e4c0`
- `0x18002f980`
- `0x180046b10`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002fa8b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002fa8b`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002fa20`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002fa20`
- `USER32!SendMessageW` at `0x18002fac2`
- `USER32!SendMessageW` at `0x18002fac2`
- `USER32!MapWindowPoints` at `0x18002faa1`
- `USER32!MapWindowPoints` at `0x18002faa1`

## pseudocode

```c
int __fastcall CListView32::accDoDefaultAction(HWND *this, struct tagVARIANT *a2)
{
  HWND v2; // rax
  int result; // eax
  void *v6; // rax
  void *v7; // rbx
  HWND v8; // r8
  unsigned __int64 v9; // rcx
  HWND v10; // rcx
  char v11; // al
  HANDLE hProcess; // [rsp+40h] [rbp-30h] BYREF
  __int64 v13; // [rsp+48h] [rbp-28h] BYREF
  struct tagRECT Buffer; // [rsp+50h] [rbp-20h] BYREF

  v2 = *this;
  hProcess = 0;
  Buffer = 0;
  if ( !(*((unsigned int (__fastcall **)(HWND *))v2 + 30))(this) )
    return -2147024809;
  if ( !a2->lVal )
    return -2147352573;
  v6 = SharedAlloc(0x10u, this[10], &hProcess);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  Buffer.left = 1;
  WriteProcessMemory(hProcess, v6, &Buffer, 0x10u, 0);
  v8 = this[10];
  v9 = a2->lVal - 1;
  v13 = 0;
  result = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, v8, 0x100Eu, v9, (__int64)v7, &v13);
  if ( result >= 0 )
  {
    if ( v13 )
    {
      ReadProcessMemory(hProcess, v7, &Buffer, 0x10u, 0);
      MapWindowPoints(this[10], 0, (LPPOINT)&Buffer, 2u);
      Buffer.right -= Buffer.left;
      v10 = this[10];
      Buffer.bottom -= Buffer.top;
      v11 = SendMessageW(v10, 0x1037u, 0, 0);
      if ( ClickOnTheRect(&Buffer, this[10], (v11 & 0x40) == 0) )
      {
        SharedFree(v7, hProcess);
        return 0;
      }
    }
    SharedFree(v7, hProcess);
    return -2147352573;
  }
  return result;
}

```

## disassembly

```asm
0x18002f980  mov     [rsp-18h+arg_10], rbx
0x18002f985  push    rbp
0x18002f986  push    rdi
0x18002f987  push    r14
0x18002f989  mov     rbp, rsp
0x18002f98c  sub     rsp, 70h
0x18002f990  mov     rax, cs:__security_cookie
0x18002f997  xor     rax, rsp
0x18002f99a  mov     [rbp+var_10], rax
0x18002f99e  mov     rax, [rcx]
0x18002f9a1  xorps   xmm0, xmm0
0x18002f9a4  mov     r14, rdx
0x18002f9a7  mov     [rbp+hProcess], 0
0x18002f9af  mov     rdi, rcx
0x18002f9b2  movups  [rbp+Buffer], xmm0
0x18002f9b6  mov     rax, [rax+0F0h]
0x18002f9bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9c2  test    eax, eax
0x18002f9c4  jnz     short loc_18002F9D0
0x18002f9c6  mov     eax, 80070057h
0x18002f9cb  jmp     loc_18002FB05
0x18002f9d0  cmp     dword ptr [r14+8], 0
0x18002f9d5  jz      loc_18002FB00
0x18002f9db  mov     rdx, [rdi+50h]; HWND
0x18002f9df  lea     r8, [rbp+hProcess]; void **
0x18002f9e3  mov     ecx, 10h; dwSize
0x18002f9e8  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18002f9ed  mov     rbx, rax
0x18002f9f0  test    rax, rax
0x18002f9f3  jnz     short loc_18002F9FF
0x18002f9f5  mov     eax, 8007000Eh
0x18002f9fa  jmp     loc_18002FB05
0x18002f9ff  mov     rcx, [rbp+hProcess]; hProcess
0x18002fa03  lea     r8, [rbp+Buffer]; lpBuffer
0x18002fa07  mov     r9d, 10h; nSize
0x18002fa0d  mov     dword ptr [rbp+Buffer], 1
0x18002fa14  mov     rdx, rbx; lpBaseAddress
0x18002fa17  mov     [rsp+70h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18002fa20  call    cs:__imp_WriteProcessMemory
0x18002fa26  mov     eax, [r14+8]
0x18002fa2a  mov     r9d, 100Eh; unsigned int
0x18002fa30  mov     r8, [rdi+50h]; HWND
0x18002fa34  dec     eax
0x18002fa36  movsxd  rcx, eax
0x18002fa39  xor     edx, edx; bool
0x18002fa3b  lea     rax, [rbp+var_28]
0x18002fa3f  mov     [rbp+var_28], 0
0x18002fa47  mov     [rsp+70h+var_40], rax; __int64 *
0x18002fa4c  mov     [rsp+70h+var_48], rbx; __int64
0x18002fa51  mov     [rsp+70h+lpNumberOfBytesWritten], rcx; unsigned __int64
0x18002fa56  mov     rcx, rdi; this
0x18002fa59  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002fa5e  test    eax, eax
0x18002fa60  js      loc_18002FB05
0x18002fa66  cmp     [rbp+var_28], 0
0x18002fa6b  jz      loc_18002FAF4
0x18002fa71  mov     rcx, [rbp+hProcess]; hProcess
0x18002fa75  lea     r8, [rbp+Buffer]; lpBuffer
0x18002fa79  mov     r9d, 10h; nSize
0x18002fa7f  mov     [rsp+70h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x18002fa88  mov     rdx, rbx; lpBaseAddress
0x18002fa8b  call    cs:__imp_ReadProcessMemory
0x18002fa91  mov     rcx, [rdi+50h]; hWndFrom
0x18002fa95  lea     r8, [rbp+Buffer]; lpPoints
0x18002fa99  mov     r9d, 2; cPoints
0x18002fa9f  xor     edx, edx; hWndTo
0x18002faa1  call    cs:__imp_MapWindowPoints
0x18002faa7  mov     eax, dword ptr [rbp+Buffer]
0x18002faaa  xor     r9d, r9d; lParam
0x18002faad  sub     dword ptr [rbp+Buffer+8], eax
0x18002fab0  xor     r8d, r8d; wParam
0x18002fab3  mov     eax, dword ptr [rbp+Buffer+4]
0x18002fab6  mov     edx, 1037h; Msg
0x18002fabb  mov     rcx, [rdi+50h]; hWnd
0x18002fabf  sub     dword ptr [rbp+Buffer+0Ch], eax
0x18002fac2  call    cs:__imp_SendMessageW
0x18002fac8  mov     rdx, [rdi+50h]; HWND
0x18002facc  lea     rcx, [rbp+Buffer]; struct tagRECT *
0x18002fad0  shr     eax, 6
0x18002fad3  not     eax
0x18002fad5  and     eax, 1
0x18002fad8  mov     r8d, eax; int
0x18002fadb  call    ?ClickOnTheRect@@YAHPEAUtagRECT@@PEAUHWND__@@H@Z; ClickOnTheRect(tagRECT *,HWND__ *,int)
0x18002fae0  test    eax, eax
0x18002fae2  jz      short loc_18002FAF4
0x18002fae4  mov     rdx, [rbp+hProcess]; hProcess
0x18002fae8  mov     rcx, rbx; lpAddress
0x18002faeb  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002faf0  xor     eax, eax
0x18002faf2  jmp     short loc_18002FB05
0x18002faf4  mov     rdx, [rbp+hProcess]; hProcess
0x18002faf8  mov     rcx, rbx; lpAddress
0x18002fafb  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002fb00  mov     eax, 80020003h
0x18002fb05  mov     rcx, [rbp+var_10]
0x18002fb09  xor     rcx, rsp; StackCookie
0x18002fb0c  call    __security_check_cookie
0x18002fb11  mov     rbx, [rsp+70h+arg_10]
0x18002fb19  add     rsp, 70h
0x18002fb1d  pop     r14
0x18002fb1f  pop     rdi
0x18002fb20  pop     rbp
0x18002fb21  retn
```
