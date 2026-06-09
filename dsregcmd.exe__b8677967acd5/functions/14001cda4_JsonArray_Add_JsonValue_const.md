# JsonArray::Add(JsonValue const *)

- ea: `0x14001cda4`
- end: `0x14001cdfd`
- name: `?Add@JsonArray@@QEAAXPEBVJsonValue@@@Z`
- size: `89`
- prototype: `void __fastcall(JsonArray *__hidden this, const struct JsonValue *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140023b80`
- `0x14002a154`

## callees

- `0x14001c3b0`
- `0x14001c78c`
- `0x14001cda4`
- `0x14002c3e8`

## pseudocode

```c
void __fastcall JsonArray::Add(JsonArray *this, const struct JsonValue *a2)
{
  _BYTE *v2; // rax
  _QWORD *v3; // rcx
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-18h] BYREF
  const struct JsonValue *v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = a2;
  if ( !a2 )
  {
    JsonException::JsonException((JsonException *)pExceptionObject, -895090685);
    throw (JsonException *)pExceptionObject;
  }
  v2 = (_BYTE *)*((_QWORD *)this + 3);
  v3 = (_QWORD *)((char *)this + 16);
  if ( v2 == (_BYTE *)v3[2] )
  {
    std::vector<JsonValue const *>::_Emplace_reallocate<JsonValue const * const &>(v3, v2, &v5);
  }
  else
  {
    *(_QWORD *)v2 = a2;
    v3[1] += 8LL;
  }
}

```

## disassembly

```asm
0x14001cda4  mov     [rsp+arg_8], rdx
0x14001cda9  sub     rsp, 38h
0x14001cdad  test    rdx, rdx
0x14001cdb0  jz      short loc_14001CDDC
0x14001cdb2  mov     rax, [rcx+18h]
0x14001cdb6  add     rcx, 10h
0x14001cdba  cmp     rax, [rcx+10h]
0x14001cdbe  jz      short loc_14001CDCA
0x14001cdc0  mov     [rax], rdx
0x14001cdc3  add     qword ptr [rcx+8], 8
0x14001cdc8  jmp     short loc_14001CDD7
0x14001cdca  lea     r8, [rsp+38h+arg_8]
0x14001cdcf  mov     rdx, rax
0x14001cdd2  call    ??$_Emplace_reallocate@AEBQEBVJsonValue@@@?$vector@PEBVJsonValue@@V?$allocator@PEBVJsonValue@@@std@@@std@@AEAAPEAPEBVJsonValue@@QEAPEBV2@AEBQEBV2@@Z; std::vector<JsonValue const *>::_Emplace_reallocate<JsonValue const * const &>(JsonValue const * * const,JsonValue const * const &)
0x14001cdd7  add     rsp, 38h
0x14001cddb  retn
0x14001cddc  mov     edx, 0CAA60003h; int
0x14001cde1  lea     rcx, [rsp+38h+pExceptionObject]; this
0x14001cde6  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x14001cdeb  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x14001cdf2  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x14001cdf7  call    _CxxThrowException_0
```
