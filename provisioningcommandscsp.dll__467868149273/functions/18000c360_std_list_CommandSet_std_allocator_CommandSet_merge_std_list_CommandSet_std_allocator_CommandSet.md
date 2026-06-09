# std::list<CommandSet,std::allocator<CommandSet>>::merge(std::list<CommandSet,std::allocator<CommandSet>> &)

- ea: `0x18000c360`
- end: `0x18000c473`
- name: `?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c744`

## callees

- `0x18000c360`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c41d`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c41d`

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
0x18000c360  cmp     rdx, rcx
0x18000c363  jz      locret_18000C471
0x18000c369  mov     [rsp+arg_0], rbx
0x18000c36e  mov     [rsp+arg_8], rsi
0x18000c373  push    rdi
0x18000c374  sub     rsp, 20h
0x18000c378  mov     r10, [rcx]
0x18000c37b  mov     rdi, rdx
0x18000c37e  mov     r9, [rdx]
0x18000c381  mov     rbx, rcx
0x18000c384  mov     rsi, 38E38E38E38E38Dh
0x18000c38e  mov     r8, [r10]
0x18000c391  mov     rax, [r9]
0x18000c394  cmp     r8, r10
0x18000c397  jz      short loc_18000C401
0x18000c399  cmp     rax, r9
0x18000c39c  jz      loc_18000C462
0x18000c3a2  mov     ecx, [r8+10h]
0x18000c3a6  cmp     [rax+10h], ecx
0x18000c3a9  jnb     short loc_18000C3FC
0x18000c3ab  mov     rdx, [rbx+8]
0x18000c3af  mov     rcx, rsi
0x18000c3b2  sub     rcx, rdx
0x18000c3b5  cmp     rcx, 1
0x18000c3b9  jb      short loc_18000C416
0x18000c3bb  mov     r11, [rax]
0x18000c3be  lea     rcx, [rdx+1]
0x18000c3c2  mov     [rbx+8], rcx
0x18000c3c6  dec     qword ptr [rdi+8]
0x18000c3ca  mov     rcx, [rax+8]
0x18000c3ce  mov     [rcx], r11
0x18000c3d1  mov     rcx, [r11+8]
0x18000c3d5  mov     [rcx], r8
0x18000c3d8  mov     rcx, [r8+8]
0x18000c3dc  mov     [rcx], rax
0x18000c3df  mov     rcx, [r11+8]
0x18000c3e3  mov     rdx, [r8+8]
0x18000c3e7  mov     [r8+8], rcx
0x18000c3eb  mov     rcx, [rax+8]
0x18000c3ef  mov     [r11+8], rcx
0x18000c3f3  mov     [rax+8], rdx
0x18000c3f7  mov     rax, r11
0x18000c3fa  jmp     short loc_18000C394
0x18000c3fc  mov     r8, [r8]
0x18000c3ff  jmp     short loc_18000C394
0x18000c401  cmp     rax, r9
0x18000c404  jz      short loc_18000C462
0x18000c406  mov     rcx, [rbx+8]
0x18000c40a  mov     rdx, [rdi+8]
0x18000c40e  sub     rsi, rcx
0x18000c411  cmp     rsi, rdx
0x18000c414  jnb     short loc_18000C42A
0x18000c416  lea     rcx, aListTTooLong; "list<T> too long"
0x18000c41d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000c42a  add     rcx, rdx
0x18000c42d  mov     [rbx+8], rcx
0x18000c431  sub     [rdi+8], rdx
0x18000c435  mov     rcx, [rax+8]
0x18000c439  mov     [rcx], r9
0x18000c43c  mov     rcx, [r9+8]
0x18000c440  mov     [rcx], r10
0x18000c443  mov     rcx, [r10+8]
0x18000c447  mov     [rcx], rax
0x18000c44a  mov     rcx, [r9+8]
0x18000c44e  mov     rdx, [r10+8]
0x18000c452  mov     [r10+8], rcx
0x18000c456  mov     rcx, [rax+8]
0x18000c45a  mov     [r9+8], rcx
0x18000c45e  mov     [rax+8], rdx
0x18000c462  mov     rbx, [rsp+28h+arg_0]
0x18000c467  mov     rsi, [rsp+28h+arg_8]
0x18000c46c  add     rsp, 20h
0x18000c470  pop     rdi
0x18000c471  retn
```
