# CToolBar32::GetItemData(int,_TBBUTTON *)

- ea: `0x1800065b4`
- end: `0x1800066a4`
- name: `?GetItemData@CToolBar32@@QEAAHHPEAU_TBBUTTON@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(CToolBar32 *__hidden this, int, struct _TBBUTTON *)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180005454`
- `0x18000c8a0`
- `0x18001b8c0`
- `0x1800435a0`
- `0x180043930`
- `0x180044140`
- `0x1800443c0`

## callees

- `0x1800056a4`
- `0x1800065b4`
- `0x180007700`
- `0x18000771c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000667f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000667f`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x1800065f8`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x1800065f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006609`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006609`

## pseudocode

```c
__int64 __fastcall CToolBar32::GetItemData(CToolBar32 *this, int a2, struct _TBBUTTON *a3)
{
  unsigned int v6; // esi
  void *ProcessHandleFromHwnd; // rax
  void *v8; // rbx
  void *v9; // rdi
  HWND v10; // r8
  __int64 v12; // [rsp+80h] [rbp+8h] BYREF

  v6 = 0;
  ProcessHandleFromHwnd = (void *)GetProcessHandleFromHwnd(*((_QWORD *)this + 10));
  v8 = ProcessHandleFromHwnd;
  if ( ProcessHandleFromHwnd )
  {
    v9 = VirtualAllocEx(ProcessHandleFromHwnd, 0, 0x24u, 0x1000u, 4u);
    if ( v9 )
    {
      v10 = (HWND)*((_QWORD *)this + 10);
      v12 = 0;
      if ( CAccessible::AccSendMessageTimeout(this, 0, v10, 0x417u, a2 - 1, (__int64)v9, &v12) < 0 )
      {
        SharedFree(v9, v8);
        return 0;
      }
      if ( v12 )
      {
        ReadProcessMemory(v8, v9, a3, 0x20u, 0);
        v6 = 1;
      }
      SharedFree(v9, v8);
    }
    else
    {
      CloseHandle(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800065b4  push    rbx
0x1800065b6  push    rbp
0x1800065b7  push    rsi
0x1800065b8  push    rdi
0x1800065b9  push    r14
0x1800065bb  push    r15
0x1800065bd  sub     rsp, 48h
0x1800065c1  mov     rbp, rcx
0x1800065c4  mov     r14, r8
0x1800065c7  mov     rcx, [rcx+50h]
0x1800065cb  mov     r15d, edx
0x1800065ce  xor     esi, esi
0x1800065d0  call    GetProcessHandleFromHwnd
0x1800065d5  mov     rbx, rax
0x1800065d8  test    rax, rax
0x1800065db  jz      loc_180006695
0x1800065e1  xor     edx, edx; lpAddress
0x1800065e3  mov     [rsp+78h+flProtect], 4; flProtect
0x1800065eb  mov     r9d, 1000h; flAllocationType
0x1800065f1  lea     r8d, [rsi+24h]; dwSize
0x1800065f5  mov     rcx, rax; hProcess
0x1800065f8  call    cs:__imp_VirtualAllocEx
0x1800065fe  mov     rdi, rax
0x180006601  test    rax, rax
0x180006604  jnz     short loc_180006614
0x180006606  mov     rcx, rbx; hObject
0x180006609  call    cs:__imp_CloseHandle
0x18000660f  jmp     loc_180006695
0x180006614  mov     r8, [rbp+50h]; HWND
0x180006618  lea     eax, [r15-1]
0x18000661c  movsxd  rcx, eax
0x18000661f  mov     r9d, 417h; unsigned int
0x180006625  lea     rax, [rsp+78h+arg_0]
0x18000662d  mov     [rsp+78h+arg_0], rsi
0x180006635  mov     [rsp+78h+var_48], rax; __int64 *
0x18000663a  xor     edx, edx; bool
0x18000663c  mov     [rsp+78h+var_50], rdi; __int64
0x180006641  mov     qword ptr [rsp+78h+flProtect], rcx; unsigned __int64
0x180006646  mov     rcx, rbp; this
0x180006649  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18000664e  test    eax, eax
0x180006650  jns     short loc_180006661
0x180006652  mov     rdx, rbx; hProcess
0x180006655  mov     rcx, rdi; lpAddress
0x180006658  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18000665d  xor     eax, eax
0x18000665f  jmp     short loc_180006697
0x180006661  cmp     [rsp+78h+arg_0], rsi
0x180006669  jz      short loc_18000668A
0x18000666b  mov     r9d, 20h ; ' '; nSize
0x180006671  mov     qword ptr [rsp+78h+flProtect], rsi; lpNumberOfBytesRead
0x180006676  mov     r8, r14; lpBuffer
0x180006679  mov     rdx, rdi; lpBaseAddress
0x18000667c  mov     rcx, rbx; hProcess
0x18000667f  call    cs:__imp_ReadProcessMemory
0x180006685  mov     esi, 1
0x18000668a  mov     rdx, rbx; hProcess
0x18000668d  mov     rcx, rdi; lpAddress
0x180006690  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180006695  mov     eax, esi
0x180006697  add     rsp, 48h
0x18000669b  pop     r15
0x18000669d  pop     r14
0x18000669f  pop     rdi
0x1800066a0  pop     rsi
0x1800066a1  pop     rbp
0x1800066a2  pop     rbx
0x1800066a3  retn
```
