# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180005210`
- end: `0x1800052ac`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `156`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005210`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005267`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005267`
- `ntdll!RtlFreeHeap` at `0x18000527f`
- `ntdll!RtlFreeHeap` at `0x18000527f`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *P)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)P + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)P + 2, i - 1, i);
        i = *((_DWORD *)P + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( P )
    {
      *((_DWORD *)P + 2) = -1073741823;
      *(_QWORD *)P = &ATL::CComClassFactory::`vftable';
      if ( P[56] != (_BYTE)v3 )
      {
        P[56] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(P + 16));
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    }
  }
  else if ( i == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v3;
}

```

## disassembly

```asm
0x180005210  mov     [rsp+arg_0], rbx
0x180005215  push    rdi
0x180005216  sub     rsp, 20h
0x18000521a  mov     rbx, rcx
0x18000521d  mov     r8d, 7FFFFFFFh
0x180005223  mov     ecx, [rcx+8]
0x180005226  jmp     short loc_180005237
0x180005228  lea     edx, [rcx-1]
0x18000522b  mov     eax, ecx
0x18000522d  lock cmpxchg [rbx+8], edx
0x180005232  jz      short loc_18000523C
0x180005234  mov     ecx, [rbx+8]
0x180005237  cmp     ecx, r8d
0x18000523a  jnz     short loc_180005228
0x18000523c  lea     edi, [rcx-1]
0x18000523f  test    edi, edi
0x180005241  jnz     short loc_180005287
0x180005243  test    rbx, rbx
0x180005246  jz      short loc_18000529F
0x180005248  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000524f  mov     dword ptr [rbx+8], 0C0000001h
0x180005256  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000525a  mov     [rbx], rax
0x18000525d  cmp     [rcx+28h], dil
0x180005261  jz      short loc_18000526D
0x180005263  mov     [rcx+28h], dil
0x180005267  call    cs:__imp_DeleteCriticalSection
0x18000526d  mov     rcx, gs:60h
0x180005276  mov     r8, rbx; P
0x180005279  xor     edx, edx; Flags
0x18000527b  mov     rcx, [rcx+30h]; HeapHandle
0x18000527f  call    cs:__imp_RtlFreeHeap
0x180005285  jmp     short loc_18000529F
0x180005287  cmp     edi, 1
0x18000528a  jnz     short loc_18000529F
0x18000528c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005293  mov     rdx, [rcx]
0x180005296  mov     rax, [rdx+10h]
0x18000529a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000529f  mov     rbx, [rsp+28h+arg_0]
0x1800052a4  mov     eax, edi
0x1800052a6  add     rsp, 20h
0x1800052aa  pop     rdi
0x1800052ab  retn
```
