# NTCache::evict(void)

- ea: `0x18001dd28`
- end: `0x18001ddd4`
- name: `?evict@NTCache@@IEAAXXZ`
- size: `172`
- prototype: `void __fastcall(NTCache *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001dddc`

## callees

- `0x1800181ec`
- `0x180018218`
- `0x18001dd28`
- `0x18001f5d0`

## import_xrefs

- `msvcrt!free` at `0x18001ddba`
- `msvcrt!free` at `0x18001ddba`

## pseudocode

```c
void __fastcall NTCache::evict(NTCache *this)
{
  unsigned __int64 SystemTimeAsDWORDLONG; // rsi
  _QWORD *v2; // rbx
  _QWORD *v3; // rdi
  __int64 v4; // rcx
  _QWORD *v5; // r8
  _QWORD *v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h]
  __int64 v8; // [rsp+30h] [rbp-18h]

  SystemTimeAsDWORDLONG = GetSystemTimeAsDWORDLONG(this);
  v7 = qword_1800402E0;
  v6 = *(_QWORD **)qword_1800402E0;
  v8 = qword_1800402E0 + 8 * qword_1800402C8;
LABEL_2:
  hash_table<unsigned long,identity<unsigned long>,std::pair<EAPSession *,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64,EAPSession *>>>>>,EAPSessionTable::Extractor,std::equal_to<unsigned long>>::const_iterator::find_node(&v6);
LABEL_3:
  v2 = v6;
  while ( 1 )
  {
    v3 = (_QWORD *)v7;
    if ( v7 == v8 )
      break;
    v4 = v2[1];
    if ( !*(_DWORD *)(v4 + 128) || SystemTimeAsDWORDLONG < *(_QWORD *)(v4 + 136) )
    {
      v6 = (_QWORD *)*v2;
      goto LABEL_2;
    }
    NTDomain::Release((NTDomain *)v4);
    while ( *v3 )
    {
      if ( (_QWORD *)*v3 == v2 )
      {
        v6 = (_QWORD *)*v2;
        hash_table<unsigned long,identity<unsigned long>,std::pair<EAPSession *,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64,EAPSession *>>>>>,EAPSessionTable::Extractor,std::equal_to<unsigned long>>::const_iterator::find_node(&v6);
        *v3 = *v5;
        free(v5);
        goto LABEL_3;
      }
      v3 = (_QWORD *)*v3;
    }
  }
}

```

## disassembly

```asm
0x18001dd28  push    rbp
0x18001dd2a  push    rbx
0x18001dd2b  push    rsi
0x18001dd2c  push    rdi
0x18001dd2d  mov     rbp, rsp
0x18001dd30  sub     rsp, 48h
0x18001dd34  call    GetSystemTimeAsDWORDLONG
0x18001dd39  mov     rdx, cs:qword_1800402E0
0x18001dd40  mov     rsi, rax
0x18001dd43  mov     [rbp+var_20], rdx
0x18001dd47  mov     rcx, [rdx]
0x18001dd4a  mov     [rbp+var_28], rcx
0x18001dd4e  mov     rcx, cs:qword_1800402C8
0x18001dd55  lea     rdx, [rdx+rcx*8]
0x18001dd59  mov     [rbp+var_18], rdx
0x18001dd5d  lea     rcx, [rbp+var_28]
0x18001dd61  call    ?find_node@const_iterator@?$hash_table@KU?$identity@K@@U?$pair@PEAVEAPSession@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@_KPEAVEAPSession@@@std@@@std@@@std@@@std@@@std@@UExtractor@EAPSessionTable@@U?$equal_to@K@3@@@IEAAXXZ; hash_table<ulong,identity<ulong>,std::pair<EAPSession *,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64,EAPSession *>>>>>,EAPSessionTable::Extractor,std::equal_to<ulong>>::const_iterator::find_node(void)
0x18001dd66  mov     rbx, [rbp+var_28]
0x18001dd6a  mov     rdi, [rbp+var_20]
0x18001dd6e  cmp     rdi, [rbp+var_18]
0x18001dd72  jz      short loc_18001DDCB
0x18001dd74  mov     rcx, [rbx+8]; this
0x18001dd78  cmp     dword ptr [rcx+80h], 0
0x18001dd7f  jz      short loc_18001DDC2
0x18001dd81  cmp     rsi, [rcx+88h]
0x18001dd88  jb      short loc_18001DDC2
0x18001dd8a  call    ?Release@NTDomain@@QEAAXXZ; NTDomain::Release(void)
0x18001dd8f  mov     r8, [rdi]
0x18001dd92  test    r8, r8
0x18001dd95  jz      short loc_18001DD6A
0x18001dd97  cmp     r8, rbx
0x18001dd9a  jz      short loc_18001DDA1
0x18001dd9c  mov     rdi, r8
0x18001dd9f  jmp     short loc_18001DD8F
0x18001dda1  mov     rax, [rbx]
0x18001dda4  lea     rcx, [rbp+var_28]
0x18001dda8  mov     [rbp+var_28], rax
0x18001ddac  call    ?find_node@const_iterator@?$hash_table@KU?$identity@K@@U?$pair@PEAVEAPSession@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@_KPEAVEAPSession@@@std@@@std@@@std@@@std@@@std@@UExtractor@EAPSessionTable@@U?$equal_to@K@3@@@IEAAXXZ; hash_table<ulong,identity<ulong>,std::pair<EAPSession *,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64,EAPSession *>>>>>,EAPSessionTable::Extractor,std::equal_to<ulong>>::const_iterator::find_node(void)
0x18001ddb1  mov     rdx, [r8]
0x18001ddb4  mov     rcx, r8; Block
0x18001ddb7  mov     [rdi], rdx
0x18001ddba  call    cs:__imp_free
0x18001ddc0  jmp     short loc_18001DD66
0x18001ddc2  mov     rax, [rbx]
0x18001ddc5  mov     [rbp+var_28], rax
0x18001ddc9  jmp     short loc_18001DD5D
0x18001ddcb  add     rsp, 48h
0x18001ddcf  pop     rdi
0x18001ddd0  pop     rsi
0x18001ddd1  pop     rbx
0x18001ddd2  pop     rbp
0x18001ddd3  retn
```
