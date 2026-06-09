# TComObject<NOutermost::CDevice>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002260`
- end: `0x1800023ae`
- name: `?QueryInterface@?$TComObject@VCDevice@NOutermost@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002260`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall TComObject<NOutermost::CDevice>::QueryInterface(char *a1, _DWORD *a2, char **a3)
{
  GUID **i; // rbx
  GUID *v7; // r10
  GUID *v8; // rcx
  int v9; // ebp
  __int64 result; // rax
  char *v11; // rbx

  if ( a1 )
  {
    if ( !a3 )
      return 2147500035LL;
    *a3 = 0;
    if ( !*a2 && !a2[1] && a2[2] == 192 && a2[3] == 1174405120 )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
      *a3 = a1;
      return 0;
    }
    for ( i = &`NOutermost::CDevice::_GetEntries'::`2'::_entries; ; i += 3 )
    {
      v7 = i[2];
      if ( !v7 )
        return 2147500034LL;
      v8 = *i;
      if ( *i )
      {
        if ( v8->Data1 != *a2
          || *(_DWORD *)&v8->Data2 != a2[1]
          || *(_DWORD *)v8->Data4 != a2[2]
          || *(_DWORD *)&v8->Data4[4] != a2[3] )
        {
          continue;
        }
        v9 = 0;
      }
      else
      {
        v9 = 1;
      }
      if ( v7 == (GUID *)1 )
      {
        v11 = (char *)i[1] + (_QWORD)a1;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
        *a3 = v11;
        return 0;
      }
      result = ((__int64 (__fastcall *)(char *, _DWORD *, char **, GUID *))i[2])(a1, a2, a3, i[1]);
      if ( !(_DWORD)result || !v9 && (int)result < 0 )
        return result;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180002260  push    rbx
0x180002262  push    rbp
0x180002263  push    rsi
0x180002264  push    rdi
0x180002265  push    r14
0x180002267  sub     rsp, 30h
0x18000226b  mov     rdi, r8
0x18000226e  mov     rsi, rdx
0x180002271  mov     r14, rcx
0x180002274  test    rcx, rcx
0x180002277  jz      loc_1800023A4
0x18000227d  test    r8, r8
0x180002280  jz      loc_180002343
0x180002286  mov     qword ptr [r8], 0
0x18000228d  cmp     dword ptr [rdx], 0
0x180002290  jz      short loc_180002307
0x180002292  lea     rbx, ?_entries@?1??_GetEntries@CDevice@NOutermost@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU45@B; ATL::_ATL_INTMAP_ENTRY const near * const `NOutermost::CDevice::_GetEntries(void)'::`2'::_entries
0x180002299  mov     r10, [rbx+10h]
0x18000229d  test    r10, r10
0x1800022a0  jz      short loc_1800022F7
0x1800022a2  mov     rcx, [rbx]
0x1800022a5  test    rcx, rcx
0x1800022a8  jz      short loc_1800022BA
0x1800022aa  mov     eax, [rsi]
0x1800022ac  cmp     [rcx], eax
0x1800022ae  jz      loc_180002353
0x1800022b4  add     rbx, 18h
0x1800022b8  jmp     short loc_180002299
0x1800022ba  mov     ebp, 1
0x1800022bf  cmp     r10, 1
0x1800022c3  jz      loc_18000237E
0x1800022c9  mov     r9, [rbx+8]
0x1800022cd  mov     r8, rdi
0x1800022d0  mov     rdx, rsi
0x1800022d3  mov     rcx, r14
0x1800022d6  mov     rax, r10
0x1800022d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022de  test    eax, eax
0x1800022e0  jnz     short loc_1800022ED
0x1800022e2  add     rsp, 30h
0x1800022e6  pop     r14
0x1800022e8  pop     rdi
0x1800022e9  pop     rsi
0x1800022ea  pop     rbp
0x1800022eb  pop     rbx
0x1800022ec  retn
0x1800022ed  test    ebp, ebp
0x1800022ef  jnz     short loc_1800022B4
0x1800022f1  test    eax, eax
0x1800022f3  jns     short loc_1800022B4
0x1800022f5  jmp     short loc_1800022E2
0x1800022f7  mov     eax, 80004002h
0x1800022fc  add     rsp, 30h
0x180002300  pop     r14
0x180002302  pop     rdi
0x180002303  pop     rsi
0x180002304  pop     rbp
0x180002305  pop     rbx
0x180002306  retn
0x180002307  cmp     dword ptr [rdx+4], 0
0x18000230b  jnz     short loc_180002292
0x18000230d  cmp     dword ptr [rdx+8], 0C0h
0x180002314  jnz     loc_180002292
0x18000231a  cmp     dword ptr [rdx+0Ch], 46000000h
0x180002321  jnz     loc_180002292
0x180002327  mov     rax, [rcx]
0x18000232a  mov     rax, [rax+8]
0x18000232e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002333  mov     [rdi], r14
0x180002336  xor     eax, eax
0x180002338  add     rsp, 30h
0x18000233c  pop     r14
0x18000233e  pop     rdi
0x18000233f  pop     rsi
0x180002340  pop     rbp
0x180002341  pop     rbx
0x180002342  retn
0x180002343  mov     eax, 80004003h
0x180002348  add     rsp, 30h
0x18000234c  pop     r14
0x18000234e  pop     rdi
0x18000234f  pop     rsi
0x180002350  pop     rbp
0x180002351  pop     rbx
0x180002352  retn
0x180002353  mov     eax, [rsi+4]
0x180002356  cmp     [rcx+4], eax
0x180002359  jnz     loc_1800022B4
0x18000235f  mov     eax, [rsi+8]
0x180002362  cmp     [rcx+8], eax
0x180002365  jnz     loc_1800022B4
0x18000236b  mov     eax, [rsi+0Ch]
0x18000236e  cmp     [rcx+0Ch], eax
0x180002371  jnz     loc_1800022B4
0x180002377  xor     ebp, ebp
0x180002379  jmp     loc_1800022BF
0x18000237e  mov     rbx, [rbx+8]
0x180002382  add     rbx, r14
0x180002385  mov     rax, [rbx]
0x180002388  mov     rcx, rbx
0x18000238b  mov     rax, [rax+8]
0x18000238f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002394  mov     [rdi], rbx
0x180002397  xor     eax, eax
0x180002399  add     rsp, 30h
0x18000239d  pop     r14
0x18000239f  pop     rdi
0x1800023a0  pop     rsi
0x1800023a1  pop     rbp
0x1800023a2  pop     rbx
0x1800023a3  retn
0x1800023a4  mov     eax, 80070057h
0x1800023a9  jmp     loc_1800022E2
```
