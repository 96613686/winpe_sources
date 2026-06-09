# InitServerInfo(ushort *,IMSAdminBaseW * *)

- ea: `0x180003bd8`
- end: `0x180003c37`
- name: `?InitServerInfo@@YAJPEAGPEAPEAUIMSAdminBaseW@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct IMSAdminBaseW **)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180005a58`
- `0x18000683c`
- `0x18000745c`
- `0x180007a80`
- `0x18000828c`
- `0x180008fc0`
- `0x180009df0`
- `0x18000c8d8`

## callees

- `0x180003ab8`
- `0x180003bd8`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall InitServerInfo(unsigned __int16 *a1, struct IMSAdminBaseW **a2)
{
  bool v3; // zf
  unsigned __int16 *v4; // rcx
  int inited; // eax
  struct IMSAdminBaseW *v7; // rcx
  unsigned int v8; // ebx
  struct IMSAdminBaseW *v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = 0;
  v3 = a1 == 0;
  v4 = L"Localhost";
  if ( !v3 )
    v4 = a1;
  inited = InitAdminBase(v4, &v10);
  v7 = v10;
  v8 = inited;
  if ( inited >= 0 )
  {
    *a2 = v10;
    v7 = 0;
  }
  if ( v7 )
    ((void (__fastcall *)(struct IMSAdminBaseW *))v7->lpVtbl->Release)(v7);
  return v8;
}

```

## disassembly

```asm
0x180003bd8  mov     [rsp+arg_8], rbx
0x180003bdd  push    rdi
0x180003bde  sub     rsp, 20h
0x180003be2  mov     rax, rcx
0x180003be5  mov     [rsp+28h+arg_0], 0
0x180003bee  test    rax, rax
0x180003bf1  lea     rcx, aLocalhost_0; "Localhost"
0x180003bf8  mov     rdi, rdx
0x180003bfb  lea     rdx, [rsp+28h+arg_0]; struct IMSAdminBaseW **
0x180003c00  cmovnz  rcx, rax; unsigned __int16 *
0x180003c04  call    ?InitAdminBase@@YAJPEAGPEAPEAUIMSAdminBaseW@@@Z; InitAdminBase(ushort *,IMSAdminBaseW * *)
0x180003c09  mov     rcx, [rsp+28h+arg_0]
0x180003c0e  mov     ebx, eax
0x180003c10  test    eax, eax
0x180003c12  js      short loc_180003C19
0x180003c14  mov     [rdi], rcx
0x180003c17  xor     ecx, ecx
0x180003c19  test    rcx, rcx
0x180003c1c  jz      short loc_180003C2A
0x180003c1e  mov     rax, [rcx]
0x180003c21  mov     rax, [rax+10h]
0x180003c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c2a  mov     eax, ebx
0x180003c2c  mov     rbx, [rsp+28h+arg_8]
0x180003c31  add     rsp, 20h
0x180003c35  pop     rdi
0x180003c36  retn
```
