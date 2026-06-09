# PssNtWin32LiveSystemProvider::ReadVirtual(void *,unsigned __int64,void *,ulong,ulong *)

- ea: `0x180022890`
- end: `0x180022af8`
- name: `?ReadVirtual@PssNtWin32LiveSystemProvider@@UEAAJPEAX_K0KPEAK@Z`
- size: `616`
- prototype: `signed int __fastcall(PssNtWin32LiveSystemProvider *this, void *, unsigned __int64, char *, size_t Size, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800021f4`
- `0x180003424`
- `0x180015770`
- `0x180022890`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022a45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022a45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002290c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002290c`

## pseudocode

```c
signed int __fastcall PssNtWin32LiveSystemProvider::ReadVirtual(
        PssNtWin32LiveSystemProvider *this,
        void *a2,
        unsigned __int64 a3,
        char *a4,
        size_t Size,
        unsigned int *a6)
{
  unsigned __int64 v7; // r12
  signed int result; // eax
  unsigned int v10; // r15d
  unsigned int *v11; // rsi
  int v12; // edi
  unsigned int v13; // ebx
  unsigned __int64 v14; // rcx
  unsigned int v15; // edi
  int v16; // eax
  int v17; // ecx
  unsigned int v18; // [rsp+30h] [rbp-49h] BYREF
  void *v19; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v20[8]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v21; // [rsp+80h] [rbp+7h]
  unsigned int v22; // [rsp+88h] [rbp+Fh]
  int v23; // [rsp+D0h] [rbp+57h] BYREF
  unsigned int v24; // [rsp+D8h] [rbp+5Fh]

  v7 = a3;
  if ( a2 != *((void **)this + 153) )
    return Win32LiveSystemProvider::ReadVirtual(this, a2, a3, a4, Size, a6);
  v10 = 0;
  v23 = 0;
  memset_0(v20, 0, 0x50u);
  v11 = a6;
  v12 = Size;
  v13 = Size;
  v19 = 0;
  v18 = 0;
  *a6 = 0;
  v24 = v13;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1296));
  if ( !(*((unsigned int (__fastcall **)(_QWORD, __int64, int *, __int64))this + 142))(
          *((_QWORD *)this + 153),
          2,
          &v23,
          4)
    && v23 )
  {
    memset_0(v20, 0, 0x50u);
    result = (*((__int64 (__fastcall **)(_QWORD))this + 148))(*((_QWORD *)this + 154));
    if ( result )
    {
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( !(*((unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *, int))this + 143))(
            *((_QWORD *)this + 153),
            0,
            *((_QWORD *)this + 154),
            v20,
            80) )
    {
      while ( 1 )
      {
        if ( !v13 )
        {
LABEL_16:
          v12 = Size;
          break;
        }
        v14 = v7 - v20[0];
        if ( v7 - v20[0] < v22 )
        {
          if ( !v21 )
          {
            *v11 = v10;
            return -2147024597;
          }
          v15 = v22 - v14;
          if ( v13 < v22 - (unsigned int)v14 )
            v15 = v13;
          memcpy_0(&a4[v10], (const void *)(v14 + v21), v15);
          v7 += v15;
          v13 = v24 - v15;
          v24 -= v15;
          v10 += v15;
        }
        memset_0(v20, 0, 0x50u);
        if ( (*((unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *, int))this + 143))(
               *((_QWORD *)this + 153),
               0,
               *((_QWORD *)this + 154),
               v20,
               80) )
        {
          goto LABEL_16;
        }
      }
    }
    *v11 = v10;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1296));
  if ( *v11 == v12 )
    return 0;
  v16 = (*((__int64 (__fastcall **)(_QWORD, __int64, void **))this + 142))(*((_QWORD *)this + 153), 1, &v19);
  v17 = v16;
  if ( v16 )
  {
    if ( *v11 )
      return -2147024597;
    if ( v16 > 0 )
      return (unsigned __int16)v16 | 0x80070000;
    return v17;
  }
  else
  {
    if ( !Win32LiveSystemProvider::ReadVirtual(this, v19, v7, &a4[v10], v13, &v18) )
      *v11 += v18;
    return v12 != *v11 ? 0x8007012B : 0;
  }
}

```

## disassembly

```asm
0x180022890  mov     [rsp-8+arg_10], rbx
0x180022895  push    rbp
0x180022896  push    rsi
0x180022897  push    rdi
0x180022898  push    r12
0x18002289a  push    r13
0x18002289c  push    r14
0x18002289e  push    r15
0x1800228a0  lea     rbp, [rsp-17h]
0x1800228a5  sub     rsp, 90h
0x1800228ac  mov     r13, r9
0x1800228af  mov     r12, r8
0x1800228b2  mov     r14, rcx
0x1800228b5  cmp     rdx, [rcx+4C8h]
0x1800228bc  jz      short loc_1800228D8
0x1800228be  mov     rax, [rbp+47h+arg_28]
0x1800228c2  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x1800228c7  mov     eax, dword ptr [rbp+47h+Size]
0x1800228ca  mov     [rsp+0C0h+var_A0], eax; unsigned int
0x1800228ce  call    ?ReadVirtual@Win32LiveSystemProvider@@UEAAJPEAX_K0KPEAK@Z; Win32LiveSystemProvider::ReadVirtual(void *,unsigned __int64,void *,ulong,ulong *)
0x1800228d3  jmp     loc_180022ADD
0x1800228d8  xor     r15d, r15d
0x1800228db  lea     rcx, [rbp+47h+var_80]; void *
0x1800228df  xor     edx, edx; Val
0x1800228e1  mov     [rbp+47h+arg_0], r15d
0x1800228e5  lea     r8d, [r15+50h]; Size
0x1800228e9  call    memset_0
0x1800228ee  mov     rsi, [rbp+47h+arg_28]
0x1800228f2  lea     rcx, [r14+510h]; lpCriticalSection
0x1800228f9  mov     edi, dword ptr [rbp+47h+Size]
0x1800228fc  mov     ebx, edi
0x1800228fe  mov     [rbp+47h+var_88], r15
0x180022902  mov     [rbp+47h+var_90], r15d
0x180022906  mov     [rsi], r15d
0x180022909  mov     [rbp+47h+arg_8], ebx
0x18002290c  call    cs:__imp_EnterCriticalSection
0x180022912  mov     rcx, [r14+4C8h]
0x180022919  lea     r9d, [r15+4]
0x18002291d  mov     rax, [r14+470h]
0x180022924  lea     r8, [rbp+47h+arg_0]
0x180022928  lea     edx, [r15+2]
0x18002292c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022931  test    eax, eax
0x180022933  jnz     loc_180022A3E
0x180022939  cmp     [rbp+47h+arg_0], r15d
0x18002293d  jz      loc_180022A3E
0x180022943  xor     edx, edx; Val
0x180022945  lea     r8d, [r15+50h]; Size
0x180022949  lea     rcx, [rbp+47h+var_80]; void *
0x18002294d  call    memset_0
0x180022952  mov     rcx, [r14+4D0h]
0x180022959  mov     rax, [r14+4A0h]
0x180022960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022965  test    eax, eax
0x180022967  jz      short loc_18002297C
0x180022969  jle     loc_180022ADD
0x18002296f  movzx   eax, ax
0x180022972  or      eax, 80070000h
0x180022977  jmp     loc_180022ADD
0x18002297c  mov     r8, [r14+4D0h]
0x180022983  lea     r9, [rbp+47h+var_80]
0x180022987  mov     rcx, [r14+4C8h]
0x18002298e  xor     edx, edx
0x180022990  mov     rax, [r14+478h]
0x180022997  mov     [rsp+0C0h+var_A0], 50h ; 'P'
0x18002299f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229a4  test    eax, eax
0x1800229a6  jnz     loc_180022A3B
0x1800229ac  test    ebx, ebx
0x1800229ae  jz      loc_180022A38
0x1800229b4  mov     edi, [rbp+47h+var_38]
0x1800229b7  mov     rcx, r12
0x1800229ba  sub     rcx, [rbp+47h+var_80]
0x1800229be  cmp     rcx, rdi
0x1800229c1  jnb     short loc_1800229F9
0x1800229c3  mov     rax, [rbp+47h+var_40]
0x1800229c7  test    rax, rax
0x1800229ca  jz      loc_180022A86
0x1800229d0  sub     edi, ecx
0x1800229d2  lea     rdx, [rcx+rax]; Src
0x1800229d6  cmp     ebx, edi
0x1800229d8  mov     ecx, r15d
0x1800229db  cmovb   edi, ebx
0x1800229de  add     rcx, r13; void *
0x1800229e1  mov     r8d, edi; Size
0x1800229e4  mov     ebx, edi
0x1800229e6  call    memcpy_0
0x1800229eb  add     r12, rbx
0x1800229ee  mov     ebx, [rbp+47h+arg_8]
0x1800229f1  sub     ebx, edi
0x1800229f3  mov     [rbp+47h+arg_8], ebx
0x1800229f6  add     r15d, edi
0x1800229f9  mov     edi, 50h ; 'P'
0x1800229fe  lea     rcx, [rbp+47h+var_80]; void *
0x180022a02  mov     r8d, edi; Size
0x180022a05  xor     edx, edx; Val
0x180022a07  call    memset_0
0x180022a0c  mov     r8, [r14+4D0h]
0x180022a13  lea     r9, [rbp+47h+var_80]
0x180022a17  mov     rcx, [r14+4C8h]
0x180022a1e  xor     edx, edx
0x180022a20  mov     rax, [r14+478h]
0x180022a27  mov     [rsp+0C0h+var_A0], edi
0x180022a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a30  test    eax, eax
0x180022a32  jz      loc_1800229AC
0x180022a38  mov     edi, dword ptr [rbp+47h+Size]
0x180022a3b  mov     [rsi], r15d
0x180022a3e  lea     rcx, [r14+510h]; lpCriticalSection
0x180022a45  call    cs:__imp_LeaveCriticalSection
0x180022a4b  cmp     [rsi], edi
0x180022a4d  jz      loc_180022ADB
0x180022a53  mov     rcx, [r14+4C8h]
0x180022a5a  lea     r8, [rbp+47h+var_88]
0x180022a5e  mov     rax, [r14+470h]
0x180022a65  mov     r9d, 8
0x180022a6b  lea     edx, [r9-7]
0x180022a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a74  mov     ecx, eax
0x180022a76  test    eax, eax
0x180022a78  jz      short loc_180022AA1
0x180022a7a  cmp     dword ptr [rsi], 0
0x180022a7d  jz      short loc_180022A90
0x180022a7f  mov     ecx, 8007012Bh
0x180022a84  jmp     short loc_180022A9D
0x180022a86  mov     [rsi], r15d
0x180022a89  mov     eax, 8007012Bh
0x180022a8e  jmp     short loc_180022ADD
0x180022a90  test    eax, eax
0x180022a92  jle     short loc_180022A9D
0x180022a94  movzx   ecx, ax
0x180022a97  or      ecx, 80070000h
0x180022a9d  mov     eax, ecx
0x180022a9f  jmp     short loc_180022ADD
0x180022aa1  mov     rdx, [rbp+47h+var_88]; void *
0x180022aa5  lea     rax, [rbp+47h+var_90]
0x180022aa9  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x180022aae  mov     r8, r12; unsigned __int64
0x180022ab1  mov     r9d, r15d
0x180022ab4  mov     rcx, r14; this
0x180022ab7  add     r9, r13; void *
0x180022aba  mov     [rsp+0C0h+var_A0], ebx; unsigned int
0x180022abe  call    ?ReadVirtual@Win32LiveSystemProvider@@UEAAJPEAX_K0KPEAK@Z; Win32LiveSystemProvider::ReadVirtual(void *,unsigned __int64,void *,ulong,ulong *)
0x180022ac3  test    eax, eax
0x180022ac5  jnz     short loc_180022ACC
0x180022ac7  mov     eax, [rbp+47h+var_90]
0x180022aca  add     [rsi], eax
0x180022acc  mov     eax, [rsi]
0x180022ace  sub     eax, edi
0x180022ad0  neg     eax
0x180022ad2  sbb     eax, eax
0x180022ad4  and     eax, 8007012Bh
0x180022ad9  jmp     short loc_180022ADD
0x180022adb  xor     eax, eax
0x180022add  mov     rbx, [rsp+0C0h+arg_10]
0x180022ae5  add     rsp, 90h
0x180022aec  pop     r15
0x180022aee  pop     r14
0x180022af0  pop     r13
0x180022af2  pop     r12
0x180022af4  pop     rdi
0x180022af5  pop     rsi
0x180022af6  pop     rbp
0x180022af7  retn
```
