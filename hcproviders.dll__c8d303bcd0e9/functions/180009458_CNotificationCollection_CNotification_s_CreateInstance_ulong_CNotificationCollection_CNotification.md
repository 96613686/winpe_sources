# CNotificationCollection<CNotification>::s_CreateInstance(ulong,CNotificationCollection<CNotification> * *)

- ea: `0x180009458`
- end: `0x1800094d8`
- name: `?s_CreateInstance@?$CNotificationCollection@VCNotification@@@@SAJKPEAPEAV1@@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800019f0`

## callees

- `0x180004fc8`
- `0x180008f04`
- `0x180009458`
- `0x18000b010`

## import_xrefs

- `COMCTL32!__imp_DPA_Create` at `0x18000948e`
- `COMCTL32!__imp_DPA_Create` at `0x18000948e`

## pseudocode

```c
__int64 __fastcall CNotificationCollection<CNotification>::s_CreateInstance(__int64 a1, _QWORD *a2)
{
  void *v3; // rax
  _QWORD *v4; // rdi
  HDPA v5; // rax
  unsigned int v6; // ebx

  v3 = operator new(0x18u);
  if ( v3 && (v4 = (_QWORD *)CNotificationCollection<CNotification>::CNotificationCollection<CNotification>(v3)) != 0 )
  {
    v5 = DPA_Create(1);
    v4[2] = v5;
    if ( v5 )
    {
      v6 = 0;
      *a2 = v4;
    }
    else
    {
      v6 = -2147024882;
      (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x180009458  mov     [rsp+arg_0], rbx
0x18000945d  mov     [rsp+arg_8], rsi
0x180009462  push    rdi
0x180009463  sub     rsp, 20h
0x180009467  mov     ecx, 18h; Size
0x18000946c  mov     rsi, rdx
0x18000946f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009474  test    rax, rax
0x180009477  jz      short loc_1800094C0
0x180009479  mov     rcx, rax
0x18000947c  call    ??0?$CNotificationCollection@VCNotification@@@@IEAA@XZ; CNotificationCollection<CNotification>::CNotificationCollection<CNotification>(void)
0x180009481  mov     rdi, rax
0x180009484  test    rax, rax
0x180009487  jz      short loc_1800094C0
0x180009489  mov     ecx, 1; cItemGrow
0x18000948e  call    cs:__imp_DPA_Create
0x180009495  nop     dword ptr [rax+rax+00h]
0x18000949a  mov     [rdi+10h], rax
0x18000949e  test    rax, rax
0x1800094a1  jnz     short loc_1800094B9
0x1800094a3  mov     rcx, [rdi]
0x1800094a6  mov     ebx, 8007000Eh
0x1800094ab  mov     rax, [rcx+10h]
0x1800094af  mov     rcx, rdi
0x1800094b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094b7  jmp     short loc_1800094C5
0x1800094b9  xor     ebx, ebx
0x1800094bb  mov     [rsi], rdi
0x1800094be  jmp     short loc_1800094C5
0x1800094c0  mov     ebx, 8007000Eh
0x1800094c5  mov     rsi, [rsp+28h+arg_8]
0x1800094ca  mov     eax, ebx
0x1800094cc  mov     rbx, [rsp+28h+arg_0]
0x1800094d1  add     rsp, 20h
0x1800094d5  pop     rdi
0x1800094d6  retn
```
