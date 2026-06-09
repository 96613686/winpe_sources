# IASTL::IASComponentObject<NTEventLog>::attemptTransition(IASTL::IASComponent::Event)

- ea: `0x180012be0`
- end: `0x180012c0b`
- name: `?attemptTransition@?$IASComponentObject@VNTEventLog@@@IASTL@@MEAAJW4Event@IASComponent@2@@Z`
- size: `43`
- prototype: `__int64 __fastcall(NTEventLog *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180012be0`
- `0x180015100`
- `0x180015250`

## pseudocode

```c
__int64 __fastcall IASTL::IASComponentObject<NTEventLog>::attemptTransition(NTEventLog *a1, int a2)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx

  if ( !a2 )
    return 0;
  v2 = a2 - 1;
  if ( !v2 )
    return NTEventLog::Initialize(a1);
  v3 = v2 - 1;
  if ( !v3 )
    return 0;
  v4 = v3 - 1;
  if ( !v4 )
    return 0;
  if ( v4 == 1 )
    return NTEventLog::Shutdown(a1);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180012be0  test    edx, edx
0x180012be2  jz      short loc_180012C08
0x180012be4  sub     edx, 1
0x180012be7  jz      short loc_180012C03
0x180012be9  sub     edx, 1
0x180012bec  jz      short loc_180012C08
0x180012bee  sub     edx, 1
0x180012bf1  jz      short loc_180012C08
0x180012bf3  cmp     edx, 1
0x180012bf6  jz      short loc_180012BFE
0x180012bf8  mov     eax, 80004005h
0x180012bfd  retn
0x180012bfe  jmp     ?Shutdown@NTEventLog@@UEAAJXZ; NTEventLog::Shutdown(void)
0x180012c03  jmp     ?Initialize@NTEventLog@@UEAAJXZ; NTEventLog::Initialize(void)
0x180012c08  xor     eax, eax
0x180012c0a  retn
```
