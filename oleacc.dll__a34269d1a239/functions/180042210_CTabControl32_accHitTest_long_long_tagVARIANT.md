# CTabControl32::accHitTest(long,long,tagVARIANT *)

- ea: `0x180042210`
- end: `0x180042333`
- name: `?accHitTest@CTabControl32@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(CTabControl32 *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x1800191c0`
- `0x180042210`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800422c2`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800422c2`
- `USER32!ScreenToClient` at `0x18004229a`
- `USER32!ScreenToClient` at `0x18004229a`

## pseudocode

```c
int __fastcall CTabControl32::accHitTest(HWND *this, int a2, int a3, struct tagVARIANT *a4)
{
  int result; // eax
  void *v9; // rdi
  HWND v10; // rcx
  HANDLE v11; // rsi
  HWND v12; // r8
  int v13; // ebp
  LONG v14; // eax
  HANDLE hProcess[9]; // [rsp+40h] [rbp-48h] BYREF
  struct tagPOINT Point; // [rsp+A8h] [rbp+20h] BYREF

  hProcess[0] = 0;
  Point = 0;
  a4->vt = 0;
  result = CClient::accHitTest((CClient *)this, a2, a3, a4);
  if ( !result && a4->vt == 3 )
  {
    v9 = SharedAlloc(0xCu, this[10], hProcess);
    if ( v9 )
    {
      v10 = this[10];
      Point.x = a2;
      Point.y = a3;
      ScreenToClient(v10, &Point);
      v11 = hProcess[0];
      WriteProcessMemory(hProcess[0], v9, &Point, 8u, 0);
      v12 = this[10];
      hProcess[0] = 0;
      v13 = CAccessible::AccSendMessageTimeout(
              (CAccessible *)this,
              0,
              v12,
              0x130Du,
              0,
              (__int64)v9,
              (__int64 *)hProcess);
      SharedFree(v9, v11);
      if ( v13 >= 0 )
      {
        v14 = LODWORD(hProcess[0]) + 1;
        a4->vt = 3;
        a4->lVal = v14;
        return 0;
      }
      else
      {
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
0x180042210  mov     rax, rsp
0x180042213  push    rbx
0x180042214  push    rbp
0x180042215  push    rsi
0x180042216  push    rdi
0x180042217  push    r12
0x180042219  push    r14
0x18004221b  sub     rsp, 58h
0x18004221f  mov     qword ptr [rax-48h], 0
0x180042227  mov     rbx, r9
0x18004222a  mov     qword ptr [rax+20h], 0
0x180042232  mov     esi, r8d
0x180042235  xor     eax, eax
0x180042237  mov     r14d, edx
0x18004223a  mov     [r9], ax
0x18004223e  mov     rbp, rcx
0x180042241  call    ?accHitTest@CClient@@UEAAJJJPEAUtagVARIANT@@@Z; CClient::accHitTest(long,long,tagVARIANT *)
0x180042246  test    eax, eax
0x180042248  jnz     loc_180042326
0x18004224e  lea     r12d, [rax+3]
0x180042252  cmp     [rbx], r12w
0x180042256  jnz     loc_180042326
0x18004225c  mov     rdx, [rbp+50h]; HWND
0x180042260  lea     r8, [rsp+88h+hProcess]; void **
0x180042265  lea     ecx, [rax+0Ch]; dwSize
0x180042268  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18004226d  mov     rdi, rax
0x180042270  test    rax, rax
0x180042273  jnz     short loc_18004227F
0x180042275  mov     eax, 8007000Eh
0x18004227a  jmp     loc_180042326
0x18004227f  mov     rcx, [rbp+50h]; hWnd
0x180042283  lea     rdx, [rsp+88h+Point]; lpPoint
0x18004228b  mov     [rsp+88h+Point.x], r14d
0x180042293  mov     [rsp+88h+Point.y], esi
0x18004229a  call    cs:__imp_ScreenToClient
0x1800422a0  mov     rsi, [rsp+88h+hProcess]
0x1800422a5  lea     r8, [rsp+88h+Point]; lpBuffer
0x1800422ad  mov     rcx, rsi; hProcess
0x1800422b0  mov     [rsp+88h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x1800422b9  mov     r9d, 8; nSize
0x1800422bf  mov     rdx, rdi; lpBaseAddress
0x1800422c2  call    cs:__imp_WriteProcessMemory
0x1800422c8  mov     r8, [rbp+50h]; HWND
0x1800422cc  lea     rax, [rsp+88h+hProcess]
0x1800422d1  mov     [rsp+88h+var_58], rax; __int64 *
0x1800422d6  mov     r9d, 130Dh; unsigned int
0x1800422dc  mov     [rsp+88h+var_60], rdi; __int64
0x1800422e1  xor     edx, edx; bool
0x1800422e3  mov     rcx, rbp; this
0x1800422e6  mov     [rsp+88h+lpNumberOfBytesWritten], 0; unsigned __int64
0x1800422ef  mov     [rsp+88h+hProcess], 0
0x1800422f8  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x1800422fd  mov     ebp, eax
0x1800422ff  mov     rdx, rsi; hProcess
0x180042302  mov     rcx, rdi; lpAddress
0x180042305  test    eax, eax
0x180042307  jns     short loc_180042312
0x180042309  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18004230e  mov     eax, ebp
0x180042310  jmp     short loc_180042326
0x180042312  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180042317  mov     eax, dword ptr [rsp+88h+hProcess]
0x18004231b  inc     eax
0x18004231d  mov     [rbx], r12w
0x180042321  mov     [rbx+8], eax
0x180042324  xor     eax, eax
0x180042326  add     rsp, 58h
0x18004232a  pop     r14
0x18004232c  pop     r12
0x18004232e  pop     rdi
0x18004232f  pop     rsi
0x180042330  pop     rbp
0x180042331  pop     rbx
0x180042332  retn
```
