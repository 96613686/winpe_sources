# CServiceProvider::Unadvise(void)

- ea: `0x18000b500`
- end: `0x18000b5b0`
- name: `?Unadvise@CServiceProvider@@UEAAJXZ`
- size: `176`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000b500`
- `0x18000bce4`
- `0x18000bd30`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Unadvise(CServiceProvider *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 16LL))(*((_QWORD *)this + 10));
    *((_QWORD *)this + 10) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u )
    WPP_SF_sqd(v2[2], 42, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000b500  mov     [rsp+arg_0], rbx
0x18000b505  push    rdi
0x18000b506  sub     rsp, 30h
0x18000b50a  mov     rbx, rcx
0x18000b50d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b514  lea     rdi, WPP_GLOBAL_Control
0x18000b51b  cmp     rcx, rdi
0x18000b51e  jz      short loc_18000B54B
0x18000b520  cmp     byte ptr [rcx+19h], 4
0x18000b524  jb      short loc_18000B54B
0x18000b526  mov     rcx, [rcx+10h]
0x18000b52a  lea     rax, [rbx-10h]
0x18000b52e  mov     edx, 29h ; ')'
0x18000b533  mov     [rsp+38h+var_18], rax
0x18000b538  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000b53f  call    WPP_SF_sq
0x18000b544  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b54b  mov     rdx, [rbx+50h]
0x18000b54f  test    rdx, rdx
0x18000b552  jz      short loc_18000B572
0x18000b554  mov     rax, [rdx]
0x18000b557  mov     rcx, rdx
0x18000b55a  mov     rax, [rax+10h]
0x18000b55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b563  mov     qword ptr [rbx+50h], 0
0x18000b56b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b572  cmp     rcx, rdi
0x18000b575  jz      short loc_18000B5A3
0x18000b577  cmp     byte ptr [rcx+19h], 4
0x18000b57b  jb      short loc_18000B5A3
0x18000b57d  mov     rcx, [rcx+10h]
0x18000b581  lea     rax, [rbx-10h]
0x18000b585  mov     edx, 2Ah ; '*'
0x18000b58a  mov     [rsp+38h+var_10], 0
0x18000b592  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000b599  mov     [rsp+38h+var_18], rax
0x18000b59e  call    WPP_SF_sqd
0x18000b5a3  mov     rbx, [rsp+38h+arg_0]
0x18000b5a8  xor     eax, eax
0x18000b5aa  add     rsp, 30h
0x18000b5ae  pop     rdi
0x18000b5af  retn
```
