# CConfigGeneralPage::`scalar deleting destructor'(uint)

- ea: `0x18000fbd0`
- end: `0x18000fbff`
- name: `??_GCConfigGeneralPage@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CConfigGeneralPage *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800012d0`
- `0x18000fbd0`
- `0x180010574`

## pseudocode

```c
CConfigGeneralPage *__fastcall CConfigGeneralPage::`scalar deleting destructor'(CConfigGeneralPage *this, char a2)
{
  CConfigGeneralPage::~CConfigGeneralPage(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000fbd0  mov     [rsp+arg_0], rbx
0x18000fbd5  push    rdi
0x18000fbd6  sub     rsp, 20h
0x18000fbda  mov     ebx, edx
0x18000fbdc  mov     rdi, rcx
0x18000fbdf  call    ??1CConfigGeneralPage@@UEAA@XZ; CConfigGeneralPage::~CConfigGeneralPage(void)
0x18000fbe4  test    bl, 1
0x18000fbe7  jz      short loc_18000FBF1
0x18000fbe9  mov     rcx, rdi; Block
0x18000fbec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fbf1  mov     rbx, [rsp+28h+arg_0]
0x18000fbf6  mov     rax, rdi
0x18000fbf9  add     rsp, 20h
0x18000fbfd  pop     rdi
0x18000fbfe  retn
```
