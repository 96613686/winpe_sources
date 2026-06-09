# CONFIG_FILE::~CONFIG_FILE(void)

- ea: `0x180023820`
- end: `0x180023a17`
- name: `??1CONFIG_FILE@@EEAA@XZ`
- size: `503`
- prototype: `void __fastcall(CONFIG_FILE *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180023e70`

## callees

- `0x180010a80`
- `0x180010c70`
- `0x180010cb8`
- `0x180011b80`
- `0x180014b34`
- `0x180016440`
- `0x180017850`
- `0x180018d88`
- `0x180018edc`
- `0x18001a684`
- `0x180023820`
- `0x180025fe0`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023962`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023962`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023970`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023970`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800239e7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800239e7`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800239a4`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800239dd`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800239a4`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800239dd`

## pseudocode

```c
void __fastcall CONFIG_FILE::~CONFIG_FILE(CONFIG_FILE *this)
{
  CONFIG_ELEMENT *v2; // rcx
  LOCATION_TABLE *v3; // rcx
  SECTION_GROUP_TABLE *v4; // rcx
  SECTION_GROUP_TABLE *v5; // rcx
  CONFIG_FILE *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  SCHEMA_TABLE *v9; // rcx
  void *v10; // rdi
  HANDLE ProcessHeap; // rax
  SCHEMA_FILE_LIST *v12; // rcx

  *((_DWORD *)this + 8) = 2020042339;
  *(_QWORD *)this = &CONFIG_FILE::`vftable'{for `IAppHostConfigFile'};
  *((_QWORD *)this + 1) = &CONFIG_FILE::`vftable'{for `IArrayListEntry'};
  *((_QWORD *)this + 2) = &CONFIG_FILE::`vftable'{for `INativeConfigFile'};
  v2 = (CONFIG_ELEMENT *)*((_QWORD *)this + 35);
  if ( v2 )
  {
    CONFIG_ELEMENT::DereferenceConfigElement(v2);
    *((_QWORD *)this + 35) = 0;
  }
  v3 = (LOCATION_TABLE *)*((_QWORD *)this + 22);
  if ( v3 )
  {
    LOCATION_TABLE::DereferenceLocationTable(v3);
    *((_QWORD *)this + 22) = 0;
  }
  v4 = (SECTION_GROUP_TABLE *)*((_QWORD *)this + 19);
  if ( v4 )
  {
    SECTION_GROUP_TABLE::DereferenceSectionGroupTable(v4);
    *((_QWORD *)this + 19) = 0;
  }
  v5 = (SECTION_GROUP_TABLE *)*((_QWORD *)this + 20);
  if ( v5 )
  {
    SECTION_GROUP_TABLE::DereferenceSectionGroupTable(v5);
    *((_QWORD *)this + 20) = 0;
  }
  v6 = (CONFIG_FILE *)*((_QWORD *)this + 16);
  if ( v6 )
  {
    CONFIG_FILE::DereferenceConfigFile(v6);
    *((_QWORD *)this + 16) = 0;
  }
  v7 = *((_QWORD *)this + 21);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 120LL))(v7);
    *((_QWORD *)this + 21) = 0;
  }
  v8 = *((_QWORD *)this + 38);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 56LL))(v8);
    *((_QWORD *)this + 38) = 0;
  }
  ARRAY_LIST::Clear((CONFIG_FILE *)((char *)this + 312));
  v9 = (SCHEMA_TABLE *)*((_QWORD *)this + 44);
  if ( v9 )
  {
    SCHEMA_TABLE::DereferenceSchemaTable(v9);
    *((_QWORD *)this + 44) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 45);
  if ( v10 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
    *((_QWORD *)this + 45) = 0;
  }
  v12 = (SCHEMA_FILE_LIST *)*((_QWORD *)this + 25);
  if ( v12 )
  {
    SCHEMA_FILE_LIST::DereferenceSchemaFileList(v12);
    *((_QWORD *)this + 25) = 0;
  }
  CReaderWriterLock3::~CReaderWriterLock3((CONFIG_FILE *)((char *)this + 344));
  ARRAY_LIST::~ARRAY_LIST((CONFIG_FILE *)((char *)this + 328));
  ARRAY_LIST::~ARRAY_LIST((CONFIG_FILE *)((char *)this + 312));
  ARRAY_LIST::~ARRAY_LIST((CONFIG_FILE *)((char *)this + 288));
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((CONFIG_FILE *)((char *)this + 208));
  CReaderWriterLock3::~CReaderWriterLock3((CONFIG_FILE *)((char *)this + 184));
  STRU::~STRU((CONFIG_FILE *)((char *)this + 72));
  SMALL_STRU::Reset((CONFIG_FILE *)((char *)this + 48));
  SMALL_STRU::Reset((CONFIG_FILE *)((char *)this + 40));
  DispatchSupportedComObject::~DispatchSupportedComObject((CONFIG_FILE *)((char *)this + 24));
}

```

## disassembly

```asm
0x180023820  mov     [rsp+arg_0], rbx
0x180023825  mov     [rsp+arg_8], rsi
0x18002382a  push    rdi
0x18002382b  sub     rsp, 20h
0x18002382f  lea     rax, ??_7CONFIG_FILE@@6BIAppHostConfigFile@@@; const CONFIG_FILE::`vftable'{for `IAppHostConfigFile'}
0x180023836  mov     dword ptr [rcx+20h], 78676663h
0x18002383d  mov     [rcx], rax
0x180023840  mov     rbx, rcx
0x180023843  lea     rax, ??_7CONFIG_FILE@@6BIArrayListEntry@@@; const CONFIG_FILE::`vftable'{for `IArrayListEntry'}
0x18002384a  mov     [rcx+8], rax
0x18002384e  lea     rax, ??_7CONFIG_FILE@@6BINativeConfigFile@@@; const CONFIG_FILE::`vftable'{for `INativeConfigFile'}
0x180023855  mov     [rcx+10h], rax
0x180023859  mov     rcx, [rcx+118h]; this
0x180023860  test    rcx, rcx
0x180023863  jz      short loc_180023875
0x180023865  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x18002386a  mov     qword ptr [rbx+118h], 0
0x180023875  mov     rcx, [rbx+0B0h]; this
0x18002387c  test    rcx, rcx
0x18002387f  jz      short loc_180023891
0x180023881  call    ?DereferenceLocationTable@LOCATION_TABLE@@QEAAXXZ; LOCATION_TABLE::DereferenceLocationTable(void)
0x180023886  mov     qword ptr [rbx+0B0h], 0
0x180023891  mov     rcx, [rbx+98h]; this
0x180023898  test    rcx, rcx
0x18002389b  jz      short loc_1800238AD
0x18002389d  call    ?DereferenceSectionGroupTable@SECTION_GROUP_TABLE@@QEAAXXZ; SECTION_GROUP_TABLE::DereferenceSectionGroupTable(void)
0x1800238a2  mov     qword ptr [rbx+98h], 0
0x1800238ad  mov     rcx, [rbx+0A0h]; this
0x1800238b4  test    rcx, rcx
0x1800238b7  jz      short loc_1800238C9
0x1800238b9  call    ?DereferenceSectionGroupTable@SECTION_GROUP_TABLE@@QEAAXXZ; SECTION_GROUP_TABLE::DereferenceSectionGroupTable(void)
0x1800238be  mov     qword ptr [rbx+0A0h], 0
0x1800238c9  mov     rcx, [rbx+80h]; this
0x1800238d0  test    rcx, rcx
0x1800238d3  jz      short loc_1800238E5
0x1800238d5  call    ?DereferenceConfigFile@CONFIG_FILE@@QEAAXXZ; CONFIG_FILE::DereferenceConfigFile(void)
0x1800238da  mov     qword ptr [rbx+80h], 0
0x1800238e5  mov     rcx, [rbx+0A8h]
0x1800238ec  test    rcx, rcx
0x1800238ef  jz      short loc_180023908
0x1800238f1  mov     rax, [rcx]
0x1800238f4  mov     rax, [rax+78h]
0x1800238f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238fd  mov     qword ptr [rbx+0A8h], 0
0x180023908  mov     rcx, [rbx+130h]
0x18002390f  test    rcx, rcx
0x180023912  jz      short loc_18002392B
0x180023914  mov     rax, [rcx]
0x180023917  mov     rax, [rax+38h]
0x18002391b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023920  mov     qword ptr [rbx+130h], 0
0x18002392b  lea     rsi, [rbx+138h]
0x180023932  mov     rcx, rsi; this
0x180023935  call    ?Clear@ARRAY_LIST@@QEAAXXZ; ARRAY_LIST::Clear(void)
0x18002393a  mov     rcx, [rbx+160h]; this
0x180023941  test    rcx, rcx
0x180023944  jz      short loc_180023956
0x180023946  call    ?DereferenceSchemaTable@SCHEMA_TABLE@@QEAAXXZ; SCHEMA_TABLE::DereferenceSchemaTable(void)
0x18002394b  mov     qword ptr [rbx+160h], 0
0x180023956  mov     rdi, [rbx+168h]
0x18002395d  test    rdi, rdi
0x180023960  jz      short loc_180023981
0x180023962  call    cs:__imp_GetProcessHeap
0x180023968  mov     r8, rdi; lpMem
0x18002396b  xor     edx, edx; dwFlags
0x18002396d  mov     rcx, rax; hHeap
0x180023970  call    cs:__imp_HeapFree
0x180023976  mov     qword ptr [rbx+168h], 0
0x180023981  mov     rcx, [rbx+0C8h]; this
0x180023988  test    rcx, rcx
0x18002398b  jz      short loc_18002399D
0x18002398d  call    ?DereferenceSchemaFileList@SCHEMA_FILE_LIST@@QEAAXXZ; SCHEMA_FILE_LIST::DereferenceSchemaFileList(void)
0x180023992  mov     qword ptr [rbx+0C8h], 0
0x18002399d  lea     rcx, [rbx+158h]
0x1800239a4  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x1800239aa  lea     rcx, [rbx+148h]; this
0x1800239b1  call    ??1ARRAY_LIST@@QEAA@XZ; ARRAY_LIST::~ARRAY_LIST(void)
0x1800239b6  mov     rcx, rsi; this
0x1800239b9  call    ??1ARRAY_LIST@@QEAA@XZ; ARRAY_LIST::~ARRAY_LIST(void)
0x1800239be  lea     rcx, [rbx+120h]; this
0x1800239c5  call    ??1ARRAY_LIST@@QEAA@XZ; ARRAY_LIST::~ARRAY_LIST(void)
0x1800239ca  lea     rcx, [rbx+0D0h]; this
0x1800239d1  call    ??1PARSE_ERROR_INFO@@UEAA@XZ; PARSE_ERROR_INFO::~PARSE_ERROR_INFO(void)
0x1800239d6  lea     rcx, [rbx+0B8h]
0x1800239dd  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x1800239e3  lea     rcx, [rbx+48h]
0x1800239e7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800239ed  lea     rcx, [rbx+30h]; this
0x1800239f1  call    ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
0x1800239f6  lea     rcx, [rbx+28h]; this
0x1800239fa  call    ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
0x1800239ff  lea     rcx, [rbx+18h]; this
0x180023a03  mov     rbx, [rsp+28h+arg_0]
0x180023a08  mov     rsi, [rsp+28h+arg_8]
0x180023a0d  add     rsp, 20h
0x180023a11  pop     rdi
0x180023a12  jmp     ??1DispatchSupportedComObject@@IEAA@XZ; DispatchSupportedComObject::~DispatchSupportedComObject(void)
```
