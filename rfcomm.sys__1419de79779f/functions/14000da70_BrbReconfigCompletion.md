# BrbReconfigCompletion

- ea: `0x14000da70`
- end: `0x14000dbfa`
- name: `BrbReconfigCompletion`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14000da70`
- `0x14000f3ec`
- `0x140017ab8`
- `0x140017db4`
- `0x1400186b4`
- `0x14001ea34`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000da9b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000da9b`

## string_xrefs

- `0x14000dba1`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`

## pseudocode

```c
__int64 __fastcall BrbReconfigCompletion(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v11; // edi
  int v12; // r9d
  __int64 result; // rax
  int v14; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    KeGetCurrentIrql();
    WPP_RECORDER_SF_dqqd(WPP_GLOBAL_Control->DeviceExtension, v8, v9, v10);
  }
  if ( !a4 && !*(_DWORD *)(a2 + 28) )
  {
    SessionReconfigComplete(a3, (_OWORD *)a2);
    goto LABEL_19;
  }
  v11 = *(_DWORD *)(a2 + 28);
  if ( v11 >= 0 )
    v11 = a4;
  if ( v11 == -2147483631 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_19;
    v12 = 36;
LABEL_14:
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      2,
      v12,
      (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
    goto LABEL_19;
  }
  if ( v11 == -1073741667 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_19;
    v12 = 37;
    goto LABEL_14;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      38,
      (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids,
      v11);
  _InterlockedExchange64((volatile __int64 *)(a3 + 280), 0);
  SessionDisconnectInd(a3, 0, (unsigned int)v11);
  if ( *(_DWORD *)(a3 + 48) != 6 )
    SessionDisconnect(a3);
LABEL_19:
  RefObj_ReleaseEx(a3 + 24, 1413697091, 797, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c");
  result = (*(__int64 (__fastcall **)(__int64))(a1 + 320))(a2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_(
             WPP_GLOBAL_Control->DeviceExtension,
             v14,
             3,
             39,
             (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
  return result;
}

```

## disassembly

```asm
0x14000da70  push    rbx
0x14000da72  push    rbp
0x14000da73  push    rsi
0x14000da74  push    rdi
0x14000da75  push    r12
0x14000da77  push    r14
0x14000da79  push    r15
0x14000da7b  sub     rsp, 50h
0x14000da7f  mov     ebp, r9d
0x14000da82  mov     rbx, r8
0x14000da85  mov     rsi, rdx
0x14000da88  mov     r14, rcx
0x14000da8b  lea     r15, WPP_RECORDER_INITIALIZED
0x14000da92  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000da99  jz      short loc_14000DACC
0x14000da9b  call    cs:__imp_KeGetCurrentIrql
0x14000daa2  nop     dword ptr [rax+rax+00h]
0x14000daa7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000daae  movzx   eax, al
0x14000dab1  mov     [rsp+88h+var_48], eax
0x14000dab5  mov     [rsp+88h+var_50], rsi
0x14000daba  mov     rcx, [rcx+40h]
0x14000dabe  mov     [rsp+88h+var_58], rbx
0x14000dac3  mov     [rsp+88h+var_60], ebp
0x14000dac7  call    WPP_RECORDER_SF_dqqd
0x14000dacc  lea     r12, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000dad3  test    ebp, ebp
0x14000dad5  jnz     short loc_14000DAEC
0x14000dad7  cmp     [rsi+1Ch], ebp
0x14000dada  jnz     short loc_14000DAEC
0x14000dadc  mov     rdx, rsi
0x14000dadf  mov     rcx, rbx
0x14000dae2  call    SessionReconfigComplete
0x14000dae7  jmp     loc_14000DB98
0x14000daec  mov     edi, [rsi+1Ch]
0x14000daef  test    edi, edi
0x14000daf1  cmovns  edi, ebp
0x14000daf4  cmp     edi, 80000011h
0x14000dafa  jnz     short loc_14000DB11
0x14000dafc  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000db03  jz      loc_14000DB98
0x14000db09  mov     r9d, 24h ; '$'
0x14000db0f  jmp     short loc_14000DB28
0x14000db11  cmp     edi, 0C000009Dh
0x14000db17  jnz     short loc_14000DB45
0x14000db19  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000db20  jz      short loc_14000DB98
0x14000db22  mov     r9d, 25h ; '%'
0x14000db28  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db2f  mov     r8d, 2
0x14000db35  mov     [rsp+88h+var_68], r12
0x14000db3a  mov     rcx, [rcx+40h]
0x14000db3e  call    WPP_RECORDER_SF_
0x14000db43  jmp     short loc_14000DB98
0x14000db45  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000db4c  jz      short loc_14000DB71
0x14000db4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db55  mov     r9d, 26h ; '&'
0x14000db5b  mov     [rsp+88h+var_60], edi
0x14000db5f  mov     [rsp+88h+var_68], r12
0x14000db64  mov     rcx, [rcx+40h]
0x14000db68  lea     r8d, [r9-25h]
0x14000db6c  call    WPP_RECORDER_SF_d
0x14000db71  xor     eax, eax
0x14000db73  xor     r9d, r9d
0x14000db76  xchg    rax, [rbx+118h]
0x14000db7d  mov     r8d, edi
0x14000db80  xor     edx, edx
0x14000db82  mov     rcx, rbx
0x14000db85  call    SessionDisconnectInd
0x14000db8a  cmp     dword ptr [rbx+30h], 6
0x14000db8e  jz      short loc_14000DB98
0x14000db90  mov     rcx, rbx
0x14000db93  call    SessionDisconnect
0x14000db98  lea     rcx, [rbx+18h]
0x14000db9c  mov     edx, 54434E43h
0x14000dba1  lea     r9, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000dba8  mov     r8d, 31Dh
0x14000dbae  call    RefObj_ReleaseEx
0x14000dbb3  mov     rax, [r14+140h]
0x14000dbba  mov     rcx, rsi
0x14000dbbd  call    _guard_dispatch_icall
0x14000dbc2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000dbc9  jz      short loc_14000DBEA
0x14000dbcb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dbd2  mov     r9d, 27h ; '''
0x14000dbd8  mov     [rsp+88h+var_68], r12
0x14000dbdd  mov     rcx, [rcx+40h]
0x14000dbe1  lea     r8d, [r9-24h]
0x14000dbe5  call    WPP_RECORDER_SF_
0x14000dbea  add     rsp, 50h
0x14000dbee  pop     r15
0x14000dbf0  pop     r14
0x14000dbf2  pop     r12
0x14000dbf4  pop     rdi
0x14000dbf5  pop     rsi
0x14000dbf6  pop     rbp
0x14000dbf7  pop     rbx
0x14000dbf8  retn
```
