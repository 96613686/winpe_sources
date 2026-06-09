# WszCreateProcess(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,int,ulong,void *,ushort const *,_STARTUPINFOW *,_PROCESS_INFORMATION *)

- ea: `0x18003a040`
- end: `0x18003a16a`
- name: `?WszCreateProcess@@YAHPEBG0PEAU_SECURITY_ATTRIBUTES@@1HKPEAX0PEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `298`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpApplicationName@<rcx>, const unsigned __int16 *Src@<rdx>, struct _SECURITY_ATTRIBUTES *@<r8>, struct _SECURITY_ATTRIBUTES *@<r9>, int, DWORD, void *, const unsigned __int16 *, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002a784`

## callees

- `0x180030530`
- `0x180030568`
- `0x18003a040`
- `0x18003f263`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18003a0b6`
- `KERNEL32!SetLastError` at `0x18003a143`
- `KERNEL32!SetLastError` at `0x18003a0b6`
- `KERNEL32!SetLastError` at `0x18003a143`
- `KERNEL32!CreateProcessW` at `0x18003a120`
- `KERNEL32!CreateProcessW` at `0x18003a120`
- `KERNEL32!GetLastError` at `0x18003a128`
- `KERNEL32!GetLastError` at `0x18003a128`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WszCreateProcess(
        LPCWSTR lpApplicationName,
        const unsigned __int16 *Src,
        struct _SECURITY_ATTRIBUTES *a3,
        struct _SECURITY_ATTRIBUTES *a4,
        int a5,
        DWORD dwCreationFlags,
        void *a7,
        const unsigned __int16 *a8,
        struct _STARTUPINFOW *lpStartupInfo,
        struct _PROCESS_INFORMATION *lpProcessInformation)
{
  __int64 v12; // rbx
  unsigned __int64 v13; // rbx
  unsigned __int128 v14; // rax
  WCHAR *v15; // rax
  WCHAR *v16; // rdi
  BOOL v17; // esi
  unsigned int ProcessW; // ebx
  DWORD LastError; // ebp

  v12 = -1;
  do
    ++v12;
  while ( Src[v12] );
  v13 = v12 + 1;
  v14 = v13 * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v13, 2u) )
    *(_QWORD *)&v14 = -1;
  v15 = (WCHAR *)operator new(v14, *((const struct NoThrow **)&v14 + 1));
  v16 = v15;
  v17 = v15 != 0;
  if ( v15 )
  {
    memcpy_0(v15, Src, 2 * v13);
    ProcessW = CreateProcessW(
                 lpApplicationName,
                 v16,
                 0,
                 0,
                 1,
                 dwCreationFlags,
                 0,
                 0,
                 lpStartupInfo,
                 lpProcessInformation);
    LastError = GetLastError();
    if ( v17 )
      operator delete(v16);
    SetLastError(LastError);
    return ProcessW;
  }
  else
  {
    SetLastError(0xEu);
    if ( v17 )
      operator delete(0);
    return 0;
  }
}

```

## disassembly

```asm
0x18003a040  mov     rax, rsp
0x18003a043  mov     [rax+8], rbx
0x18003a047  mov     [rax+10h], rbp
0x18003a04b  mov     [rax+18h], rsi
0x18003a04f  mov     [rax+20h], rdi
0x18003a053  push    r12
0x18003a055  push    r14
0x18003a057  push    r15
0x18003a059  sub     rsp, 60h
0x18003a05d  mov     rbp, rdx
0x18003a060  mov     r14, rcx
0x18003a063  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003a067  mov     rbx, rcx
0x18003a06a  xor     r15d, r15d
0x18003a06d  inc     rbx
0x18003a070  cmp     [rdx+rbx*2], r15w
0x18003a075  jnz     short loc_18003A06D
0x18003a077  mov     r12d, 1
0x18003a07d  add     rbx, r12
0x18003a080  lea     eax, [r12+1]
0x18003a085  mul     rbx
0x18003a088  cmovo   rax, rcx
0x18003a08c  mov     rcx, rax; dwBytes
0x18003a08f  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18003a094  mov     rdi, rax
0x18003a097  mov     [rsp+78h+var_28], rax
0x18003a09c  mov     [rsp+78h+var_20], r15d
0x18003a0a1  mov     esi, r15d
0x18003a0a4  test    rax, rax
0x18003a0a7  cmovnz  esi, r12d
0x18003a0ab  mov     [rsp+78h+var_20], esi
0x18003a0af  jnz     short loc_18003A0D1
0x18003a0b1  lea     ecx, [r12+0Dh]; dwErrCode
0x18003a0b6  call    cs:__imp_SetLastError
0x18003a0bc  nop
0x18003a0bd  test    esi, esi
0x18003a0bf  jz      short loc_18003A0CD
0x18003a0c1  xor     ecx, ecx; lpMem
0x18003a0c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a0c8  mov     [rsp+78h+var_20], r15d
0x18003a0cd  xor     eax, eax
0x18003a0cf  jmp     short loc_18003A14B
0x18003a0d1  lea     r8, [rbx+rbx]; Size
0x18003a0d5  mov     rdx, rbp; Src
0x18003a0d8  mov     rcx, rdi; void *
0x18003a0db  call    memcpy_0
0x18003a0e0  mov     rax, [rsp+78h+arg_48]
0x18003a0e8  mov     [rsp+78h+lpProcessInformation], rax; lpProcessInformation
0x18003a0ed  mov     rax, [rsp+78h+arg_40]
0x18003a0f5  mov     [rsp+78h+lpStartupInfo], rax; lpStartupInfo
0x18003a0fa  mov     [rsp+78h+lpCurrentDirectory], r15; lpCurrentDirectory
0x18003a0ff  mov     [rsp+78h+lpEnvironment], r15; lpEnvironment
0x18003a104  mov     eax, [rsp+78h+arg_28]
0x18003a10b  mov     [rsp+78h+dwCreationFlags], eax; dwCreationFlags
0x18003a10f  mov     [rsp+78h+bInheritHandles], r12d; bInheritHandles
0x18003a114  xor     r9d, r9d; lpThreadAttributes
0x18003a117  xor     r8d, r8d; lpProcessAttributes
0x18003a11a  mov     rdx, rdi; lpCommandLine
0x18003a11d  mov     rcx, r14; lpApplicationName
0x18003a120  call    cs:__imp_CreateProcessW
0x18003a126  mov     ebx, eax
0x18003a128  call    cs:__imp_GetLastError
0x18003a12e  mov     ebp, eax
0x18003a130  test    esi, esi
0x18003a132  jz      short loc_18003A141
0x18003a134  mov     rcx, rdi; lpMem
0x18003a137  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a13c  mov     [rsp+78h+var_20], r15d
0x18003a141  mov     ecx, ebp; dwErrCode
0x18003a143  call    cs:__imp_SetLastError
0x18003a149  mov     eax, ebx
0x18003a14b  lea     r11, [rsp+78h+var_18]
0x18003a150  mov     rbx, [r11+20h]
0x18003a154  mov     rbp, [r11+28h]
0x18003a158  mov     rsi, [r11+30h]
0x18003a15c  mov     rdi, [r11+38h]
0x18003a160  mov     rsp, r11
0x18003a163  pop     r15
0x18003a165  pop     r14
0x18003a167  pop     r12
0x18003a169  retn
```
