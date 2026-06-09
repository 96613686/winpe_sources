# dia::CDiaLoadCallback::Fread(void *,long,unsigned __int64)

- ea: `0x18010f6e0`
- end: `0x18010f7dd`
- name: `?Fread@CDiaLoadCallback@dia@@IEAA_NPEAXJ_K@Z`
- size: `253`
- prototype: `bool(dia::CDiaLoadCallback *__hidden this, void *, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18010f8c0`
- `0x180110350`

## callees

- `0x18010f6e0`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18010f7af`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18010f7af`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18010f792`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18010f792`

## pseudocode

```c
bool __fastcall dia::CDiaLoadCallback::Fread(dia::CDiaLoadCallback *this, void *a2, unsigned int a3, size_t a4)
{
  __int64 v5; // rcx
  size_t v8; // rax
  FILE *v9; // rcx
  int v11; // [rsp+40h] [rbp+8h] BYREF

  v5 = *((_QWORD *)this + 14);
  if ( v5 || (v5 = *((_QWORD *)this + 15)) != 0 )
  {
    v11 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, int *, void *))(*(_QWORD *)v5 + 24LL))(
           v5,
           a3,
           (unsigned int)a4,
           &v11,
           a2) < 0
      || a4 != v11 )
    {
LABEL_9:
      LOBYTE(v8) = 0;
      return v8;
    }
    LOBYTE(v8) = 1;
  }
  else
  {
    v9 = (FILE *)*((_QWORD *)this + 33);
    if ( !v9 )
      goto LABEL_9;
    if ( fseek(v9, a3, 0) )
      goto LABEL_9;
    v8 = fread(a2, a4, 1u, *((FILE **)this + 33));
    if ( v8 != 1 )
      goto LABEL_9;
  }
  return v8;
}

```

## disassembly

```asm
0x18010f6e0  mov     [rsp+arg_8], rbx
0x18010f6e5  mov     [rsp+arg_10], rsi
0x18010f6ea  push    rdi
0x18010f6eb  sub     rsp, 30h
0x18010f6ef  mov     rdi, rcx
0x18010f6f2  mov     r10d, r8d
0x18010f6f5  mov     rcx, [rcx+70h]
0x18010f6f9  mov     rbx, r9
0x18010f6fc  mov     rsi, rdx
0x18010f6ff  test    rcx, rcx
0x18010f702  jz      short loc_18010F750
0x18010f704  mov     [rsp+38h+arg_0], 0
0x18010f70c  lea     r9, [rsp+38h+arg_0]
0x18010f711  mov     rax, [rcx]
0x18010f714  mov     r8d, ebx
0x18010f717  mov     edx, r10d
0x18010f71a  mov     [rsp+38h+var_18], rsi
0x18010f71f  mov     rax, [rax+18h]
0x18010f723  call    cs:__guard_dispatch_icall_fptr
0x18010f729  test    eax, eax
0x18010f72b  js      loc_18010F7CB
0x18010f731  mov     eax, [rsp+38h+arg_0]
0x18010f735  cmp     rbx, rax
0x18010f738  jnz     loc_18010F7CB
0x18010f73e  mov     al, 1
0x18010f740  mov     rbx, [rsp+38h+arg_8]
0x18010f745  mov     rsi, [rsp+38h+arg_10]
0x18010f74a  add     rsp, 30h
0x18010f74e  pop     rdi
0x18010f74f  retn
0x18010f750  mov     rcx, [rdi+78h]
0x18010f754  test    rcx, rcx
0x18010f757  jz      short loc_18010F780
0x18010f759  mov     [rsp+38h+arg_0], 0
0x18010f761  lea     r9, [rsp+38h+arg_0]
0x18010f766  mov     rax, [rcx]
0x18010f769  mov     r8d, ebx
0x18010f76c  mov     edx, r10d
0x18010f76f  mov     [rsp+38h+var_18], rsi
0x18010f774  mov     rax, [rax+18h]
0x18010f778  call    cs:__guard_dispatch_icall_fptr
0x18010f77e  jmp     short loc_18010F729
0x18010f780  mov     rcx, [rdi+108h]; Stream
0x18010f787  test    rcx, rcx
0x18010f78a  jz      short loc_18010F7CB
0x18010f78c  xor     r8d, r8d; Origin
0x18010f78f  mov     edx, r10d; Offset
0x18010f792  call    cs:__imp_fseek
0x18010f798  test    eax, eax
0x18010f79a  jnz     short loc_18010F7CB
0x18010f79c  mov     r9, [rdi+108h]; Stream
0x18010f7a3  mov     r8d, 1; ElementCount
0x18010f7a9  mov     rdx, rbx; ElementSize
0x18010f7ac  mov     rcx, rsi; Buffer
0x18010f7af  call    cs:__imp_fread
0x18010f7b5  cmp     rax, 1
0x18010f7b9  jnz     short loc_18010F7CB
0x18010f7bb  mov     rbx, [rsp+38h+arg_8]
0x18010f7c0  mov     rsi, [rsp+38h+arg_10]
0x18010f7c5  add     rsp, 30h
0x18010f7c9  pop     rdi
0x18010f7ca  retn
0x18010f7cb  mov     rbx, [rsp+38h+arg_8]
0x18010f7d0  xor     al, al
0x18010f7d2  mov     rsi, [rsp+38h+arg_10]
0x18010f7d7  add     rsp, 30h
0x18010f7db  pop     rdi
0x18010f7dc  retn
```
