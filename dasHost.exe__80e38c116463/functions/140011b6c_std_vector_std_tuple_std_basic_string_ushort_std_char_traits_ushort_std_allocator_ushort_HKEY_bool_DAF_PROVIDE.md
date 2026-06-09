# std::vector<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>,std::allocator<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x140011b6c`
- end: `0x140011bf3`
- name: `??1_Reallocation_guard@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@@2@@std@@QEAA@XZ`
- size: `135`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140011224`

## callees

- `0x1400018d4`
- `0x1400106b4`
- `0x140011b6c`

## pseudocode

```c
void __fastcall std::vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 v2; // rsi
  __int64 i; // rdi
  __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  void *v6; // rax

  if ( a1[1] )
  {
    v2 = a1[4];
    for ( i = a1[3]; i != v2; i += 48 )
      std::wstring::~wstring((char **)(i + 16));
    v4 = a1[1];
    v5 = 48LL * a1[2];
    if ( v5 < 0x1000 )
    {
      v6 = (void *)a1[1];
    }
    else
    {
      v6 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
  }
}

```

## disassembly

```asm
0x140011b6c  mov     [rsp+arg_0], rbx
0x140011b71  mov     [rsp+arg_8], rsi
0x140011b76  push    rdi
0x140011b77  sub     rsp, 20h
0x140011b7b  cmp     qword ptr [rcx+8], 0
0x140011b80  mov     rbx, rcx
0x140011b83  jz      short loc_140011BE3
0x140011b85  mov     rsi, [rcx+20h]
0x140011b89  mov     rdi, [rcx+18h]
0x140011b8d  jmp     short loc_140011B9C
0x140011b8f  lea     rcx, [rdi+10h]
0x140011b93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011b98  add     rdi, 30h ; '0'
0x140011b9c  cmp     rdi, rsi
0x140011b9f  jnz     short loc_140011B8F
0x140011ba1  mov     rax, [rbx+10h]
0x140011ba5  mov     rcx, [rbx+8]
0x140011ba9  lea     rdx, [rax+rax*2]
0x140011bad  shl     rdx, 4; unsigned __int64
0x140011bb1  cmp     rdx, 1000h
0x140011bb8  jb      short loc_140011BD8
0x140011bba  mov     rax, [rcx-8]
0x140011bbe  sub     rcx, rax
0x140011bc1  sub     rcx, 8
0x140011bc5  cmp     rcx, 1Fh
0x140011bc9  ja      short loc_140011BD1
0x140011bcb  add     rdx, 27h ; '''
0x140011bcf  jmp     short loc_140011BDB
0x140011bd1  mov     ecx, 5
0x140011bd6  int     29h; Win8: RtlFailFast(ecx)
0x140011bd8  mov     rax, rcx
0x140011bdb  mov     rcx, rax; void *
0x140011bde  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011be3  mov     rbx, [rsp+28h+arg_0]
0x140011be8  mov     rsi, [rsp+28h+arg_8]
0x140011bed  add     rsp, 20h
0x140011bf1  pop     rdi
0x140011bf2  retn
```
