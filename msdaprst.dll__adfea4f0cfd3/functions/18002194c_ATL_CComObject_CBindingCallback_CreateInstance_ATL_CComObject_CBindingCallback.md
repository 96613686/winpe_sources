# ATL::CComObject<CBindingCallback>::CreateInstance(ATL::CComObject<CBindingCallback> * *)

- ea: `0x18002194c`
- end: `0x1800219cd`
- name: `?CreateInstance@?$CComObject@VCBindingCallback@@@ATL@@SAJPEAPEAV12@@Z`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022d50`

## callees

- `0x180001dd4`
- `0x18000a3d4`
- `0x18002194c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CBindingCallback>::CreateInstance(unsigned __int8 **a1, unsigned int a2)
{
  __int64 result; // rax
  unsigned __int8 *v4; // rax
  unsigned __int8 *v5; // rbx
  unsigned int v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = MMMAlloc(0x20u, a2);
  try
  {
    v5 = v4;
    if ( v4 )
    {
      ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)v4 + 2);
      *((_QWORD *)v5 + 3) = 0;
      *(_QWORD *)v5 = &ATL::CComObject<CBindingCallback>::`vftable';
      _InterlockedIncrement(&dword_1800464E8);
    }
    else
    {
      v5 = 0;
    }
    result = v5 == 0 ? 0x8007000E : 0;
    *a1 = v5;
  }
  catch ( long v6 )
  {
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18002194c  mov     [rsp+arg_8], rbx
0x180021951  push    rdi
0x180021952  sub     rsp, 30h
0x180021956  mov     rdi, rcx
0x180021959  test    rcx, rcx
0x18002195c  jnz     short loc_180021965
0x18002195e  mov     eax, 80004003h
0x180021963  jmp     short loc_1800219C1
0x180021965  mov     qword ptr [rcx], 0
0x18002196c  mov     ecx, 20h ; ' '; unsigned int
0x180021971  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180021976  mov     rbx, rax
0x180021979  mov     [rsp+38h+arg_0], rax
0x18002197e  test    rax, rax
0x180021981  jz      short loc_1800219A7
0x180021983  lea     rcx, [rax+8]
0x180021987  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x18002198c  mov     qword ptr [rbx+18h], 0
0x180021994  lea     rax, ??_7?$CComObject@VCBindingCallback@@@ATL@@6B@; const ATL::CComObject<CBindingCallback>::`vftable'
0x18002199b  mov     [rbx], rax
0x18002199e  lock inc cs:dword_1800464E8
0x1800219a5  jmp     short loc_1800219A9
0x1800219a7  xor     ebx, ebx
0x1800219a9  mov     rax, rbx
0x1800219ac  neg     rax
0x1800219af  sbb     eax, eax
0x1800219b1  not     eax
0x1800219b3  and     eax, 8007000Eh
0x1800219b8  mov     [rdi], rbx
0x1800219bb  jmp     short loc_1800219C1
0x1800219bd  mov     eax, [rsp+38h+var_18]
0x1800219c1  mov     rbx, [rsp+38h+arg_8]
0x1800219c6  add     rsp, 30h
0x1800219ca  pop     rdi
0x1800219cb  retn
```
