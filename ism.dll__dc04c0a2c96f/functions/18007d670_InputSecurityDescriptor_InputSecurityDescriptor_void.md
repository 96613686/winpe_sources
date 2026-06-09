# InputSecurityDescriptor::~InputSecurityDescriptor(void)

- ea: `0x18007d670`
- end: `0x18007d6a2`
- name: `??1InputSecurityDescriptor@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(InputSecurityDescriptor *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003a734`
- `0x18003aa60`
- `0x1800e25fc`
- `0x1800e5a54`
- `0x1801a572c`
- `0x1801c59e3`
- `0x1801c5aed`
- `0x1801c5aff`
- `0x1801c6873`

## callees

- `0x18007d670`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d69a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d69a`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18007d687`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18007d687`

## pseudocode

```c
void __fastcall InputSecurityDescriptor::~InputSecurityDescriptor(InputSecurityDescriptor *this)
{
  void *v2; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    if ( *((_BYTE *)this + 8) )
      FreeTransientObjectSecurityDescriptor();
    else
      LocalFree(v2);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18007d670  push    rbx
0x18007d672  sub     rsp, 20h
0x18007d676  mov     rbx, rcx
0x18007d679  mov     rcx, [rcx]; hMem
0x18007d67c  test    rcx, rcx
0x18007d67f  jz      short loc_18007D694
0x18007d681  cmp     byte ptr [rbx+8], 0
0x18007d685  jz      short loc_18007D69A
0x18007d687  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18007d68d  mov     qword ptr [rbx], 0
0x18007d694  add     rsp, 20h
0x18007d698  pop     rbx
0x18007d699  retn
0x18007d69a  call    cs:__imp_LocalFree
0x18007d6a0  jmp     short loc_18007D68D
```
