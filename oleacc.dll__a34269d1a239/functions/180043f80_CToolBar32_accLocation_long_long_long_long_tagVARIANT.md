# CToolBar32::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x180043f80`
- end: `0x18004412e`
- name: `?accLocation@CToolBar32@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(CToolBar32 *__hidden this, int *, int *, int *, int *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18001c430`
- `0x18001e4c0`
- `0x180043f80`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800440c5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800440c5`
- `USER32!MapWindowPoints` at `0x1800440d9`
- `USER32!MapWindowPoints` at `0x1800440d9`

## pseudocode

```c
__int64 __fastcall CToolBar32::accLocation(CToolBar32 *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  __int64 v10; // rax
  IRecordInfo *pRecInfo; // xmm1_8
  HWND v13; // rdx
  void *v14; // rbx
  LONG lVal; // eax
  HWND v16; // r8
  unsigned int v17; // edi
  int v18; // r14d
  ULONG Hi32; // edx
  int v20; // eax
  int *v21; // rcx
  HANDLE hProcess; // [rsp+40h] [rbp-49h] BYREF
  __int64 v23; // [rsp+48h] [rbp-41h] BYREF
  int *v24; // [rsp+50h] [rbp-39h]
  struct tagVARIANT Buffer; // [rsp+60h] [rbp-29h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v10 = *(_QWORD *)this;
  v24 = a5;
  if ( !(*(unsigned int (__fastcall **)(CToolBar32 *, struct tagVARIANT *))(v10 + 240))(this, a6) )
    return 2147942487LL;
  if ( a6->lVal )
  {
    v13 = (HWND)*((_QWORD *)this + 10);
    hProcess = 0;
    *(_OWORD *)&Buffer.vt = 0;
    v14 = SharedAlloc(0x10u, v13, &hProcess);
    if ( v14 )
    {
      lVal = a6->lVal;
      v16 = (HWND)*((_QWORD *)this + 10);
      v17 = 1;
      v23 = 0;
      v18 = CAccessible::AccSendMessageTimeout(this, 0, v16, 0x41Du, lVal - 1, (__int64)v14, &v23);
      if ( v18 >= 0 )
      {
        if ( v23 )
        {
          v17 = 0;
          ReadProcessMemory(hProcess, v14, &Buffer, 0x10u, 0);
          MapWindowPoints(*((HWND *)this + 10), 0, (LPPOINT)&Buffer, 2u);
          Hi32 = Buffer.decVal.Hi32;
          v20 = Buffer.lVal - *(_DWORD *)&Buffer.vt;
          *a2 = *(_DWORD *)&Buffer.vt;
          v21 = v24;
          *a3 = Hi32;
          *a4 = v20;
          *v21 = Buffer.cyVal.Hi - Hi32;
        }
        SharedFree(v14, hProcess);
        return v17;
      }
      else
      {
        SharedFree(v14, hProcess);
        return (unsigned int)v18;
      }
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    pRecInfo = a6->pRecInfo;
    *(_OWORD *)&Buffer.vt = *(_OWORD *)&a6->vt;
    Buffer.pRecInfo = pRecInfo;
    return CClient::accLocation((HWND *)this, a2, a3, a4, a5, &Buffer);
  }
}

```

## disassembly

```asm
0x180043f80  push    rbp
0x180043f82  push    rbx
0x180043f83  push    rsi
0x180043f84  push    rdi
0x180043f85  push    r12
0x180043f87  push    r13
0x180043f89  push    r14
0x180043f8b  push    r15
0x180043f8d  lea     rbp, [rsp-0Fh]
0x180043f92  sub     rsp, 98h
0x180043f99  mov     rax, cs:__security_cookie
0x180043fa0  xor     rax, rsp
0x180043fa3  mov     [rbp+47h+var_50], rax
0x180043fa7  mov     rbx, [rbp+47h+arg_20]
0x180043fab  xor     r14d, r14d
0x180043fae  mov     rdi, [rbp+47h+arg_28]
0x180043fb2  mov     r15, rdx
0x180043fb5  mov     [rdx], r14d
0x180043fb8  mov     r13, r9
0x180043fbb  mov     [r8], r14d
0x180043fbe  mov     rdx, rdi
0x180043fc1  mov     [r9], r14d
0x180043fc4  mov     r12, r8
0x180043fc7  mov     [rbx], r14d
0x180043fca  mov     rsi, rcx
0x180043fcd  mov     rax, [rcx]
0x180043fd0  mov     [rbp+47h+var_80], rbx
0x180043fd4  mov     rax, [rax+0F0h]
0x180043fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fe0  test    eax, eax
0x180043fe2  jnz     short loc_180043FEE
0x180043fe4  mov     eax, 80070057h
0x180043fe9  jmp     loc_18004410E
0x180043fee  cmp     [rdi+8], r14d
0x180043ff2  jnz     short loc_180044029
0x180043ff4  movups  xmm0, xmmword ptr [rdi]
0x180043ff7  lea     rax, [rbp+47h+Buffer]
0x180043ffb  mov     r9, r13; int *
0x180043ffe  movsd   xmm1, qword ptr [rdi+10h]
0x180044003  mov     r8, r12; int *
0x180044006  mov     [rsp+0D0h+var_A8], rax; struct tagVARIANT *
0x18004400b  mov     rdx, r15; int *
0x18004400e  mov     rcx, rsi; this
0x180044011  movaps  [rbp+47h+Buffer], xmm0
0x180044015  movsd   [rbp+47h+var_60], xmm1
0x18004401a  mov     [rsp+0D0h+lpNumberOfBytesRead], rbx; int *
0x18004401f  call    ?accLocation@CClient@@UEAAJPEAJ000UtagVARIANT@@@Z; CClient::accLocation(long *,long *,long *,long *,tagVARIANT)
0x180044024  jmp     loc_18004410E
0x180044029  mov     rdx, [rsi+50h]; HWND
0x18004402d  lea     r8, [rbp+47h+hProcess]; void **
0x180044031  xorps   xmm0, xmm0
0x180044034  mov     [rbp+47h+hProcess], r14
0x180044038  mov     ecx, 10h; dwSize
0x18004403d  movups  [rbp+47h+Buffer], xmm0
0x180044041  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180044046  mov     rbx, rax
0x180044049  test    rax, rax
0x18004404c  jnz     short loc_180044058
0x18004404e  mov     eax, 8007000Eh
0x180044053  jmp     loc_18004410E
0x180044058  mov     eax, [rdi+8]
0x18004405b  mov     r9d, 41Dh; unsigned int
0x180044061  mov     r8, [rsi+50h]; HWND
0x180044065  mov     edi, 1
0x18004406a  sub     eax, edi
0x18004406c  mov     [rbp+47h+var_88], r14
0x180044070  movsxd  rcx, eax
0x180044073  xor     edx, edx; bool
0x180044075  lea     rax, [rbp+47h+var_88]
0x180044079  mov     [rsp+0D0h+var_A0], rax; __int64 *
0x18004407e  mov     [rsp+0D0h+var_A8], rbx; __int64
0x180044083  mov     [rsp+0D0h+lpNumberOfBytesRead], rcx; unsigned __int64
0x180044088  mov     rcx, rsi; this
0x18004408b  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180044090  mov     r14d, eax
0x180044093  test    eax, eax
0x180044095  jns     short loc_1800440A8
0x180044097  mov     rdx, [rbp+47h+hProcess]; hProcess
0x18004409b  mov     rcx, rbx; lpAddress
0x18004409e  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800440a3  mov     eax, r14d
0x1800440a6  jmp     short loc_18004410E
0x1800440a8  cmp     [rbp+47h+var_88], 0
0x1800440ad  jz      short loc_180044100
0x1800440af  mov     rcx, [rbp+47h+hProcess]; hProcess
0x1800440b3  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x1800440b7  xor     edi, edi
0x1800440b9  mov     rdx, rbx; lpBaseAddress
0x1800440bc  mov     [rsp+0D0h+lpNumberOfBytesRead], rdi; lpNumberOfBytesRead
0x1800440c1  lea     r9d, [rdi+10h]; nSize
0x1800440c5  call    cs:__imp_ReadProcessMemory
0x1800440cb  mov     rcx, [rsi+50h]; hWndFrom
0x1800440cf  lea     r9d, [rdi+2]; cPoints
0x1800440d3  lea     r8, [rbp+47h+Buffer]; lpPoints
0x1800440d7  xor     edx, edx; hWndTo
0x1800440d9  call    cs:__imp_MapWindowPoints
0x1800440df  mov     ecx, dword ptr [rbp+47h+Buffer]
0x1800440e2  mov     edx, dword ptr [rbp+47h+Buffer+4]
0x1800440e5  mov     eax, dword ptr [rbp+47h+Buffer+8]
0x1800440e8  sub     eax, ecx
0x1800440ea  mov     [r15], ecx
0x1800440ed  mov     rcx, [rbp+47h+var_80]
0x1800440f1  mov     [r12], edx
0x1800440f5  mov     [r13+0], eax
0x1800440f9  mov     eax, dword ptr [rbp+47h+Buffer+0Ch]
0x1800440fc  sub     eax, edx
0x1800440fe  mov     [rcx], eax
0x180044100  mov     rdx, [rbp+47h+hProcess]; hProcess
0x180044104  mov     rcx, rbx; lpAddress
0x180044107  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18004410c  mov     eax, edi
0x18004410e  mov     rcx, [rbp+47h+var_50]
0x180044112  xor     rcx, rsp; StackCookie
0x180044115  call    __security_check_cookie
0x18004411a  add     rsp, 98h
0x180044121  pop     r15
0x180044123  pop     r14
0x180044125  pop     r13
0x180044127  pop     r12
0x180044129  pop     rdi
0x18004412a  pop     rsi
0x18004412b  pop     rbx
0x18004412c  pop     rbp
0x18004412d  retn
```
