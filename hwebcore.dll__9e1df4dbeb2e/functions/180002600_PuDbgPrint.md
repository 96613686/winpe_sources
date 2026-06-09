# PuDbgPrint

- ea: `0x180002600`
- end: `0x18000270e`
- name: `PuDbgPrint`
- size: `270`
- prototype: `__int64 __fastcall(struct _DEBUG_PRINTS *, char *, unsigned int, char *, char *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001948`

## callees

- `0x180002224`
- `0x1800023a8`
- `0x180002600`
- `0x180002de0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800026b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800026b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002662`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026cc`

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
0x180002600  push    rbp
0x180002602  push    rbx
0x180002603  push    rsi
0x180002604  push    rdi
0x180002605  push    r14
0x180002607  push    r15
0x180002609  lea     rbp, [rsp-98h]
0x180002611  sub     rsp, 198h
0x180002618  mov     rax, cs:__security_cookie
0x18000261f  xor     rax, rsp
0x180002622  mov     [rbp+0C0h+var_40], rax
0x180002629  lea     rax, [rbp+0C0h+var_140]
0x18000262d  mov     [rsp+1C0h+var_150], 100h
0x180002635  mov     [rsp+1C0h+lpMem], rax
0x18000263a  mov     r14, r9
0x18000263d  mov     esi, r8d
0x180002640  mov     [rsp+1C0h+var_14C], 100h
0x180002647  mov     rdi, rdx
0x18000264a  mov     [rsp+1C0h+var_148], 0
0x180002652  mov     r15, rcx
0x180002655  mov     [rbp+0C0h+var_140], 0
0x180002659  mov     [rsp+1C0h+var_180], 0
0x180002662  call    cs:__imp_GetLastError
0x180002669  nop     dword ptr [rax+rax+00h]
0x18000266e  mov     rdx, [rbp+0C0h+arg_20]
0x180002675  lea     rcx, [rsp+1C0h+var_178]; this
0x18000267a  mov     ebx, eax
0x18000267c  mov     r9d, esi; unsigned int
0x18000267f  lea     rax, [rbp+0C0h+arg_28]
0x180002686  mov     r8, rdi; char *
0x180002689  mov     [rsp+1C0h+var_180], rax
0x18000268e  lea     rax, [rsp+1C0h+var_180]
0x180002693  mov     [rsp+1C0h+var_190], rax; char **
0x180002698  mov     [rsp+1C0h+var_198], rdx; char *
0x18000269d  mov     rdx, r15; struct _DEBUG_PRINTS *
0x1800026a0  mov     [rsp+1C0h+var_1A0], r14; char *
0x1800026a5  call    ?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z; FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)
0x1800026aa  lea     rdx, [rsp+1C0h+var_178]; struct STRA *
0x1800026af  mov     rcx, r15; struct _DEBUG_PRINTS *
0x1800026b2  call    ?PupOutputMessage@@YAXPEAU_DEBUG_PRINTS@@PEAVSTRA@@@Z; PupOutputMessage(_DEBUG_PRINTS *,STRA *)
0x1800026b7  mov     ecx, ebx; dwErrCode
0x1800026b9  call    cs:__imp_SetLastError
0x1800026c0  nop     dword ptr [rax+rax+00h]
0x1800026c5  cmp     byte ptr [rsp+1C0h+var_14C], 0
0x1800026ca  jz      short loc_1800026EE
0x1800026cc  call    cs:__imp_GetProcessHeap
0x1800026d3  nop     dword ptr [rax+rax+00h]
0x1800026d8  mov     r8, [rsp+1C0h+lpMem]; lpMem
0x1800026dd  xor     edx, edx; dwFlags
0x1800026df  mov     rcx, rax; hHeap
0x1800026e2  call    cs:__imp_HeapFree
0x1800026e9  nop     dword ptr [rax+rax+00h]
0x1800026ee  mov     rcx, [rbp+0C0h+var_40]
0x1800026f5  xor     rcx, rsp; StackCookie
0x1800026f8  call    __security_check_cookie
0x1800026fd  add     rsp, 198h
0x180002704  pop     r15
0x180002706  pop     r14
0x180002708  pop     rdi
0x180002709  pop     rsi
0x18000270a  pop     rbx
0x18000270b  pop     rbp
0x18000270c  retn
```
