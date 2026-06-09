# RfcommDispatchFdoControl

- ea: `0x140002ac8`
- end: `0x140002e18`
- name: `RfcommDispatchFdoControl`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000256c`

## callees

- `0x140001800`
- `0x140001958`
- `0x140002ac8`
- `0x140003074`
- `0x140003cb4`
- `0x140003ed4`
- `0x140004a68`
- `0x140004b4c`
- `0x14000aba8`
- `0x140019cd0`
- `0x14001ea34`
- `0x140032cf8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002bf2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002cb1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002bf2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002cb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002cd9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002cd9`

## string_xrefs

- `0x140002d64`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`
- `0x140002db5`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`
- `0x140002b4b`: `OpenFirewall`

## pseudocode

```c
__int64 __fastcall RfcommDispatchFdoControl(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // rdi
  __int64 v5; // r15
  unsigned int v6; // esi
  __int64 v7; // rbx
  __int64 v8; // r14
  int v9; // eax
  int v10; // edx
  __int64 v11; // rdx
  int v12; // r9d
  KIRQL v13; // bl
  __int64 v14; // r14
  __int64 v15; // r8
  KIRQL v16; // bl
  __int64 v17; // rax
  int v18; // edx
  __int64 v19; // rdi

  v4 = *(_QWORD *)(a1 + 64);
  v5 = *(_QWORD *)(*(_QWORD *)(v4 + 96) + 16LL);
  if ( !v5 )
    return (unsigned int)-1073741811;
  v7 = *(_QWORD *)(a2 + 184);
  if ( *(_DWORD *)(v7 + 24) != 1180092 && *(_DWORD *)(v7 + 24) != 1180096 )
    return (unsigned int)-1073741637;
  if ( *(_DWORD *)(v7 + 16) != 17 || (v8 = *(_QWORD *)(a2 + 24)) == 0 )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    v12 = 62;
    goto LABEL_39;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_SLDid(WPP_GLOBAL_Control->DeviceExtension, (unsigned int)L"CloseFirewall", *(_DWORD *)(v7 + 24), a4);
  v9 = RfcommValidateFirewallRequest(v8);
  v6 = v9;
  if ( v9 >= 0 )
  {
    v11 = *(_QWORD *)(v7 + 48);
    if ( *(_DWORD *)(v7 + 24) == 1180092 )
    {
      v6 = RfcommAddFirewallEntry(v4, v11, v8);
      if ( (v6 & 0x80000000) != 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v6;
        v12 = 65;
LABEL_39:
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          19,
          v12,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          v6);
        return v6;
      }
      v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 48));
      v14 = RfcommApplyActionOnConnObjLocked(v5, v8, 1);
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 48), v13);
      if ( !v14 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v6;
        v12 = 66;
        goto LABEL_39;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          19,
          67,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          v14,
          *(_DWORD *)(v14 + 24) - 1);
      v15 = 1403;
    }
    else
    {
      v6 = RfcommRemoveFirewallEntry(v4, v11, v8);
      if ( (v6 & 0x80000000) != 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v6;
        v12 = 68;
        goto LABEL_39;
      }
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 48));
      v14 = RfcommApplyActionOnConnObjLocked(v5, v8, 2);
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 48), v16);
      if ( !v14 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v6;
        v12 = 69;
        goto LABEL_39;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          19,
          70,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          v14);
      v17 = TdiReferenceChannelLocked(v14, 1313754947);
      v19 = v17;
      if ( v17 )
      {
        ChannelDisconnectRequest(v17, 2);
        RefObj_ReleaseEx(v19 + 24, 1313754947, 1440, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          19,
          71,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          v14,
          *(_DWORD *)(v14 + 24) - 1);
      v15 = 1444;
    }
    RefObj_ReleaseEx(v14 + 24, 541672532, v15, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
    return v6;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      19,
      64,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      v9);
  return v6;
}

```

## disassembly

```asm
0x140002ac8  push    rbx
0x140002aca  push    rbp
0x140002acb  push    rsi
0x140002acc  push    rdi
0x140002acd  push    r14
0x140002acf  push    r15
0x140002ad1  sub     rsp, 58h
0x140002ad5  mov     rdi, [rcx+40h]
0x140002ad9  mov     rax, [rdi+60h]
0x140002add  mov     r15, [rax+10h]
0x140002ae1  test    r15, r15
0x140002ae4  jnz     short loc_140002AF0
0x140002ae6  mov     esi, 0C000000Dh
0x140002aeb  jmp     loc_140002E08
0x140002af0  mov     rbx, [rdx+0B8h]
0x140002af7  mov     r8d, [rbx+18h]
0x140002afb  mov     eax, r8d
0x140002afe  sub     eax, 1201BCh
0x140002b03  jz      short loc_140002B14
0x140002b05  cmp     eax, 4
0x140002b08  jz      short loc_140002B14
0x140002b0a  mov     esi, 0C00000BBh
0x140002b0f  jmp     loc_140002E08
0x140002b14  cmp     dword ptr [rbx+10h], 11h
0x140002b18  jnz     loc_140002DC7
0x140002b1e  mov     r14, [rdx+18h]
0x140002b22  test    r14, r14
0x140002b25  jz      loc_140002DC7
0x140002b2b  lea     rbp, WPP_RECORDER_INITIALIZED
0x140002b32  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002b39  jz      short loc_140002B8A
0x140002b3b  movzx   eax, byte ptr [r14+10h]
0x140002b40  lea     rdx, aClosefirewall; "CloseFirewall"
0x140002b47  mov     [rsp+88h+var_40], eax
0x140002b4b  lea     rcx, aOpenfirewall; "OpenFirewall"
0x140002b52  mov     rax, [r14+8]
0x140002b56  cmp     r8d, 1201BCh
0x140002b5d  mov     [rsp+88h+var_48], rax
0x140002b62  mov     eax, [r14+4]
0x140002b66  cmovnz  rcx, rdx
0x140002b6a  mov     [rsp+88h+var_50], eax
0x140002b6e  mov     eax, [r14]
0x140002b71  mov     [rsp+88h+var_58], eax
0x140002b75  mov     [rsp+88h+var_60], rcx
0x140002b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b81  mov     rcx, [rcx+40h]
0x140002b85  call    WPP_RECORDER_SF_SLDid
0x140002b8a  mov     rcx, r14
0x140002b8d  call    RfcommValidateFirewallRequest
0x140002b92  mov     esi, eax
0x140002b94  test    eax, eax
0x140002b96  jns     short loc_140002BB4
0x140002b98  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002b9f  jz      loc_140002E08
0x140002ba5  mov     r9d, 40h ; '@'
0x140002bab  mov     dword ptr [rsp+88h+var_60], eax
0x140002baf  jmp     loc_140002DE6
0x140002bb4  cmp     dword ptr [rbx+18h], 1201BCh
0x140002bbb  mov     r8, r14
0x140002bbe  mov     rdx, [rbx+30h]
0x140002bc2  mov     rcx, rdi
0x140002bc5  jnz     loc_140002C8A
0x140002bcb  call    RfcommAddFirewallEntry
0x140002bd0  mov     esi, eax
0x140002bd2  test    eax, eax
0x140002bd4  jns     short loc_140002BEE
0x140002bd6  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002bdd  jz      loc_140002E08
0x140002be3  mov     r9d, 41h ; 'A'
0x140002be9  jmp     loc_140002DE2
0x140002bee  lea     rcx, [r15+30h]; SpinLock
0x140002bf2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002bf9  nop     dword ptr [rax+rax+00h]
0x140002bfe  mov     r8d, 1
0x140002c04  mov     rdx, r14
0x140002c07  mov     rcx, r15
0x140002c0a  mov     bl, al
0x140002c0c  call    RfcommApplyActionOnConnObjLocked
0x140002c11  mov     dl, bl; NewIrql
0x140002c13  lea     rcx, [r15+30h]; SpinLock
0x140002c17  mov     r14, rax
0x140002c1a  call    cs:__imp_KeReleaseSpinLock
0x140002c21  nop     dword ptr [rax+rax+00h]
0x140002c26  test    r14, r14
0x140002c29  jnz     short loc_140002C41
0x140002c2b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002c32  jz      loc_140002E08
0x140002c38  lea     r9d, [r14+42h]
0x140002c3c  jmp     loc_140002DE2
0x140002c41  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002c48  jz      short loc_140002C7F
0x140002c4a  mov     eax, [r14+18h]
0x140002c4e  lea     rbx, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140002c55  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c5c  mov     r9d, 43h ; 'C'
0x140002c62  dec     eax
0x140002c64  mov     [rsp+88h+var_58], eax
0x140002c68  mov     [rsp+88h+var_60], r14
0x140002c6d  mov     rcx, [rcx+40h]
0x140002c71  lea     r8d, [r9-30h]
0x140002c75  mov     [rsp+88h+var_68], rbx
0x140002c7a  call    WPP_RECORDER_SF_qD
0x140002c7f  mov     r8d, 57Bh
0x140002c85  jmp     loc_140002DB0
0x140002c8a  call    RfcommRemoveFirewallEntry
0x140002c8f  mov     esi, eax
0x140002c91  test    eax, eax
0x140002c93  jns     short loc_140002CAD
0x140002c95  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002c9c  jz      loc_140002E08
0x140002ca2  mov     r9d, 44h ; 'D'
0x140002ca8  jmp     loc_140002DE2
0x140002cad  lea     rcx, [r15+30h]; SpinLock
0x140002cb1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002cb8  nop     dword ptr [rax+rax+00h]
0x140002cbd  mov     r8d, 2
0x140002cc3  mov     rdx, r14
0x140002cc6  mov     rcx, r15
0x140002cc9  mov     bl, al
0x140002ccb  call    RfcommApplyActionOnConnObjLocked
0x140002cd0  mov     dl, bl; NewIrql
0x140002cd2  lea     rcx, [r15+30h]; SpinLock
0x140002cd6  mov     r14, rax
0x140002cd9  call    cs:__imp_KeReleaseSpinLock
0x140002ce0  nop     dword ptr [rax+rax+00h]
0x140002ce5  test    r14, r14
0x140002ce8  jnz     short loc_140002D00
0x140002cea  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002cf1  jz      loc_140002E08
0x140002cf7  lea     r9d, [r14+45h]
0x140002cfb  jmp     loc_140002DE2
0x140002d00  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002d07  lea     rbx, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140002d0e  jz      short loc_140002D34
0x140002d10  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d17  mov     r9d, 46h ; 'F'
0x140002d1d  mov     [rsp+88h+var_60], r14
0x140002d22  mov     [rsp+88h+var_68], rbx
0x140002d27  mov     rcx, [rcx+40h]
0x140002d2b  lea     r8d, [r9-33h]
0x140002d2f  call    WPP_RECORDER_SF_q
0x140002d34  mov     r15d, 4E4E4F43h
0x140002d3a  mov     rcx, r14
0x140002d3d  mov     edx, r15d
0x140002d40  call    TdiReferenceChannelLocked
0x140002d45  mov     rdi, rax
0x140002d48  test    rax, rax
0x140002d4b  jz      short loc_140002D73
0x140002d4d  mov     edx, 2
0x140002d52  mov     rcx, rax
0x140002d55  call    ChannelDisconnectRequest
0x140002d5a  lea     rcx, [rdi+18h]
0x140002d5e  mov     r8d, 5A0h
0x140002d64  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140002d6b  mov     edx, r15d
0x140002d6e  call    RefObj_ReleaseEx
0x140002d73  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002d7a  jz      short loc_140002DAA
0x140002d7c  mov     eax, [r14+18h]
0x140002d80  mov     r9d, 47h ; 'G'
0x140002d86  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d8d  dec     eax
0x140002d8f  mov     [rsp+88h+var_58], eax
0x140002d93  mov     [rsp+88h+var_60], r14
0x140002d98  lea     r8d, [r9-34h]
0x140002d9c  mov     [rsp+88h+var_68], rbx
0x140002da1  mov     rcx, [rcx+40h]
0x140002da5  call    WPP_RECORDER_SF_qD
0x140002daa  mov     r8d, 5A4h
0x140002db0  mov     edx, 20494454h
0x140002db5  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140002dbc  lea     rcx, [r14+18h]
0x140002dc0  call    RefObj_ReleaseEx
0x140002dc5  jmp     short loc_140002E08
0x140002dc7  mov     esi, 0C000000Dh
0x140002dcc  lea     rbp, WPP_RECORDER_INITIALIZED
0x140002dd3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002dda  jz      short loc_140002E08
0x140002ddc  mov     r9d, 3Eh ; '>'
0x140002de2  mov     dword ptr [rsp+88h+var_60], esi
0x140002de6  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ded  lea     rbx, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140002df4  mov     r8d, 13h
0x140002dfa  mov     [rsp+88h+var_68], rbx
0x140002dff  mov     rcx, [rcx+40h]
0x140002e03  call    WPP_RECORDER_SF_d
0x140002e08  mov     eax, esi
0x140002e0a  add     rsp, 58h
0x140002e0e  pop     r15
0x140002e10  pop     r14
0x140002e12  pop     rdi
0x140002e13  pop     rsi
0x140002e14  pop     rbp
0x140002e15  pop     rbx
0x140002e16  retn
```
