# CreateCaretThing(HWND__ *,_GUID const &,void * *)

- ea: `0x180002910`
- end: `0x1800029c8`
- name: `?CreateCaretThing@@YAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `184`
- prototype: `__int64 __fastcall(HWND hWnd, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800097e0`
- `0x180027e10`

## callees

- `0x180002910`
- `0x1800029d0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002931`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002931`
- `USER32!GetWindowThreadProcessId` at `0x180002956`
- `USER32!GetWindowThreadProcessId` at `0x180002956`

## pseudocode

```c
__int64 __fastcall CreateCaretThing(HWND hWnd, const struct _GUID *a2, void **a3)
{
  CCaret *v6; // rax
  CCaret *v7; // rbx
  DWORD WindowThreadProcessId; // eax
  __int64 (__fastcall **v9)(CCaret *, const struct _GUID *, void **); // rcx
  int v10; // edi

  *a3 = 0;
  v6 = (CCaret *)LocalAlloc(0x40u, 0x80u);
  if ( !v6 )
    return 2147942414LL;
  v7 = CCaret::CCaret(v6);
  if ( !v7 )
    return 2147942414LL;
  WindowThreadProcessId = GetWindowThreadProcessId(hWnd, 0);
  *((_DWORD *)v7 + 30) = WindowThreadProcessId;
  if ( WindowThreadProcessId )
  {
    v9 = *(__int64 (__fastcall ***)(CCaret *, const struct _GUID *, void **))v7;
    *((_QWORD *)v7 + 10) = hWnd;
    v10 = (*v9)(v7, a2, a3);
    if ( v10 < 0 )
      (*(void (__fastcall **)(CCaret *, __int64))(*(_QWORD *)v7 + 224LL))(v7, 1);
    return (unsigned int)v10;
  }
  else
  {
    (*(void (__fastcall **)(CCaret *, __int64))(*(_QWORD *)v7 + 224LL))(v7, 1);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180002910  push    rbx
0x180002912  push    rbp
0x180002913  push    rsi
0x180002914  push    rdi
0x180002915  sub     rsp, 28h
0x180002919  mov     rbp, rdx
0x18000291c  mov     qword ptr [r8], 0
0x180002923  mov     edx, 80h; uBytes
0x180002928  mov     rdi, rcx
0x18000292b  mov     rsi, r8
0x18000292e  lea     ecx, [rdx-40h]; uFlags
0x180002931  call    cs:__imp_LocalAlloc
0x180002937  mov     [rsp+48h+arg_10], rax
0x18000293c  test    rax, rax
0x18000293f  jz      short loc_1800029BA
0x180002941  mov     rcx, rax; this
0x180002944  call    ??0CCaret@@QEAA@XZ; CCaret::CCaret(void)
0x180002949  mov     rbx, rax
0x18000294c  test    rax, rax
0x18000294f  jz      short loc_1800029BA
0x180002951  xor     edx, edx; lpdwProcessId
0x180002953  mov     rcx, rdi; hWnd
0x180002956  call    cs:__imp_GetWindowThreadProcessId
0x18000295c  mov     [rbx+78h], eax
0x18000295f  test    eax, eax
0x180002961  jz      short loc_18000299C
0x180002963  mov     rcx, [rbx]
0x180002966  mov     r8, rsi
0x180002969  mov     rdx, rbp
0x18000296c  mov     [rbx+50h], rdi
0x180002970  mov     rax, [rcx]
0x180002973  mov     rcx, rbx
0x180002976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000297b  mov     edi, eax
0x18000297d  test    eax, eax
0x18000297f  jns     short loc_180002998
0x180002981  mov     rcx, [rbx]
0x180002984  mov     edx, 1
0x180002989  mov     rax, [rcx+0E0h]
0x180002990  mov     rcx, rbx
0x180002993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002998  mov     eax, edi
0x18000299a  jmp     short loc_1800029BF
0x18000299c  mov     rax, [rbx]
0x18000299f  mov     edx, 1
0x1800029a4  mov     rcx, rbx
0x1800029a7  mov     rax, [rax+0E0h]
0x1800029ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029b3  mov     eax, 80004005h
0x1800029b8  jmp     short loc_1800029BF
0x1800029ba  mov     eax, 8007000Eh
0x1800029bf  add     rsp, 28h
0x1800029c3  pop     rdi
0x1800029c4  pop     rsi
0x1800029c5  pop     rbp
0x1800029c6  pop     rbx
0x1800029c7  retn
```
