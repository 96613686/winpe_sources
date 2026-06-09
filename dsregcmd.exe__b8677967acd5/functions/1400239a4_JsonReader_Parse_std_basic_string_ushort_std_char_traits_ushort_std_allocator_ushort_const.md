# JsonReader::Parse(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400239a4`
- end: `0x140023b79`
- name: `?Parse@JsonReader@@QEAAPEAVJsonValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `469`
- prototype: `JsonObject *__fastcall(void **this, _QWORD *)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000d384`
- `0x14000ea0c`
- `0x140024cc0`
- `0x1400251d4`

## callees

- `0x1400017d4`
- `0x140001814`
- `0x1400028ac`
- `0x14000df44`
- `0x14001c78c`
- `0x14001c7ac`
- `0x140023844`
- `0x1400239a4`
- `0x140023c5c`
- `0x14002410c`
- `0x1400245d4`
- `0x14002c3e8`

## string_xrefs

- `0x140023aad`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`
- `0x140023af5`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`

## pseudocode

```c
JsonObject *__fastcall JsonReader::Parse(void **this, _QWORD *a2)
{
  void ***v3; // rax
  _QWORD *v4; // rax
  void ***v5; // rcx
  void *v6; // rcx
  unsigned int CurrentToken; // eax
  __int64 v8; // rdx
  JsonObject *v9; // rax
  JsonObject *v10; // rax
  JsonObject *v11; // rdi
  _BYTE pExceptionObject[16]; // [rsp+20h] [rbp-40h] BYREF
  void *Block[2]; // [rsp+30h] [rbp-30h] BYREF
  void *v15; // [rsp+40h] [rbp-20h]
  void *v16; // [rsp+48h] [rbp-18h]
  void *v17; // [rsp+50h] [rbp-10h]

  if ( !a2[2] )
  {
    JsonException::JsonException((JsonException *)pExceptionObject, -895090685);
    throw (JsonException *)pExceptionObject;
  }
  *((_DWORD *)this + 12) = 0;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  this[5] = a2;
  *(_OWORD *)Block = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v3 = (void ***)operator new(0x10u);
  v3[1] = 0;
  Block[0] = v3;
  *v3 = Block;
  if ( this != Block )
  {
    std::deque<JsonValue *>::_Tidy(this);
    v4 = *this;
    v5 = (void ***)Block[0];
    *this = Block[0];
    Block[0] = v4;
    if ( v5 )
    {
      *v5 = this;
      v4 = Block[0];
    }
    if ( v4 )
      *v4 = Block;
    this[1] = Block[1];
    this[2] = v15;
    this[3] = v16;
    this[4] = v17;
    Block[1] = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
  }
  std::deque<JsonValue *>::_Tidy(Block);
  v6 = Block[0];
  Block[0] = 0;
  operator delete(v6);
  CurrentToken = JsonReader::GetCurrentToken((__int64)this);
  v8 = *((unsigned int *)this + 12);
  if ( *((_WORD *)this[5] + v8) )
    *((_DWORD *)this + 12) = v8 + 1;
  if ( CurrentToken == 9 )
  {
    v9 = (JsonObject *)operator new(0x28u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jsonreader.cpp");
    if ( v9 )
    {
      *((_DWORD *)v9 + 2) = 2;
      *(_QWORD *)v9 = &JsonArray::`vftable';
      *((_QWORD *)v9 + 2) = 0;
      *((_QWORD *)v9 + 3) = 0;
      *((_QWORD *)v9 + 4) = 0;
    }
    else
    {
      v9 = 0;
    }
LABEL_20:
    v11 = v9;
    JsonReader::PushToStack((JsonReader *)this, v9);
    JsonReader::ParseDataAndStack((JsonReader *)this);
    return v11;
  }
  if ( CurrentToken == 6 )
  {
    v10 = (JsonObject *)operator new(0x20u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jsonreader.cpp");
    if ( v10 )
      v9 = JsonObject::JsonObject(v10);
    else
      v9 = 0;
    goto LABEL_20;
  }
  return (JsonObject *)JsonReader::ParseSimpleValue(this, CurrentToken);
}

```

## disassembly

```asm
0x1400239a4  mov     [rsp-8+arg_0], rbx
0x1400239a9  mov     [rsp-8+arg_18], rdi
0x1400239ae  push    rbp
0x1400239af  mov     rbp, rsp
0x1400239b2  sub     rsp, 60h
0x1400239b6  mov     rbx, rcx
0x1400239b9  xor     edi, edi
0x1400239bb  cmp     [rdx+10h], rdi
0x1400239bf  jz      loc_140023B5A
0x1400239c5  mov     [rbp+arg_8], rdi
0x1400239c9  mov     [rcx+30h], edi
0x1400239cc  cmp     qword ptr [rdx+18h], 7
0x1400239d1  jbe     short loc_1400239D6
0x1400239d3  mov     rdx, [rdx]
0x1400239d6  mov     [rcx+28h], rdx
0x1400239da  xorps   xmm0, xmm0
0x1400239dd  movdqu  xmmword ptr [rbp+Block], xmm0
0x1400239e2  mov     [rbp+var_20], rdi
0x1400239e6  mov     [rbp+var_18], rdi
0x1400239ea  mov     [rbp+var_10], rdi
0x1400239ee  mov     ecx, 10h; Size
0x1400239f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400239f8  mov     [rax+8], rdi
0x1400239fc  mov     [rbp+Block], rax
0x140023a00  lea     rcx, [rbp+Block]
0x140023a04  mov     [rax], rcx
0x140023a07  lea     rax, [rbp+Block]
0x140023a0b  cmp     rbx, rax
0x140023a0e  jz      short loc_140023A6E
0x140023a10  mov     rcx, rbx
0x140023a13  call    ?_Tidy@?$deque@PEAVJsonValue@@V?$allocator@PEAVJsonValue@@@std@@@std@@AEAAXXZ; std::deque<JsonValue *>::_Tidy(void)
0x140023a18  mov     rax, [rbx]
0x140023a1b  mov     rcx, [rbp+Block]
0x140023a1f  mov     [rbx], rcx
0x140023a22  mov     [rbp+Block], rax
0x140023a26  test    rcx, rcx
0x140023a29  jz      short loc_140023A32
0x140023a2b  mov     [rcx], rbx
0x140023a2e  mov     rax, [rbp+Block]
0x140023a32  test    rax, rax
0x140023a35  jz      short loc_140023A3E
0x140023a37  lea     rcx, [rbp+Block]
0x140023a3b  mov     [rax], rcx
0x140023a3e  mov     rax, [rbp+Block+8]
0x140023a42  mov     [rbx+8], rax
0x140023a46  mov     rax, [rbp+var_20]
0x140023a4a  mov     [rbx+10h], rax
0x140023a4e  mov     rax, [rbp+var_18]
0x140023a52  mov     [rbx+18h], rax
0x140023a56  mov     rax, [rbp+var_10]
0x140023a5a  mov     [rbx+20h], rax
0x140023a5e  mov     [rbp+Block+8], rdi
0x140023a62  mov     [rbp+var_20], rdi
0x140023a66  mov     [rbp+var_18], rdi
0x140023a6a  mov     [rbp+var_10], rdi
0x140023a6e  lea     rcx, [rbp+Block]
0x140023a72  call    ?_Tidy@?$deque@PEAVJsonValue@@V?$allocator@PEAVJsonValue@@@std@@@std@@AEAAXXZ; std::deque<JsonValue *>::_Tidy(void)
0x140023a77  mov     rcx, [rbp+Block]; Block
0x140023a7b  mov     [rbp+Block], rdi
0x140023a7f  mov     edx, 10h
0x140023a84  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x140023a89  mov     rcx, rbx
0x140023a8c  call    ?GetCurrentToken@JsonReader@@AEAA?AW4JSON_PARSER_TOKEN@@XZ; JsonReader::GetCurrentToken(void)
0x140023a91  mov     edx, [rbx+30h]
0x140023a94  mov     rcx, [rbx+28h]
0x140023a98  cmp     [rcx+rdx*2], di
0x140023a9c  jz      short loc_140023AA4
0x140023a9e  lea     ecx, [rdx+1]
0x140023aa1  mov     [rbx+30h], ecx
0x140023aa4  cmp     eax, 9
0x140023aa7  jnz     short loc_140023AEC
0x140023aa9  lea     r9d, [rax+26h]; int
0x140023aad  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140023ab4  lea     edx, [rax-8]; int
0x140023ab7  lea     ecx, [rax+1Fh]; unsigned __int64
0x140023aba  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140023abf  mov     [rbp+arg_8], rax
0x140023ac3  test    rax, rax
0x140023ac6  jz      short loc_140023AE7
0x140023ac8  mov     dword ptr [rax+8], 2
0x140023acf  lea     rcx, ??_7JsonArray@@6B@; const JsonArray::`vftable'
0x140023ad6  mov     [rax], rcx
0x140023ad9  mov     [rax+10h], rdi
0x140023add  mov     [rax+18h], rdi
0x140023ae1  mov     [rax+20h], rdi
0x140023ae5  jmp     short loc_140023B1D
0x140023ae7  mov     rax, rdi
0x140023aea  jmp     short loc_140023B1D
0x140023aec  cmp     eax, 6
0x140023aef  jnz     short loc_140023B3D
0x140023af1  lea     r9d, [rax+2Dh]; int
0x140023af5  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140023afc  lea     edx, [rax-5]; int
0x140023aff  lea     ecx, [rax+1Ah]; unsigned __int64
0x140023b02  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140023b07  mov     [rbp+arg_10], rax
0x140023b0b  test    rax, rax
0x140023b0e  jz      short loc_140023B1A
0x140023b10  mov     rcx, rax; this
0x140023b13  call    ??0JsonObject@@QEAA@XZ; JsonObject::JsonObject(void)
0x140023b18  jmp     short loc_140023B1D
0x140023b1a  mov     rax, rdi
0x140023b1d  mov     rdi, rax
0x140023b20  mov     [rbp+arg_8], rax
0x140023b24  mov     rdx, rax; struct JsonValue *
0x140023b27  mov     rcx, rbx; this
0x140023b2a  call    ?PushToStack@JsonReader@@AEAAXPEAVJsonValue@@@Z; JsonReader::PushToStack(JsonValue *)
0x140023b2f  mov     rcx, rbx; this
0x140023b32  call    ?ParseDataAndStack@JsonReader@@AEAAXXZ; JsonReader::ParseDataAndStack(void)
0x140023b37  nop
0x140023b38  mov     rax, rdi
0x140023b3b  jmp     short loc_140023B48
0x140023b3d  mov     edx, eax
0x140023b3f  mov     rcx, rbx
0x140023b42  call    ?ParseSimpleValue@JsonReader@@AEAAPEAVJsonPrimitive@@W4JSON_PARSER_TOKEN@@@Z; JsonReader::ParseSimpleValue(JSON_PARSER_TOKEN)
0x140023b47  nop
0x140023b48  lea     r11, [rsp+60h+var_s0]
0x140023b4d  mov     rbx, [r11+10h]
0x140023b51  mov     rdi, [r11+28h]
0x140023b55  mov     rsp, r11
0x140023b58  pop     rbp
0x140023b59  retn
0x140023b5a  mov     edx, 0CAA60003h; int
0x140023b5f  lea     rcx, [rbp+pExceptionObject]; this
0x140023b63  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x140023b68  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023b6f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140023b73  call    _CxxThrowException_0
```
