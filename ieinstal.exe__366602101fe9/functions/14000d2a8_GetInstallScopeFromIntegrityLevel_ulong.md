# GetInstallScopeFromIntegrityLevel(ulong *)

- ea: `0x14000d2a8`
- end: `0x14000d30b`
- name: `?GetInstallScopeFromIntegrityLevel@@YAJPEAK@Z`
- size: `99`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000b3c0`
- `0x14000d314`

## callees

- `0x14000d2a8`

## import_xrefs

- `iertutil!__imp_?GetProcessIntegrityLevel@@YAJPEAXPEAK@Z` at `0x14000d2c6`
- `iertutil!__imp_?GetProcessIntegrityLevel@@YAJPEAXPEAK@Z` at `0x14000d2c6`

## pseudocode

```c
__int64 __fastcall GetInstallScopeFromIntegrityLevel(unsigned int *a1)
{
  unsigned int ProcessIntegrityLevel; // eax
  unsigned int v3; // edx
  unsigned int v5; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v5 = 0;
  ProcessIntegrityLevel = GetProcessIntegrityLevel(0, &v5);
  v3 = ProcessIntegrityLevel;
  if ( ProcessIntegrityLevel )
  {
    if ( ProcessIntegrityLevel != 1 )
      return v3;
    v3 = 0;
LABEL_6:
    *a1 = 1;
    return v3;
  }
  if ( v5 >= 0x3000 )
    goto LABEL_6;
  *a1 = v5 >= 0x2000 ? 2 : 0;
  return v3;
}

```

## disassembly

```asm
0x14000d2a8  push    rbx
0x14000d2aa  sub     rsp, 20h
0x14000d2ae  mov     rbx, rcx
0x14000d2b1  mov     dword ptr [rcx], 0
0x14000d2b7  xor     ecx, ecx
0x14000d2b9  mov     [rsp+28h+arg_0], 0
0x14000d2c1  lea     rdx, [rsp+28h+arg_0]
0x14000d2c6  call    cs:__imp_?GetProcessIntegrityLevel@@YAJPEAXPEAK@Z; GetProcessIntegrityLevel(void *,ulong *)
0x14000d2cd  nop     dword ptr [rax+rax+00h]
0x14000d2d2  mov     edx, eax
0x14000d2d4  test    eax, eax
0x14000d2d6  jnz     short loc_14000D2F5
0x14000d2d8  cmp     [rsp+28h+arg_0], 3000h
0x14000d2e0  jnb     short loc_14000D2FC
0x14000d2e2  cmp     [rsp+28h+arg_0], 2000h
0x14000d2ea  sbb     eax, eax
0x14000d2ec  not     eax
0x14000d2ee  and     eax, 2
0x14000d2f1  mov     [rbx], eax
0x14000d2f3  jmp     short loc_14000D302
0x14000d2f5  cmp     eax, 1
0x14000d2f8  jnz     short loc_14000D302
0x14000d2fa  xor     edx, edx
0x14000d2fc  mov     dword ptr [rbx], 1
0x14000d302  mov     eax, edx
0x14000d304  add     rsp, 20h
0x14000d308  pop     rbx
0x14000d309  retn
```
