# blue2th::Migrator::LogResult(blue2th::Migrator::Step,long)

- ea: `0x1800088a4`
- end: `0x18000893a`
- name: `?LogResult@Migrator@blue2th@@QEAAXW4Step@12@J@Z`
- size: `150`
- prototype: `void __fastcall(__int64, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c740`

## callees

- `0x1800088a4`
- `0x18000a8a8`

## string_xrefs

- `0x1800088cc`: `Migration Attempted B2T`
- `0x180008917`: `RegistryDelete`

## pseudocode

```c
void __fastcall blue2th::Migrator::LogResult(__int64 a1, int a2, int a3, unsigned int a4)
{
  _DWORD *v4; // rax
  unsigned int v7; // r9d
  int v8; // eax
  int v9; // ebx
  int v10; // ebx
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // [rsp+20h] [rbp-18h]
  unsigned int v13; // [rsp+20h] [rbp-18h]
  int v14; // [rsp+48h] [rbp+10h] BYREF
  int v15; // [rsp+50h] [rbp+18h] BYREF

  v15 = a3;
  v4 = *(_DWORD **)(a1 + 24);
  v14 = a2;
  if ( v4 )
    *v4 = a2;
  RegistryHelper::Write(
    L"SOFTWARE\\Microsoft\\Enrollment",
    L"Migration Attempted B2T",
    (const unsigned __int8 *)&v14,
    a4,
    v12);
  v8 = v15;
  if ( v15 >= 0 )
    v8 = *(_DWORD *)(a1 + 32);
  *(_DWORD *)(a1 + 32) = v8;
  v9 = a2 - 3;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 == 1 )
        v11 = L"ResourceManager";
      else
        v11 = L"Unknown";
    }
    else
    {
      v11 = L"Schedule";
    }
  }
  else
  {
    v11 = L"RegistryDelete";
  }
  RegistryHelper::Write(
    L"SOFTWARE\\Microsoft\\Enrollment\\MigrationStatus",
    v11,
    (const unsigned __int8 *)&v15,
    v7,
    v13);
}

```

## disassembly

```asm
0x1800088a4  mov     [rsp+arg_0], rbx
0x1800088a9  mov     [rsp+arg_10], r8d
0x1800088ae  push    rdi
0x1800088af  sub     rsp, 30h
0x1800088b3  mov     rax, [rcx+18h]
0x1800088b7  mov     ebx, edx
0x1800088b9  mov     [rsp+38h+arg_8], edx
0x1800088bd  mov     rdi, rcx
0x1800088c0  test    rax, rax
0x1800088c3  jz      short loc_1800088C7
0x1800088c5  mov     [rax], edx
0x1800088c7  lea     r8, [rsp+38h+arg_8]; unsigned __int8 *
0x1800088cc  lea     rdx, aMigrationAttem; "Migration Attempted B2T"
0x1800088d3  lea     rcx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Enrollment"
0x1800088da  call    ?Write@RegistryHelper@@SAXPEBG0PEBEKK@Z; RegistryHelper::Write(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x1800088df  mov     eax, [rsp+38h+arg_10]
0x1800088e3  test    eax, eax
0x1800088e5  js      short loc_1800088EA
0x1800088e7  mov     eax, [rdi+20h]
0x1800088ea  mov     [rdi+20h], eax
0x1800088ed  sub     ebx, 3
0x1800088f0  jz      short loc_180008917
0x1800088f2  sub     ebx, 1
0x1800088f5  jz      short loc_18000890E
0x1800088f7  cmp     ebx, 1
0x1800088fa  jz      short loc_180008905
0x1800088fc  lea     rdx, aUnknown; "Unknown"
0x180008903  jmp     short loc_18000891E
0x180008905  lea     rdx, aResourcemanage_1; "ResourceManager"
0x18000890c  jmp     short loc_18000891E
0x18000890e  lea     rdx, aSchedule; "Schedule"
0x180008915  jmp     short loc_18000891E
0x180008917  lea     rdx, aRegistrydelete; "RegistryDelete"
0x18000891e  lea     r8, [rsp+38h+arg_10]; unsigned __int8 *
0x180008923  lea     rcx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Enrollment\\Migrat"...
0x18000892a  call    ?Write@RegistryHelper@@SAXPEBG0PEBEKK@Z; RegistryHelper::Write(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x18000892f  mov     rbx, [rsp+38h+arg_0]
0x180008934  add     rsp, 30h
0x180008938  pop     rdi
0x180008939  retn
```
