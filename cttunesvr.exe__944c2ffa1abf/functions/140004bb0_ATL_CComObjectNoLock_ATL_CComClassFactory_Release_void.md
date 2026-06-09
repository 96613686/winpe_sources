# ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(void)

- ea: `0x140004bb0`
- end: `0x140004c22`
- name: `?Release@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `114`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400011e0`
- `0x140004bb0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140004c07`
- `KERNEL32!DeleteCriticalSection` at `0x140004c07`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(char *Block)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)Block + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, i - 1, i);
        i = *((_DWORD *)Block + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 && Block )
  {
    *((_DWORD *)Block + 2) = -1073741823;
    *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
    if ( Block[56] != (_BYTE)v3 )
    {
      Block[56] = v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
    }
    operator delete(Block);
  }
  return v3;
}

```

## disassembly

```asm
0x140004bb0  mov     [rsp+arg_0], rbx
0x140004bb5  push    rdi
0x140004bb6  sub     rsp, 20h
0x140004bba  mov     rbx, rcx
0x140004bbd  mov     r8d, 7FFFFFFFh
0x140004bc3  mov     ecx, [rcx+8]
0x140004bc6  jmp     short loc_140004BD7
0x140004bc8  lea     edx, [rcx-1]
0x140004bcb  mov     eax, ecx
0x140004bcd  lock cmpxchg [rbx+8], edx
0x140004bd2  jz      short loc_140004BDC
0x140004bd4  mov     ecx, [rbx+8]
0x140004bd7  cmp     ecx, r8d
0x140004bda  jnz     short loc_140004BC8
0x140004bdc  lea     edi, [rcx-1]
0x140004bdf  test    edi, edi
0x140004be1  jnz     short loc_140004C15
0x140004be3  test    rbx, rbx
0x140004be6  jz      short loc_140004C15
0x140004be8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x140004bef  mov     dword ptr [rbx+8], 0C0000001h
0x140004bf6  lea     rcx, [rbx+10h]; lpCriticalSection
0x140004bfa  mov     [rbx], rax
0x140004bfd  cmp     [rcx+28h], dil
0x140004c01  jz      short loc_140004C0D
0x140004c03  mov     [rcx+28h], dil
0x140004c07  call    cs:__imp_DeleteCriticalSection
0x140004c0d  mov     rcx, rbx; Block
0x140004c10  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004c15  mov     rbx, [rsp+28h+arg_0]
0x140004c1a  mov     eax, edi
0x140004c1c  add     rsp, 20h
0x140004c20  pop     rdi
0x140004c21  retn
```
