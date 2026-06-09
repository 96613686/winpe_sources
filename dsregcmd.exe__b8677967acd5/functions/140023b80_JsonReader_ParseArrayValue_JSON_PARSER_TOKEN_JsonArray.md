# JsonReader::ParseArrayValue(JSON_PARSER_TOKEN,JsonArray &)

- ea: `0x140023b80`
- end: `0x140023c53`
- name: `?ParseArrayValue@JsonReader@@AEAAXW4JSON_PARSER_TOKEN@@AEAVJsonArray@@@Z`
- size: `211`
- prototype: `void __fastcall(JsonReader *, __int64, JsonArray *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140023c5c`

## callees

- `0x140001814`
- `0x14001c7ac`
- `0x14001cda4`
- `0x140023b80`
- `0x14002410c`
- `0x1400245d4`

## string_xrefs

- `0x140023bba`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`
- `0x140023bed`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall JsonReader::ParseArrayValue(JsonReader *a1, __int64 a2, JsonArray *a3)
{
  const struct JsonValue *v5; // rax
  JsonObject *v6; // rax
  const struct JsonValue *v7; // rbx
  _DWORD *v8; // rax

  if ( (_DWORD)a2 == 9 )
  {
    v8 = operator new(0x28u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jsonreader.cpp");
    v7 = 0;
    if ( v8 )
    {
      v8[2] = 2;
      *(_QWORD *)v8 = &JsonArray::`vftable';
      *((_QWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 3) = 0;
      *((_QWORD *)v8 + 4) = 0;
      v7 = (const struct JsonValue *)v8;
    }
  }
  else
  {
    if ( (_DWORD)a2 != 6 )
    {
      v5 = (const struct JsonValue *)JsonReader::ParseSimpleValue(a1, a2);
      JsonArray::Add(a3, v5);
      return;
    }
    v6 = (JsonObject *)operator new(0x20u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jsonreader.cpp");
    v7 = 0;
    if ( v6 )
      v7 = JsonObject::JsonObject(v6);
  }
  JsonArray::Add(a3, v7);
  JsonReader::PushToStack(a1, v7);
}

```

## disassembly

```asm
0x140023b80  mov     [rsp+arg_0], rbx
0x140023b85  mov     [rsp+arg_8], rsi
0x140023b8a  push    rdi
0x140023b8b  sub     rsp, 20h
0x140023b8f  mov     rdi, r8
0x140023b92  mov     rsi, rcx
0x140023b95  cmp     edx, 9
0x140023b98  jz      short loc_140023BE7
0x140023b9a  cmp     edx, 6
0x140023b9d  jz      short loc_140023BB4
0x140023b9f  call    ?ParseSimpleValue@JsonReader@@AEAAPEAVJsonPrimitive@@W4JSON_PARSER_TOKEN@@@Z; JsonReader::ParseSimpleValue(JSON_PARSER_TOKEN)
0x140023ba4  mov     rdx, rax; struct JsonValue *
0x140023ba7  mov     rcx, rdi; this
0x140023baa  call    ?Add@JsonArray@@QEAAXPEBVJsonValue@@@Z; JsonArray::Add(JsonValue const *)
0x140023baf  jmp     loc_140023C43
0x140023bb4  mov     r9d, 0F4h; int
0x140023bba  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140023bc1  mov     edx, 1; int
0x140023bc6  lea     ecx, [rdx+1Fh]; unsigned __int64
0x140023bc9  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140023bce  mov     [rsp+28h+arg_18], rax
0x140023bd3  xor     ebx, ebx
0x140023bd5  test    rax, rax
0x140023bd8  jz      short loc_140023BE5
0x140023bda  mov     rcx, rax; this
0x140023bdd  call    ??0JsonObject@@QEAA@XZ; JsonObject::JsonObject(void)
0x140023be2  mov     rbx, rax
0x140023be5  jmp     short loc_140023C2D
0x140023be7  mov     r9d, 0F2h; int
0x140023bed  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140023bf4  mov     edx, 1; int
0x140023bf9  lea     ecx, [rdx+27h]; unsigned __int64
0x140023bfc  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140023c01  mov     [rsp+28h+arg_18], rax
0x140023c06  xor     ebx, ebx
0x140023c08  test    rax, rax
0x140023c0b  jz      short loc_140023C2D
0x140023c0d  mov     dword ptr [rax+8], 2
0x140023c14  lea     rcx, ??_7JsonArray@@6B@; const JsonArray::`vftable'
0x140023c1b  mov     [rax], rcx
0x140023c1e  mov     [rax+10h], rbx
0x140023c22  mov     [rax+18h], rbx
0x140023c26  mov     [rax+20h], rbx
0x140023c2a  mov     rbx, rax
0x140023c2d  mov     rdx, rbx; struct JsonValue *
0x140023c30  mov     rcx, rdi; this
0x140023c33  call    ?Add@JsonArray@@QEAAXPEBVJsonValue@@@Z; JsonArray::Add(JsonValue const *)
0x140023c38  mov     rdx, rbx; struct JsonValue *
0x140023c3b  mov     rcx, rsi; this
0x140023c3e  call    ?PushToStack@JsonReader@@AEAAXPEAVJsonValue@@@Z; JsonReader::PushToStack(JsonValue *)
0x140023c43  mov     rbx, [rsp+28h+arg_0]
0x140023c48  mov     rsi, [rsp+28h+arg_8]
0x140023c4d  add     rsp, 20h
0x140023c51  pop     rdi
0x140023c52  retn
```
