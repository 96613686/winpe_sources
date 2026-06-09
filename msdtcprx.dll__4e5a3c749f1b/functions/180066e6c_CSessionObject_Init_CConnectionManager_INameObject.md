# CSessionObject::Init(CConnectionManager *,INameObject *)

- ea: `0x180066e6c`
- end: `0x180067006`
- name: `?Init@CSessionObject@@QEAAJPEAVCConnectionManager@@PEAUINameObject@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(CSessionObject *__hidden this, struct CConnectionManager *, struct INameObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800562b4`

## callees

- `0x18001234c`
- `0x180066e6c`
- `0x18006700c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180066ee5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180066f12`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180066f38`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180066ee5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180066f12`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180066f38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066fbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066fd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066fec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066fbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066fd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066fec`

## pseudocode

```c
int __fastcall CSessionObject::Init(CSessionObject *this, struct CConnectionManager *a2, struct INameObject *a3)
{
  int v5; // edi
  HANDLE EventA; // rax
  int v7; // edi
  void **v8; // rsi
  HANDLE v9; // rax
  HANDLE v10; // rax
  unsigned __int8 **v11; // rax
  int result; // eax
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx

  *((_QWORD *)this + 81) = a2;
  *(_DWORD *)this = 0;
  *((_DWORD *)this + 165) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 355) = 0;
  v5 = 1;
  *((_DWORD *)this + 1) = 1;
  *((_QWORD *)this + 11) = a3;
  (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)a3 + 8LL))(a3);
  *((_DWORD *)this + 26) = 1;
  CSessionObject::SetStatus(this, 2);
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_DWORD *)this + 170) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_DWORD *)this + 167) = 0;
  EventA = CreateEventA(0, 0, 1, 0);
  *((_QWORD *)this + 16) = EventA;
  if ( !EventA )
  {
    v7 = -2147024882;
    v8 = (void **)((char *)this + 136);
LABEL_10:
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)a3 + 16LL))(a3);
    v13 = *v8;
    *((_QWORD *)this + 11) = 0;
    *((_DWORD *)this + 1) = 0;
    *((_QWORD *)this + 81) = 0;
    *((_DWORD *)this + 26) = 0;
    if ( v13 )
    {
      CloseHandle(v13);
      *v8 = 0;
    }
    v14 = (void *)*((_QWORD *)this + 18);
    if ( v14 )
    {
      CloseHandle(v14);
      *((_QWORD *)this + 18) = 0;
    }
    v15 = (void *)*((_QWORD *)this + 16);
    if ( v15 )
    {
      CloseHandle(v15);
      *((_QWORD *)this + 16) = 0;
    }
    return v7;
  }
  v9 = CreateEventA(0, 1, 1, 0);
  v8 = (void **)((char *)this + 136);
  *((_QWORD *)this + 17) = v9;
  if ( !v9 || (v10 = CreateEventA(0, 1, 1, 0), (*((_QWORD *)this + 18) = v10) == 0) )
  {
    v7 = -2147024882;
    goto LABEL_10;
  }
  v11 = (unsigned __int8 **)(*(__int64 (__fastcall **)(struct INameObject *))(*(_QWORD *)a3 + 32LL))(a3);
  result = CSessionObject::IsMyGuidBigger(this, *v11, a3);
  if ( result )
  {
    if ( result != 1 )
      return result;
    v5 = 2;
  }
  *((_DWORD *)this + 24) = v5;
  v7 = (***((__int64 (__fastcall ****)(_QWORD, CSessionObject *))this + 80))(*((_QWORD *)this + 80), this);
  if ( v7 )
    goto LABEL_10;
  return v7;
}

```

## disassembly

```asm
0x180066e6c  push    rbx
0x180066e6e  push    rbp
0x180066e6f  push    rsi
0x180066e70  push    rdi
0x180066e71  push    r14
0x180066e73  sub     rsp, 20h
0x180066e77  xor     ebp, ebp
0x180066e79  mov     [rcx+288h], rdx
0x180066e80  mov     [rcx], ebp
0x180066e82  mov     rbx, rcx
0x180066e85  mov     [rcx+294h], ebp
0x180066e8b  mov     r14, r8
0x180066e8e  mov     [rcx+10h], ebp
0x180066e91  mov     [rcx+58Ch], ebp
0x180066e97  lea     edi, [rbp+1]
0x180066e9a  mov     [rcx+4], edi
0x180066e9d  mov     [rcx+58h], r8
0x180066ea1  mov     rcx, r8
0x180066ea4  mov     rax, [r8]
0x180066ea7  mov     rax, [rax+8]
0x180066eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066eb0  lea     edx, [rbp+2]
0x180066eb3  mov     [rbx+68h], edi
0x180066eb6  mov     rcx, rbx
0x180066eb9  call    ?SetStatus@CSessionObject@@QEAAXW4_SessionStatus@@@Z; CSessionObject::SetStatus(_SessionStatus)
0x180066ebe  xor     r9d, r9d; lpName
0x180066ec1  mov     [rbx+8], rbp
0x180066ec5  mov     r8d, edi; bInitialState
0x180066ec8  mov     [rbx+18h], ebp
0x180066ecb  xor     edx, edx; bManualReset
0x180066ecd  mov     [rbx+2A0h], rbp
0x180066ed4  xor     ecx, ecx; lpEventAttributes
0x180066ed6  mov     [rbx+2A8h], ebp
0x180066edc  mov     [rbx+20h], ebp
0x180066edf  mov     [rbx+29Ch], ebp
0x180066ee5  call    cs:__imp_CreateEventA
0x180066eeb  mov     [rbx+80h], rax
0x180066ef2  test    rax, rax
0x180066ef5  jnz     short loc_180066F08
0x180066ef7  mov     edi, 8007000Eh
0x180066efc  lea     rsi, [rbx+88h]
0x180066f03  jmp     loc_180066F96
0x180066f08  xor     r9d, r9d; lpName
0x180066f0b  mov     r8d, edi; bInitialState
0x180066f0e  mov     edx, edi; bManualReset
0x180066f10  xor     ecx, ecx; lpEventAttributes
0x180066f12  call    cs:__imp_CreateEventA
0x180066f18  lea     rsi, [rbx+88h]
0x180066f1f  mov     [rsi], rax
0x180066f22  test    rax, rax
0x180066f25  jnz     short loc_180066F2E
0x180066f27  mov     edi, 8007000Eh
0x180066f2c  jmp     short loc_180066F96
0x180066f2e  xor     r9d, r9d; lpName
0x180066f31  mov     r8d, edi; bInitialState
0x180066f34  mov     edx, edi; bManualReset
0x180066f36  xor     ecx, ecx; lpEventAttributes
0x180066f38  call    cs:__imp_CreateEventA
0x180066f3e  mov     [rbx+90h], rax
0x180066f45  test    rax, rax
0x180066f48  jz      short loc_180066F27
0x180066f4a  mov     rax, [r14]
0x180066f4d  mov     rcx, r14
0x180066f50  mov     rax, [rax+20h]
0x180066f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f59  mov     r8, r14; struct INameObject *
0x180066f5c  mov     rcx, rbx; this
0x180066f5f  mov     rdx, [rax]; unsigned __int8 *
0x180066f62  call    ?IsMyGuidBigger@CSessionObject@@AEAAJPEAEPEAUINameObject@@@Z; CSessionObject::IsMyGuidBigger(uchar *,INameObject *)
0x180066f67  test    eax, eax
0x180066f69  jz      short loc_180066F78
0x180066f6b  cmp     eax, edi
0x180066f6d  jnz     loc_180066FFB
0x180066f73  mov     edi, 2
0x180066f78  mov     [rbx+60h], edi
0x180066f7b  mov     rdx, rbx
0x180066f7e  mov     rcx, [rbx+280h]
0x180066f85  mov     rax, [rcx]
0x180066f88  mov     rax, [rax]
0x180066f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f90  mov     edi, eax
0x180066f92  test    eax, eax
0x180066f94  jz      short loc_180066FF9
0x180066f96  mov     rcx, [r14]
0x180066f99  mov     rax, [rcx+10h]
0x180066f9d  mov     rcx, r14
0x180066fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066fa5  mov     rcx, [rsi]; hObject
0x180066fa8  mov     [rbx+58h], rbp
0x180066fac  mov     [rbx+4], ebp
0x180066faf  mov     [rbx+288h], rbp
0x180066fb6  mov     [rbx+68h], ebp
0x180066fb9  test    rcx, rcx
0x180066fbc  jz      short loc_180066FC7
0x180066fbe  call    cs:__imp_CloseHandle
0x180066fc4  mov     [rsi], rbp
0x180066fc7  mov     rcx, [rbx+90h]; hObject
0x180066fce  test    rcx, rcx
0x180066fd1  jz      short loc_180066FE0
0x180066fd3  call    cs:__imp_CloseHandle
0x180066fd9  mov     [rbx+90h], rbp
0x180066fe0  mov     rcx, [rbx+80h]; hObject
0x180066fe7  test    rcx, rcx
0x180066fea  jz      short loc_180066FF9
0x180066fec  call    cs:__imp_CloseHandle
0x180066ff2  mov     [rbx+80h], rbp
0x180066ff9  mov     eax, edi
0x180066ffb  add     rsp, 20h
0x180066fff  pop     r14
0x180067001  pop     rdi
0x180067002  pop     rsi
0x180067003  pop     rbp
0x180067004  pop     rbx
0x180067005  retn
```
