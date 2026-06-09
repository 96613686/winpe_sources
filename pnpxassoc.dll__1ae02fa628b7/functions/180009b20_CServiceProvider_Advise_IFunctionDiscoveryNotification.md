# CServiceProvider::Advise(IFunctionDiscoveryNotification *)

- ea: `0x180009b20`
- end: `0x180009c01`
- name: `?Advise@CServiceProvider@@UEAAJPEAUIFunctionDiscoveryNotification@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this, struct IFunctionDiscoveryNotification *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180009b20`
- `0x18000bce4`
- `0x18000bd30`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Advise(CServiceProvider *this, struct IFunctionDiscoveryNotification *a2)
{
  _BYTE *v4; // r9
  unsigned int v5; // esi
  __int64 v6; // rcx
  int v7; // eax
  bool v8; // cf

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = -2147024809;
  if ( a2 )
    v5 = 0;
  if ( *((struct IFunctionDiscoveryNotification **)this + 10) != a2 )
  {
    if ( a2 )
      ((void (__fastcall *)(struct IFunctionDiscoveryNotification *))a2->lpVtbl->AddRef)(a2);
    v6 = *((_QWORD *)this + 10);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 10) = a2;
    v4 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  if ( a2 )
    v8 = v4[25] < 4u;
  else
    v8 = v4[25] < 2u;
  if ( v4 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v7) = !v8;
    if ( v7 )
      WPP_SF_sqd(*((_QWORD *)v4 + 2), 40, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  return v5;
}

```

## disassembly

```asm
0x180009b20  push    rbx
0x180009b22  push    rbp
0x180009b23  push    rsi
0x180009b24  push    rdi
0x180009b25  sub     rsp, 38h
0x180009b29  mov     rbx, rdx
0x180009b2c  mov     rdi, rcx
0x180009b2f  mov     r9, cs:WPP_GLOBAL_Control
0x180009b36  lea     rbp, WPP_GLOBAL_Control
0x180009b3d  cmp     r9, rbp
0x180009b40  jz      short loc_180009B6E
0x180009b42  cmp     byte ptr [r9+19h], 4
0x180009b47  jb      short loc_180009B6E
0x180009b49  lea     rax, [rcx-10h]
0x180009b4d  mov     edx, 27h ; '''
0x180009b52  mov     rcx, [r9+10h]
0x180009b56  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x180009b5d  mov     [rsp+58h+var_38], rax
0x180009b62  call    WPP_SF_sq
0x180009b67  mov     r9, cs:WPP_GLOBAL_Control
0x180009b6e  xor     eax, eax
0x180009b70  mov     esi, 80070057h
0x180009b75  test    rbx, rbx
0x180009b78  cmovnz  esi, eax
0x180009b7b  cmp     [rdi+50h], rbx
0x180009b7f  jz      short loc_180009BB5
0x180009b81  test    rbx, rbx
0x180009b84  jz      short loc_180009B95
0x180009b86  mov     rax, [rbx]
0x180009b89  mov     rcx, rbx
0x180009b8c  mov     rax, [rax+8]
0x180009b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b95  mov     rcx, [rdi+50h]
0x180009b99  test    rcx, rcx
0x180009b9c  jz      short loc_180009BAA
0x180009b9e  mov     rax, [rcx]
0x180009ba1  mov     rax, [rax+10h]
0x180009ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009baa  mov     [rdi+50h], rbx
0x180009bae  mov     r9, cs:WPP_GLOBAL_Control
0x180009bb5  xor     eax, eax
0x180009bb7  test    rbx, rbx
0x180009bba  jz      short loc_180009BC3
0x180009bbc  cmp     byte ptr [r9+19h], 4
0x180009bc1  jmp     short loc_180009BC8
0x180009bc3  cmp     byte ptr [r9+19h], 2
0x180009bc8  setnb   al
0x180009bcb  cmp     r9, rbp
0x180009bce  jz      short loc_180009BF6
0x180009bd0  test    eax, eax
0x180009bd2  jz      short loc_180009BF6
0x180009bd4  lea     rcx, [rdi-10h]
0x180009bd8  mov     [rsp+58h+var_30], esi
0x180009bdc  mov     [rsp+58h+var_38], rcx
0x180009be1  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x180009be8  mov     rcx, [r9+10h]
0x180009bec  mov     edx, 28h ; '('
0x180009bf1  call    WPP_SF_sqd
0x180009bf6  mov     eax, esi
0x180009bf8  add     rsp, 38h
0x180009bfc  pop     rdi
0x180009bfd  pop     rsi
0x180009bfe  pop     rbp
0x180009bff  pop     rbx
0x180009c00  retn
```
