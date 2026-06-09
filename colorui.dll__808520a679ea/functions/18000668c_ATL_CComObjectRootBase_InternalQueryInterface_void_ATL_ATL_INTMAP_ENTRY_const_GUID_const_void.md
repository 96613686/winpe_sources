# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000668c`
- end: `0x180006790`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007730`
- `0x180007760`
- `0x180007780`
- `0x1800077b0`
- `0x1800077e0`

## callees

- `0x18000668c`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  __int64 result; // rax
  __int64 v9; // rbx
  char *v10; // rbx
  _DWORD *v11; // rcx
  int v12; // ebp
  __int64 (__fastcall *v13)(char *, const struct _GUID *, char **, _QWORD); // rax

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v9 = *((_QWORD *)a2 + 1);
    goto LABEL_9;
  }
  if ( !*((_QWORD *)a2 + 2) )
    return 2147500034LL;
  while ( 1 )
  {
    v11 = *(_DWORD **)v6;
    if ( *(_QWORD *)v6 )
    {
      if ( *v11 != a3->Data1
        || v11[1] != *(_DWORD *)&a3->Data2
        || v11[2] != *(_DWORD *)a3->Data4
        || v11[3] != *(_DWORD *)&a3->Data4[4] )
      {
        goto LABEL_22;
      }
      v12 = 0;
    }
    else
    {
      v12 = 1;
    }
    v13 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
    if ( v13 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      break;
    result = v13(a1, a3, a4, *((_QWORD *)v6 + 1));
    if ( !(_DWORD)result || !v12 && (int)result < 0 )
      return result;
LABEL_22:
    v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    if ( !*((_QWORD *)v6 + 2) )
      return 2147500034LL;
  }
  v9 = *((_QWORD *)v6 + 1);
LABEL_9:
  v10 = &a1[v9];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
  result = 0;
  *a4 = v10;
  return result;
}

```

## disassembly

```asm
0x18000668c  push    rbx
0x18000668e  push    rbp
0x18000668f  push    rsi
0x180006690  push    rdi
0x180006691  push    r14
0x180006693  sub     rsp, 30h
0x180006697  mov     rsi, r9
0x18000669a  mov     rdi, r8
0x18000669d  mov     rbx, rdx
0x1800066a0  mov     r14, rcx
0x1800066a3  test    rcx, rcx
0x1800066a6  jz      loc_180006780
0x1800066ac  test    rdx, rdx
0x1800066af  jz      loc_180006780
0x1800066b5  test    r9, r9
0x1800066b8  jnz     short loc_1800066C4
0x1800066ba  mov     eax, 80004003h
0x1800066bf  jmp     loc_180006785
0x1800066c4  mov     qword ptr [r9], 0
0x1800066cb  cmp     dword ptr [r8], 0
0x1800066cf  jnz     short loc_180006709
0x1800066d1  cmp     dword ptr [r8+4], 0
0x1800066d6  jnz     short loc_180006709
0x1800066d8  cmp     dword ptr [r8+8], 0C0h
0x1800066e0  jnz     short loc_180006709
0x1800066e2  cmp     dword ptr [r8+0Ch], 46000000h
0x1800066ea  jnz     short loc_180006709
0x1800066ec  mov     rbx, [rdx+8]
0x1800066f0  add     rbx, r14
0x1800066f3  mov     rcx, rbx
0x1800066f6  mov     rax, [rbx]
0x1800066f9  mov     rax, [rax+8]
0x1800066fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006702  xor     eax, eax
0x180006704  mov     [rsi], rbx
0x180006707  jmp     short loc_180006785
0x180006709  cmp     qword ptr [rdx+10h], 0
0x18000670e  jz      short loc_180006770
0x180006710  mov     rcx, [rbx]
0x180006713  test    rcx, rcx
0x180006716  jnz     short loc_18000671D
0x180006718  lea     ebp, [rcx+1]
0x18000671b  jmp     short loc_18000673D
0x18000671d  mov     eax, [rdi]
0x18000671f  cmp     [rcx], eax
0x180006721  jnz     short loc_180006765
0x180006723  mov     eax, [rdi+4]
0x180006726  cmp     [rcx+4], eax
0x180006729  jnz     short loc_180006765
0x18000672b  mov     eax, [rdi+8]
0x18000672e  cmp     [rcx+8], eax
0x180006731  jnz     short loc_180006765
0x180006733  mov     eax, [rdi+0Ch]
0x180006736  cmp     [rcx+0Ch], eax
0x180006739  jnz     short loc_180006765
0x18000673b  xor     ebp, ebp
0x18000673d  mov     rax, [rbx+10h]
0x180006741  cmp     rax, 1
0x180006745  jz      short loc_180006777
0x180006747  mov     r9, [rbx+8]
0x18000674b  mov     r8, rsi
0x18000674e  mov     rdx, rdi
0x180006751  mov     rcx, r14
0x180006754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006759  test    eax, eax
0x18000675b  jz      short loc_180006785
0x18000675d  test    ebp, ebp
0x18000675f  jnz     short loc_180006765
0x180006761  test    eax, eax
0x180006763  js      short loc_180006785
0x180006765  add     rbx, 18h
0x180006769  cmp     qword ptr [rbx+10h], 0
0x18000676e  jnz     short loc_180006710
0x180006770  mov     eax, 80004002h
0x180006775  jmp     short loc_180006785
0x180006777  mov     rbx, [rbx+8]
0x18000677b  jmp     loc_1800066F0
0x180006780  mov     eax, 80070057h
0x180006785  add     rsp, 30h
0x180006789  pop     r14
0x18000678b  pop     rdi
0x18000678c  pop     rsi
0x18000678d  pop     rbp
0x18000678e  pop     rbx
0x18000678f  retn
```
