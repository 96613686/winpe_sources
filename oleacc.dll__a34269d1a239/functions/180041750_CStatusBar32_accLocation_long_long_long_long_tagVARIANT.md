# CStatusBar32::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x180041750`
- end: `0x1800418f1`
- name: `?accLocation@CStatusBar32@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `417`
- prototype: `__int64 __fastcall(CStatusBar32 *__hidden this, int *, int *, int *, int *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18001c430`
- `0x18001e4c0`
- `0x180041750`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180041880`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180041880`
- `USER32!MapWindowPoints` at `0x180041896`
- `USER32!MapWindowPoints` at `0x180041896`

## pseudocode

```c
__int64 __fastcall CStatusBar32::accLocation(HWND *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  HWND v9; // rax
  IRecordInfo *pRecInfo; // xmm1_8
  void *v13; // rdi
  HWND v14; // r8
  unsigned __int64 v15; // rcx
  int v16; // ebx
  int v17; // edx
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
  Buffer = 0;
  hProcess = 0;
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
      v16 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, v14, 0x40Au, v15, (__int64)v13, &v20);
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
          v16 = 0;
        }
        else
        {
          v16 = 1;
        }
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
0x180041750  push    rbp
0x180041752  push    rbx
0x180041753  push    rsi
0x180041754  push    rdi
0x180041755  push    r12
0x180041757  push    r13
0x180041759  push    r14
0x18004175b  push    r15
0x18004175d  lea     rbp, [rsp-0Fh]
0x180041762  sub     rsp, 98h
0x180041769  mov     rax, cs:__security_cookie
0x180041770  xor     rax, rsp
0x180041773  mov     [rbp+47h+var_50], rax
0x180041777  mov     r13, [rbp+47h+arg_20]
0x18004177b  xor     edi, edi
0x18004177d  mov     rbx, [rbp+47h+arg_28]
0x180041781  mov     r14, rdx
0x180041784  mov     [rdx], edi
0x180041786  xorps   xmm0, xmm0
0x180041789  mov     [r8], edi
0x18004178c  mov     rdx, rbx
0x18004178f  mov     [r9], edi
0x180041792  mov     r12, r9
0x180041795  mov     [r13+0], edi
0x180041799  mov     r15, r8
0x18004179c  mov     rax, [rcx]
0x18004179f  mov     rsi, rcx
0x1800417a2  movups  [rbp+47h+Buffer], xmm0
0x1800417a6  mov     [rbp+47h+hProcess], rdi
0x1800417aa  mov     rax, [rax+0F0h]
0x1800417b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417b6  test    eax, eax
0x1800417b8  jnz     short loc_1800417C4
0x1800417ba  mov     eax, 80070057h
0x1800417bf  jmp     loc_1800418D1
0x1800417c4  cmp     [rbx+8], edi
0x1800417c7  jnz     short loc_1800417FE
0x1800417c9  movups  xmm0, xmmword ptr [rbx]
0x1800417cc  lea     rax, [rbp+47h+var_80]
0x1800417d0  mov     r9, r12; int *
0x1800417d3  movsd   xmm1, qword ptr [rbx+10h]
0x1800417d8  mov     r8, r15; int *
0x1800417db  mov     [rsp+0D0h+var_A8], rax; struct tagVARIANT *
0x1800417e0  mov     rdx, r14; int *
0x1800417e3  mov     rcx, rsi; this
0x1800417e6  movaps  xmmword ptr [rbp+47h+var_80], xmm0
0x1800417ea  movsd   qword ptr [rbp+47h+var_80+10h], xmm1
0x1800417ef  mov     [rsp+0D0h+lpNumberOfBytesRead], r13; int *
0x1800417f4  call    ?accLocation@CClient@@UEAAJPEAJ000UtagVARIANT@@@Z; CClient::accLocation(long *,long *,long *,long *,tagVARIANT)
0x1800417f9  jmp     loc_1800418D1
0x1800417fe  mov     rdx, [rsi+50h]; HWND
0x180041802  lea     r8, [rbp+47h+hProcess]; void **
0x180041806  mov     ecx, 10h; dwSize
0x18004180b  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180041810  mov     rdi, rax
0x180041813  test    rax, rax
0x180041816  jnz     short loc_180041822
0x180041818  mov     eax, 8007000Eh
0x18004181d  jmp     loc_1800418D1
0x180041822  mov     eax, [rbx+8]
0x180041825  mov     r9d, 40Ah; unsigned int
0x18004182b  mov     r8, [rsi+50h]; HWND
0x18004182f  dec     eax
0x180041831  movsxd  rcx, eax
0x180041834  xor     edx, edx; bool
0x180041836  lea     rax, [rbp+47h+var_88]
0x18004183a  mov     [rbp+47h+var_88], 0
0x180041842  mov     [rsp+0D0h+var_A0], rax; __int64 *
0x180041847  mov     [rsp+0D0h+var_A8], rdi; __int64
0x18004184c  mov     [rsp+0D0h+lpNumberOfBytesRead], rcx; unsigned __int64
0x180041851  mov     rcx, rsi; this
0x180041854  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180041859  mov     ebx, eax
0x18004185b  test    eax, eax
0x18004185d  js      short loc_1800418C3
0x18004185f  cmp     [rbp+47h+var_88], 0
0x180041864  jz      short loc_1800418BE
0x180041866  mov     rcx, [rbp+47h+hProcess]; hProcess
0x18004186a  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x18004186e  mov     r9d, 10h; nSize
0x180041874  mov     [rsp+0D0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18004187d  mov     rdx, rdi; lpBaseAddress
0x180041880  call    cs:__imp_ReadProcessMemory
0x180041886  mov     rcx, [rsi+50h]; hWndFrom
0x18004188a  lea     r8, [rbp+47h+Buffer]; lpPoints
0x18004188e  mov     r9d, 2; cPoints
0x180041894  xor     edx, edx; hWndTo
0x180041896  call    cs:__imp_MapWindowPoints
0x18004189c  mov     ecx, dword ptr [rbp+47h+Buffer]
0x18004189f  mov     edx, dword ptr [rbp+47h+Buffer+4]
0x1800418a2  mov     eax, dword ptr [rbp+47h+Buffer+8]
0x1800418a5  sub     eax, ecx
0x1800418a7  mov     [r14], ecx
0x1800418aa  mov     [r15], edx
0x1800418ad  mov     [r12], eax
0x1800418b1  mov     eax, dword ptr [rbp+47h+Buffer+0Ch]
0x1800418b4  sub     eax, edx
0x1800418b6  mov     [r13+0], eax
0x1800418ba  xor     ebx, ebx
0x1800418bc  jmp     short loc_1800418C3
0x1800418be  mov     ebx, 1
0x1800418c3  mov     rdx, [rbp+47h+hProcess]; hProcess
0x1800418c7  mov     rcx, rdi; lpAddress
0x1800418ca  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800418cf  mov     eax, ebx
0x1800418d1  mov     rcx, [rbp+47h+var_50]
0x1800418d5  xor     rcx, rsp; StackCookie
0x1800418d8  call    __security_check_cookie
0x1800418dd  add     rsp, 98h
0x1800418e4  pop     r15
0x1800418e6  pop     r14
0x1800418e8  pop     r13
0x1800418ea  pop     r12
0x1800418ec  pop     rdi
0x1800418ed  pop     rsi
0x1800418ee  pop     rbx
0x1800418ef  pop     rbp
0x1800418f0  retn
```
