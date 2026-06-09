# CDetectionAndSharing::GetFwGroupsStatus(NET_FW_PROFILE_TYPE2_ *)

- ea: `0x180002e90`
- end: `0x180002f7c`
- name: `?GetFwGroupsStatus@CDetectionAndSharing@@AEAAJPEAW4NET_FW_PROFILE_TYPE2_@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(CDetectionAndSharing *__hidden this, enum NET_FW_PROFILE_TYPE2_ *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800025c8`

## callees

- `0x1800025a0`
- `0x180002e90`
- `0x180005010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002ecd`
- `OLEAUT32!__imp_SysAllocString` at `0x180002ecd`
- `OLEAUT32!__imp_SysFreeString` at `0x180002f40`
- `OLEAUT32!__imp_SysFreeString` at `0x180002f40`

## pseudocode

```c
__int64 __fastcall CDetectionAndSharing::GetFwGroupsStatus(CDetectionAndSharing *this, enum NET_FW_PROFILE_TYPE2_ *a2)
{
  int v2; // ebx
  unsigned int i; // r14d
  __int64 v6; // rbp
  OLECHAR *v7; // r15
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  __int16 v12; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  for ( i = 0; (unsigned __int64)i < *((_QWORD *)this + 11); ++i )
  {
    v6 = 32LL * i;
    v7 = SysAllocString(*(const OLECHAR **)(*((_QWORD *)this + 10) + v6 + 8));
    if ( !v7 )
      return (unsigned int)-2147024882;
    v8 = (__int64 *)*((_QWORD *)this + 9);
    v12 = 0;
    v9 = *v8;
    if ( a2 )
      v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, OLECHAR *, __int16 *))(v9 + 168))(
              v8,
              *(unsigned int *)a2,
              v7,
              &v12);
    else
      v10 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, __int16 *))(v9 + 216))(v8, v7, &v12);
    v2 = v10;
    if ( v10 >= 0 )
    {
      if ( (unsigned __int64)i >= *((_QWORD *)this + 11) )
        ATL::AtlThrowImpl(-2147024809);
      *(_DWORD *)(*((_QWORD *)this + 10) + v6 + 28) = v12 == -1;
    }
    SysFreeString(v7);
    if ( v2 < 0 )
      return (unsigned int)v2;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002e90  mov     [rsp+arg_0], rbx
0x180002e95  mov     [rsp+arg_8], rbp
0x180002e9a  push    rsi
0x180002e9b  push    rdi
0x180002e9c  push    r12
0x180002e9e  push    r14
0x180002ea0  push    r15
0x180002ea2  sub     rsp, 30h
0x180002ea6  xor     ebx, ebx
0x180002ea8  mov     r12, rdx
0x180002eab  xor     r14d, r14d
0x180002eae  mov     rdi, rcx
0x180002eb1  mov     esi, r14d
0x180002eb4  cmp     rsi, [rdi+58h]
0x180002eb8  jnb     loc_180002F58
0x180002ebe  mov     rcx, [rdi+50h]
0x180002ec2  mov     ebp, esi
0x180002ec4  shl     rbp, 5
0x180002ec8  mov     rcx, [rcx+rbp+8]; psz
0x180002ecd  call    cs:__imp_SysAllocString
0x180002ed3  mov     r15, rax
0x180002ed6  test    rax, rax
0x180002ed9  jz      short loc_180002F53
0x180002edb  mov     rcx, [rdi+48h]
0x180002edf  xor     eax, eax
0x180002ee1  mov     [rsp+58h+arg_10], ax
0x180002ee6  mov     rax, [rcx]
0x180002ee9  test    r12, r12
0x180002eec  jz      short loc_180002F08
0x180002eee  mov     edx, [r12]
0x180002ef2  lea     r9, [rsp+58h+arg_10]
0x180002ef7  mov     rax, [rax+0A8h]
0x180002efe  mov     r8, r15
0x180002f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f06  jmp     short loc_180002F1C
0x180002f08  mov     rax, [rax+0D8h]
0x180002f0f  lea     r8, [rsp+58h+arg_10]
0x180002f14  mov     rdx, r15
0x180002f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f1c  mov     ebx, eax
0x180002f1e  test    eax, eax
0x180002f20  js      short loc_180002F3D
0x180002f22  xor     ecx, ecx
0x180002f24  or      eax, 0FFFFFFFFh
0x180002f27  cmp     ax, [rsp+58h+arg_10]
0x180002f2c  setz    cl
0x180002f2f  cmp     rsi, [rdi+58h]
0x180002f33  jnb     short loc_180002F71
0x180002f35  mov     rax, [rdi+50h]
0x180002f39  mov     [rax+rbp+1Ch], ecx
0x180002f3d  mov     rcx, r15; bstrString
0x180002f40  call    cs:__imp_SysFreeString
0x180002f46  inc     r14d
0x180002f49  test    ebx, ebx
0x180002f4b  jns     loc_180002EB1
0x180002f51  jmp     short loc_180002F58
0x180002f53  mov     ebx, 8007000Eh
0x180002f58  mov     rbp, [rsp+58h+arg_8]
0x180002f5d  mov     eax, ebx
0x180002f5f  mov     rbx, [rsp+58h+arg_0]
0x180002f64  add     rsp, 30h
0x180002f68  pop     r15
0x180002f6a  pop     r14
0x180002f6c  pop     r12
0x180002f6e  pop     rdi
0x180002f6f  pop     rsi
0x180002f70  retn
0x180002f71  mov     ecx, 80070057h; int
0x180002f76  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
