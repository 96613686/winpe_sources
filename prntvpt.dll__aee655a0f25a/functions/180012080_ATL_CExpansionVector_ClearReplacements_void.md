# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180012080`
- end: `0x1800120f3`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800111f4`
- `0x180012100`

## callees

- `0x18000f530`
- `0x180012080`
- `0x1800136b4`
- `0x180015d8c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800120ec`
- `KERNEL32!RaiseException` at `0x1800120ec`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int i; // ebx
  void **ValueAt; // rax

  v1 = *((_DWORD *)this + 4);
  if ( v1 > 0 )
  {
    for ( i = 0; i < v1; ++i )
    {
      if ( i < 0 || i >= v1 )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x1800120F2LL);
      }
      operator delete(*(void **)(*(_QWORD *)this + 8LL * i));
      ValueAt = (void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)i);
      operator delete(*ValueAt);
      v1 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x180012080  mov     [rsp+arg_0], rbx
0x180012085  push    rdi
0x180012086  sub     rsp, 20h
0x18001208a  mov     eax, [rcx+10h]
0x18001208d  mov     rdi, rcx
0x180012090  test    eax, eax
0x180012092  jle     short loc_1800120C8
0x180012094  xor     ebx, ebx
0x180012096  test    ebx, ebx
0x180012098  js      short loc_1800120DD
0x18001209a  cmp     ebx, eax
0x18001209c  jge     short loc_1800120DD
0x18001209e  mov     rcx, [rdi]
0x1800120a1  movsxd  rax, ebx
0x1800120a4  mov     rcx, [rcx+rax*8]; Block
0x1800120a8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800120ad  mov     edx, ebx
0x1800120af  mov     rcx, rdi
0x1800120b2  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1800120b7  mov     rcx, [rax]; Block
0x1800120ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800120bf  mov     eax, [rdi+10h]
0x1800120c2  inc     ebx
0x1800120c4  cmp     ebx, eax
0x1800120c6  jl      short loc_180012096
0x1800120c8  mov     rcx, rdi
0x1800120cb  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x1800120d0  mov     rbx, [rsp+28h+arg_0]
0x1800120d5  xor     eax, eax
0x1800120d7  add     rsp, 20h
0x1800120db  pop     rdi
0x1800120dc  retn
0x1800120dd  xor     r9d, r9d; lpArguments
0x1800120e0  xor     r8d, r8d; nNumberOfArguments
0x1800120e3  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800120e8  lea     edx, [r9+1]; dwExceptionFlags
0x1800120ec  call    cs:__imp_RaiseException
```
