# CServiceProvider::Delete(ushort const *,IFunctionDiscoveryNotification *)

- ea: `0x18000a780`
- end: `0x18000a84d`
- name: `?Delete@CServiceProvider@@UEAAJPEBGPEAUIFunctionDiscoveryNotification@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this, const unsigned __int16 *, struct IFunctionDiscoveryNotification *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x18000a780`
- `0x18000bce4`
- `0x18000bd30`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Delete(
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
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  v6 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *))(*((_QWORD *)this + 1) + 40LL))(
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
      WPP_SF_sqd(v7[2], 19, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x18000a780  push    rbx
0x18000a782  push    rbp
0x18000a783  push    rsi
0x18000a784  push    rdi
0x18000a785  sub     rsp, 38h
0x18000a789  mov     rsi, r8
0x18000a78c  mov     rdi, rdx
0x18000a78f  mov     rbx, rcx
0x18000a792  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a799  lea     rbp, WPP_GLOBAL_Control
0x18000a7a0  cmp     rcx, rbp
0x18000a7a3  jz      short loc_18000A7C5
0x18000a7a5  cmp     byte ptr [rcx+19h], 4
0x18000a7a9  jb      short loc_18000A7C5
0x18000a7ab  mov     rcx, [rcx+10h]
0x18000a7af  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a7b6  mov     edx, 12h
0x18000a7bb  mov     [rsp+58h+var_38], rbx
0x18000a7c0  call    WPP_SF_sq
0x18000a7c5  lea     rcx, [rbx+8]
0x18000a7c9  mov     rdx, rdi
0x18000a7cc  mov     rax, [rcx]
0x18000a7cf  mov     rax, [rax+28h]
0x18000a7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d8  mov     edi, eax
0x18000a7da  test    eax, eax
0x18000a7dc  jnz     short loc_18000A80B
0x18000a7de  test    rsi, rsi
0x18000a7e1  jz      short loc_18000A7FC
0x18000a7e3  mov     rcx, [rsi]
0x18000a7e6  lea     edx, [rdi+1]
0x18000a7e9  mov     r9, [rbx+58h]
0x18000a7ed  xor     r8d, r8d
0x18000a7f0  mov     rax, [rcx+18h]
0x18000a7f4  mov     rcx, rsi
0x18000a7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a803  xor     eax, eax
0x18000a805  cmp     byte ptr [rcx+19h], 4
0x18000a809  jmp     short loc_18000A818
0x18000a80b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a812  xor     eax, eax
0x18000a814  cmp     byte ptr [rcx+19h], 2
0x18000a818  setnb   al
0x18000a81b  cmp     rcx, rbp
0x18000a81e  jz      short loc_18000A842
0x18000a820  test    eax, eax
0x18000a822  jz      short loc_18000A842
0x18000a824  mov     rcx, [rcx+10h]
0x18000a828  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a82f  mov     edx, 13h
0x18000a834  mov     [rsp+58h+var_30], edi
0x18000a838  mov     [rsp+58h+var_38], rbx
0x18000a83d  call    WPP_SF_sqd
0x18000a842  mov     eax, edi
0x18000a844  add     rsp, 38h
0x18000a848  pop     rdi
0x18000a849  pop     rsi
0x18000a84a  pop     rbp
0x18000a84b  pop     rbx
0x18000a84c  retn
```
