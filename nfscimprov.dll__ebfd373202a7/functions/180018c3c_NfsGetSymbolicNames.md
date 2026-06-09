# NfsGetSymbolicNames

- ea: `0x180018c3c`
- end: `0x180018e0a`
- name: `NfsGetSymbolicNames`
- size: `462`
- prototype: `__int64 __fastcall(unsigned __int16 *Src)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x180019250`

## callees

- `0x180001da6`
- `0x180009704`
- `0x18000eae4`
- `0x180018c3c`
- `0x18001cba0`
- `0x180022000`
- `0x180035b40`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180018dc6`
- `KERNEL32!HeapFree` at `0x180018dda`
- `KERNEL32!HeapFree` at `0x180018dc6`
- `KERNEL32!HeapFree` at `0x180018dda`
- `KERNEL32!GetLastError` at `0x180018cb2`
- `KERNEL32!GetLastError` at `0x180018cb2`
- `KERNEL32!CloseHandle` at `0x180018cd3`
- `KERNEL32!CloseHandle` at `0x180018cd3`
- `KERNEL32!HeapAlloc` at `0x180018d23`
- `KERNEL32!HeapAlloc` at `0x180018d23`
- `KERNEL32!GetProcessHeap` at `0x180018d10`
- `KERNEL32!GetProcessHeap` at `0x180018db8`
- `KERNEL32!GetProcessHeap` at `0x180018dcc`
- `KERNEL32!GetProcessHeap` at `0x180018d10`
- `KERNEL32!GetProcessHeap` at `0x180018db8`
- `KERNEL32!GetProcessHeap` at `0x180018dcc`
- `KERNEL32!CreateFileW` at `0x180018c9c`
- `KERNEL32!CreateFileW` at `0x180018c9c`

## string_xrefs

- `0x180018c95`: `\\.\MountPointManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NfsGetSymbolicNames(unsigned __int16 *Src, __int64 a2)
{
  struct _MOUNTMGR_MOUNT_POINTS *v4; // rsi
  HANDLE FileW; // rbx
  int v6; // r8d
  DWORD MountPoints; // ebp
  int v8; // r8d
  unsigned int i; // edx
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int v12; // edi
  _WORD *v13; // r14
  _WORD *v14; // r15
  unsigned int v15; // ebp
  unsigned int v16; // ecx
  __int64 v17; // rbx
  __int64 v18; // rdx
  HANDLE v19; // rax
  HANDLE v20; // rax
  struct _MOUNTMGR_MOUNT_POINTS *v22[2]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp-68h] BYREF

  v4 = 0;
  v22[0] = 0;
  FileW = CreateFileW(L"\\\\.\\MountPointManager", 0x80000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 || (MountPoints = GetLastError()) == 0 )
  {
    MountPoints = NfsQueryMountPoints(FileW, Src, v6, v22);
    CloseHandle(FileW);
    v4 = v22[0];
  }
  if ( MountPoints )
  {
    v13 = 0;
    v12 = MountPoints;
  }
  else
  {
    v8 = 2;
    for ( i = 0; i < *((_DWORD *)v4 + 1); ++i )
      v8 += *((unsigned __int16 *)v4 + 12 * i + 6) + 2;
    v10 = v8 + 2;
    ProcessHeap = GetProcessHeap();
    v12 = 8;
    v13 = HeapAlloc(ProcessHeap, 8u, v10);
    if ( v13 )
    {
      v12 = 0;
      if ( *((_DWORD *)v4 + 1) )
      {
        v14 = v13;
        v15 = 0;
        do
        {
          v16 = *((unsigned __int16 *)v4 + 12 * v15 + 6);
          if ( (_WORD)v16 )
          {
            v17 = v16 >> 1;
            memcpy_0(v14, (char *)v4 + *((unsigned int *)v4 + 6 * v15 + 2), *((unsigned __int16 *)v4 + 12 * v15 + 6));
            v14[v17] = 0;
            std::wstring::wstring(v23, v14);
            std::set<std::wstring>::insert(a2, v22, v23);
            LOBYTE(v18) = 1;
            std::wstring::_Tidy(v23, v18, 0);
            v14 += (unsigned int)(v17 + 1);
          }
          ++v15;
        }
        while ( v15 < *((_DWORD *)v4 + 1) );
        *v14 = 0;
      }
    }
  }
  v19 = GetProcessHeap();
  HeapFree(v19, 0, v13);
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v4);
  return v12;
}

```

## disassembly

```asm
0x180018c3c  mov     [rsp+arg_10], rbx
0x180018c41  push    rbp
0x180018c42  push    rsi
0x180018c43  push    rdi
0x180018c44  push    r12
0x180018c46  push    r13
0x180018c48  push    r14
0x180018c4a  push    r15
0x180018c4c  sub     rsp, 80h
0x180018c53  mov     rax, cs:__security_cookie
0x180018c5a  xor     rax, rsp
0x180018c5d  mov     [rsp+0B8h+var_48], rax
0x180018c62  mov     r12, rdx
0x180018c65  mov     rdi, rcx
0x180018c68  xor     r13d, r13d
0x180018c6b  mov     esi, r13d
0x180018c6e  mov     [rsp+0B8h+var_78], r13
0x180018c73  mov     [rsp+0B8h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x180018c7c  mov     [rsp+0B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180018c84  lea     r8d, [r13+3]; dwShareMode
0x180018c88  mov     [rsp+0B8h+dwCreationDisposition], r8d; dwCreationDisposition
0x180018c8d  xor     r9d, r9d; lpSecurityAttributes
0x180018c90  mov     edx, 80000000h; dwDesiredAccess
0x180018c95  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x180018c9c  call    cs:__imp_CreateFileW
0x180018ca2  mov     rbx, rax
0x180018ca5  lea     rcx, [rax+1]
0x180018ca9  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180018cb0  jnz     short loc_180018CBE
0x180018cb2  call    cs:__imp_GetLastError
0x180018cb8  mov     ebp, eax
0x180018cba  test    eax, eax
0x180018cbc  jnz     short loc_180018CDE
0x180018cbe  lea     r9, [rsp+0B8h+var_78]; struct _MOUNTMGR_MOUNT_POINTS **
0x180018cc3  mov     rdx, rdi; Src
0x180018cc6  mov     rcx, rbx; hDevice
0x180018cc9  call    ?NfsQueryMountPoints@@YAKPEAXPEAGHPEAPEAU_MOUNTMGR_MOUNT_POINTS@@@Z; NfsQueryMountPoints(void *,ushort *,int,_MOUNTMGR_MOUNT_POINTS * *)
0x180018cce  mov     ebp, eax
0x180018cd0  mov     rcx, rbx; hObject
0x180018cd3  call    cs:__imp_CloseHandle
0x180018cd9  mov     rsi, [rsp+0B8h+var_78]
0x180018cde  test    ebp, ebp
0x180018ce0  jnz     loc_180018DB3
0x180018ce6  lea     r8d, [rbp+2]
0x180018cea  mov     edx, r13d
0x180018ced  cmp     [rsi+4], r13d
0x180018cf1  jbe     short loc_180018D0C
0x180018cf3  mov     eax, edx
0x180018cf5  lea     rcx, [rax+rax*2]
0x180018cf9  movzx   eax, word ptr [rsi+rcx*8+0Ch]
0x180018cfe  add     r8d, 2
0x180018d02  add     r8d, eax
0x180018d05  inc     edx
0x180018d07  cmp     edx, [rsi+4]
0x180018d0a  jb      short loc_180018CF3
0x180018d0c  lea     ebx, [r8+2]
0x180018d10  call    cs:__imp_GetProcessHeap
0x180018d16  mov     rcx, rax; hHeap
0x180018d19  mov     r8d, ebx; dwBytes
0x180018d1c  mov     edi, 8
0x180018d21  mov     edx, edi; dwFlags
0x180018d23  call    cs:__imp_HeapAlloc
0x180018d29  mov     r14, rax
0x180018d2c  test    rax, rax
0x180018d2f  jz      loc_180018DB8
0x180018d35  mov     edi, ebp
0x180018d37  mov     eax, [rsi+4]
0x180018d3a  test    eax, eax
0x180018d3c  jz      short loc_180018DB8
0x180018d3e  mov     r15, r14
0x180018d41  mov     ebp, r13d
0x180018d44  mov     eax, ebp
0x180018d46  lea     rdx, [rax+rax*2]
0x180018d4a  movzx   ecx, word ptr [rsi+rdx*8+0Ch]
0x180018d4f  test    cx, cx
0x180018d52  jz      short loc_180018DA6
0x180018d54  mov     ebx, ecx
0x180018d56  shr     ebx, 1
0x180018d58  mov     r8d, ecx; Size
0x180018d5b  mov     edx, [rsi+rdx*8+8]
0x180018d5f  add     rdx, rsi; Src
0x180018d62  mov     rcx, r15; void *
0x180018d65  call    memcpy_0
0x180018d6a  mov     [r15+rbx*2], r13w
0x180018d6f  mov     rdx, r15
0x180018d72  lea     rcx, [rsp+0B8h+var_68]
0x180018d77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180018d7c  nop
0x180018d7d  lea     r8, [rsp+0B8h+var_68]
0x180018d82  lea     rdx, [rsp+0B8h+var_78]
0x180018d87  mov     rcx, r12
0x180018d8a  call    ?insert@?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::set<std::wstring>::insert(std::wstring &&)
0x180018d8f  nop
0x180018d90  xor     r8d, r8d
0x180018d93  mov     dl, 1
0x180018d95  lea     rcx, [rsp+0B8h+var_68]
0x180018d9a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018d9f  lea     eax, [rbx+1]
0x180018da2  lea     r15, [r15+rax*2]
0x180018da6  inc     ebp
0x180018da8  cmp     ebp, [rsi+4]
0x180018dab  jb      short loc_180018D44
0x180018dad  mov     [r15], r13w
0x180018db1  jmp     short loc_180018DB8
0x180018db3  mov     r14, r13
0x180018db6  mov     edi, ebp
0x180018db8  call    cs:__imp_GetProcessHeap
0x180018dbe  mov     rcx, rax; hHeap
0x180018dc1  mov     r8, r14; lpMem
0x180018dc4  xor     edx, edx; dwFlags
0x180018dc6  call    cs:__imp_HeapFree
0x180018dcc  call    cs:__imp_GetProcessHeap
0x180018dd2  mov     rcx, rax; hHeap
0x180018dd5  mov     r8, rsi; lpMem
0x180018dd8  xor     edx, edx; dwFlags
0x180018dda  call    cs:__imp_HeapFree
0x180018de0  mov     eax, edi
0x180018de2  mov     rcx, [rsp+0B8h+var_48]
0x180018de7  xor     rcx, rsp; StackCookie
0x180018dea  call    __security_check_cookie
0x180018def  mov     rbx, [rsp+0B8h+arg_10]
0x180018df7  add     rsp, 80h
0x180018dfe  pop     r15
0x180018e00  pop     r14
0x180018e02  pop     r13
0x180018e04  pop     r12
0x180018e06  pop     rdi
0x180018e07  pop     rsi
0x180018e08  pop     rbp
0x180018e09  retn
```
