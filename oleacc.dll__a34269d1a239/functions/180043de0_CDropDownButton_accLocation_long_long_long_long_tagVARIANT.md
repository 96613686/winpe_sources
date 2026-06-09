# CDropDownButton::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x180043de0`
- end: `0x180043f79`
- name: `?accLocation@CDropDownButton@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `409`
- prototype: `__int64 __usercall@<rax>(CDropDownButton *__hidden this@<rcx>, int *@<rdx>, int *@<r8>, int *@<r9>, int *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18001e4c0`
- `0x180043de0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180043f02`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180043f02`
- `USER32!MapWindowPoints` at `0x180043f19`
- `USER32!MapWindowPoints` at `0x180043f19`

## pseudocode

```c
__int64 __fastcall CDropDownButton::accLocation(
        CDropDownButton *this,
        int *a2,
        int *a3,
        int *a4,
        int *a5,
        struct tagVARIANT *a6)
{
  LONG v10; // eax
  __int64 *v11; // rcx
  __int64 v12; // rax
  IRecordInfo *pRecInfo; // xmm1_8
  int v14; // edi
  HWND v15; // rdx
  void *v16; // rbx
  HWND v17; // r8
  int v18; // edx
  int v19; // eax
  unsigned __int64 lpNumberOfBytesRead; // [rsp+20h] [rbp-59h]
  HANDLE hProcess; // [rsp+40h] [rbp-39h] BYREF
  __int128 Buffer; // [rsp+50h] [rbp-29h] BYREF
  IRecordInfo *v24; // [rsp+60h] [rbp-19h]

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  if ( a6->lVal )
  {
    v15 = (HWND)*((_QWORD *)this + 18);
    hProcess = 0;
    v16 = SharedAlloc(0x10u, v15, &hProcess);
    if ( v16 )
    {
      v17 = (HWND)*((_QWORD *)this + 18);
      lpNumberOfBytesRead = *((_DWORD *)this + 32) - 1;
      *(_QWORD *)&Buffer = 0;
      v14 = CAccessible::AccSendMessageTimeout(
              this,
              0,
              v17,
              0x467u,
              lpNumberOfBytesRead,
              (__int64)v16,
              (__int64 *)&Buffer);
      if ( v14 >= 0 )
      {
        if ( (_QWORD)Buffer )
        {
          v14 = 0;
          Buffer = 0;
          ReadProcessMemory(hProcess, v16, &Buffer, 0x10u, 0);
          MapWindowPoints(*((HWND *)this + 18), 0, (LPPOINT)&Buffer, 2u);
          v18 = DWORD1(Buffer);
          v19 = DWORD2(Buffer) - Buffer;
          *a2 = Buffer;
          *a3 = v18;
          *a4 = v19;
          *a5 = HIDWORD(Buffer) - v18;
        }
        else
        {
          v14 = -2147467259;
        }
      }
      SharedFree(v16, hProcess);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v10 = *((_DWORD *)this + 32);
    v11 = (__int64 *)*((_QWORD *)this + 17);
    a6->lVal = v10;
    v12 = *v11;
    pRecInfo = a6->pRecInfo;
    Buffer = *(_OWORD *)&a6->vt;
    v24 = pRecInfo;
    return (unsigned int)(*(__int64 (__fastcall **)(__int64 *, int *))(v12 + 176))(v11, a2);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180043de0  push    rbp
0x180043de2  push    rbx
0x180043de3  push    rsi
0x180043de4  push    rdi
0x180043de5  push    r12
0x180043de7  push    r13
0x180043de9  push    r14
0x180043deb  push    r15
0x180043ded  lea     rbp, [rsp-0Fh]
0x180043df2  sub     rsp, 88h
0x180043df9  mov     rax, cs:__security_cookie
0x180043e00  xor     rax, rsp
0x180043e03  mov     [rbp+47h+var_50], rax
0x180043e07  mov     r10, [rbp+47h+arg_28]
0x180043e0b  xor     edi, edi
0x180043e0d  mov     r13, [rbp+47h+arg_20]
0x180043e11  mov     r12, r9
0x180043e14  mov     [rdx], edi
0x180043e16  mov     r15, r8
0x180043e19  mov     [r8], edi
0x180043e1c  mov     r14, rdx
0x180043e1f  mov     rsi, rcx
0x180043e22  mov     [r9], edi
0x180043e25  mov     [r13+0], edi
0x180043e29  cmp     [r10+8], edi
0x180043e2d  jnz     short loc_180043E7A
0x180043e2f  mov     eax, [rcx+80h]
0x180043e35  lea     rdx, [rbp+47h+Buffer]
0x180043e39  mov     rcx, [rcx+88h]
0x180043e40  mov     [r10+8], eax
0x180043e44  movups  xmm0, xmmword ptr [r10]
0x180043e48  mov     [rsp+0C0h+var_98], rdx
0x180043e4d  mov     rdx, r14
0x180043e50  mov     rax, [rcx]
0x180043e53  movsd   xmm1, qword ptr [r10+10h]
0x180043e59  movaps  [rbp+47h+Buffer], xmm0
0x180043e5d  movsd   [rbp+47h+var_60], xmm1
0x180043e62  mov     rax, [rax+0B0h]
0x180043e69  mov     [rsp+0C0h+lpNumberOfBytesRead], r13
0x180043e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e73  mov     edi, eax
0x180043e75  jmp     loc_180043F57
0x180043e7a  mov     rdx, [rcx+90h]; HWND
0x180043e81  lea     r8, [rbp+47h+hProcess]; void **
0x180043e85  mov     ecx, 10h; dwSize
0x180043e8a  mov     [rbp+47h+hProcess], rdi
0x180043e8e  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180043e93  mov     rbx, rax
0x180043e96  test    rax, rax
0x180043e99  jz      loc_180043F52
0x180043e9f  mov     ecx, [rsi+80h]
0x180043ea5  lea     rax, [rbp+47h+Buffer]
0x180043ea9  mov     r8, [rsi+90h]; HWND
0x180043eb0  dec     ecx
0x180043eb2  movsxd  rdx, ecx
0x180043eb5  mov     r9d, 467h; unsigned int
0x180043ebb  mov     [rsp+0C0h+var_90], rax; __int64 *
0x180043ec0  mov     rcx, rsi; this
0x180043ec3  mov     [rsp+0C0h+var_98], rbx; __int64
0x180043ec8  mov     [rsp+0C0h+lpNumberOfBytesRead], rdx; unsigned __int64
0x180043ecd  xor     edx, edx; bool
0x180043ecf  mov     qword ptr [rbp+47h+Buffer], rdi
0x180043ed3  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180043ed8  mov     edi, eax
0x180043eda  test    eax, eax
0x180043edc  js      short loc_180043F44
0x180043ede  cmp     qword ptr [rbp+47h+Buffer], 0
0x180043ee3  jz      short loc_180043F3F
0x180043ee5  mov     rcx, [rbp+47h+hProcess]; hProcess
0x180043ee9  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x180043eed  xor     edi, edi
0x180043eef  xorps   xmm0, xmm0
0x180043ef2  mov     rdx, rbx; lpBaseAddress
0x180043ef5  mov     [rsp+0C0h+lpNumberOfBytesRead], rdi; lpNumberOfBytesRead
0x180043efa  movups  [rbp+47h+Buffer], xmm0
0x180043efe  lea     r9d, [rdi+10h]; nSize
0x180043f02  call    cs:__imp_ReadProcessMemory
0x180043f08  mov     rcx, [rsi+90h]; hWndFrom
0x180043f0f  lea     r9d, [rdi+2]; cPoints
0x180043f13  lea     r8, [rbp+47h+Buffer]; lpPoints
0x180043f17  xor     edx, edx; hWndTo
0x180043f19  call    cs:__imp_MapWindowPoints
0x180043f1f  mov     ecx, dword ptr [rbp+47h+Buffer]
0x180043f22  mov     edx, dword ptr [rbp+47h+Buffer+4]
0x180043f25  mov     eax, dword ptr [rbp+47h+Buffer+8]
0x180043f28  sub     eax, ecx
0x180043f2a  mov     [r14], ecx
0x180043f2d  mov     [r15], edx
0x180043f30  mov     [r12], eax
0x180043f34  mov     eax, dword ptr [rbp+47h+Buffer+0Ch]
0x180043f37  sub     eax, edx
0x180043f39  mov     [r13+0], eax
0x180043f3d  jmp     short loc_180043F44
0x180043f3f  mov     edi, 80004005h
0x180043f44  mov     rdx, [rbp+47h+hProcess]; hProcess
0x180043f48  mov     rcx, rbx; lpAddress
0x180043f4b  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180043f50  jmp     short loc_180043F57
0x180043f52  mov     edi, 8007000Eh
0x180043f57  mov     eax, edi
0x180043f59  mov     rcx, [rbp+47h+var_50]
0x180043f5d  xor     rcx, rsp; StackCookie
0x180043f60  call    __security_check_cookie
0x180043f65  add     rsp, 88h
0x180043f6c  pop     r15
0x180043f6e  pop     r14
0x180043f70  pop     r13
0x180043f72  pop     r12
0x180043f74  pop     rdi
0x180043f75  pop     rsi
0x180043f76  pop     rbx
0x180043f77  pop     rbp
0x180043f78  retn
```
