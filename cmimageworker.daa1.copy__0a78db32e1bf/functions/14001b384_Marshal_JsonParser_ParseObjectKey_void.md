# Marshal::JsonParser::ParseObjectKey(void)

- ea: `0x14001b384`
- end: `0x14001b47d`
- name: `?ParseObjectKey@JsonParser@Marshal@@AEAAXXZ`
- size: `249`
- prototype: `void __fastcall(Marshal::JsonParser *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14001a3c4`
- `0x14001e274`

## callees

- `0x140002d4e`
- `0x140014138`
- `0x14001b384`
- `0x14001b484`
- `0x14002e8d8`

## pseudocode

```c
void __fastcall Marshal::JsonParser::ParseObjectKey(Marshal::JsonParser *this)
{
  _QWORD *v2; // rax
  char **v3; // rcx
  unsigned __int64 v4; // rdx
  char *v5; // rsi
  __int64 v6; // rbx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // rax
  __int64 v10; // r10
  unsigned __int64 v11; // r9
  bool v12; // cf
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_QWORD *)Marshal::JsonParser::ParseString(this);
  v3 = (char **)((char *)this + 32);
  if ( (_QWORD *)((char *)this + 32) != v2 )
  {
    v4 = v2[2];
    if ( v2[3] > 7u )
      v2 = (_QWORD *)*v2;
    if ( v4 > *((_QWORD *)this + 7) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v3);
    }
    else
    {
      if ( *((_QWORD *)this + 7) <= 7u )
        v5 = (char *)this + 32;
      else
        v5 = *v3;
      v6 = 2 * v4;
      *((_QWORD *)this + 6) = v4;
      memmove_0(v5, v2, 2 * v4);
      *(_WORD *)&v5[v6] = 0;
    }
  }
  v7 = *((_QWORD *)this + 1);
  v8 = *((_QWORD *)this + 2);
  if ( v8 >= v7 || *(_WORD *)(*(_QWORD *)this + 2 * v8) != 58 )
  {
    pExceptionObject = 11;
    throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
  }
  v9 = *((_QWORD *)this + 1);
  v10 = 1;
  if ( v7 >= v8 + 1 )
    v9 = v8 + 1;
  *((_QWORD *)this + 3) = v9;
  while ( 1 )
  {
    v11 = v8 + v10;
    v12 = v7 < v8 + v10;
    if ( v7 <= v8 + v10 )
      break;
    if ( *(_WORD *)(*(_QWORD *)this + 2 * v11) != 9
      && *(_WORD *)(*(_QWORD *)this + 2 * v11) != 10
      && *(_WORD *)(*(_QWORD *)this + 2 * v11) != 13
      && *(_WORD *)(*(_QWORD *)this + 2 * v11) != 32 )
    {
      v12 = v7 < v11;
      break;
    }
    ++v10;
  }
  if ( !v12 )
    v7 = v8 + v10;
  *((_QWORD *)this + 2) = v7;
}

```

## disassembly

```asm
0x14001b384  mov     [rsp+arg_8], rbx
0x14001b389  mov     [rsp+arg_10], rsi
0x14001b38e  push    rdi
0x14001b38f  sub     rsp, 20h
0x14001b393  mov     rdi, rcx
0x14001b396  call    ?ParseString@JsonParser@Marshal@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Marshal::JsonParser::ParseString(void)
0x14001b39b  lea     rcx, [rdi+20h]
0x14001b39f  cmp     rcx, rax
0x14001b3a2  jz      short loc_14001B3ED
0x14001b3a4  cmp     qword ptr [rax+18h], 7
0x14001b3a9  mov     rdx, [rax+10h]
0x14001b3ad  jbe     short loc_14001B3B2
0x14001b3af  mov     rax, [rax]
0x14001b3b2  cmp     rdx, [rcx+18h]
0x14001b3b6  ja      short loc_14001B3E5
0x14001b3b8  cmp     qword ptr [rcx+18h], 7
0x14001b3bd  jbe     short loc_14001B3C4
0x14001b3bf  mov     rsi, [rcx]
0x14001b3c2  jmp     short loc_14001B3C7
0x14001b3c4  mov     rsi, rcx
0x14001b3c7  lea     rbx, [rdx+rdx]
0x14001b3cb  mov     [rcx+10h], rdx
0x14001b3cf  mov     r8, rbx; Size
0x14001b3d2  mov     rdx, rax; Src
0x14001b3d5  mov     rcx, rsi; void *
0x14001b3d8  call    memmove_0
0x14001b3dd  xor     eax, eax
0x14001b3df  mov     [rbx+rsi], ax
0x14001b3e3  jmp     short loc_14001B3ED
0x14001b3e5  mov     r9, rax
0x14001b3e8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14001b3ed  mov     rdx, [rdi+8]
0x14001b3f1  mov     r8, [rdi+10h]
0x14001b3f5  cmp     r8, rdx
0x14001b3f8  jnb     short loc_14001B463
0x14001b3fa  mov     rax, [rdi]
0x14001b3fd  cmp     word ptr [rax+r8*2], 3Ah ; ':'
0x14001b403  jnz     short loc_14001B463
0x14001b405  lea     rcx, [r8+1]
0x14001b409  mov     rax, rdx
0x14001b40c  cmp     rdx, rcx
0x14001b40f  mov     r10d, 1
0x14001b415  cmovnb  rax, rcx
0x14001b419  mov     [rdi+18h], rax
0x14001b41d  lea     r9, [r8+r10]
0x14001b421  cmp     rdx, r9
0x14001b424  jbe     short loc_14001B44A
0x14001b426  mov     rax, [rdi]
0x14001b429  movzx   ecx, word ptr [rax+r9*2]
0x14001b42e  sub     ecx, 9
0x14001b431  jz      short loc_14001B442
0x14001b433  sub     ecx, 1
0x14001b436  jz      short loc_14001B442
0x14001b438  sub     ecx, 3
0x14001b43b  jz      short loc_14001B442
0x14001b43d  cmp     ecx, 13h
0x14001b440  jnz     short loc_14001B447
0x14001b442  inc     r10
0x14001b445  jmp     short loc_14001B41D
0x14001b447  cmp     rdx, r9
0x14001b44a  mov     rbx, [rsp+28h+arg_8]
0x14001b44f  cmovnb  rdx, r9
0x14001b453  mov     rsi, [rsp+28h+arg_10]
0x14001b458  mov     [rdi+10h], rdx
0x14001b45c  add     rsp, 20h
0x14001b460  pop     rdi
0x14001b461  retn
0x14001b463  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001b46a  mov     [rsp+28h+pExceptionObject], 0Bh
0x14001b472  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14001b477  call    _CxxThrowException_0
```
