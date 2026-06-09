# ChannelDisconnectRequest

- ea: `0x140019cd0`
- end: `0x140019e56`
- name: `ChannelDisconnectRequest`
- size: `390`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000280c`
- `0x140002ac8`
- `0x140008ac0`
- `0x14001190c`
- `0x14001291c`
- `0x140015c4c`
- `0x140018d08`

## callees

- `0x140003bf4`
- `0x140005050`
- `0x1400105ec`
- `0x1400149b4`
- `0x1400197ec`
- `0x140019cd0`
- `0x14001a164`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019cf0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019cf0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019d61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019ddd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019d61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019ddd`

## pseudocode

```c
__int64 __fastcall ChannelDisconnectRequest(__int64 a1, int a2)
{
  __int64 v2; // rbp
  const char *v5; // rax
  __int64 v6; // rdx
  int v7; // edx
  char v8; // di
  char v10; // si
  __int64 v11; // rdx
  __int64 v12; // rdx

  v2 = *(_QWORD *)(a1 + 56);
  *(_BYTE *)(v2 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 56));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v5 = ChannelStateTxt(*(_DWORD *)(a1 + 48));
    WPP_RECORDER_SF_qs(WPP_GLOBAL_Control->DeviceExtension, v6, 3, 24, v6, a1, (__int64)v5);
  }
  v7 = *(_DWORD *)(a1 + 48);
  v8 = 1;
  *(_BYTE *)(a1 + 186) = 1;
  if ( v7 == 9 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 56), *(_BYTE *)(v2 + 64));
    return 0;
  }
  v10 = 0;
  if ( v7 == 4 || v7 == 5 || (unsigned int)(v7 - 6) <= 1 )
  {
    if ( *(_QWORD *)(a1 + 104) == a1 + 104 && *(_QWORD *)(a1 + 120) == a1 + 120 || a2 == 2 )
    {
      ChannelSetState(a1, 8);
      v10 = 1;
LABEL_17:
      v8 = 0;
      goto LABEL_18;
    }
    if ( v7 == 4 )
    {
      v11 = 6;
    }
    else
    {
      if ( (unsigned int)(v7 - 6) <= 1 )
        goto LABEL_17;
      v11 = 7;
    }
    ChannelSetState(a1, v11);
    goto LABEL_17;
  }
LABEL_18:
  KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 56), *(_BYTE *)(v2 + 64));
  if ( v10 && (int)RfcommSendDISC(v2, a1) < 0 || v8 )
    ChannelDisconnect(a1, 0xC000013B, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v12,
      3u,
      0x19u,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids);
  return 259;
}

```

## disassembly

```asm
0x140019cd0  push    rbx
0x140019cd2  push    rbp
0x140019cd3  push    rsi
0x140019cd4  push    rdi
0x140019cd5  push    r12
0x140019cd7  push    r14
0x140019cd9  push    r15
0x140019cdb  sub     rsp, 40h
0x140019cdf  mov     rbp, [rcx+38h]
0x140019ce3  mov     rbx, rcx
0x140019ce6  mov     r15d, edx
0x140019ce9  lea     r14, [rbp+38h]
0x140019ced  mov     rcx, r14; SpinLock
0x140019cf0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019cf7  nop     dword ptr [rax+rax+00h]
0x140019cfc  mov     [rbp+40h], al
0x140019cff  lea     r12, WPP_RECORDER_INITIALIZED
0x140019d06  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140019d0d  lea     rdx, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x140019d14  jz      short loc_140019D47
0x140019d16  mov     ecx, [rbx+30h]
0x140019d19  call    ChannelStateTxt
0x140019d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019d25  mov     r9d, 18h
0x140019d2b  mov     [rsp+78h+var_48], rax
0x140019d30  mov     [rsp+78h+var_50], rbx
0x140019d35  mov     [rsp+78h+var_58], rdx
0x140019d3a  mov     rcx, [rcx+40h]
0x140019d3e  lea     r8d, [r9-15h]
0x140019d42  call    WPP_RECORDER_SF_qs
0x140019d47  mov     edx, [rbx+30h]
0x140019d4a  mov     edi, 1
0x140019d4f  mov     [rbx+0BAh], dil
0x140019d56  cmp     edx, 9
0x140019d59  jnz     short loc_140019D74
0x140019d5b  mov     dl, [rbp+40h]; NewIrql
0x140019d5e  mov     rcx, r14; SpinLock
0x140019d61  call    cs:__imp_KeReleaseSpinLock
0x140019d68  nop     dword ptr [rax+rax+00h]
0x140019d6d  xor     eax, eax
0x140019d6f  jmp     loc_140019E46
0x140019d74  xor     sil, sil
0x140019d77  mov     ecx, edx
0x140019d79  sub     ecx, 4
0x140019d7c  jz      short loc_140019D8A
0x140019d7e  sub     ecx, edi
0x140019d80  jz      short loc_140019D8A
0x140019d82  sub     ecx, edi
0x140019d84  jz      short loc_140019D8A
0x140019d86  cmp     ecx, edi
0x140019d88  jnz     short loc_140019DD7
0x140019d8a  lea     rax, [rbx+68h]
0x140019d8e  cmp     [rax], rax
0x140019d91  jnz     short loc_140019D9C
0x140019d93  lea     rax, [rbx+78h]
0x140019d97  cmp     [rax], rax
0x140019d9a  jz      short loc_140019DA2
0x140019d9c  cmp     r15d, 2
0x140019da0  jnz     short loc_140019DB4
0x140019da2  mov     edx, 8
0x140019da7  mov     rcx, rbx
0x140019daa  call    ChannelSetState
0x140019daf  mov     sil, dil
0x140019db2  jmp     short loc_140019DD4
0x140019db4  cmp     edx, 4
0x140019db7  jnz     short loc_140019DC0
0x140019db9  mov     edx, 6
0x140019dbe  jmp     short loc_140019DCC
0x140019dc0  lea     eax, [rdx-6]
0x140019dc3  cmp     eax, edi
0x140019dc5  jbe     short loc_140019DD4
0x140019dc7  mov     edx, 7
0x140019dcc  mov     rcx, rbx
0x140019dcf  call    ChannelSetState
0x140019dd4  xor     dil, dil
0x140019dd7  mov     dl, [rbp+40h]; NewIrql
0x140019dda  mov     rcx, r14; SpinLock
0x140019ddd  call    cs:__imp_KeReleaseSpinLock
0x140019de4  nop     dword ptr [rax+rax+00h]
0x140019de9  test    sil, sil
0x140019dec  jz      short loc_140019DFD
0x140019dee  mov     rdx, rbx
0x140019df1  mov     rcx, rbp
0x140019df4  call    RfcommSendDISC
0x140019df9  test    eax, eax
0x140019dfb  js      short loc_140019E02
0x140019dfd  test    dil, dil
0x140019e00  jz      short loc_140019E12
0x140019e02  xor     r8d, r8d
0x140019e05  mov     edx, 0C000013Bh
0x140019e0a  mov     rcx, rbx
0x140019e0d  call    ChannelDisconnect
0x140019e12  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140019e19  jz      short loc_140019E41
0x140019e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140019e22  lea     rax, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x140019e29  mov     r9d, 19h
0x140019e2f  mov     [rsp+78h+var_58], rax
0x140019e34  mov     rcx, [rcx+40h]
0x140019e38  lea     r8d, [r9-16h]
0x140019e3c  call    WPP_RECORDER_SF_
0x140019e41  mov     eax, 103h
0x140019e46  add     rsp, 40h
0x140019e4a  pop     r15
0x140019e4c  pop     r14
0x140019e4e  pop     r12
0x140019e50  pop     rdi
0x140019e51  pop     rsi
0x140019e52  pop     rbp
0x140019e53  pop     rbx
0x140019e54  retn
```
