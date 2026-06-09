# FIPfVolumeFSOpPreventConflicts

- ea: `0x140010cd0`
- end: `0x140010e7e`
- name: `FIPfVolumeFSOpPreventConflicts`
- size: `430`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1400149e0`
- `0x140016dc0`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140002548`
- `0x14000ef70`
- `0x140010cd0`
- `0x140013bc0`
- `0x140015a48`
- `0x140015d3c`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x140010d1e`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x140010d1e`
- `FLTMGR!FltReleaseContext` at `0x140010e59`
- `FLTMGR!FltReleaseContext` at `0x140010e59`

## string_xrefs

- `0x140010da8`: `\FI_GlobalOpenAttemptsRundown`

## pseudocode

```c
void __fastcall FIPfVolumeFSOpPreventConflicts(__int64 a1, unsigned int a2, __int64 *a3)
{
  void *v6; // rdi
  unsigned int v7; // ebx
  unsigned int v8; // r14d
  __int64 v9; // r15
  wchar_t *v10; // rcx
  unsigned __int16 v11; // si
  int v12; // r8d
  _WORD *v13; // r14
  __int64 v14; // r15
  void *v15; // [rsp+40h] [rbp-20h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h]
  __int64 v18; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v19; // [rsp+B8h] [rbp+58h]

  v15 = 0;
  v16 = 0;
  v6 = 0;
  v7 = MEMORY[0xFFFFF78000000320];
  v8 = MEMORY[0xFFFFF78000000004];
  v17 = MEMORY[0xFFFFF78000000320];
  v19 = MEMORY[0xFFFFF78000000004];
  if ( PsIsCurrentThreadPrefetching() )
  {
    _InterlockedAdd(&dword_1400098E8, 1u);
    v9 = 0;
    goto LABEL_10;
  }
  LODWORD(v18) = 0;
  v9 = 1;
  if ( (int)FIVolumeGet(a1, &v15, &v18) < 0 )
  {
    _InterlockedAdd(&dword_140009904, 1u);
    FIPfOpenAttemptsRundownStart((__m128i *)1, a2, (__int64)&v16);
    _InterlockedExchange(&dword_1400099E0, dword_1400099F0);
    LODWORD(v18) = 0;
    if ( (int)FIVolumeGet(a1, &v15, &v18) < 0 )
    {
      _InterlockedAdd(&dword_140009908, 1u);
      v6 = v15;
      v10 = FIPfGlobalOpenAttemptsRundown;
      v11 = 29;
      v12 = 2;
      goto LABEL_8;
    }
    FIPfOpenAttemptsRundownEnd(1);
  }
  v13 = v15;
  FIPfVolumeRundownAllPrefetchStart(v15, a2, &v16);
  FILockSharedAcquire(v13 + 12);
  v11 = v13[47];
  v18 = *((_QWORD *)v13 + 13);
  FILockExclusiveRelease(v13 + 12);
  LODWORD(v10) = v18;
  v12 = 1;
  v14 = (__int64)v13;
  v8 = v19;
  v9 = v14 | 2;
LABEL_8:
  if ( (_WORD)v16 )
    FIPfConflictTelemetryAccumulate(
      (_DWORD)v10,
      v11,
      v12,
      a2,
      ((v8 * HIDWORD(v17)) << 8) + ((v8 * (unsigned __int64)v7) >> 24),
      (__int64)&v16,
      0);
LABEL_10:
  *a3 = v9;
  if ( v6 )
    FltReleaseContext(v6);
}

```

## disassembly

```asm
0x140010cd0  mov     [rsp-38h+arg_0], rbx
0x140010cd5  push    rbp
0x140010cd6  push    rsi
0x140010cd7  push    rdi
0x140010cd8  push    r12
0x140010cda  push    r13
0x140010cdc  push    r14
0x140010cde  push    r15
0x140010ce0  mov     rbp, rsp
0x140010ce3  sub     rsp, 60h
0x140010ce7  xor     r15d, r15d
0x140010cea  mov     rbx, 0FFFFF78000000320h
0x140010cf4  mov     r13, r8
0x140010cf7  mov     [rbp+var_20], r15
0x140010cfb  mov     r12d, edx
0x140010cfe  mov     [rbp+var_18], r15
0x140010d02  mov     rsi, rcx
0x140010d05  mov     edi, r15d
0x140010d08  mov     rbx, [rbx]
0x140010d0b  mov     eax, ds:0FFFFF78000000004h
0x140010d14  mov     r14d, eax
0x140010d17  mov     [rbp+var_10], rbx
0x140010d1b  mov     [rbp+arg_18], eax
0x140010d1e  call    cs:__imp_PsIsCurrentThreadPrefetching
0x140010d25  nop     dword ptr [rax+rax+00h]
0x140010d2a  test    al, al
0x140010d2c  jz      short loc_140010D44
0x140010d2e  lea     r15d, [rdi+1]
0x140010d32  lock add cs:dword_1400098E8, r15d
0x140010d3a  xor     eax, eax
0x140010d3c  mov     r15d, eax
0x140010d3f  jmp     loc_140010E4D
0x140010d44  lea     r8, [rbp+arg_10]
0x140010d48  mov     dword ptr [rbp+arg_10], r15d
0x140010d4c  lea     rdx, [rbp+var_20]
0x140010d50  mov     rcx, rsi
0x140010d53  call    FIVolumeGet
0x140010d58  mov     r15d, 1
0x140010d5e  test    eax, eax
0x140010d60  jns     short loc_140010DC3
0x140010d62  lock add cs:dword_140009904, r15d
0x140010d6a  lea     r8, [rbp+var_18]
0x140010d6e  mov     edx, r12d
0x140010d71  mov     ecx, r15d
0x140010d74  call    FIPfOpenAttemptsRundownStart
0x140010d79  mov     eax, cs:dword_1400099F0
0x140010d7f  lea     r8, [rbp+arg_10]
0x140010d83  xchg    eax, cs:dword_1400099E0
0x140010d89  lea     rdx, [rbp+var_20]
0x140010d8d  mov     dword ptr [rbp+arg_10], edi
0x140010d90  mov     rcx, rsi
0x140010d93  call    FIVolumeGet
0x140010d98  test    eax, eax
0x140010d9a  jns     short loc_140010DBB
0x140010d9c  lock add cs:dword_140009908, r15d
0x140010da4  mov     rdi, [rbp+var_20]
0x140010da8  lea     rcx, FIPfGlobalOpenAttemptsRundown; "\\FI_GlobalOpenAttemptsRundown"
0x140010daf  lea     esi, [r15+1Ch]
0x140010db3  xor     eax, eax
0x140010db5  lea     r8d, [r15+1]
0x140010db9  jmp     short loc_140010E09
0x140010dbb  mov     rcx, r15
0x140010dbe  call    FIPfOpenAttemptsRundownEnd
0x140010dc3  mov     r14, [rbp+var_20]
0x140010dc7  lea     r8, [rbp+var_18]
0x140010dcb  mov     rcx, r14
0x140010dce  mov     edx, r12d
0x140010dd1  call    FIPfVolumeRundownAllPrefetchStart
0x140010dd6  lea     rcx, [r14+18h]
0x140010dda  call    FILockSharedAcquire
0x140010ddf  mov     rax, [r14+68h]
0x140010de3  lea     rcx, [r14+18h]
0x140010de7  movzx   esi, word ptr [r14+5Eh]
0x140010dec  mov     [rbp+arg_10], rax
0x140010df0  call    FILockExclusiveRelease
0x140010df5  mov     rcx, [rbp+arg_10]
0x140010df9  mov     r8d, r15d
0x140010dfc  mov     r15, r14
0x140010dff  xor     eax, eax
0x140010e01  mov     r14d, [rbp+arg_18]
0x140010e05  or      r15, 2
0x140010e09  cmp     word ptr [rbp+var_18], ax
0x140010e0d  jbe     short loc_140010E4D
0x140010e0f  mov     eax, dword ptr [rbp+var_10+4]
0x140010e12  movzx   edx, si
0x140010e15  mov     r9d, r14d
0x140010e18  imul    rax, r9
0x140010e1c  mov     [rsp+60h+var_30], 0
0x140010e25  shl     rax, 8
0x140010e29  mov     r10d, ebx
0x140010e2c  imul    r10, r9
0x140010e30  mov     r9d, r12d
0x140010e33  shr     r10, 18h
0x140010e37  add     r10, rax
0x140010e3a  lea     rax, [rbp+var_18]
0x140010e3e  mov     [rsp+60h+var_38], rax
0x140010e43  mov     [rsp+60h+var_40], r10
0x140010e48  call    FIPfConflictTelemetryAccumulate
0x140010e4d  mov     [r13+0], r15
0x140010e51  test    rdi, rdi
0x140010e54  jz      short loc_140010E65
0x140010e56  mov     rcx, rdi; Context
0x140010e59  call    cs:__imp_FltReleaseContext
0x140010e60  nop     dword ptr [rax+rax+00h]
0x140010e65  mov     rbx, [rsp+60h+arg_0]
0x140010e6d  add     rsp, 60h
0x140010e71  pop     r15
0x140010e73  pop     r14
0x140010e75  pop     r13
0x140010e77  pop     r12
0x140010e79  pop     rdi
0x140010e7a  pop     rsi
0x140010e7b  pop     rbp
0x140010e7c  retn
```
