# RRasAdminConnectionRemoveQuarantine

- ea: `0x18000d2f0`
- end: `0x18000d361`
- name: `RRasAdminConnectionRemoveQuarantine`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000d2f0`
- `0x180019a24`

## import_xrefs

- `MPRDDM!DDMAdminRemoveQuarantine` at `0x18000d342`
- `MPRDDM!DDMAdminRemoveQuarantine` at `0x18000d342`

## pseudocode

```c
__int64 __fastcall RRasAdminConnectionRemoveQuarantine(__int64 a1, unsigned int a2, unsigned int a3)
{
  unsigned int v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  if ( (unsigned int)DimSecObjAccessCheckOrAllowedServices(3u, (WINBOOL *)&v6) || v6 )
    return 5;
  if ( (gbldwDIMComponentsLoaded & 4) == 0 || (_DWORD)qword_180070F24 == 1 || (unsigned int)(qword_180070F24 - 2) < 2 )
    return 903;
  return DDMAdminRemoveQuarantine(a2, a3);
}

```

## disassembly

```asm
0x18000d2f0  mov     [rsp+arg_0], rbx
0x18000d2f5  push    rdi
0x18000d2f6  sub     rsp, 20h
0x18000d2fa  mov     edi, edx
0x18000d2fc  mov     ecx, 3; unsigned int
0x18000d301  lea     rdx, [rsp+28h+arg_18]; unsigned int *
0x18000d306  mov     [rsp+28h+arg_18], 0
0x18000d30e  mov     ebx, r8d
0x18000d311  call    ?DimSecObjAccessCheckOrAllowedServices@@YAKKPEAK@Z; DimSecObjAccessCheckOrAllowedServices(ulong,ulong *)
0x18000d316  test    eax, eax
0x18000d318  jnz     short loc_18000D351
0x18000d31a  cmp     [rsp+28h+arg_18], eax
0x18000d31e  jnz     short loc_18000D351
0x18000d320  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x18000d327  jz      short loc_18000D34A
0x18000d329  mov     eax, dword ptr cs:qword_180070F24
0x18000d32f  sub     eax, 1
0x18000d332  jz      short loc_18000D34A
0x18000d334  sub     eax, 1
0x18000d337  jz      short loc_18000D34A
0x18000d339  cmp     eax, 1
0x18000d33c  jz      short loc_18000D34A
0x18000d33e  mov     ecx, edi
0x18000d340  mov     edx, ebx
0x18000d342  call    cs:__imp_DDMAdminRemoveQuarantine
0x18000d348  jmp     short loc_18000D356
0x18000d34a  mov     eax, 387h
0x18000d34f  jmp     short loc_18000D356
0x18000d351  mov     eax, 5
0x18000d356  mov     rbx, [rsp+28h+arg_0]
0x18000d35b  add     rsp, 20h
0x18000d35f  pop     rdi
0x18000d360  retn
```
