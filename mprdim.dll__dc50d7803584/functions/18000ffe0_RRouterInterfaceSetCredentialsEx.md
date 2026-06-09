# RRouterInterfaceSetCredentialsEx

- ea: `0x18000ffe0`
- end: `0x18001007a`
- name: `RRouterInterfaceSetCredentialsEx`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000ffe0`
- `0x180019950`
- `0x1800276d0`

## import_xrefs

- `MPRDDM!DDMServicePostListens` at `0x18001005b`
- `MPRDDM!DDMServicePostListens` at `0x18001005b`

## pseudocode

```c
unsigned int __fastcall RRouterInterfaceSetCredentialsEx(
        __int64 a1,
        unsigned int a2,
        struct _DIM_INFORMATION_CONTAINER *a3,
        unsigned int a4)
{
  __int64 v5; // rbx
  CDimInterfaceTable *v7; // rcx
  __int64 v8; // rdx
  unsigned int result; // eax
  bool v10; // [rsp+30h] [rbp-18h] BYREF
  WINBOOL v11; // [rsp+34h] [rbp-14h] BYREF
  int v12[4]; // [rsp+38h] [rbp-10h] BYREF

  v5 = a4;
  v11 = 0;
  v10 = 0;
  if ( DimSecObjAccessCheck(1u, &v11) || v11 )
    return 5;
  if ( (_DWORD)v5 == -1 )
    v8 = -1;
  else
    v8 = v5;
  result = CDimInterfaceTable::SetCredentialsEx(v7, (void *const)v8, a2, a3, &v10);
  if ( v10 && (gbldwDIMComponentsLoaded & 4) != 0 )
  {
    v12[0] = 9;
    DDMServicePostListens(v12);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ffe0  mov     rax, rsp
0x18000ffe3  mov     [rax+8], rbx
0x18000ffe7  mov     [rax+10h], rsi
0x18000ffeb  push    rdi
0x18000ffec  sub     rsp, 40h
0x18000fff0  mov     esi, edx
0x18000fff2  mov     ebx, r9d
0x18000fff5  lea     rdx, [rax-14h]; AccessStatus
0x18000fff9  mov     dword ptr [rax-14h], 0
0x180010000  mov     ecx, 1; DesiredAccess
0x180010005  mov     byte ptr [rax-18h], 0
0x180010009  mov     rdi, r8
0x18001000c  call    ?DimSecObjAccessCheck@@YAKKPEAK@Z; DimSecObjAccessCheck(ulong,ulong *)
0x180010011  test    eax, eax
0x180010013  jnz     short loc_180010065
0x180010015  cmp     [rsp+48h+var_14], eax
0x180010019  jnz     short loc_180010065
0x18001001b  cmp     ebx, 0FFFFFFFFh
0x18001001e  jnz     short loc_180010026
0x180010020  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180010024  jmp     short loc_180010029
0x180010026  mov     rdx, rbx; void *
0x180010029  lea     rax, [rsp+48h+var_18]
0x18001002e  mov     r9, rdi; struct _DIM_INFORMATION_CONTAINER *
0x180010031  mov     r8d, esi; unsigned int
0x180010034  mov     [rsp+48h+var_28], rax; bool *
0x180010039  call    ?SetCredentialsEx@CDimInterfaceTable@@QEAAKQEAXKPEAU_DIM_INFORMATION_CONTAINER@@AEA_N@Z; CDimInterfaceTable::SetCredentialsEx(void * const,ulong,_DIM_INFORMATION_CONTAINER *,bool &)
0x18001003e  cmp     [rsp+48h+var_18], 0
0x180010043  jz      short loc_18001006A
0x180010045  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x18001004c  jz      short loc_18001006A
0x18001004e  lea     rcx, [rsp+48h+var_10]
0x180010053  mov     [rsp+48h+var_10], 9
0x18001005b  call    cs:__imp_DDMServicePostListens
0x180010061  xor     eax, eax
0x180010063  jmp     short loc_18001006A
0x180010065  mov     eax, 5
0x18001006a  mov     rbx, [rsp+48h+arg_0]
0x18001006f  mov     rsi, [rsp+48h+arg_8]
0x180010074  add     rsp, 40h
0x180010078  pop     rdi
0x180010079  retn
```
