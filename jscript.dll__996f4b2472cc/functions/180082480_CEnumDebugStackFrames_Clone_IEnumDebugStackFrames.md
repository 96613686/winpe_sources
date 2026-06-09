# CEnumDebugStackFrames::Clone(IEnumDebugStackFrames * *)

- ea: `0x180082480`
- end: `0x18008253b`
- name: `?Clone@CEnumDebugStackFrames@@UEAAJPEAPEAUIEnumDebugStackFrames@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, struct IEnumDebugStackFrames **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800585d0`
- `0x1800820b0`
- `0x180082480`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800824ae`
- `KERNEL32!GetCurrentThreadId` at `0x1800824ae`

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
0x180082480  mov     [rsp+arg_0], rbx
0x180082485  mov     [rsp+arg_8], rsi
0x18008248a  push    rdi
0x18008248b  sub     rsp, 20h
0x18008248f  mov     rsi, rdx
0x180082492  mov     rdi, rcx
0x180082495  test    rdx, rdx
0x180082498  jnz     short loc_1800824A4
0x18008249a  mov     eax, 80004003h
0x18008249f  jmp     loc_18008252A
0x1800824a4  mov     qword ptr [rdx], 0
0x1800824ab  mov     ebx, [rcx+0Ch]
0x1800824ae  call    cs:__imp_GetCurrentThreadId
0x1800824b5  nop     dword ptr [rax+rax+00h]
0x1800824ba  cmp     eax, ebx
0x1800824bc  jz      short loc_1800824C5
0x1800824be  mov     eax, 8000FFFFh
0x1800824c3  jmp     short loc_18008252A
0x1800824c5  mov     ecx, 30h ; '0'; Size
0x1800824ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800824cf  test    rax, rax
0x1800824d2  jz      short loc_180082525
0x1800824d4  mov     r8, [rdi+28h]; struct CSession *
0x1800824d8  mov     rcx, rax; this
0x1800824db  mov     rdx, [rdi+10h]; unsigned __int64
0x1800824df  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x1800824e4  mov     rdx, rax
0x1800824e7  test    rax, rax
0x1800824ea  jz      short loc_180082525
0x1800824ec  mov     ecx, [rdi+1Ch]
0x1800824ef  xor     ecx, [rax+1Ch]
0x1800824f2  and     ecx, 0FFFFFFFEh
0x1800824f5  xor     ecx, [rdi+1Ch]
0x1800824f8  mov     [rax+1Ch], ecx
0x1800824fb  xor     ecx, [rdi+1Ch]
0x1800824fe  and     ecx, 0FFFFFFFDh
0x180082501  xor     ecx, [rdi+1Ch]
0x180082504  mov     [rax+1Ch], ecx
0x180082507  mov     eax, [rdi+18h]
0x18008250a  mov     [rdx+18h], eax
0x18008250d  mov     rax, [rdi+20h]
0x180082511  mov     [rdx+20h], rax
0x180082515  test    rax, rax
0x180082518  jz      short loc_18008251E
0x18008251a  lock inc dword ptr [rax+28h]
0x18008251e  mov     [rsi], rdx
0x180082521  xor     eax, eax
0x180082523  jmp     short loc_18008252A
0x180082525  mov     eax, 8007000Eh
0x18008252a  mov     rbx, [rsp+28h+arg_0]
0x18008252f  mov     rsi, [rsp+28h+arg_8]
0x180082534  add     rsp, 20h
0x180082538  pop     rdi
0x180082539  retn
```
