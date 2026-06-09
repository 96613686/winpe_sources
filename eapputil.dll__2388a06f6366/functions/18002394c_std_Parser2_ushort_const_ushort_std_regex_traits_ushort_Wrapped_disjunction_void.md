# std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Wrapped_disjunction(void)

- ea: `0x18002394c`
- end: `0x180023a75`
- name: `?_Wrapped_disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ`
- size: `297`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x1800203d8`

## callees

- `0x1800207d4`
- `0x180021640`
- `0x180021764`
- `0x180021dd4`
- `0x1800223f8`
- `0x180022474`
- `0x18002349c`
- `0x18002394c`
- `0x180024d50`

## import_xrefs

- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x1800239ed`
- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x1800239ed`

## pseudocode

```c
char __fastcall std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Wrapped_disjunction(
        __int64 a1)
{
  int *v2; // rbx
  int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v7; // rdi

  if ( (int)++*(_DWORD *)(a1 + 20) >= 1000 )
    std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Error(a1, 12);
  v2 = (int *)(a1 + 112);
  if ( (*(_QWORD *)(a1 + 96) & 0x4000000LL) == 0 && *v2 == 41 )
    std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Error(a1, 5);
  if ( (*(_BYTE *)(a1 + 96) & 0x20) == 0 || *v2 != 63 )
  {
    if ( (*(_DWORD *)(a1 + 104) & 0x200) == 0 )
    {
      if ( ++*(_DWORD *)(a1 + 16) >= 0x3E8u )
      {
        std::_Xregex_error(12);
        __debugbreak();
      }
      v7 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Begin_capture_group(a1 + 56);
      std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(a1);
      std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(a1 + 56, v7);
      std::vector<bool>::resize(a1 + 24, (unsigned int)(*(_DWORD *)(a1 + 16) + 1));
      *(_DWORD *)(*(_QWORD *)(a1 + 24) + 4 * ((unsigned __int64)*(unsigned int *)(v7 + 32) >> 5)) |= 1 << (*(_BYTE *)(v7 + 32) & 0x1F);
      goto LABEL_17;
    }
LABEL_13:
    std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Do_noncapture_group(a1);
LABEL_17:
    --*(_DWORD *)(a1 + 20);
    return 1;
  }
  std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Next((_QWORD *)a1);
  v3 = *v2;
  std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Next((_QWORD *)a1);
  switch ( v3 )
  {
    case ':':
      goto LABEL_13;
    case '!':
      LOBYTE(v4) = 1;
      break;
    case '=':
      v4 = 0;
      break;
    default:
      std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Error(v5, 10);
  }
  std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Do_assert_group(a1, v4);
  --*(_DWORD *)(a1 + 20);
  return 0;
}

```

## disassembly

```asm
0x18002394c  mov     [rsp+arg_0], rbx
0x180023951  mov     [rsp+arg_8], rsi
0x180023956  push    rdi
0x180023957  sub     rsp, 20h
0x18002395b  inc     dword ptr [rcx+14h]
0x18002395e  mov     eax, 3E8h
0x180023963  mov     rsi, rcx
0x180023966  cmp     [rcx+14h], eax
0x180023969  jge     loc_180023A5F
0x18002396f  test    qword ptr [rcx+60h], 4000000h
0x180023977  lea     rbx, [rcx+70h]
0x18002397b  jnz     short loc_180023986
0x18002397d  cmp     dword ptr [rbx], 29h ; ')'
0x180023980  jz      loc_180023A6A
0x180023986  test    byte ptr [rcx+60h], 20h
0x18002398a  jz      short loc_1800239CB
0x18002398c  cmp     dword ptr [rbx], 3Fh ; '?'
0x18002398f  jnz     short loc_1800239CB
0x180023991  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x180023996  mov     ebx, [rbx]
0x180023998  mov     rcx, rsi
0x18002399b  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x1800239a0  cmp     ebx, 3Ah ; ':'
0x1800239a3  jz      short loc_1800239D4
0x1800239a5  cmp     ebx, 21h ; '!'
0x1800239a8  jnz     short loc_1800239BE
0x1800239aa  mov     dl, 1
0x1800239ac  mov     rcx, rsi
0x1800239af  call    ?_Do_assert_group@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAX_N@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Do_assert_group(bool)
0x1800239b4  dec     dword ptr [rsi+14h]
0x1800239b7  xor     al, al
0x1800239b9  jmp     loc_180023A44
0x1800239be  cmp     ebx, 3Dh ; '='
0x1800239c1  jnz     loc_180023A54
0x1800239c7  xor     edx, edx
0x1800239c9  jmp     short loc_1800239AC
0x1800239cb  test    dword ptr [rcx+68h], 200h
0x1800239d2  jz      short loc_1800239DE
0x1800239d4  mov     rcx, rsi
0x1800239d7  call    ?_Do_noncapture_group@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Do_noncapture_group(void)
0x1800239dc  jmp     short loc_180023A3F
0x1800239de  inc     dword ptr [rcx+10h]
0x1800239e1  mov     edx, [rcx+10h]
0x1800239e4  cmp     edx, eax
0x1800239e6  jb      short loc_1800239F4
0x1800239e8  mov     ecx, 0Ch
0x1800239ed  call    cs:__imp_?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z; std::_Xregex_error(std::regex_constants::error_type)
0x1800239f3  int     3; Trap to Debugger
0x1800239f4  add     rcx, 38h ; '8'
0x1800239f8  call    ?_Begin_capture_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@I@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_capture_group(uint)
0x1800239fd  mov     rcx, rsi
0x180023a00  mov     rdi, rax
0x180023a03  call    ?_Disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)
0x180023a08  mov     rdx, rdi
0x180023a0b  lea     rcx, [rsi+38h]
0x180023a0f  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x180023a14  mov     edx, [rsi+10h]
0x180023a17  lea     rcx, [rsi+18h]
0x180023a1b  inc     edx
0x180023a1d  call    ?resize@?$vector@_NV?$allocator@_N@std@@@std@@QEAAX_K_N@Z; std::vector<bool>::resize(unsigned __int64,bool)
0x180023a22  mov     r8d, [rdi+20h]
0x180023a26  mov     rcx, [rsi+18h]
0x180023a2a  mov     edx, r8d
0x180023a2d  shr     rdx, 5
0x180023a31  and     r8d, 1Fh
0x180023a35  mov     eax, [rcx+rdx*4]
0x180023a38  bts     eax, r8d
0x180023a3c  mov     [rcx+rdx*4], eax
0x180023a3f  dec     dword ptr [rsi+14h]
0x180023a42  mov     al, 1
0x180023a44  mov     rbx, [rsp+28h+arg_0]
0x180023a49  mov     rsi, [rsp+28h+arg_8]
0x180023a4e  add     rsp, 20h
0x180023a52  pop     rdi
0x180023a53  retn
0x180023a54  mov     edx, 0Ah
0x180023a59  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
0x180023a5f  mov     edx, 0Ch
0x180023a64  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
0x180023a6a  mov     edx, 5
0x180023a6f  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
```
