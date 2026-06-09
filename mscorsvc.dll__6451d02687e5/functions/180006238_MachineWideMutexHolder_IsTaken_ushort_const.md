# MachineWideMutexHolder::IsTaken(ushort const *)

- ea: `0x180006238`
- end: `0x180006327`
- name: `?IsTaken@MachineWideMutexHolder@@SAHPEBG@Z`
- size: `239`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180004078`
- `0x180004170`
- `0x1800050b4`

## callees

- `0x180005fc4`
- `0x180006238`
- `0x180030d84`
- `0x180036354`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800062b5`
- `KERNEL32!DeleteFileW` at `0x1800062b5`
- `KERNEL32!HeapFree` at `0x1800062f7`
- `KERNEL32!HeapFree` at `0x1800062f7`
- `KERNEL32!GetProcessHeap` at `0x1800062e2`
- `KERNEL32!GetProcessHeap` at `0x1800062e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MachineWideMutexHolder::IsTaken(unsigned __int16 *a1)
{
  const unsigned __int16 *v1; // rbx
  unsigned int v2; // edi
  WCHAR *v3; // rbx
  HANDLE ProcessHeap; // rax
  int v6; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v7; // [rsp+2Ch] [rbp-DCh]
  LPCWSTR lpFileName; // [rsp+38h] [rbp-D0h]
  __int16 v9; // [rsp+40h] [rbp-C8h] BYREF

  v7 = 512;
  lpFileName = (LPCWSTR)&v9;
  v6 = 2;
  v9 = 0;
  GenerateMachineWideFileName((SString *)&v6, a1);
  SString::ConvertToUnicode((SString *)&v6);
  v1 = lpFileName;
  DeleteFileW(lpFileName);
  v2 = FileExists(v1);
  if ( (v7 & 0x800000000LL) != 0 )
  {
    v3 = (WCHAR *)lpFileName;
    if ( lpFileName )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v3);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180006238  mov     rax, rsp
0x18000623b  mov     [rax+10h], rbx
0x18000623f  mov     [rax+18h], rsi
0x180006243  mov     [rax+20h], rdi
0x180006247  push    rbp
0x180006248  lea     rbp, [rax-158h]
0x18000624f  sub     rsp, 250h
0x180006256  mov     rax, cs:__security_cookie
0x18000625d  xor     rax, rsp
0x180006260  mov     [rbp+150h+var_10], rax
0x180006267  xor     esi, esi
0x180006269  mov     qword ptr [rsp+250h+var_230], rsi
0x18000626e  mov     qword ptr [rsp+24h], 200h
0x180006277  mov     [rsp+250h+lpFileName], rsi
0x18000627c  lea     rax, [rsp+250h+var_218]
0x180006281  mov     [rsp+250h+lpFileName], rax
0x180006286  mov     [rsp+250h+var_230], 2
0x18000628e  mov     rax, [rsp+250h+lpFileName]
0x180006293  mov     [rax], si
0x180006296  mov     rdx, rcx; unsigned __int16 *
0x180006299  lea     rcx, [rsp+250h+var_230]; this
0x18000629e  call    GenerateMachineWideFileName
0x1800062a3  lea     rcx, [rsp+250h+var_230]; this
0x1800062a8  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800062ad  mov     rbx, [rsp+250h+lpFileName]
0x1800062b2  mov     rcx, rbx; lpFileName
0x1800062b5  call    cs:__imp_DeleteFileW
0x1800062bb  mov     rcx, rbx; unsigned __int16 *
0x1800062be  call    ?FileExists@@YAHPEBG@Z; FileExists(ushort const *)
0x1800062c3  mov     edi, eax
0x1800062c5  test    byte ptr [rsp+250h+var_228], 8
0x1800062ca  jz      short loc_1800062FD
0x1800062cc  mov     rbx, [rsp+250h+lpFileName]
0x1800062d1  test    rbx, rbx
0x1800062d4  jz      short loc_1800062FD
0x1800062d6  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800062dd  test    rax, rax
0x1800062e0  jnz     short loc_1800062EF
0x1800062e2  call    cs:__imp_GetProcessHeap
0x1800062e8  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800062ef  mov     r8, rbx; lpMem
0x1800062f2  xor     edx, edx; dwFlags
0x1800062f4  mov     rcx, rax; hHeap
0x1800062f7  call    cs:__imp_HeapFree
0x1800062fd  mov     eax, edi
0x1800062ff  mov     rcx, [rbp+150h+var_10]
0x180006306  xor     rcx, rsp; StackCookie
0x180006309  call    __security_check_cookie
0x18000630e  lea     r11, [rsp+250h+var_s0]
0x180006316  mov     rbx, [r11+18h]
0x18000631a  mov     rsi, [r11+20h]
0x18000631e  mov     rdi, [r11+28h]
0x180006322  mov     rsp, r11
0x180006325  pop     rbp
0x180006326  retn
```
