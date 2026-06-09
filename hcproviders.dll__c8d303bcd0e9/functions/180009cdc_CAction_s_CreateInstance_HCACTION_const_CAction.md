# CAction::s_CreateInstance(HCACTION const *,CAction * *)

- ea: `0x180009cdc`
- end: `0x180009d7b`
- name: `?s_CreateInstance@CAction@@SAJPEBUHCACTION@@PEAPEAV1@@Z`
- size: `159`
- prototype: `__int64 __fastcall(const struct HCACTION *, struct CAction **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009a10`

## callees

- `0x180002300`
- `0x180004fc8`
- `0x180009cdc`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CAction::s_CreateInstance(PVOID *a1, struct CAction **a2)
{
  _QWORD *v4; // rax
  struct CAction *v5; // rbx
  int v6; // edi

  v4 = operator new(0x30u);
  v5 = (struct CAction *)v4;
  if ( v4 )
  {
    v4[2] = 0;
    v4[3] = 0;
    v4[4] = 0;
    *v4 = &CAction::`vftable'{for `IHCAction'};
    v4[1] = &CAction::`vftable'{for `CCommandImpl'};
    v4[5] = 1;
    _InterlockedIncrement(&g_cLocks);
    v6 = CCommandImpl::_Initialize((CCommandImpl *)(v4 + 1), a1);
    if ( v6 < 0 )
    {
      (*(void (__fastcall **)(struct CAction *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    else
    {
      *((_DWORD *)v5 + 11) = *((unsigned __int8 *)a1 + 24);
      *a2 = v5;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009cdc  push    rbx
0x180009cde  push    rsi
0x180009cdf  push    rdi
0x180009ce0  push    r14
0x180009ce2  sub     rsp, 28h
0x180009ce6  mov     rsi, rcx
0x180009ce9  mov     r14, rdx
0x180009cec  mov     ecx, 30h ; '0'; Size
0x180009cf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009cf6  mov     rbx, rax
0x180009cf9  test    rax, rax
0x180009cfc  jz      short loc_180009D69
0x180009cfe  mov     qword ptr [rax+10h], 0
0x180009d06  mov     qword ptr [rax+18h], 0
0x180009d0e  mov     qword ptr [rax+20h], 0
0x180009d16  lea     rax, ??_7CAction@@6BIHCAction@@@; const CAction::`vftable'{for `IHCAction'}
0x180009d1d  mov     [rbx], rax
0x180009d20  lea     rax, ??_7CAction@@6BCCommandImpl@@@; const CAction::`vftable'{for `CCommandImpl'}
0x180009d27  mov     [rbx+8], rax
0x180009d2b  mov     qword ptr [rbx+28h], 1
0x180009d33  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x180009d3a  lea     rcx, [rbx+8]; this
0x180009d3e  mov     rdx, rsi; struct HCCOMMAND *
0x180009d41  call    ?_Initialize@CCommandImpl@@MEAAJPEBUHCCOMMAND@@@Z; CCommandImpl::_Initialize(HCCOMMAND const *)
0x180009d46  mov     edi, eax
0x180009d48  test    eax, eax
0x180009d4a  js      short loc_180009D58
0x180009d4c  movzx   eax, byte ptr [rsi+18h]
0x180009d50  mov     [rbx+2Ch], eax
0x180009d53  mov     [r14], rbx
0x180009d56  jmp     short loc_180009D6E
0x180009d58  mov     rax, [rbx]
0x180009d5b  mov     rcx, rbx
0x180009d5e  mov     rax, [rax+10h]
0x180009d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d67  jmp     short loc_180009D6E
0x180009d69  mov     edi, 8007000Eh
0x180009d6e  mov     eax, edi
0x180009d70  add     rsp, 28h
0x180009d74  pop     r14
0x180009d76  pop     rdi
0x180009d77  pop     rsi
0x180009d78  pop     rbx
0x180009d79  retn
```
