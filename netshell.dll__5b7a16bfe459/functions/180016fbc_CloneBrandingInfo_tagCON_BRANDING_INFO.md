# CloneBrandingInfo(tagCON_BRANDING_INFO *)

- ea: `0x180016fbc`
- end: `0x1800170a0`
- name: `?CloneBrandingInfo@@YAPEAUtagCON_BRANDING_INFO@@PEAU1@@Z`
- size: `228`
- prototype: `struct tagCON_BRANDING_INFO *__fastcall(struct tagCON_BRANDING_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180016eb4`

## callees

- `0x180016fbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180017031`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001707a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180017031`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001707a`
- `ole32!CoTaskMemFree` at `0x18001703e`
- `ole32!CoTaskMemFree` at `0x180017088`
- `ole32!CoTaskMemFree` at `0x18001703e`
- `ole32!CoTaskMemFree` at `0x180017088`
- `ole32!CoTaskMemAlloc` at `0x180016fdd`
- `ole32!CoTaskMemAlloc` at `0x18001701a`
- `ole32!CoTaskMemAlloc` at `0x180017062`
- `ole32!CoTaskMemAlloc` at `0x180016fdd`
- `ole32!CoTaskMemAlloc` at `0x18001701a`
- `ole32!CoTaskMemAlloc` at `0x180017062`

## pseudocode

```c
LPVOID *__fastcall CloneBrandingInfo(struct tagCON_BRANDING_INFO *a1)
{
  LPVOID *v3; // rax
  LPVOID *v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned int v8; // r14d
  LPVOID v9; // rax
  __int64 v10; // rax
  __int64 v11; // rsi
  LPVOID v12; // rax

  if ( !a1 )
    return 0;
  v3 = (LPVOID *)CoTaskMemAlloc(0x10u);
  v4 = v3;
  if ( v3 )
  {
    *v3 = 0;
    v5 = -1;
    v3[1] = 0;
    if ( *(_QWORD *)a1 )
    {
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v6) );
      v7 = (unsigned int)(v6 + 1);
      if ( (_DWORD)v7 )
      {
        v8 = v7;
        v9 = CoTaskMemAlloc(2 * v7);
        *v4 = v9;
        if ( v9 )
        {
          if ( (unsigned int)_o_wcscpy_s(v9, v8, *(_QWORD *)a1) )
          {
            CoTaskMemFree(*v4);
            *v4 = 0;
          }
        }
      }
    }
    v10 = *((_QWORD *)a1 + 1);
    if ( v10 )
    {
      do
        ++v5;
      while ( *(_WORD *)(v10 + 2 * v5) );
      v11 = (unsigned int)(v5 + 1);
      if ( (_DWORD)v11 )
      {
        v12 = CoTaskMemAlloc(2 * v11);
        v4[1] = v12;
        if ( v12 )
        {
          if ( (unsigned int)_o_wcscpy_s(v12, (unsigned int)v11, *((_QWORD *)a1 + 1)) )
          {
            CoTaskMemFree(v4[1]);
            v4[1] = 0;
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180016fbc  push    rbx
0x180016fbe  push    rbp
0x180016fbf  push    rsi
0x180016fc0  push    rdi
0x180016fc1  push    r14
0x180016fc3  sub     rsp, 20h
0x180016fc7  xor     ebp, ebp
0x180016fc9  mov     rdi, rcx
0x180016fcc  test    rcx, rcx
0x180016fcf  jnz     short loc_180016FD8
0x180016fd1  xor     eax, eax
0x180016fd3  jmp     loc_180017095
0x180016fd8  mov     ecx, 10h; cb
0x180016fdd  call    cs:__imp_CoTaskMemAlloc
0x180016fe3  mov     rbx, rax
0x180016fe6  test    rax, rax
0x180016fe9  jz      loc_180017092
0x180016fef  mov     [rax], rbp
0x180016ff2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016ff6  mov     [rax+8], rbp
0x180016ffa  mov     rcx, [rdi]
0x180016ffd  test    rcx, rcx
0x180017000  jz      short loc_180017047
0x180017002  mov     rax, rsi
0x180017005  inc     rax
0x180017008  cmp     [rcx+rax*2], bp
0x18001700c  jnz     short loc_180017005
0x18001700e  add     eax, 1
0x180017011  jz      short loc_180017047
0x180017013  lea     rcx, [rax+rax]; cb
0x180017017  mov     r14d, eax
0x18001701a  call    cs:__imp_CoTaskMemAlloc
0x180017020  mov     [rbx], rax
0x180017023  test    rax, rax
0x180017026  jz      short loc_180017047
0x180017028  mov     r8, [rdi]
0x18001702b  mov     edx, r14d
0x18001702e  mov     rcx, rax
0x180017031  call    cs:__imp__o_wcscpy_s
0x180017037  test    eax, eax
0x180017039  jz      short loc_180017047
0x18001703b  mov     rcx, [rbx]; pv
0x18001703e  call    cs:__imp_CoTaskMemFree
0x180017044  mov     [rbx], rbp
0x180017047  mov     rax, [rdi+8]
0x18001704b  test    rax, rax
0x18001704e  jz      short loc_180017092
0x180017050  inc     rsi
0x180017053  cmp     [rax+rsi*2], bp
0x180017057  jnz     short loc_180017050
0x180017059  add     esi, 1
0x18001705c  jz      short loc_180017092
0x18001705e  lea     rcx, [rsi+rsi]; cb
0x180017062  call    cs:__imp_CoTaskMemAlloc
0x180017068  mov     [rbx+8], rax
0x18001706c  test    rax, rax
0x18001706f  jz      short loc_180017092
0x180017071  mov     r8, [rdi+8]
0x180017075  mov     edx, esi
0x180017077  mov     rcx, rax
0x18001707a  call    cs:__imp__o_wcscpy_s
0x180017080  test    eax, eax
0x180017082  jz      short loc_180017092
0x180017084  mov     rcx, [rbx+8]; pv
0x180017088  call    cs:__imp_CoTaskMemFree
0x18001708e  mov     [rbx+8], rbp
0x180017092  mov     rax, rbx
0x180017095  add     rsp, 20h
0x180017099  pop     r14
0x18001709b  pop     rdi
0x18001709c  pop     rsi
0x18001709d  pop     rbp
0x18001709e  pop     rbx
0x18001709f  retn
```
