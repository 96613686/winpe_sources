# Mso::Sqm::WinSqmApi::GetSqmGuidRid(_GUID *,SQM_UID_TYPE)

- ea: `0x1801236e0`
- end: `0x180123790`
- name: `?GetSqmGuidRid@WinSqmApi@Sqm@Mso@@UEAAXPEAU_GUID@@W4SQM_UID_TYPE@@@Z`
- size: `176`
- prototype: `void __high(struct _GUID *, enum SQM_UID_TYPE)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180052cd0`
- `0x180052d34`
- `0x18009b040`
- `0x1800bc198`
- `0x1801236e0`

## import_xrefs

- `ole32!CoCreateGuid` at `0x180123724`
- `ole32!CoCreateGuid` at `0x18012375a`
- `ole32!CoCreateGuid` at `0x180123724`
- `ole32!CoCreateGuid` at `0x18012375a`

## pseudocode

```c
char __fastcall Mso::Sqm::WinSqmApi::GetSqmGuidRid(__int64 a1, const struct _msoreg *a2, struct _GUID *a3)
{
  char result; // al
  HRESULT v5; // eax
  const struct _msoreg *v6; // rcx
  HRESULT Guid; // eax

  if ( !a2 )
    CrashWithRecovery(0x1E5433D9u, 0);
  if ( !(_DWORD)a3 )
  {
    result = Mso::Orapi::Read((Mso::Orapi *)&vmsoridSqmMachineGuid, a2, a3);
    if ( result )
      return result;
    Guid = CoCreateGuid((GUID *)a2);
    _mm_lfence();
    if ( Guid < 0 )
      CrashWithRecoveryHrTag(Guid, 0x1E5433D8u);
    v6 = (const struct _msoreg *)&vmsoridSqmMachineGuid;
    return MsoFRegSetBinary(v6, (const unsigned __int8 *)a2, 0x10u);
  }
  if ( (_DWORD)a3 != 1 )
    CrashWithRecovery(0x1E5433D6u, 0);
  result = Mso::Orapi::Read((Mso::Orapi *)&vmsoridSqmUserGuid, a2, a3);
  if ( !result )
  {
    v5 = CoCreateGuid((GUID *)a2);
    _mm_lfence();
    if ( v5 < 0 )
      CrashWithRecoveryHrTag(v5, 0x1E5433D7u);
    v6 = (const struct _msoreg *)&vmsoridSqmUserGuid;
    return MsoFRegSetBinary(v6, (const unsigned __int8 *)a2, 0x10u);
  }
  return result;
}

```

## disassembly

```asm
0x1801236e0  push    rbx
0x1801236e2  sub     rsp, 20h
0x1801236e6  mov     rbx, rdx
0x1801236e9  test    rdx, rdx
0x1801236ec  jnz     short loc_1801236F9
0x1801236ee  mov     ecx, 1E5433D9h; unsigned int
0x1801236f3  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801236f9  test    r8d, r8d
0x1801236fc  jz      short loc_180123747
0x1801236fe  cmp     r8d, 1
0x180123702  jz      short loc_180123711
0x180123704  xor     edx, edx; struct CrashContext *
0x180123706  mov     ecx, 1E5433D6h; unsigned int
0x18012370b  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180123711  lea     rcx, ?vmsoridSqmUserGuid@@3U_msoreg@@B; this
0x180123718  call    ?Read@Orapi@Mso@@YA_NAEBU_msoreg@@AEAU_GUID@@@Z; Mso::Orapi::Read(_msoreg const &,_GUID &)
0x18012371d  test    al, al
0x18012371f  jnz     short loc_18012378A
0x180123721  mov     rcx, rbx; pguid
0x180123724  call    cs:__imp_CoCreateGuid
0x18012372a  lfence
0x18012372d  test    eax, eax
0x18012372f  jns     short loc_18012373E
0x180123731  mov     edx, 1E5433D7h; unsigned int
0x180123736  mov     ecx, eax; int
0x180123738  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x18012373e  lea     rcx, ?vmsoridSqmUserGuid@@3U_msoreg@@B; _msoreg const vmsoridSqmUserGuid
0x180123745  jmp     short loc_18012377B
0x180123747  lea     rcx, ?vmsoridSqmMachineGuid@@3U_msoreg@@B; this
0x18012374e  call    ?Read@Orapi@Mso@@YA_NAEBU_msoreg@@AEAU_GUID@@@Z; Mso::Orapi::Read(_msoreg const &,_GUID &)
0x180123753  test    al, al
0x180123755  jnz     short loc_18012378A
0x180123757  mov     rcx, rbx; pguid
0x18012375a  call    cs:__imp_CoCreateGuid
0x180123760  lfence
0x180123763  test    eax, eax
0x180123765  jns     short loc_180123774
0x180123767  mov     edx, 1E5433D8h; unsigned int
0x18012376c  mov     ecx, eax; int
0x18012376e  call    ?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180123774  lea     rcx, ?vmsoridSqmMachineGuid@@3U_msoreg@@B; struct _msoreg *
0x18012377b  mov     r8d, 10h; unsigned int
0x180123781  mov     rdx, rbx; unsigned __int8 *
0x180123784  call    ?MsoFRegSetBinary@@YAHPEBU_msoreg@@PEBEK@Z; MsoFRegSetBinary(_msoreg const *,uchar const *,ulong)
0x180123789  nop
0x18012378a  add     rsp, 20h
0x18012378e  pop     rbx
0x18012378f  retn
```
