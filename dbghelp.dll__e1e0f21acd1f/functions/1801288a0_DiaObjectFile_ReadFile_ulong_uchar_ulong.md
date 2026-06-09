# DiaObjectFile::ReadFile(ulong,uchar *,ulong)

- ea: `0x1801288a0`
- end: `0x1801289cd`
- name: `?ReadFile@DiaObjectFile@@IEAA_NKPEAEK@Z`
- size: `301`
- prototype: `bool(DiaObjectFile *__hidden this, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180127120`
- `0x1801274a0`
- `0x180127f10`
- `0x1801286c0`
- `0x1801289e0`
- `0x180128f60`
- `0x18012ce20`
- `0x18012d610`

## callees

- `0x180027430`
- `0x1800c0690`
- `0x1801288a0`
- `0x180169420`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!__doserrno` at `0x180128980`
- `api-ms-win-crt-runtime-l1-1-0!__doserrno` at `0x180128980`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180128916`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180128916`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x18012892d`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x18012892d`
- `api-ms-win-crt-private-l1-1-0!_o__read` at `0x180128942`
- `api-ms-win-crt-private-l1-1-0!_o__read` at `0x180128942`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18012890a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18012890a`

## pseudocode

```c
char __fastcall DiaObjectFile::ReadFile(DiaObjectFile *this, __int64 a2, unsigned __int8 *a3, unsigned int a4)
{
  size_t v4; // rsi
  __int64 v6; // r9
  __int64 v9; // rax
  const void *v10; // rdx
  __int64 v11; // rax
  signed int v12; // edx
  int v13[4]; // [rsp+20h] [rbp-248h] BYREF
  wchar_t v14[264]; // [rsp+30h] [rbp-238h] BYREF

  v4 = a4;
  v6 = (unsigned int)a2;
  if ( !(_DWORD)v4 )
    return 1;
  v9 = *((unsigned int *)this + 10);
  if ( (*((_DWORD *)this + 12) & 0x800000) != 0 )
  {
    if ( a3 )
    {
      v10 = (const void *)((unsigned int)a2 + v9 + *((_QWORD *)this + 4));
      if ( v10 )
      {
        memcpy_0(a3, v10, v4);
        return 1;
      }
      memset_0(a3, 0, v4);
    }
    *(_DWORD *)_o__errno(this, a2, a3, v6) = 22;
    _invalid_parameter_noinfo();
    return 1;
  }
  else
  {
    if ( _lseeki64(*((_DWORD *)this + 4), (unsigned int)(a2 + v9), 0) != -1
      && _read(*((_DWORD *)this + 4), a3, v4) == (_DWORD)v4 )
    {
      return 1;
    }
    v11 = *((_QWORD *)this + 23);
    v13[0] = 260;
    if ( (*(unsigned int (__fastcall **)(_QWORD, wchar_t *, int *))(**(_QWORD **)(v11 + 256) + 256LL))(
           *(_QWORD *)(v11 + 256),
           v14,
           v13) )
    {
      v12 = *__doserrno();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      SymCache::ReportErrorViaCallback(*(SymCache **)(*((_QWORD *)this + 23) + 648LL), v12, v14, 0);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1801288a0  push    rbx
0x1801288a2  push    rsi
0x1801288a3  push    rdi
0x1801288a4  sub     rsp, 250h
0x1801288ab  mov     rax, cs:__security_cookie
0x1801288b2  xor     rax, rsp
0x1801288b5  mov     [rsp+268h+var_28], rax
0x1801288bd  mov     esi, r9d
0x1801288c0  mov     rdi, r8
0x1801288c3  mov     r9d, edx
0x1801288c6  mov     rbx, rcx
0x1801288c9  test    esi, esi
0x1801288cb  jnz     short loc_1801288D4
0x1801288cd  mov     al, 1
0x1801288cf  jmp     loc_1801289B2
0x1801288d4  test    dword ptr [rcx+30h], 800000h
0x1801288db  mov     eax, [rcx+28h]
0x1801288de  jz      short loc_180128923
0x1801288e0  test    rdi, rdi
0x1801288e3  jz      short loc_18012890A
0x1801288e5  mov     rdx, [rcx+20h]
0x1801288e9  mov     r8, rsi; Size
0x1801288ec  add     rdx, rax
0x1801288ef  mov     rcx, rdi; void *
0x1801288f2  add     rdx, r9; Src
0x1801288f5  jz      short loc_180128903
0x1801288f7  call    memcpy_0
0x1801288fc  mov     al, 1
0x1801288fe  jmp     loc_1801289B2
0x180128903  xor     edx, edx; Val
0x180128905  call    memset_0
0x18012890a  call    cs:__imp__o__errno
0x180128910  mov     dword ptr [rax], 16h
0x180128916  call    cs:__imp__invalid_parameter_noinfo
0x18012891c  mov     al, 1
0x18012891e  jmp     loc_1801289B2
0x180128923  mov     ecx, [rcx+10h]; FileHandle
0x180128926  lea     edx, [r9+rax]; Offset
0x18012892a  xor     r8d, r8d; Origin
0x18012892d  call    cs:__imp__lseeki64
0x180128933  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180128937  jz      short loc_18012894C
0x180128939  mov     ecx, [rbx+10h]; FileHandle
0x18012893c  mov     r8d, esi; MaxCharCount
0x18012893f  mov     rdx, rdi; DstBuf
0x180128942  call    cs:__imp__read
0x180128948  cmp     eax, esi
0x18012894a  jz      short loc_1801288CD
0x18012894c  mov     rax, [rbx+0B8h]
0x180128953  lea     r8, [rsp+268h+var_248]
0x180128958  mov     [rsp+268h+var_248], 104h
0x180128960  lea     rdx, [rsp+268h+var_238]
0x180128965  mov     rcx, [rax+100h]
0x18012896c  mov     rax, [rcx]
0x18012896f  mov     rax, [rax+100h]
0x180128976  call    cs:__guard_dispatch_icall_fptr
0x18012897c  test    eax, eax
0x18012897e  jz      short loc_1801289B0
0x180128980  call    cs:__imp___doserrno
0x180128986  mov     edx, [rax]
0x180128988  test    edx, edx
0x18012898a  jle     short loc_180128995
0x18012898c  movzx   edx, dx
0x18012898f  or      edx, 80070000h; int
0x180128995  mov     rcx, [rbx+0B8h]
0x18012899c  lea     r8, [rsp+268h+var_238]; wchar_t *
0x1801289a1  xor     r9d, r9d; wchar_t *
0x1801289a4  mov     rcx, [rcx+288h]; this
0x1801289ab  call    ?ReportErrorViaCallback@SymCache@@QEAAXJPEB_W0@Z; SymCache::ReportErrorViaCallback(long,wchar_t const *,wchar_t const *)
0x1801289b0  xor     al, al
0x1801289b2  mov     rcx, [rsp+268h+var_28]
0x1801289ba  xor     rcx, rsp; StackCookie
0x1801289bd  call    __security_check_cookie
0x1801289c2  add     rsp, 250h
0x1801289c9  pop     rdi
0x1801289ca  pop     rsi
0x1801289cb  pop     rbx
0x1801289cc  retn
```
