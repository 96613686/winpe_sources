# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800076f4`
- end: `0x180007770`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010788`

## callees

- `0x1800076f4`
- `0x180008618`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180007729`
- `KERNEL32!GetProcessHeap` at `0x180007729`
- `KERNEL32!HeapFree` at `0x18000773d`
- `KERNEL32!HeapFree` at `0x18000773d`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = *v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = *(_QWORD *)(v3 + 8);
      wil::details_abi::ThreadLocalData::~ThreadLocalData((wil::details_abi::ThreadLocalData *)(v4 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x1800076f4  mov     [rsp+arg_0], rbx
0x1800076f9  mov     [rsp+arg_8], rbp
0x1800076fe  mov     [rsp+arg_10], rsi
0x180007703  push    rdi
0x180007704  sub     rsp, 20h
0x180007708  lea     rbp, [rcx+50h]
0x18000770c  mov     rdi, rcx
0x18000770f  cmp     rcx, rbp
0x180007712  jz      short loc_18000775A
0x180007714  mov     rsi, [rdi]
0x180007717  jmp     short loc_180007749
0x180007719  mov     rbx, rsi
0x18000771c  mov     rsi, [rsi+8]
0x180007720  lea     rcx, [rbx+10h]; this
0x180007724  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180007729  call    cs:__imp_GetProcessHeap
0x180007730  nop     dword ptr [rax+rax+00h]
0x180007735  mov     r8, rbx; lpMem
0x180007738  xor     edx, edx; dwFlags
0x18000773a  mov     rcx, rax; hHeap
0x18000773d  call    cs:__imp_HeapFree
0x180007744  nop     dword ptr [rax+rax+00h]
0x180007749  test    rsi, rsi
0x18000774c  jnz     short loc_180007719
0x18000774e  mov     [rdi], rsi
0x180007751  add     rdi, 8
0x180007755  cmp     rdi, rbp
0x180007758  jnz     short loc_180007714
0x18000775a  mov     rbx, [rsp+28h+arg_0]
0x18000775f  mov     rbp, [rsp+28h+arg_8]
0x180007764  mov     rsi, [rsp+28h+arg_10]
0x180007769  add     rsp, 20h
0x18000776d  pop     rdi
0x18000776e  retn
```
