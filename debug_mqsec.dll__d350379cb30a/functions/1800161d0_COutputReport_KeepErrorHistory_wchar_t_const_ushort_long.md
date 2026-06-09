# COutputReport::KeepErrorHistory(wchar_t const *,ushort,long)

- ea: `0x1800161d0`
- end: `0x18001623b`
- name: `?KeepErrorHistory@COutputReport@@QEAAXPEB_WGJ@Z`
- size: `107`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, const wchar_t *, unsigned __int16, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b95c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180016202`
- `KERNEL32!GetCurrentThreadId` at `0x180016202`
- `KERNEL32!LeaveCriticalSection` at `0x180016227`
- `KERNEL32!LeaveCriticalSection` at `0x180016227`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall COutputReport::KeepErrorHistory(
        CCriticalSection *lpCriticalSection,
        const wchar_t *a2,
        unsigned __int16 a3,
        int a4)
{
  int v5; // ebp
  __int64 v8; // rdi
  __int64 v9; // rbx

  v5 = a3;
  CCriticalSection::Lock(lpCriticalSection);
  v8 = *((_DWORD *)lpCriticalSection + 10) & 0x3F;
  v9 = 3 * v8;
  *((_DWORD *)lpCriticalSection + 2 * v9 + 14) = GetCurrentThreadId();
  *((_DWORD *)lpCriticalSection + 2 * v9 + 15) = a4;
  *((_DWORD *)lpCriticalSection + 2 * v9 + 16) = v5;
  *((_QWORD *)lpCriticalSection + 3 * v8 + 9) = a2;
  ++*((_DWORD *)lpCriticalSection + 10);
  LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
}

```

## disassembly

```asm
0x1800161d0  push    rbx
0x1800161d2  push    rbp
0x1800161d3  push    rsi
0x1800161d4  push    rdi
0x1800161d5  push    r14
0x1800161d7  push    r15
0x1800161d9  sub     rsp, 28h
0x1800161dd  mov     esi, r9d
0x1800161e0  movzx   ebp, r8w
0x1800161e4  mov     r14, rdx
0x1800161e7  mov     r15, rcx
0x1800161ea  mov     [rsp+58h+arg_0], rcx
0x1800161ef  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x1800161f4  nop
0x1800161f5  mov     eax, [r15+28h]
0x1800161f9  and     eax, 3Fh
0x1800161fc  mov     edi, eax
0x1800161fe  lea     rbx, [rax+rax*2]
0x180016202  call    cs:__imp_GetCurrentThreadId
0x180016208  mov     [r15+rbx*8+38h], eax
0x18001620d  mov     [r15+rbx*8+3Ch], esi
0x180016212  mov     [r15+rbx*8+40h], ebp
0x180016217  lea     rax, [rdi+rdi*2]
0x18001621b  mov     [r15+rax*8+48h], r14
0x180016220  inc     dword ptr [r15+28h]
0x180016224  mov     rcx, r15; lpCriticalSection
0x180016227  call    cs:__imp_LeaveCriticalSection
0x18001622d  nop
0x18001622e  add     rsp, 28h
0x180016232  pop     r15
0x180016234  pop     r14
0x180016236  pop     rdi
0x180016237  pop     rsi
0x180016238  pop     rbp
0x180016239  pop     rbx
0x18001623a  retn
```
