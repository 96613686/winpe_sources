# CryptHash::~CryptHash(void)

- ea: `0x180003348`
- end: `0x18000336c`
- name: `??1CryptHash@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(CryptHash *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d50`
- `0x180003dd4`
- `0x180003ed8`
- `0x180004220`
- `0x1800042ec`
- `0x1800050b0`

## callees

- `0x180003348`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x180003359`
- `ADVAPI32!CryptDestroyHash` at `0x180003359`

## pseudocode

```c
void __fastcall CryptHash::~CryptHash(HCRYPTHASH *this)
{
  HCRYPTHASH v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    CryptDestroyHash(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180003348  push    rbx
0x18000334a  sub     rsp, 20h
0x18000334e  mov     rbx, rcx
0x180003351  mov     rcx, [rcx]; hHash
0x180003354  test    rcx, rcx
0x180003357  jz      short loc_180003366
0x180003359  call    cs:__imp_CryptDestroyHash
0x18000335f  mov     qword ptr [rbx], 0
0x180003366  add     rsp, 20h
0x18000336a  pop     rbx
0x18000336b  retn
```
