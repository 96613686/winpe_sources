# basessp::BaseSSP::WSTUnloadCredTable(void)

- ea: `0x1800441e4`
- end: `0x18004425a`
- name: `?WSTUnloadCredTable@BaseSSP@basessp@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(basessp::BaseSSP *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180043460`
- `0x180044170`

## callees

- `0x180044080`
- `0x1800441e4`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180044253`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800441f9`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800441f9`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180044231`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180044231`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18004420d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18004420d`
- `ntdll!RtlReleaseResource` at `0x180044242`
- `ntdll!RtlReleaseResource` at `0x180044242`

## pseudocode

```c
void __fastcall basessp::BaseSSP::WSTUnloadCredTable(basessp::BaseSSP *this)
{
  struct _RTL_RESOURCE *v1; // rdi
  BOOLEAN i; // dl
  struct basessp::_WST_CREDENTIAL **v4; // rax
  struct basessp::_WST_CREDENTIAL **v5; // rbx

  v1 = (struct _RTL_RESOURCE *)((char *)this + 112);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
  for ( i = 1; ; i = 0 )
  {
    v4 = (struct basessp::_WST_CREDENTIAL **)RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 8), i);
    v5 = v4;
    if ( !v4 || !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 8), v4) )
      break;
    *((_DWORD *)*v5 + 3) = 0;
    basessp::BaseSSP::WSTDereferenceCredential(this, *v5);
  }
  RtlReleaseResource(v1);
  RtlDeleteResource(v1);
}

```

## disassembly

```asm
0x1800441e4  push    rbx
0x1800441e6  push    rbp
0x1800441e7  push    rsi
0x1800441e8  push    rdi
0x1800441e9  sub     rsp, 28h
0x1800441ed  lea     rdi, [rcx+70h]
0x1800441f1  mov     rbp, rcx
0x1800441f4  mov     rcx, rdi; Resource
0x1800441f7  mov     dl, 1; Wait
0x1800441f9  call    cs:__imp_RtlAcquireResourceExclusive
0x1800441ff  mov     dl, 1
0x180044201  lea     rsi, [rbp+8]
0x180044205  jmp     short loc_18004422E
0x180044207  mov     rdx, rbx; Buffer
0x18004420a  mov     rcx, rsi; Table
0x18004420d  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180044213  test    al, al
0x180044215  jz      short loc_18004423F
0x180044217  mov     rcx, [rbx]
0x18004421a  mov     dword ptr [rcx+0Ch], 0
0x180044221  mov     rcx, rbp; this
0x180044224  mov     rdx, [rbx]; struct basessp::_WST_CREDENTIAL *
0x180044227  call    ?WSTDereferenceCredential@BaseSSP@basessp@@QEAAXPEAU_WST_CREDENTIAL@2@@Z; basessp::BaseSSP::WSTDereferenceCredential(basessp::_WST_CREDENTIAL *)
0x18004422c  xor     edx, edx; Restart
0x18004422e  mov     rcx, rsi; Table
0x180044231  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180044237  mov     rbx, rax
0x18004423a  test    rax, rax
0x18004423d  jnz     short loc_180044207
0x18004423f  mov     rcx, rdi; Resource
0x180044242  call    cs:__imp_RtlReleaseResource
0x180044248  mov     rcx, rdi
0x18004424b  add     rsp, 28h
0x18004424f  pop     rdi
0x180044250  pop     rsi
0x180044251  pop     rbp
0x180044252  pop     rbx
0x180044253  jmp     cs:__imp_RtlDeleteResource
```
