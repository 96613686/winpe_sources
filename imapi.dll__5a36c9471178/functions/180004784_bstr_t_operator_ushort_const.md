# _bstr_t::operator=(ushort const *)

- ea: `0x180004784`
- end: `0x18000483f`
- name: `??4_bstr_t@@QEAAAEAV0@PEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000689c`
- `0x18000ab90`
- `0x18000ce60`

## callees

- `0x180001144`
- `0x180001150`
- `0x18000115c`
- `0x180004784`
- `0x180017020`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000480c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000480c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047b6`

## pseudocode

```c
BSTR **__fastcall _bstr_t::operator=(BSTR **a1, const OLECHAR *a2)
{
  BSTR *v2; // rbx
  BSTR v5; // rcx
  BSTR *v6; // rax
  BSTR *v7; // rbx
  BSTR v8; // rax
  struct IErrorInfo *v9; // rdx
  __int64 v10; // rcx
  struct IErrorInfo *v11; // r8
  bool v12; // r9
  BSTR **result; // rax

  v2 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2 + 4, 0xFFFFFFFF) == 1 )
    {
      if ( *v2 )
      {
        SysFreeString(*v2);
        *v2 = 0;
      }
      v5 = v2[1];
      if ( v5 )
      {
        operator delete[](v5);
        v2[1] = 0;
      }
      operator delete(v2);
    }
    *a1 = 0;
  }
  v6 = (BSTR *)operator new(0x18u);
  v7 = v6;
  if ( v6 )
  {
    v6[1] = 0;
    *((_DWORD *)v6 + 4) = 1;
    v8 = SysAllocString(a2);
    *v7 = v8;
    if ( !v8 && a2 )
      _com_issue_error(v10, v9, v11, v12);
  }
  else
  {
    v7 = 0;
  }
  result = a1;
  *a1 = v7;
  return result;
}

```

## disassembly

```asm
0x180004784  mov     [rsp+arg_8], rbx
0x180004789  mov     [rsp+arg_10], rsi
0x18000478e  push    rdi
0x18000478f  sub     rsp, 20h
0x180004793  mov     rbx, [rcx]
0x180004796  mov     rsi, rdx
0x180004799  mov     rdi, rcx
0x18000479c  test    rbx, rbx
0x18000479f  jz      short loc_1800047E8
0x1800047a1  or      eax, 0FFFFFFFFh
0x1800047a4  lock xadd [rbx+10h], eax
0x1800047a9  cmp     eax, 1
0x1800047ac  jnz     short loc_1800047E1
0x1800047ae  mov     rcx, [rbx]; bstrString
0x1800047b1  test    rcx, rcx
0x1800047b4  jz      short loc_1800047C3
0x1800047b6  call    cs:__imp_SysFreeString
0x1800047bc  mov     qword ptr [rbx], 0
0x1800047c3  mov     rcx, [rbx+8]; Block
0x1800047c7  test    rcx, rcx
0x1800047ca  jz      short loc_1800047D9
0x1800047cc  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800047d1  mov     qword ptr [rbx+8], 0
0x1800047d9  mov     rcx, rbx; Block
0x1800047dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800047e1  mov     qword ptr [rdi], 0
0x1800047e8  mov     ecx, 18h; Size
0x1800047ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800047f2  mov     rbx, rax
0x1800047f5  test    rax, rax
0x1800047f8  jz      short loc_180004821
0x1800047fa  mov     rcx, rsi; psz
0x1800047fd  mov     qword ptr [rax+8], 0
0x180004805  mov     dword ptr [rax+10h], 1
0x18000480c  call    cs:__imp_SysAllocString
0x180004812  mov     [rbx], rax
0x180004815  test    rax, rax
0x180004818  jnz     short loc_180004823
0x18000481a  test    rsi, rsi
0x18000481d  jnz     short loc_180004839
0x18000481f  jmp     short loc_180004823
0x180004821  xor     ebx, ebx
0x180004823  mov     rsi, [rsp+28h+arg_10]
0x180004828  mov     rax, rdi
0x18000482b  mov     [rdi], rbx
0x18000482e  mov     rbx, [rsp+28h+arg_8]
0x180004833  add     rsp, 20h
0x180004837  pop     rdi
0x180004838  retn
0x180004839  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
