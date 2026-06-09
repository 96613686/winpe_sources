# CFaxConfigUI::CleanUp(void)

- ea: `0x18000fc3c`
- end: `0x18000fcee`
- name: `?CleanUp@CFaxConfigUI@@AEAAXXZ`
- size: `178`
- prototype: `void __fastcall(CFaxConfigUI *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000fd8c`
- `0x1800101a0`

## callees

- `0x1800012d0`
- `0x18000fc3c`
- `0x180017010`

## import_xrefs

- `FXSAPI!FaxClose` at `0x18000fcb6`
- `FXSAPI!FaxClose` at `0x18000fcb6`

## pseudocode

```c
void __fastcall CFaxConfigUI::CleanUp(CFaxConfigUI *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  __int64 v3; // rdi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void *v5; // rcx

  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 3);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = 0;
  for ( *((_QWORD *)this + 3) = 0; (unsigned int)v3 < *((_DWORD *)this + 12); v3 = (unsigned int)(v3 + 1) )
  {
    v4 = *(void (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)this + 4) + 8 * v3);
    if ( v4 )
      (**v4)(v4, 1);
  }
  operator delete(*((void **)this + 4));
  v5 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 12) = 0;
  if ( v5 )
  {
    FaxClose(v5);
    *((_QWORD *)this + 7) = 0;
  }
  if ( *((_QWORD *)this + 5) )
  {
    if ( g_pFaxSecurity )
      ((void (__fastcall *)(LPSECURITYINFO))g_pFaxSecurity->lpVtbl->Release)(g_pFaxSecurity);
  }
}

```

## disassembly

```asm
0x18000fc3c  mov     [rsp+arg_0], rbx
0x18000fc41  push    rdi
0x18000fc42  sub     rsp, 20h
0x18000fc46  mov     rbx, rcx
0x18000fc49  mov     rcx, [rcx+18h]
0x18000fc4d  test    rcx, rcx
0x18000fc50  jz      short loc_18000FC62
0x18000fc52  mov     rax, [rcx]
0x18000fc55  mov     edx, 1
0x18000fc5a  mov     rax, [rax]
0x18000fc5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc62  xor     edi, edi
0x18000fc64  mov     qword ptr [rbx+18h], 0
0x18000fc6c  cmp     [rbx+30h], edi
0x18000fc6f  jbe     short loc_18000FC95
0x18000fc71  mov     rax, [rbx+20h]
0x18000fc75  mov     rcx, [rax+rdi*8]
0x18000fc79  test    rcx, rcx
0x18000fc7c  jz      short loc_18000FC8E
0x18000fc7e  mov     rax, [rcx]
0x18000fc81  mov     edx, 1
0x18000fc86  mov     rax, [rax]
0x18000fc89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc8e  inc     edi
0x18000fc90  cmp     edi, [rbx+30h]
0x18000fc93  jb      short loc_18000FC71
0x18000fc95  mov     rcx, [rbx+20h]; Block
0x18000fc99  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fc9e  mov     rcx, [rbx+38h]; FaxHandle
0x18000fca2  mov     qword ptr [rbx+20h], 0
0x18000fcaa  mov     dword ptr [rbx+30h], 0
0x18000fcb1  test    rcx, rcx
0x18000fcb4  jz      short loc_18000FCC4
0x18000fcb6  call    cs:__imp_FaxClose
0x18000fcbc  mov     qword ptr [rbx+38h], 0
0x18000fcc4  cmp     qword ptr [rbx+28h], 0
0x18000fcc9  jz      short loc_18000FCE3
0x18000fccb  mov     rcx, cs:?g_pFaxSecurity@@3PEAVCFaxSecurity@@EA; CFaxSecurity * g_pFaxSecurity
0x18000fcd2  test    rcx, rcx
0x18000fcd5  jz      short loc_18000FCE3
0x18000fcd7  mov     rax, [rcx]
0x18000fcda  mov     rax, [rax+10h]
0x18000fcde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fce3  mov     rbx, [rsp+28h+arg_0]
0x18000fce8  add     rsp, 20h
0x18000fcec  pop     rdi
0x18000fced  retn
```
