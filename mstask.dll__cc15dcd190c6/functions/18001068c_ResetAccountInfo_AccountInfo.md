# ResetAccountInfo(_AccountInfo *)

- ea: `0x18001068c`
- end: `0x180010709`
- name: `?ResetAccountInfo@@YAXPEAU_AccountInfo@@@Z`
- size: `125`
- prototype: `void __fastcall(struct _AccountInfo *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180010350`
- `0x180019f64`

## callees

- `0x180009f38`
- `0x18001068c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106a8`

## pseudocode

```c
void __fastcall ResetAccountInfo(struct _AccountInfo *a1)
{
  void *v2; // rcx
  const WCHAR *v3; // rax
  __int64 v4; // rcx
  __int64 i; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
  }
  v3 = (const WCHAR *)*((_QWORD *)a1 + 1);
  if ( v3 && v3 != &String )
  {
    v4 = -1;
    do
      ++v4;
    while ( v3[v4] );
    for ( i = 2 * v4 + 2; i; --i )
    {
      *(_BYTE *)v3 = 0;
      v3 = (const WCHAR *)((char *)v3 + 1);
    }
    operator delete(*((void **)a1 + 1));
    *((_QWORD *)a1 + 1) = &String;
  }
}

```

## disassembly

```asm
0x18001068c  mov     [rsp+arg_0], rbx
0x180010691  mov     [rsp+arg_8], rsi
0x180010696  push    rdi
0x180010697  sub     rsp, 20h
0x18001069b  mov     rbx, rcx
0x18001069e  xor     edi, edi
0x1800106a0  mov     rcx, [rcx]; pv
0x1800106a3  test    rcx, rcx
0x1800106a6  jz      short loc_1800106B1
0x1800106a8  call    cs:__imp_CoTaskMemFree
0x1800106ae  mov     [rbx], rdi
0x1800106b1  mov     rax, [rbx+8]
0x1800106b5  test    rax, rax
0x1800106b8  jz      short loc_1800106F9
0x1800106ba  lea     rsi, String
0x1800106c1  cmp     rax, rsi
0x1800106c4  jz      short loc_1800106F9
0x1800106c6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800106ca  inc     rcx
0x1800106cd  cmp     [rax+rcx*2], di
0x1800106d1  jnz     short loc_1800106CA
0x1800106d3  lea     rcx, ds:2[rcx*2]
0x1800106db  test    rcx, rcx
0x1800106de  jz      short loc_1800106EC
0x1800106e0  mov     [rax], dil
0x1800106e3  inc     rax
0x1800106e6  sub     rcx, 1
0x1800106ea  jnz     short loc_1800106E0
0x1800106ec  mov     rcx, [rbx+8]; Block
0x1800106f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800106f5  mov     [rbx+8], rsi
0x1800106f9  mov     rbx, [rsp+28h+arg_0]
0x1800106fe  mov     rsi, [rsp+28h+arg_8]
0x180010703  add     rsp, 20h
0x180010707  pop     rdi
0x180010708  retn
```
