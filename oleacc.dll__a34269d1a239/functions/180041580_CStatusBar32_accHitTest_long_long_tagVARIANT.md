# CStatusBar32::accHitTest(long,long,tagVARIANT *)

- ea: `0x180041580`
- end: `0x18004173f`
- name: `?accHitTest@CStatusBar32@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(CStatusBar32 *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x1800191c0`
- `0x180041580`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800416b5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800416b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041713`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041713`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180041679`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180041679`
- `USER32!ScreenToClient` at `0x1800416cb`
- `USER32!ScreenToClient` at `0x1800416cb`

## pseudocode

```c
int __fastcall CStatusBar32::accHitTest(HWND *this, int a2, int a3, struct tagVARIANT *a4)
{
  HWND v4; // rax
  int result; // eax
  unsigned __int64 v10; // rdi
  void *v11; // r14
  HWND v12; // r8
  int v13; // esi
  SIZE_T v14; // rsi
  _DWORD *v15; // rax
  _DWORD *v16; // rdi
  HWND v17; // rcx
  LONG x; // edx
  LONG v19; // r9d
  int i; // eax
  int v21; // ecx
  unsigned __int64 lpNumberOfBytesRead; // [rsp+20h] [rbp-38h]
  HANDLE hProcess; // [rsp+40h] [rbp-18h] BYREF
  struct tagPOINT Point; // [rsp+A0h] [rbp+48h] BYREF

  v4 = *this;
  hProcess = 0;
  (*((void (__fastcall **)(HWND *))v4 + 29))(this);
  result = CClient::accHitTest((CClient *)this, a2, a3, a4);
  if ( !result && a4->vt == 3 && !a4->lVal && *((_DWORD *)this + 23) )
  {
    v10 = 4LL * *((unsigned int *)this + 23);
    if ( v10 > 0xFFFFFFFF )
    {
      return -2147024362;
    }
    else
    {
      v11 = SharedAlloc((unsigned int)v10, this[10], &hProcess);
      if ( !v11 )
        return -2147024882;
      v12 = this[10];
      lpNumberOfBytesRead = *((int *)this + 23);
      Point = 0;
      v13 = CAccessible::AccSendMessageTimeout(
              (CAccessible *)this,
              0,
              v12,
              0x406u,
              lpNumberOfBytesRead,
              (__int64)v11,
              (__int64 *)&Point);
      if ( v13 < 0 )
        goto LABEL_13;
      if ( *(__int64 *)&Point > *((int *)this + 23) )
      {
        v13 = 1;
LABEL_13:
        SharedFree(v11, hProcess);
        return v13;
      }
      Point = 0;
      v14 = (unsigned int)v10;
      v15 = LocalAlloc(0x40u, (unsigned int)v10);
      v16 = v15;
      if ( !v15 )
      {
        v13 = -2147024882;
        goto LABEL_13;
      }
      ReadProcessMemory(hProcess, v11, v15, v14, 0);
      v17 = this[10];
      Point.x = a2;
      Point.y = a3;
      ScreenToClient(v17, &Point);
      x = Point.x;
      v19 = 0;
      for ( i = 0; i < *((_DWORD *)this + 23); ++i )
      {
        v21 = v16[i];
        if ( v21 == -1 )
        {
          v16[i] = 0x7FFFFFFF;
          v21 = 0x7FFFFFFF;
          x = Point.x;
        }
        if ( x >= v19 && x < v21 )
        {
          a4->lVal = i + 1;
          break;
        }
        v19 = v21;
      }
      LocalFree(v16);
      SharedFree(v11, hProcess);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180041580  push    rbp
0x180041582  push    rbx
0x180041583  push    rsi
0x180041584  push    rdi
0x180041585  push    r12
0x180041587  push    r13
0x180041589  push    r14
0x18004158b  push    r15
0x18004158d  mov     rbp, rsp
0x180041590  sub     rsp, 58h
0x180041594  mov     rax, [rcx]
0x180041597  xor     esi, esi
0x180041599  mov     r15, r9
0x18004159c  mov     [rbp+hProcess], rsi
0x1800415a0  mov     r12d, r8d
0x1800415a3  mov     r13d, edx
0x1800415a6  mov     rbx, rcx
0x1800415a9  mov     rax, [rax+0E8h]
0x1800415b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415b5  mov     r9, r15; struct tagVARIANT *
0x1800415b8  mov     r8d, r12d; int
0x1800415bb  mov     edx, r13d; int
0x1800415be  mov     rcx, rbx; this
0x1800415c1  call    ?accHitTest@CClient@@UEAAJJJPEAUtagVARIANT@@@Z; CClient::accHitTest(long,long,tagVARIANT *)
0x1800415c6  test    eax, eax
0x1800415c8  jnz     loc_18004172E
0x1800415ce  cmp     word ptr [r15], 3
0x1800415d3  jnz     loc_18004172E
0x1800415d9  cmp     [r15+8], esi
0x1800415dd  jnz     loc_18004172E
0x1800415e3  cmp     [rbx+5Ch], esi
0x1800415e6  jz      loc_18004172E
0x1800415ec  mov     edi, [rbx+5Ch]
0x1800415ef  mov     eax, 0FFFFFFFFh
0x1800415f4  shl     rdi, 2
0x1800415f8  cmp     rdi, rax
0x1800415fb  ja      loc_180041729
0x180041601  mov     rdx, [rbx+50h]; HWND
0x180041605  lea     r8, [rbp+hProcess]; void **
0x180041609  mov     ecx, edi; dwSize
0x18004160b  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180041610  mov     r14, rax
0x180041613  test    rax, rax
0x180041616  jnz     short loc_180041622
0x180041618  mov     eax, 8007000Eh
0x18004161d  jmp     loc_18004172E
0x180041622  movsxd  rax, dword ptr [rbx+5Ch]
0x180041626  lea     rcx, [rbp+Point]
0x18004162a  mov     r8, [rbx+50h]; HWND
0x18004162e  mov     r9d, 406h; unsigned int
0x180041634  mov     [rsp+58h+var_28], rcx; __int64 *
0x180041639  xor     edx, edx; bool
0x18004163b  mov     [rsp+58h+var_30], r14; __int64
0x180041640  mov     rcx, rbx; this
0x180041643  mov     [rsp+58h+lpNumberOfBytesRead], rax; unsigned __int64
0x180041648  mov     qword ptr [rbp+Point.x], rsi
0x18004164c  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180041651  mov     esi, eax
0x180041653  test    eax, eax
0x180041655  js      short loc_18004168C
0x180041657  movsxd  rax, dword ptr [rbx+5Ch]
0x18004165b  cmp     qword ptr [rbp+Point.x], rax
0x18004165f  jle     short loc_180041668
0x180041661  mov     esi, 1
0x180041666  jmp     short loc_18004168C
0x180041668  mov     edx, edi; uBytes
0x18004166a  mov     ecx, 40h ; '@'; uFlags
0x18004166f  mov     qword ptr [rbp+Point.x], 0
0x180041677  mov     esi, edi
0x180041679  call    cs:__imp_LocalAlloc
0x18004167f  mov     rdi, rax
0x180041682  test    rax, rax
0x180041685  jnz     short loc_18004169F
0x180041687  mov     esi, 8007000Eh
0x18004168c  mov     rdx, [rbp+hProcess]; hProcess
0x180041690  mov     rcx, r14; lpAddress
0x180041693  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180041698  mov     eax, esi
0x18004169a  jmp     loc_18004172E
0x18004169f  mov     rcx, [rbp+hProcess]; hProcess
0x1800416a3  mov     r9, rsi; nSize
0x1800416a6  mov     r8, rdi; lpBuffer
0x1800416a9  mov     [rsp+58h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x1800416b2  mov     rdx, r14; lpBaseAddress
0x1800416b5  call    cs:__imp_ReadProcessMemory
0x1800416bb  mov     rcx, [rbx+50h]; hWnd
0x1800416bf  lea     rdx, [rbp+Point]; lpPoint
0x1800416c3  mov     [rbp+Point.x], r13d
0x1800416c7  mov     [rbp+Point.y], r12d
0x1800416cb  call    cs:__imp_ScreenToClient
0x1800416d1  mov     edx, [rbp+Point.x]
0x1800416d4  xor     r9d, r9d
0x1800416d7  xor     eax, eax
0x1800416d9  mov     r10d, 7FFFFFFFh
0x1800416df  cmp     eax, [rbx+5Ch]
0x1800416e2  jge     short loc_180041710
0x1800416e4  movsxd  r8, eax
0x1800416e7  mov     ecx, [rdi+r8*4]
0x1800416eb  cmp     ecx, 0FFFFFFFFh
0x1800416ee  jnz     short loc_1800416FA
0x1800416f0  mov     [rdi+r8*4], r10d
0x1800416f4  mov     ecx, r10d
0x1800416f7  mov     edx, [rbp+Point.x]
0x1800416fa  cmp     edx, r9d
0x1800416fd  jl      short loc_180041703
0x1800416ff  cmp     edx, ecx
0x180041701  jl      short loc_18004170A
0x180041703  mov     r9d, ecx
0x180041706  inc     eax
0x180041708  jmp     short loc_1800416DF
0x18004170a  inc     eax
0x18004170c  mov     [r15+8], eax
0x180041710  mov     rcx, rdi; hMem
0x180041713  call    cs:__imp_LocalFree
0x180041719  mov     rdx, [rbp+hProcess]; hProcess
0x18004171d  mov     rcx, r14; lpAddress
0x180041720  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180041725  xor     eax, eax
0x180041727  jmp     short loc_18004172E
0x180041729  mov     eax, 80070216h
0x18004172e  add     rsp, 58h
0x180041732  pop     r15
0x180041734  pop     r14
0x180041736  pop     r13
0x180041738  pop     r12
0x18004173a  pop     rdi
0x18004173b  pop     rsi
0x18004173c  pop     rbx
0x18004173d  pop     rbp
0x18004173e  retn
```
