# CHeader32::accHitTest(long,long,tagVARIANT *)

- ea: `0x18002c660`
- end: `0x18002c7c2`
- name: `?accHitTest@CHeader32@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(CHeader32 *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x1800191c0`
- `0x18002c660`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002c799`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002c799`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002c727`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002c727`
- `USER32!ScreenToClient` at `0x18002c702`
- `USER32!ScreenToClient` at `0x18002c702`

## pseudocode

```c
int __fastcall CHeader32::accHitTest(HWND *this, int a2, int a3, struct tagVARIANT *a4)
{
  int result; // eax
  char *v9; // rbx
  HWND v10; // rcx
  HANDLE v11; // rsi
  HWND v12; // r8
  int v13; // ebp
  struct tagPOINT Point; // [rsp+60h] [rbp+8h] BYREF
  HANDLE hProcess; // [rsp+78h] [rbp+20h] BYREF

  hProcess = 0;
  Point = 0;
  a4->vt = 0;
  (*((void (__fastcall **)(HWND *))*this + 29))(this);
  result = CClient::accHitTest((CClient *)this, a2, a3, a4);
  if ( !result && a4->vt == 3 && !a4->lVal )
  {
    v9 = (char *)SharedAlloc(0x10u, this[10], &hProcess);
    if ( v9 )
    {
      v10 = this[10];
      Point.x = a2;
      Point.y = a3;
      ScreenToClient(v10, &Point);
      v11 = hProcess;
      WriteProcessMemory(hProcess, v9, &Point, 8u, 0);
      v12 = this[10];
      hProcess = 0;
      v13 = CAccessible::AccSendMessageTimeout(
              (CAccessible *)this,
              0,
              v12,
              0x1206u,
              0,
              (__int64)v9,
              (__int64 *)&hProcess);
      if ( v13 >= 0 )
      {
        if ( hProcess != (HANDLE)-1LL )
        {
          ReadProcessMemory(v11, v9 + 12, &a4->decVal.8, 4u, 0);
          ++a4->lVal;
        }
        SharedFree(v9, v11);
        return 0;
      }
      else
      {
        SharedFree(v9, v11);
        return v13;
      }
    }
    else
    {
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c660  mov     rax, rsp
0x18002c663  mov     [rax+10h], rbx
0x18002c667  mov     [rax+18h], rbp
0x18002c66b  push    rsi
0x18002c66c  push    rdi
0x18002c66d  push    r14
0x18002c66f  sub     rsp, 40h
0x18002c673  mov     qword ptr [rax+20h], 0
0x18002c67b  mov     rdi, r9
0x18002c67e  mov     qword ptr [rax+8], 0
0x18002c686  mov     esi, r8d
0x18002c689  xor     eax, eax
0x18002c68b  mov     ebp, edx
0x18002c68d  mov     [r9], ax
0x18002c691  mov     r14, rcx
0x18002c694  mov     rax, [rcx]
0x18002c697  mov     rax, [rax+0E8h]
0x18002c69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6a3  mov     r9, rdi; struct tagVARIANT *
0x18002c6a6  mov     r8d, esi; int
0x18002c6a9  mov     edx, ebp; int
0x18002c6ab  mov     rcx, r14; this
0x18002c6ae  call    ?accHitTest@CClient@@UEAAJJJPEAUtagVARIANT@@@Z; CClient::accHitTest(long,long,tagVARIANT *)
0x18002c6b3  test    eax, eax
0x18002c6b5  jnz     loc_18002C7AF
0x18002c6bb  cmp     word ptr [rdi], 3
0x18002c6bf  jnz     loc_18002C7AF
0x18002c6c5  cmp     [rdi+8], eax
0x18002c6c8  jnz     loc_18002C7AF
0x18002c6ce  mov     rdx, [r14+50h]; HWND
0x18002c6d2  lea     r8, [rsp+58h+hProcess]; void **
0x18002c6d7  lea     ecx, [rax+10h]; dwSize
0x18002c6da  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18002c6df  mov     rbx, rax
0x18002c6e2  test    rax, rax
0x18002c6e5  jnz     short loc_18002C6F1
0x18002c6e7  mov     eax, 8007000Eh
0x18002c6ec  jmp     loc_18002C7AF
0x18002c6f1  mov     rcx, [r14+50h]; hWnd
0x18002c6f5  lea     rdx, [rsp+58h+Point]; lpPoint
0x18002c6fa  mov     [rsp+58h+Point.x], ebp
0x18002c6fe  mov     [rsp+58h+Point.y], esi
0x18002c702  call    cs:__imp_ScreenToClient
0x18002c708  mov     rsi, [rsp+58h+hProcess]
0x18002c70d  lea     r8, [rsp+58h+Point]; lpBuffer
0x18002c712  mov     rcx, rsi; hProcess
0x18002c715  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18002c71e  mov     r9d, 8; nSize
0x18002c724  mov     rdx, rbx; lpBaseAddress
0x18002c727  call    cs:__imp_WriteProcessMemory
0x18002c72d  mov     r8, [r14+50h]; HWND
0x18002c731  lea     rax, [rsp+58h+hProcess]
0x18002c736  mov     [rsp+58h+var_28], rax; __int64 *
0x18002c73b  mov     r9d, 1206h; unsigned int
0x18002c741  mov     [rsp+58h+var_30], rbx; __int64
0x18002c746  xor     edx, edx; bool
0x18002c748  mov     rcx, r14; this
0x18002c74b  mov     [rsp+58h+lpNumberOfBytesWritten], 0; unsigned __int64
0x18002c754  mov     [rsp+58h+hProcess], 0
0x18002c75d  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002c762  mov     ebp, eax
0x18002c764  test    eax, eax
0x18002c766  jns     short loc_18002C777
0x18002c768  mov     rdx, rsi; hProcess
0x18002c76b  mov     rcx, rbx; lpAddress
0x18002c76e  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002c773  mov     eax, ebp
0x18002c775  jmp     short loc_18002C7AF
0x18002c777  cmp     [rsp+58h+hProcess], 0FFFFFFFFFFFFFFFFh
0x18002c77d  jz      short loc_18002C7A2
0x18002c77f  lea     rdx, [rbx+0Ch]; lpBaseAddress
0x18002c783  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x18002c78c  mov     r9d, 4; nSize
0x18002c792  lea     r8, [rdi+8]; lpBuffer
0x18002c796  mov     rcx, rsi; hProcess
0x18002c799  call    cs:__imp_ReadProcessMemory
0x18002c79f  inc     dword ptr [rdi+8]
0x18002c7a2  mov     rdx, rsi; hProcess
0x18002c7a5  mov     rcx, rbx; lpAddress
0x18002c7a8  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002c7ad  xor     eax, eax
0x18002c7af  mov     rbx, [rsp+58h+arg_8]
0x18002c7b4  mov     rbp, [rsp+58h+arg_10]
0x18002c7b9  add     rsp, 40h
0x18002c7bd  pop     r14
0x18002c7bf  pop     rdi
0x18002c7c0  pop     rsi
0x18002c7c1  retn
```
