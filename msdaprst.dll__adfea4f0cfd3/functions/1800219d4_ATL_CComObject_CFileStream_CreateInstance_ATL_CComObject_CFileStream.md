# ATL::CComObject<CFileStream>::CreateInstance(ATL::CComObject<CFileStream> * *)

- ea: `0x1800219d4`
- end: `0x180021a55`
- name: `?CreateInstance@?$CComObject@VCFileStream@@@ATL@@SAJPEAPEAV12@@Z`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022240`

## callees

- `0x180001dd4`
- `0x18000a3d4`
- `0x1800219d4`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFileStream>::CreateInstance(unsigned __int8 **a1, unsigned int a2)
{
  __int64 result; // rax
  unsigned __int8 *v4; // rax
  unsigned __int8 *v5; // rbx

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = MMMAlloc(0x20u, a2);
  v5 = v4;
  if ( v4 )
  {
    ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)v4 + 2);
    *((_QWORD *)v5 + 3) = 0;
    *(_QWORD *)v5 = &ATL::CComObject<CFileStream>::`vftable';
    _InterlockedIncrement(&dword_1800464E8);
  }
  else
  {
    v5 = 0;
  }
  result = v5 == 0 ? 0x8007000E : 0;
  *a1 = v5;
  return result;
}

```

## disassembly

```asm
0x1800219d4  mov     [rsp+arg_8], rbx
0x1800219d9  push    rdi
0x1800219da  sub     rsp, 30h
0x1800219de  mov     rdi, rcx
0x1800219e1  test    rcx, rcx
0x1800219e4  jnz     short loc_1800219ED
0x1800219e6  mov     eax, 80004003h
0x1800219eb  jmp     short loc_180021A49
0x1800219ed  mov     qword ptr [rcx], 0
0x1800219f4  mov     ecx, 20h ; ' '; unsigned int
0x1800219f9  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800219fe  mov     rbx, rax
0x180021a01  mov     [rsp+38h+arg_0], rax
0x180021a06  test    rax, rax
0x180021a09  jz      short loc_180021A2F
0x180021a0b  lea     rcx, [rax+8]
0x180021a0f  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x180021a14  mov     qword ptr [rbx+18h], 0
0x180021a1c  lea     rax, ??_7?$CComObject@VCFileStream@@@ATL@@6B@; const ATL::CComObject<CFileStream>::`vftable'
0x180021a23  mov     [rbx], rax
0x180021a26  lock inc cs:dword_1800464E8
0x180021a2d  jmp     short loc_180021A31
0x180021a2f  xor     ebx, ebx
0x180021a31  mov     rax, rbx
0x180021a34  neg     rax
0x180021a37  sbb     eax, eax
0x180021a39  not     eax
0x180021a3b  and     eax, 8007000Eh
0x180021a40  mov     [rdi], rbx
0x180021a43  jmp     short loc_180021A49
0x180021a45  mov     eax, [rsp+38h+var_18]
0x180021a49  mov     rbx, [rsp+38h+arg_8]
0x180021a4e  add     rsp, 30h
0x180021a52  pop     rdi
0x180021a53  retn
```
