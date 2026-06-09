# CngRsa32Compat_SHAFinal_Ex

- ea: `0x140008ffc`
- end: `0x140009043`
- name: `CngRsa32Compat_SHAFinal_Ex`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140026360`
- `0x140026464`

## callees

- `0x140008ffc`

## import_xrefs

- `cng!BCryptFinishHash` at `0x14000900f`
- `cng!BCryptFinishHash` at `0x14000900f`
- `cng!BCryptDestroyHash` at `0x140009029`
- `cng!BCryptDestroyHash` at `0x140009029`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHAFinal_Ex(BCRYPT_HASH_HANDLE *a1, UCHAR *a2)
{
  NTSTATUS result; // eax

  if ( BCryptFinishHash(*a1, a2, 0x14u, 0) < 0 )
    __fastfail(7u);
  result = BCryptDestroyHash(*a1);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x140008ffc  push    rbx
0x140008ffe  sub     rsp, 20h
0x140009002  xor     r9d, r9d; dwFlags
0x140009005  mov     rbx, rcx
0x140009008  mov     rcx, [rcx]; hHash
0x14000900b  lea     r8d, [r9+14h]; cbOutput
0x14000900f  call    cs:__imp_BCryptFinishHash
0x140009016  nop     dword ptr [rax+rax+00h]
0x14000901b  test    eax, eax
0x14000901d  jns     short loc_140009026
0x14000901f  mov     ecx, 7
0x140009024  int     29h; Win8: RtlFailFast(ecx)
0x140009026  mov     rcx, [rbx]; hHash
0x140009029  call    cs:__imp_BCryptDestroyHash
0x140009030  nop     dword ptr [rax+rax+00h]
0x140009035  mov     qword ptr [rbx], 0
0x14000903c  add     rsp, 20h
0x140009040  pop     rbx
0x140009041  retn
```
