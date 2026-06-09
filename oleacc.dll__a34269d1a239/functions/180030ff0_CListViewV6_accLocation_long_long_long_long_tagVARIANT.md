# CListViewV6::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x180030ff0`
- end: `0x1800311b0`
- name: `?accLocation@CListViewV6@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `448`
- prototype: `__int64 __usercall@<rax>(CListViewV6 *__hidden this@<rcx>, int *@<rdx>, int *@<r8>, int *@<r9>, int *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18001e4c0`
- `0x180030948`
- `0x180030acc`
- `0x180030ff0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031145`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031145`
- `USER32!MapWindowPoints` at `0x180031159`
- `USER32!MapWindowPoints` at `0x180031159`

## pseudocode

```c
__int64 __fastcall CListViewV6::accLocation(HWND *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  CListViewV6 *v10; // rcx
  int v11; // ebx
  __int64 *v12; // rcx
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 v14; // rax
  HWND v15; // rdx
  void *v16; // rdi
  HWND v17; // r8
  int v18; // r8d
  int v19; // eax
  int *v20; // rcx
  unsigned __int64 lpNumberOfBytesRead; // [rsp+20h] [rbp-69h]
  HANDLE hProcess; // [rsp+40h] [rbp-49h] BYREF
  int *v24; // [rsp+48h] [rbp-41h]
  __int128 Buffer; // [rsp+50h] [rbp-39h] BYREF
  IRecordInfo *v26; // [rsp+60h] [rbp-29h]
  __int64 v27; // [rsp+70h] [rbp-19h] BYREF
  int v28; // [rsp+78h] [rbp-11h]

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v24 = a5;
  v27 = 0;
  v28 = 0;
  v11 = CListViewV6::_ValidateChild((CListViewV6 *)this, a6, (struct tagLVACCINDEX *)&v27);
  if ( v11 >= 0 )
  {
    if ( !a6->lVal )
    {
LABEL_5:
      v12 = (__int64 *)this[16];
      pRecInfo = a6->pRecInfo;
      v14 = *v12;
      Buffer = *(_OWORD *)&a6->vt;
      v26 = pRecInfo;
      return (unsigned int)(*(__int64 (__fastcall **)(__int64 *, int *, int *, int *, int *, __int128 *))(v14 + 176))(
                             v12,
                             a2,
                             a3,
                             a4,
                             a5,
                             &Buffer);
    }
    if ( (unsigned int)CListViewV6::_IsItem(v10, (const struct tagLVACCINDEX *)&v27) )
    {
      a6->lVal = v27 + 1;
      goto LABEL_5;
    }
    v15 = this[10];
    hProcess = 0;
    v11 = -2147024882;
    v16 = SharedAlloc(0x10u, v15, &hProcess);
    if ( v16 )
    {
      v17 = this[10];
      lpNumberOfBytesRead = a6->lVal;
      *(_QWORD *)&Buffer = 0;
      v11 = CAccessible::AccSendMessageTimeout(
              (CAccessible *)this,
              0,
              v17,
              0x10C5u,
              lpNumberOfBytesRead,
              (__int64)v16,
              (__int64 *)&Buffer);
      if ( v11 >= 0 )
      {
        v11 = 1;
        if ( (_QWORD)Buffer )
        {
          v11 = 0;
          Buffer = 0;
          ReadProcessMemory(hProcess, v16, &Buffer, 0x10u, 0);
          MapWindowPoints(this[10], 0, (LPPOINT)&Buffer, 2u);
          v18 = DWORD1(Buffer);
          v19 = DWORD2(Buffer) - Buffer;
          *a2 = Buffer;
          v20 = v24;
          *a3 = v18;
          *a4 = v19;
          *v20 = HIDWORD(Buffer) - v18;
        }
      }
      SharedFree(v16, hProcess);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180030ff0  push    rbp
0x180030ff2  push    rbx
0x180030ff3  push    rsi
0x180030ff4  push    rdi
0x180030ff5  push    r12
0x180030ff7  push    r13
0x180030ff9  push    r14
0x180030ffb  push    r15
0x180030ffd  lea     rbp, [rsp-0Fh]
0x180031002  sub     rsp, 98h
0x180031009  mov     rax, cs:__security_cookie
0x180031010  xor     rax, rsp
0x180031013  mov     [rbp+47h+var_50], rax
0x180031017  mov     rdi, [rbp+47h+arg_20]
0x18003101b  xor     eax, eax
0x18003101d  mov     rsi, [rbp+47h+arg_28]
0x180031021  mov     r12, r8
0x180031024  mov     [rdx], eax
0x180031026  mov     r15, rdx
0x180031029  mov     [r8], eax
0x18003102c  mov     rdx, rsi; struct tagVARIANT *
0x18003102f  mov     [r9], eax
0x180031032  lea     r8, [rbp+47h+var_60]; struct tagLVACCINDEX *
0x180031036  mov     [rdi], eax
0x180031038  mov     r13, r9
0x18003103b  mov     r14, rcx
0x18003103e  mov     [rbp+47h+var_88], rdi
0x180031042  mov     [rbp+47h+var_60], rax
0x180031046  mov     [rbp+47h+var_58], eax
0x180031049  call    ?_ValidateChild@CListViewV6@@AEAAJPEAUtagVARIANT@@PEAUtagLVACCINDEX@@@Z; CListViewV6::_ValidateChild(tagVARIANT *,tagLVACCINDEX *)
0x18003104e  mov     ebx, eax
0x180031050  test    eax, eax
0x180031052  js      loc_18003118E
0x180031058  cmp     dword ptr [rsi+8], 0
0x18003105c  jz      short loc_180031073
0x18003105e  lea     rdx, [rbp+47h+var_60]; struct tagLVACCINDEX *
0x180031062  call    ?_IsItem@CListViewV6@@AEAAHPEBUtagLVACCINDEX@@@Z; CListViewV6::_IsItem(tagLVACCINDEX const *)
0x180031067  test    eax, eax
0x180031069  jz      short loc_1800310B8
0x18003106b  mov     eax, dword ptr [rbp+47h+var_60]
0x18003106e  inc     eax
0x180031070  mov     [rsi+8], eax
0x180031073  mov     rcx, [r14+80h]
0x18003107a  lea     rdx, [rbp+47h+Buffer]
0x18003107e  movups  xmm0, xmmword ptr [rsi]
0x180031081  mov     r9, r13
0x180031084  mov     [rsp+0D0h+var_A8], rdx
0x180031089  movsd   xmm1, qword ptr [rsi+10h]
0x18003108e  mov     r8, r12
0x180031091  mov     rax, [rcx]
0x180031094  mov     rdx, r15
0x180031097  movaps  [rbp+47h+Buffer], xmm0
0x18003109b  movsd   [rbp+47h+var_70], xmm1
0x1800310a0  mov     [rsp+0D0h+lpNumberOfBytesRead], rdi
0x1800310a5  mov     rax, [rax+0B0h]
0x1800310ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310b1  mov     ebx, eax
0x1800310b3  jmp     loc_18003118E
0x1800310b8  mov     rdx, [r14+50h]; HWND
0x1800310bc  lea     r8, [rbp+47h+hProcess]; void **
0x1800310c0  mov     ecx, 10h; dwSize
0x1800310c5  mov     [rbp+47h+hProcess], 0
0x1800310cd  mov     ebx, 8007000Eh
0x1800310d2  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x1800310d7  mov     rdi, rax
0x1800310da  test    rax, rax
0x1800310dd  jz      loc_18003118E
0x1800310e3  movsxd  rcx, dword ptr [rsi+8]
0x1800310e7  lea     rax, [rbp+47h+Buffer]
0x1800310eb  mov     r8, [r14+50h]; HWND
0x1800310ef  mov     r9d, 10C5h; unsigned int
0x1800310f5  mov     [rsp+0D0h+var_A0], rax; __int64 *
0x1800310fa  xor     edx, edx; bool
0x1800310fc  mov     [rsp+0D0h+var_A8], rdi; __int64
0x180031101  mov     [rsp+0D0h+lpNumberOfBytesRead], rcx; unsigned __int64
0x180031106  mov     rcx, r14; this
0x180031109  mov     qword ptr [rbp+47h+Buffer], 0
0x180031111  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180031116  mov     ebx, eax
0x180031118  test    eax, eax
0x18003111a  js      short loc_180031182
0x18003111c  cmp     qword ptr [rbp+47h+Buffer], 0
0x180031121  mov     ebx, 1
0x180031126  jz      short loc_180031182
0x180031128  mov     rcx, [rbp+47h+hProcess]; hProcess
0x18003112c  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x180031130  xor     ebx, ebx
0x180031132  xorps   xmm0, xmm0
0x180031135  mov     rdx, rdi; lpBaseAddress
0x180031138  mov     [rsp+0D0h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18003113d  movups  [rbp+47h+Buffer], xmm0
0x180031141  lea     r9d, [rbx+10h]; nSize
0x180031145  call    cs:__imp_ReadProcessMemory
0x18003114b  mov     rcx, [r14+50h]; hWndFrom
0x18003114f  lea     r9d, [rbx+2]; cPoints
0x180031153  lea     r8, [rbp+47h+Buffer]; lpPoints
0x180031157  xor     edx, edx; hWndTo
0x180031159  call    cs:__imp_MapWindowPoints
0x18003115f  mov     ecx, dword ptr [rbp+47h+Buffer]
0x180031162  mov     r8d, dword ptr [rbp+47h+Buffer+4]
0x180031166  mov     eax, dword ptr [rbp+47h+Buffer+8]
0x180031169  sub     eax, ecx
0x18003116b  mov     [r15], ecx
0x18003116e  mov     rcx, [rbp+47h+var_88]
0x180031172  mov     [r12], r8d
0x180031176  mov     [r13+0], eax
0x18003117a  mov     eax, dword ptr [rbp+47h+Buffer+0Ch]
0x18003117d  sub     eax, r8d
0x180031180  mov     [rcx], eax
0x180031182  mov     rdx, [rbp+47h+hProcess]; hProcess
0x180031186  mov     rcx, rdi; lpAddress
0x180031189  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18003118e  mov     eax, ebx
0x180031190  mov     rcx, [rbp+47h+var_50]
0x180031194  xor     rcx, rsp; StackCookie
0x180031197  call    __security_check_cookie
0x18003119c  add     rsp, 98h
0x1800311a3  pop     r15
0x1800311a5  pop     r14
0x1800311a7  pop     r13
0x1800311a9  pop     r12
0x1800311ab  pop     rdi
0x1800311ac  pop     rsi
0x1800311ad  pop     rbx
0x1800311ae  pop     rbp
0x1800311af  retn
```
