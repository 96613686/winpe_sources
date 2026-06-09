# std::list<CommandSet,std::allocator<CommandSet>>::merge(std::list<CommandSet,std::allocator<CommandSet>> &)

- ea: `0x140009af4`
- end: `0x140009c00`
- name: `?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009ecc`

## callees

- `0x140009af4`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009bb1`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009bb1`

## pseudocode

```c
void __fastcall std::list<CommandSet>::merge(__int64 ***a1, __int64 ***a2)
{
  __int64 **v2; // r10
  __int64 **v4; // r9
  __int64 **v6; // r8
  __int64 **v7; // rax
  __int64 **v8; // rdx
  __int64 *v9; // r11
  __int64 *v10; // rdx
  __int64 **v11; // rcx
  unsigned __int64 v12; // rdx
  __int64 *v13; // rdx

  if ( a2 != a1 )
  {
    v2 = *a1;
    v4 = *a2;
    v6 = (__int64 **)**a1;
    v7 = (__int64 **)**a2;
    while ( v6 != v2 )
    {
      if ( v7 == v4 )
        return;
      if ( *((_DWORD *)v7 + 4) >= *((_DWORD *)v6 + 4) )
      {
        v6 = (__int64 **)*v6;
      }
      else
      {
        v8 = a1[1];
        if ( v8 == (__int64 **)0x38E38E38E38E38DLL )
          goto LABEL_11;
        v9 = *v7;
        a1[1] = (__int64 **)((char *)v8 + 1);
        a2[1] = (__int64 **)((char *)a2[1] - 1);
        *v7[1] = (__int64)v9;
        *(_QWORD *)v9[1] = v6;
        *v6[1] = (__int64)v7;
        v10 = v6[1];
        v6[1] = (__int64 *)v9[1];
        v9[1] = (__int64)v7[1];
        v7[1] = v10;
        v7 = (__int64 **)v9;
      }
    }
    if ( v7 != v4 )
    {
      v11 = a1[1];
      v12 = (unsigned __int64)a2[1];
      if ( 0x38E38E38E38E38DLL - (__int64)v11 < v12 )
LABEL_11:
        std::_Xlength_error("list<T> too long");
      a1[1] = (__int64 **)((char *)v11 + v12);
      a2[1] = (__int64 **)((char *)a2[1] - v12);
      *v7[1] = (__int64)v4;
      *v4[1] = (__int64)v2;
      *v2[1] = (__int64)v7;
      v13 = v2[1];
      v2[1] = v4[1];
      v4[1] = v7[1];
      v7[1] = v13;
    }
  }
}

```

## disassembly

```asm
0x140009af4  cmp     rdx, rcx
0x140009af7  jz      locret_140009BFF
0x140009afd  mov     [rsp+arg_0], rbx
0x140009b02  mov     [rsp+arg_8], rsi
0x140009b07  push    rdi
0x140009b08  sub     rsp, 20h
0x140009b0c  mov     r10, [rcx]
0x140009b0f  mov     rdi, rdx
0x140009b12  mov     r9, [rdx]
0x140009b15  mov     rbx, rcx
0x140009b18  mov     rsi, 38E38E38E38E38Dh
0x140009b22  mov     r8, [r10]
0x140009b25  mov     rax, [r9]
0x140009b28  cmp     r8, r10
0x140009b2b  jz      short loc_140009B95
0x140009b2d  cmp     rax, r9
0x140009b30  jz      loc_140009BF0
0x140009b36  mov     ecx, [r8+10h]
0x140009b3a  cmp     [rax+10h], ecx
0x140009b3d  jnb     short loc_140009B90
0x140009b3f  mov     rdx, [rbx+8]
0x140009b43  mov     rcx, rsi
0x140009b46  sub     rcx, rdx
0x140009b49  cmp     rcx, 1
0x140009b4d  jb      short loc_140009BAA
0x140009b4f  mov     r11, [rax]
0x140009b52  lea     rcx, [rdx+1]
0x140009b56  mov     [rbx+8], rcx
0x140009b5a  dec     qword ptr [rdi+8]
0x140009b5e  mov     rcx, [rax+8]
0x140009b62  mov     [rcx], r11
0x140009b65  mov     rcx, [r11+8]
0x140009b69  mov     [rcx], r8
0x140009b6c  mov     rcx, [r8+8]
0x140009b70  mov     [rcx], rax
0x140009b73  mov     rcx, [r11+8]
0x140009b77  mov     rdx, [r8+8]
0x140009b7b  mov     [r8+8], rcx
0x140009b7f  mov     rcx, [rax+8]
0x140009b83  mov     [r11+8], rcx
0x140009b87  mov     [rax+8], rdx
0x140009b8b  mov     rax, r11
0x140009b8e  jmp     short loc_140009B28
0x140009b90  mov     r8, [r8]
0x140009b93  jmp     short loc_140009B28
0x140009b95  cmp     rax, r9
0x140009b98  jz      short loc_140009BF0
0x140009b9a  mov     rcx, [rbx+8]
0x140009b9e  mov     rdx, [rdi+8]
0x140009ba2  sub     rsi, rcx
0x140009ba5  cmp     rsi, rdx
0x140009ba8  jnb     short loc_140009BB8
0x140009baa  lea     rcx, aListTTooLong; "list<T> too long"
0x140009bb1  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140009bb8  add     rcx, rdx
0x140009bbb  mov     [rbx+8], rcx
0x140009bbf  sub     [rdi+8], rdx
0x140009bc3  mov     rcx, [rax+8]
0x140009bc7  mov     [rcx], r9
0x140009bca  mov     rcx, [r9+8]
0x140009bce  mov     [rcx], r10
0x140009bd1  mov     rcx, [r10+8]
0x140009bd5  mov     [rcx], rax
0x140009bd8  mov     rcx, [r9+8]
0x140009bdc  mov     rdx, [r10+8]
0x140009be0  mov     [r10+8], rcx
0x140009be4  mov     rcx, [rax+8]
0x140009be8  mov     [r9+8], rcx
0x140009bec  mov     [rax+8], rdx
0x140009bf0  mov     rbx, [rsp+28h+arg_0]
0x140009bf5  mov     rsi, [rsp+28h+arg_8]
0x140009bfa  add     rsp, 20h
0x140009bfe  pop     rdi
0x140009bff  retn
```
