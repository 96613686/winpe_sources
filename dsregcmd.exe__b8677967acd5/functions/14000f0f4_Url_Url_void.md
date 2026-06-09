# Url::Url(void)

- ea: `0x14000f0f4`
- end: `0x14000f169`
- name: `??0Url@@QEAA@XZ`
- size: `117`
- prototype: `Url *__fastcall(Url *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009b24`
- `0x14000a610`
- `0x14000d134`
- `0x14000f208`
- `0x14001088c`
- `0x14001eb64`

## callees

- `0x140001814`
- `0x140002814`
- `0x14000f0f4`
- `0x140030010`

## string_xrefs

- `0x14000f12a`: `onecore\ds\security\dsreg\win32\adal.native\url.cpp`

## pseudocode

```c
Url *__fastcall Url::Url(Url *this)
{
  void *v2; // rax
  void *v3; // rbx

  *(_QWORD *)this = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v2 = operator new(0x68u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\url.cpp", 22);
  v3 = v2;
  if ( v2 )
    memset_0(v2, 0, 0x68u);
  else
    v3 = 0;
  *((_QWORD *)this + 1) = v3;
  return this;
}

```

## disassembly

```asm
0x14000f0f4  mov     [rsp+arg_8], rbx
0x14000f0f9  mov     [rsp+arg_0], rcx
0x14000f0fe  push    rdi
0x14000f0ff  sub     rsp, 20h
0x14000f103  mov     rdi, rcx
0x14000f106  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000f10d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000f114  mov     rax, [rax+18h]
0x14000f118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f11d  add     rax, 18h
0x14000f121  mov     [rdi], rax
0x14000f124  mov     r9d, 16h; int
0x14000f12a  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14000f131  lea     edx, [r9-15h]; int
0x14000f135  lea     ecx, [rdx+67h]; unsigned __int64
0x14000f138  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14000f13d  mov     rbx, rax
0x14000f140  test    rax, rax
0x14000f143  jz      short loc_14000F155
0x14000f145  xor     edx, edx; Val
0x14000f147  lea     r8d, [rdx+68h]; Size
0x14000f14b  mov     rcx, rax; void *
0x14000f14e  call    memset_0
0x14000f153  jmp     short loc_14000F157
0x14000f155  xor     ebx, ebx
0x14000f157  mov     [rdi+8], rbx
0x14000f15b  mov     rax, rdi
0x14000f15e  mov     rbx, [rsp+28h+arg_8]
0x14000f163  add     rsp, 20h
0x14000f167  pop     rdi
0x14000f168  retn
```
