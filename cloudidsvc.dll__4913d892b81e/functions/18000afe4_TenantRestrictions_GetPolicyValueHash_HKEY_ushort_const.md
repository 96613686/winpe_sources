# TenantRestrictions::GetPolicyValueHash(HKEY__ *,ushort const *)

- ea: `0x18000afe4`
- end: `0x18000b079`
- name: `?GetPolicyValueHash@TenantRestrictions@@CA_KPEAUHKEY__@@PEBG@Z`
- size: `149`
- prototype: `unsigned __int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ae7c`

## callees

- `0x18000afe4`
- `0x18000c41c`
- `0x180010114`
- `0x180010488`
- `0x18001059c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b057`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b057`

## string_xrefs

- `0x18000b02d`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`

## pseudocode

```c
unsigned __int64 __fastcall TenantRestrictions::GetPolicyValueHash(HKEY a1, const unsigned __int16 *a2)
{
  int RegistryString; // eax
  unsigned __int64 RegMultiSzHash; // rbx
  void *v5; // r11
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned __int16 *v9; // [rsp+50h] [rbp+18h] BYREF

  if ( !RegistryValuePresent(a1, a2) )
    return GetRegMultiSzHash(&qword_180014598);
  v9 = 0;
  RegistryString = ReadRegistryString(a1, (__int64)&v9);
  if ( RegistryString < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x168,
      (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
      (const char *)(unsigned int)RegistryString,
      v7);
  RegMultiSzHash = GetRegMultiSzHash(v9);
  if ( v5 )
    LocalFree(v5);
  return RegMultiSzHash;
}

```

## disassembly

```asm
0x18000afe4  mov     [rsp+arg_0], rbx
0x18000afe9  push    rdi
0x18000afea  sub     rsp, 30h
0x18000afee  mov     rbx, rdx
0x18000aff1  mov     rdi, rcx
0x18000aff4  call    ?RegistryValuePresent@@YA_NPEAUHKEY__@@PEBG@Z; RegistryValuePresent(HKEY__ *,ushort const *)
0x18000aff9  test    al, al
0x18000affb  jz      short loc_18000B062
0x18000affd  mov     [rsp+38h+arg_10], 0
0x18000b006  lea     rax, [rsp+38h+arg_10]
0x18000b00b  mov     qword ptr [rsp+38h+var_18], rax; int
0x18000b010  mov     r9d, 20h ; ' '
0x18000b016  mov     r8, rbx
0x18000b019  mov     rcx, rdi; hkey
0x18000b01c  call    ?ReadRegistryString@@YAJPEAUHKEY__@@PEBG1KAEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@Z; ReadRegistryString(HKEY__ *,ushort const *,ushort const *,ulong,wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &)
0x18000b021  mov     rcx, [rsp+38h]; this
0x18000b026  test    eax, eax
0x18000b028  jns     short loc_18000B03F
0x18000b02a  mov     r9d, eax; char *
0x18000b02d  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000b034  mov     edx, 168h; void *
0x18000b039  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b03f  mov     r11, [rsp+38h+arg_10]
0x18000b044  mov     rcx, r11; unsigned __int16 *
0x18000b047  call    ?GetRegMultiSzHash@@YA_KPEBG@Z; GetRegMultiSzHash(ushort const *)
0x18000b04c  mov     rbx, rax
0x18000b04f  test    r11, r11
0x18000b052  jz      short loc_18000B05D
0x18000b054  mov     rcx, r11; hMem
0x18000b057  call    cs:__imp_LocalFree
0x18000b05d  mov     rax, rbx
0x18000b060  jmp     short loc_18000B06E
0x18000b062  lea     rcx, qword_180014598; unsigned __int16 *
0x18000b069  call    ?GetRegMultiSzHash@@YA_KPEBG@Z; GetRegMultiSzHash(ushort const *)
0x18000b06e  mov     rbx, [rsp+38h+arg_0]
0x18000b073  add     rsp, 30h
0x18000b077  pop     rdi
0x18000b078  retn
```
