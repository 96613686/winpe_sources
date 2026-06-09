# Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(_MI_Operation *)

- ea: `0x18000a3a0`
- end: `0x18000a453`
- name: `?MI_Operation_Close_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW4_MI_Result@@PEAU_MI_Operation@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::Plugin::CimUtilities *this, struct _MI_Operation *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009ce0`
- `0x18000a070`

## callees

- `0x18000a3a0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(
        Microsoft::HostGuardian::Client::Plugin::CimUtilities *this,
        struct _MI_Operation *a2)
{
  unsigned int v3; // esi
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rcx
  char v8; // [rsp+70h] [rbp+28h] BYREF
  int v9; // [rsp+78h] [rbp+30h] BYREF
  __int64 v10; // [rsp+80h] [rbp+38h] BYREF
  __int64 v11; // [rsp+88h] [rbp+40h] BYREF

  v8 = 0;
  v11 = 0;
  v3 = 4;
  v9 = 0;
  v10 = 0;
  if ( this )
  {
    while ( 1 )
    {
      v4 = *((_QWORD *)this + 2);
      if ( !v4 )
        break;
      v5 = (*(__int64 (__fastcall **)(Microsoft::HostGuardian::Client::Plugin::CimUtilities *, __int64 *, char *, int *, __int64 *, _QWORD))(v4 + 24))(
             this,
             &v11,
             &v8,
             &v9,
             &v10,
             0);
      v6 = (__int64)this + 16;
      if ( v5 || v9 )
        goto LABEL_11;
      if ( v8 != 1 )
        goto LABEL_10;
    }
    v6 = (__int64)this + 16;
  }
  else
  {
    v6 = 16;
  }
  v9 = 4;
  v8 = 0;
LABEL_10:
  if ( this )
  {
LABEL_11:
    if ( *(_QWORD *)v6 )
      return (**(unsigned int (__fastcall ***)(Microsoft::HostGuardian::Client::Plugin::CimUtilities *))v6)(this);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a3a0  push    rbp
0x18000a3a2  push    rbx
0x18000a3a3  push    rsi
0x18000a3a4  push    rdi
0x18000a3a5  mov     rbp, rsp
0x18000a3a8  sub     rsp, 48h
0x18000a3ac  mov     [rbp+arg_0], 0
0x18000a3b0  mov     rbx, rcx
0x18000a3b3  mov     [rbp+arg_18], 0
0x18000a3bb  mov     esi, 4
0x18000a3c0  mov     [rbp+arg_8], 0
0x18000a3c7  mov     [rbp+arg_10], 0
0x18000a3cf  test    rcx, rcx
0x18000a3d2  jz      short loc_18000A423
0x18000a3d4  lea     rdi, [rbx+10h]
0x18000a3d8  mov     rax, [rdi]
0x18000a3db  test    rax, rax
0x18000a3de  jz      short loc_18000A41E
0x18000a3e0  mov     rax, [rax+18h]
0x18000a3e4  lea     rcx, [rbp+arg_10]
0x18000a3e8  mov     [rsp+48h+var_20], 0
0x18000a3f1  lea     r9, [rbp+arg_8]
0x18000a3f5  mov     [rsp+48h+var_28], rcx
0x18000a3fa  lea     r8, [rbp+arg_0]
0x18000a3fe  mov     rcx, rbx
0x18000a401  lea     rdx, [rbp+arg_18]
0x18000a405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a40a  mov     rcx, rdi
0x18000a40d  test    eax, eax
0x18000a40f  jnz     short loc_18000A433
0x18000a411  cmp     [rbp+arg_8], eax
0x18000a414  jnz     short loc_18000A433
0x18000a416  cmp     [rbp+arg_0], 1
0x18000a41a  jz      short loc_18000A3D4
0x18000a41c  jmp     short loc_18000A42E
0x18000a41e  mov     rcx, rdi
0x18000a421  jmp     short loc_18000A427
0x18000a423  add     rcx, 10h
0x18000a427  mov     [rbp+arg_8], esi
0x18000a42a  mov     [rbp+arg_0], 0
0x18000a42e  test    rbx, rbx
0x18000a431  jz      short loc_18000A448
0x18000a433  mov     rax, [rcx]
0x18000a436  test    rax, rax
0x18000a439  jz      short loc_18000A448
0x18000a43b  mov     rax, [rax]
0x18000a43e  mov     rcx, rbx
0x18000a441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a446  mov     esi, eax
0x18000a448  mov     eax, esi
0x18000a44a  add     rsp, 48h
0x18000a44e  pop     rdi
0x18000a44f  pop     rsi
0x18000a450  pop     rbx
0x18000a451  pop     rbp
0x18000a452  retn
```
