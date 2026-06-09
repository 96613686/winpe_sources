# PuDbgPrint

- ea: `0x1800024c0`
- end: `0x1800025b5`
- name: `PuDbgPrint`
- size: `245`
- prototype: `__int64 __fastcall(struct _DEBUG_PRINTS *, char *, unsigned int, char *, char *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001948`

## callees

- `0x180002154`
- `0x1800022ac`
- `0x1800024c0`
- `0x180002be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002573`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002522`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002590`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002590`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002580`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002580`

## pseudocode

```c
void __fastcall PuDbgPrint(struct _DEBUG_PRINTS *a1, char *a2, int a3, char *a4, char *a5, char a6)
{
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  char *v12; // [rsp+40h] [rbp-C0h] BYREF
  char *v13[4]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-98h]
  int v15; // [rsp+70h] [rbp-90h]
  __int16 v16; // [rsp+74h] [rbp-8Ch]
  int v17; // [rsp+78h] [rbp-88h]
  char v18; // [rsp+80h] [rbp-80h] BYREF

  v15 = 256;
  lpMem = &v18;
  v16 = 256;
  v17 = 0;
  v18 = 0;
  LastError = GetLastError();
  v12 = &a6;
  FormatMsgToBuffer(v13, a1, a2, a3, a4, a5, &v12);
  PupOutputMessage(a1, (struct STRA *)v13);
  SetLastError(LastError);
  if ( (_BYTE)v16 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x1800024c0  push    rbp
0x1800024c2  push    rbx
0x1800024c3  push    rsi
0x1800024c4  push    rdi
0x1800024c5  push    r14
0x1800024c7  push    r15
0x1800024c9  lea     rbp, [rsp-98h]
0x1800024d1  sub     rsp, 198h
0x1800024d8  mov     rax, cs:__security_cookie
0x1800024df  xor     rax, rsp
0x1800024e2  mov     [rbp+0C0h+var_40], rax
0x1800024e9  lea     rax, [rbp+0C0h+var_140]
0x1800024ed  mov     [rsp+1C0h+var_150], 100h
0x1800024f5  mov     [rsp+1C0h+lpMem], rax
0x1800024fa  mov     r14, r9
0x1800024fd  mov     esi, r8d
0x180002500  mov     [rsp+1C0h+var_14C], 100h
0x180002507  mov     rdi, rdx
0x18000250a  mov     [rsp+1C0h+var_148], 0
0x180002512  mov     r15, rcx
0x180002515  mov     [rbp+0C0h+var_140], 0
0x180002519  mov     [rsp+1C0h+var_180], 0
0x180002522  call    cs:__imp_GetLastError
0x180002528  mov     rdx, [rbp+0C0h+arg_20]
0x18000252f  lea     rcx, [rsp+1C0h+var_178]; this
0x180002534  mov     ebx, eax
0x180002536  mov     r9d, esi; unsigned int
0x180002539  lea     rax, [rbp+0C0h+arg_28]
0x180002540  mov     r8, rdi; char *
0x180002543  mov     [rsp+1C0h+var_180], rax
0x180002548  lea     rax, [rsp+1C0h+var_180]
0x18000254d  mov     [rsp+1C0h+var_190], rax; char **
0x180002552  mov     [rsp+1C0h+var_198], rdx; char *
0x180002557  mov     rdx, r15; struct _DEBUG_PRINTS *
0x18000255a  mov     [rsp+1C0h+var_1A0], r14; char *
0x18000255f  call    ?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z; FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)
0x180002564  lea     rdx, [rsp+1C0h+var_178]; struct STRA *
0x180002569  mov     rcx, r15; struct _DEBUG_PRINTS *
0x18000256c  call    ?PupOutputMessage@@YAXPEAU_DEBUG_PRINTS@@PEAVSTRA@@@Z; PupOutputMessage(_DEBUG_PRINTS *,STRA *)
0x180002571  mov     ecx, ebx; dwErrCode
0x180002573  call    cs:__imp_SetLastError
0x180002579  cmp     byte ptr [rsp+1C0h+var_14C], 0
0x18000257e  jz      short loc_180002596
0x180002580  call    cs:__imp_GetProcessHeap
0x180002586  mov     r8, [rsp+1C0h+lpMem]; lpMem
0x18000258b  xor     edx, edx; dwFlags
0x18000258d  mov     rcx, rax; hHeap
0x180002590  call    cs:__imp_HeapFree
0x180002596  mov     rcx, [rbp+0C0h+var_40]
0x18000259d  xor     rcx, rsp; StackCookie
0x1800025a0  call    __security_check_cookie
0x1800025a5  add     rsp, 198h
0x1800025ac  pop     r15
0x1800025ae  pop     r14
0x1800025b0  pop     rdi
0x1800025b1  pop     rsi
0x1800025b2  pop     rbx
0x1800025b3  pop     rbp
0x1800025b4  retn
```
