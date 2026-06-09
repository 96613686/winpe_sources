# ValidateAllowedCsp(IXmlReader *,ushort const * *,ulong)

- ea: `0x1800021e0`
- end: `0x1800022ef`
- name: `?ValidateAllowedCsp@@YAJPEAUIXmlReader@@PEAPEBGK@Z`
- size: `271`
- prototype: `__int64 __fastcall(struct IXmlReader *, const unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002300`

## callees

- `0x1800021e0`
- `0x180008010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002257`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800022d2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002257`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800022d2`

## pseudocode

```c
__int64 __fastcall ValidateAllowedCsp(struct IXmlReader *a1, const unsigned __int16 **a2, unsigned int a3)
{
  struct IXmlReaderVtbl *lpVtbl; // rax
  int i; // eax
  int v9; // ebx
  const unsigned __int16 *v10; // rdx
  __int64 v11; // r8
  const unsigned __int16 *v12; // rax
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+58h] [rbp+20h] BYREF

  lpVtbl = a1->lpVtbl;
  v13 = 0;
  v14 = 0;
  for ( i = ((__int64 (__fastcall *)(struct IXmlReader *))lpVtbl->MoveToFirstAttribute)(a1);
        ;
        i = ((__int64 (__fastcall *)(struct IXmlReader *))a1->lpVtbl->MoveToNextAttribute)(a1) )
  {
    if ( i )
      return 2147942405LL;
    if ( ((int (__fastcall *)(struct IXmlReader *, __int64 *, _QWORD))a1->lpVtbl->GetLocalName)(a1, &v13, 0) < 0
      || ((int (__fastcall *)(struct IXmlReader *, __int64 *, _QWORD))a1->lpVtbl->GetValue)(a1, &v14, 0) < 0 )
    {
      return 2147549183LL;
    }
    if ( !(unsigned int)_o__wcsicmp(L"type", v13) )
      break;
  }
  v9 = 0;
  if ( !a3 )
    return 2147942405LL;
  while ( 1 )
  {
    v10 = a2[v9];
    if ( !v10 )
      break;
    v11 = 0x7FFFFFFF;
    v12 = a2[v9];
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    if ( !v11 || ((0x7FFFFFFF - v11) & -(__int64)(v11 != 0)) == 0 )
      break;
    if ( !(unsigned int)_o__wcsicmp(v14, v10) )
      return 0;
    if ( ++v9 >= a3 )
      return 2147942405LL;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800021e0  mov     [rsp+arg_8], rbx
0x1800021e5  push    rbp
0x1800021e6  push    rsi
0x1800021e7  push    rdi
0x1800021e8  sub     rsp, 20h
0x1800021ec  mov     rax, [rcx]
0x1800021ef  xor     ebp, ebp
0x1800021f1  mov     edi, r8d
0x1800021f4  mov     [rsp+38h+arg_0], rbp
0x1800021f9  mov     rsi, rdx
0x1800021fc  mov     [rsp+38h+arg_18], rbp
0x180002201  mov     rbx, rcx
0x180002204  mov     rax, [rax+40h]
0x180002208  jmp     short loc_18000226B
0x18000220a  mov     rax, [rbx]
0x18000220d  lea     rdx, [rsp+38h+arg_0]
0x180002212  xor     r8d, r8d
0x180002215  mov     rcx, rbx
0x180002218  mov     rax, [rax+70h]
0x18000221c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002221  test    eax, eax
0x180002223  js      loc_1800022E8
0x180002229  mov     rax, [rbx]
0x18000222c  lea     rdx, [rsp+38h+arg_18]
0x180002231  xor     r8d, r8d
0x180002234  mov     rcx, rbx
0x180002237  mov     rax, [rax+80h]
0x18000223e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002243  test    eax, eax
0x180002245  js      loc_1800022E8
0x18000224b  mov     rdx, [rsp+38h+arg_0]
0x180002250  lea     rcx, aType; "type"
0x180002257  call    cs:__imp__o__wcsicmp
0x18000225d  test    eax, eax
0x18000225f  jz      short loc_180002286
0x180002261  mov     rax, [rbx]
0x180002264  mov     rcx, rbx
0x180002267  mov     rax, [rax+48h]
0x18000226b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002270  test    eax, eax
0x180002272  jz      short loc_18000220A
0x180002274  mov     eax, 80070005h
0x180002279  mov     rbx, [rsp+38h+arg_8]
0x18000227e  add     rsp, 20h
0x180002282  pop     rdi
0x180002283  pop     rsi
0x180002284  pop     rbp
0x180002285  retn
0x180002286  mov     ebx, ebp
0x180002288  test    edi, edi
0x18000228a  jz      short loc_180002274
0x18000228c  mov     eax, ebx
0x18000228e  mov     rdx, [rsi+rax*8]
0x180002292  test    rdx, rdx
0x180002295  jz      short loc_1800022E8
0x180002297  mov     r8d, 7FFFFFFFh
0x18000229d  mov     rax, rdx
0x1800022a0  cmp     [rax], bp
0x1800022a3  jz      short loc_1800022AF
0x1800022a5  add     rax, 2
0x1800022a9  sub     r8, 1
0x1800022ad  jnz     short loc_1800022A0
0x1800022af  mov     ecx, 7FFFFFFFh
0x1800022b4  mov     rax, r8
0x1800022b7  sub     rcx, r8
0x1800022ba  neg     rax
0x1800022bd  sbb     r9, r9
0x1800022c0  and     r9, rcx
0x1800022c3  test    r8, r8
0x1800022c6  jz      short loc_1800022E8
0x1800022c8  test    r9, r9
0x1800022cb  jz      short loc_1800022E8
0x1800022cd  mov     rcx, [rsp+38h+arg_18]
0x1800022d2  call    cs:__imp__o__wcsicmp
0x1800022d8  test    eax, eax
0x1800022da  jz      short loc_1800022E4
0x1800022dc  inc     ebx
0x1800022de  cmp     ebx, edi
0x1800022e0  jb      short loc_18000228C
0x1800022e2  jmp     short loc_180002274
0x1800022e4  xor     eax, eax
0x1800022e6  jmp     short loc_180002279
0x1800022e8  mov     eax, 8000FFFFh
0x1800022ed  jmp     short loc_180002279
```
