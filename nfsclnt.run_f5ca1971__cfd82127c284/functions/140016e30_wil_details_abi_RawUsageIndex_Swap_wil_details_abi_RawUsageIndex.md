# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x140016e30`
- end: `0x140016ef2`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140012f14`
- `0x140015aac`
- `0x140016560`

## callees

- `0x140016e30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140016e97`
- `KERNEL32!HeapFree` at `0x140016ec1`
- `KERNEL32!HeapFree` at `0x140016e97`
- `KERNEL32!HeapFree` at `0x140016ec1`
- `KERNEL32!GetProcessHeap` at `0x140016e89`
- `KERNEL32!GetProcessHeap` at `0x140016eb3`
- `KERNEL32!GetProcessHeap` at `0x140016e89`
- `KERNEL32!GetProcessHeap` at `0x140016eb3`

## pseudocode

```c
void __fastcall wil::details_abi::RawUsageIndex::Swap(
        wil::details_abi::RawUsageIndex *this,
        struct wil::details_abi::RawUsageIndex *a2)
{
  __int64 v2; // rbp
  __int128 v5; // xmm6
  __int64 v6; // xmm7_8
  __int64 v7; // rax
  void *v8; // rsi
  HANDLE ProcessHeap; // rax
  void *v10; // rsi
  HANDLE v11; // rax
  char v12; // cl
  char v13; // al
  char v14; // cl

  v2 = *((_QWORD *)this + 6);
  v5 = *(_OWORD *)((char *)this + 24);
  v6 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 6) = 0;
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)((char *)a2 + 24);
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 5);
  v7 = *((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = 0;
  v8 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = v7;
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  *(_OWORD *)((char *)a2 + 24) = v5;
  *((_QWORD *)a2 + 5) = v6;
  v10 = (void *)*((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = v2;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  v12 = *((_BYTE *)this + 56);
  *((_BYTE *)this + 56) = *((_BYTE *)a2 + 56);
  v13 = *((_BYTE *)a2 + 57);
  *((_BYTE *)a2 + 56) = v12;
  v14 = *((_BYTE *)this + 57);
  *((_BYTE *)this + 57) = v13;
  *((_BYTE *)a2 + 57) = v14;
}

```

## disassembly

```asm
0x140016e30  push    rbx
0x140016e32  push    rbp
0x140016e33  push    rsi
0x140016e34  push    rdi
0x140016e35  sub     rsp, 48h
0x140016e39  mov     rbp, [rcx+30h]
0x140016e3d  mov     rbx, rdx
0x140016e40  movaps  [rsp+68h+var_38], xmm6
0x140016e45  mov     rdi, rcx
0x140016e48  movups  xmm6, xmmword ptr [rcx+18h]
0x140016e4c  movaps  [rsp+68h+var_48], xmm7
0x140016e51  movsd   xmm7, qword ptr [rcx+28h]
0x140016e56  mov     qword ptr [rcx+30h], 0
0x140016e5e  movups  xmm0, xmmword ptr [rdx+18h]
0x140016e62  movups  xmmword ptr [rcx+18h], xmm0
0x140016e66  movsd   xmm1, qword ptr [rdx+28h]
0x140016e6b  movsd   qword ptr [rcx+28h], xmm1
0x140016e70  mov     rax, [rdx+30h]
0x140016e74  mov     qword ptr [rdx+30h], 0
0x140016e7c  mov     rsi, [rcx+30h]
0x140016e80  mov     [rcx+30h], rax
0x140016e84  test    rsi, rsi
0x140016e87  jz      short loc_140016E9D
0x140016e89  call    cs:__imp_GetProcessHeap
0x140016e8f  mov     r8, rsi; lpMem
0x140016e92  xor     edx, edx; dwFlags
0x140016e94  mov     rcx, rax; hHeap
0x140016e97  call    cs:__imp_HeapFree
0x140016e9d  movups  xmmword ptr [rbx+18h], xmm6
0x140016ea1  movsd   qword ptr [rbx+28h], xmm7
0x140016ea6  mov     rsi, [rbx+30h]
0x140016eaa  mov     [rbx+30h], rbp
0x140016eae  test    rsi, rsi
0x140016eb1  jz      short loc_140016EC7
0x140016eb3  call    cs:__imp_GetProcessHeap
0x140016eb9  mov     r8, rsi; lpMem
0x140016ebc  xor     edx, edx; dwFlags
0x140016ebe  mov     rcx, rax; hHeap
0x140016ec1  call    cs:__imp_HeapFree
0x140016ec7  mov     al, [rbx+38h]
0x140016eca  mov     cl, [rdi+38h]
0x140016ecd  movaps  xmm6, [rsp+68h+var_38]
0x140016ed2  movaps  xmm7, [rsp+68h+var_48]
0x140016ed7  mov     [rdi+38h], al
0x140016eda  mov     al, [rbx+39h]
0x140016edd  mov     [rbx+38h], cl
0x140016ee0  mov     cl, [rdi+39h]
0x140016ee3  mov     [rdi+39h], al
0x140016ee6  mov     [rbx+39h], cl
0x140016ee9  add     rsp, 48h
0x140016eed  pop     rdi
0x140016eee  pop     rsi
0x140016eef  pop     rbp
0x140016ef0  pop     rbx
0x140016ef1  retn
```
