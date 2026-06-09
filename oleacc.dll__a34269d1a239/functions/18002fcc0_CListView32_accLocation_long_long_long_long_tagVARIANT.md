# CListView32::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x18002fcc0`
- end: `0x18002fe93`
- name: `?accLocation@CListView32@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(CListView32 *__hidden this, int *, int *, int *, int *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18001c430`
- `0x18001e4c0`
- `0x18002fcc0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002fe28`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002fe28`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002fdc6`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002fdc6`
- `USER32!MapWindowPoints` at `0x18002fe3e`
- `USER32!MapWindowPoints` at `0x18002fe3e`

## pseudocode

```c
int __fastcall CListView32::accLocation(HWND *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  HWND v10; // rax
  int result; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  void *v13; // rax
  void *v14; // rbx
  HWND v15; // r8
  unsigned __int64 v16; // rcx
  int v17; // r8d
  int v18; // eax
  int *v19; // rcx
  HANDLE hProcess; // [rsp+40h] [rbp-49h] BYREF
  __int64 v21; // [rsp+48h] [rbp-41h] BYREF
  int *v22; // [rsp+50h] [rbp-39h]
  struct tagVARIANT v23; // [rsp+60h] [rbp-29h] BYREF
  __int128 Buffer; // [rsp+80h] [rbp-9h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v10 = *this;
  v22 = a5;
  Buffer = 0;
  hProcess = 0;
  if ( !(*((unsigned int (__fastcall **)(HWND *, struct tagVARIANT *))v10 + 30))(this, a6) )
    return -2147024809;
  if ( a6->lVal )
  {
    v13 = SharedAlloc(0x10u, this[10], &hProcess);
    v14 = v13;
    if ( v13 )
    {
      LODWORD(Buffer) = 0;
      WriteProcessMemory(hProcess, v13, &Buffer, 0x10u, 0);
      v15 = this[10];
      v16 = a6->lVal - 1;
      v21 = 0;
      result = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, v15, 0x100Eu, v16, (__int64)v14, &v21);
      if ( result >= 0 )
      {
        if ( v21 )
        {
          ReadProcessMemory(hProcess, v14, &Buffer, 0x10u, 0);
          MapWindowPoints(this[10], 0, (LPPOINT)&Buffer, 2u);
          v17 = DWORD1(Buffer);
          v18 = DWORD2(Buffer) - Buffer;
          *a2 = Buffer;
          v19 = v22;
          *a3 = v17;
          *a4 = v18;
          *v19 = HIDWORD(Buffer) - v17;
        }
        SharedFree(v14, hProcess);
        return 0;
      }
    }
    else
    {
      return -2147024882;
    }
  }
  else
  {
    pRecInfo = a6->pRecInfo;
    *(_OWORD *)&v23.vt = *(_OWORD *)&a6->vt;
    v23.pRecInfo = pRecInfo;
    return CClient::accLocation((CClient *)this, a2, a3, a4, a5, &v23);
  }
  return result;
}

```

## disassembly

```asm
0x18002fcc0  push    rbp
0x18002fcc2  push    rbx
0x18002fcc3  push    rsi
0x18002fcc4  push    rdi
0x18002fcc5  push    r12
0x18002fcc7  push    r13
0x18002fcc9  push    r15
0x18002fccb  lea     rbp, [rsp-17h]
0x18002fcd0  sub     rsp, 0A0h
0x18002fcd7  mov     rax, cs:__security_cookie
0x18002fcde  xor     rax, rsp
0x18002fce1  mov     [rbp+47h+var_40], rax
0x18002fce5  mov     rbx, [rbp+47h+arg_20]
0x18002fce9  mov     r15, rdx
0x18002fcec  mov     rdi, [rbp+47h+arg_28]
0x18002fcf0  xorps   xmm0, xmm0
0x18002fcf3  mov     dword ptr [rdx], 0
0x18002fcf9  mov     r13, r9
0x18002fcfc  mov     dword ptr [r8], 0
0x18002fd03  mov     rdx, rdi
0x18002fd06  mov     dword ptr [r9], 0
0x18002fd0d  mov     r12, r8
0x18002fd10  mov     dword ptr [rbx], 0
0x18002fd16  mov     rsi, rcx
0x18002fd19  mov     rax, [rcx]
0x18002fd1c  mov     [rbp+47h+var_80], rbx
0x18002fd20  movups  [rbp+47h+Buffer], xmm0
0x18002fd24  mov     [rbp+47h+hProcess], 0
0x18002fd2c  mov     rax, [rax+0F0h]
0x18002fd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd38  test    eax, eax
0x18002fd3a  jnz     short loc_18002FD46
0x18002fd3c  mov     eax, 80070057h
0x18002fd41  jmp     loc_18002FE75
0x18002fd46  cmp     dword ptr [rdi+8], 0
0x18002fd4a  jnz     short loc_18002FD81
0x18002fd4c  movups  xmm0, xmmword ptr [rdi]
0x18002fd4f  lea     rax, [rbp+47h+var_70]
0x18002fd53  mov     r9, r13; int *
0x18002fd56  movsd   xmm1, qword ptr [rdi+10h]
0x18002fd5b  mov     r8, r12; int *
0x18002fd5e  mov     [rsp+0D0h+var_A8], rax; struct tagVARIANT *
0x18002fd63  mov     rdx, r15; int *
0x18002fd66  mov     rcx, rsi; this
0x18002fd69  movaps  xmmword ptr [rbp+47h+var_70], xmm0
0x18002fd6d  movsd   qword ptr [rbp+47h+var_70+10h], xmm1
0x18002fd72  mov     [rsp+0D0h+lpNumberOfBytesWritten], rbx; int *
0x18002fd77  call    ?accLocation@CClient@@UEAAJPEAJ000UtagVARIANT@@@Z; CClient::accLocation(long *,long *,long *,long *,tagVARIANT)
0x18002fd7c  jmp     loc_18002FE75
0x18002fd81  mov     rdx, [rsi+50h]; HWND
0x18002fd85  lea     r8, [rbp+47h+hProcess]; void **
0x18002fd89  mov     ecx, 10h; dwSize
0x18002fd8e  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18002fd93  mov     rbx, rax
0x18002fd96  test    rax, rax
0x18002fd99  jnz     short loc_18002FDA5
0x18002fd9b  mov     eax, 8007000Eh
0x18002fda0  jmp     loc_18002FE75
0x18002fda5  mov     rcx, [rbp+47h+hProcess]; hProcess
0x18002fda9  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x18002fdad  mov     r9d, 10h; nSize
0x18002fdb3  mov     dword ptr [rbp+47h+Buffer], 0
0x18002fdba  mov     rdx, rbx; lpBaseAddress
0x18002fdbd  mov     [rsp+0D0h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18002fdc6  call    cs:__imp_WriteProcessMemory
0x18002fdcc  mov     eax, [rdi+8]
0x18002fdcf  mov     r9d, 100Eh; unsigned int
0x18002fdd5  mov     r8, [rsi+50h]; HWND
0x18002fdd9  dec     eax
0x18002fddb  movsxd  rcx, eax
0x18002fdde  xor     edx, edx; bool
0x18002fde0  lea     rax, [rbp+47h+var_88]
0x18002fde4  mov     [rbp+47h+var_88], 0
0x18002fdec  mov     [rsp+0D0h+var_A0], rax; __int64 *
0x18002fdf1  mov     [rsp+0D0h+var_A8], rbx; __int64
0x18002fdf6  mov     [rsp+0D0h+lpNumberOfBytesWritten], rcx; unsigned __int64
0x18002fdfb  mov     rcx, rsi; this
0x18002fdfe  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002fe03  test    eax, eax
0x18002fe05  js      short loc_18002FE75
0x18002fe07  cmp     [rbp+47h+var_88], 0
0x18002fe0c  jz      short loc_18002FE67
0x18002fe0e  mov     rcx, [rbp+47h+hProcess]; hProcess
0x18002fe12  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x18002fe16  mov     r9d, 10h; nSize
0x18002fe1c  mov     [rsp+0D0h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x18002fe25  mov     rdx, rbx; lpBaseAddress
0x18002fe28  call    cs:__imp_ReadProcessMemory
0x18002fe2e  mov     rcx, [rsi+50h]; hWndFrom
0x18002fe32  lea     r8, [rbp+47h+Buffer]; lpPoints
0x18002fe36  mov     r9d, 2; cPoints
0x18002fe3c  xor     edx, edx; hWndTo
0x18002fe3e  call    cs:__imp_MapWindowPoints
0x18002fe44  mov     ecx, dword ptr [rbp+47h+Buffer]
0x18002fe47  mov     r8d, dword ptr [rbp+47h+Buffer+4]
0x18002fe4b  mov     eax, dword ptr [rbp+47h+Buffer+8]
0x18002fe4e  sub     eax, ecx
0x18002fe50  mov     [r15], ecx
0x18002fe53  mov     rcx, [rbp+47h+var_80]
0x18002fe57  mov     [r12], r8d
0x18002fe5b  mov     [r13+0], eax
0x18002fe5f  mov     eax, dword ptr [rbp+47h+Buffer+0Ch]
0x18002fe62  sub     eax, r8d
0x18002fe65  mov     [rcx], eax
0x18002fe67  mov     rdx, [rbp+47h+hProcess]; hProcess
0x18002fe6b  mov     rcx, rbx; lpAddress
0x18002fe6e  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002fe73  xor     eax, eax
0x18002fe75  mov     rcx, [rbp+47h+var_40]
0x18002fe79  xor     rcx, rsp; StackCookie
0x18002fe7c  call    __security_check_cookie
0x18002fe81  add     rsp, 0A0h
0x18002fe88  pop     r15
0x18002fe8a  pop     r13
0x18002fe8c  pop     r12
0x18002fe8e  pop     rdi
0x18002fe8f  pop     rsi
0x18002fe90  pop     rbx
0x18002fe91  pop     rbp
0x18002fe92  retn
```
