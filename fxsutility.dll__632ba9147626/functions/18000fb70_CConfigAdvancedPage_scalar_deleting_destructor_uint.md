# CConfigAdvancedPage::`scalar deleting destructor'(uint)

- ea: `0x18000fb70`
- end: `0x18000fbc1`
- name: `??_GCConfigAdvancedPage@@UEAAPEAXI@Z`
- size: `81`
- prototype: `void *__fastcall(CConfigAdvancedPage *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x1800012d0`
- `0x18000fb70`

## import_xrefs

- `FXSAPI!FaxFreeBuffer` at `0x18000fb95`
- `FXSAPI!FaxFreeBuffer` at `0x18000fb95`

## pseudocode

```c
CConfigAdvancedPage *__fastcall CConfigAdvancedPage::`scalar deleting destructor'(CConfigAdvancedPage *this, char a2)
{
  void *v4; // rcx

  *(_QWORD *)this = &CConfigAdvancedPage::`vftable';
  v4 = (void *)*((_QWORD *)this + 71);
  if ( v4 )
    FaxFreeBuffer(v4);
  *(_QWORD *)this = &CPage::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000fb70  mov     [rsp+arg_0], rbx
0x18000fb75  push    rdi
0x18000fb76  sub     rsp, 20h
0x18000fb7a  lea     rax, ??_7CConfigAdvancedPage@@6B@; const CConfigAdvancedPage::`vftable'
0x18000fb81  mov     rbx, rcx
0x18000fb84  mov     [rcx], rax
0x18000fb87  mov     edi, edx
0x18000fb89  mov     rcx, [rcx+238h]; Buffer
0x18000fb90  test    rcx, rcx
0x18000fb93  jz      short loc_18000FB9B
0x18000fb95  call    cs:__imp_FaxFreeBuffer
0x18000fb9b  lea     rax, ??_7CPage@@6B@; const CPage::`vftable'
0x18000fba2  mov     [rbx], rax
0x18000fba5  test    dil, 1
0x18000fba9  jz      short loc_18000FBB3
0x18000fbab  mov     rcx, rbx; Block
0x18000fbae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fbb3  mov     rax, rbx
0x18000fbb6  mov     rbx, [rsp+28h+arg_0]
0x18000fbbb  add     rsp, 20h
0x18000fbbf  pop     rdi
0x18000fbc0  retn
```
