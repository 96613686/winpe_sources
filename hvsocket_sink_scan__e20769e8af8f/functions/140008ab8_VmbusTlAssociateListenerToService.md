# VmbusTlAssociateListenerToService

- ea: `0x140008ab8`
- end: `0x140008c06`
- name: `VmbusTlAssociateListenerToService`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14001e5ac`

## callees

- `0x140001828`
- `0x140008ab8`
- `0x14000a048`
- `0x14000a154`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008bee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008bee`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008be2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008be2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008b0e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008b0e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008b1e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008b1e`

## string_xrefs

- `0x140008af3`: `VmbusTlAssociateListenerToService`
- `0x140008b86`: `VmbusTlAssociateListenerToService`
- `0x140008bcd`: `VmbusTlAssociateListenerToService`

## pseudocode

```c
__int64 __fastcall VmbusTlAssociateListenerToService(__int64 a1, __int64 a2)
{
  __int64 v5; // rbp
  unsigned int v6; // edi

  if ( *(_QWORD *)(a2 + 360) )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceServiceError((unsigned int)"VmbusTlAssociateListenerToService", 135, -1073741811, a1 + 112, a2 + 408);
    return 3221225485LL;
  }
  else
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v5 = a2 + 408;
    if ( (int)VmbusTlInsertObjectToTable(a1, (struct _RTL_AVL_TABLE *)(a1 + 168), (__int128 *)(a2 + 408), a2, 1) < 0 )
    {
      v6 = -1073741302;
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceServiceError((unsigned int)"VmbusTlAssociateListenerToService", 157, -1073741302, a1 + 112, v5);
    }
    else
    {
      *(_QWORD *)(a2 + 360) = a1;
      *(_BYTE *)(a2 + 172) = 1;
      ++*(_DWORD *)(a1 + 164);
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlAssociateListenerToService",
          151,
          a1,
          *(_QWORD *)(a1 + 8),
          (__int64)"Reference object");
      if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 8)) <= 1 )
        __fastfail(0xEu);
      v6 = 0;
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    KeLeaveCriticalRegion();
    return v6;
  }
}

```

## disassembly

```asm
0x140008ab8  push    rbx
0x140008aba  push    rbp
0x140008abb  push    rsi
0x140008abc  push    rdi
0x140008abd  sub     rsp, 38h
0x140008ac1  cmp     qword ptr [rdx+168h], 0
0x140008ac9  mov     rdi, rdx
0x140008acc  mov     rbx, rcx
0x140008acf  jz      short loc_140008B0E
0x140008ad1  mov     r8d, cs:dword_140013058
0x140008ad8  mov     esi, 0C000000Dh
0x140008add  cmp     r8d, 2
0x140008ae1  jbe     short loc_140008B07
0x140008ae3  add     rdx, 198h
0x140008aea  lea     r9, [rcx+70h]
0x140008aee  mov     [rsp+58h+var_38], rdx
0x140008af3  lea     rcx, aVmbustlassocia_0; "VmbusTlAssociateListenerToService"
0x140008afa  mov     edx, 87h
0x140008aff  mov     r8d, esi
0x140008b02  call    HvsocketTraceServiceError
0x140008b07  mov     eax, esi
0x140008b09  jmp     loc_140008BFC
0x140008b0e  call    cs:__imp_KeEnterCriticalRegion
0x140008b15  nop     dword ptr [rax+rax+00h]
0x140008b1a  lea     rcx, [rbx+10h]; FastMutex
0x140008b1e  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140008b25  nop     dword ptr [rax+rax+00h]
0x140008b2a  lea     rbp, [rdi+198h]
0x140008b31  mov     byte ptr [rsp+58h+var_38], 1
0x140008b36  mov     r8, rbp
0x140008b39  lea     rdx, [rbx+0A8h]
0x140008b40  mov     r9, rdi
0x140008b43  mov     rcx, rbx
0x140008b46  call    VmbusTlInsertObjectToTable
0x140008b4b  test    eax, eax
0x140008b4d  js      short loc_140008BB1
0x140008b4f  mov     [rdi+168h], rbx
0x140008b56  mov     byte ptr [rdi+0ACh], 1
0x140008b5d  inc     dword ptr [rbx+0A4h]
0x140008b63  mov     eax, cs:dword_140013058
0x140008b69  cmp     eax, 5
0x140008b6c  jbe     short loc_140008B92
0x140008b6e  mov     r9, [rbx+8]
0x140008b72  lea     rax, aReferenceObjec; "Reference object"
0x140008b79  mov     r8, rbx
0x140008b7c  mov     [rsp+58h+var_38], rax
0x140008b81  mov     edx, 97h
0x140008b86  lea     rcx, aVmbustlassocia_0; "VmbusTlAssociateListenerToService"
0x140008b8d  call    HvsocketTraceReferenceCount
0x140008b92  mov     eax, 1
0x140008b97  lock xadd [rbx+8], rax
0x140008b9d  inc     rax
0x140008ba0  cmp     rax, 1
0x140008ba4  jg      short loc_140008BAD
0x140008ba6  mov     ecx, 0Eh
0x140008bab  int     29h; Win8: RtlFailFast(ecx)
0x140008bad  xor     edi, edi
0x140008baf  jmp     short loc_140008BDE
0x140008bb1  mov     eax, cs:dword_140013058
0x140008bb7  mov     edi, 0C000020Ah
0x140008bbc  cmp     eax, 2
0x140008bbf  jbe     short loc_140008BDE
0x140008bc1  lea     r9, [rbx+70h]
0x140008bc5  mov     [rsp+58h+var_38], rbp
0x140008bca  mov     r8d, edi
0x140008bcd  lea     rcx, aVmbustlassocia_0; "VmbusTlAssociateListenerToService"
0x140008bd4  mov     edx, 9Dh
0x140008bd9  call    HvsocketTraceServiceError
0x140008bde  lea     rcx, [rbx+10h]; FastMutex
0x140008be2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140008be9  nop     dword ptr [rax+rax+00h]
0x140008bee  call    cs:__imp_KeLeaveCriticalRegion
0x140008bf5  nop     dword ptr [rax+rax+00h]
0x140008bfa  mov     eax, edi
0x140008bfc  add     rsp, 38h
0x140008c00  pop     rdi
0x140008c01  pop     rsi
0x140008c02  pop     rbp
0x140008c03  pop     rbx
0x140008c04  retn
```
