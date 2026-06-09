# CServiceProvider::Associate(ushort const *,IFunctionDiscoveryNotification *)

- ea: `0x18000a070`
- end: `0x18000a167`
- name: `?Associate@CServiceProvider@@UEAAJPEBGPEAUIFunctionDiscoveryNotification@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this, const unsigned __int16 *, struct IFunctionDiscoveryNotification *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update`

## callees

- `0x18000a070`
- `0x18000b2e4`
- `0x18000bce4`
- `0x18000bd30`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Associate(
        CServiceProvider *this,
        const unsigned __int16 *a2,
        struct IFunctionDiscoveryNotification *a3)
{
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  int v8; // eax
  bool v9; // cf

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  if ( !a3 || (v6 = CServiceProvider::SetupPnpNotification(this, 1u, QUA_ADD, a3, 0)) == 0 )
  {
    v6 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *))(*((_QWORD *)this + 1) + 24LL))(
           (char *)this + 8,
           a2);
    if ( !v6 )
    {
      v7 = WPP_GLOBAL_Control;
      v8 = 0;
      v9 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
      goto LABEL_11;
    }
    if ( a3 )
      CServiceProvider::SetupPnpNotification(this, 0, QUA_ADD, a3, 0);
  }
  v7 = WPP_GLOBAL_Control;
  v8 = 0;
  v9 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
LABEL_11:
  if ( v7 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v8) = !v9;
    if ( v8 )
      WPP_SF_sqd(v7[2], 15, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x18000a070  push    rbx
0x18000a072  push    rbp
0x18000a073  push    rsi
0x18000a074  push    rdi
0x18000a075  push    r14
0x18000a077  sub     rsp, 30h
0x18000a07b  mov     rbx, r8
0x18000a07e  mov     rbp, rdx
0x18000a081  mov     rsi, rcx
0x18000a084  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a08b  lea     r14, WPP_GLOBAL_Control
0x18000a092  cmp     rcx, r14
0x18000a095  jz      short loc_18000A0B7
0x18000a097  cmp     byte ptr [rcx+19h], 4
0x18000a09b  jb      short loc_18000A0B7
0x18000a09d  mov     rcx, [rcx+10h]
0x18000a0a1  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a0a8  mov     edx, 0Eh
0x18000a0ad  mov     [rsp+58h+var_38], rsi
0x18000a0b2  call    WPP_SF_sq
0x18000a0b7  test    rbx, rbx
0x18000a0ba  jz      short loc_18000A0DD
0x18000a0bc  xor     r8d, r8d; enum tagQueryUpdateAction
0x18000a0bf  mov     [rsp+58h+var_38], 0; unsigned __int16 *
0x18000a0c8  mov     r9, rbx; struct IFunctionDiscoveryNotification *
0x18000a0cb  mov     rcx, rsi; this
0x18000a0ce  lea     edx, [r8+1]; int
0x18000a0d2  call    ?SetupPnpNotification@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG@Z; CServiceProvider::SetupPnpNotification(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *)
0x18000a0d7  mov     edi, eax
0x18000a0d9  test    eax, eax
0x18000a0db  jnz     short loc_18000A114
0x18000a0dd  lea     rcx, [rsi+8]
0x18000a0e1  mov     rdx, rbp
0x18000a0e4  mov     rax, [rcx]
0x18000a0e7  mov     rax, [rax+18h]
0x18000a0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0f0  mov     edi, eax
0x18000a0f2  test    eax, eax
0x18000a0f4  jz      short loc_18000A123
0x18000a0f6  test    rbx, rbx
0x18000a0f9  jz      short loc_18000A114
0x18000a0fb  mov     r9, rbx; struct IFunctionDiscoveryNotification *
0x18000a0fe  mov     [rsp+58h+var_38], 0; unsigned __int16 *
0x18000a107  xor     r8d, r8d; enum tagQueryUpdateAction
0x18000a10a  xor     edx, edx; int
0x18000a10c  mov     rcx, rsi; this
0x18000a10f  call    ?SetupPnpNotification@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG@Z; CServiceProvider::SetupPnpNotification(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *)
0x18000a114  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a11b  xor     eax, eax
0x18000a11d  cmp     byte ptr [rcx+19h], 2
0x18000a121  jmp     short loc_18000A130
0x18000a123  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a12a  xor     eax, eax
0x18000a12c  cmp     byte ptr [rcx+19h], 4
0x18000a130  setnb   al
0x18000a133  cmp     rcx, r14
0x18000a136  jz      short loc_18000A15A
0x18000a138  test    eax, eax
0x18000a13a  jz      short loc_18000A15A
0x18000a13c  mov     rcx, [rcx+10h]
0x18000a140  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a147  mov     edx, 0Fh
0x18000a14c  mov     [rsp+58h+var_30], edi
0x18000a150  mov     [rsp+58h+var_38], rsi
0x18000a155  call    WPP_SF_sqd
0x18000a15a  mov     eax, edi
0x18000a15c  add     rsp, 30h
0x18000a160  pop     r14
0x18000a162  pop     rdi
0x18000a163  pop     rsi
0x18000a164  pop     rbp
0x18000a165  pop     rbx
0x18000a166  retn
```
