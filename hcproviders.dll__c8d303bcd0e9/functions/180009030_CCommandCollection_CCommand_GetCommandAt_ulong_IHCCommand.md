# CCommandCollection<CCommand>::GetCommandAt(ulong,IHCCommand * *)

- ea: `0x180009030`
- end: `0x1800090a5`
- name: `?GetCommandAt@?$CCommandCollection@VCCommand@@@@UEAAJKPEAPEAUIHCCommand@@@Z`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009030`
- `0x18000b010`

## import_xrefs

- `COMCTL32!__imp_DPA_GetPtr` at `0x180009043`
- `COMCTL32!__imp_DPA_GetPtr` at `0x180009043`

## pseudocode

```c
__int64 __fastcall CCommandCollection<CCommand>::GetCommandAt(__int64 a1, unsigned int a2, __int64 a3)
{
  _QWORD *Ptr; // rax
  char *v5; // rbx
  unsigned int v6; // edi

  Ptr = DPA_GetPtr(*(HDPA *)(a1 + 16), a2);
  if ( Ptr )
  {
    v5 = (char *)(Ptr + 4);
    (*(void (__fastcall **)(_QWORD *))(Ptr[4] + 8LL))(Ptr + 4);
    v6 = (**(__int64 (__fastcall ***)(char *, GUID *, __int64))v5)(v5, &GUID_3d2eafc0_96d0_4925_9f7d_ff80b168f243, a3);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180009030  mov     [rsp+arg_0], rbx
0x180009035  push    rdi
0x180009036  sub     rsp, 20h
0x18000903a  mov     rcx, [rcx+10h]; hdpa
0x18000903e  mov     rdi, r8
0x180009041  mov     edx, edx; i
0x180009043  call    cs:__imp_DPA_GetPtr
0x18000904a  nop     dword ptr [rax+rax+00h]
0x18000904f  test    rax, rax
0x180009052  jz      short loc_180009092
0x180009054  lea     rbx, [rax+20h]
0x180009058  mov     rax, [rbx]
0x18000905b  mov     rcx, rbx
0x18000905e  mov     rax, [rax+8]
0x180009062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009067  mov     rax, [rbx]
0x18000906a  lea     rdx, _GUID_3d2eafc0_96d0_4925_9f7d_ff80b168f243
0x180009071  mov     r8, rdi
0x180009074  mov     rcx, rbx
0x180009077  mov     rax, [rax]
0x18000907a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000907f  mov     rdx, [rbx]
0x180009082  mov     edi, eax
0x180009084  mov     rcx, rbx
0x180009087  mov     rax, [rdx+10h]
0x18000908b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009090  jmp     short loc_180009097
0x180009092  mov     edi, 80070057h
0x180009097  mov     rbx, [rsp+28h+arg_0]
0x18000909c  mov     eax, edi
0x18000909e  add     rsp, 20h
0x1800090a2  pop     rdi
0x1800090a3  retn
```
