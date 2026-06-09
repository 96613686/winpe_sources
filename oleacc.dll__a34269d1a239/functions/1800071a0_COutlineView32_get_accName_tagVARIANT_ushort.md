# COutlineView32::get_accName(tagVARIANT,ushort * *)

- ea: `0x1800071a0`
- end: `0x1800073a6`
- name: `?get_accName@COutlineView32@@UEAAJUtagVARIANT@@PEAPEAG@Z`
- size: `518`
- prototype: `__int64 __fastcall(COutlineView32 *__hidden this, struct tagVARIANT *__struct_ptr, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800071a0`
- `0x180007530`
- `0x180007700`
- `0x18000771c`
- `0x18000ccd0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180007356`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180007356`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x180007301`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x180007301`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18000727e`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180007298`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800072b2`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800072d3`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18000727e`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180007298`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800072b2`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800072d3`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x18000722b`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x18000722b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000730a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000730a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007334`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007313`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007313`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007246`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007246`
- `OLEAUT32!__imp_SysAllocString` at `0x180007365`
- `OLEAUT32!__imp_SysAllocString` at `0x180007365`
- `USER32!SendMessageW` at `0x1800072e8`
- `USER32!SendMessageW` at `0x1800072e8`

## pseudocode

```c
int __fastcall COutlineView32::get_accName(HWND *this, struct tagVARIANT *a2, unsigned __int16 **a3)
{
  HWND v5; // rax
  WPARAM Lo; // rdx
  void *ProcessHandleFromHwnd; // rax
  void *v9; // rbx
  char *v10; // r14
  _WORD *v11; // rax
  _WORD *v12; // rdi
  IRecordInfo *pRecInfo; // xmm1_8
  struct tagVARIANT v15; // [rsp+30h] [rbp-20h] BYREF
  int Buffer; // [rsp+90h] [rbp+40h] BYREF
  LPCVOID lpBaseAddress; // [rsp+A0h] [rbp+50h] BYREF
  struct _TREEITEM *v18; // [rsp+A8h] [rbp+58h] BYREF

  *a3 = 0;
  v5 = *this;
  lpBaseAddress = 0;
  if ( !(*((unsigned int (__fastcall **)(HWND *))v5 + 30))(this) )
    return -2147024809;
  Lo = a2->cyVal.Lo;
  if ( !(_DWORD)Lo )
  {
    pRecInfo = a2->pRecInfo;
    *(_OWORD *)&v15.vt = *(_OWORD *)&a2->vt;
    v15.pRecInfo = pRecInfo;
    return CClient::get_accName((CClient *)this, &v15, a3);
  }
  v18 = TVItemFromChildID(this[10], Lo);
  if ( !v18 )
    return -2147024809;
  ProcessHandleFromHwnd = (void *)GetProcessHandleFromHwnd(this[10]);
  v9 = ProcessHandleFromHwnd;
  if ( !ProcessHandleFromHwnd )
    return -2147024882;
  v10 = (char *)VirtualAllocEx(ProcessHandleFromHwnd, 0, 0x23Au, 0x1000u, 4u);
  if ( !v10 )
  {
    CloseHandle(v9);
    return -2147024882;
  }
  v11 = LocalAlloc(0x40u, 0x202u);
  v12 = v11;
  if ( !v11 )
  {
    SharedFree(v10, v9);
    return -2147024882;
  }
  *v11 = 0;
  Buffer = 1;
  lpBaseAddress = v10 + 56;
  WriteProcessMemory(v9, v10, &Buffer, 4u, 0);
  WriteProcessMemory(v9, v10 + 8, &v18, 8u, 0);
  WriteProcessMemory(v9, v10 + 24, &lpBaseAddress, 8u, 0);
  Buffer = 256;
  WriteProcessMemory(v9, v10 + 32, &Buffer, 4u, 0);
  if ( (unsigned int)SendMessageW(this[10], 0x113Eu, 0, (LPARAM)v10) )
  {
    ReadProcessMemory(v9, lpBaseAddress, v12, 0x202u, 0);
    if ( *v12 )
      *a3 = SysAllocString(v12);
  }
  VirtualFreeEx(v9, v10, 0, 0x8000u);
  CloseHandle(v9);
  LocalFree(v12);
  return *a3 == 0;
}

```

## disassembly

```asm
0x1800071a0  push    rbp
0x1800071a2  push    rbx
0x1800071a3  push    rsi
0x1800071a4  push    rdi
0x1800071a5  push    r13
0x1800071a7  push    r14
0x1800071a9  push    r15
0x1800071ab  mov     rbp, rsp
0x1800071ae  sub     rsp, 50h
0x1800071b2  xor     r13d, r13d
0x1800071b5  mov     r15, r8
0x1800071b8  mov     [r8], r13
0x1800071bb  mov     rbx, rdx
0x1800071be  mov     rax, [rcx]
0x1800071c1  mov     rsi, rcx
0x1800071c4  mov     [rbp+lpBaseAddress], r13
0x1800071c8  mov     rax, [rax+0F0h]
0x1800071cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071d4  test    eax, eax
0x1800071d6  jz      loc_180007370
0x1800071dc  mov     edx, [rbx+8]; wParam
0x1800071df  test    edx, edx
0x1800071e1  jz      loc_180007377
0x1800071e7  mov     rcx, [rsi+50h]; HWND
0x1800071eb  call    ?TVItemFromChildID@@YAPEAU_TREEITEM@@PEAUHWND__@@K@Z; TVItemFromChildID(HWND__ *,ulong)
0x1800071f0  mov     [rbp+arg_18], rax
0x1800071f4  test    rax, rax
0x1800071f7  jz      loc_180007370
0x1800071fd  mov     rcx, [rsi+50h]
0x180007201  call    GetProcessHandleFromHwnd
0x180007206  mov     rbx, rax
0x180007209  test    rax, rax
0x18000720c  jz      loc_18000733A
0x180007212  xor     edx, edx; lpAddress
0x180007214  mov     [rsp+50h+flProtect], 4; flProtect
0x18000721c  mov     r9d, 1000h; flAllocationType
0x180007222  mov     r8d, 23Ah; dwSize
0x180007228  mov     rcx, rax; hProcess
0x18000722b  call    cs:__imp_VirtualAllocEx
0x180007231  mov     r14, rax
0x180007234  test    rax, rax
0x180007237  jz      loc_180007331
0x18000723d  mov     edx, 202h; uBytes
0x180007242  lea     ecx, [r13+40h]; uFlags
0x180007246  call    cs:__imp_LocalAlloc
0x18000724c  mov     rdi, rax
0x18000724f  test    rax, rax
0x180007252  jz      loc_180007399
0x180007258  mov     [rax], r13w
0x18000725c  lea     r9d, [r13+4]; nSize
0x180007260  lea     rax, [r14+38h]
0x180007264  mov     [rbp+Buffer], 1
0x18000726b  lea     r8, [rbp+Buffer]; lpBuffer
0x18000726f  mov     [rbp+lpBaseAddress], rax
0x180007273  mov     rdx, r14; lpBaseAddress
0x180007276  mov     qword ptr [rsp+50h+flProtect], r13; lpNumberOfBytesWritten
0x18000727b  mov     rcx, rbx; hProcess
0x18000727e  call    cs:__imp_WriteProcessMemory
0x180007284  lea     rdx, [r14+8]; lpBaseAddress
0x180007288  mov     qword ptr [rsp+50h+flProtect], r13; lpNumberOfBytesWritten
0x18000728d  lea     r9d, [r13+8]; nSize
0x180007291  mov     rcx, rbx; hProcess
0x180007294  lea     r8, [rbp+arg_18]; lpBuffer
0x180007298  call    cs:__imp_WriteProcessMemory
0x18000729e  lea     rdx, [r14+18h]; lpBaseAddress
0x1800072a2  mov     qword ptr [rsp+50h+flProtect], r13; lpNumberOfBytesWritten
0x1800072a7  lea     r9d, [r13+8]; nSize
0x1800072ab  mov     rcx, rbx; hProcess
0x1800072ae  lea     r8, [rbp+lpBaseAddress]; lpBuffer
0x1800072b2  call    cs:__imp_WriteProcessMemory
0x1800072b8  lea     rdx, [r14+20h]; lpBaseAddress
0x1800072bc  mov     [rbp+Buffer], 100h
0x1800072c3  lea     r9d, [r13+4]; nSize
0x1800072c7  mov     qword ptr [rsp+50h+flProtect], r13; lpNumberOfBytesWritten
0x1800072cc  lea     r8, [rbp+Buffer]; lpBuffer
0x1800072d0  mov     rcx, rbx; hProcess
0x1800072d3  call    cs:__imp_WriteProcessMemory
0x1800072d9  mov     rcx, [rsi+50h]; hWnd
0x1800072dd  mov     r9, r14; lParam
0x1800072e0  xor     r8d, r8d; wParam
0x1800072e3  mov     edx, 113Eh; Msg
0x1800072e8  call    cs:__imp_SendMessageW
0x1800072ee  test    eax, eax
0x1800072f0  jnz     short loc_180007341
0x1800072f2  mov     r9d, 8000h; dwFreeType
0x1800072f8  xor     r8d, r8d; dwSize
0x1800072fb  mov     rdx, r14; lpAddress
0x1800072fe  mov     rcx, rbx; hProcess
0x180007301  call    cs:__imp_VirtualFreeEx
0x180007307  mov     rcx, rbx; hObject
0x18000730a  call    cs:__imp_CloseHandle
0x180007310  mov     rcx, rdi; hMem
0x180007313  call    cs:__imp_LocalFree
0x180007319  cmp     [r15], r13
0x18000731c  mov     eax, r13d
0x18000731f  setz    al
0x180007322  add     rsp, 50h
0x180007326  pop     r15
0x180007328  pop     r14
0x18000732a  pop     r13
0x18000732c  pop     rdi
0x18000732d  pop     rsi
0x18000732e  pop     rbx
0x18000732f  pop     rbp
0x180007330  retn
0x180007331  mov     rcx, rbx; hObject
0x180007334  call    cs:__imp_CloseHandle
0x18000733a  mov     eax, 8007000Eh
0x18000733f  jmp     short loc_180007322
0x180007341  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180007345  mov     r9d, 202h; nSize
0x18000734b  mov     r8, rdi; lpBuffer
0x18000734e  mov     qword ptr [rsp+50h+flProtect], r13; lpNumberOfBytesRead
0x180007353  mov     rcx, rbx; hProcess
0x180007356  call    cs:__imp_ReadProcessMemory
0x18000735c  cmp     [rdi], r13w
0x180007360  jz      short loc_1800072F2
0x180007362  mov     rcx, rdi; psz
0x180007365  call    cs:__imp_SysAllocString
0x18000736b  mov     [r15], rax
0x18000736e  jmp     short loc_1800072F2
0x180007370  mov     eax, 80070057h
0x180007375  jmp     short loc_180007322
0x180007377  movups  xmm0, xmmword ptr [rbx]
0x18000737a  lea     rdx, [rbp+var_20]; struct tagVARIANT
0x18000737e  mov     r8, r15; unsigned __int16 **
0x180007381  movsd   xmm1, qword ptr [rbx+10h]
0x180007386  mov     rcx, rsi; this
0x180007389  movaps  xmmword ptr [rbp+var_20], xmm0
0x18000738d  movsd   qword ptr [rbp+var_20+10h], xmm1
0x180007392  call    ?get_accName@CClient@@UEAAJUtagVARIANT@@PEAPEAG@Z; CClient::get_accName(tagVARIANT,ushort * *)
0x180007397  jmp     short loc_180007322
0x180007399  mov     rdx, rbx; hProcess
0x18000739c  mov     rcx, r14; lpAddress
0x18000739f  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800073a4  jmp     short loc_18000733A
```
