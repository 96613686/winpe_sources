# CGlobalMappingBuilder::~CGlobalMappingBuilder(void)

- ea: `0x18007c0c0`
- end: `0x18007c1c4`
- name: `??1CGlobalMappingBuilder@@UEAA@XZ`
- size: `260`
- prototype: `void __fastcall(CGlobalMappingBuilder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007c2f0`

## callees

- `0x180047a60`
- `0x18006ba5c`
- `0x18006ed20`
- `0x18007c0c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c14a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c16e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c18c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c14a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c16e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c18c`

## pseudocode

```c
void __fastcall CGlobalMappingBuilder::~CGlobalMappingBuilder(CGlobalMappingBuilder *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  _QWORD v6[2]; // [rsp+20h] [rbp-28h] BYREF

  *(_QWORD *)this = &CGlobalMappingBuilder::`vftable';
  v6[0] = CSchemaCache::s_ReleaseCB<IPropertyDescription>;
  v6[1] = 0;
  CByteHashTable::_RemoveCallback(
    (CGlobalMappingBuilder *)((char *)this + 200),
    1,
    CHashTable<CSchemaData,_GUID>::s_DestroyCallback,
    v6);
  v2 = (void *)*((_QWORD *)this + 21);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 21) = 0;
  }
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 24) = 0;
  v3 = (void *)*((_QWORD *)this + 17);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 17) = 0;
  }
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 20) = 0;
  v4 = (void *)*((_QWORD *)this + 13);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 13) = 0;
  }
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 16) = 0;
  v5 = (void *)*((_QWORD *)this + 9);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 9) = 0;
  }
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 12) = 0;
  CCacheFileBuilder<SCHEMA_HEADER,CSchemaBuilder>::~CCacheFileBuilder<SCHEMA_HEADER,CSchemaBuilder>(this);
}

```

## disassembly

```asm
0x18007c0c0  mov     r11, rsp
0x18007c0c3  mov     [r11+10h], rbx
0x18007c0c7  mov     [r11+18h], rsi
0x18007c0cb  push    rdi
0x18007c0cc  sub     rsp, 40h
0x18007c0d0  mov     rax, cs:__security_cookie
0x18007c0d7  xor     rax, rsp
0x18007c0da  mov     [rsp+48h+var_18], rax
0x18007c0df  mov     rbx, rcx
0x18007c0e2  lea     rax, ??_7CGlobalMappingBuilder@@6B@; const CGlobalMappingBuilder::`vftable'
0x18007c0e9  mov     [rcx], rax
0x18007c0ec  lea     rax, ??$s_ReleaseCB@UIPropertyDescription@@@CSchemaCache@@SAXPEAUIPropertyDescription@@@Z; CSchemaCache::s_ReleaseCB<IPropertyDescription>(IPropertyDescription *)
0x18007c0f3  mov     [r11-28h], rax
0x18007c0f7  xor     esi, esi
0x18007c0f9  mov     [r11-20h], rsi
0x18007c0fd  add     rcx, 0C8h; this
0x18007c104  lea     r9, [r11-28h]; void *
0x18007c108  lea     r8, ?s_DestroyCallback@?$CHashTable@VCSchemaData@@U_GUID@@@@CAXPEAEIPEAX@Z; void (*)(unsigned __int8 *, unsigned int, void *)
0x18007c10f  lea     edx, [rsi+1]; int
0x18007c112  call    ?_RemoveCallback@CByteHashTable@@AEAAXHP6AXPEAEIPEAX@Z1@Z; CByteHashTable::_RemoveCallback(int,void (*)(uchar *,uint,void *),void *)
0x18007c117  mov     rcx, [rbx+0A8h]; pv
0x18007c11e  test    rcx, rcx
0x18007c121  jz      short loc_18007C130
0x18007c123  call    cs:__imp_CoTaskMemFree
0x18007c129  mov     [rbx+0A8h], rsi
0x18007c130  mov     [rbx+0B0h], rsi
0x18007c137  mov     [rbx+0C0h], rsi
0x18007c13e  mov     rcx, [rbx+88h]; pv
0x18007c145  test    rcx, rcx
0x18007c148  jz      short loc_18007C157
0x18007c14a  call    cs:__imp_CoTaskMemFree
0x18007c150  mov     [rbx+88h], rsi
0x18007c157  mov     [rbx+90h], rsi
0x18007c15e  mov     [rbx+0A0h], rsi
0x18007c165  mov     rcx, [rbx+68h]; pv
0x18007c169  test    rcx, rcx
0x18007c16c  jz      short loc_18007C178
0x18007c16e  call    cs:__imp_CoTaskMemFree
0x18007c174  mov     [rbx+68h], rsi
0x18007c178  mov     [rbx+70h], rsi
0x18007c17c  mov     [rbx+80h], rsi
0x18007c183  mov     rcx, [rbx+48h]; pv
0x18007c187  test    rcx, rcx
0x18007c18a  jz      short loc_18007C196
0x18007c18c  call    cs:__imp_CoTaskMemFree
0x18007c192  mov     [rbx+48h], rsi
0x18007c196  mov     [rbx+50h], rsi
0x18007c19a  mov     [rbx+60h], rsi
0x18007c19e  mov     rcx, rbx
0x18007c1a1  call    ??1?$CCacheFileBuilder@USCHEMA_HEADER@@VCSchemaBuilder@@@@UEAA@XZ; CCacheFileBuilder<SCHEMA_HEADER,CSchemaBuilder>::~CCacheFileBuilder<SCHEMA_HEADER,CSchemaBuilder>(void)
0x18007c1a6  nop
0x18007c1a7  mov     rcx, [rsp+48h+var_18]
0x18007c1ac  xor     rcx, rsp; StackCookie
0x18007c1af  call    __security_check_cookie
0x18007c1b4  mov     rbx, [rsp+48h+arg_8]
0x18007c1b9  mov     rsi, [rsp+48h+arg_10]
0x18007c1be  add     rsp, 40h
0x18007c1c2  pop     rdi
0x18007c1c3  retn
```
