# CServiceProvider::Unassociate(ushort const *,IFunctionDiscoveryNotification *)

- ea: `0x18000b8e0`
- end: `0x18000b9ad`
- name: `?Unassociate@CServiceProvider@@UEAAJPEBGPEAUIFunctionDiscoveryNotification@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this, const unsigned __int16 *, struct IFunctionDiscoveryNotification *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update`

## callees

- `0x18000b8e0`
- `0x18000bce4`
- `0x18000bd30`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Unassociate(
        CServiceProvider *this,
        const unsigned __int16 *a2,
        struct IFunctionDiscoveryNotification *a3)
{
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  int v8; // eax
  bool v9; // cf
  CServiceProvider *v11; // [rsp+20h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v11 = this;
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  v6 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *))(*((_QWORD *)this + 1) + 32LL))(
         (char *)this + 8,
         a2);
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    v8 = 0;
    v9 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  }
  else
  {
    if ( a3 )
      ((void (__fastcall *)(struct IFunctionDiscoveryNotification *, __int64, _QWORD, _QWORD, CServiceProvider *))a3->lpVtbl->OnUpdate)(
        a3,
        1,
        0,
        *((_QWORD *)this + 11),
        v11);
    v7 = WPP_GLOBAL_Control;
    v8 = 0;
    v9 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  }
  if ( v7 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v8) = !v9;
    if ( v8 )
      WPP_SF_sqd(v7[2], 17, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x18000b8e0  push    rbx
0x18000b8e2  push    rbp
0x18000b8e3  push    rsi
0x18000b8e4  push    rdi
0x18000b8e5  sub     rsp, 38h
0x18000b8e9  mov     rsi, r8
0x18000b8ec  mov     rdi, rdx
0x18000b8ef  mov     rbx, rcx
0x18000b8f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8f9  lea     rbp, WPP_GLOBAL_Control
0x18000b900  cmp     rcx, rbp
0x18000b903  jz      short loc_18000B925
0x18000b905  cmp     byte ptr [rcx+19h], 4
0x18000b909  jb      short loc_18000B925
0x18000b90b  mov     rcx, [rcx+10h]
0x18000b90f  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000b916  mov     edx, 10h
0x18000b91b  mov     [rsp+58h+var_38], rbx
0x18000b920  call    WPP_SF_sq
0x18000b925  lea     rcx, [rbx+8]
0x18000b929  mov     rdx, rdi
0x18000b92c  mov     rax, [rcx]
0x18000b92f  mov     rax, [rax+20h]
0x18000b933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b938  mov     edi, eax
0x18000b93a  test    eax, eax
0x18000b93c  jnz     short loc_18000B96B
0x18000b93e  test    rsi, rsi
0x18000b941  jz      short loc_18000B95C
0x18000b943  mov     rcx, [rsi]
0x18000b946  lea     edx, [rdi+1]
0x18000b949  mov     r9, [rbx+58h]
0x18000b94d  xor     r8d, r8d
0x18000b950  mov     rax, [rcx+18h]
0x18000b954  mov     rcx, rsi
0x18000b957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b95c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b963  xor     eax, eax
0x18000b965  cmp     byte ptr [rcx+19h], 4
0x18000b969  jmp     short loc_18000B978
0x18000b96b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b972  xor     eax, eax
0x18000b974  cmp     byte ptr [rcx+19h], 2
0x18000b978  setnb   al
0x18000b97b  cmp     rcx, rbp
0x18000b97e  jz      short loc_18000B9A2
0x18000b980  test    eax, eax
0x18000b982  jz      short loc_18000B9A2
0x18000b984  mov     rcx, [rcx+10h]
0x18000b988  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000b98f  mov     edx, 11h
0x18000b994  mov     [rsp+58h+var_30], edi
0x18000b998  mov     [rsp+58h+var_38], rbx
0x18000b99d  call    WPP_SF_sqd
0x18000b9a2  mov     eax, edi
0x18000b9a4  add     rsp, 38h
0x18000b9a8  pop     rdi
0x18000b9a9  pop     rsi
0x18000b9aa  pop     rbp
0x18000b9ab  pop     rbx
0x18000b9ac  retn
```
