# CConfigAdvancedPage::OnNotify(HWND__ *,ushort,tagNMHDR *,int &)

- ea: `0x180014db0`
- end: `0x180014def`
- name: `?OnNotify@CConfigAdvancedPage@@UEAAKPEAUHWND__@@GPEAUtagNMHDR@@AEAH@Z`
- size: `63`
- prototype: `unsigned int __fastcall(CConfigAdvancedPage *__hidden this, HWND, unsigned __int16, struct tagNMHDR *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180014db0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::OnNotify(
        CConfigAdvancedPage *this,
        HWND a2,
        __int16 a3,
        struct tagNMHDR *a4,
        int *a5)
{
  if ( a3 == 4534 || a3 == 4535 )
  {
    if ( a4->code == -759 )
      (*(void (__fastcall **)(CConfigAdvancedPage *, HWND))(*(_QWORD *)this + 80LL))(this, a2);
    *a5 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180014db0  sub     rsp, 28h
0x180014db4  movzx   r10d, r8w
0x180014db8  sub     r10d, 11B6h
0x180014dbf  jz      short loc_180014DC7
0x180014dc1  cmp     r10d, 1
0x180014dc5  jnz     short loc_180014DE8
0x180014dc7  cmp     dword ptr [r9+10h], 0FFFFFD09h
0x180014dcf  jnz     short loc_180014DDD
0x180014dd1  mov     rax, [rcx]
0x180014dd4  mov     rax, [rax+50h]
0x180014dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ddd  mov     rax, [rsp+28h+arg_20]
0x180014de2  mov     dword ptr [rax], 1
0x180014de8  xor     eax, eax
0x180014dea  add     rsp, 28h
0x180014dee  retn
```
