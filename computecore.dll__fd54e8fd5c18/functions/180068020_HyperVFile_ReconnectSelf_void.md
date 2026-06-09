# HyperVFile::ReconnectSelf(void)

- ea: `0x180068020`
- end: `0x18006829f`
- name: `?ReconnectSelf@HyperVFile@@MEAAHXZ`
- size: `639`
- prototype: `__int64 __fastcall(HyperVFile *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180007dbc`
- `0x180007e24`
- `0x180066284`
- `0x180068020`
- `0x1800682a8`
- `0x18006b7c4`
- `0x180081f2c`
- `0x180082140`
- `0x18008226c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006815f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006815f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180068167`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180068167`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068116`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068116`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006811c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006811c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HyperVFile::ReconnectSelf(HyperVFile *this)
{
  unsigned int v2; // edi
  int IsDebugTraceEnabled; // ebp
  _DWORD *v4; // rax
  bool v5; // si
  __int64 v6; // rax
  RTL_SRWLOCK *v7; // rcx
  int v8; // ebp
  _DWORD *v9; // rax
  bool v10; // si
  __int64 v11; // rax

  v2 = 0;
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 40LL))(*((_QWORD *)this + 75)) )
  {
    IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0xC040u);
    v4 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
    v2 = 1;
    v5 = v4 && *v4;
    if ( IsDebugTraceEnabled || v5 )
    {
      if ( dword_1800E4718 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 16LL) )
      {
        Init_thread_header(&dword_1800E4718);
        if ( dword_1800E4718 == -1 )
        {
          byte_1800E1B2C = IsDebugTraceEnabled != 0;
          byte_1800E1B2D = v5;
          Init_thread_footer(&dword_1800E4718);
        }
      }
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
      HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1800E1B18, v6);
    }
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 56LL))(*((_QWORD *)this + 75)) )
      HvsThrowWin32Error(0x37u);
    AcquireSRWLockExclusive((PSRWLOCK)this + 94);
    *((_DWORD *)this + 190) = GetCurrentThreadId();
    if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 75) + 88LL))(
            *((_QWORD *)this + 75),
            1,
            *((unsigned int *)this + 186)) )
      HvsThrowWin32Error(0x5B4u);
    ++*((_DWORD *)this + 192);
    v7 = (RTL_SRWLOCK *)((char *)this + 752);
    if ( *((_DWORD *)this + 190) )
    {
      *((_DWORD *)this + 190) = 0;
      ReleaseSRWLockExclusive(v7);
    }
    else
    {
      ReleaseSRWLockShared(v7);
    }
    HyperVFile::ReloadFile(this, 0);
    v8 = HvsIsDebugTraceEnabled(0xC040u);
    v9 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
    v10 = v9 && *v9;
    if ( v8 || v10 )
    {
      if ( dword_1800E471C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 16LL) )
      {
        Init_thread_header(&dword_1800E471C);
        if ( dword_1800E471C == -1 )
        {
          byte_1800E1B5C = v8 != 0;
          byte_1800E1B5D = v10;
          Init_thread_footer(&dword_1800E471C);
        }
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
      HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1800E1B48, v11);
    }
    HyperVFile::UnlockFile(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180068020  push    rbx
0x180068022  push    rbp
0x180068023  push    rsi
0x180068024  push    rdi
0x180068025  push    r13
0x180068027  push    r14
0x180068029  sub     rsp, 48h
0x18006802d  mov     rbx, rcx
0x180068030  xor     edi, edi
0x180068032  mov     rcx, [rcx+258h]
0x180068039  mov     rax, [rcx]
0x18006803c  mov     rax, [rax+28h]
0x180068040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068045  test    eax, eax
0x180068047  jnz     loc_180068211
0x18006804d  mov     ecx, 0C040h; unsigned __int16
0x180068052  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x180068057  mov     ebp, eax
0x180068059  test    eax, eax
0x18006805b  setnz   r14b
0x18006805f  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180068064  mov     rax, [rax+8]
0x180068068  mov     edi, 1
0x18006806d  test    rax, rax
0x180068070  jz      short loc_18006807D
0x180068072  mov     eax, [rax]
0x180068074  test    eax, eax
0x180068076  jz      short loc_18006807D
0x180068078  mov     sil, dil
0x18006807b  jmp     short loc_180068080
0x18006807d  xor     sil, sil
0x180068080  mov     r13d, 10h
0x180068086  test    ebp, ebp
0x180068088  jnz     short loc_18006808F
0x18006808a  test    sil, sil
0x18006808d  jz      short loc_1800680DA
0x18006808f  mov     edx, cs:_tls_index
0x180068095  mov     rax, gs:58h
0x18006809e  mov     rax, [rax+rdx*8]
0x1800680a2  mov     ecx, [r13+rax+0]
0x1800680a7  cmp     cs:dword_1800E4718, ecx
0x1800680ad  jg      loc_180068251
0x1800680b3  mov     rcx, [rbx+258h]
0x1800680ba  mov     rax, [rcx]
0x1800680bd  mov     rax, [rax+48h]
0x1800680c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680c6  mov     r8, rax
0x1800680c9  lea     rdx, off_1800E1B18; struct HvsDebugTraceParameters *
0x1800680d0  mov     ecx, 0C040h; unsigned int
0x1800680d5  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x1800680da  mov     rcx, [rbx+258h]
0x1800680e1  mov     rax, [rcx]
0x1800680e4  mov     rax, [rax+38h]
0x1800680e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680ed  test    eax, eax
0x1800680ef  jz      loc_180068289
0x1800680f5  xorps   xmm0, xmm0
0x1800680f8  movups  [rsp+78h+var_48], xmm0
0x1800680fd  mov     qword ptr [rsp+78h+var_48], rbx
0x180068102  mov     byte ptr [rsp+78h+var_48+8], dil
0x180068107  lea     rsi, [rbx+2F0h]
0x18006810e  mov     qword ptr [rsp+78h+var_58], rsi
0x180068113  mov     rcx, rsi; SRWLock
0x180068116  call    cs:__imp_AcquireSRWLockExclusive
0x18006811c  call    cs:__imp_GetCurrentThreadId
0x180068122  mov     [rsi+8], eax
0x180068125  mov     rcx, [rbx+258h]
0x18006812c  mov     rax, [rcx]
0x18006812f  mov     r8d, [rbx+2E8h]
0x180068136  mov     edx, edi
0x180068138  mov     rax, [rax+58h]
0x18006813c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068141  test    eax, eax
0x180068143  jz      loc_180068294
0x180068149  add     [rbx+300h], edi
0x18006814f  mov     rcx, rsi; SRWLock
0x180068152  cmp     dword ptr [rsi+8], 0
0x180068156  jz      short loc_180068167
0x180068158  mov     dword ptr [rsi+8], 0
0x18006815f  call    cs:__imp_ReleaseSRWLockExclusive
0x180068165  jmp     short loc_18006816D
0x180068167  call    cs:__imp_ReleaseSRWLockShared
0x18006816d  xorps   xmm0, xmm0
0x180068170  movups  [rsp+78h+var_58], xmm0
0x180068175  mov     qword ptr [rsp+78h+var_58], rbx
0x18006817a  mov     byte ptr [rsp+78h+var_58+8], dil
0x18006817f  xor     edx, edx; int
0x180068181  mov     rcx, rbx; this
0x180068184  call    ?ReloadFile@HyperVFile@@IEAAXH@Z; HyperVFile::ReloadFile(int)
0x180068189  mov     ecx, 0C040h; unsigned __int16
0x18006818e  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x180068193  mov     ebp, eax
0x180068195  test    eax, eax
0x180068197  setnz   r14b
0x18006819b  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x1800681a0  mov     rax, [rax+8]
0x1800681a4  test    rax, rax
0x1800681a7  jz      short loc_1800681B4
0x1800681a9  mov     eax, [rax]
0x1800681ab  test    eax, eax
0x1800681ad  jz      short loc_1800681B4
0x1800681af  mov     sil, dil
0x1800681b2  jmp     short loc_1800681B7
0x1800681b4  xor     sil, sil
0x1800681b7  test    ebp, ebp
0x1800681b9  jnz     short loc_1800681C0
0x1800681bb  test    sil, sil
0x1800681be  jz      short loc_180068208
0x1800681c0  mov     edx, cs:_tls_index
0x1800681c6  mov     rax, gs:58h
0x1800681cf  mov     rax, [rax+rdx*8]
0x1800681d3  mov     ecx, [r13+rax+0]
0x1800681d8  cmp     cs:dword_1800E471C, ecx
0x1800681de  jg      short loc_180068220
0x1800681e0  mov     rcx, [rbx+258h]
0x1800681e7  mov     rax, [rcx]
0x1800681ea  mov     rax, [rax+48h]
0x1800681ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681f3  mov     r8, rax
0x1800681f6  lea     rdx, off_1800E1B48; struct HvsDebugTraceParameters *
0x1800681fd  mov     ecx, 0C040h; unsigned int
0x180068202  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x180068207  nop
0x180068208  mov     rcx, rbx; this
0x18006820b  call    ?UnlockFile@HyperVFile@@IEAAXXZ; HyperVFile::UnlockFile(void)
0x180068210  nop
0x180068211  mov     eax, edi
0x180068213  add     rsp, 48h
0x180068217  pop     r14
0x180068219  pop     r13
0x18006821b  pop     rdi
0x18006821c  pop     rsi
0x18006821d  pop     rbp
0x18006821e  pop     rbx
0x18006821f  retn
0x180068220  lea     rcx, dword_1800E471C
0x180068227  call    _Init_thread_header
0x18006822c  cmp     cs:dword_1800E471C, 0FFFFFFFFh
0x180068233  jnz     short loc_1800681E0
0x180068235  mov     cs:byte_1800E1B5C, r14b
0x18006823c  mov     cs:byte_1800E1B5D, sil
0x180068243  lea     rcx, dword_1800E471C
0x18006824a  call    _Init_thread_footer
0x18006824f  jmp     short loc_1800681E0
0x180068251  lea     rcx, dword_1800E4718
0x180068258  call    _Init_thread_header
0x18006825d  cmp     cs:dword_1800E4718, 0FFFFFFFFh
0x180068264  jnz     loc_1800680B3
0x18006826a  mov     cs:byte_1800E1B2C, r14b
0x180068271  mov     cs:byte_1800E1B2D, sil
0x180068278  lea     rcx, dword_1800E4718
0x18006827f  call    _Init_thread_footer
0x180068284  jmp     loc_1800680B3
0x180068289  mov     ecx, 37h ; '7'; unsigned int
0x18006828e  call    ?HvsThrowWin32Error@@YAXK@Z; HvsThrowWin32Error(ulong)
0x180068294  mov     ecx, 5B4h; unsigned int
0x180068299  call    ?HvsThrowWin32Error@@YAXK@Z; HvsThrowWin32Error(ulong)
```
