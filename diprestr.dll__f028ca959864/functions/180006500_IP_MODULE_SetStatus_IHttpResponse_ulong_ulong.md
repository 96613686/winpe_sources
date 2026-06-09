# IP_MODULE::SetStatus(IHttpResponse *,ulong,ulong)

- ea: `0x180006500`
- end: `0x180006583`
- name: `?SetStatus@IP_MODULE@@CAJPEAVIHttpResponse@@KK@Z`
- size: `131`
- prototype: `__int64 __fastcall(struct IHttpResponse *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047a4`

## callees

- `0x180006500`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall IP_MODULE::SetStatus(struct IHttpResponse *a1, int a2, unsigned __int16 a3)
{
  unsigned int v3; // ebx
  int v4; // edx
  __int64 v5; // r9
  __int64 v6; // rdx
  const char *v7; // r8

  v3 = 0;
  if ( a2 )
  {
    v4 = a2 - 401;
    if ( v4 )
    {
      v5 = a3;
      if ( v4 == 3 )
      {
        v6 = 404;
        v7 = "Not Found";
      }
      else
      {
        v6 = 403;
        v7 = "Forbidden";
      }
    }
    else
    {
      v5 = a3;
      v6 = 401;
      v7 = "Unauthorized";
    }
    return (*(unsigned int (__fastcall **)(struct IHttpResponse *, __int64, const char *, __int64, _DWORD, _QWORD, _DWORD))(*(_QWORD *)a1 + 24LL))(
             a1,
             v6,
             v7,
             v5,
             0,
             0,
             0);
  }
  else
  {
    (*(void (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)a1 + 104LL))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x180006500  push    rbx
0x180006502  sub     rsp, 40h
0x180006506  xor     ebx, ebx
0x180006508  test    edx, edx
0x18000650a  jz      short loc_18000656F
0x18000650c  mov     r10d, 191h
0x180006512  sub     edx, r10d
0x180006515  jz      short loc_180006544
0x180006517  sub     edx, 2
0x18000651a  jz      short loc_180006532
0x18000651c  cmp     edx, 1
0x18000651f  jnz     short loc_180006532
0x180006521  movzx   r9d, r8w
0x180006525  lea     edx, [r10+3]
0x180006529  lea     r8, aNotFound; "Not Found"
0x180006530  jmp     short loc_180006552
0x180006532  movzx   r9d, r8w
0x180006536  mov     edx, 193h
0x18000653b  lea     r8, aForbidden; "Forbidden"
0x180006542  jmp     short loc_180006552
0x180006544  movzx   r9d, r8w
0x180006548  mov     edx, r10d
0x18000654b  lea     r8, aUnauthorized; "Unauthorized"
0x180006552  mov     rax, [rcx]
0x180006555  mov     [rsp+48h+var_18], ebx
0x180006559  mov     [rsp+48h+var_20], rbx
0x18000655e  mov     [rsp+48h+var_28], ebx
0x180006562  mov     rax, [rax+18h]
0x180006566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000656b  mov     ebx, eax
0x18000656d  jmp     short loc_18000657B
0x18000656f  mov     rax, [rcx]
0x180006572  mov     rax, [rax+68h]
0x180006576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000657b  mov     eax, ebx
0x18000657d  add     rsp, 40h
0x180006581  pop     rbx
0x180006582  retn
```
