# JsonReader::ParseNameValuePair(JSON_PARSER_TOKEN,JsonObject &)

- ea: `0x140023e64`
- end: `0x140024013`
- name: `?ParseNameValuePair@JsonReader@@AEAAXW4JSON_PARSER_TOKEN@@AEAVJsonObject@@@Z`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140023c5c`

## callees

- `0x140001814`
- `0x140001b60`
- `0x1400032ec`
- `0x14001c78c`
- `0x14001c7ac`
- `0x14001ce88`
- `0x140023844`
- `0x140023e64`
- `0x14002410c`
- `0x1400244d4`
- `0x1400245d4`
- `0x14002c3e8`

## string_xrefs

- `0x140023f14`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall JsonReader::ParseNameValuePair(__int64 a1, int a2, __int64 a3)
{
  int CurrentToken; // eax
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rdx
  struct JsonValue *v9; // rax
  struct JsonValue *v10; // rbx
  JsonObject *v11; // rax
  _DWORD *v13; // [rsp+20h] [rbp-40h]
  _QWORD pExceptionObject[2]; // [rsp+28h] [rbp-38h] BYREF
  char *v15[4]; // [rsp+38h] [rbp-28h] BYREF

  if ( a2 != 5 )
  {
    JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
    throw (JsonException *)pExceptionObject;
  }
  JsonReader::ParseString(a1, v15);
  CurrentToken = JsonReader::GetCurrentToken(a1);
  v6 = *(unsigned int *)(a1 + 48);
  if ( *(_WORD *)(*(_QWORD *)(a1 + 40) + 2 * v6) )
    *(_DWORD *)(a1 + 48) = v6 + 1;
  if ( CurrentToken != 8 )
  {
    JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
    throw (JsonException *)pExceptionObject;
  }
  v7 = JsonReader::GetCurrentToken(a1);
  v8 = *(unsigned int *)(a1 + 48);
  if ( *(_WORD *)(*(_QWORD *)(a1 + 40) + 2 * v8) )
    *(_DWORD *)(a1 + 48) = v8 + 1;
  if ( v7 == 9 || v7 == 6 )
  {
    if ( v7 == 9 )
    {
      v9 = (struct JsonValue *)operator new(
                                 0x28u,
                                 1,
                                 "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jsonreader.cpp");
      v10 = v9;
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
        v10 = 0;
      }
    }
    else
    {
      v11 = (JsonObject *)operator new(0x20u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jsonreader.cpp");
      pExceptionObject[0] = v11;
      if ( v11 )
        v10 = JsonObject::JsonObject(v11);
      else
        v10 = 0;
    }
    JsonReader::PushToStack((JsonReader *)a1, v10);
    JsonObject::AddNameToValueMapping(a3, (__int64)v15, (__int64)v10);
  }
  else
  {
    v13 = JsonReader::ParseSimpleValue(a1, v7);
    JsonObject::AddNameToValueMapping(a3, (__int64)v15, (__int64)v13);
  }
  return std::wstring::~wstring(v15);
}

```

## disassembly

```asm
0x140023e64  mov     [rsp-18h+arg_8], rbx
0x140023e69  mov     [rsp-18h+arg_18], rsi
0x140023e6e  push    rbp
0x140023e6f  push    rdi
0x140023e70  push    r14
0x140023e72  mov     rbp, rsp
0x140023e75  sub     rsp, 60h
0x140023e79  mov     rax, cs:__security_cookie
0x140023e80  xor     rax, rsp
0x140023e83  mov     [rbp+var_8], rax
0x140023e87  mov     rsi, r8
0x140023e8a  mov     rdi, rcx
0x140023e8d  cmp     edx, 5
0x140023e90  jnz     loc_140023FF4
0x140023e96  lea     rdx, [rbp+var_28]
0x140023e9a  call    ?ParseString@JsonReader@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; JsonReader::ParseString(void)
0x140023e9f  nop
0x140023ea0  mov     rcx, rdi
0x140023ea3  call    ?GetCurrentToken@JsonReader@@AEAA?AW4JSON_PARSER_TOKEN@@XZ; JsonReader::GetCurrentToken(void)
0x140023ea8  mov     edx, [rdi+30h]
0x140023eab  mov     rcx, [rdi+28h]
0x140023eaf  xor     r14d, r14d
0x140023eb2  cmp     [rcx+rdx*2], r14w
0x140023eb7  jz      short loc_140023EBF
0x140023eb9  lea     ecx, [rdx+1]
0x140023ebc  mov     [rdi+30h], ecx
0x140023ebf  cmp     eax, 8
0x140023ec2  jnz     loc_140023FD5
0x140023ec8  mov     rcx, rdi
0x140023ecb  call    ?GetCurrentToken@JsonReader@@AEAA?AW4JSON_PARSER_TOKEN@@XZ; JsonReader::GetCurrentToken(void)
0x140023ed0  mov     edx, [rdi+30h]
0x140023ed3  mov     rcx, [rdi+28h]
0x140023ed7  cmp     [rcx+rdx*2], r14w
0x140023edc  jz      short loc_140023EE3
0x140023ede  inc     edx
0x140023ee0  mov     [rdi+30h], edx
0x140023ee3  cmp     eax, 9
0x140023ee6  jz      short loc_140023F10
0x140023ee8  cmp     eax, 6
0x140023eeb  jz      short loc_140023F10
0x140023eed  mov     edx, eax
0x140023eef  mov     rcx, rdi
0x140023ef2  call    ?ParseSimpleValue@JsonReader@@AEAAPEAVJsonPrimitive@@W4JSON_PARSER_TOKEN@@@Z; JsonReader::ParseSimpleValue(JSON_PARSER_TOKEN)
0x140023ef7  mov     [rbp+var_40], rax
0x140023efb  mov     r8, rax
0x140023efe  lea     rdx, [rbp+var_28]
0x140023f02  mov     rcx, rsi
0x140023f05  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@Z; JsonObject::AddNameToValueMapping(std::wstring const &,JsonValue const *)
0x140023f0a  nop
0x140023f0b  jmp     loc_140023FAB
0x140023f10  mov     [rbp+var_40], r14
0x140023f14  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140023f1b  mov     edx, 1; int
0x140023f20  cmp     eax, 9
0x140023f23  jnz     short loc_140023F63
0x140023f25  mov     r9d, 0CCh; int
0x140023f2b  lea     ecx, [rdx+27h]; unsigned __int64
0x140023f2e  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140023f33  mov     rbx, rax
0x140023f36  mov     [rbp+var_40], rax
0x140023f3a  test    rax, rax
0x140023f3d  jz      short loc_140023F5E
0x140023f3f  mov     dword ptr [rax+8], 2
0x140023f46  lea     rax, ??_7JsonArray@@6B@; const JsonArray::`vftable'
0x140023f4d  mov     [rbx], rax
0x140023f50  mov     [rbx+10h], r14
0x140023f54  mov     [rbx+18h], r14
0x140023f58  mov     [rbx+20h], r14
0x140023f5c  jmp     short loc_140023F8C
0x140023f5e  mov     rbx, r14
0x140023f61  jmp     short loc_140023F8C
0x140023f63  mov     r9d, 0CEh; int
0x140023f69  mov     ecx, 20h ; ' '; unsigned __int64
0x140023f6e  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140023f73  mov     [rbp+pExceptionObject], rax
0x140023f77  test    rax, rax
0x140023f7a  jz      short loc_140023F89
0x140023f7c  mov     rcx, rax; this
0x140023f7f  call    ??0JsonObject@@QEAA@XZ; JsonObject::JsonObject(void)
0x140023f84  mov     rbx, rax
0x140023f87  jmp     short loc_140023F8C
0x140023f89  mov     rbx, r14
0x140023f8c  mov     [rbp+var_40], rbx
0x140023f90  mov     rdx, rbx; struct JsonValue *
0x140023f93  mov     rcx, rdi; this
0x140023f96  call    ?PushToStack@JsonReader@@AEAAXPEAVJsonValue@@@Z; JsonReader::PushToStack(JsonValue *)
0x140023f9b  mov     r8, rbx
0x140023f9e  lea     rdx, [rbp+var_28]
0x140023fa2  mov     rcx, rsi
0x140023fa5  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@Z; JsonObject::AddNameToValueMapping(std::wstring const &,JsonValue const *)
0x140023faa  nop
0x140023fab  lea     rcx, [rbp+var_28]
0x140023faf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023fb4  mov     rcx, [rbp+var_8]
0x140023fb8  xor     rcx, rsp; StackCookie
0x140023fbb  call    __security_check_cookie
0x140023fc0  lea     r11, [rsp+60h+var_s0]
0x140023fc5  mov     rbx, [r11+28h]
0x140023fc9  mov     rsi, [r11+38h]
0x140023fcd  mov     rsp, r11
0x140023fd0  pop     r14
0x140023fd2  pop     rdi
0x140023fd3  pop     rbp
0x140023fd4  retn
0x140023fd5  mov     edx, 0CAA60007h; int
0x140023fda  lea     rcx, [rbp+pExceptionObject]; this
0x140023fde  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x140023fe3  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023fea  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140023fee  call    _CxxThrowException_0
0x140023ff4  mov     edx, 0CAA60007h; int
0x140023ff9  lea     rcx, [rbp+pExceptionObject]; this
0x140023ffd  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x140024002  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140024009  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002400d  call    _CxxThrowException_0
```
