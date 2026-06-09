# COleScript::UpdateInfo(hostinfo)

- ea: `0x18007de90`
- end: `0x18007dfb2`
- name: `?UpdateInfo@COleScript@@UEAAJW4hostinfo@@@Z`
- size: `290`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18007d458`
- `0x18007de90`
- `0x180096010`

## import_xrefs

- `KERNEL32!IsValidCodePage` at `0x18007df3a`
- `KERNEL32!IsValidCodePage` at `0x18007df3a`
- `ole32!CoTaskMemFree` at `0x18007df98`
- `ole32!CoTaskMemFree` at `0x18007df98`

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
  if ( (**v3)(v3, qword_1800A5DC0, &v12) < 0 )
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
0x18007de90  mov     [rsp+arg_8], rbx
0x18007de95  push    rbp
0x18007de96  push    rsi
0x18007de97  push    rdi
0x18007de98  sub     rsp, 20h
0x18007de9c  mov     rdi, rcx
0x18007de9f  mov     [rsp+38h+arg_10], 0
0x18007dea8  mov     rcx, [rcx+60h]
0x18007deac  mov     ebx, edx
0x18007deae  mov     [rsp+38h+pv], 0
0x18007deb7  test    rcx, rcx
0x18007deba  jnz     short loc_18007DEC6
0x18007debc  mov     eax, 8000FFFFh
0x18007dec1  jmp     loc_18007DFA5
0x18007dec6  mov     rax, [rcx]
0x18007dec9  lea     r8, [rsp+38h+arg_10]
0x18007dece  lea     rdx, qword_1800A5DC0
0x18007ded5  mov     rax, [rax]
0x18007ded8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dedd  test    eax, eax
0x18007dedf  jns     short loc_18007DEEB
0x18007dee1  mov     eax, 80004005h
0x18007dee6  jmp     loc_18007DFA5
0x18007deeb  mov     rcx, [rsp+38h+arg_10]
0x18007def0  lea     r8, [rsp+38h+pv]
0x18007def5  mov     edx, ebx
0x18007def7  mov     rax, [rcx]
0x18007defa  mov     rax, [rax+18h]
0x18007defe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007df03  mov     rcx, [rsp+38h+arg_10]
0x18007df08  mov     ebp, eax
0x18007df0a  mov     rdx, [rcx]
0x18007df0d  mov     rax, [rdx+10h]
0x18007df11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007df16  test    ebp, ebp
0x18007df18  jns     short loc_18007DF21
0x18007df1a  mov     eax, ebp
0x18007df1c  jmp     loc_18007DFA5
0x18007df21  test    ebx, ebx
0x18007df23  jz      short loc_18007DF67
0x18007df25  cmp     ebx, 1
0x18007df28  jz      short loc_18007DF31
0x18007df2a  mov     ebx, 8000FFFFh
0x18007df2f  jmp     short loc_18007DF93
0x18007df31  mov     rax, [rsp+38h+pv]
0x18007df36  mov     ebx, [rax]
0x18007df38  mov     ecx, ebx; CodePage
0x18007df3a  call    cs:__imp_IsValidCodePage
0x18007df40  test    eax, eax
0x18007df42  jnz     short loc_18007DF48
0x18007df44  xor     ecx, ecx
0x18007df46  jmp     short loc_18007DF59
0x18007df48  mov     ecx, 1
0x18007df4d  mov     [rdi+0ACh], ebx
0x18007df53  mov     [rdi+0A8h], ecx
0x18007df59  xor     eax, eax
0x18007df5b  mov     ebx, 80070057h
0x18007df60  test    ecx, ecx
0x18007df62  cmovnz  ebx, eax
0x18007df65  jmp     short loc_18007DF93
0x18007df67  mov     rdx, [rsp+38h+pv]
0x18007df6c  lea     rcx, [rdi-50h]; this
0x18007df70  mov     edx, [rdx]; unsigned int
0x18007df72  call    ?SetCurrentLocale@COleScript@@QEAAHK@Z; COleScript::SetCurrentLocale(ulong)
0x18007df77  test    eax, eax
0x18007df79  jnz     short loc_18007DF82
0x18007df7b  mov     ebx, 80070057h
0x18007df80  jmp     short loc_18007DF93
0x18007df82  mov     eax, [rdi+78h]
0x18007df85  xor     ebx, ebx
0x18007df87  mov     [rdi+80h], eax
0x18007df8d  mov     [rdi+84h], eax
0x18007df93  mov     rcx, [rsp+38h+pv]; pv
0x18007df98  call    cs:__imp_CoTaskMemFree
0x18007df9e  xor     eax, eax
0x18007dfa0  test    ebx, ebx
0x18007dfa2  cmovs   eax, ebx
0x18007dfa5  mov     rbx, [rsp+38h+arg_8]
0x18007dfaa  add     rsp, 20h
0x18007dfae  pop     rdi
0x18007dfaf  pop     rsi
0x18007dfb0  pop     rbp
0x18007dfb1  retn
```
