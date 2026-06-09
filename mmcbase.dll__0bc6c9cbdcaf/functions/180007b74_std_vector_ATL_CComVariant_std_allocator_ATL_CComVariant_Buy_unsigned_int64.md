# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::_Buy(unsigned __int64)

- ea: `0x180007b74`
- end: `0x180007bf8`
- name: `?_Buy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAA_N_K@Z`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013c0c`

## callees

- `0x180007b74`
- `0x180009928`
- `0x180009950`

## import_xrefs

- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180007bcc`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180007bcc`

## pseudocode

```c
char __fastcall std::vector<ATL::CComVariant>::_Buy(_QWORD *a1, unsigned __int64 a2)
{
  __int64 v4; // rdi
  char *v5; // rax

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  if ( !a2 )
    return 0;
  if ( a2 > 0xAAAAAAAAAAAAAAALL )
    std::_Xlength_error("vector<T> too long");
  v4 = 24 * a2;
  v5 = (char *)operator new(24 * a2);
  if ( !v5 )
    std::_Xbad_alloc();
  *a1 = v5;
  a1[1] = v5;
  a1[2] = &v5[v4];
  return 1;
}

```

## disassembly

```asm
0x180007b74  mov     [rsp+arg_0], rbx
0x180007b79  push    rdi
0x180007b7a  sub     rsp, 20h
0x180007b7e  mov     qword ptr [rcx], 0
0x180007b85  mov     rbx, rcx
0x180007b88  mov     qword ptr [rcx+8], 0
0x180007b90  mov     qword ptr [rcx+10h], 0
0x180007b98  test    rdx, rdx
0x180007b9b  jnz     short loc_180007BA1
0x180007b9d  xor     al, al
0x180007b9f  jmp     short loc_180007BED
0x180007ba1  mov     rax, 0AAAAAAAAAAAAAAAh
0x180007bab  cmp     rdx, rax
0x180007bae  jbe     short loc_180007BBD
0x180007bb0  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x180007bb7  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180007bbd  lea     rax, [rdx+rdx*2]
0x180007bc1  lea     rdi, ds:0[rax*8]
0x180007bc9  mov     rcx, rdi
0x180007bcc  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007bd2  test    rax, rax
0x180007bd5  jnz     short loc_180007BDD
0x180007bd7  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007bdd  mov     [rbx], rax
0x180007be0  mov     [rbx+8], rax
0x180007be4  add     rax, rdi
0x180007be7  mov     [rbx+10h], rax
0x180007beb  mov     al, 1
0x180007bed  mov     rbx, [rsp+28h+arg_0]
0x180007bf2  add     rsp, 20h
0x180007bf6  pop     rdi
0x180007bf7  retn
```
