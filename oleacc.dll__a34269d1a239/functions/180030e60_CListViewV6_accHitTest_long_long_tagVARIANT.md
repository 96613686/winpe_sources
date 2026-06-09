# CListViewV6::accHitTest(long,long,tagVARIANT *)

- ea: `0x180030e60`
- end: `0x180030fe1`
- name: `?accHitTest@CListViewV6@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(CListViewV6 *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x1800191c0`
- `0x180030e60`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180030f22`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180030f22`
- `OLEAUT32!__imp_VariantClear` at `0x180030eb2`
- `OLEAUT32!__imp_VariantClear` at `0x180030eb2`
- `USER32!ScreenToClient` at `0x180030eff`
- `USER32!ScreenToClient` at `0x180030eff`

## pseudocode

```c
__int64 __fastcall CListViewV6::accHitTest(HWND *this, int a2, int a3, struct tagVARIANT *a4)
{
  int v8; // edi
  HWND v9; // rdx
  void *v10; // r14
  HWND v11; // rcx
  HANDLE v12; // r15
  HWND v13; // r8
  HWND v14; // rax
  __int128 v15; // xmm0
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int (__fastcall *v17)(HWND *, __int128 *, HANDLE *); // rax
  unsigned __int64 lpNumberOfBytesWritten; // [rsp+20h] [rbp-50h]
  HANDLE hProcess[2]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v21; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *v22; // [rsp+60h] [rbp-10h]
  struct tagPOINT Point; // [rsp+B8h] [rbp+48h] BYREF

  a4->vt = 0;
  v8 = CClient::accHitTest((CClient *)this, a2, a3, a4);
  if ( !v8 && a4->vt == 3 && !a4->lVal )
  {
    VariantClear(a4);
    v9 = this[10];
    hProcess[0] = 0;
    v8 = -2147024882;
    v10 = SharedAlloc(8u, v9, hProcess);
    if ( v10 )
    {
      a4->vt = 3;
      a4->lVal = 0;
      v11 = this[10];
      Point.x = a2;
      Point.y = a3;
      ScreenToClient(v11, &Point);
      v12 = hProcess[0];
      WriteProcessMemory(hProcess[0], v10, &Point, 8u, 0);
      v13 = this[10];
      lpNumberOfBytesWritten = *((int *)this + 34);
      hProcess[0] = 0;
      v8 = CAccessible::AccSendMessageTimeout(
             (CAccessible *)this,
             0,
             v13,
             0x10C6u,
             lpNumberOfBytesWritten,
             (__int64)v10,
             (__int64 *)hProcess);
      if ( v8 >= 0 && LODWORD(hProcess[0]) != -1 && LODWORD(hProcess[0]) != *((_DWORD *)this + 34) )
      {
        a4->lVal = (LONG)hProcess[0];
        a4->vt = 3;
        v14 = *this;
        v8 = 0;
        v15 = *(_OWORD *)&a4->vt;
        hProcess[0] = 0;
        pRecInfo = a4->pRecInfo;
        v17 = (unsigned int (__fastcall *)(HWND *, __int128 *, HANDLE *))*((_QWORD *)v14 + 9);
        v21 = v15;
        v22 = pRecInfo;
        if ( !v17(this, &v21, hProcess) )
        {
          a4->byref = hProcess[0];
          a4->vt = 9;
        }
      }
      SharedFree(v10, v12);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180030e60  mov     [rsp-28h+arg_0], rbx
0x180030e65  mov     [rsp-28h+arg_8], rsi
0x180030e6a  push    rbp
0x180030e6b  push    rdi
0x180030e6c  push    r12
0x180030e6e  push    r14
0x180030e70  push    r15
0x180030e72  mov     rbp, rsp
0x180030e75  sub     rsp, 70h
0x180030e79  xor     eax, eax
0x180030e7b  mov     rbx, r9
0x180030e7e  mov     [r9], ax
0x180030e82  mov     r15d, r8d
0x180030e85  mov     r12d, edx
0x180030e88  mov     rsi, rcx
0x180030e8b  call    ?accHitTest@CClient@@UEAAJJJPEAUtagVARIANT@@@Z; CClient::accHitTest(long,long,tagVARIANT *)
0x180030e90  mov     edi, eax
0x180030e92  test    eax, eax
0x180030e94  jnz     loc_180030FC6
0x180030e9a  lea     eax, [rdi+3]
0x180030e9d  cmp     [rbx], ax
0x180030ea0  jnz     loc_180030FC6
0x180030ea6  cmp     [rbx+8], edi
0x180030ea9  jnz     loc_180030FC6
0x180030eaf  mov     rcx, rbx; pvarg
0x180030eb2  call    cs:__imp_VariantClear
0x180030eb8  mov     rdx, [rsi+50h]; HWND
0x180030ebc  lea     r8, [rbp+hProcess]; void **
0x180030ec0  mov     ecx, 8; dwSize
0x180030ec5  mov     [rbp+hProcess], 0
0x180030ecd  mov     edi, 8007000Eh
0x180030ed2  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180030ed7  mov     r14, rax
0x180030eda  test    rax, rax
0x180030edd  jz      loc_180030FC6
0x180030ee3  mov     word ptr [rbx], 3
0x180030ee8  lea     rdx, [rbp+Point]; lpPoint
0x180030eec  mov     dword ptr [rbx+8], 0
0x180030ef3  mov     rcx, [rsi+50h]; hWnd
0x180030ef7  mov     [rbp+Point.x], r12d
0x180030efb  mov     [rbp+Point.y], r15d
0x180030eff  call    cs:__imp_ScreenToClient
0x180030f05  mov     r15, [rbp+hProcess]
0x180030f09  lea     r8, [rbp+Point]; lpBuffer
0x180030f0d  mov     rcx, r15; hProcess
0x180030f10  mov     [rsp+70h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180030f19  mov     r9d, 8; nSize
0x180030f1f  mov     rdx, r14; lpBaseAddress
0x180030f22  call    cs:__imp_WriteProcessMemory
0x180030f28  movsxd  rax, dword ptr [rsi+88h]
0x180030f2f  lea     rcx, [rbp+hProcess]
0x180030f33  mov     r8, [rsi+50h]; HWND
0x180030f37  mov     r9d, 10C6h; unsigned int
0x180030f3d  mov     [rsp+70h+var_40], rcx; __int64 *
0x180030f42  xor     edx, edx; bool
0x180030f44  mov     [rsp+70h+var_48], r14; __int64
0x180030f49  mov     rcx, rsi; this
0x180030f4c  mov     [rsp+70h+lpNumberOfBytesWritten], rax; unsigned __int64
0x180030f51  mov     [rbp+hProcess], 0
0x180030f59  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180030f5e  mov     edi, eax
0x180030f60  test    eax, eax
0x180030f62  js      short loc_180030FBB
0x180030f64  mov     eax, dword ptr [rbp+hProcess]
0x180030f67  cmp     eax, 0FFFFFFFFh
0x180030f6a  jz      short loc_180030FBB
0x180030f6c  cmp     eax, [rsi+88h]
0x180030f72  jz      short loc_180030FBB
0x180030f74  mov     [rbx+8], eax
0x180030f77  lea     r8, [rbp+hProcess]
0x180030f7b  mov     word ptr [rbx], 3
0x180030f80  lea     rdx, [rbp+var_20]
0x180030f84  mov     rax, [rsi]
0x180030f87  xor     edi, edi
0x180030f89  movups  xmm0, xmmword ptr [rbx]
0x180030f8c  mov     rcx, rsi
0x180030f8f  mov     [rbp+hProcess], rdi
0x180030f93  movsd   xmm1, qword ptr [rbx+10h]
0x180030f98  mov     rax, [rax+48h]
0x180030f9c  movaps  [rbp+var_20], xmm0
0x180030fa0  movsd   [rbp+var_10], xmm1
0x180030fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030faa  test    eax, eax
0x180030fac  jnz     short loc_180030FBB
0x180030fae  mov     rax, [rbp+hProcess]
0x180030fb2  mov     [rbx+8], rax
0x180030fb6  mov     word ptr [rbx], 9
0x180030fbb  mov     rdx, r15; hProcess
0x180030fbe  mov     rcx, r14; lpAddress
0x180030fc1  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180030fc6  lea     r11, [rsp+70h+var_s0]
0x180030fcb  mov     eax, edi
0x180030fcd  mov     rbx, [r11+30h]
0x180030fd1  mov     rsi, [r11+38h]
0x180030fd5  mov     rsp, r11
0x180030fd8  pop     r15
0x180030fda  pop     r14
0x180030fdc  pop     r12
0x180030fde  pop     rdi
0x180030fdf  pop     rbp
0x180030fe0  retn
```
