# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x1800122c4`
- end: `0x180012390`
- name: `??1_Clear_guard@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `204`
- prototype: `void __fastcall(unsigned __int64 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013220`

## callees

- `0x180002c8c`
- `0x18000dcb0`
- `0x1800122c4`
- `0x18001382c`

## pseudocode

```c
void __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rbx
  unsigned __int64 v2; // rcx
  char **v3; // rsi
  char *v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = v1[1];
    if ( v1[7] >> 3 <= v1[2] )
    {
      **(_QWORD **)(v2 + 8) = 0;
      v3 = *(char ***)v2;
      if ( *(_QWORD *)v2 )
      {
        do
        {
          v4 = *v3;
          std::wstring::~wstring(v3 + 2);
          operator delete(v3, 0x30u);
          v3 = (char **)v4;
        }
        while ( v4 );
      }
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8) = v1[1];
      v1[2] = 0;
      v5 = (void *)v1[3];
      v6 = (v1[4] - (unsigned __int64)v5 + 7) >> 3;
      if ( (unsigned __int64)v5 > v1[4] )
        v6 = 0;
      if ( v6 )
        memset64(v5, v1[1], v6);
    }
    else
    {
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Unchecked_erase(
        v1,
        *(_QWORD *)v2,
        v1[1]);
    }
  }
}

```

## disassembly

```asm
0x1800122c4  mov     [rsp+arg_0], rbx
0x1800122c9  mov     [rsp+arg_8], rsi
0x1800122ce  push    rdi
0x1800122cf  sub     rsp, 20h
0x1800122d3  mov     rbx, [rcx]
0x1800122d6  test    rbx, rbx
0x1800122d9  jz      loc_180012380
0x1800122df  cmp     qword ptr [rbx+10h], 0
0x1800122e4  jz      loc_180012380
0x1800122ea  mov     rax, [rbx+38h]
0x1800122ee  mov     rcx, [rbx+8]
0x1800122f2  shr     rax, 3
0x1800122f6  cmp     rax, [rbx+10h]
0x1800122fa  jbe     short loc_18001230C
0x1800122fc  mov     rdx, [rcx]
0x1800122ff  mov     r8, rcx
0x180012302  mov     rcx, rbx
0x180012305  call    ?_Unchecked_erase@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Unchecked_erase(std::_List_node<std::wstring,void *> *,std::_List_node<std::wstring,void *> * const)
0x18001230a  jmp     short loc_180012380
0x18001230c  mov     rax, [rcx+8]
0x180012310  mov     qword ptr [rax], 0
0x180012317  mov     rsi, [rcx]
0x18001231a  test    rsi, rsi
0x18001231d  jz      short loc_180012340
0x18001231f  mov     rdi, [rsi]
0x180012322  lea     rcx, [rsi+10h]; void *
0x180012326  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001232b  mov     edx, 30h ; '0'; unsigned __int64
0x180012330  mov     rcx, rsi; void *
0x180012333  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012338  mov     rsi, rdi
0x18001233b  test    rdi, rdi
0x18001233e  jnz     short loc_18001231F
0x180012340  mov     rax, [rbx+8]
0x180012344  xor     edx, edx
0x180012346  mov     [rax], rax
0x180012349  mov     rax, [rbx+8]
0x18001234d  mov     [rax+8], rax
0x180012351  mov     qword ptr [rbx+10h], 0
0x180012359  mov     rdi, [rbx+18h]
0x18001235d  mov     rcx, [rbx+20h]
0x180012361  sub     rcx, rdi
0x180012364  add     rcx, 7
0x180012368  shr     rcx, 3
0x18001236c  cmp     rdi, [rbx+20h]
0x180012370  cmova   rcx, rdx
0x180012374  test    rcx, rcx
0x180012377  jz      short loc_180012380
0x180012379  mov     rax, [rbx+8]
0x18001237d  rep stosq
0x180012380  mov     rbx, [rsp+28h+arg_0]
0x180012385  mov     rsi, [rsp+28h+arg_8]
0x18001238a  add     rsp, 20h
0x18001238e  pop     rdi
0x18001238f  retn
```
