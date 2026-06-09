# LsaDbrDeleteTrustedDomain(void *,_LSAPR_SID *)

- ea: `0x18000d4b0`
- end: `0x18000d527`
- name: `?LsaDbrDeleteTrustedDomain@@YAJPEAXPEAU_LSAPR_SID@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(void *, struct _LSAPR_SID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18000d4b0`
- `0x18000d5e0`
- `0x180036d24`

## import_xrefs

- `LSASRV!LsapCloseHandle` at `0x18000d514`
- `LSASRV!LsapCloseHandle` at `0x18000d514`
- `LSASRV!LsarDeleteObject` at `0x18000d4fd`
- `LSASRV!LsarDeleteObject` at `0x18000d4fd`

## pseudocode

```c
__int64 __fastcall LsaDbrDeleteTrustedDomain(void *a1, struct _LSAPR_SID *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  void *v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  if ( LsapValidateDomainSid(a2) )
  {
    v4 = LsaDbrOpenTrustedDomain(a1, a2, 0x10000u, &v7);
    if ( v4 >= 0 )
      v4 = LsarDeleteObject(&v7, v5);
  }
  else
  {
    v4 = -1073741811;
  }
  if ( v7 )
    LsapCloseHandle(&v7, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d4b0  mov     [rsp+arg_0], rbx
0x18000d4b5  push    rdi
0x18000d4b6  sub     rsp, 20h
0x18000d4ba  mov     rdi, rcx
0x18000d4bd  mov     [rsp+28h+arg_10], 0
0x18000d4c6  mov     rcx, rdx; Sid1
0x18000d4c9  mov     rbx, rdx
0x18000d4cc  call    ?LsapValidateDomainSid@@YAEPEAX@Z; LsapValidateDomainSid(void *)
0x18000d4d1  test    al, al
0x18000d4d3  jnz     short loc_18000D4DC
0x18000d4d5  mov     ebx, 0C000000Dh
0x18000d4da  jmp     short loc_18000D505
0x18000d4dc  lea     r9, [rsp+28h+arg_10]; void **
0x18000d4e1  mov     r8d, 10000h; unsigned int
0x18000d4e7  mov     rdx, rbx; Sid
0x18000d4ea  mov     rcx, rdi; void *
0x18000d4ed  call    ?LsaDbrOpenTrustedDomain@@YAJPEAXPEAU_LSAPR_SID@@KPEAPEAX@Z; LsaDbrOpenTrustedDomain(void *,_LSAPR_SID *,ulong,void * *)
0x18000d4f2  mov     ebx, eax
0x18000d4f4  test    eax, eax
0x18000d4f6  js      short loc_18000D505
0x18000d4f8  lea     rcx, [rsp+28h+arg_10]
0x18000d4fd  call    cs:__imp_LsarDeleteObject
0x18000d503  mov     ebx, eax
0x18000d505  cmp     [rsp+28h+arg_10], 0
0x18000d50b  jz      short loc_18000D51A
0x18000d50d  mov     edx, ebx
0x18000d50f  lea     rcx, [rsp+28h+arg_10]
0x18000d514  call    cs:__imp_LsapCloseHandle
0x18000d51a  mov     eax, ebx
0x18000d51c  mov     rbx, [rsp+28h+arg_0]
0x18000d521  add     rsp, 20h
0x18000d525  pop     rdi
0x18000d526  retn
```
