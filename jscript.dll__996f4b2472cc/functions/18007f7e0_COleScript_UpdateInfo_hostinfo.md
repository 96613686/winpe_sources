# COleScript::UpdateInfo(hostinfo)

- ea: `0x18007f7e0`
- end: `0x18007f90f`
- name: `?UpdateInfo@COleScript@@UEAAJW4hostinfo@@@Z`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18007ed58`
- `0x18007f7e0`
- `0x180098010`

## import_xrefs

- `KERNEL32!IsValidCodePage` at `0x18007f88a`
- `KERNEL32!IsValidCodePage` at `0x18007f88a`
- `ole32!CoTaskMemFree` at `0x18007f8ee`
- `ole32!CoTaskMemFree` at `0x18007f8ee`

## pseudocode

```c
__int64 __fastcall COleScript::UpdateInfo(__int64 a1, unsigned int a2)
{
  int (__fastcall ***v3)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 result; // rax
  int v6; // ebp
  int v7; // ebx
  UINT v8; // ebx
  int v9; // ecx
  int v10; // eax
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  v12 = 0;
  v3 = *(int (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 96);
  pv = 0;
  if ( !v3 )
    return 2147549183LL;
  if ( (**v3)(v3, qword_1800A7DB0, &v12) < 0 )
    return 2147500037LL;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v12 + 24LL))(v12, a2, &pv);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v6 < 0 )
    return (unsigned int)v6;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v8 = *(_DWORD *)pv;
      if ( IsValidCodePage(*(_DWORD *)pv) )
      {
        v9 = 1;
        *(_DWORD *)(a1 + 172) = v8;
        *(_DWORD *)(a1 + 168) = 1;
      }
      else
      {
        v9 = 0;
      }
      v7 = -2147024809;
      if ( v9 )
        v7 = 0;
    }
    else
    {
      v7 = -2147418113;
    }
  }
  else if ( COleScript::SetCurrentLocale((COleScript *)(a1 - 80), *(_DWORD *)pv) )
  {
    v10 = *(_DWORD *)(a1 + 120);
    v7 = 0;
    *(_DWORD *)(a1 + 128) = v10;
    *(_DWORD *)(a1 + 132) = v10;
  }
  else
  {
    v7 = -2147024809;
  }
  CoTaskMemFree(pv);
  result = 0;
  if ( v7 < 0 )
    return (unsigned int)v7;
  return result;
}

```

## disassembly

```asm
0x18007f7e0  mov     [rsp+arg_8], rbx
0x18007f7e5  push    rbp
0x18007f7e6  push    rsi
0x18007f7e7  push    rdi
0x18007f7e8  sub     rsp, 20h
0x18007f7ec  mov     rdi, rcx
0x18007f7ef  mov     [rsp+38h+arg_10], 0
0x18007f7f8  mov     rcx, [rcx+60h]
0x18007f7fc  mov     ebx, edx
0x18007f7fe  mov     [rsp+38h+pv], 0
0x18007f807  test    rcx, rcx
0x18007f80a  jnz     short loc_18007F816
0x18007f80c  mov     eax, 8000FFFFh
0x18007f811  jmp     loc_18007F901
0x18007f816  mov     rax, [rcx]
0x18007f819  lea     r8, [rsp+38h+arg_10]
0x18007f81e  lea     rdx, qword_1800A7DB0
0x18007f825  mov     rax, [rax]
0x18007f828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f82d  test    eax, eax
0x18007f82f  jns     short loc_18007F83B
0x18007f831  mov     eax, 80004005h
0x18007f836  jmp     loc_18007F901
0x18007f83b  mov     rcx, [rsp+38h+arg_10]
0x18007f840  lea     r8, [rsp+38h+pv]
0x18007f845  mov     edx, ebx
0x18007f847  mov     rax, [rcx]
0x18007f84a  mov     rax, [rax+18h]
0x18007f84e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f853  mov     rcx, [rsp+38h+arg_10]
0x18007f858  mov     ebp, eax
0x18007f85a  mov     rdx, [rcx]
0x18007f85d  mov     rax, [rdx+10h]
0x18007f861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f866  test    ebp, ebp
0x18007f868  jns     short loc_18007F871
0x18007f86a  mov     eax, ebp
0x18007f86c  jmp     loc_18007F901
0x18007f871  test    ebx, ebx
0x18007f873  jz      short loc_18007F8BD
0x18007f875  cmp     ebx, 1
0x18007f878  jz      short loc_18007F881
0x18007f87a  mov     ebx, 8000FFFFh
0x18007f87f  jmp     short loc_18007F8E9
0x18007f881  mov     rax, [rsp+38h+pv]
0x18007f886  mov     ebx, [rax]
0x18007f888  mov     ecx, ebx; CodePage
0x18007f88a  call    cs:__imp_IsValidCodePage
0x18007f891  nop     dword ptr [rax+rax+00h]
0x18007f896  test    eax, eax
0x18007f898  jnz     short loc_18007F89E
0x18007f89a  xor     ecx, ecx
0x18007f89c  jmp     short loc_18007F8AF
0x18007f89e  mov     ecx, 1
0x18007f8a3  mov     [rdi+0ACh], ebx
0x18007f8a9  mov     [rdi+0A8h], ecx
0x18007f8af  xor     eax, eax
0x18007f8b1  mov     ebx, 80070057h
0x18007f8b6  test    ecx, ecx
0x18007f8b8  cmovnz  ebx, eax
0x18007f8bb  jmp     short loc_18007F8E9
0x18007f8bd  mov     rdx, [rsp+38h+pv]
0x18007f8c2  lea     rcx, [rdi-50h]; this
0x18007f8c6  mov     edx, [rdx]; unsigned int
0x18007f8c8  call    ?SetCurrentLocale@COleScript@@QEAAHK@Z; COleScript::SetCurrentLocale(ulong)
0x18007f8cd  test    eax, eax
0x18007f8cf  jnz     short loc_18007F8D8
0x18007f8d1  mov     ebx, 80070057h
0x18007f8d6  jmp     short loc_18007F8E9
0x18007f8d8  mov     eax, [rdi+78h]
0x18007f8db  xor     ebx, ebx
0x18007f8dd  mov     [rdi+80h], eax
0x18007f8e3  mov     [rdi+84h], eax
0x18007f8e9  mov     rcx, [rsp+38h+pv]; pv
0x18007f8ee  call    cs:__imp_CoTaskMemFree
0x18007f8f5  nop     dword ptr [rax+rax+00h]
0x18007f8fa  xor     eax, eax
0x18007f8fc  test    ebx, ebx
0x18007f8fe  cmovs   eax, ebx
0x18007f901  mov     rbx, [rsp+38h+arg_8]
0x18007f906  add     rsp, 20h
0x18007f90a  pop     rdi
0x18007f90b  pop     rsi
0x18007f90c  pop     rbp
0x18007f90d  retn
```
