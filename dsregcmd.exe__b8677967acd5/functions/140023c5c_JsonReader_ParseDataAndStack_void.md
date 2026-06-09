# JsonReader::ParseDataAndStack(void)

- ea: `0x140023c5c`
- end: `0x140023e5b`
- name: `?ParseDataAndStack@JsonReader@@AEAAXXZ`
- size: `511`
- prototype: `void __fastcall(JsonReader *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400239a4`

## callees

- `0x14001c78c`
- `0x140023844`
- `0x140023b80`
- `0x140023c5c`
- `0x140023e64`
- `0x14002c3e8`

## pseudocode

```c
void __fastcall JsonReader::ParseDataAndStack(JsonReader *this)
{
  _QWORD *v2; // rdi
  __int16 v3; // dx
  __int64 v4; // rcx
  __int64 v5; // rsi
  unsigned int CurrentToken; // eax
  __int64 v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  bool v10; // zf
  unsigned int v11; // eax
  __int64 v12; // rcx
  bool v13; // zf
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  v2 = (_QWORD *)((char *)this + 32);
  while ( 1 )
  {
    v3 = *(_WORD *)(*((_QWORD *)this + 5) + 2LL * *((unsigned int *)this + 12));
    if ( !v3 )
      break;
    v2 = (_QWORD *)((char *)this + 32);
    v4 = *((_QWORD *)this + 4);
    if ( !v4 )
      break;
    v5 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 1)
                               + 8
                               * ((*((_QWORD *)this + 2) - 1LL)
                                & ((unsigned __int64)(v4 + *((_QWORD *)this + 3) - 1LL) >> 1)))
                   + 8LL * (((_DWORD)v4 + *((_DWORD *)this + 6) - 1) & 1));
    CurrentToken = JsonReader::GetCurrentToken((__int64)this);
    v7 = *((unsigned int *)this + 12);
    v8 = CurrentToken;
    if ( *(_WORD *)(*((_QWORD *)this + 5) + 2 * v7) )
      *((_DWORD *)this + 12) = v7 + 1;
    if ( CurrentToken == 7 || CurrentToken == 10 )
    {
      v10 = (*v2)-- == 1;
      if ( v10 )
        *((_QWORD *)this + 3) = 0;
    }
    else
    {
      v9 = *(_DWORD *)(v5 + 8);
      if ( (_DWORD)v8 == 11 )
      {
        if ( v9 == 1 )
        {
          v10 = *(_QWORD *)(v5 + 24) == 0;
LABEL_13:
          if ( v10 )
          {
            JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
            throw (JsonException *)pExceptionObject;
          }
        }
        else if ( v9 == 2 )
        {
          v10 = *(_QWORD *)(v5 + 24) == *(_QWORD *)(v5 + 16);
          goto LABEL_13;
        }
        v11 = JsonReader::GetCurrentToken((__int64)this);
        v12 = *((unsigned int *)this + 12);
        v8 = v11;
        if ( *(_WORD *)(*((_QWORD *)this + 5) + 2 * v12) )
          *((_DWORD *)this + 12) = v12 + 1;
        if ( v11 == 7 || v11 == 10 )
        {
          JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
          throw (JsonException *)pExceptionObject;
        }
        goto LABEL_24;
      }
      if ( v9 == 1 )
      {
        v13 = *(_QWORD *)(v5 + 24) == 0;
      }
      else
      {
        if ( v9 != 2 )
          goto LABEL_24;
        v13 = *(_QWORD *)(v5 + 24) == *(_QWORD *)(v5 + 16);
      }
      if ( !v13 )
      {
        JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
        throw (JsonException *)pExceptionObject;
      }
LABEL_24:
      if ( *(_DWORD *)(v5 + 8) == 1 )
        JsonReader::ParseNameValuePair((__int64)this, v8, v5);
      else
        JsonReader::ParseArrayValue(this, v8, (JsonArray *)v5);
    }
  }
  if ( *v2 )
  {
    JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
    throw (JsonException *)pExceptionObject;
  }
  if ( v3 && (unsigned int)JsonReader::GetCurrentToken((__int64)this) != 12 )
  {
    JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
    throw (JsonException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x140023c5c  push    rbx
0x140023c5e  push    rbp
0x140023c5f  push    rsi
0x140023c60  push    rdi
0x140023c61  sub     rsp, 38h
0x140023c65  mov     rbx, rcx
0x140023c68  lea     rdi, [rcx+20h]
0x140023c6c  xor     ebp, ebp
0x140023c6e  mov     ecx, [rbx+30h]
0x140023c71  mov     rax, [rbx+28h]
0x140023c75  movzx   edx, word ptr [rax+rcx*2]
0x140023c79  test    dx, dx
0x140023c7c  jz      loc_140023D92
0x140023c82  lea     rdi, [rbx+20h]
0x140023c86  mov     rcx, [rdi]
0x140023c89  test    rcx, rcx
0x140023c8c  jz      loc_140023D92
0x140023c92  mov     rdx, [rbx+18h]
0x140023c96  mov     rax, [rbx+10h]
0x140023c9a  dec     rdx
0x140023c9d  add     rdx, rcx
0x140023ca0  dec     rax
0x140023ca3  mov     rcx, rdx
0x140023ca6  and     edx, 1
0x140023ca9  shr     rcx, 1
0x140023cac  and     rcx, rax
0x140023caf  mov     rax, [rbx+8]
0x140023cb3  mov     rax, [rax+rcx*8]
0x140023cb7  mov     rcx, rbx
0x140023cba  mov     rsi, [rax+rdx*8]
0x140023cbe  call    ?GetCurrentToken@JsonReader@@AEAA?AW4JSON_PARSER_TOKEN@@XZ; JsonReader::GetCurrentToken(void)
0x140023cc3  mov     ecx, [rbx+30h]
0x140023cc6  mov     edx, eax
0x140023cc8  mov     rax, [rbx+28h]
0x140023ccc  cmp     [rax+rcx*2], bp
0x140023cd0  jz      short loc_140023CD8
0x140023cd2  lea     eax, [rcx+1]
0x140023cd5  mov     [rbx+30h], eax
0x140023cd8  cmp     edx, 7
0x140023cdb  jz      loc_140023D7F
0x140023ce1  cmp     edx, 0Ah
0x140023ce4  jz      loc_140023D7F
0x140023cea  mov     eax, [rsi+8]
0x140023ced  cmp     edx, 0Bh
0x140023cf0  jnz     short loc_140023D41
0x140023cf2  cmp     eax, 1
0x140023cf5  jnz     short loc_140023CFD
0x140023cf7  cmp     [rsi+18h], rbp
0x140023cfb  jmp     short loc_140023D0A
0x140023cfd  cmp     eax, 2
0x140023d00  jnz     short loc_140023D10
0x140023d02  mov     rax, [rsi+18h]
0x140023d06  cmp     rax, [rsi+10h]
0x140023d0a  jz      loc_140023DF8
0x140023d10  mov     rcx, rbx
0x140023d13  call    ?GetCurrentToken@JsonReader@@AEAA?AW4JSON_PARSER_TOKEN@@XZ; JsonReader::GetCurrentToken(void)
0x140023d18  mov     ecx, [rbx+30h]
0x140023d1b  mov     edx, eax
0x140023d1d  mov     rax, [rbx+28h]
0x140023d21  cmp     [rax+rcx*2], bp
0x140023d25  jz      short loc_140023D2D
0x140023d27  lea     eax, [rcx+1]
0x140023d2a  mov     [rbx+30h], eax
0x140023d2d  cmp     edx, 7
0x140023d30  jz      loc_140023DD7
0x140023d36  cmp     edx, 0Ah
0x140023d39  jz      loc_140023DD7
0x140023d3f  jmp     short loc_140023D5F
0x140023d41  cmp     eax, 1
0x140023d44  jnz     short loc_140023D4C
0x140023d46  cmp     [rsi+18h], rbp
0x140023d4a  jmp     short loc_140023D59
0x140023d4c  cmp     eax, 2
0x140023d4f  jnz     short loc_140023D5F
0x140023d51  mov     rax, [rsi+18h]
0x140023d55  cmp     rax, [rsi+10h]
0x140023d59  jnz     loc_140023E19
0x140023d5f  cmp     dword ptr [rsi+8], 1
0x140023d63  mov     r8, rsi
0x140023d66  mov     rcx, rbx
0x140023d69  jnz     short loc_140023D75
0x140023d6b  call    ?ParseNameValuePair@JsonReader@@AEAAXW4JSON_PARSER_TOKEN@@AEAVJsonObject@@@Z; JsonReader::ParseNameValuePair(JSON_PARSER_TOKEN,JsonObject &)
0x140023d70  jmp     loc_140023C6E
0x140023d75  call    ?ParseArrayValue@JsonReader@@AEAAXW4JSON_PARSER_TOKEN@@AEAVJsonArray@@@Z; JsonReader::ParseArrayValue(JSON_PARSER_TOKEN,JsonArray &)
0x140023d7a  jmp     loc_140023C6E
0x140023d7f  sub     qword ptr [rdi], 1
0x140023d83  jnz     loc_140023C6E
0x140023d89  mov     [rbx+18h], rbp
0x140023d8d  jmp     loc_140023C6E
0x140023d92  cmp     [rdi], rbp
0x140023d95  jnz     loc_140023E3A
0x140023d9b  test    dx, dx
0x140023d9e  jz      short loc_140023DAD
0x140023da0  mov     rcx, rbx
0x140023da3  call    ?GetCurrentToken@JsonReader@@AEAA?AW4JSON_PARSER_TOKEN@@XZ; JsonReader::GetCurrentToken(void)
0x140023da8  cmp     eax, 0Ch
0x140023dab  jnz     short loc_140023DB6
0x140023dad  add     rsp, 38h
0x140023db1  pop     rdi
0x140023db2  pop     rsi
0x140023db3  pop     rbp
0x140023db4  pop     rbx
0x140023db5  retn
0x140023db6  mov     edx, 0CAA60007h; int
0x140023dbb  lea     rcx, [rsp+58h+pExceptionObject]; this
0x140023dc0  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x140023dc5  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023dcc  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140023dd1  call    _CxxThrowException_0
0x140023dd7  mov     edx, 0CAA60007h; int
0x140023ddc  lea     rcx, [rsp+58h+pExceptionObject]; this
0x140023de1  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x140023de6  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023ded  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140023df2  call    _CxxThrowException_0
0x140023df8  mov     edx, 0CAA60007h; int
0x140023dfd  lea     rcx, [rsp+58h+pExceptionObject]; this
0x140023e02  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x140023e07  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023e0e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140023e13  call    _CxxThrowException_0
0x140023e19  mov     edx, 0CAA60007h; int
0x140023e1e  lea     rcx, [rsp+58h+pExceptionObject]; this
0x140023e23  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x140023e28  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023e2f  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140023e34  call    _CxxThrowException_0
0x140023e3a  mov     edx, 0CAA60007h; int
0x140023e3f  lea     rcx, [rsp+58h+pExceptionObject]; this
0x140023e44  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x140023e49  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023e50  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140023e55  call    _CxxThrowException_0
```
