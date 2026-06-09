# CHeader32::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x18002c7d0`
- end: `0x18002c96c`
- name: `?accLocation@CHeader32@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(CHeader32 *__hidden this, int *, int *, int *, int *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18001c430`
- `0x18001e4c0`
- `0x18002c7d0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002c900`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002c900`
- `USER32!MapWindowPoints` at `0x18002c916`
- `USER32!MapWindowPoints` at `0x18002c916`

## pseudocode

```c
__int64 __fastcall CHeader32::accLocation(HWND *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  HWND v9; // rax
  IRecordInfo *pRecInfo; // xmm1_8
  void *v13; // rbx
  HWND v14; // r8
  unsigned __int64 v15; // rcx
  int v16; // edi
  int v17; // r8d
  int v18; // eax
  HANDLE hProcess; // [rsp+40h] [rbp-49h] BYREF
  __int64 v20; // [rsp+48h] [rbp-41h] BYREF
  struct tagVARIANT v21; // [rsp+50h] [rbp-39h] BYREF
  __int128 Buffer; // [rsp+70h] [rbp-19h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v9 = *this;
  hProcess = 0;
  Buffer = 0;
  if ( !(*((unsigned int (__fastcall **)(HWND *, struct tagVARIANT *))v9 + 30))(this, a6) )
    return 2147942487LL;
  if ( a6->lVal )
  {
    v13 = SharedAlloc(0x10u, this[10], &hProcess);
    if ( v13 )
    {
      v14 = this[10];
      v15 = a6->lVal - 1;
      v20 = 0;
      v16 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, v14, 0x1207u, v15, (__int64)v13, &v20);
      if ( v16 >= 0 )
      {
        if ( v20 )
        {
          ReadProcessMemory(hProcess, v13, &Buffer, 0x10u, 0);
          MapWindowPoints(this[10], 0, (LPPOINT)&Buffer, 2u);
          v17 = DWORD1(Buffer);
          v18 = DWORD2(Buffer) - Buffer;
          *a2 = Buffer;
          *a3 = v17;
          *a4 = v18;
          *a5 = HIDWORD(Buffer) - v17;
        }
        v16 = 0;
      }
      SharedFree(v13, hProcess);
      return (unsigned int)v16;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    pRecInfo = a6->pRecInfo;
    *(_OWORD *)&v21.vt = *(_OWORD *)&a6->vt;
    v21.pRecInfo = pRecInfo;
    return CClient::accLocation(this, a2, a3, a4, a5, &v21);
  }
}

```

## disassembly

```asm
0x18002c7d0  push    rbp
0x18002c7d2  push    rbx
0x18002c7d3  push    rsi
0x18002c7d4  push    rdi
0x18002c7d5  push    r12
0x18002c7d7  push    r13
0x18002c7d9  push    r14
0x18002c7db  push    r15
0x18002c7dd  lea     rbp, [rsp-0Fh]
0x18002c7e2  sub     rsp, 98h
0x18002c7e9  mov     rax, cs:__security_cookie
0x18002c7f0  xor     rax, rsp
0x18002c7f3  mov     [rbp+47h+var_50], rax
0x18002c7f7  mov     r13, [rbp+47h+arg_20]
0x18002c7fb  xor     ebx, ebx
0x18002c7fd  mov     rdi, [rbp+47h+arg_28]
0x18002c801  mov     r14, rdx
0x18002c804  mov     [rdx], ebx
0x18002c806  xorps   xmm0, xmm0
0x18002c809  mov     [r8], ebx
0x18002c80c  mov     rdx, rdi
0x18002c80f  mov     [r9], ebx
0x18002c812  mov     r12, r9
0x18002c815  mov     [r13+0], ebx
0x18002c819  mov     r15, r8
0x18002c81c  mov     rax, [rcx]
0x18002c81f  mov     rsi, rcx
0x18002c822  mov     [rbp+47h+hProcess], rbx
0x18002c826  movups  [rbp+47h+Buffer], xmm0
0x18002c82a  mov     rax, [rax+0F0h]
0x18002c831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c836  test    eax, eax
0x18002c838  jnz     short loc_18002C844
0x18002c83a  mov     eax, 80070057h
0x18002c83f  jmp     loc_18002C94C
0x18002c844  cmp     [rdi+8], ebx
0x18002c847  jnz     short loc_18002C87E
0x18002c849  movups  xmm0, xmmword ptr [rdi]
0x18002c84c  lea     rax, [rbp+47h+var_80]
0x18002c850  mov     r9, r12; int *
0x18002c853  movsd   xmm1, qword ptr [rdi+10h]
0x18002c858  mov     r8, r15; int *
0x18002c85b  mov     [rsp+0D0h+var_A8], rax; struct tagVARIANT *
0x18002c860  mov     rdx, r14; int *
0x18002c863  mov     rcx, rsi; this
0x18002c866  movaps  xmmword ptr [rbp+47h+var_80], xmm0
0x18002c86a  movsd   qword ptr [rbp+47h+var_80+10h], xmm1
0x18002c86f  mov     [rsp+0D0h+lpNumberOfBytesRead], r13; int *
0x18002c874  call    ?accLocation@CClient@@UEAAJPEAJ000UtagVARIANT@@@Z; CClient::accLocation(long *,long *,long *,long *,tagVARIANT)
0x18002c879  jmp     loc_18002C94C
0x18002c87e  mov     rdx, [rsi+50h]; HWND
0x18002c882  lea     r8, [rbp+47h+hProcess]; void **
0x18002c886  mov     ecx, 10h; dwSize
0x18002c88b  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18002c890  mov     rbx, rax
0x18002c893  test    rax, rax
0x18002c896  jnz     short loc_18002C8A2
0x18002c898  mov     eax, 8007000Eh
0x18002c89d  jmp     loc_18002C94C
0x18002c8a2  mov     eax, [rdi+8]
0x18002c8a5  mov     r9d, 1207h; unsigned int
0x18002c8ab  mov     r8, [rsi+50h]; HWND
0x18002c8af  dec     eax
0x18002c8b1  movsxd  rcx, eax
0x18002c8b4  xor     edx, edx; bool
0x18002c8b6  lea     rax, [rbp+47h+var_88]
0x18002c8ba  mov     [rbp+47h+var_88], 0
0x18002c8c2  mov     [rsp+0D0h+var_A0], rax; __int64 *
0x18002c8c7  mov     [rsp+0D0h+var_A8], rbx; __int64
0x18002c8cc  mov     [rsp+0D0h+lpNumberOfBytesRead], rcx; unsigned __int64
0x18002c8d1  mov     rcx, rsi; this
0x18002c8d4  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002c8d9  mov     edi, eax
0x18002c8db  test    eax, eax
0x18002c8dd  js      short loc_18002C93E
0x18002c8df  cmp     [rbp+47h+var_88], 0
0x18002c8e4  jz      short loc_18002C93C
0x18002c8e6  mov     rcx, [rbp+47h+hProcess]; hProcess
0x18002c8ea  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x18002c8ee  mov     r9d, 10h; nSize
0x18002c8f4  mov     [rsp+0D0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18002c8fd  mov     rdx, rbx; lpBaseAddress
0x18002c900  call    cs:__imp_ReadProcessMemory
0x18002c906  mov     rcx, [rsi+50h]; hWndFrom
0x18002c90a  lea     r8, [rbp+47h+Buffer]; lpPoints
0x18002c90e  mov     r9d, 2; cPoints
0x18002c914  xor     edx, edx; hWndTo
0x18002c916  call    cs:__imp_MapWindowPoints
0x18002c91c  mov     ecx, dword ptr [rbp+47h+Buffer]
0x18002c91f  mov     r8d, dword ptr [rbp+47h+Buffer+4]
0x18002c923  mov     eax, dword ptr [rbp+47h+Buffer+8]
0x18002c926  sub     eax, ecx
0x18002c928  mov     [r14], ecx
0x18002c92b  mov     [r15], r8d
0x18002c92e  mov     [r12], eax
0x18002c932  mov     eax, dword ptr [rbp+47h+Buffer+0Ch]
0x18002c935  sub     eax, r8d
0x18002c938  mov     [r13+0], eax
0x18002c93c  xor     edi, edi
0x18002c93e  mov     rdx, [rbp+47h+hProcess]; hProcess
0x18002c942  mov     rcx, rbx; lpAddress
0x18002c945  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002c94a  mov     eax, edi
0x18002c94c  mov     rcx, [rbp+47h+var_50]
0x18002c950  xor     rcx, rsp; StackCookie
0x18002c953  call    __security_check_cookie
0x18002c958  add     rsp, 98h
0x18002c95f  pop     r15
0x18002c961  pop     r14
0x18002c963  pop     r13
0x18002c965  pop     r12
0x18002c967  pop     rdi
0x18002c968  pop     rsi
0x18002c969  pop     rbx
0x18002c96a  pop     rbp
0x18002c96b  retn
```
