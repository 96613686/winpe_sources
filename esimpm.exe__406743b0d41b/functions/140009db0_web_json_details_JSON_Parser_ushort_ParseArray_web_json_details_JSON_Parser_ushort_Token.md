# web::json::details::JSON_Parser<ushort>::_ParseArray(web::json::details::JSON_Parser<ushort>::Token &)

- ea: `0x140009db0`
- end: `0x140009f6f`
- name: `?_ParseArray@?$JSON_Parser@G@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z`
- size: `447`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000a3c0`

## callees

- `0x140002f84`
- `0x1400064b0`
- `0x140007f60`
- `0x1400088d0`
- `0x1400098a0`
- `0x140009cb0`
- `0x140009db0`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall web::json::details::JSON_Parser<unsigned short>::_ParseArray(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  __int64 *v8; // rax
  _QWORD *v9; // rcx
  const struct web::json::details::json_error_category_impl *v10; // rax
  _QWORD *v11; // rax
  int v13; // [rsp+2Ch] [rbp-3Ch]
  _QWORD *v14; // [rsp+80h] [rbp+18h] BYREF
  _QWORD *v15; // [rsp+88h] [rbp+20h]

  web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
  if ( *(_DWORD *)(a3 + 72) )
  {
    v6 = operator new(8u);
    v14 = v6;
    if ( v6 )
    {
      *v6 = &web::json::details::_Null::`vftable';
      *a2 = v6;
    }
    else
    {
      *a2 = 0;
    }
  }
  else
  {
    v7 = operator new(0x20u);
    v14 = v7;
    if ( v7 )
    {
      *v7 = &web::json::details::_Array::`vftable';
      v7[1] = 0;
      v7[2] = 0;
      v7[3] = 0;
    }
    else
    {
      v7 = 0;
    }
    v15 = v7;
    if ( *(_DWORD *)a3 == 4 )
    {
LABEL_20:
      web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
      if ( !*(_DWORD *)(a3 + 72) )
      {
        *a2 = v7;
        return a2;
      }
    }
    else
    {
      do
      {
        v8 = (__int64 *)web::json::details::JSON_Parser<unsigned short>::ParseValue(a1, &v14, a3);
        v9 = (_QWORD *)v7[2];
        if ( v9 == (_QWORD *)v7[3] )
        {
          std::vector<web::json::value>::_Emplace_reallocate<web::json::value>(v7 + 1, v7[2], (__int64)v8);
        }
        else
        {
          web::json::value::value(v9, v8);
          v7[2] += 8LL;
        }
        if ( v14 )
          (*(void (__fastcall **)(_QWORD *, __int64))(*v14 + 192LL))(v14, 1);
        if ( *(_DWORD *)(a3 + 72) )
          break;
        if ( *(_DWORD *)a3 == 4 )
          goto LABEL_20;
        if ( *(_DWORD *)a3 != 5 )
        {
          v10 = web::json::details::json_error_category((web::json::details *)(unsigned int)(*(_DWORD *)a3 - 4));
          *(_DWORD *)(a3 + 72) = 2;
          *(_DWORD *)(a3 + 76) = v13;
          *(_QWORD *)(a3 + 80) = v10;
          break;
        }
        web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
      }
      while ( !*(_DWORD *)(a3 + 72) );
    }
    v11 = operator new(8u);
    v14 = v11;
    if ( v11 )
      *v11 = &web::json::details::_Null::`vftable';
    else
      v11 = 0;
    *a2 = v11;
    if ( v7 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v7 + 192LL))(v7, 1);
  }
  return a2;
}

```

## disassembly

```asm
0x140009db0  mov     [rsp+arg_0], rbx
0x140009db5  push    rbp
0x140009db6  push    rsi
0x140009db7  push    rdi
0x140009db8  push    r14
0x140009dba  push    r15
0x140009dbc  sub     rsp, 40h
0x140009dc0  mov     rdi, r8
0x140009dc3  mov     rsi, rdx
0x140009dc6  mov     r14, rcx
0x140009dc9  xor     r15d, r15d
0x140009dcc  mov     rdx, r8
0x140009dcf  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x140009dd4  cmp     [rdi+48h], r15d
0x140009dd8  jz      short loc_140009E0E
0x140009dda  mov     ecx, 8; Size
0x140009ddf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009de4  mov     [rsp+68h+arg_10], rax
0x140009dec  test    rax, rax
0x140009def  jz      short loc_140009E03
0x140009df1  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x140009df8  mov     [rax], rcx
0x140009dfb  mov     [rsi], rax
0x140009dfe  jmp     loc_140009F5B
0x140009e03  mov     rax, r15
0x140009e06  mov     [rsi], rax
0x140009e09  jmp     loc_140009F5B
0x140009e0e  mov     ecx, 20h ; ' '; Size
0x140009e13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009e18  mov     rbx, rax
0x140009e1b  mov     [rsp+68h+arg_10], rax
0x140009e23  test    rax, rax
0x140009e26  jz      short loc_140009E40
0x140009e28  lea     rax, ??_7_Array@details@json@web@@6B@; const web::json::details::_Array::`vftable'
0x140009e2f  mov     [rbx], rax
0x140009e32  mov     [rbx+8], r15
0x140009e36  mov     [rbx+10h], r15
0x140009e3a  mov     [rbx+18h], r15
0x140009e3e  jmp     short loc_140009E43
0x140009e40  mov     rbx, r15
0x140009e43  mov     [rsp+68h+arg_18], rbx
0x140009e4b  cmp     dword ptr [rdi], 4
0x140009e4e  jz      loc_140009F00
0x140009e54  nop     dword ptr [rax+00h]
0x140009e58  nop     dword ptr [rax+rax+00000000h]
0x140009e60  mov     r8, rdi
0x140009e63  lea     rdx, [rsp+68h+arg_10]
0x140009e6b  mov     rcx, r14
0x140009e6e  call    ?ParseValue@?$JSON_Parser@G@details@json@web@@QEAA?AVvalue@34@AEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::ParseValue(web::json::details::JSON_Parser<ushort>::Token &)
0x140009e73  nop
0x140009e74  mov     rcx, [rbx+10h]
0x140009e78  cmp     rcx, [rbx+18h]
0x140009e7c  jz      short loc_140009E8D
0x140009e7e  mov     rdx, rax
0x140009e81  call    ??0value@json@web@@QEAA@$$QEAV012@@Z; web::json::value::value(web::json::value &&)
0x140009e86  add     qword ptr [rbx+10h], 8
0x140009e8b  jmp     short loc_140009E9D
0x140009e8d  mov     r8, rax
0x140009e90  mov     rdx, rcx
0x140009e93  lea     rcx, [rbx+8]
0x140009e97  call    ??$_Emplace_reallocate@Vvalue@json@web@@@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAPEAVvalue@json@web@@QEAV234@$$QEAV234@@Z; std::vector<web::json::value>::_Emplace_reallocate<web::json::value>(web::json::value * const,web::json::value &&)
0x140009e9c  nop
0x140009e9d  mov     rcx, [rsp+68h+arg_10]
0x140009ea5  test    rcx, rcx
0x140009ea8  jz      short loc_140009EBE
0x140009eaa  mov     rax, [rcx]
0x140009ead  mov     edx, 1
0x140009eb2  mov     rax, [rax+0C0h]
0x140009eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ebe  cmp     dword ptr [rdi+48h], 0
0x140009ec2  jnz     short loc_140009F11
0x140009ec4  mov     ecx, [rdi]
0x140009ec6  sub     ecx, 4; this
0x140009ec9  jz      short loc_140009F00
0x140009ecb  cmp     ecx, 1
0x140009ece  jnz     short loc_140009EE7
0x140009ed0  mov     rdx, rdi
0x140009ed3  mov     rcx, r14
0x140009ed6  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x140009edb  cmp     dword ptr [rdi+48h], 0
0x140009edf  jz      loc_140009E60
0x140009ee5  jmp     short loc_140009F11
0x140009ee7  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x140009eec  mov     dword ptr [rdi+48h], 2
0x140009ef3  mov     ecx, [rsp+68h+var_3C]
0x140009ef7  mov     [rdi+4Ch], ecx
0x140009efa  mov     [rdi+50h], rax
0x140009efe  jmp     short loc_140009F11
0x140009f00  mov     rdx, rdi
0x140009f03  mov     rcx, r14
0x140009f06  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x140009f0b  cmp     dword ptr [rdi+48h], 0
0x140009f0f  jz      short loc_140009F58
0x140009f11  mov     ecx, 8; Size
0x140009f16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009f1b  mov     [rsp+68h+arg_10], rax
0x140009f23  test    rax, rax
0x140009f26  jz      short loc_140009F34
0x140009f28  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x140009f2f  mov     [rax], rcx
0x140009f32  jmp     short loc_140009F37
0x140009f34  mov     rax, r15
0x140009f37  mov     [rsi], rax
0x140009f3a  test    rbx, rbx
0x140009f3d  jz      short loc_140009F5B
0x140009f3f  mov     rax, [rbx]
0x140009f42  mov     edx, 1
0x140009f47  mov     rcx, rbx
0x140009f4a  mov     rax, [rax+0C0h]
0x140009f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f56  jmp     short loc_140009F5B
0x140009f58  mov     [rsi], rbx
0x140009f5b  mov     rax, rsi
0x140009f5e  mov     rbx, [rsp+68h+arg_0]
0x140009f63  add     rsp, 40h
0x140009f67  pop     r15
0x140009f69  pop     r14
0x140009f6b  pop     rdi
0x140009f6c  pop     rsi
0x140009f6d  pop     rbp
0x140009f6e  retn
```
