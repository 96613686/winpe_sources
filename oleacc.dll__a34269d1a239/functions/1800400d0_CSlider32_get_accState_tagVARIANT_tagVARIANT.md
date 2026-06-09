# CSlider32::get_accState(tagVARIANT,tagVARIANT *)

- ea: `0x1800400d0`
- end: `0x180040303`
- name: `?get_accState@CSlider32@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `563`
- prototype: `__int64 __fastcall(CSlider32 *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800056a4`
- `0x180005ca0`
- `0x180006c58`
- `0x18000771c`
- `0x18001e4c0`
- `0x1800400d0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180040210`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180040295`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180040210`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180040295`
- `USER32!GetWindowLongW` at `0x180040177`
- `USER32!GetWindowLongW` at `0x180040177`

## pseudocode

```c
__int64 __fastcall CSlider32::get_accState(HWND *this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  HWND v3; // rax
  unsigned int (__fastcall *v7)(HWND *); // rax
  IRecordInfo *pRecInfo; // xmm1_8
  LPVOID v10; // rax
  void *v11; // rsi
  int v12; // r15d
  LPVOID v13; // rax
  void *v14; // r15
  int v15; // r13d
  __int64 v16; // rcx
  __int64 v17; // r8
  HANDLE hProcess; // [rsp+40h] [rbp-39h] BYREF
  HANDLE v19; // [rsp+48h] [rbp-31h] BYREF
  struct tagVARIANT v20; // [rsp+50h] [rbp-29h] BYREF
  __int128 v21; // [rsp+70h] [rbp-9h] BYREF
  __int128 Buffer; // [rsp+80h] [rbp+7h] BYREF

  a3->vt = 0;
  v3 = *this;
  hProcess = 0;
  v19 = 0;
  Buffer = 0;
  v7 = (unsigned int (__fastcall *)(HWND *))*((_QWORD *)v3 + 30);
  v21 = 0;
  if ( !v7(this) )
    return 2147942487LL;
  if ( !a2->lVal )
  {
    pRecInfo = a2->pRecInfo;
    *(_OWORD *)&v20.vt = *(_OWORD *)&a2->vt;
    v20.pRecInfo = pRecInfo;
    return CClient::get_accState((CClient *)this, &v20, a3);
  }
  a3->vt = 3;
  a3->lVal = 0;
  if ( (GetWindowLongW(this[10], -16) & 0x80u) == 0 )
  {
    if ( a2->lVal != 2 )
    {
      v10 = SharedAlloc(0x10u, this[10], &hProcess);
      v11 = v10;
      if ( !v10 )
        return 2147942414LL;
      v12 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, this[10], 0x41Au, 0, (__int64)v10, 0);
      if ( v12 < 0 )
      {
        SharedFree(v11, hProcess);
        return (unsigned int)v12;
      }
      ReadProcessMemory(hProcess, v11, &Buffer, 0x10u, 0);
      v13 = SharedAlloc(0x10u, this[10], &v19);
      v14 = v13;
      if ( v13 )
      {
        v15 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, this[10], 0x419u, 0, (__int64)v13, 0);
        if ( v15 < 0 )
        {
          SharedFree(v14, v19);
          SharedFree(v11, hProcess);
          return (unsigned int)v15;
        }
        ReadProcessMemory(v19, v14, &v21, 0x10u, 0);
        v16 = 8;
        if ( a2->lVal != 3 )
          v16 = 0;
        v17 = *((_DWORD *)this + 36) != 0 ? 4 : 0;
        if ( *(_DWORD *)((char *)&Buffer + v17 + v16) == *(_DWORD *)((char *)&v21 + v17 + v16) )
          a3->lVal |= 0x8000u;
        SharedFree(v14, v19);
      }
      SharedFree(v11, hProcess);
    }
  }
  else
  {
    a3->lVal |= 0x8001u;
  }
  return 0;
}

```

## disassembly

```asm
0x1800400d0  push    rbp
0x1800400d2  push    rbx
0x1800400d3  push    rsi
0x1800400d4  push    rdi
0x1800400d5  push    r13
0x1800400d7  push    r14
0x1800400d9  push    r15
0x1800400db  lea     rbp, [rsp-27h]
0x1800400e0  sub     rsp, 0A0h
0x1800400e7  mov     rax, cs:__security_cookie
0x1800400ee  xor     rax, rsp
0x1800400f1  mov     [rbp+57h+var_40], rax
0x1800400f5  xor     r13d, r13d
0x1800400f8  xorps   xmm0, xmm0
0x1800400fb  mov     [r8], r13w
0x1800400ff  xorps   xmm1, xmm1
0x180040102  mov     rax, [rcx]
0x180040105  mov     rbx, r8
0x180040108  mov     r14, rdx
0x18004010b  mov     [rbp+57h+hProcess], r13
0x18004010f  mov     rdi, rcx
0x180040112  mov     [rbp+57h+var_88], r13
0x180040116  movups  [rbp+57h+Buffer], xmm0
0x18004011a  mov     rax, [rax+0F0h]
0x180040121  movups  [rbp+57h+var_60], xmm1
0x180040125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004012a  test    eax, eax
0x18004012c  jnz     short loc_180040138
0x18004012e  mov     eax, 80070057h
0x180040133  jmp     loc_1800402E5
0x180040138  cmp     [r14+8], r13d
0x18004013c  jnz     short loc_180040165
0x18004013e  movups  xmm0, xmmword ptr [r14]
0x180040142  lea     rdx, [rbp+57h+var_80]; struct tagVARIANT
0x180040146  mov     r8, rbx; struct tagVARIANT *
0x180040149  movsd   xmm1, qword ptr [r14+10h]
0x18004014f  mov     rcx, rdi; this
0x180040152  movaps  xmmword ptr [rbp+57h+var_80], xmm0
0x180040156  movsd   qword ptr [rbp+57h+var_80+10h], xmm1
0x18004015b  call    ?get_accState@CClient@@UEAAJUtagVARIANT@@PEAU2@@Z; CClient::get_accState(tagVARIANT,tagVARIANT *)
0x180040160  jmp     loc_1800402E5
0x180040165  mov     word ptr [rbx], 3
0x18004016a  mov     edx, 0FFFFFFF0h; nIndex
0x18004016f  mov     [rbx+8], r13d
0x180040173  mov     rcx, [rdi+50h]; hWnd
0x180040177  call    cs:__imp_GetWindowLongW
0x18004017d  test    al, al
0x18004017f  jns     short loc_18004018D
0x180040181  or      dword ptr [rbx+8], 8001h
0x180040188  jmp     loc_1800402E3
0x18004018d  cmp     dword ptr [r14+8], 2
0x180040192  jz      loc_1800402E3
0x180040198  mov     rdx, [rdi+50h]; HWND
0x18004019c  lea     r8, [rbp+57h+hProcess]; void **
0x1800401a0  mov     ecx, 10h; dwSize
0x1800401a5  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x1800401aa  mov     rsi, rax
0x1800401ad  test    rax, rax
0x1800401b0  jnz     short loc_1800401BC
0x1800401b2  mov     eax, 8007000Eh
0x1800401b7  jmp     loc_1800402E5
0x1800401bc  mov     r8, [rdi+50h]; HWND
0x1800401c0  mov     r9d, 41Ah; unsigned int
0x1800401c6  mov     [rsp+0D0h+var_A0], r13; __int64 *
0x1800401cb  xor     edx, edx; bool
0x1800401cd  mov     [rsp+0D0h+var_A8], rsi; __int64
0x1800401d2  mov     rcx, rdi; this
0x1800401d5  mov     [rsp+0D0h+lpNumberOfBytesRead], r13; unsigned __int64
0x1800401da  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x1800401df  mov     r15d, eax
0x1800401e2  test    eax, eax
0x1800401e4  jns     short loc_1800401FA
0x1800401e6  mov     rdx, [rbp+57h+hProcess]; hProcess
0x1800401ea  mov     rcx, rsi; lpAddress
0x1800401ed  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800401f2  mov     eax, r15d
0x1800401f5  jmp     loc_1800402E5
0x1800401fa  mov     rcx, [rbp+57h+hProcess]; hProcess
0x1800401fe  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180040202  mov     r9d, 10h; nSize
0x180040208  mov     [rsp+0D0h+lpNumberOfBytesRead], r13; lpNumberOfBytesRead
0x18004020d  mov     rdx, rsi; lpBaseAddress
0x180040210  call    cs:__imp_ReadProcessMemory
0x180040216  mov     rdx, [rdi+50h]; HWND
0x18004021a  lea     r8, [rbp+57h+var_88]; void **
0x18004021e  mov     ecx, 10h; dwSize
0x180040223  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180040228  mov     r15, rax
0x18004022b  test    rax, rax
0x18004022e  jz      loc_1800402D7
0x180040234  mov     r8, [rdi+50h]; HWND
0x180040238  mov     r9d, 419h; unsigned int
0x18004023e  mov     [rsp+0D0h+var_A0], r13; __int64 *
0x180040243  xor     edx, edx; bool
0x180040245  mov     [rsp+0D0h+var_A8], rax; __int64
0x18004024a  mov     rcx, rdi; this
0x18004024d  mov     [rsp+0D0h+lpNumberOfBytesRead], r13; unsigned __int64
0x180040252  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180040257  mov     r13d, eax
0x18004025a  test    eax, eax
0x18004025c  jns     short loc_18004027B
0x18004025e  mov     rdx, [rbp+57h+var_88]; hProcess
0x180040262  mov     rcx, r15; lpAddress
0x180040265  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18004026a  mov     rdx, [rbp+57h+hProcess]; hProcess
0x18004026e  mov     rcx, rsi; lpAddress
0x180040271  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180040276  mov     eax, r13d
0x180040279  jmp     short loc_1800402E5
0x18004027b  mov     rcx, [rbp+57h+var_88]; hProcess
0x18004027f  lea     r8, [rbp+57h+var_60]; lpBuffer
0x180040283  mov     r9d, 10h; nSize
0x180040289  mov     [rsp+0D0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x180040292  mov     rdx, r15; lpBaseAddress
0x180040295  call    cs:__imp_ReadProcessMemory
0x18004029b  mov     eax, [rdi+90h]
0x1800402a1  mov     ecx, 8
0x1800402a6  neg     eax
0x1800402a8  sbb     r8, r8
0x1800402ab  xor     eax, eax
0x1800402ad  and     r8d, 4
0x1800402b1  cmp     dword ptr [r14+8], 3
0x1800402b6  cmovnz  ecx, eax
0x1800402b9  add     rcx, r8
0x1800402bc  mov     eax, dword ptr [rbp+rcx+57h+var_60]
0x1800402c0  cmp     dword ptr [rbp+rcx+57h+Buffer], eax
0x1800402c4  jnz     short loc_1800402CB
0x1800402c6  bts     dword ptr [rbx+8], 0Fh
0x1800402cb  mov     rdx, [rbp+57h+var_88]; hProcess
0x1800402cf  mov     rcx, r15; lpAddress
0x1800402d2  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800402d7  mov     rdx, [rbp+57h+hProcess]; hProcess
0x1800402db  mov     rcx, rsi; lpAddress
0x1800402de  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800402e3  xor     eax, eax
0x1800402e5  mov     rcx, [rbp+57h+var_40]
0x1800402e9  xor     rcx, rsp; StackCookie
0x1800402ec  call    __security_check_cookie
0x1800402f1  add     rsp, 0A0h
0x1800402f8  pop     r15
0x1800402fa  pop     r14
0x1800402fc  pop     r13
0x1800402fe  pop     rdi
0x1800402ff  pop     rsi
0x180040300  pop     rbx
0x180040301  pop     rbp
0x180040302  retn
```
