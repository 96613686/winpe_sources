# Dfdll::CString::Assign(char const *)

- ea: `0x180002558`
- end: `0x180002604`
- name: `?Assign@CString@Dfdll@@QEAAJPEBD@Z`
- size: `172`
- prototype: `__int64 __fastcall(Dfdll::CString *__hidden this, LPCCH lpMultiByteStr)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004e30`
- `0x180005230`
- `0x180007550`

## callees

- `0x1800020d4`
- `0x180002558`
- `0x1800026bc`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CString::Assign(Dfdll::CString *this, LPCCH lpMultiByteStr)
{
  signed int v4; // ecx
  LPCCH v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rsi

  if ( lpMultiByteStr )
  {
    v5 = lpMultiByteStr;
    v6 = 0x7FFFFFFF;
    do
    {
      if ( !*v5 )
        break;
      ++v5;
      --v6;
    }
    while ( v6 );
    v4 = v6 == 0 ? 0x80070057 : 0;
    v7 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
    if ( v6 )
    {
      if ( !*((_DWORD *)this + 8)
        || (v4 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 40LL))((char *)this + 8, 0), v4 >= 0) )
      {
        *((_DWORD *)this + 8) = 0;
        v4 = Dfdll::CString::Append(this, lpMultiByteStr, v7);
        if ( v4 >= 0 )
          return 0;
      }
    }
  }
  else
  {
    return (unsigned int)Dfdll::CString::AssignNULL(this);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002558  mov     [rsp+arg_0], rbx
0x18000255d  mov     [rsp+arg_8], rsi
0x180002562  push    rdi
0x180002563  sub     rsp, 20h
0x180002567  mov     rdi, rdx
0x18000256a  mov     rbx, rcx
0x18000256d  test    rdx, rdx
0x180002570  jnz     short loc_18000257B
0x180002572  call    ?AssignNULL@CString@Dfdll@@IEAAJXZ; Dfdll::CString::AssignNULL(void)
0x180002577  mov     ecx, eax
0x180002579  jmp     short loc_1800025F2
0x18000257b  mov     r8d, 7FFFFFFFh
0x180002581  mov     rax, rdi
0x180002584  mov     edx, r8d
0x180002587  cmp     byte ptr [rax], 0
0x18000258a  jz      short loc_180002595
0x18000258c  inc     rax
0x18000258f  sub     rdx, 1
0x180002593  jnz     short loc_180002587
0x180002595  mov     rax, rdx
0x180002598  neg     rax
0x18000259b  mov     rax, rdx
0x18000259e  sbb     ecx, ecx
0x1800025a0  sub     r8, rdx
0x1800025a3  not     ecx
0x1800025a5  and     ecx, 80070057h
0x1800025ab  neg     rax
0x1800025ae  sbb     rsi, rsi
0x1800025b1  and     rsi, r8
0x1800025b4  test    rdx, rdx
0x1800025b7  jz      short loc_1800025F2
0x1800025b9  cmp     dword ptr [rbx+20h], 0
0x1800025bd  jbe     short loc_1800025D8
0x1800025bf  lea     rcx, [rbx+8]
0x1800025c3  xor     edx, edx
0x1800025c5  mov     rax, [rcx]
0x1800025c8  mov     rax, [rax+28h]
0x1800025cc  call    cs:__guard_dispatch_icall_fptr
0x1800025d2  mov     ecx, eax
0x1800025d4  test    eax, eax
0x1800025d6  js      short loc_1800025F2
0x1800025d8  and     dword ptr [rbx+20h], 0
0x1800025dc  mov     r8d, esi; unsigned int
0x1800025df  mov     rdx, rdi; lpMultiByteStr
0x1800025e2  mov     rcx, rbx; this
0x1800025e5  call    ?Append@CString@Dfdll@@QEAAJPEBDI@Z; Dfdll::CString::Append(char const *,uint)
0x1800025ea  mov     ecx, eax
0x1800025ec  test    eax, eax
0x1800025ee  js      short loc_1800025F2
0x1800025f0  xor     ecx, ecx
0x1800025f2  mov     rbx, [rsp+28h+arg_0]
0x1800025f7  mov     eax, ecx
0x1800025f9  mov     rsi, [rsp+28h+arg_8]
0x1800025fe  add     rsp, 20h
0x180002602  pop     rdi
0x180002603  retn
```
