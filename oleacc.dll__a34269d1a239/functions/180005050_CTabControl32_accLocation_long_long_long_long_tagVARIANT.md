# CTabControl32::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x180005050`
- end: `0x18000520c`
- name: `?accLocation@CTabControl32@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(CTabControl32 *__hidden this, int *, int *, int *, int *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180005050`
- `0x1800056a4`
- `0x180007700`
- `0x18000771c`
- `0x18001c430`
- `0x18001e4c0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800051bb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800051bb`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x180005122`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x180005122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005133`
- `USER32!MapWindowPoints` at `0x1800051d1`
- `USER32!MapWindowPoints` at `0x1800051d1`

## pseudocode

```c
__int64 __fastcall CTabControl32::accLocation(HWND *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  HWND v9; // rax
  IRecordInfo *pRecInfo; // xmm1_8
  void *ProcessHandleFromHwnd; // rax
  void *v14; // rbx
  void *v15; // r14
  HWND v16; // r8
  unsigned __int64 v17; // rcx
  int v18; // edi
  int v19; // edx
  int v20; // eax
  int *v21; // rcx
  __int64 v22; // [rsp+40h] [rbp-49h] BYREF
  int *v23; // [rsp+48h] [rbp-41h]
  struct tagVARIANT v24; // [rsp+50h] [rbp-39h] BYREF
  __int128 Buffer; // [rsp+70h] [rbp-19h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v9 = *this;
  v23 = a5;
  Buffer = 0;
  if ( !(*((unsigned int (__fastcall **)(HWND *, struct tagVARIANT *))v9 + 30))(this, a6) )
    return 2147942487LL;
  if ( !a6->lVal )
  {
    pRecInfo = a6->pRecInfo;
    *(_OWORD *)&v24.vt = *(_OWORD *)&a6->vt;
    v24.pRecInfo = pRecInfo;
    return CClient::accLocation(this, a2, a3, a4, a5, &v24);
  }
  ProcessHandleFromHwnd = (void *)GetProcessHandleFromHwnd(this[10]);
  v14 = ProcessHandleFromHwnd;
  if ( !ProcessHandleFromHwnd )
    return 2147942414LL;
  v15 = VirtualAllocEx(ProcessHandleFromHwnd, 0, 0x10u, 0x1000u, 4u);
  if ( !v15 )
  {
    CloseHandle(v14);
    return 2147942414LL;
  }
  v16 = this[10];
  v17 = a6->lVal - 1;
  v22 = 0;
  v18 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, v16, 0x130Au, v17, (__int64)v15, &v22);
  if ( v18 >= 0 )
  {
    if ( v22 )
    {
      ReadProcessMemory(v14, v15, &Buffer, 0x10u, 0);
      MapWindowPoints(this[10], 0, (LPPOINT)&Buffer, 2u);
      v19 = DWORD1(Buffer);
      v20 = DWORD2(Buffer) - Buffer;
      *a2 = Buffer;
      v21 = v23;
      *a3 = v19;
      *a4 = v20;
      *v21 = HIDWORD(Buffer) - v19;
    }
    v18 = 0;
  }
  SharedFree(v15, v14);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180005050  push    rbp
0x180005052  push    rbx
0x180005053  push    rsi
0x180005054  push    rdi
0x180005055  push    r12
0x180005057  push    r13
0x180005059  push    r14
0x18000505b  push    r15
0x18000505d  lea     rbp, [rsp-0Fh]
0x180005062  sub     rsp, 98h
0x180005069  mov     rax, cs:__security_cookie
0x180005070  xor     rax, rsp
0x180005073  mov     [rbp+47h+var_50], rax
0x180005077  mov     rbx, [rbp+47h+arg_20]
0x18000507b  xor     r14d, r14d
0x18000507e  mov     rdi, [rbp+47h+arg_28]
0x180005082  mov     r15, rdx
0x180005085  mov     [rdx], r14d
0x180005088  xorps   xmm0, xmm0
0x18000508b  mov     [r8], r14d
0x18000508e  mov     rdx, rdi
0x180005091  mov     [r9], r14d
0x180005094  mov     r13, r9
0x180005097  mov     [rbx], r14d
0x18000509a  mov     r12, r8
0x18000509d  mov     rax, [rcx]
0x1800050a0  mov     rsi, rcx
0x1800050a3  mov     [rbp+47h+var_88], rbx
0x1800050a7  movups  [rbp+47h+Buffer], xmm0
0x1800050ab  mov     rax, [rax+0F0h]
0x1800050b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b7  test    eax, eax
0x1800050b9  jnz     short loc_1800050C2
0x1800050bb  mov     eax, 80070057h
0x1800050c0  jmp     short loc_18000513E
0x1800050c2  cmp     [rdi+8], r14d
0x1800050c6  jnz     short loc_1800050FA
0x1800050c8  movups  xmm0, xmmword ptr [rdi]
0x1800050cb  lea     rax, [rbp+47h+var_80]
0x1800050cf  mov     r9, r13; int *
0x1800050d2  movsd   xmm1, qword ptr [rdi+10h]
0x1800050d7  mov     r8, r12; int *
0x1800050da  mov     [rsp+0D0h+var_A8], rax; struct tagVARIANT *
0x1800050df  mov     rdx, r15; int *
0x1800050e2  mov     rcx, rsi; this
0x1800050e5  movaps  xmmword ptr [rbp+47h+var_80], xmm0
0x1800050e9  movsd   qword ptr [rbp+47h+var_80+10h], xmm1
0x1800050ee  mov     qword ptr [rsp+0D0h+flProtect], rbx; int *
0x1800050f3  call    ?accLocation@CClient@@UEAAJPEAJ000UtagVARIANT@@@Z; CClient::accLocation(long *,long *,long *,long *,tagVARIANT)
0x1800050f8  jmp     short loc_18000513E
0x1800050fa  mov     rcx, [rsi+50h]
0x1800050fe  call    GetProcessHandleFromHwnd
0x180005103  mov     rbx, rax
0x180005106  test    rax, rax
0x180005109  jz      short loc_180005139
0x18000510b  xor     edx, edx; lpAddress
0x18000510d  mov     [rsp+0D0h+flProtect], 4; flProtect
0x180005115  mov     r9d, 1000h; flAllocationType
0x18000511b  mov     rcx, rax; hProcess
0x18000511e  lea     r8d, [rdx+10h]; dwSize
0x180005122  call    cs:__imp_VirtualAllocEx
0x180005128  mov     r14, rax
0x18000512b  test    rax, rax
0x18000512e  jnz     short loc_18000515E
0x180005130  mov     rcx, rbx; hObject
0x180005133  call    cs:__imp_CloseHandle
0x180005139  mov     eax, 8007000Eh
0x18000513e  mov     rcx, [rbp+47h+var_50]
0x180005142  xor     rcx, rsp; StackCookie
0x180005145  call    __security_check_cookie
0x18000514a  add     rsp, 98h
0x180005151  pop     r15
0x180005153  pop     r14
0x180005155  pop     r13
0x180005157  pop     r12
0x180005159  pop     rdi
0x18000515a  pop     rsi
0x18000515b  pop     rbx
0x18000515c  pop     rbp
0x18000515d  retn
0x18000515e  mov     eax, [rdi+8]
0x180005161  mov     r9d, 130Ah; unsigned int
0x180005167  mov     r8, [rsi+50h]; HWND
0x18000516b  dec     eax
0x18000516d  movsxd  rcx, eax
0x180005170  xor     edx, edx; bool
0x180005172  lea     rax, [rbp+47h+var_90]
0x180005176  mov     [rbp+47h+var_90], 0
0x18000517e  mov     [rsp+0D0h+var_A0], rax; __int64 *
0x180005183  mov     [rsp+0D0h+var_A8], r14; __int64
0x180005188  mov     qword ptr [rsp+0D0h+flProtect], rcx; unsigned __int64
0x18000518d  mov     rcx, rsi; this
0x180005190  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180005195  mov     edi, eax
0x180005197  test    eax, eax
0x180005199  js      short loc_1800051FA
0x18000519b  cmp     [rbp+47h+var_90], 0
0x1800051a0  jz      short loc_1800051F8
0x1800051a2  mov     r9d, 10h; nSize
0x1800051a8  mov     qword ptr [rsp+0D0h+flProtect], 0; lpNumberOfBytesRead
0x1800051b1  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x1800051b5  mov     rdx, r14; lpBaseAddress
0x1800051b8  mov     rcx, rbx; hProcess
0x1800051bb  call    cs:__imp_ReadProcessMemory
0x1800051c1  mov     rcx, [rsi+50h]; hWndFrom
0x1800051c5  lea     r8, [rbp+47h+Buffer]; lpPoints
0x1800051c9  mov     r9d, 2; cPoints
0x1800051cf  xor     edx, edx; hWndTo
0x1800051d1  call    cs:__imp_MapWindowPoints
0x1800051d7  mov     ecx, dword ptr [rbp+47h+Buffer]
0x1800051da  mov     edx, dword ptr [rbp+47h+Buffer+4]
0x1800051dd  mov     eax, dword ptr [rbp+47h+Buffer+8]
0x1800051e0  sub     eax, ecx
0x1800051e2  mov     [r15], ecx
0x1800051e5  mov     rcx, [rbp+47h+var_88]
0x1800051e9  mov     [r12], edx
0x1800051ed  mov     [r13+0], eax
0x1800051f1  mov     eax, dword ptr [rbp+47h+Buffer+0Ch]
0x1800051f4  sub     eax, edx
0x1800051f6  mov     [rcx], eax
0x1800051f8  xor     edi, edi
0x1800051fa  mov     rdx, rbx; hProcess
0x1800051fd  mov     rcx, r14; lpAddress
0x180005200  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180005205  mov     eax, edi
0x180005207  jmp     loc_18000513E
```
