# CSlider32::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x18003f5e0`
- end: `0x18003f8d7`
- name: `?accLocation@CSlider32@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `759`
- prototype: `__int64 __fastcall(CSlider32 *__hidden this, int *, int *, int *, int *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18001c430`
- `0x18001e4c0`
- `0x18003f5e0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003f735`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003f7fe`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003f735`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003f7fe`
- `USER32!GetWindowLongW` at `0x18003f6ac`
- `USER32!GetWindowLongW` at `0x18003f6ac`
- `USER32!MapWindowPoints` at `0x18003f752`
- `USER32!MapWindowPoints` at `0x18003f86f`
- `USER32!MapWindowPoints` at `0x18003f752`
- `USER32!MapWindowPoints` at `0x18003f86f`

## pseudocode

```c
__int64 __fastcall CSlider32::accLocation(HWND *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  HWND v8; // rax
  unsigned int (__fastcall *v11)(HWND *, struct tagVARIANT *); // rax
  IRecordInfo *pRecInfo; // xmm1_8
  LPVOID v14; // rax
  void *v15; // r14
  int v16; // edi
  int v17; // edx
  int v18; // eax
  int *v19; // rcx
  LPVOID v20; // rax
  void *v21; // rdi
  int v22; // r15d
  int v23; // r9d
  LONG x; // ecx
  LONG v25; // ecx
  int v26; // r8d
  LONG y; // r8d
  HANDLE v28; // rdx
  int v29; // eax
  int *v30; // rcx
  HANDLE v31; // [rsp+40h] [rbp-69h] BYREF
  HANDLE hProcess; // [rsp+48h] [rbp-61h] BYREF
  int *v33; // [rsp+50h] [rbp-59h]
  int *v34; // [rsp+58h] [rbp-51h]
  struct tagVARIANT v35; // [rsp+60h] [rbp-49h] BYREF
  struct tagPOINT Points[2]; // [rsp+80h] [rbp-29h] BYREF
  __int128 Buffer; // [rsp+90h] [rbp-19h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v8 = *this;
  v34 = a4;
  v33 = a5;
  hProcess = 0;
  v11 = (unsigned int (__fastcall *)(HWND *, struct tagVARIANT *))*((_QWORD *)v8 + 30);
  v31 = 0;
  *(_OWORD *)&Points[0].x = 0;
  Buffer = 0;
  if ( !v11(this, a6) )
    return 2147942487LL;
  if ( !a6->lVal )
  {
    pRecInfo = a6->pRecInfo;
    *(_OWORD *)&v35.vt = *(_OWORD *)&a6->vt;
    v35.pRecInfo = pRecInfo;
    return CClient::accLocation((CClient *)this, a2, a3, a4, a5, &v35);
  }
  if ( (GetWindowLongW(this[10], -16) & 0x80u) != 0 )
    return 1;
  v14 = SharedAlloc(0x10u, this[10], &hProcess);
  v15 = v14;
  if ( !v14 )
    return 2147942414LL;
  v16 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, this[10], 0x419u, 0, (__int64)v14, 0);
  if ( v16 >= 0 )
  {
    ReadProcessMemory(hProcess, v15, &Buffer, 0x10u, 0);
    if ( a6->lVal == 2 )
    {
      MapWindowPoints(this[10], 0, (LPPOINT)&Buffer, 2u);
      v17 = DWORD1(Buffer);
      v18 = DWORD2(Buffer) - Buffer;
      *a2 = Buffer;
      v19 = v33;
      *a3 = v17;
      *a4 = v18;
      *v19 = HIDWORD(Buffer) - v17;
LABEL_21:
      v16 = 0;
      goto LABEL_22;
    }
    v20 = SharedAlloc(0x10u, this[10], &v31);
    v21 = v20;
    if ( v20 )
    {
      v22 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, this[10], 0x41Au, 0, (__int64)v20, 0);
      if ( v22 >= 0 )
      {
        ReadProcessMemory(v31, v21, Points, 0x10u, 0);
        v23 = *((_DWORD *)this + 36);
        if ( v23 )
        {
          x = Points[0].x;
          Points[0].x = Points[0].y;
          Points[0].y = x;
          v25 = Points[1].x;
          Points[1].x = Points[1].y;
          Points[1].y = v25;
        }
        v26 = 1;
        if ( a6->lVal != 1 )
          v26 = 0;
        *(&Points[v26].x + (v23 != 0)) = *((_DWORD *)&Buffer + (((_BYTE)(v26 * 2) + (v23 != 0) + 2) & 3));
        MapWindowPoints(this[10], 0, Points, 2u);
        y = Points[0].y;
        v28 = v31;
        v29 = Points[1].x - Points[0].x;
        *a2 = Points[0].x;
        v30 = v34;
        *a3 = y;
        *v30 = v29;
        *v33 = Points[1].y - y;
        SharedFree(v21, v28);
        goto LABEL_21;
      }
      SharedFree(v21, v31);
      v16 = v22;
    }
    else
    {
      v16 = -2147024882;
    }
  }
LABEL_22:
  SharedFree(v15, hProcess);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18003f5e0  push    rbp
0x18003f5e2  push    rbx
0x18003f5e3  push    rsi
0x18003f5e4  push    rdi
0x18003f5e5  push    r12
0x18003f5e7  push    r13
0x18003f5e9  push    r14
0x18003f5eb  push    r15
0x18003f5ed  lea     rbp, [rsp-0Fh]
0x18003f5f2  sub     rsp, 0B8h
0x18003f5f9  mov     rax, cs:__security_cookie
0x18003f600  xor     rax, rsp
0x18003f603  mov     [rbp+47h+var_50], rax
0x18003f607  mov     rdi, [rbp+47h+arg_20]
0x18003f60b  xor     r14d, r14d
0x18003f60e  mov     rsi, [rbp+47h+arg_28]
0x18003f612  mov     r12, rdx
0x18003f615  mov     [rdx], r14d
0x18003f618  xorps   xmm0, xmm0
0x18003f61b  mov     [r8], r14d
0x18003f61e  xorps   xmm1, xmm1
0x18003f621  mov     [r9], r14d
0x18003f624  mov     rdx, rsi
0x18003f627  mov     [rdi], r14d
0x18003f62a  mov     r15, r9
0x18003f62d  mov     rax, [rcx]
0x18003f630  mov     r13, r8
0x18003f633  mov     [rbp+47h+var_98], r9
0x18003f637  mov     rbx, rcx
0x18003f63a  mov     [rbp+47h+var_A0], rdi
0x18003f63e  mov     [rbp+47h+hProcess], r14
0x18003f642  mov     rax, [rax+0F0h]
0x18003f649  mov     [rbp+47h+var_B0], r14
0x18003f64d  movups  xmmword ptr [rbp+47h+Points.x], xmm0
0x18003f651  movups  [rbp+47h+Buffer], xmm1
0x18003f655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f65a  test    eax, eax
0x18003f65c  jnz     short loc_18003F668
0x18003f65e  mov     eax, 80070057h
0x18003f663  jmp     loc_18003F8B7
0x18003f668  cmp     [rsi+8], r14d
0x18003f66c  jnz     short loc_18003F6A3
0x18003f66e  movups  xmm0, xmmword ptr [rsi]
0x18003f671  lea     rax, [rbp+47h+var_90]
0x18003f675  mov     r9, r15; int *
0x18003f678  movsd   xmm1, qword ptr [rsi+10h]
0x18003f67d  mov     r8, r13; int *
0x18003f680  mov     [rsp+0F0h+var_C8], rax; struct tagVARIANT *
0x18003f685  mov     rdx, r12; int *
0x18003f688  mov     rcx, rbx; this
0x18003f68b  movaps  xmmword ptr [rbp+47h+var_90], xmm0
0x18003f68f  movsd   qword ptr [rbp+47h+var_90+10h], xmm1
0x18003f694  mov     [rsp+0F0h+lpNumberOfBytesRead], rdi; int *
0x18003f699  call    ?accLocation@CClient@@UEAAJPEAJ000UtagVARIANT@@@Z; CClient::accLocation(long *,long *,long *,long *,tagVARIANT)
0x18003f69e  jmp     loc_18003F8B7
0x18003f6a3  mov     rcx, [rbx+50h]; hWnd
0x18003f6a7  mov     edx, 0FFFFFFF0h; nIndex
0x18003f6ac  call    cs:__imp_GetWindowLongW
0x18003f6b2  test    al, al
0x18003f6b4  jns     short loc_18003F6C0
0x18003f6b6  mov     eax, 1
0x18003f6bb  jmp     loc_18003F8B7
0x18003f6c0  mov     rdx, [rbx+50h]; HWND
0x18003f6c4  lea     r8, [rbp+47h+hProcess]; void **
0x18003f6c8  mov     ecx, 10h; dwSize
0x18003f6cd  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18003f6d2  mov     r14, rax
0x18003f6d5  test    rax, rax
0x18003f6d8  jnz     short loc_18003F6E4
0x18003f6da  mov     eax, 8007000Eh
0x18003f6df  jmp     loc_18003F8B7
0x18003f6e4  mov     r8, [rbx+50h]; HWND
0x18003f6e8  mov     r9d, 419h; unsigned int
0x18003f6ee  mov     [rsp+0F0h+var_C0], 0; __int64 *
0x18003f6f7  xor     edx, edx; bool
0x18003f6f9  mov     [rsp+0F0h+var_C8], r14; __int64
0x18003f6fe  mov     rcx, rbx; this
0x18003f701  mov     [rsp+0F0h+lpNumberOfBytesRead], 0; unsigned __int64
0x18003f70a  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18003f70f  mov     edi, eax
0x18003f711  test    eax, eax
0x18003f713  js      loc_18003F8A9
0x18003f719  mov     rcx, [rbp+47h+hProcess]; hProcess
0x18003f71d  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x18003f721  mov     edi, 10h
0x18003f726  mov     [rsp+0F0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18003f72f  mov     r9d, edi; nSize
0x18003f732  mov     rdx, r14; lpBaseAddress
0x18003f735  call    cs:__imp_ReadProcessMemory
0x18003f73b  cmp     dword ptr [rsi+8], 2
0x18003f73f  mov     rax, [rbx+50h]
0x18003f743  jnz     short loc_18003F77E
0x18003f745  lea     r9d, [rdi-0Eh]; cPoints
0x18003f749  xor     edx, edx; hWndTo
0x18003f74b  lea     r8, [rbp+47h+Buffer]; lpPoints
0x18003f74f  mov     rcx, rax; hWndFrom
0x18003f752  call    cs:__imp_MapWindowPoints
0x18003f758  mov     ecx, dword ptr [rbp+47h+Buffer]
0x18003f75b  mov     edx, dword ptr [rbp+47h+Buffer+4]
0x18003f75e  mov     eax, dword ptr [rbp+47h+Buffer+8]
0x18003f761  sub     eax, ecx
0x18003f763  mov     [r12], ecx
0x18003f767  mov     rcx, [rbp+47h+var_A0]
0x18003f76b  mov     [r13+0], edx
0x18003f76f  mov     [r15], eax
0x18003f772  mov     eax, dword ptr [rbp+47h+Buffer+0Ch]
0x18003f775  sub     eax, edx
0x18003f777  mov     [rcx], eax
0x18003f779  jmp     loc_18003F8A7
0x18003f77e  lea     r8, [rbp+47h+var_B0]; void **
0x18003f782  mov     rdx, rax; HWND
0x18003f785  mov     ecx, edi; dwSize
0x18003f787  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18003f78c  mov     rdi, rax
0x18003f78f  test    rax, rax
0x18003f792  jnz     short loc_18003F79E
0x18003f794  mov     edi, 8007000Eh
0x18003f799  jmp     loc_18003F8A9
0x18003f79e  mov     r8, [rbx+50h]; HWND
0x18003f7a2  mov     r9d, 41Ah; unsigned int
0x18003f7a8  mov     [rsp+0F0h+var_C0], 0; __int64 *
0x18003f7b1  xor     edx, edx; bool
0x18003f7b3  mov     [rsp+0F0h+var_C8], rdi; __int64
0x18003f7b8  mov     rcx, rbx; this
0x18003f7bb  mov     [rsp+0F0h+lpNumberOfBytesRead], 0; unsigned __int64
0x18003f7c4  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18003f7c9  mov     r15d, eax
0x18003f7cc  test    eax, eax
0x18003f7ce  jns     short loc_18003F7E4
0x18003f7d0  mov     rdx, [rbp+47h+var_B0]; hProcess
0x18003f7d4  mov     rcx, rdi; lpAddress
0x18003f7d7  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18003f7dc  mov     edi, r15d
0x18003f7df  jmp     loc_18003F8A9
0x18003f7e4  mov     rcx, [rbp+47h+var_B0]; hProcess
0x18003f7e8  lea     r8, [rbp+47h+Points]; lpBuffer
0x18003f7ec  mov     r9d, 10h; nSize
0x18003f7f2  mov     [rsp+0F0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18003f7fb  mov     rdx, rdi; lpBaseAddress
0x18003f7fe  call    cs:__imp_ReadProcessMemory
0x18003f804  mov     r9d, [rbx+90h]
0x18003f80b  test    r9d, r9d
0x18003f80e  jz      short loc_18003F828
0x18003f810  mov     ecx, [rbp+47h+Points.x]
0x18003f813  mov     eax, [rbp+47h+Points.y]
0x18003f816  mov     [rbp+47h+Points.x], eax
0x18003f819  mov     eax, [rbp+47h+Points.y+8]
0x18003f81c  mov     [rbp+47h+Points.y], ecx
0x18003f81f  mov     ecx, [rbp+47h+Points.x+8]
0x18003f822  mov     [rbp+47h+Points.x+8], eax
0x18003f825  mov     [rbp+47h+Points.y+8], ecx
0x18003f828  xor     eax, eax
0x18003f82a  mov     r10d, 2
0x18003f830  cmp     dword ptr [rsi+8], 1
0x18003f834  mov     r8d, r10d
0x18003f837  cmovnz  r8d, eax
0x18003f83b  mov     eax, r9d
0x18003f83e  neg     eax
0x18003f840  sbb     ecx, ecx
0x18003f842  xor     eax, eax
0x18003f844  neg     ecx
0x18003f846  lea     edx, [r10+rcx]
0x18003f84a  add     edx, r8d
0x18003f84d  and     edx, 3
0x18003f850  test    r9d, r9d
0x18003f853  mov     r9d, r10d; cPoints
0x18003f856  setnz   al
0x18003f859  lea     ecx, [r8+rax]
0x18003f85d  mov     eax, dword ptr [rbp+rdx*4+47h+Buffer]
0x18003f861  mov     [rbp+rcx*4+47h+Points.x], eax
0x18003f865  lea     r8, [rbp+47h+Points]; lpPoints
0x18003f869  mov     rcx, [rbx+50h]; hWndFrom
0x18003f86d  xor     edx, edx; hWndTo
0x18003f86f  call    cs:__imp_MapWindowPoints
0x18003f875  mov     ecx, [rbp+47h+Points.x]
0x18003f878  mov     r8d, [rbp+47h+Points.y]
0x18003f87c  mov     eax, [rbp+47h+Points.x+8]
0x18003f87f  mov     rdx, [rbp+47h+var_B0]; hProcess
0x18003f883  sub     eax, ecx
0x18003f885  mov     [r12], ecx
0x18003f889  mov     rcx, [rbp+47h+var_98]
0x18003f88d  mov     [r13+0], r8d
0x18003f891  mov     [rcx], eax
0x18003f893  mov     rcx, [rbp+47h+var_A0]
0x18003f897  mov     eax, [rbp+47h+Points.y+8]
0x18003f89a  sub     eax, r8d
0x18003f89d  mov     [rcx], eax
0x18003f89f  mov     rcx, rdi; lpAddress
0x18003f8a2  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18003f8a7  xor     edi, edi
0x18003f8a9  mov     rdx, [rbp+47h+hProcess]; hProcess
0x18003f8ad  mov     rcx, r14; lpAddress
0x18003f8b0  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18003f8b5  mov     eax, edi
0x18003f8b7  mov     rcx, [rbp+47h+var_50]
0x18003f8bb  xor     rcx, rsp; StackCookie
0x18003f8be  call    __security_check_cookie
0x18003f8c3  add     rsp, 0B8h
0x18003f8ca  pop     r15
0x18003f8cc  pop     r14
0x18003f8ce  pop     r13
0x18003f8d0  pop     r12
0x18003f8d2  pop     rdi
0x18003f8d3  pop     rsi
0x18003f8d4  pop     rbx
0x18003f8d5  pop     rbp
0x18003f8d6  retn
```
