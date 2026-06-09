# RRasAdminUpdateConnection

- ea: `0x18000d7d0`
- end: `0x18000d84e`
- name: `RRasAdminUpdateConnection`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000d7d0`
- `0x180019950`

## import_xrefs

- `MPRDDM!DDMAdminUpdateConnection` at `0x18000d82f`
- `MPRDDM!DDMAdminUpdateConnection` at `0x18000d82f`

## pseudocode

```c
__int64 __fastcall RRasAdminUpdateConnection(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rcx
  WINBOOL AccessStatus; // [rsp+48h] [rbp+20h] BYREF

  v3 = a2;
  AccessStatus = 0;
  if ( DimSecObjAccessCheck(1u, &AccessStatus) || AccessStatus )
    return 5;
  if ( (gbldwDIMComponentsLoaded & 4) == 0 || (_DWORD)qword_180070F24 == 1 || (unsigned int)(qword_180070F24 - 2) < 2 )
    return 903;
  if ( (_DWORD)v3 == -1 )
    v5 = -1;
  else
    v5 = v3;
  return DDMAdminUpdateConnection(v5, a3);
}

```

## disassembly

```asm
0x18000d7d0  mov     [rsp+arg_0], rbx
0x18000d7d5  push    rdi
0x18000d7d6  sub     rsp, 20h
0x18000d7da  mov     ebx, edx
0x18000d7dc  mov     ecx, 1; DesiredAccess
0x18000d7e1  lea     rdx, [rsp+28h+AccessStatus]; AccessStatus
0x18000d7e6  mov     [rsp+28h+AccessStatus], 0
0x18000d7ee  mov     rdi, r8
0x18000d7f1  call    ?DimSecObjAccessCheck@@YAKKPEAK@Z; DimSecObjAccessCheck(ulong,ulong *)
0x18000d7f6  test    eax, eax
0x18000d7f8  jnz     short loc_18000D83E
0x18000d7fa  cmp     [rsp+28h+AccessStatus], eax
0x18000d7fe  jnz     short loc_18000D83E
0x18000d800  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x18000d807  jz      short loc_18000D837
0x18000d809  mov     eax, dword ptr cs:qword_180070F24
0x18000d80f  sub     eax, 1
0x18000d812  jz      short loc_18000D837
0x18000d814  sub     eax, 1
0x18000d817  jz      short loc_18000D837
0x18000d819  cmp     eax, 1
0x18000d81c  jz      short loc_18000D837
0x18000d81e  cmp     ebx, 0FFFFFFFFh
0x18000d821  jnz     short loc_18000D829
0x18000d823  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d827  jmp     short loc_18000D82C
0x18000d829  mov     rcx, rbx
0x18000d82c  mov     rdx, rdi
0x18000d82f  call    cs:__imp_DDMAdminUpdateConnection
0x18000d835  jmp     short loc_18000D843
0x18000d837  mov     eax, 387h
0x18000d83c  jmp     short loc_18000D843
0x18000d83e  mov     eax, 5
0x18000d843  mov     rbx, [rsp+28h+arg_0]
0x18000d848  add     rsp, 20h
0x18000d84c  pop     rdi
0x18000d84d  retn
```
