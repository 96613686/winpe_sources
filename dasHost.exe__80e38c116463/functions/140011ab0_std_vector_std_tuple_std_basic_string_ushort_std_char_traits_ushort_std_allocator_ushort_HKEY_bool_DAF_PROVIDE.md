# std::vector<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>,std::allocator<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>>>::~vector<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>,std::allocator<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>>>(void)

- ea: `0x140011ab0`
- end: `0x140011b63`
- name: `??1?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@@2@@std@@QEAA@XZ`
- size: `179`
- prototype: `void __fastcall(char ***)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140012c08`
- `0x14001aea4`

## callees

- `0x1400018d4`
- `0x1400106b4`
- `0x140011ab0`

## pseudocode

```c
void __fastcall std::vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>::~vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>(
        char ***a1)
{
  char **v1; // rbx
  char **v3; // rsi
  char **v4; // rcx
  unsigned __int64 v5; // rdx
  char **v6; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[1];
    while ( v1 != v3 )
    {
      std::wstring::~wstring(v1 + 2);
      v1 += 6;
    }
    v4 = *a1;
    v5 = 16 * (((char *)a1[2] - (char *)*a1) >> 4);
    if ( v5 < 0x1000 )
    {
      v6 = *a1;
    }
    else
    {
      v6 = (char **)*(v4 - 1);
      if ( (unsigned __int64)((char *)v4 - (char *)v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x140011ab0  mov     [rsp+arg_0], rbx
0x140011ab5  mov     [rsp+arg_8], rsi
0x140011aba  push    rdi
0x140011abb  sub     rsp, 20h
0x140011abf  mov     rbx, [rcx]
0x140011ac2  mov     rdi, rcx
0x140011ac5  test    rbx, rbx
0x140011ac8  jz      loc_140011B53
0x140011ace  mov     rsi, [rcx+8]
0x140011ad2  jmp     short loc_140011AE1
0x140011ad4  lea     rcx, [rbx+10h]
0x140011ad8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011add  add     rbx, 30h ; '0'
0x140011ae1  cmp     rbx, rsi
0x140011ae4  jnz     short loc_140011AD4
0x140011ae6  mov     rcx, [rdi]
0x140011ae9  mov     rdx, 0AAAAAAAAAAAAAAABh
0x140011af3  mov     rax, [rdi+10h]
0x140011af7  sub     rax, rcx
0x140011afa  sar     rax, 4
0x140011afe  imul    rax, rdx
0x140011b02  lea     rdx, [rax+rax*2]
0x140011b06  shl     rdx, 4; unsigned __int64
0x140011b0a  cmp     rdx, 1000h
0x140011b11  jb      short loc_140011B31
0x140011b13  mov     rax, [rcx-8]
0x140011b17  sub     rcx, rax
0x140011b1a  sub     rcx, 8
0x140011b1e  cmp     rcx, 1Fh
0x140011b22  ja      short loc_140011B2A
0x140011b24  add     rdx, 27h ; '''
0x140011b28  jmp     short loc_140011B34
0x140011b2a  mov     ecx, 5
0x140011b2f  int     29h; Win8: RtlFailFast(ecx)
0x140011b31  mov     rax, rcx
0x140011b34  mov     rcx, rax; void *
0x140011b37  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011b3c  mov     qword ptr [rdi], 0
0x140011b43  mov     qword ptr [rdi+8], 0
0x140011b4b  mov     qword ptr [rdi+10h], 0
0x140011b53  mov     rbx, [rsp+28h+arg_0]
0x140011b58  mov     rsi, [rsp+28h+arg_8]
0x140011b5d  add     rsp, 20h
0x140011b61  pop     rdi
0x140011b62  retn
```
