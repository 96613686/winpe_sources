# CHECK_ACCESS_HANDLER::SetStatus(IHttpContext *,ushort,long)

- ea: `0x180002d54`
- end: `0x180002e04`
- name: `?SetStatus@CHECK_ACCESS_HANDLER@@AEAAXPEAVIHttpContext@@GJ@Z`
- size: `176`
- prototype: `void __fastcall(CHECK_ACCESS_HANDLER *__hidden this, struct IHttpContext *, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b5c`

## callees

- `0x180002d54`
- `0x180005010`

## pseudocode

```c
void __fastcall CHECK_ACCESS_HANDLER::SetStatus(
        CHECK_ACCESS_HANDLER *this,
        struct IHttpContext *a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v7; // rax
  __int64 v8; // r11
  int v9; // edx
  int v10; // edx
  const char *v11; // r8

  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  v8 = *((_QWORD *)this + 2);
  v9 = *(_DWORD *)(v8 + 48);
  if ( v9 )
  {
    v10 = v9 - 401;
    if ( v10 )
    {
      if ( v10 == 3 )
        v11 = "Not Found";
      else
        v11 = "Forbidden";
    }
    else
    {
      v11 = "Unauthorized";
    }
    (*(void (__fastcall **)(__int64, _QWORD, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v7 + 24LL))(
      v7,
      *(unsigned __int16 *)(v8 + 48),
      v11,
      a3,
      a4,
      0,
      0);
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 104LL))(v7);
  }
}

```

## disassembly

```asm
0x180002d54  mov     [rsp+arg_0], rbx
0x180002d59  mov     [rsp+arg_8], rsi
0x180002d5e  push    rdi
0x180002d5f  sub     rsp, 40h
0x180002d63  mov     rax, [rdx]
0x180002d66  mov     rbx, rcx
0x180002d69  mov     rcx, rdx
0x180002d6c  mov     edi, r9d
0x180002d6f  movzx   esi, r8w
0x180002d73  mov     rax, [rax+20h]
0x180002d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d7c  mov     r11, [rbx+10h]
0x180002d80  mov     r10, rax
0x180002d83  mov     edx, [r11+30h]
0x180002d87  test    edx, edx
0x180002d89  jz      short loc_180002DE5
0x180002d8b  sub     edx, 191h
0x180002d91  jz      short loc_180002DAF
0x180002d93  sub     edx, 2
0x180002d96  jz      short loc_180002DA6
0x180002d98  cmp     edx, 1
0x180002d9b  jnz     short loc_180002DA6
0x180002d9d  lea     r8, aNotFound; "Not Found"
0x180002da4  jmp     short loc_180002DB6
0x180002da6  lea     r8, aForbidden; "Forbidden"
0x180002dad  jmp     short loc_180002DB6
0x180002daf  lea     r8, aUnauthorized; "Unauthorized"
0x180002db6  mov     rax, [rax]
0x180002db9  movzx   r9d, si
0x180002dbd  movzx   edx, word ptr [r11+30h]
0x180002dc2  mov     rcx, r10
0x180002dc5  mov     [rsp+48h+var_18], 0
0x180002dcd  mov     [rsp+48h+var_20], 0
0x180002dd6  mov     rax, [rax+18h]
0x180002dda  mov     [rsp+48h+var_28], edi
0x180002dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de3  jmp     short loc_180002DF4
0x180002de5  mov     rax, [rax]
0x180002de8  mov     rcx, r10
0x180002deb  mov     rax, [rax+68h]
0x180002def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df4  mov     rbx, [rsp+48h+arg_0]
0x180002df9  mov     rsi, [rsp+48h+arg_8]
0x180002dfe  add     rsp, 40h
0x180002e02  pop     rdi
0x180002e03  retn
```
