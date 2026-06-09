# AdvancedPage::OnDefaultProfileSelectionChanged(Combo<Profile> const &,COLORPROFILETYPE,COLORPROFILESUBTYPE,ulong)

- ea: `0x1800102b4`
- end: `0x180010380`
- name: `?OnDefaultProfileSelectionChanged@AdvancedPage@@AEAAJAEBV?$Combo@UProfile@@@@W4COLORPROFILETYPE@@W4COLORPROFILESUBTYPE@@K@Z`
- size: `204`
- prototype: `__int64 __fastcall(__int64, HWND *, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fc80`

## callees

- `0x1800102b4`
- `0x180019010`

## import_xrefs

- `USER32!SendMessageW` at `0x1800102d7`
- `USER32!SendMessageW` at `0x1800102f4`
- `USER32!SendMessageW` at `0x1800102d7`
- `USER32!SendMessageW` at `0x1800102f4`

## pseudocode

```c
__int64 __fastcall AdvancedPage::OnDefaultProfileSelectionChanged(
        __int64 a1,
        HWND *a2,
        unsigned int a3,
        unsigned int a4,
        int a5)
{
  int v9; // eax
  unsigned int *v10; // rcx
  _DWORD *v12; // rdx

  v9 = SendMessageW(*a2, 0x147u, 0, 0);
  if ( v9 == -1 )
    return 0;
  v10 = (unsigned int *)SendMessageW(*a2, 0x150u, v9, 0);
  if ( v10 == (unsigned int *)-1LL )
    return 2147500037LL;
  if ( *(_DWORD *)(a1 + 32) == 1 )
    v12 = (_DWORD *)((unsigned __int64)(v10 + 133) & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64));
  else
    v12 = v10 + 133;
  if ( v10 && a3 == 1 && *v10 <= 1 )
    a3 = *v10;
  return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, _DWORD *))(**(_QWORD **)(*(_QWORD *)(a1 + 24)
                                                                                                + 16LL)
                                                                                  + 72LL))(
           *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL),
           *(unsigned int *)(a1 + 32),
           a3,
           a4,
           a5,
           v12);
}

```

## disassembly

```asm
0x1800102b4  push    rbx
0x1800102b6  push    rbp
0x1800102b7  push    rsi
0x1800102b8  push    rdi
0x1800102b9  sub     rsp, 48h
0x1800102bd  mov     rbx, rdx
0x1800102c0  mov     ebp, r9d
0x1800102c3  mov     edi, r8d
0x1800102c6  mov     rsi, rcx
0x1800102c9  xor     r9d, r9d; lParam
0x1800102cc  xor     r8d, r8d; wParam
0x1800102cf  mov     edx, 147h; Msg
0x1800102d4  mov     rcx, [rbx]; hWnd
0x1800102d7  call    cs:__imp_SendMessageW
0x1800102dd  cmp     eax, 0FFFFFFFFh
0x1800102e0  jz      loc_180010373
0x1800102e6  mov     rcx, [rbx]; hWnd
0x1800102e9  xor     r9d, r9d; lParam
0x1800102ec  movsxd  r8, eax; wParam
0x1800102ef  mov     edx, 150h; Msg
0x1800102f4  call    cs:__imp_SendMessageW
0x1800102fa  xor     ebx, ebx
0x1800102fc  mov     edx, 80004005h
0x180010301  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010305  mov     rcx, rax
0x180010308  cmovz   rcx, rbx
0x18001030c  cmovnz  edx, ebx
0x18001030f  jnz     short loc_180010315
0x180010311  mov     eax, edx
0x180010313  jmp     short loc_180010377
0x180010315  cmp     dword ptr [rsi+20h], 1
0x180010319  lea     r8, [rcx+214h]
0x180010320  jnz     short loc_180010330
0x180010322  mov     rax, rcx
0x180010325  neg     rax
0x180010328  sbb     rdx, rdx
0x18001032b  and     rdx, r8
0x18001032e  jmp     short loc_180010333
0x180010330  mov     rdx, r8
0x180010333  test    rcx, rcx
0x180010336  jz      short loc_180010342
0x180010338  cmp     edi, 1
0x18001033b  jnz     short loc_180010342
0x18001033d  cmp     [rcx], edi
0x18001033f  cmovbe  edi, [rcx]
0x180010342  mov     rax, [rsi+18h]
0x180010346  mov     r9d, ebp
0x180010349  mov     r8d, [rsp+68h+arg_20]
0x180010351  mov     [rsp+68h+var_40], rdx
0x180010356  mov     edx, [rsi+20h]
0x180010359  mov     rcx, [rax+10h]
0x18001035d  mov     [rsp+68h+var_48], r8d
0x180010362  mov     r8d, edi
0x180010365  mov     rax, [rcx]
0x180010368  mov     rax, [rax+48h]
0x18001036c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010371  jmp     short loc_180010377
0x180010373  xor     ebx, ebx
0x180010375  mov     eax, ebx
0x180010377  add     rsp, 48h
0x18001037b  pop     rdi
0x18001037c  pop     rsi
0x18001037d  pop     rbp
0x18001037e  pop     rbx
0x18001037f  retn
```
