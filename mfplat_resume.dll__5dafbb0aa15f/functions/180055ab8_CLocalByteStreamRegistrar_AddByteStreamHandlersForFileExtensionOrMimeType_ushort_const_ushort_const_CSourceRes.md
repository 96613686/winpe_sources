# CLocalByteStreamRegistrar::AddByteStreamHandlersForFileExtensionOrMimeType(ushort const *,ushort const *,CSourceResolverHandlerList *)

- ea: `0x180055ab8`
- end: `0x180055bbb`
- name: `?AddByteStreamHandlersForFileExtensionOrMimeType@CLocalByteStreamRegistrar@@QEAAJPEBG0PEAVCSourceResolverHandlerList@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, LPCWCH lpString1, LPCWCH, struct CSourceResolverHandlerList *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056634`

## callees

- `0x180055ab8`
- `0x18010c144`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055b19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055b19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055b2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055b2a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180055b6c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180055b98`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180055b6c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180055b98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLocalByteStreamRegistrar::AddByteStreamHandlersForFileExtensionOrMimeType(
        LPCRITICAL_SECTION lpCriticalSection,
        LPCWCH lpString1,
        LPCWCH a3,
        struct CSourceResolverHandlerList *a4)
{
  char v7; // bp
  char v8; // si
  __int64 v10; // rdi
  _RTL_CRITICAL_SECTION_DEBUG *DebugInfo; // r15
  const WCHAR *v12; // r8
  const WCHAR *v13; // r8

  if ( !lpString1 || (v7 = 1, !*lpString1) )
    v7 = 0;
  if ( !a3 || (v8 = 1, !*a3) )
    v8 = 0;
  if ( v7 || v8 )
  {
    EnterCriticalSection(lpCriticalSection);
    LODWORD(v10) = lpCriticalSection[1].LockCount;
    while ( (_DWORD)v10 )
    {
      v10 = (unsigned int)(v10 - 1);
      DebugInfo = lpCriticalSection[1].DebugInfo;
      if ( !v7
        || (v12 = (const WCHAR *)*((_QWORD *)&DebugInfo->Type + 3 * v10)) == 0
        || CompareStringOrdinal(lpString1, -1, v12, -1, 1) != 2 )
      {
        if ( !v8 )
          continue;
        v13 = (const WCHAR *)*((_QWORD *)&DebugInfo->CriticalSection + 3 * v10);
        if ( !v13 || CompareStringOrdinal(a3, -1, v13, -1, 1) != 2 )
          continue;
      }
      CSourceResolverHandlerList::AddLocalHandler(
        a4,
        *((struct IMFActivate **)&DebugInfo->ProcessLocksList.Flink + 3 * v10));
    }
    LeaveCriticalSection(lpCriticalSection);
  }
  return 0;
}

```

## disassembly

```asm
0x180055ab8  mov     [rsp+arg_0], rbx
0x180055abd  mov     [rsp+arg_18], r9
0x180055ac2  push    rbp
0x180055ac3  push    rsi
0x180055ac4  push    rdi
0x180055ac5  push    r12
0x180055ac7  push    r13
0x180055ac9  push    r14
0x180055acb  push    r15
0x180055acd  sub     rsp, 30h
0x180055ad1  mov     r12, r8
0x180055ad4  mov     r13, rdx
0x180055ad7  mov     rbx, rcx
0x180055ada  xor     r14d, r14d
0x180055add  test    rdx, rdx
0x180055ae0  jz      short loc_180055B32
0x180055ae2  cmp     [rdx], r14w
0x180055ae6  mov     bpl, 1
0x180055ae9  jz      short loc_180055B32
0x180055aeb  test    r12, r12
0x180055aee  jnz     short loc_180055B37
0x180055af0  mov     sil, r14b
0x180055af3  test    bpl, bpl
0x180055af6  jnz     short loc_180055B14
0x180055af8  test    sil, sil
0x180055afb  jnz     short loc_180055B14
0x180055afd  xor     eax, eax
0x180055aff  mov     rbx, [rsp+68h+arg_0]
0x180055b04  add     rsp, 30h
0x180055b08  pop     r15
0x180055b0a  pop     r14
0x180055b0c  pop     r13
0x180055b0e  pop     r12
0x180055b10  pop     rdi
0x180055b11  pop     rsi
0x180055b12  pop     rbp
0x180055b13  retn
0x180055b14  mov     [rsp+68h+arg_8], rbx
0x180055b19  call    cs:__imp_EnterCriticalSection
0x180055b1f  nop
0x180055b20  mov     edi, [rbx+30h]
0x180055b23  test    edi, edi
0x180055b25  jnz     short loc_180055B42
0x180055b27  mov     rcx, rbx; lpCriticalSection
0x180055b2a  call    cs:__imp_LeaveCriticalSection
0x180055b30  jmp     short loc_180055AFD
0x180055b32  mov     bpl, r14b
0x180055b35  jmp     short loc_180055AEB
0x180055b37  cmp     [r8], r14w
0x180055b3b  mov     sil, 1
0x180055b3e  jnz     short loc_180055AF3
0x180055b40  jmp     short loc_180055AF0
0x180055b42  dec     edi
0x180055b44  lea     r14, [rdi+rdi*2]
0x180055b48  mov     r15, [rbx+28h]
0x180055b4c  test    bpl, bpl
0x180055b4f  jz      short loc_180055B77
0x180055b51  mov     r8, [r15+r14*8]; lpString2
0x180055b55  test    r8, r8
0x180055b58  jz      short loc_180055B77
0x180055b5a  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180055b62  or      r9d, 0FFFFFFFFh; cchCount2
0x180055b66  or      edx, r9d; cchCount1
0x180055b69  mov     rcx, r13; lpString1
0x180055b6c  call    cs:__imp_CompareStringOrdinal
0x180055b72  cmp     eax, 2
0x180055b75  jz      short loc_180055BA3
0x180055b77  test    sil, sil
0x180055b7a  jz      short loc_180055B23
0x180055b7c  mov     r8, [r15+r14*8+8]; lpString2
0x180055b81  test    r8, r8
0x180055b84  jz      short loc_180055B23
0x180055b86  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180055b8e  or      r9d, 0FFFFFFFFh; cchCount2
0x180055b92  or      edx, r9d; cchCount1
0x180055b95  mov     rcx, r12; lpString1
0x180055b98  call    cs:__imp_CompareStringOrdinal
0x180055b9e  cmp     eax, 2
0x180055ba1  jnz     short loc_180055B23
0x180055ba3  mov     rdx, [r15+r14*8+10h]; struct IMFActivate *
0x180055ba8  mov     rcx, [rsp+68h+arg_18]; this
0x180055bb0  call    ?AddLocalHandler@CSourceResolverHandlerList@@QEAAJPEAUIMFActivate@@@Z; CSourceResolverHandlerList::AddLocalHandler(IMFActivate *)
0x180055bb5  jmp     loc_180055B23
```
