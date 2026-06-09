# CreateDataView(void *,MsgBase *,_ALPC_MESSAGE_ATTRIBUTES *,void * &)

- ea: `0x180043548`
- end: `0x180043666`
- name: `?CreateDataView@@YAJPEAXPEAUMsgBase@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@AEAPEAX@Z`
- size: `286`
- prototype: `__int64 __fastcall(void *, struct MsgBase *, struct _ALPC_MESSAGE_ATTRIBUTES *, void **)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f170`
- `0x18000fcf0`
- `0x18002f140`
- `0x18002ff70`
- `0x180040760`
- `0x180042cdc`
- `0x1800432a0`

## callees

- `0x180043548`
- `0x18009eac6`

## import_xrefs

- `ntdll!AlpcGetMessageAttribute` at `0x18004357b`
- `ntdll!AlpcGetMessageAttribute` at `0x18004357b`
- `ntdll!NtAlpcCreatePortSection` at `0x1800435b4`
- `ntdll!NtAlpcCreatePortSection` at `0x1800435b4`
- `ntdll!NtAlpcCreateSectionView` at `0x1800435ef`
- `ntdll!NtAlpcCreateSectionView` at `0x1800435ef`
- `ntdll!NtAlpcDeletePortSection` at `0x180043646`
- `ntdll!NtAlpcDeletePortSection` at `0x180043646`

## pseudocode

```c
__int64 __fastcall CreateDataView(void *a1, const void **a2, struct _ALPC_MESSAGE_ATTRIBUTES *a3, void **a4)
{
  __int64 MessageAttribute; // rbx
  __int64 v9; // r9
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF

  *a4 = 0;
  *((_DWORD *)a3 + 1) &= ~0x40000000u;
  MessageAttribute = AlpcGetMessageAttribute(a3, 0x40000000);
  if ( !MessageAttribute )
    return 2147500037LL;
  v9 = *((unsigned int *)a2 + 15);
  v11 = 0;
  if ( (int)NtAlpcCreatePortSection(a1, 0x40000, 0, v9, a4, &v11) < 0 || !*a4 )
    return 2147500037LL;
  *(_QWORD *)(MessageAttribute + 8) = *a4;
  *(_QWORD *)(MessageAttribute + 16) = 0;
  *(_QWORD *)(MessageAttribute + 24) = *((unsigned int *)a2 + 15);
  *(_DWORD *)MessageAttribute = 0;
  if ( (int)NtAlpcCreateSectionView(a1, 0, MessageAttribute) >= 0 && *(_QWORD *)(MessageAttribute + 16) )
  {
    *(_DWORD *)MessageAttribute = 0x20000;
    *((_DWORD *)a3 + 1) |= 0x40000000u;
    memcpy_0(*(void **)(MessageAttribute + 16), a2[8], *((unsigned int *)a2 + 15));
  }
  else
  {
    NtAlpcDeletePortSection(a1, 0);
    *a4 = 0;
    *(_OWORD *)MessageAttribute = 0;
    *(_OWORD *)(MessageAttribute + 16) = 0;
  }
  return *a4 == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180043548  mov     [rsp+arg_0], rbx
0x18004354d  mov     [rsp+arg_8], rbp
0x180043552  push    rsi
0x180043553  push    rdi
0x180043554  push    r14
0x180043556  sub     rsp, 30h
0x18004355a  mov     rbp, rdx
0x18004355d  mov     qword ptr [r9], 0
0x180043564  btr     dword ptr [r8+4], 1Eh
0x18004356a  mov     r14, rcx
0x18004356d  mov     edx, 40000000h
0x180043572  mov     rcx, r8
0x180043575  mov     rdi, r9
0x180043578  mov     rsi, r8
0x18004357b  call    cs:__imp_AlpcGetMessageAttribute
0x180043581  mov     rbx, rax
0x180043584  test    rax, rax
0x180043587  jz      loc_18004365F
0x18004358d  mov     r9d, [rbp+3Ch]
0x180043591  lea     rax, [rsp+48h+arg_10]
0x180043596  mov     [rsp+48h+var_20], rax
0x18004359b  xor     r8d, r8d
0x18004359e  mov     edx, 40000h
0x1800435a3  mov     [rsp+48h+var_28], rdi
0x1800435a8  mov     rcx, r14
0x1800435ab  mov     [rsp+48h+arg_10], 0
0x1800435b4  call    cs:__imp_NtAlpcCreatePortSection
0x1800435ba  test    eax, eax
0x1800435bc  js      loc_18004365F
0x1800435c2  mov     rax, [rdi]
0x1800435c5  test    rax, rax
0x1800435c8  jz      loc_18004365F
0x1800435ce  mov     [rbx+8], rax
0x1800435d2  mov     r8, rbx
0x1800435d5  mov     qword ptr [rbx+10h], 0
0x1800435dd  xor     edx, edx
0x1800435df  mov     eax, [rbp+3Ch]
0x1800435e2  mov     rcx, r14
0x1800435e5  mov     [rbx+18h], rax
0x1800435e9  mov     dword ptr [rbx], 0
0x1800435ef  call    cs:__imp_NtAlpcCreateSectionView
0x1800435f5  test    eax, eax
0x1800435f7  js      short loc_18004363E
0x1800435f9  cmp     qword ptr [rbx+10h], 0
0x1800435fe  jz      short loc_18004363E
0x180043600  mov     dword ptr [rbx], 20000h
0x180043606  bts     dword ptr [rsi+4], 1Eh
0x18004360b  mov     r8d, [rbp+3Ch]; Size
0x18004360f  mov     rdx, [rbp+40h]; Src
0x180043613  mov     rcx, [rbx+10h]; void *
0x180043617  call    memcpy_0
0x18004361c  mov     rax, [rdi]
0x18004361f  neg     rax
0x180043622  sbb     eax, eax
0x180043624  not     eax
0x180043626  and     eax, 80004005h
0x18004362b  mov     rbx, [rsp+48h+arg_0]
0x180043630  mov     rbp, [rsp+48h+arg_8]
0x180043635  add     rsp, 30h
0x180043639  pop     r14
0x18004363b  pop     rdi
0x18004363c  pop     rsi
0x18004363d  retn
0x18004363e  mov     r8, [rdi]
0x180043641  xor     edx, edx
0x180043643  mov     rcx, r14
0x180043646  call    cs:__imp_NtAlpcDeletePortSection
0x18004364c  xorps   xmm0, xmm0
0x18004364f  mov     qword ptr [rdi], 0
0x180043656  movups  xmmword ptr [rbx], xmm0
0x180043659  movups  xmmword ptr [rbx+10h], xmm0
0x18004365d  jmp     short loc_18004361C
0x18004365f  mov     eax, 80004005h
0x180043664  jmp     short loc_18004362B
```
