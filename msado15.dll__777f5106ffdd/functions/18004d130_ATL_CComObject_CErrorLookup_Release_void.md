# ATL::CComObject<CErrorLookup>::Release(void)

- ea: `0x18004d130`
- end: `0x18004d1c1`
- name: `?Release@?$CComObject@VCErrorLookup@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18004d130`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18004d191`
- `MSDART!MPDeleteCriticalSection` at `0x18004d191`
- `MSDART!MpHeapFree` at `0x18004d1a7`
- `MSDART!MpHeapFree` at `0x18004d1a7`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CErrorLookup>::Release(__int64 a1)
{
  signed __int32 i; // edx
  unsigned __int32 v3; // edi

  for ( i = *(_DWORD *)(a1 + 8); i != 0x7FFFFFFF; i = *(_DWORD *)(a1 + 8) )
  {
    if ( i == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), i - 1, i) )
      break;
  }
  v3 = i - 1;
  if ( i == 1 && a1 )
  {
    *(_DWORD *)(a1 + 8) = 1;
    *(_QWORD *)a1 = &ATL::CComObject<CErrorLookup>::`vftable';
    _InterlockedDecrement(&dword_180122C88);
    MPDeleteCriticalSection(a1 + 16);
    MpHeapFree(g_hHeapHandle, a1);
  }
  return v3;
}

```

## disassembly

```asm
0x18004d130  mov     [rsp+arg_0], rbx
0x18004d135  push    rdi
0x18004d136  sub     rsp, 20h
0x18004d13a  mov     edx, [rcx+8]
0x18004d13d  mov     rbx, rcx
0x18004d140  cmp     edx, 7FFFFFFFh
0x18004d146  jz      short loc_18004D169
0x18004d148  nop     dword ptr [rax+rax+00000000h]
0x18004d150  lea     r8d, [rdx-1]
0x18004d154  mov     eax, edx
0x18004d156  lock cmpxchg [rcx+8], r8d
0x18004d15c  jz      short loc_18004D169
0x18004d15e  mov     edx, [rcx+8]
0x18004d161  cmp     edx, 7FFFFFFFh
0x18004d167  jnz     short loc_18004D150
0x18004d169  lea     edi, [rdx-1]
0x18004d16c  test    edi, edi
0x18004d16e  jnz     short loc_18004D1B3
0x18004d170  test    rbx, rbx
0x18004d173  jz      short loc_18004D1B3
0x18004d175  mov     dword ptr [rcx+8], 1
0x18004d17c  lea     rax, ??_7?$CComObject@VCErrorLookup@@@ATL@@6B@; const ATL::CComObject<CErrorLookup>::`vftable'
0x18004d183  mov     [rcx], rax
0x18004d186  add     rcx, 10h
0x18004d18a  lock dec cs:dword_180122C88
0x18004d191  call    cs:__imp_MPDeleteCriticalSection
0x18004d198  nop     dword ptr [rax+rax+00h]
0x18004d19d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18004d1a4  mov     rdx, rbx
0x18004d1a7  call    cs:__imp_MpHeapFree
0x18004d1ae  nop     dword ptr [rax+rax+00h]
0x18004d1b3  mov     rbx, [rsp+28h+arg_0]
0x18004d1b8  mov     eax, edi
0x18004d1ba  add     rsp, 20h
0x18004d1be  pop     rdi
0x18004d1bf  retn
```
