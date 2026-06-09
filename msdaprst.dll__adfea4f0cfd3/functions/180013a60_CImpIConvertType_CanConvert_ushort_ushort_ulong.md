# CImpIConvertType::CanConvert(ushort,ushort,ulong)

- ea: `0x180013a60`
- end: `0x180013b2e`
- name: `?CanConvert@CImpIConvertType@@UEAAJGGK@Z`
- size: `206`
- prototype: `__int64 __fastcall(CImpIConvertType *__hidden this, unsigned __int16, unsigned __int16, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180013a60`
- `0x180016584`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180013a9f`
- `KERNEL32!GetCurrentThreadId` at `0x180013a9f`
- `KERNEL32!LeaveCriticalSection` at `0x180013b0e`
- `KERNEL32!LeaveCriticalSection` at `0x180013b0e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180013abc`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180013abc`
- `MSDART!UMSEnterCSWraper` at `0x180013a89`
- `MSDART!UMSEnterCSWraper` at `0x180013a89`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIConvertType::CanConvert(
        CImpIConvertType *this,
        unsigned __int16 a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rbx
  DWORD *v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // esi
  __int64 v13; // rcx

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  if ( !*(_DWORD *)(v8 + 12) )
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  SetErrorInfo(0, 0);
  if ( a4 )
    v10 = Exit(-2147217828, 0);
  else
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 64LL))(
            *((_QWORD *)this + 3),
            a2,
            a3);
  v11 = v10;
  --*(_DWORD *)(v8 + 16);
  if ( (*(_DWORD *)(v8 + 12))-- == 1 )
    *v9 = -1;
  v13 = *(_QWORD *)v8;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return v11;
}

```

## disassembly

```asm
0x180013a60  mov     [rsp+arg_8], rbx
0x180013a65  push    rbp
0x180013a66  push    rsi
0x180013a67  push    rdi
0x180013a68  push    r14
0x180013a6a  push    r15
0x180013a6c  sub     rsp, 20h
0x180013a70  mov     esi, r9d
0x180013a73  movzx   r14d, r8w
0x180013a77  movzx   r15d, dx
0x180013a7b  mov     rbp, rcx
0x180013a7e  mov     rbx, [rcx+18h]
0x180013a82  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180013a86  mov     rcx, rbx
0x180013a89  call    cs:__imp_UMSEnterCSWraper
0x180013a90  nop     dword ptr [rax+rax+00h]
0x180013a95  lea     rdi, [rbx+8]
0x180013a99  cmp     dword ptr [rbx+0Ch], 0
0x180013a9d  jnz     short loc_180013AAD
0x180013a9f  call    cs:__imp_GetCurrentThreadId
0x180013aa6  nop     dword ptr [rax+rax+00h]
0x180013aab  mov     [rdi], eax
0x180013aad  inc     dword ptr [rbx+0Ch]
0x180013ab0  inc     dword ptr [rbx+10h]
0x180013ab3  mov     [rsp+48h+arg_0], rbx
0x180013ab8  xor     edx, edx; perrinfo
0x180013aba  xor     ecx, ecx; dwReserved
0x180013abc  call    cs:__imp_SetErrorInfo
0x180013ac3  nop     dword ptr [rax+rax+00h]
0x180013ac8  test    esi, esi
0x180013aca  jz      short loc_180013ADD
0x180013acc  xor     edx, edx; unsigned int
0x180013ace  mov     ecx, 80040E5Ch; int
0x180013ad3  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180013ad8  cmp     esi, 1
0x180013adb  jmp     short loc_180013AF5
0x180013add  mov     rcx, [rbp+18h]
0x180013ae1  mov     rax, [rcx]
0x180013ae4  movzx   r8d, r14w
0x180013ae8  movzx   edx, r15w
0x180013aec  mov     rax, [rax+40h]
0x180013af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013af5  mov     esi, eax
0x180013af7  or      edx, 0FFFFFFFFh
0x180013afa  add     [rbx+10h], edx
0x180013afd  add     [rbx+0Ch], edx
0x180013b00  jnz     short loc_180013B04
0x180013b02  mov     [rdi], edx
0x180013b04  mov     rcx, [rbx]
0x180013b07  dec     dword ptr [rcx+30h]
0x180013b0a  add     rcx, 8; lpCriticalSection
0x180013b0e  call    cs:__imp_LeaveCriticalSection
0x180013b15  nop     dword ptr [rax+rax+00h]
0x180013b1a  mov     eax, esi
0x180013b1c  mov     rbx, [rsp+48h+arg_8]
0x180013b21  add     rsp, 20h
0x180013b25  pop     r15
0x180013b27  pop     r14
0x180013b29  pop     rdi
0x180013b2a  pop     rsi
0x180013b2b  pop     rbp
0x180013b2c  retn
```
