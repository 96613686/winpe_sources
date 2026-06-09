# publicdm::GetDevmode(void *,publicdm::DEVMODE_TYPE,ulong *,_devicemodeW * *)

- ea: `0x18000c6e4`
- end: `0x18000c84d`
- name: `?GetDevmode@publicdm@@YAJPEAXW4DEVMODE_TYPE@1@PEAKPEAPEAU_devicemodeW@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(void *, int, unsigned int *, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000856c`
- `0x18000c6e4`
- `0x18000ea40`
- `0x18001adb4`

## callees

- `0x18000c6e4`
- `0x1800225b8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c781`
- `KERNEL32!GetLastError` at `0x18000c781`
- `KERNEL32!GetProcessHeap` at `0x18000c742`
- `KERNEL32!GetProcessHeap` at `0x18000c820`
- `KERNEL32!GetProcessHeap` at `0x18000c742`
- `KERNEL32!GetProcessHeap` at `0x18000c820`
- `KERNEL32!HeapAlloc` at `0x18000c750`
- `KERNEL32!HeapAlloc` at `0x18000c750`
- `KERNEL32!HeapFree` at `0x18000c82e`
- `KERNEL32!HeapFree` at `0x18000c82e`
- `WINSPOOL!GetPrinterW` at `0x18000c738`
- `WINSPOOL!GetPrinterW` at `0x18000c777`
- `WINSPOOL!GetPrinterW` at `0x18000c738`
- `WINSPOOL!GetPrinterW` at `0x18000c777`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c7c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c7c8`

## pseudocode

```c
__int64 __fastcall publicdm::GetDevmode(void *a1, int a2, unsigned int *a3, _QWORD *a4)
{
  LPVOID v8; // rdi
  DWORD v9; // esi
  DWORD v10; // ebx
  HANDLE ProcessHeap; // rax
  signed int Devmode; // ebx
  signed int LastError; // eax
  unsigned __int16 *v14; // rsi
  void *v15; // rax
  unsigned int v16; // r9d
  HANDLE v17; // rax
  DWORD cbBuf; // [rsp+68h] [rbp+10h] BYREF

  cbBuf = 0;
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v8 = 0;
      goto LABEL_8;
    }
    v9 = 8;
  }
  else
  {
    v9 = 2;
  }
  GetPrinterW(a1, v9, 0, 0, &cbBuf);
  v10 = cbBuf;
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 0, v10);
  if ( !v8 )
  {
    Devmode = -2147024882;
    goto LABEL_11;
  }
  Devmode = 0;
  if ( GetPrinterW(a1, v9, (LPBYTE)v8, cbBuf, &cbBuf) )
    goto LABEL_13;
LABEL_8:
  LastError = GetLastError();
  Devmode = LastError;
  if ( LastError > 0 )
    Devmode = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
  if ( Devmode < 0 )
    goto LABEL_24;
  if ( !v8 )
    goto LABEL_21;
LABEL_13:
  if ( a2 )
  {
    if ( a2 != 1 )
      goto LABEL_21;
    v14 = *(unsigned __int16 **)v8;
  }
  else
  {
    v14 = (unsigned __int16 *)*((_QWORD *)v8 + 7);
  }
  if ( v14 )
  {
    v15 = CoTaskMemAlloc(v14[34] + (unsigned __int64)v14[35]);
    *a4 = v15;
    if ( v15 )
    {
      v16 = v14[34] + v14[35];
      *a3 = v16;
      memcpy_0(v15, v14, v16);
    }
    else
    {
      Devmode = -2147024882;
    }
    goto LABEL_24;
  }
LABEL_21:
  if ( a2 )
    Devmode = -2147418113;
  else
    Devmode = publicdm::GetDevmode(a1, 1, a3, a4);
LABEL_24:
  if ( v8 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v8);
  }
  return (unsigned int)Devmode;
}

```

## disassembly

```asm
0x18000c6e4  mov     [rsp+arg_0], rbx
0x18000c6e9  mov     [rsp+arg_10], rbp
0x18000c6ee  push    rsi
0x18000c6ef  push    rdi
0x18000c6f0  push    r12
0x18000c6f2  push    r14
0x18000c6f4  push    r15
0x18000c6f6  sub     rsp, 30h
0x18000c6fa  mov     [rsp+58h+cbBuf], 0
0x18000c702  mov     r15, r9
0x18000c705  mov     r12, r8
0x18000c708  mov     ebp, edx
0x18000c70a  mov     r14, rcx
0x18000c70d  test    edx, edx
0x18000c70f  jz      short loc_18000C721
0x18000c711  cmp     edx, 1
0x18000c714  jz      short loc_18000C71A
0x18000c716  xor     edi, edi
0x18000c718  jmp     short loc_18000C781
0x18000c71a  mov     esi, 8
0x18000c71f  jmp     short loc_18000C726
0x18000c721  mov     esi, 2
0x18000c726  lea     rax, [rsp+58h+cbBuf]
0x18000c72b  xor     r9d, r9d; cbBuf
0x18000c72e  xor     r8d, r8d; pPrinter
0x18000c731  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x18000c736  mov     edx, esi; Level
0x18000c738  call    cs:__imp_GetPrinterW
0x18000c73e  mov     ebx, [rsp+58h+cbBuf]
0x18000c742  call    cs:__imp_GetProcessHeap
0x18000c748  mov     r8d, ebx; dwBytes
0x18000c74b  xor     edx, edx; dwFlags
0x18000c74d  mov     rcx, rax; hHeap
0x18000c750  call    cs:__imp_HeapAlloc
0x18000c756  mov     rdi, rax
0x18000c759  test    rax, rax
0x18000c75c  jz      short loc_18000C798
0x18000c75e  mov     r9d, [rsp+58h+cbBuf]; cbBuf
0x18000c763  lea     rax, [rsp+58h+cbBuf]
0x18000c768  mov     r8, rdi; pPrinter
0x18000c76b  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x18000c770  mov     edx, esi; Level
0x18000c772  mov     rcx, r14; hPrinter
0x18000c775  xor     ebx, ebx
0x18000c777  call    cs:__imp_GetPrinterW
0x18000c77d  test    eax, eax
0x18000c77f  jnz     short loc_18000C7A6
0x18000c781  call    cs:__imp_GetLastError
0x18000c787  mov     ebx, eax
0x18000c789  test    eax, eax
0x18000c78b  jle     short loc_18000C79D
0x18000c78d  movzx   ebx, ax
0x18000c790  or      ebx, 80070000h
0x18000c796  jmp     short loc_18000C79D
0x18000c798  mov     ebx, 8007000Eh
0x18000c79d  test    ebx, ebx
0x18000c79f  js      short loc_18000C81B
0x18000c7a1  test    rdi, rdi
0x18000c7a4  jz      short loc_18000C7FD
0x18000c7a6  test    ebp, ebp
0x18000c7a8  jz      short loc_18000C7B4
0x18000c7aa  cmp     ebp, 1
0x18000c7ad  jnz     short loc_18000C7FD
0x18000c7af  mov     rsi, [rdi]
0x18000c7b2  jmp     short loc_18000C7B8
0x18000c7b4  mov     rsi, [rdi+38h]
0x18000c7b8  test    rsi, rsi
0x18000c7bb  jz      short loc_18000C7FD
0x18000c7bd  movzx   ecx, word ptr [rsi+46h]
0x18000c7c1  movzx   eax, word ptr [rsi+44h]
0x18000c7c5  add     rcx, rax; cb
0x18000c7c8  call    cs:__imp_CoTaskMemAlloc
0x18000c7ce  mov     [r15], rax
0x18000c7d1  test    rax, rax
0x18000c7d4  jz      short loc_18000C7F6
0x18000c7d6  movzx   ecx, word ptr [rsi+44h]
0x18000c7da  mov     rdx, rsi; Src
0x18000c7dd  movzx   r9d, word ptr [rsi+46h]
0x18000c7e2  add     r9d, ecx
0x18000c7e5  mov     rcx, rax; void *
0x18000c7e8  mov     r8d, r9d; Size
0x18000c7eb  mov     [r12], r9d
0x18000c7ef  call    memcpy_0
0x18000c7f4  jmp     short loc_18000C81B
0x18000c7f6  mov     ebx, 8007000Eh
0x18000c7fb  jmp     short loc_18000C81B
0x18000c7fd  test    ebp, ebp
0x18000c7ff  jnz     short loc_18000C816
0x18000c801  mov     r9, r15
0x18000c804  lea     edx, [rbp+1]
0x18000c807  mov     r8, r12
0x18000c80a  mov     rcx, r14
0x18000c80d  call    ?GetDevmode@publicdm@@YAJPEAXW4DEVMODE_TYPE@1@PEAKPEAPEAU_devicemodeW@@@Z; publicdm::GetDevmode(void *,publicdm::DEVMODE_TYPE,ulong *,_devicemodeW * *)
0x18000c812  mov     ebx, eax
0x18000c814  jmp     short loc_18000C81B
0x18000c816  mov     ebx, 8000FFFFh
0x18000c81b  test    rdi, rdi
0x18000c81e  jz      short loc_18000C834
0x18000c820  call    cs:__imp_GetProcessHeap
0x18000c826  mov     r8, rdi; lpMem
0x18000c829  xor     edx, edx; dwFlags
0x18000c82b  mov     rcx, rax; hHeap
0x18000c82e  call    cs:__imp_HeapFree
0x18000c834  mov     rbp, [rsp+58h+arg_10]
0x18000c839  mov     eax, ebx
0x18000c83b  mov     rbx, [rsp+58h+arg_0]
0x18000c840  add     rsp, 30h
0x18000c844  pop     r15
0x18000c846  pop     r14
0x18000c848  pop     r12
0x18000c84a  pop     rdi
0x18000c84b  pop     rsi
0x18000c84c  retn
```
