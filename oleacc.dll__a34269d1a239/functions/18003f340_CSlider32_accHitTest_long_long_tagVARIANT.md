# CSlider32::accHitTest(long,long,tagVARIANT *)

- ea: `0x18003f340`
- end: `0x18003f5d6`
- name: `?accHitTest@CSlider32@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `662`
- prototype: `__int64 __fastcall(CSlider32 *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x1800191c0`
- `0x18001e4c0`
- `0x18003f340`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003f459`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003f522`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003f459`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003f522`
- `USER32!ScreenToClient` at `0x18003f3de`
- `USER32!ScreenToClient` at `0x18003f3de`
- `USER32!PtInRect` at `0x18003f467`
- `USER32!PtInRect` at `0x18003f467`
- `USER32!GetWindowLongW` at `0x18003f3c0`
- `USER32!GetWindowLongW` at `0x18003f3c0`

## pseudocode

```c
__int64 __fastcall CSlider32::accHitTest(HWND *this, int a2, int a3, struct tagVARIANT *a4)
{
  unsigned int v8; // esi
  HWND v9; // rcx
  LPVOID v10; // rax
  void *v11; // r14
  int v13; // eax
  HANDLE v14; // r15
  LPVOID v15; // rax
  void *v16; // rsi
  int v17; // r12d
  int v18; // edx
  int v19; // r8d
  LONG v20; // r8d
  __int64 v21; // rax
  struct tagPOINT Point; // [rsp+40h] [rbp-40h] BYREF
  HANDLE v23; // [rsp+48h] [rbp-38h] BYREF
  HANDLE hProcess; // [rsp+50h] [rbp-30h] BYREF
  __int128 v25; // [rsp+58h] [rbp-28h] BYREF
  RECT Buffer; // [rsp+68h] [rbp-18h] BYREF

  Point = 0;
  hProcess = 0;
  Buffer = 0;
  v25 = 0;
  v23 = 0;
  v8 = CClient::accHitTest((CClient *)this, a2, a3, a4);
  if ( v8 || a4->vt != 3 || a4->lVal || (GetWindowLongW(this[10], -16) & 0x80u) != 0 )
    return v8;
  v9 = this[10];
  Point.x = a2;
  Point.y = a3;
  ScreenToClient(v9, &Point);
  v10 = SharedAlloc(0x10u, this[10], &hProcess);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  v13 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, this[10], 0x419u, 0, (__int64)v10, 0);
  v14 = hProcess;
  v8 = v13;
  if ( v13 < 0 )
  {
LABEL_14:
    SharedFree(v11, v14);
    return v8;
  }
  ReadProcessMemory(hProcess, v11, &Buffer, 0x10u, 0);
  if ( !PtInRect(&Buffer, Point) )
  {
    v15 = SharedAlloc(0x10u, this[10], &v23);
    v16 = v15;
    if ( v15 )
    {
      v17 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, this[10], 0x41Au, 0, (__int64)v15, 0);
      if ( v17 >= 0 )
      {
        ReadProcessMemory(v23, v16, &v25, 0x10u, 0);
        v18 = *((_DWORD *)this + 36);
        if ( v18 )
        {
          *(_QWORD *)&v25 = __PAIR64__(v25, DWORD1(v25));
          *((_QWORD *)&v25 + 1) = __PAIR64__(DWORD2(v25), HIDWORD(v25));
        }
        v19 = *(LONG *)((char *)&Point.x + (v18 == 0 ? 4 : 0));
        if ( v19 >= *(_DWORD *)((char *)&v25 + (v18 == 0 ? 4 : 0))
          && v19 < *(_DWORD *)((char *)&v25 + (-(__int64)(v18 != 0) & 0xFFFFFFFFFFFFFFFCuLL) + 12) )
        {
          v20 = *(LONG *)((char *)&Point.x + (v18 != 0 ? 4 : 0));
          if ( v20 < *(_DWORD *)((char *)&v25 + (v18 != 0 ? 4 : 0))
            || v20 >= *(LONG *)((char *)&Buffer.left + (v18 != 0 ? 4 : 0)) )
          {
            v21 = v18 != 0 ? 4 : 0;
            if ( v20 >= *(LONG *)((char *)&Buffer.right + v21) && v20 < *(_DWORD *)((char *)&v25 + v21 + 8) )
              a4->lVal = 3;
          }
          else
          {
            a4->lVal = 1;
          }
        }
        SharedFree(v16, v23);
        goto LABEL_27;
      }
      SharedFree(v16, v23);
      v8 = v17;
    }
    else
    {
      v8 = -2147024882;
    }
    goto LABEL_14;
  }
  a4->lVal = 2;
LABEL_27:
  SharedFree(v11, v14);
  return 0;
}

```

## disassembly

```asm
0x18003f340  push    rbp
0x18003f342  push    rbx
0x18003f343  push    rsi
0x18003f344  push    rdi
0x18003f345  push    r12
0x18003f347  push    r14
0x18003f349  push    r15
0x18003f34b  mov     rbp, rsp
0x18003f34e  sub     rsp, 80h
0x18003f355  mov     rax, cs:__security_cookie
0x18003f35c  xor     rax, rsp
0x18003f35f  mov     [rbp+var_8], rax
0x18003f363  xorps   xmm0, xmm0
0x18003f366  mov     qword ptr [rbp+Point.x], 0
0x18003f36e  xorps   xmm1, xmm1
0x18003f371  mov     [rbp+hProcess], 0
0x18003f379  movups  [rbp+Buffer], xmm0
0x18003f37d  mov     rdi, r9
0x18003f380  mov     r15d, r8d
0x18003f383  movups  [rbp+var_28], xmm1
0x18003f387  mov     r14d, edx
0x18003f38a  mov     [rbp+var_38], 0
0x18003f392  mov     rbx, rcx
0x18003f395  call    ?accHitTest@CClient@@UEAAJJJPEAUtagVARIANT@@@Z; CClient::accHitTest(long,long,tagVARIANT *)
0x18003f39a  mov     esi, eax
0x18003f39c  test    eax, eax
0x18003f39e  jnz     loc_18003F4E8
0x18003f3a4  lea     eax, [rsi+3]
0x18003f3a7  cmp     [rdi], ax
0x18003f3aa  jnz     loc_18003F4E8
0x18003f3b0  cmp     [rdi+8], esi
0x18003f3b3  jnz     loc_18003F4E8
0x18003f3b9  mov     rcx, [rbx+50h]; hWnd
0x18003f3bd  lea     edx, [rsi-10h]; nIndex
0x18003f3c0  call    cs:__imp_GetWindowLongW
0x18003f3c6  test    al, al
0x18003f3c8  js      loc_18003F4E8
0x18003f3ce  mov     rcx, [rbx+50h]; hWnd
0x18003f3d2  lea     rdx, [rbp+Point]; lpPoint
0x18003f3d6  mov     [rbp+Point.x], r14d
0x18003f3da  mov     [rbp+Point.y], r15d
0x18003f3de  call    cs:__imp_ScreenToClient
0x18003f3e4  mov     rdx, [rbx+50h]; HWND
0x18003f3e8  lea     r12d, [rsi+10h]
0x18003f3ec  mov     ecx, r12d; dwSize
0x18003f3ef  lea     r8, [rbp+hProcess]; void **
0x18003f3f3  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18003f3f8  mov     r14, rax
0x18003f3fb  test    rax, rax
0x18003f3fe  jnz     short loc_18003F40A
0x18003f400  mov     eax, 8007000Eh
0x18003f405  jmp     loc_18003F4EA
0x18003f40a  mov     r8, [rbx+50h]; HWND
0x18003f40e  mov     r9d, 419h; unsigned int
0x18003f414  mov     [rsp+80h+var_50], 0; __int64 *
0x18003f41d  xor     edx, edx; bool
0x18003f41f  mov     [rsp+80h+var_58], r14; __int64
0x18003f424  mov     rcx, rbx; this
0x18003f427  mov     [rsp+80h+lpNumberOfBytesRead], 0; unsigned __int64
0x18003f430  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18003f435  mov     r15, [rbp+hProcess]
0x18003f439  mov     esi, eax
0x18003f43b  test    eax, eax
0x18003f43d  js      loc_18003F4DD
0x18003f443  mov     r9, r12; nSize
0x18003f446  mov     [rsp+80h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18003f44f  lea     r8, [rbp+Buffer]; lpBuffer
0x18003f453  mov     rdx, r14; lpBaseAddress
0x18003f456  mov     rcx, r15; hProcess
0x18003f459  call    cs:__imp_ReadProcessMemory
0x18003f45f  mov     rdx, qword ptr [rbp+Point.x]; pt
0x18003f463  lea     rcx, [rbp+Buffer]; lprc
0x18003f467  call    cs:__imp_PtInRect
0x18003f46d  test    eax, eax
0x18003f46f  jz      short loc_18003F47D
0x18003f471  mov     dword ptr [rdi+8], 2
0x18003f478  jmp     loc_18003F5C4
0x18003f47d  mov     rdx, [rbx+50h]; HWND
0x18003f481  lea     r8, [rbp+var_38]; void **
0x18003f485  mov     ecx, r12d; dwSize
0x18003f488  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18003f48d  mov     rsi, rax
0x18003f490  test    rax, rax
0x18003f493  jnz     short loc_18003F49C
0x18003f495  mov     esi, 8007000Eh
0x18003f49a  jmp     short loc_18003F4DD
0x18003f49c  mov     r8, [rbx+50h]; HWND
0x18003f4a0  mov     r9d, 41Ah; unsigned int
0x18003f4a6  mov     [rsp+80h+var_50], 0; __int64 *
0x18003f4af  xor     edx, edx; bool
0x18003f4b1  mov     [rsp+80h+var_58], rsi; __int64
0x18003f4b6  mov     rcx, rbx; this
0x18003f4b9  mov     [rsp+80h+lpNumberOfBytesRead], 0; unsigned __int64
0x18003f4c2  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18003f4c7  mov     r12d, eax
0x18003f4ca  test    eax, eax
0x18003f4cc  jns     short loc_18003F508
0x18003f4ce  mov     rdx, [rbp+var_38]; hProcess
0x18003f4d2  mov     rcx, rsi; lpAddress
0x18003f4d5  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18003f4da  mov     esi, r12d
0x18003f4dd  mov     rdx, r15; hProcess
0x18003f4e0  mov     rcx, r14; lpAddress
0x18003f4e3  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18003f4e8  mov     eax, esi
0x18003f4ea  mov     rcx, [rbp+var_8]
0x18003f4ee  xor     rcx, rsp; StackCookie
0x18003f4f1  call    __security_check_cookie
0x18003f4f6  add     rsp, 80h
0x18003f4fd  pop     r15
0x18003f4ff  pop     r14
0x18003f501  pop     r12
0x18003f503  pop     rdi
0x18003f504  pop     rsi
0x18003f505  pop     rbx
0x18003f506  pop     rbp
0x18003f507  retn
0x18003f508  mov     rcx, [rbp+var_38]; hProcess
0x18003f50c  lea     r8, [rbp+var_28]; lpBuffer
0x18003f510  mov     r9d, 10h; nSize
0x18003f516  mov     [rsp+80h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18003f51f  mov     rdx, rsi; lpBaseAddress
0x18003f522  call    cs:__imp_ReadProcessMemory
0x18003f528  mov     edx, [rbx+90h]
0x18003f52e  test    edx, edx
0x18003f530  jz      short loc_18003F54A
0x18003f532  mov     ecx, dword ptr [rbp+var_28]
0x18003f535  mov     eax, dword ptr [rbp+var_28+4]
0x18003f538  mov     dword ptr [rbp+var_28], eax
0x18003f53b  mov     eax, dword ptr [rbp+var_28+0Ch]
0x18003f53e  mov     dword ptr [rbp+var_28+4], ecx
0x18003f541  mov     ecx, dword ptr [rbp+var_28+8]
0x18003f544  mov     dword ptr [rbp+var_28+8], eax
0x18003f547  mov     dword ptr [rbp+var_28+0Ch], ecx
0x18003f54a  mov     eax, edx
0x18003f54c  neg     eax
0x18003f54e  sbb     rcx, rcx
0x18003f551  not     rcx
0x18003f554  and     ecx, 4
0x18003f557  mov     r8d, [rbp+rcx+Point.x]
0x18003f55c  cmp     r8d, dword ptr [rbp+rcx+var_28]
0x18003f561  jl      short loc_18003F5B8
0x18003f563  mov     eax, edx
0x18003f565  neg     eax
0x18003f567  sbb     rcx, rcx
0x18003f56a  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18003f56e  cmp     r8d, dword ptr [rbp+rcx+var_28+0Ch]
0x18003f573  jge     short loc_18003F5B8
0x18003f575  mov     eax, edx
0x18003f577  neg     eax
0x18003f579  sbb     rcx, rcx
0x18003f57c  and     ecx, 4
0x18003f57f  mov     r8d, [rbp+rcx+Point.x]
0x18003f584  cmp     r8d, dword ptr [rbp+rcx+var_28]
0x18003f589  jl      short loc_18003F59B
0x18003f58b  cmp     r8d, dword ptr [rbp+rcx+Buffer]
0x18003f590  jge     short loc_18003F59B
0x18003f592  mov     dword ptr [rdi+8], 1
0x18003f599  jmp     short loc_18003F5B8
0x18003f59b  neg     edx
0x18003f59d  sbb     rax, rax
0x18003f5a0  and     eax, 4
0x18003f5a3  cmp     r8d, dword ptr [rbp+rax+Buffer+8]
0x18003f5a8  jl      short loc_18003F5B8
0x18003f5aa  cmp     r8d, dword ptr [rbp+rax+var_28+8]
0x18003f5af  jge     short loc_18003F5B8
0x18003f5b1  mov     dword ptr [rdi+8], 3
0x18003f5b8  mov     rdx, [rbp+var_38]; hProcess
0x18003f5bc  mov     rcx, rsi; lpAddress
0x18003f5bf  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18003f5c4  mov     rdx, r15; hProcess
0x18003f5c7  mov     rcx, r14; lpAddress
0x18003f5ca  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18003f5cf  xor     eax, eax
0x18003f5d1  jmp     loc_18003F4EA
```
