# IASTL::IASComponentObject<InfoBase>::attemptTransition(IASTL::IASComponent::Event)

- ea: `0x180012ba0`
- end: `0x180012bcb`
- name: `?attemptTransition@?$IASComponentObject@VInfoBase@@@IASTL@@MEAAJW4Event@IASComponent@2@@Z`
- size: `43`
- prototype: `__int64 __fastcall(InfoBase *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180012ba0`
- `0x1800157b8`
- `0x180015968`

## pseudocode

```c
__int64 __fastcall IASTL::IASComponentObject<InfoBase>::attemptTransition(InfoBase *a1, int a2)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx

  if ( !a2 )
    return 0;
  v2 = a2 - 1;
  if ( !v2 )
    return InfoBase::Initialize(a1);
  v3 = v2 - 1;
  if ( !v3 )
    return 0;
  v4 = v3 - 1;
  if ( !v4 )
    return 0;
  if ( v4 == 1 )
    return InfoBase::Shutdown(a1);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180012ba0  test    edx, edx
0x180012ba2  jz      short loc_180012BC8
0x180012ba4  sub     edx, 1
0x180012ba7  jz      short loc_180012BC3
0x180012ba9  sub     edx, 1
0x180012bac  jz      short loc_180012BC8
0x180012bae  sub     edx, 1
0x180012bb1  jz      short loc_180012BC8
0x180012bb3  cmp     edx, 1
0x180012bb6  jz      short loc_180012BBE
0x180012bb8  mov     eax, 80004005h
0x180012bbd  retn
0x180012bbe  jmp     ?Shutdown@InfoBase@@UEAAJXZ; InfoBase::Shutdown(void)
0x180012bc3  jmp     ?Initialize@InfoBase@@UEAAJXZ; InfoBase::Initialize(void)
0x180012bc8  xor     eax, eax
0x180012bca  retn
```
