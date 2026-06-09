# std::list<CommandSet,std::allocator<CommandSet>>::merge(std::list<CommandSet,std::allocator<CommandSet>> &)

- ea: `0x18000bd6c`
- end: `0x18000be78`
- name: `?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z`
- size: `268`
- prototype: `void __fastcall(__int64 ***, __int64 ***)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c144`

## callees

- `0x18000bd6c`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000be29`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000be29`

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
0x18000bd6c  cmp     rdx, rcx
0x18000bd6f  jz      locret_18000BE77
0x18000bd75  mov     [rsp+arg_0], rbx
0x18000bd7a  mov     [rsp+arg_8], rsi
0x18000bd7f  push    rdi
0x18000bd80  sub     rsp, 20h
0x18000bd84  mov     r10, [rcx]
0x18000bd87  mov     rdi, rdx
0x18000bd8a  mov     r9, [rdx]
0x18000bd8d  mov     rbx, rcx
0x18000bd90  mov     rsi, 38E38E38E38E38Dh
0x18000bd9a  mov     r8, [r10]
0x18000bd9d  mov     rax, [r9]
0x18000bda0  cmp     r8, r10
0x18000bda3  jz      short loc_18000BE0D
0x18000bda5  cmp     rax, r9
0x18000bda8  jz      loc_18000BE68
0x18000bdae  mov     ecx, [r8+10h]
0x18000bdb2  cmp     [rax+10h], ecx
0x18000bdb5  jnb     short loc_18000BE08
0x18000bdb7  mov     rdx, [rbx+8]
0x18000bdbb  mov     rcx, rsi
0x18000bdbe  sub     rcx, rdx
0x18000bdc1  cmp     rcx, 1
0x18000bdc5  jb      short loc_18000BE22
0x18000bdc7  mov     r11, [rax]
0x18000bdca  lea     rcx, [rdx+1]
0x18000bdce  mov     [rbx+8], rcx
0x18000bdd2  dec     qword ptr [rdi+8]
0x18000bdd6  mov     rcx, [rax+8]
0x18000bdda  mov     [rcx], r11
0x18000bddd  mov     rcx, [r11+8]
0x18000bde1  mov     [rcx], r8
0x18000bde4  mov     rcx, [r8+8]
0x18000bde8  mov     [rcx], rax
0x18000bdeb  mov     rcx, [r11+8]
0x18000bdef  mov     rdx, [r8+8]
0x18000bdf3  mov     [r8+8], rcx
0x18000bdf7  mov     rcx, [rax+8]
0x18000bdfb  mov     [r11+8], rcx
0x18000bdff  mov     [rax+8], rdx
0x18000be03  mov     rax, r11
0x18000be06  jmp     short loc_18000BDA0
0x18000be08  mov     r8, [r8]
0x18000be0b  jmp     short loc_18000BDA0
0x18000be0d  cmp     rax, r9
0x18000be10  jz      short loc_18000BE68
0x18000be12  mov     rcx, [rbx+8]
0x18000be16  mov     rdx, [rdi+8]
0x18000be1a  sub     rsi, rcx
0x18000be1d  cmp     rsi, rdx
0x18000be20  jnb     short loc_18000BE30
0x18000be22  lea     rcx, aListTTooLong; "list<T> too long"
0x18000be29  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000be30  add     rcx, rdx
0x18000be33  mov     [rbx+8], rcx
0x18000be37  sub     [rdi+8], rdx
0x18000be3b  mov     rcx, [rax+8]
0x18000be3f  mov     [rcx], r9
0x18000be42  mov     rcx, [r9+8]
0x18000be46  mov     [rcx], r10
0x18000be49  mov     rcx, [r10+8]
0x18000be4d  mov     [rcx], rax
0x18000be50  mov     rcx, [r9+8]
0x18000be54  mov     rdx, [r10+8]
0x18000be58  mov     [r10+8], rcx
0x18000be5c  mov     rcx, [rax+8]
0x18000be60  mov     [r9+8], rcx
0x18000be64  mov     [rax+8], rdx
0x18000be68  mov     rbx, [rsp+28h+arg_0]
0x18000be6d  mov     rsi, [rsp+28h+arg_8]
0x18000be72  add     rsp, 20h
0x18000be76  pop     rdi
0x18000be77  retn
```
