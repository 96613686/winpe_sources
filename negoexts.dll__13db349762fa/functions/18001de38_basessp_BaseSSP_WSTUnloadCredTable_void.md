# basessp::BaseSSP::WSTUnloadCredTable(void)

- ea: `0x18001de38`
- end: `0x18001deae`
- name: `?WSTUnloadCredTable@BaseSSP@basessp@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(basessp::BaseSSP *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000db48`

## callees

- `0x180004230`
- `0x18001de38`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001de85`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001de85`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001de61`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001de61`
- `ntdll!RtlDeleteResource` at `0x18001dea7`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001de4d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001de4d`
- `ntdll!RtlReleaseResource` at `0x18001de96`
- `ntdll!RtlReleaseResource` at `0x18001de96`

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
0x18001de38  push    rbx
0x18001de3a  push    rbp
0x18001de3b  push    rsi
0x18001de3c  push    rdi
0x18001de3d  sub     rsp, 28h
0x18001de41  lea     rdi, [rcx+70h]
0x18001de45  mov     rbp, rcx
0x18001de48  mov     rcx, rdi; Resource
0x18001de4b  mov     dl, 1; Wait
0x18001de4d  call    cs:__imp_RtlAcquireResourceExclusive
0x18001de53  mov     dl, 1
0x18001de55  lea     rsi, [rbp+8]
0x18001de59  jmp     short loc_18001DE82
0x18001de5b  mov     rdx, rbx; Buffer
0x18001de5e  mov     rcx, rsi; Table
0x18001de61  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18001de67  test    al, al
0x18001de69  jz      short loc_18001DE93
0x18001de6b  mov     rcx, [rbx]
0x18001de6e  mov     dword ptr [rcx+0Ch], 0
0x18001de75  mov     rcx, rbp; this
0x18001de78  mov     rdx, [rbx]; struct basessp::_WST_CREDENTIAL *
0x18001de7b  call    ?WSTDereferenceCredential@BaseSSP@basessp@@QEAAXPEAU_WST_CREDENTIAL@2@@Z; basessp::BaseSSP::WSTDereferenceCredential(basessp::_WST_CREDENTIAL *)
0x18001de80  xor     edx, edx; Restart
0x18001de82  mov     rcx, rsi; Table
0x18001de85  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18001de8b  mov     rbx, rax
0x18001de8e  test    rax, rax
0x18001de91  jnz     short loc_18001DE5B
0x18001de93  mov     rcx, rdi; Resource
0x18001de96  call    cs:__imp_RtlReleaseResource
0x18001de9c  mov     rcx, rdi
0x18001de9f  add     rsp, 28h
0x18001dea3  pop     rdi
0x18001dea4  pop     rsi
0x18001dea5  pop     rbp
0x18001dea6  pop     rbx
0x18001dea7  jmp     cs:__imp_RtlDeleteResource
```
