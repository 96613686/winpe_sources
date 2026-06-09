# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001600`
- end: `0x1800016d8`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `216`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001600`
- `0x180002970`
- `0x18000c010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18000166f`
- `rtutils!TracePrintfExA` at `0x18000166f`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _DWORD *v6; // rbx
  unsigned int v7; // edi

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( a2 )
  {
    return (unsigned int)-2147221232;
  }
  else
  {
    v6 = operator new(0x28u);
    if ( v6 )
    {
      v6[2] = 1;
      *(_QWORD *)v6 = &CRasProvider::`vftable';
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CRasProvider::CRasProvider");
      v6[6] = 0;
      *((_QWORD *)v6 + 4) = 0;
      *((_QWORD *)v6 + 2) = 0;
      _InterlockedIncrement(&dword_180012828);
      v7 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v6)(v6, a3, a4);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180001600  mov     [rsp+arg_10], rsi
0x180001605  push    rdi
0x180001606  sub     rsp, 20h
0x18000160a  mov     rdi, r9
0x18000160d  mov     rsi, r8
0x180001610  test    r9, r9
0x180001613  jz      loc_1800016D1
0x180001619  mov     [rsp+28h+arg_8], rbp
0x18000161e  xor     ebp, ebp
0x180001620  mov     [r9], rbp
0x180001623  test    rdx, rdx
0x180001626  jnz     loc_1800016C3
0x18000162c  mov     ecx, 28h ; '('; Size
0x180001631  mov     [rsp+28h+arg_0], rbx
0x180001636  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000163b  mov     rbx, rax
0x18000163e  test    rax, rax
0x180001641  jz      loc_1800016CA
0x180001647  lea     rax, ??_7CRasProvider@@6B@; const CRasProvider::`vftable'
0x18000164e  mov     dword ptr [rbx+8], 1
0x180001655  mov     [rbx], rax
0x180001658  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000165e  cmp     ecx, 0FFFFFFFFh
0x180001661  jz      short loc_180001675
0x180001663  lea     r8, aCrasproviderCr_0; "CRasProvider::CRasProvider"
0x18000166a  mov     edx, 0Ch; dwFlags
0x18000166f  call    cs:__imp_TracePrintfExA
0x180001675  mov     [rbx+18h], ebp
0x180001678  mov     [rbx+20h], rbp
0x18000167c  mov     [rbx+10h], rbp
0x180001680  lock inc cs:dword_180012828
0x180001687  mov     rax, [rbx]
0x18000168a  mov     r8, rdi
0x18000168d  mov     rdx, rsi
0x180001690  mov     rcx, rbx
0x180001693  mov     rax, [rax]
0x180001696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000169b  mov     edi, eax
0x18000169d  mov     rcx, rbx
0x1800016a0  mov     rax, [rbx]
0x1800016a3  mov     rax, [rax+10h]
0x1800016a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016ac  mov     rbx, [rsp+28h+arg_0]
0x1800016b1  mov     rbp, [rsp+28h+arg_8]
0x1800016b6  mov     eax, edi
0x1800016b8  mov     rsi, [rsp+28h+arg_10]
0x1800016bd  add     rsp, 20h
0x1800016c1  pop     rdi
0x1800016c2  retn
0x1800016c3  mov     edi, 80040110h
0x1800016c8  jmp     short loc_1800016B1
0x1800016ca  mov     edi, 8007000Eh
0x1800016cf  jmp     short loc_1800016AC
0x1800016d1  mov     eax, 80070057h
0x1800016d6  jmp     short loc_1800016B8
```
