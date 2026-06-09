# TVGetImageIndex(HWND__ *,_TREEITEM *,int * const)

- ea: `0x180007598`
- end: `0x1800076f3`
- name: `?TVGetImageIndex@@YAHPEAUHWND__@@PEAU_TREEITEM@@QEAH@Z`
- size: `347`
- prototype: `__int64 __fastcall(HWND hWnd, struct _TREEITEM *, int *const)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800048c0`
- `0x1800073b0`
- `0x18003c2c0`

## callees

- `0x180007598`
- `0x180007700`
- `0x18000771c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000767b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180007699`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000767b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180007699`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180007612`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180007631`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180007612`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180007631`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x1800075e1`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x1800075e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076e9`
- `USER32!SendMessageW` at `0x180007645`
- `USER32!SendMessageW` at `0x180007645`

## pseudocode

```c
__int64 __fastcall TVGetImageIndex(HWND hWnd, struct _TREEITEM *a2, int *const a3)
{
  void *ProcessHandleFromHwnd; // rax
  void *v6; // rbx
  void *v7; // rax
  LPARAM v8; // rdi
  unsigned int v9; // esi
  unsigned int v10; // ecx
  _DWORD v12[10]; // [rsp+30h] [rbp-28h] BYREF
  struct _TREEITEM *v13; // [rsp+68h] [rbp+10h] BYREF
  int Buffer; // [rsp+78h] [rbp+20h] BYREF

  v13 = a2;
  ProcessHandleFromHwnd = (void *)GetProcessHandleFromHwnd(hWnd);
  v6 = ProcessHandleFromHwnd;
  if ( !ProcessHandleFromHwnd )
    return 0;
  v7 = VirtualAllocEx(ProcessHandleFromHwnd, 0, 0x38u, 0x1000u, 4u);
  v8 = (LPARAM)v7;
  if ( !v7 )
  {
    CloseHandle(v6);
    return 0;
  }
  Buffer = 10;
  WriteProcessMemory(v6, v7, &Buffer, 4u, 0);
  WriteProcessMemory(v6, (LPVOID)(v8 + 8), &v13, 8u, 0);
  if ( (unsigned int)SendMessageW(hWnd, 0x113Eu, 0, v8) )
  {
    Buffer = 0;
    v12[0] = 0;
    ReadProcessMemory(v6, (LPCVOID)(v8 + 36), &Buffer, 4u, 0);
    ReadProcessMemory(v6, (LPCVOID)(v8 + 16), v12, 4u, 0);
    v9 = 1;
    v10 = v12[0];
    *a3 = Buffer;
    a3[2] = (v10 >> 8) & 0xF;
    a3[1] = (unsigned __int16)v10 >> 12;
  }
  else
  {
    v9 = 0;
  }
  SharedFree((void *)v8, v6);
  return v9;
}

```

## disassembly

```asm
0x180007598  mov     [rsp+arg_0], rbx
0x18000759d  mov     [rsp+arg_10], rsi
0x1800075a2  mov     [rsp+arg_8], rdx
0x1800075a7  push    rdi
0x1800075a8  push    r14
0x1800075aa  push    r15
0x1800075ac  sub     rsp, 40h
0x1800075b0  mov     r14, r8
0x1800075b3  mov     rsi, rcx
0x1800075b6  call    GetProcessHandleFromHwnd
0x1800075bb  mov     rbx, rax
0x1800075be  test    rax, rax
0x1800075c1  jz      loc_1800076EF
0x1800075c7  mov     r15d, 4
0x1800075cd  xor     edx, edx; lpAddress
0x1800075cf  mov     r9d, 1000h; flAllocationType
0x1800075d5  mov     [rsp+58h+flProtect], r15d; flProtect
0x1800075da  mov     rcx, rax; hProcess
0x1800075dd  lea     r8d, [r15+34h]; dwSize
0x1800075e1  call    cs:__imp_VirtualAllocEx
0x1800075e7  mov     rdi, rax
0x1800075ea  mov     rcx, rbx; hObject
0x1800075ed  test    rax, rax
0x1800075f0  jz      loc_1800076E9
0x1800075f6  mov     r9d, r15d; nSize
0x1800075f9  mov     [rsp+58h+Buffer], 0Ah
0x180007601  lea     r8, [rsp+58h+Buffer]; lpBuffer
0x180007606  mov     qword ptr [rsp+58h+flProtect], 0; lpNumberOfBytesWritten
0x18000760f  mov     rdx, rax; lpBaseAddress
0x180007612  call    cs:__imp_WriteProcessMemory
0x180007618  lea     rdx, [rdi+8]; lpBaseAddress
0x18000761c  mov     qword ptr [rsp+58h+flProtect], 0; lpNumberOfBytesWritten
0x180007625  lea     r9d, [r15+4]; nSize
0x180007629  mov     rcx, rbx; hProcess
0x18000762c  lea     r8, [rsp+58h+arg_8]; lpBuffer
0x180007631  call    cs:__imp_WriteProcessMemory
0x180007637  mov     r9, rdi; lParam
0x18000763a  xor     r8d, r8d; wParam
0x18000763d  mov     edx, 113Eh; Msg
0x180007642  mov     rcx, rsi; hWnd
0x180007645  call    cs:__imp_SendMessageW
0x18000764b  test    eax, eax
0x18000764d  jz      loc_1800076E5
0x180007653  lea     rdx, [rdi+24h]; lpBaseAddress
0x180007657  mov     [rsp+58h+Buffer], 0
0x18000765f  mov     r9d, r15d; nSize
0x180007662  mov     [rsp+58h+var_28], 0
0x18000766a  lea     r8, [rsp+58h+Buffer]; lpBuffer
0x18000766f  mov     qword ptr [rsp+58h+flProtect], 0; lpNumberOfBytesRead
0x180007678  mov     rcx, rbx; hProcess
0x18000767b  call    cs:__imp_ReadProcessMemory
0x180007681  lea     rdx, [rdi+10h]; lpBaseAddress
0x180007685  mov     qword ptr [rsp+58h+flProtect], 0; lpNumberOfBytesRead
0x18000768e  mov     r9d, r15d; nSize
0x180007691  lea     r8, [rsp+58h+var_28]; lpBuffer
0x180007696  mov     rcx, rbx; hProcess
0x180007699  call    cs:__imp_ReadProcessMemory
0x18000769f  mov     eax, [rsp+58h+Buffer]
0x1800076a3  lea     esi, [r15-3]
0x1800076a7  mov     ecx, [rsp+58h+var_28]
0x1800076ab  mov     [r14], eax
0x1800076ae  mov     eax, ecx
0x1800076b0  shr     eax, 8
0x1800076b3  and     eax, 0Fh
0x1800076b6  shr     ecx, 0Ch
0x1800076b9  and     ecx, 0Fh
0x1800076bc  mov     [r14+8], eax
0x1800076c0  mov     [r14+4], ecx
0x1800076c4  mov     rdx, rbx; hProcess
0x1800076c7  mov     rcx, rdi; lpAddress
0x1800076ca  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800076cf  mov     eax, esi
0x1800076d1  mov     rbx, [rsp+58h+arg_0]
0x1800076d6  mov     rsi, [rsp+58h+arg_10]
0x1800076db  add     rsp, 40h
0x1800076df  pop     r15
0x1800076e1  pop     r14
0x1800076e3  pop     rdi
0x1800076e4  retn
0x1800076e5  xor     esi, esi
0x1800076e7  jmp     short loc_1800076C4
0x1800076e9  call    cs:__imp_CloseHandle
0x1800076ef  xor     eax, eax
0x1800076f1  jmp     short loc_1800076D1
```
