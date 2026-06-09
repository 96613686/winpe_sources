# nfsoncrpc_rpc_create_client2

- ea: `0x14000d4f0`
- end: `0x14000d5f1`
- name: `nfsoncrpc_rpc_create_client2`
- size: `257`
- prototype: `__int64 __usercall@<rax>(PADDRINFOW *ppResult@<rcx>, char *Source@<rdx>, int, int, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c80c`

## callees

- `0x14000cf28`
- `0x14000d3a4`
- `0x14000d4f0`
- `0x14000d5f8`
- `0x14000e120`

## pseudocode

```c
char *__fastcall nfsoncrpc_rpc_create_client2(
        PADDRINFOW *ppResult,
        char *Source,
        int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        int a8)
{
  int v8; // edi
  int v13; // r14d
  unsigned __int16 v14; // ax
  char *result; // rax

  v8 = 6;
  if ( a8 == 6 )
  {
    if ( !*((_DWORD *)ppResult + 9) )
    {
      *((_DWORD *)ppResult + 5) = 1;
      *((_DWORD *)ppResult + 6) = 6;
    }
    v13 = 6;
    v8 = 17;
  }
  else
  {
    if ( a8 != 17 )
      goto LABEL_11;
    *((_DWORD *)ppResult + 5) = 2;
    v13 = 17;
    *((_DWORD *)ppResult + 6) = 17;
  }
  if ( !(unsigned int)nfsoncrpc_getaddresses(ppResult, Source) )
  {
    if ( *((_WORD *)ppResult + 38) )
      return nfsoncrpc_rpc_create_client_ex((__int64)ppResult, a3, a4, 0, 0, a7);
    v14 = nfsoncrpc_getrpcport(Source, v13, v8);
    if ( !v14 )
    {
      *((_DWORD *)ppResult + 44) = 8;
      goto LABEL_11;
    }
    nfsoncrpc_setdestport(ppResult, v14);
    if ( !(unsigned int)nfsoncrpc_getaddresses(ppResult, Source) )
      return nfsoncrpc_rpc_create_client_ex((__int64)ppResult, a3, a4, 0, 0, a7);
  }
LABEL_11:
  result = 0;
  if ( !*((_DWORD *)ppResult + 44) )
    *((_DWORD *)ppResult + 44) = 12;
  return result;
}

```

## disassembly

```asm
0x14000d4f0  push    rbx
0x14000d4f2  push    rbp
0x14000d4f3  push    rdi
0x14000d4f4  push    r12
0x14000d4f6  push    r14
0x14000d4f8  push    r15
0x14000d4fa  sub     rsp, 48h
0x14000d4fe  mov     edi, 6
0x14000d503  mov     r15d, r9d
0x14000d506  mov     r12d, r8d
0x14000d509  mov     rbp, rdx
0x14000d50c  mov     rbx, rcx
0x14000d50f  cmp     [rsp+78h+arg_38], edi
0x14000d516  jz      short loc_14000D536
0x14000d518  cmp     [rsp+78h+arg_38], 11h
0x14000d520  jnz     short loc_14000D58D
0x14000d522  mov     dword ptr [rcx+14h], 2
0x14000d529  lea     r14d, [rdi+0Bh]
0x14000d52d  mov     dword ptr [rcx+18h], 11h
0x14000d534  jmp     short loc_14000D54E
0x14000d536  cmp     dword ptr [rcx+24h], 0
0x14000d53a  jnz     short loc_14000D546
0x14000d53c  mov     dword ptr [rcx+14h], 1
0x14000d543  mov     [rcx+18h], edi
0x14000d546  mov     r14d, edi
0x14000d549  mov     edi, 11h
0x14000d54e  call    nfsoncrpc_getaddresses
0x14000d553  test    eax, eax
0x14000d555  jnz     short loc_14000D58D
0x14000d557  cmp     ax, [rbx+4Ch]
0x14000d55b  jnz     short loc_14000D5C9
0x14000d55d  mov     r9d, [rsp+78h+arg_38]
0x14000d565  mov     r8d, r15d
0x14000d568  mov     [rsp+78h+var_50], edi; int
0x14000d56c  mov     edx, r12d
0x14000d56f  mov     rcx, rbp; Source
0x14000d572  mov     [rsp+78h+var_58], r14d; int
0x14000d577  call    nfsoncrpc_getrpcport
0x14000d57c  xor     ecx, ecx
0x14000d57e  cmp     cx, ax
0x14000d581  jnz     short loc_14000D5AF
0x14000d583  mov     dword ptr [rbx+0B0h], 8
0x14000d58d  xor     eax, eax
0x14000d58f  cmp     [rbx+0B0h], eax
0x14000d595  jnz     short loc_14000D5A1
0x14000d597  mov     dword ptr [rbx+0B0h], 0Ch
0x14000d5a1  add     rsp, 48h
0x14000d5a5  pop     r15
0x14000d5a7  pop     r14
0x14000d5a9  pop     r12
0x14000d5ab  pop     rdi
0x14000d5ac  pop     rbp
0x14000d5ad  pop     rbx
0x14000d5ae  retn
0x14000d5af  movzx   edx, ax
0x14000d5b2  mov     rcx, rbx
0x14000d5b5  call    nfsoncrpc_setdestport
0x14000d5ba  mov     rdx, rbp; Source
0x14000d5bd  mov     rcx, rbx; ppResult
0x14000d5c0  call    nfsoncrpc_getaddresses
0x14000d5c5  test    eax, eax
0x14000d5c7  jnz     short loc_14000D58D
0x14000d5c9  mov     rax, [rsp+78h+arg_30]
0x14000d5d1  xor     r9d, r9d
0x14000d5d4  mov     qword ptr [rsp+78h+var_50], rax
0x14000d5d9  mov     r8d, r15d
0x14000d5dc  mov     edx, r12d
0x14000d5df  mov     [rsp+78h+var_58], 0
0x14000d5e7  mov     rcx, rbx
0x14000d5ea  call    nfsoncrpc_rpc_create_client_ex
0x14000d5ef  jmp     short loc_14000D5A1
```
