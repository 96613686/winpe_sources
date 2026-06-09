# CDSLink::GetDesiredBufferSize(ulong *)

- ea: `0x18000f910`
- end: `0x18000f9d0`
- name: `?GetDesiredBufferSize@CDSLink@@UEAAJPEAK@Z`
- size: `192`
- prototype: `__int64 __fastcall(CDSLink *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800014f0`
- `0x18000f910`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f96c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f96c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f9ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f9ab`

## pseudocode

```c
__int64 __fastcall CDSLink::GetDesiredBufferSize(CDSLink *this, unsigned int *a2)
{
  unsigned int v5; // ebx
  int v6; // [rsp+20h] [rbp-38h] BYREF
  __int128 v7; // [rsp+28h] [rbp-30h] BYREF
  __int16 v8; // [rsp+38h] [rbp-20h]

  if ( !a2 )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 3) )
    return 2289570097LL;
  v6 = 18;
  v8 = 0;
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( (*(int (__fastcall **)(_QWORD, __int128 *, int *))(**((_QWORD **)this + 3) + 144LL))(
         *((_QWORD *)this + 3),
         &v7,
         &v6) < 0 )
  {
    v5 = -2147418113;
  }
  else
  {
    *a2 = 2 * DWORD2(v7);
    v5 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  return v5;
}

```

## disassembly

```asm
0x18000f910  mov     [rsp+arg_18], rbx
0x18000f915  push    rdi
0x18000f916  sub     rsp, 50h
0x18000f91a  mov     rax, cs:__security_cookie
0x18000f921  xor     rax, rsp
0x18000f924  mov     [rsp+58h+var_18], rax
0x18000f929  mov     rbx, rdx
0x18000f92c  mov     rdi, rcx
0x18000f92f  test    rdx, rdx
0x18000f932  jnz     short loc_18000F93B
0x18000f934  mov     eax, 80004003h
0x18000f939  jmp     short loc_18000F9B8
0x18000f93b  cmp     qword ptr [rcx+18h], 0
0x18000f940  jnz     short loc_18000F949
0x18000f942  mov     eax, 88781131h
0x18000f947  jmp     short loc_18000F9B8
0x18000f949  xorps   xmm0, xmm0
0x18000f94c  mov     [rsp+58h+arg_10], rsi
0x18000f951  xor     eax, eax
0x18000f953  mov     [rsp+58h+var_38], 12h
0x18000f95b  add     rcx, 88h; lpCriticalSection
0x18000f962  mov     [rsp+58h+var_20], ax
0x18000f967  movups  [rsp+58h+var_30], xmm0
0x18000f96c  call    cs:__imp_EnterCriticalSection
0x18000f972  mov     rcx, [rdi+18h]
0x18000f976  lea     r8, [rsp+58h+var_38]
0x18000f97b  lea     rdx, [rsp+58h+var_30]
0x18000f980  mov     rax, [rcx]
0x18000f983  mov     rax, [rax+90h]
0x18000f98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f98f  test    eax, eax
0x18000f991  js      short loc_18000F99F
0x18000f993  mov     eax, dword ptr [rsp+58h+var_30+8]
0x18000f997  add     eax, eax
0x18000f999  mov     [rbx], eax
0x18000f99b  xor     ebx, ebx
0x18000f99d  jmp     short loc_18000F9A4
0x18000f99f  mov     ebx, 8000FFFFh
0x18000f9a4  lea     rcx, [rdi+88h]; lpCriticalSection
0x18000f9ab  call    cs:__imp_LeaveCriticalSection
0x18000f9b1  mov     rsi, [rsp+58h+arg_10]
0x18000f9b6  mov     eax, ebx
0x18000f9b8  mov     rcx, [rsp+58h+var_18]
0x18000f9bd  xor     rcx, rsp; StackCookie
0x18000f9c0  call    __security_check_cookie
0x18000f9c5  mov     rbx, [rsp+58h+arg_18]
0x18000f9ca  add     rsp, 50h
0x18000f9ce  pop     rdi
0x18000f9cf  retn
```
