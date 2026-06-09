# RfcommGetNextCmdLocked

- ea: `0x140013bf8`
- end: `0x140013d17`
- name: `RfcommGetNextCmdLocked`
- size: `287`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011050`
- `0x1400149b4`
- `0x140014c64`
- `0x140014eb4`
- `0x14001513c`
- `0x1400152ec`
- `0x14001552c`

## callees

- `0x140004a68`
- `0x140004e58`
- `0x140013bf8`
- `0x14001e74c`

## string_xrefs

- `0x140013ccf`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
_QWORD *__fastcall RfcommGetNextCmdLocked(__int64 a1, __int64 a2)
{
  _QWORD **v2; // rax
  _QWORD *v3; // rdi
  volatile __int32 *v4; // rsi
  _QWORD *v5; // rbx
  __int64 v6; // rax
  _QWORD *v7; // rcx

  if ( a2 )
  {
    v2 = (_QWORD **)(a2 + 152);
    v3 = (_QWORD *)(a2 + 136);
    v4 = (volatile __int32 *)(a2 + 144);
  }
  else
  {
    v2 = (_QWORD **)(a1 + 192);
    v3 = (_QWORD *)(a1 + 176);
    v4 = (volatile __int32 *)(a1 + 184);
  }
  v5 = *v2;
  if ( *v2 == v2 )
    return 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      16,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      *v3,
      (char)v5);
  if ( *v3 )
    return 0;
  *v3 = v5;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      17,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v5);
  v6 = *v5;
  if ( *(_QWORD **)(*v5 + 8LL) != v5 || (v7 = (_QWORD *)v5[1], (_QWORD *)*v7 != v5) )
    __fastfail(3u);
  *v7 = v6;
  *(_QWORD *)(v6 + 8) = v7;
  v5[1] = v5;
  *v5 = v5;
  RefObj_AddRefEx(v5 + 3, 1346917442, 710, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  _InterlockedExchange(v4, 60);
  return v5;
}

```

## disassembly

```asm
0x140013bf8  push    rbx
0x140013bfa  push    rsi
0x140013bfb  push    rdi
0x140013bfc  push    r14
0x140013bfe  push    r15
0x140013c00  sub     rsp, 40h
0x140013c04  test    rdx, rdx
0x140013c07  jz      short loc_140013C20
0x140013c09  lea     rax, [rdx+98h]
0x140013c10  lea     rdi, [rdx+88h]
0x140013c17  lea     rsi, [rdx+90h]
0x140013c1e  jmp     short loc_140013C35
0x140013c20  lea     rax, [rcx+0C0h]
0x140013c27  lea     rdi, [rcx+0B0h]
0x140013c2e  lea     rsi, [rcx+0B8h]
0x140013c35  mov     rbx, [rax]
0x140013c38  cmp     rbx, rax
0x140013c3b  jz      loc_140013D05
0x140013c41  lea     r14, WPP_RECORDER_INITIALIZED
0x140013c48  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140013c4f  lea     r15, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140013c56  jz      short loc_140013C84
0x140013c58  mov     rcx, cs:WPP_GLOBAL_Control
0x140013c5f  mov     r9d, 10h
0x140013c65  mov     rax, [rdi]
0x140013c68  mov     [rsp+68h+var_38], rbx
0x140013c6d  mov     [rsp+68h+var_40], rax
0x140013c72  mov     rcx, [rcx+40h]
0x140013c76  lea     r8d, [r9-0Dh]
0x140013c7a  mov     [rsp+68h+var_48], r15
0x140013c7f  call    WPP_RECORDER_SF_qq
0x140013c84  cmp     qword ptr [rdi], 0
0x140013c88  jnz     short loc_140013D05
0x140013c8a  mov     [rdi], rbx
0x140013c8d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140013c94  jz      short loc_140013CBA
0x140013c96  mov     rcx, cs:WPP_GLOBAL_Control
0x140013c9d  mov     r9d, 11h
0x140013ca3  mov     [rsp+68h+var_40], rbx
0x140013ca8  mov     [rsp+68h+var_48], r15
0x140013cad  mov     rcx, [rcx+40h]
0x140013cb1  lea     r8d, [r9-0Eh]
0x140013cb5  call    WPP_RECORDER_SF_q
0x140013cba  mov     rax, [rbx]
0x140013cbd  cmp     [rax+8], rbx
0x140013cc1  jnz     short loc_140013CFE
0x140013cc3  mov     rcx, [rbx+8]
0x140013cc7  cmp     [rcx], rbx
0x140013cca  jnz     short loc_140013CFE
0x140013ccc  mov     [rcx], rax
0x140013ccf  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140013cd6  mov     [rax+8], rcx
0x140013cda  mov     edx, 50485442h
0x140013cdf  lea     rcx, [rbx+18h]
0x140013ce3  mov     [rbx+8], rbx
0x140013ce7  mov     r8d, 2C6h
0x140013ced  mov     [rbx], rbx
0x140013cf0  call    RefObj_AddRefEx
0x140013cf5  mov     eax, 3Ch ; '<'
0x140013cfa  xchg    eax, [rsi]
0x140013cfc  jmp     short loc_140013D07
0x140013cfe  mov     ecx, 3
0x140013d03  int     29h; Win8: RtlFailFast(ecx)
0x140013d05  xor     ebx, ebx
0x140013d07  mov     rax, rbx
0x140013d0a  add     rsp, 40h
0x140013d0e  pop     r15
0x140013d10  pop     r14
0x140013d12  pop     rdi
0x140013d13  pop     rsi
0x140013d14  pop     rbx
0x140013d15  retn
```
