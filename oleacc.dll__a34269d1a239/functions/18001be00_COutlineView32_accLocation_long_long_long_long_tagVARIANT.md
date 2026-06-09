# COutlineView32::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x18001be00`
- end: `0x18001bfed`
- name: `?accLocation@COutlineView32@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `493`
- prototype: `__int64 __fastcall(COutlineView32 *__hidden this, int *, int *, int *, int *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800056a4`
- `0x180007530`
- `0x180007700`
- `0x18000771c`
- `0x18001be00`
- `0x18001c430`
- `0x18001e4c0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001bf78`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001bf78`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18001bf15`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18001bf15`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x18001bee2`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x18001bee2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bef3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bef3`
- `USER32!MapWindowPoints` at `0x18001bf8e`
- `USER32!MapWindowPoints` at `0x18001bf8e`

## pseudocode

```c
__int64 __fastcall COutlineView32::accLocation(HWND *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  HWND v10; // rax
  WPARAM Lo; // rdx
  IRecordInfo *pRecInfo; // xmm1_8
  void *ProcessHandleFromHwnd; // rax
  void *v15; // rbx
  void *v16; // rax
  void *v17; // rsi
  HWND v18; // r8
  int v19; // r14d
  ULONG Hi32; // edx
  int v21; // eax
  int *v22; // rcx
  struct _TREEITEM *Buffer; // [rsp+40h] [rbp-39h] BYREF
  int *v24; // [rsp+48h] [rbp-31h]
  struct tagVARIANT Points; // [rsp+50h] [rbp-29h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v10 = *this;
  v24 = a5;
  if ( !(*((unsigned int (__fastcall **)(HWND *, struct tagVARIANT *))v10 + 30))(this, a6) )
    return 2147942487LL;
  Lo = a6->cyVal.Lo;
  if ( !(_DWORD)Lo )
  {
    pRecInfo = a6->pRecInfo;
    *(_OWORD *)&Points.vt = *(_OWORD *)&a6->vt;
    Points.pRecInfo = pRecInfo;
    return CClient::accLocation((CClient *)this, a2, a3, a4, a5, &Points);
  }
  Buffer = TVItemFromChildID(this[10], Lo);
  if ( !Buffer )
    return 2147942487LL;
  ProcessHandleFromHwnd = (void *)GetProcessHandleFromHwnd(this[10]);
  v15 = ProcessHandleFromHwnd;
  if ( !ProcessHandleFromHwnd )
    return 2147942414LL;
  v16 = VirtualAllocEx(ProcessHandleFromHwnd, 0, 0x10u, 0x1000u, 4u);
  v17 = v16;
  if ( !v16 )
  {
    CloseHandle(v15);
    return 2147942414LL;
  }
  WriteProcessMemory(v15, v16, &Buffer, 8u, 0);
  v18 = this[10];
  *(_QWORD *)&Points.vt = 0;
  v19 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, v18, 0x1104u, 1u, (__int64)v17, (__int64 *)&Points);
  if ( v19 >= 0 )
  {
    if ( *(_QWORD *)&Points.vt )
    {
      *(_OWORD *)&Points.vt = 0;
      ReadProcessMemory(v15, v17, &Points, 0x10u, 0);
      MapWindowPoints(this[10], 0, (LPPOINT)&Points, 2u);
      Hi32 = Points.decVal.Hi32;
      v21 = Points.lVal - *(_DWORD *)&Points.vt;
      *a2 = *(_DWORD *)&Points.vt;
      v22 = v24;
      *a3 = Hi32;
      *a4 = v21;
      *v22 = Points.cyVal.Hi - Hi32;
    }
    v19 = 0;
  }
  SharedFree(v17, v15);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18001be00  push    rbp
0x18001be02  push    rbx
0x18001be03  push    rsi
0x18001be04  push    rdi
0x18001be05  push    r12
0x18001be07  push    r13
0x18001be09  push    r14
0x18001be0b  push    r15
0x18001be0d  lea     rbp, [rsp-0Fh]
0x18001be12  sub     rsp, 88h
0x18001be19  mov     rax, cs:__security_cookie
0x18001be20  xor     rax, rsp
0x18001be23  mov     [rbp+47h+var_50], rax
0x18001be27  mov     rsi, [rbp+47h+arg_20]
0x18001be2b  xor     r14d, r14d
0x18001be2e  mov     rbx, [rbp+47h+arg_28]
0x18001be32  mov     r15, rdx
0x18001be35  mov     [rdx], r14d
0x18001be38  mov     r13, r9
0x18001be3b  mov     [r8], r14d
0x18001be3e  mov     rdx, rbx
0x18001be41  mov     [r9], r14d
0x18001be44  mov     r12, r8
0x18001be47  mov     [rsi], r14d
0x18001be4a  mov     rdi, rcx
0x18001be4d  mov     rax, [rcx]
0x18001be50  mov     [rbp+47h+var_78], rsi
0x18001be54  mov     rax, [rax+0F0h]
0x18001be5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be60  test    eax, eax
0x18001be62  jz      loc_18001BFC8
0x18001be68  mov     edx, [rbx+8]; wParam
0x18001be6b  test    edx, edx
0x18001be6d  jnz     short loc_18001BEA4
0x18001be6f  movups  xmm0, xmmword ptr [rbx]
0x18001be72  lea     rax, [rbp+47h+Points]
0x18001be76  mov     r9, r13; int *
0x18001be79  movsd   xmm1, qword ptr [rbx+10h]
0x18001be7e  mov     r8, r12; int *
0x18001be81  mov     [rsp+0C0h+var_98], rax; struct tagVARIANT *
0x18001be86  mov     rdx, r15; int *
0x18001be89  mov     rcx, rdi; this
0x18001be8c  movaps  xmmword ptr [rbp+47h+Points.x], xmm0
0x18001be90  movsd   [rbp+47h+var_60], xmm1
0x18001be95  mov     qword ptr [rsp+0C0h+flProtect], rsi; int *
0x18001be9a  call    ?accLocation@CClient@@UEAAJPEAJ000UtagVARIANT@@@Z; CClient::accLocation(long *,long *,long *,long *,tagVARIANT)
0x18001be9f  jmp     loc_18001BFCD
0x18001bea4  mov     rcx, [rdi+50h]; HWND
0x18001bea8  call    ?TVItemFromChildID@@YAPEAU_TREEITEM@@PEAUHWND__@@K@Z; TVItemFromChildID(HWND__ *,ulong)
0x18001bead  mov     [rbp+47h+Buffer], rax
0x18001beb1  test    rax, rax
0x18001beb4  jz      loc_18001BFC8
0x18001beba  mov     rcx, [rdi+50h]
0x18001bebe  call    GetProcessHandleFromHwnd
0x18001bec3  mov     rbx, rax
0x18001bec6  test    rax, rax
0x18001bec9  jz      short loc_18001BEF9
0x18001becb  xor     edx, edx; lpAddress
0x18001becd  mov     [rsp+0C0h+flProtect], 4; flProtect
0x18001bed5  mov     r9d, 1000h; flAllocationType
0x18001bedb  mov     rcx, rax; hProcess
0x18001bede  lea     r8d, [rdx+10h]; dwSize
0x18001bee2  call    cs:__imp_VirtualAllocEx
0x18001bee8  mov     rsi, rax
0x18001beeb  mov     rcx, rbx; hProcess
0x18001beee  test    rax, rax
0x18001bef1  jnz     short loc_18001BF03
0x18001bef3  call    cs:__imp_CloseHandle
0x18001bef9  mov     eax, 8007000Eh
0x18001befe  jmp     loc_18001BFCD
0x18001bf03  mov     r9d, 8; nSize
0x18001bf09  mov     qword ptr [rsp+0C0h+flProtect], r14; lpNumberOfBytesWritten
0x18001bf0e  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x18001bf12  mov     rdx, rsi; lpBaseAddress
0x18001bf15  call    cs:__imp_WriteProcessMemory
0x18001bf1b  mov     r8, [rdi+50h]; HWND
0x18001bf1f  lea     rax, [rbp+47h+Points]
0x18001bf23  mov     [rsp+0C0h+var_90], rax; __int64 *
0x18001bf28  mov     r9d, 1104h; unsigned int
0x18001bf2e  mov     [rsp+0C0h+var_98], rsi; __int64
0x18001bf33  xor     edx, edx; bool
0x18001bf35  mov     rcx, rdi; this
0x18001bf38  mov     qword ptr [rsp+0C0h+flProtect], 1; unsigned __int64
0x18001bf41  mov     qword ptr [rbp+47h+Points.x], r14
0x18001bf45  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18001bf4a  mov     r14d, eax
0x18001bf4d  test    eax, eax
0x18001bf4f  js      short loc_18001BFB8
0x18001bf51  cmp     qword ptr [rbp+47h+Points.x], 0
0x18001bf56  jz      short loc_18001BFB5
0x18001bf58  xorps   xmm0, xmm0
0x18001bf5b  mov     qword ptr [rsp+0C0h+flProtect], 0; lpNumberOfBytesRead
0x18001bf64  mov     r9d, 10h; nSize
0x18001bf6a  lea     r8, [rbp+47h+Points]; lpBuffer
0x18001bf6e  mov     rdx, rsi; lpBaseAddress
0x18001bf71  mov     rcx, rbx; hProcess
0x18001bf74  movups  xmmword ptr [rbp+47h+Points.x], xmm0
0x18001bf78  call    cs:__imp_ReadProcessMemory
0x18001bf7e  mov     rcx, [rdi+50h]; hWndFrom
0x18001bf82  lea     r8, [rbp+47h+Points]; lpPoints
0x18001bf86  mov     r9d, 2; cPoints
0x18001bf8c  xor     edx, edx; hWndTo
0x18001bf8e  call    cs:__imp_MapWindowPoints
0x18001bf94  mov     ecx, [rbp+47h+Points.x]
0x18001bf97  mov     edx, [rbp+47h+Points.y]
0x18001bf9a  mov     eax, [rbp+47h+Points.x+8]
0x18001bf9d  sub     eax, ecx
0x18001bf9f  mov     [r15], ecx
0x18001bfa2  mov     rcx, [rbp+47h+var_78]
0x18001bfa6  mov     [r12], edx
0x18001bfaa  mov     [r13+0], eax
0x18001bfae  mov     eax, [rbp+47h+Points.y+8]
0x18001bfb1  sub     eax, edx
0x18001bfb3  mov     [rcx], eax
0x18001bfb5  xor     r14d, r14d
0x18001bfb8  mov     rdx, rbx; hProcess
0x18001bfbb  mov     rcx, rsi; lpAddress
0x18001bfbe  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18001bfc3  mov     eax, r14d
0x18001bfc6  jmp     short loc_18001BFCD
0x18001bfc8  mov     eax, 80070057h
0x18001bfcd  mov     rcx, [rbp+47h+var_50]
0x18001bfd1  xor     rcx, rsp; StackCookie
0x18001bfd4  call    __security_check_cookie
0x18001bfd9  add     rsp, 88h
0x18001bfe0  pop     r15
0x18001bfe2  pop     r14
0x18001bfe4  pop     r13
0x18001bfe6  pop     r12
0x18001bfe8  pop     rdi
0x18001bfe9  pop     rsi
0x18001bfea  pop     rbx
0x18001bfeb  pop     rbp
0x18001bfec  retn
```
