# KerbUpdateRealmTable(_RTL_AVL_TABLE *)

- ea: `0x180094704`
- end: `0x180094873`
- name: `?KerbUpdateRealmTable@@YAXPEAU_RTL_AVL_TABLE@@@Z`
- size: `367`
- prototype: `void __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180094410`

## callees

- `0x18008b70c`
- `0x180094704`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180094757`
- `ntdll!RtlEqualUnicodeString` at `0x180094757`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180094766`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18009478a`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180094827`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180094766`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18009478a`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180094827`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18009477f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18009477f`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180094741`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180094741`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800947ba`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800947ba`
- `ntdll!RtlReleaseResource` at `0x18009486c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18009471f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18009471f`

## string_xrefs

- `0x18009480f`: `KerbUpdateRealmTable`
- `0x180094845`: `KerbUpdateRealmTable`
- `0x1800947d5`: `update: NewKey %p, SpnSuffix %wZ, Realm %wZ\n`

## pseudocode

```c
void __fastcall KerbUpdateRealmTable(PRTL_AVL_TABLE Table)
{
  BOOLEAN i; // dl
  const UNICODE_STRING *v3; // rax
  UNICODE_STRING *v4; // rax
  const UNICODE_STRING *v5; // rbx
  PVOID v6; // rax
  BOOLEAN j; // dl
  _QWORD *inserted; // rax
  unsigned __int16 *v9; // rax

  RtlAcquireResourceExclusive(&HostToRealmLock, 1u);
  if ( HostToRealmTable.NumberGenericTableElements == Table->NumberGenericTableElements )
  {
    for ( i = 1; ; i = 0 )
    {
      v4 = (UNICODE_STRING *)RtlEnumerateGenericTableAvl(&HostToRealmTable, i);
      v5 = v4;
      if ( !v4 )
        break;
      v3 = (const UNICODE_STRING *)RtlLookupElementGenericTableAvl(Table, v4);
      if ( !v3 || !RtlEqualUnicodeString(v5 + 1, v3 + 1, 1u) )
        goto LABEL_9;
    }
  }
  else
  {
LABEL_9:
    while ( 1 )
    {
      v6 = RtlEnumerateGenericTableAvl(&HostToRealmTable, 1u);
      if ( !v6 )
        break;
      RtlDeleteElementGenericTableAvl(&HostToRealmTable, v6);
    }
    HostToRealmUsed = 0;
    for ( j = 1; ; j = 0 )
    {
      v9 = (unsigned __int16 *)RtlEnumerateGenericTableAvl(Table, j);
      if ( !v9 )
        break;
      inserted = RtlInsertElementGenericTableAvl(&HostToRealmTable, v9, v9[9] + 32 + (unsigned int)v9[1], 0);
      if ( !inserted )
      {
        KerbTracerT::Log(1, "KerbUpdateRealmTable", 445, "Insert into table failed\n");
        break;
      }
      inserted[1] = inserted + 4;
      inserted[3] = (char *)inserted + 2 * ((unsigned __int64)*((unsigned __int16 *)inserted + 1) >> 1) + 32;
      KerbTracerT::Log(
        19,
        "KerbUpdateRealmTable",
        457,
        "update: NewKey %p, SpnSuffix %wZ, Realm %wZ\n",
        WORD1(inserted),
        inserted,
        inserted + 2);
      HostToRealmUsed = 1;
    }
  }
  RtlReleaseResource(&HostToRealmLock);
}

```

## disassembly

```asm
0x180094704  mov     [rsp+arg_0], rbx
0x180094709  mov     [rsp+arg_8], rsi
0x18009470e  push    rdi
0x18009470f  sub     rsp, 40h
0x180094713  mov     rdi, rcx
0x180094716  mov     dl, 1; Wait
0x180094718  lea     rcx, ?HostToRealmLock@@3U_RTL_RESOURCE@@A; Resource
0x18009471f  call    cs:__imp_RtlAcquireResourceExclusive
0x180094725  mov     eax, [rdi+2Ch]
0x180094728  lea     rsi, ?HostToRealmTable@@3U_RTL_AVL_TABLE@@A; _RTL_AVL_TABLE HostToRealmTable
0x18009472f  cmp     cs:?HostToRealmTable@@3U_RTL_AVL_TABLE@@A.NumberGenericTableElements, eax; _RTL_AVL_TABLE HostToRealmTable ...
0x180094735  jnz     short loc_180094785
0x180094737  mov     dl, 1
0x180094739  jmp     short loc_180094763
0x18009473b  mov     rdx, rbx; Buffer
0x18009473e  mov     rcx, rdi; Table
0x180094741  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180094747  test    rax, rax
0x18009474a  jz      short loc_180094785
0x18009474c  lea     rdx, [rax+10h]; String2
0x180094750  mov     r8b, 1; CaseInsensitive
0x180094753  lea     rcx, [rbx+10h]; String1
0x180094757  call    cs:__imp_RtlEqualUnicodeString
0x18009475d  test    al, al
0x18009475f  jz      short loc_180094785
0x180094761  xor     edx, edx; Restart
0x180094763  mov     rcx, rsi; Table
0x180094766  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18009476c  mov     rbx, rax
0x18009476f  test    rax, rax
0x180094772  jnz     short loc_18009473B
0x180094774  jmp     loc_180094856
0x180094779  mov     rdx, rax; Buffer
0x18009477c  mov     rcx, rsi; Table
0x18009477f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180094785  mov     dl, 1; Restart
0x180094787  mov     rcx, rsi; Table
0x18009478a  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180094790  test    rax, rax
0x180094793  jnz     short loc_180094779
0x180094795  mov     cs:?HostToRealmUsed@@3EA, al; uchar HostToRealmUsed
0x18009479b  mov     dl, 1
0x18009479d  jmp     loc_180094824
0x1800947a2  movzx   edx, word ptr [rax+12h]
0x1800947a6  xor     r9d, r9d; NewElement
0x1800947a9  movzx   r8d, word ptr [rax+2]
0x1800947ae  add     edx, 20h ; ' '
0x1800947b1  add     r8d, edx; BufferSize
0x1800947b4  mov     rcx, rsi; Table
0x1800947b7  mov     rdx, rax; Buffer
0x1800947ba  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1800947c0  test    rax, rax
0x1800947c3  jz      short loc_180094838
0x1800947c5  lea     rcx, [rax+20h]
0x1800947c9  mov     [rax+8], rcx
0x1800947cd  lea     r8, [rax+10h]
0x1800947d1  movzx   ecx, word ptr [rax+2]
0x1800947d5  lea     r9, aUpdateNewkeyPS; "update: NewKey %p, SpnSuffix %wZ, Realm"...
0x1800947dc  shr     rcx, 1
0x1800947df  add     rcx, 10h
0x1800947e3  mov     [rsp+48h+var_18], r8
0x1800947e8  mov     [rsp+48h+var_20], rax
0x1800947ed  mov     r8d, 1C9h
0x1800947f3  lea     rcx, [rax+rcx*2]
0x1800947f7  mov     [rax+18h], rcx
0x1800947fb  mov     rcx, rax
0x1800947fe  shr     rcx, 10h
0x180094802  movzx   edx, cx
0x180094805  mov     ecx, 13h
0x18009480a  mov     [rsp+48h+var_28], rdx
0x18009480f  lea     rdx, aKerbupdatereal; "KerbUpdateRealmTable"
0x180094816  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009481b  xor     edx, edx; Restart
0x18009481d  mov     cs:?HostToRealmUsed@@3EA, 1; uchar HostToRealmUsed
0x180094824  mov     rcx, rdi; Table
0x180094827  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18009482d  test    rax, rax
0x180094830  jnz     loc_1800947A2
0x180094836  jmp     short loc_180094856
0x180094838  lea     r9, aInsertIntoTabl; "Insert into table failed\n"
0x18009483f  mov     r8d, 1BDh
0x180094845  lea     rdx, aKerbupdatereal; "KerbUpdateRealmTable"
0x18009484c  mov     ecx, 1
0x180094851  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180094856  lea     rcx, ?HostToRealmLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE HostToRealmLock
0x18009485d  mov     rbx, [rsp+48h+arg_0]
0x180094862  mov     rsi, [rsp+48h+arg_8]
0x180094867  add     rsp, 40h
0x18009486b  pop     rdi
0x18009486c  jmp     cs:__imp_RtlReleaseResource
```
