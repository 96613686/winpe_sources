# std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Compile(void)

- ea: `0x18002dcd4`
- end: `0x18002ddad`
- name: `?_Compile@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Root_node@2@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18002a4e0`

## callees

- `0x180002fd4`
- `0x18002dcd4`
- `0x18002de68`
- `0x18002ebe0`
- `0x18002eca0`
- `0x18002fc54`

## pseudocode

```c
__int64 __fastcall std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Compile(
        __int64 a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 result; // rax

  try
  {
    v2 = operator new(0x28u);
    v3 = v2;
    if ( v2 )
    {
      v2[1] = 13;
      v2[2] = 0;
      v2[3] = 0;
      *v2 = &std::_Node_endif::`vftable';
      *((_DWORD *)v2 + 8) = 0;
    }
    else
    {
      v3 = 0;
    }
    v3[3] = *(_QWORD *)(a1 + 72);
    v4 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 16LL);
    if ( v4 )
    {
      v3[2] = v4;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 16LL) + 24LL) = v3;
    }
    *(_QWORD *)(*(_QWORD *)(a1 + 72) + 16LL) = v3;
    *(_QWORD *)(a1 + 72) = v3;
    std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(a1);
    if ( *(_QWORD *)a1 != *(_QWORD *)(a1 + 16) )
    {
      std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Error(v5, 14);
      JUMPOUT(0x18002DDABLL);
    }
    std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(a1 + 64, v3);
    std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(a1 + 64, 21);
    result = *(_QWORD *)(a1 + 64);
    *(_DWORD *)(result + 32) = *(_DWORD *)(a1 + 112);
    *(_DWORD *)(result + 40) = *(_DWORD *)(a1 + 24) + 1;
  }
  catch ( ... )
  {
    std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Discard_pattern(a1 + 64);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18002dcd4  mov     [rsp+arg_10], rbx
0x18002dcd9  mov     [rsp+arg_18], rsi
0x18002dcde  mov     [rsp+arg_0], rcx
0x18002dce3  push    rdi
0x18002dce4  sub     rsp, 20h
0x18002dce8  mov     rdi, rcx
0x18002dceb  mov     ecx, 28h ; '('; Size
0x18002dcf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002dcf5  mov     rbx, rax
0x18002dcf8  xor     edx, edx
0x18002dcfa  test    rax, rax
0x18002dcfd  jz      short loc_18002DD1E
0x18002dcff  mov     qword ptr [rax+8], 0Dh
0x18002dd07  mov     [rax+10h], rdx
0x18002dd0b  mov     [rax+18h], rdx
0x18002dd0f  lea     rax, ??_7_Node_endif@std@@6B@; const std::_Node_endif::`vftable'
0x18002dd16  mov     [rbx], rax
0x18002dd19  mov     [rbx+20h], edx
0x18002dd1c  jmp     short loc_18002DD21
0x18002dd1e  mov     rbx, rdx
0x18002dd21  mov     rax, [rdi+48h]
0x18002dd25  mov     [rbx+18h], rax
0x18002dd29  mov     rax, [rdi+48h]
0x18002dd2d  mov     rcx, [rax+10h]
0x18002dd31  test    rcx, rcx
0x18002dd34  jz      short loc_18002DD46
0x18002dd36  mov     [rbx+10h], rcx
0x18002dd3a  mov     rax, [rdi+48h]
0x18002dd3e  mov     rcx, [rax+10h]
0x18002dd42  mov     [rcx+18h], rbx
0x18002dd46  mov     rax, [rdi+48h]
0x18002dd4a  mov     [rax+10h], rbx
0x18002dd4e  mov     [rdi+48h], rbx
0x18002dd52  mov     rcx, rdi
0x18002dd55  call    ?_Disjunction@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)
0x18002dd5a  mov     rax, [rdi+10h]
0x18002dd5e  cmp     [rdi], rax
0x18002dd61  jnz     short loc_18002DDA1
0x18002dd63  lea     rsi, [rdi+40h]
0x18002dd67  mov     rdx, rbx
0x18002dd6a  mov     rcx, rsi
0x18002dd6d  call    ?_End_group@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18002dd72  mov     edx, 15h
0x18002dd77  mov     rcx, rsi
0x18002dd7a  call    ?_New_node@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x18002dd7f  mov     rax, [rsi]
0x18002dd82  mov     ecx, [rdi+70h]
0x18002dd85  mov     [rax+20h], ecx
0x18002dd88  mov     ecx, [rdi+18h]
0x18002dd8b  inc     ecx
0x18002dd8d  mov     [rax+28h], ecx
0x18002dd90  mov     rbx, [rsp+28h+arg_10]
0x18002dd95  mov     rsi, [rsp+28h+arg_18]
0x18002dd9a  add     rsp, 20h
0x18002dd9e  pop     rdi
0x18002dd9f  retn
0x18002dda1  mov     edx, 0Eh
0x18002dda6  call    ?_Error@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
```
