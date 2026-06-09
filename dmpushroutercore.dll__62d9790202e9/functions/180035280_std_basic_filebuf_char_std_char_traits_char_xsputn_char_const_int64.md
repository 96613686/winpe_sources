# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x180035280`
- end: `0x18003532b`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800064a2`
- `0x180035280`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18003530f`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18003530f`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x18003529d`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x18003529d`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsputn(__int64 a1, char *a2, __int64 a3)
{
  __int64 v3; // rbx
  char *v4; // rsi
  void *v8; // r9
  int v9; // ecx
  size_t v10; // r15
  __int64 v11; // r9

  v3 = a3;
  v4 = a2;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsputn();
  v8 = **(void ***)(a1 + 64);
  if ( v8 )
    v9 = **(_DWORD **)(a1 + 88);
  else
    v9 = 0;
  if ( a3 > 0 )
  {
    if ( v9 > 0 )
    {
      v10 = v9;
      if ( a3 < v9 )
        v10 = a3;
      memcpy_0(v8, a2, v10);
      v3 -= v10;
      **(_DWORD **)(a1 + 88) -= v10;
      **(_QWORD **)(a1 + 64) += (int)v10;
      if ( v3 <= 0 )
        return a3 - v3;
      v4 += v10;
    }
    v11 = *(_QWORD *)(a1 + 128);
    if ( v11 )
      v3 -= _o_fwrite(v4, 1, v3, v11);
  }
  return a3 - v3;
}

```

## disassembly

```asm
0x180035280  push    rbx
0x180035282  push    rbp
0x180035283  push    rsi
0x180035284  push    rdi
0x180035285  push    r14
0x180035287  push    r15
0x180035289  sub     rsp, 28h
0x18003528d  cmp     qword ptr [rcx+68h], 0
0x180035292  mov     rbx, r8
0x180035295  mov     rsi, rdx
0x180035298  mov     rdi, rcx
0x18003529b  jz      short loc_1800352A5
0x18003529d  call    cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x1800352a3  jmp     short loc_18003531E
0x1800352a5  mov     rax, [rcx+40h]
0x1800352a9  mov     rbp, rbx
0x1800352ac  mov     r9, [rax]
0x1800352af  test    r9, r9
0x1800352b2  jz      short loc_1800352BC
0x1800352b4  mov     rax, [rcx+58h]
0x1800352b8  mov     ecx, [rax]
0x1800352ba  jmp     short loc_1800352BE
0x1800352bc  xor     ecx, ecx
0x1800352be  test    rbx, rbx
0x1800352c1  jle     short loc_180035318
0x1800352c3  test    ecx, ecx
0x1800352c5  jle     short loc_1800352F8
0x1800352c7  movsxd  r15, ecx
0x1800352ca  mov     rcx, r9; void *
0x1800352cd  cmp     rbx, r15
0x1800352d0  cmovl   r15, rbx
0x1800352d4  mov     r8, r15; Size
0x1800352d7  call    memcpy_0
0x1800352dc  mov     rax, [rdi+58h]
0x1800352e0  sub     rbx, r15
0x1800352e3  sub     [rax], r15d
0x1800352e6  mov     rcx, [rdi+40h]
0x1800352ea  movsxd  rax, r15d
0x1800352ed  add     [rcx], rax
0x1800352f0  test    rbx, rbx
0x1800352f3  jle     short loc_180035318
0x1800352f5  add     rsi, r15
0x1800352f8  mov     r9, [rdi+80h]
0x1800352ff  test    r9, r9
0x180035302  jz      short loc_180035318
0x180035304  mov     r8, rbx
0x180035307  mov     edx, 1
0x18003530c  mov     rcx, rsi
0x18003530f  call    cs:__imp__o_fwrite
0x180035315  sub     rbx, rax
0x180035318  sub     rbp, rbx
0x18003531b  mov     rax, rbp
0x18003531e  add     rsp, 28h
0x180035322  pop     r15
0x180035324  pop     r14
0x180035326  pop     rdi
0x180035327  pop     rsi
0x180035328  pop     rbp
0x180035329  pop     rbx
0x18003532a  retn
```
