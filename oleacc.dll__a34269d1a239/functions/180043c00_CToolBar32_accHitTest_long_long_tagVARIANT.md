# CToolBar32::accHitTest(long,long,tagVARIANT *)

- ea: `0x180043c00`
- end: `0x180043dcc`
- name: `?accHitTest@CToolBar32@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(CToolBar32 *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x1800191c0`
- `0x18001e4c0`
- `0x180043c00`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180043d23`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180043d23`
- `USER32!ScreenToClient` at `0x180043c8f`
- `USER32!ScreenToClient` at `0x180043c8f`
- `USER32!PtInRect` at `0x180043d31`
- `USER32!PtInRect` at `0x180043d31`

## pseudocode

```c
int __fastcall CToolBar32::accHitTest(HWND *this, int a2, int a3, struct tagVARIANT *a4)
{
  HWND v4; // rax
  void (__fastcall *v9)(HWND *); // rax
  int result; // eax
  HWND v11; // rcx
  void *v12; // rdi
  int i; // esi
  HWND v14; // r8
  int v15; // r15d
  HWND v16; // rax
  __int128 v17; // xmm0
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int (__fastcall *v19)(HWND *, __int128 *, __int64 *); // rax
  __int64 v20; // [rsp+40h] [rbp-39h] BYREF
  struct tagPOINT Point; // [rsp+48h] [rbp-31h] BYREF
  HANDLE hProcess; // [rsp+50h] [rbp-29h] BYREF
  __int128 v23; // [rsp+60h] [rbp-19h] BYREF
  IRecordInfo *v24; // [rsp+70h] [rbp-9h]
  RECT Buffer; // [rsp+80h] [rbp+7h] BYREF

  v4 = *this;
  Point = 0;
  hProcess = 0;
  v9 = (void (__fastcall *)(HWND *))*((_QWORD *)v4 + 29);
  Buffer = 0;
  v9(this);
  result = CClient::accHitTest((CClient *)this, a2, a3, a4);
  if ( !result && a4->vt == 3 && !a4->lVal )
  {
    v11 = this[10];
    Point.x = a2;
    Point.y = a3;
    ScreenToClient(v11, &Point);
    v12 = SharedAlloc(0x10u, this[10], &hProcess);
    if ( v12 )
    {
      for ( i = 0; i < *((_DWORD *)this + 23); ++i )
      {
        v14 = this[10];
        v20 = 0;
        v15 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, v14, 0x41Du, i, (__int64)v12, &v20);
        if ( v15 < 0 )
          goto LABEL_15;
        if ( v20 )
        {
          ReadProcessMemory(hProcess, v12, &Buffer, 0x10u, 0);
          if ( PtInRect(&Buffer, Point) )
          {
            a4->vt = 3;
            a4->lVal = i + 1;
            v16 = *this;
            v17 = *(_OWORD *)&a4->vt;
            v20 = 0;
            pRecInfo = a4->pRecInfo;
            v19 = (unsigned int (__fastcall *)(HWND *, __int128 *, __int64 *))*((_QWORD *)v16 + 9);
            v23 = v17;
            v24 = pRecInfo;
            if ( !v19(this, &v23, &v20) )
            {
              a4->llVal = v20;
              a4->vt = 9;
            }
            v15 = 0;
LABEL_15:
            SharedFree(v12, hProcess);
            return v15;
          }
        }
      }
      SharedFree(v12, hProcess);
      return 0;
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
0x180043c00  push    rbp
0x180043c02  push    rbx
0x180043c03  push    rsi
0x180043c04  push    rdi
0x180043c05  push    r14
0x180043c07  push    r15
0x180043c09  lea     rbp, [rsp-2Fh]
0x180043c0e  sub     rsp, 0A8h
0x180043c15  mov     rax, cs:__security_cookie
0x180043c1c  xor     rax, rsp
0x180043c1f  mov     [rbp+57h+var_40], rax
0x180043c23  mov     rax, [rcx]
0x180043c26  xorps   xmm0, xmm0
0x180043c29  mov     rbx, r9
0x180043c2c  mov     qword ptr [rbp+57h+Point.x], 0
0x180043c34  mov     esi, r8d
0x180043c37  mov     [rbp+57h+hProcess], 0
0x180043c3f  mov     edi, edx
0x180043c41  mov     r14, rcx
0x180043c44  mov     rax, [rax+0E8h]
0x180043c4b  movups  [rbp+57h+Buffer], xmm0
0x180043c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c54  mov     r9, rbx; struct tagVARIANT *
0x180043c57  mov     r8d, esi; int
0x180043c5a  mov     edx, edi; int
0x180043c5c  mov     rcx, r14; this
0x180043c5f  call    ?accHitTest@CClient@@UEAAJJJPEAUtagVARIANT@@@Z; CClient::accHitTest(long,long,tagVARIANT *)
0x180043c64  test    eax, eax
0x180043c66  jnz     loc_180043DB0
0x180043c6c  lea     ecx, [rax+3]
0x180043c6f  cmp     [rbx], cx
0x180043c72  jnz     loc_180043DB0
0x180043c78  cmp     [rbx+8], eax
0x180043c7b  jnz     loc_180043DB0
0x180043c81  mov     rcx, [r14+50h]; hWnd
0x180043c85  lea     rdx, [rbp+57h+Point]; lpPoint
0x180043c89  mov     [rbp+57h+Point.x], edi
0x180043c8c  mov     [rbp+57h+Point.y], esi
0x180043c8f  call    cs:__imp_ScreenToClient
0x180043c95  mov     rdx, [r14+50h]; HWND
0x180043c99  lea     r8, [rbp+57h+hProcess]; void **
0x180043c9d  mov     ecx, 10h; dwSize
0x180043ca2  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180043ca7  mov     rdi, rax
0x180043caa  test    rax, rax
0x180043cad  jnz     short loc_180043CB9
0x180043caf  mov     eax, 8007000Eh
0x180043cb4  jmp     loc_180043DB0
0x180043cb9  xor     esi, esi
0x180043cbb  cmp     esi, [r14+5Ch]
0x180043cbf  jge     loc_180043DA2
0x180043cc5  mov     r8, [r14+50h]; HWND
0x180043cc9  lea     rcx, [rbp+57h+var_90]
0x180043ccd  mov     [rsp+0D0h+var_A0], rcx; __int64 *
0x180043cd2  mov     r9d, 41Dh; unsigned int
0x180043cd8  movsxd  rax, esi
0x180043cdb  mov     rcx, r14; this
0x180043cde  mov     [rsp+0D0h+var_A8], rdi; __int64
0x180043ce3  xor     edx, edx; bool
0x180043ce5  mov     [rsp+0D0h+lpNumberOfBytesRead], rax; unsigned __int64
0x180043cea  mov     [rbp+57h+var_90], 0
0x180043cf2  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180043cf7  mov     r15d, eax
0x180043cfa  test    eax, eax
0x180043cfc  js      loc_180043D91
0x180043d02  cmp     [rbp+57h+var_90], 0
0x180043d07  jz      short loc_180043D3B
0x180043d09  mov     rcx, [rbp+57h+hProcess]; hProcess
0x180043d0d  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180043d11  mov     r9d, 10h; nSize
0x180043d17  mov     [rsp+0D0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x180043d20  mov     rdx, rdi; lpBaseAddress
0x180043d23  call    cs:__imp_ReadProcessMemory
0x180043d29  mov     rdx, qword ptr [rbp+57h+Point.x]; pt
0x180043d2d  lea     rcx, [rbp+57h+Buffer]; lprc
0x180043d31  call    cs:__imp_PtInRect
0x180043d37  test    eax, eax
0x180043d39  jnz     short loc_180043D42
0x180043d3b  inc     esi
0x180043d3d  jmp     loc_180043CBB
0x180043d42  mov     word ptr [rbx], 3
0x180043d47  lea     eax, [rsi+1]
0x180043d4a  mov     [rbx+8], eax
0x180043d4d  lea     r8, [rbp+57h+var_90]
0x180043d51  mov     rax, [r14]
0x180043d54  lea     rdx, [rbp+57h+var_70]
0x180043d58  movups  xmm0, xmmword ptr [rbx]
0x180043d5b  mov     rcx, r14
0x180043d5e  mov     [rbp+57h+var_90], 0
0x180043d66  movsd   xmm1, qword ptr [rbx+10h]
0x180043d6b  mov     rax, [rax+48h]
0x180043d6f  movaps  [rbp+57h+var_70], xmm0
0x180043d73  movsd   [rbp+57h+var_60], xmm1
0x180043d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d7d  test    eax, eax
0x180043d7f  jnz     short loc_180043D8E
0x180043d81  mov     rax, [rbp+57h+var_90]
0x180043d85  mov     [rbx+8], rax
0x180043d89  mov     word ptr [rbx], 9
0x180043d8e  xor     r15d, r15d
0x180043d91  mov     rdx, [rbp+57h+hProcess]; hProcess
0x180043d95  mov     rcx, rdi; lpAddress
0x180043d98  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180043d9d  mov     eax, r15d
0x180043da0  jmp     short loc_180043DB0
0x180043da2  mov     rdx, [rbp+57h+hProcess]; hProcess
0x180043da6  mov     rcx, rdi; lpAddress
0x180043da9  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180043dae  xor     eax, eax
0x180043db0  mov     rcx, [rbp+57h+var_40]
0x180043db4  xor     rcx, rsp; StackCookie
0x180043db7  call    __security_check_cookie
0x180043dbc  add     rsp, 0A8h
0x180043dc3  pop     r15
0x180043dc5  pop     r14
0x180043dc7  pop     rdi
0x180043dc8  pop     rsi
0x180043dc9  pop     rbx
0x180043dca  pop     rbp
0x180043dcb  retn
```
