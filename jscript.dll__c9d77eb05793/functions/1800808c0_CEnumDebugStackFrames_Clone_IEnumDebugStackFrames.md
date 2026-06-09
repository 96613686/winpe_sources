# CEnumDebugStackFrames::Clone(IEnumDebugStackFrames * *)

- ea: `0x1800808c0`
- end: `0x180080974`
- name: `?Clone@CEnumDebugStackFrames@@UEAAJPEAPEAUIEnumDebugStackFrames@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, struct IEnumDebugStackFrames **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800576a0`
- `0x180080510`
- `0x1800808c0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800808ee`
- `KERNEL32!GetCurrentThreadId` at `0x1800808ee`

## pseudocode

```c
__int64 __fastcall CEnumDebugStackFrames::Clone(CEnumDebugStackFrames *this, struct IEnumDebugStackFrames **a2)
{
  int v5; // ebx
  CEnumDebugStackFrames *v6; // rax
  CEnumDebugStackFrames *v7; // rax
  struct IEnumDebugStackFrames *v8; // rdx
  unsigned int v9; // ecx
  __int64 v10; // rax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v5 )
    return 2147549183LL;
  v6 = (CEnumDebugStackFrames *)operator new(0x30u);
  if ( !v6 )
    return 2147942414LL;
  v7 = CEnumDebugStackFrames::CEnumDebugStackFrames(v6, *((_QWORD *)this + 2), *((struct CSession **)this + 5));
  v8 = (struct IEnumDebugStackFrames *)v7;
  if ( !v7 )
    return 2147942414LL;
  v9 = *((_DWORD *)this + 7) ^ (*((_DWORD *)v7 + 7) ^ *((_DWORD *)this + 7)) & 0xFFFFFFFE;
  *((_DWORD *)v7 + 7) = v9;
  *((_DWORD *)v7 + 7) = *((_DWORD *)this + 7) ^ (*((_DWORD *)this + 7) ^ v9) & 0xFFFFFFFD;
  *((_DWORD *)v7 + 6) = *((_DWORD *)this + 6);
  v10 = *((_QWORD *)this + 4);
  v8[4].lpVtbl = (struct IEnumDebugStackFramesVtbl *)v10;
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 40));
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x1800808c0  mov     [rsp+arg_0], rbx
0x1800808c5  mov     [rsp+arg_8], rsi
0x1800808ca  push    rdi
0x1800808cb  sub     rsp, 20h
0x1800808cf  mov     rsi, rdx
0x1800808d2  mov     rdi, rcx
0x1800808d5  test    rdx, rdx
0x1800808d8  jnz     short loc_1800808E4
0x1800808da  mov     eax, 80004003h
0x1800808df  jmp     loc_180080964
0x1800808e4  mov     qword ptr [rdx], 0
0x1800808eb  mov     ebx, [rcx+0Ch]
0x1800808ee  call    cs:__imp_GetCurrentThreadId
0x1800808f4  cmp     eax, ebx
0x1800808f6  jz      short loc_1800808FF
0x1800808f8  mov     eax, 8000FFFFh
0x1800808fd  jmp     short loc_180080964
0x1800808ff  mov     ecx, 30h ; '0'; Size
0x180080904  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080909  test    rax, rax
0x18008090c  jz      short loc_18008095F
0x18008090e  mov     r8, [rdi+28h]; struct CSession *
0x180080912  mov     rcx, rax; this
0x180080915  mov     rdx, [rdi+10h]; unsigned __int64
0x180080919  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x18008091e  mov     rdx, rax
0x180080921  test    rax, rax
0x180080924  jz      short loc_18008095F
0x180080926  mov     ecx, [rdi+1Ch]
0x180080929  xor     ecx, [rax+1Ch]
0x18008092c  and     ecx, 0FFFFFFFEh
0x18008092f  xor     ecx, [rdi+1Ch]
0x180080932  mov     [rax+1Ch], ecx
0x180080935  xor     ecx, [rdi+1Ch]
0x180080938  and     ecx, 0FFFFFFFDh
0x18008093b  xor     ecx, [rdi+1Ch]
0x18008093e  mov     [rax+1Ch], ecx
0x180080941  mov     eax, [rdi+18h]
0x180080944  mov     [rdx+18h], eax
0x180080947  mov     rax, [rdi+20h]
0x18008094b  mov     [rdx+20h], rax
0x18008094f  test    rax, rax
0x180080952  jz      short loc_180080958
0x180080954  lock inc dword ptr [rax+28h]
0x180080958  mov     [rsi], rdx
0x18008095b  xor     eax, eax
0x18008095d  jmp     short loc_180080964
0x18008095f  mov     eax, 8007000Eh
0x180080964  mov     rbx, [rsp+28h+arg_0]
0x180080969  mov     rsi, [rsp+28h+arg_8]
0x18008096e  add     rsp, 20h
0x180080972  pop     rdi
0x180080973  retn
```
