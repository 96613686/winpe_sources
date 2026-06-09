# Dfdll::CString::Assign(ushort const *)

- ea: `0x180002604`
- end: `0x1800026bb`
- name: `?Assign@CString@Dfdll@@QEAAJPEBG@Z`
- size: `183`
- prototype: `__int64 __fastcall(Dfdll::CString *__hidden this, const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003e88`
- `0x180004580`
- `0x180005400`
- `0x180006180`
- `0x180007a7c`
- `0x18000a2ac`
- `0x18000aa14`
- `0x18000ab8c`
- `0x18000c800`
- `0x18000c954`
- `0x18000cac8`
- `0x18000dadc`
- `0x1800122cc`

## callees

- `0x180002238`
- `0x180002604`
- `0x1800026bc`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CString::Assign(Dfdll::CString *this, struct std::nothrow_t *a2)
{
  signed int v4; // ecx
  struct std::nothrow_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rsi

  if ( a2 )
  {
    v5 = a2;
    v6 = 0x7FFFFFFF;
    do
    {
      if ( !*(_WORD *)v5 )
        break;
      v5 = (struct std::nothrow_t *)((char *)v5 + 2);
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
        v4 = Dfdll::CString::Append(this, a2, v7);
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
0x180002604  mov     [rsp+arg_0], rbx
0x180002609  mov     [rsp+arg_8], rbp
0x18000260e  mov     [rsp+arg_10], rsi
0x180002613  push    rdi
0x180002614  sub     rsp, 20h
0x180002618  xor     ebp, ebp
0x18000261a  mov     rdi, rdx
0x18000261d  mov     rbx, rcx
0x180002620  test    rdx, rdx
0x180002623  jnz     short loc_18000262E
0x180002625  call    ?AssignNULL@CString@Dfdll@@IEAAJXZ; Dfdll::CString::AssignNULL(void)
0x18000262a  mov     ecx, eax
0x18000262c  jmp     short loc_1800026A4
0x18000262e  mov     r8d, 7FFFFFFFh
0x180002634  mov     rax, rdi
0x180002637  mov     edx, r8d
0x18000263a  cmp     [rax], bp
0x18000263d  jz      short loc_180002649
0x18000263f  add     rax, 2
0x180002643  sub     rdx, 1
0x180002647  jnz     short loc_18000263A
0x180002649  mov     rax, rdx
0x18000264c  neg     rax
0x18000264f  mov     rax, rdx
0x180002652  sbb     ecx, ecx
0x180002654  sub     r8, rdx
0x180002657  not     ecx
0x180002659  and     ecx, 80070057h
0x18000265f  neg     rax
0x180002662  sbb     rsi, rsi
0x180002665  and     rsi, r8
0x180002668  test    rdx, rdx
0x18000266b  jz      short loc_1800026A4
0x18000266d  cmp     [rbx+20h], ebp
0x180002670  jbe     short loc_18000268B
0x180002672  lea     rcx, [rbx+8]
0x180002676  xor     edx, edx
0x180002678  mov     rax, [rcx]
0x18000267b  mov     rax, [rax+28h]
0x18000267f  call    cs:__guard_dispatch_icall_fptr
0x180002685  mov     ecx, eax
0x180002687  test    eax, eax
0x180002689  js      short loc_1800026A4
0x18000268b  mov     r8d, esi; unsigned int
0x18000268e  mov     [rbx+20h], ebp
0x180002691  mov     rdx, rdi; unsigned __int16 *
0x180002694  mov     rcx, rbx; this
0x180002697  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x18000269c  mov     ecx, eax
0x18000269e  test    eax, eax
0x1800026a0  js      short loc_1800026A4
0x1800026a2  mov     ecx, ebp
0x1800026a4  mov     rbx, [rsp+28h+arg_0]
0x1800026a9  mov     eax, ecx
0x1800026ab  mov     rbp, [rsp+28h+arg_8]
0x1800026b0  mov     rsi, [rsp+28h+arg_10]
0x1800026b5  add     rsp, 20h
0x1800026b9  pop     rdi
0x1800026ba  retn
```
