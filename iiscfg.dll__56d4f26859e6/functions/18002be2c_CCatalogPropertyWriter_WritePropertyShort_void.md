# CCatalogPropertyWriter::WritePropertyShort(void)

- ea: `0x18002be2c`
- end: `0x18002bf84`
- name: `?WritePropertyShort@CCatalogPropertyWriter@@AEAAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(CCatalogPropertyWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002b458`

## callees

- `0x18002ac94`
- `0x18002be2c`
- `0x18002c604`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002bf62`
- `ole32!CoTaskMemFree` at `0x18002bf62`

## string_xrefs

- `0x18002be45`: `			<Property       InheritsPropertiesFrom ="IIsConfigObject:`

## pseudocode

```c
__int64 __fastcall CCatalogPropertyWriter::WritePropertyShort(CCatalogPropertyWriter *this)
{
  CWriter *v2; // rcx
  void *v3; // rsi
  int v4; // ebx
  char *v5; // rdx
  __int64 v6; // rbp
  __int64 v7; // r8
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(CWriter **)this;
  v3 = 0;
  pv = 0;
  v4 = CWriter::WriteToFile(
         v2,
         (char *)L"\t\t\t<Property       InheritsPropertiesFrom =\"IIsConfigObject:",
         g_cchBeginPropertyShort,
         0);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v5 = (char *)*((_QWORD *)this + 3);
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&v5[2 * v7] );
  v4 = CWriter::WriteToFile(*(CWriter **)this, v5, v7, 0);
  if ( v4 < 0 )
    return (unsigned int)v4;
  if ( (**((_DWORD **)this + 13) & 0x200) == 0 )
    goto LABEL_12;
  v4 = CWriterGlobalHelper::FlagToString(
         *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
         0x200u,
         (unsigned __int16 **)&pv,
         L"COLUMNMETA",
         0xCu);
  if ( v4 < 0
    || (v4 = CWriter::WriteToFile(*(CWriter **)this, (char *)L"\"  MetaFlagsEx=\"", g_cchMetaFlagsExEq, 0), v4 < 0)
    || (v4 = CWriter::WriteToFile(*(CWriter **)this, (char *)L"| ", g_cchOr, 0), v4 < 0) )
  {
    v3 = pv;
  }
  else
  {
    v3 = pv;
    do
      ++v6;
    while ( *((_WORD *)pv + v6) );
    v4 = CWriter::WriteToFile(*(CWriter **)this, (char *)pv, v6, 0);
    if ( v4 >= 0 )
LABEL_12:
      v4 = CWriter::WriteToFile(*(CWriter **)this, (char *)L"\"/>\r\n", g_cchEndPropertyShort, 0);
  }
  if ( v3 )
    CoTaskMemFree(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002be2c  mov     [rsp+arg_8], rbx
0x18002be31  mov     [rsp+arg_10], rbp
0x18002be36  push    rsi
0x18002be37  push    rdi
0x18002be38  push    r14
0x18002be3a  sub     rsp, 30h
0x18002be3e  mov     r8d, cs:?g_cchBeginPropertyShort@@3KA; unsigned int
0x18002be45  lea     rdx, aPropertyInheri; "\t\t\t<Property       InheritsPropertie"...
0x18002be4c  mov     rdi, rcx
0x18002be4f  xor     r14d, r14d
0x18002be52  mov     rcx, [rcx]; this
0x18002be55  xor     r9d, r9d; int
0x18002be58  mov     esi, r14d
0x18002be5b  mov     [rsp+48h+pv], r14
0x18002be60  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002be65  mov     ebx, eax
0x18002be67  test    eax, eax
0x18002be69  js      loc_18002BF68
0x18002be6f  mov     rdx, [rdi+18h]; void *
0x18002be73  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18002be77  mov     r8, rbp
0x18002be7a  inc     r8; unsigned int
0x18002be7d  cmp     [rdx+r8*2], r14w
0x18002be82  jnz     short loc_18002BE7A
0x18002be84  mov     rcx, [rdi]; this
0x18002be87  xor     r9d, r9d; int
0x18002be8a  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002be8f  mov     ebx, eax
0x18002be91  test    eax, eax
0x18002be93  js      loc_18002BF68
0x18002be99  mov     rax, [rdi+68h]
0x18002be9d  mov     edx, 200h; unsigned int
0x18002bea2  test    [rax], edx
0x18002bea4  jz      loc_18002BF3F
0x18002beaa  mov     rcx, [rdi]
0x18002bead  lea     r9, aColumnmeta; "COLUMNMETA"
0x18002beb4  lea     r8, [rsp+48h+pv]; unsigned __int16 **
0x18002beb9  mov     [rsp+48h+var_28], 0Ch; unsigned int
0x18002bec1  mov     rcx, [rcx+10040h]; this
0x18002bec8  call    ?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z; CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)
0x18002becd  mov     ebx, eax
0x18002becf  test    eax, eax
0x18002bed1  js      loc_18002BF7D
0x18002bed7  mov     r8d, cs:?g_cchMetaFlagsExEq@@3KA; unsigned int
0x18002bede  lea     rdx, aMetaflagsex_0; "\"  MetaFlagsEx=\""
0x18002bee5  mov     rcx, [rdi]; this
0x18002bee8  xor     r9d, r9d; int
0x18002beeb  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002bef0  mov     ebx, eax
0x18002bef2  test    eax, eax
0x18002bef4  js      loc_18002BF7D
0x18002befa  mov     r8d, cs:?g_cchOr@@3KA; unsigned int
0x18002bf01  lea     rdx, asc_18003D368; "| "
0x18002bf08  mov     rcx, [rdi]; this
0x18002bf0b  xor     r9d, r9d; int
0x18002bf0e  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002bf13  mov     ebx, eax
0x18002bf15  test    eax, eax
0x18002bf17  js      short loc_18002BF7D
0x18002bf19  mov     rsi, [rsp+48h+pv]
0x18002bf1e  inc     rbp
0x18002bf21  cmp     [rsi+rbp*2], r14w
0x18002bf26  jnz     short loc_18002BF1E
0x18002bf28  mov     rcx, [rdi]; this
0x18002bf2b  xor     r9d, r9d; int
0x18002bf2e  mov     r8d, ebp; unsigned int
0x18002bf31  mov     rdx, rsi; void *
0x18002bf34  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002bf39  mov     ebx, eax
0x18002bf3b  test    eax, eax
0x18002bf3d  js      short loc_18002BF5A
0x18002bf3f  mov     r8d, cs:?g_cchEndPropertyShort@@3KA; unsigned int
0x18002bf46  lea     rdx, asc_18003D138; "\"/>\r\n"
0x18002bf4d  mov     rcx, [rdi]; this
0x18002bf50  xor     r9d, r9d; int
0x18002bf53  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002bf58  mov     ebx, eax
0x18002bf5a  test    rsi, rsi
0x18002bf5d  jz      short loc_18002BF68
0x18002bf5f  mov     rcx, rsi; pv
0x18002bf62  call    cs:__imp_CoTaskMemFree
0x18002bf68  mov     rbp, [rsp+48h+arg_10]
0x18002bf6d  mov     eax, ebx
0x18002bf6f  mov     rbx, [rsp+48h+arg_8]
0x18002bf74  add     rsp, 30h
0x18002bf78  pop     r14
0x18002bf7a  pop     rdi
0x18002bf7b  pop     rsi
0x18002bf7c  retn
0x18002bf7d  mov     rsi, [rsp+48h+pv]
0x18002bf82  jmp     short loc_18002BF5A
```
