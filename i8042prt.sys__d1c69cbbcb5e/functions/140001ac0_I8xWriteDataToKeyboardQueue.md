# I8xWriteDataToKeyboardQueue

- ea: `0x140001ac0`
- end: `0x140001d27`
- name: `I8xWriteDataToKeyboardQueue`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400019e0`

## callees

- `0x1400014e0`
- `0x140001ac0`
- `0x140004530`
- `0x140005140`

## pseudocode

```c
char __fastcall I8xWriteDataToKeyboardQueue(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v6; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      22,
      (__int64)WPP_575c8870bf553b08b608d7700ff895e9_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        2,
        23,
        (__int64)WPP_575c8870bf553b08b608d7700ff895e9_Traceguids,
        *(_QWORD *)(a1 + 880),
        *(_QWORD *)(a1 + 888));
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          2,
          24,
          (__int64)WPP_575c8870bf553b08b608d7700ff895e9_Traceguids,
          *(_DWORD *)(a1 + 92));
    }
  }
  v4 = *(_QWORD *)(a1 + 880);
  if ( v4 == *(_QWORD *)(a1 + 888) && *(_DWORD *)(a1 + 92) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        5,
        25,
        (__int64)WPP_575c8870bf553b08b608d7700ff895e9_Traceguids);
    v6 = *(_QWORD *)(a1 + 880);
    if ( v6 == *(_QWORD *)(a1 + 872) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          2,
          26,
          (__int64)WPP_575c8870bf553b08b608d7700ff895e9_Traceguids);
      v6 = *(_QWORD *)(a1 + 896);
    }
    *(_DWORD *)(v6 - 10) = 255;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        27,
        (__int64)WPP_575c8870bf553b08b608d7700ff895e9_Traceguids);
    return 0;
  }
  else
  {
    *(_QWORD *)v4 = *(_QWORD *)a2;
    *(_DWORD *)(v4 + 8) = *(_DWORD *)(a2 + 8);
    ++*(_DWORD *)(a1 + 92);
    *(_QWORD *)(a1 + 880) += 12LL;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        4,
        28,
        (__int64)WPP_575c8870bf553b08b608d7700ff895e9_Traceguids,
        *(_DWORD *)(a1 + 92));
    if ( *(_QWORD *)(a1 + 880) == *(_QWORD *)(a1 + 896) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          2,
          29,
          (__int64)WPP_575c8870bf553b08b608d7700ff895e9_Traceguids);
      *(_QWORD *)(a1 + 880) = *(_QWORD *)(a1 + 872);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        30,
        (__int64)WPP_575c8870bf553b08b608d7700ff895e9_Traceguids);
    return 1;
  }
}

```

## disassembly

```asm
0x140001ac0  push    rbx
0x140001ac2  push    rbp
0x140001ac3  push    rsi
0x140001ac4  push    rdi
0x140001ac5  sub     rsp, 48h
0x140001ac9  mov     rdi, rdx
0x140001acc  mov     rbx, rcx
0x140001acf  lea     rsi, WPP_RECORDER_INITIALIZED
0x140001ad6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001add  lea     rbp, WPP_575c8870bf553b08b608d7700ff895e9_Traceguids
0x140001ae4  jnz     loc_140001BF9
0x140001aea  mov     rcx, [rbx+370h]
0x140001af1  cmp     rcx, [rbx+378h]
0x140001af8  jz      short loc_140001B50
0x140001afa  movsd   xmm0, qword ptr [rdi]
0x140001afe  movsd   qword ptr [rcx], xmm0
0x140001b02  mov     eax, [rdi+8]
0x140001b05  mov     [rcx+8], eax
0x140001b08  inc     dword ptr [rbx+5Ch]
0x140001b0b  add     qword ptr [rbx+370h], 0Ch
0x140001b13  mov     eax, [rbx+5Ch]
0x140001b16  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001b1d  jnz     loc_140001C9A
0x140001b23  mov     rax, [rbx+380h]
0x140001b2a  cmp     [rbx+370h], rax
0x140001b31  jz      loc_140001CC4
0x140001b37  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001b3e  jnz     loc_140001D01
0x140001b44  mov     al, 1
0x140001b46  add     rsp, 48h
0x140001b4a  pop     rdi
0x140001b4b  pop     rsi
0x140001b4c  pop     rbp
0x140001b4d  pop     rbx
0x140001b4e  retn
0x140001b50  cmp     dword ptr [rbx+5Ch], 0
0x140001b54  jz      short loc_140001AFA
0x140001b56  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001b5d  jz      short loc_140001B80
0x140001b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b66  mov     r9d, 19h
0x140001b6c  mov     r8d, 5
0x140001b72  mov     [rsp+68h+var_48], rbp
0x140001b77  mov     rcx, [rcx+40h]
0x140001b7b  call    WPP_RECORDER_SF_
0x140001b80  mov     rax, [rbx+370h]
0x140001b87  cmp     rax, [rbx+368h]
0x140001b8e  jnz     short loc_140001BC1
0x140001b90  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001b97  jz      short loc_140001BBA
0x140001b99  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ba0  mov     r9d, 1Ah
0x140001ba6  mov     r8d, 2
0x140001bac  mov     [rsp+68h+var_48], rbp
0x140001bb1  mov     rcx, [rcx+40h]
0x140001bb5  call    WPP_RECORDER_SF_
0x140001bba  mov     rax, [rbx+380h]
0x140001bc1  mov     dword ptr [rax-0Ah], 0FFh
0x140001bc8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001bcf  jz      short loc_140001BF2
0x140001bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140001bd8  mov     r9d, 1Bh
0x140001bde  mov     r8d, 3
0x140001be4  mov     [rsp+68h+var_48], rbp
0x140001be9  mov     rcx, [rcx+40h]
0x140001bed  call    WPP_RECORDER_SF_
0x140001bf2  xor     al, al
0x140001bf4  jmp     loc_140001B46
0x140001bf9  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c00  mov     r9d, 16h
0x140001c06  mov     r8d, 3
0x140001c0c  mov     [rsp+68h+var_48], rbp
0x140001c11  mov     rcx, [rcx+40h]
0x140001c15  call    WPP_RECORDER_SF_
0x140001c1a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001c21  jz      loc_140001AEA
0x140001c27  mov     rax, [rbx+378h]
0x140001c2e  mov     r9d, 17h
0x140001c34  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c3b  mov     r8d, 2
0x140001c41  mov     [rsp+68h+var_38], rax
0x140001c46  mov     rax, [rbx+370h]
0x140001c4d  mov     [rsp+68h+var_40], rax
0x140001c52  mov     rcx, [rcx+40h]
0x140001c56  mov     [rsp+68h+var_48], rbp
0x140001c5b  call    WPP_RECORDER_SF_qq
0x140001c60  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001c67  jz      loc_140001AEA
0x140001c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c74  mov     r9d, 18h
0x140001c7a  mov     eax, [rbx+5Ch]
0x140001c7d  mov     r8d, 2
0x140001c83  mov     dword ptr [rsp+68h+var_40], eax
0x140001c87  mov     [rsp+68h+var_48], rbp
0x140001c8c  mov     rcx, [rcx+40h]
0x140001c90  call    WPP_RECORDER_SF_d
0x140001c95  jmp     loc_140001AEA
0x140001c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ca1  mov     r9d, 1Ch
0x140001ca7  mov     dword ptr [rsp+68h+var_40], eax
0x140001cab  mov     r8d, 4
0x140001cb1  mov     [rsp+68h+var_48], rbp
0x140001cb6  mov     rcx, [rcx+40h]
0x140001cba  call    WPP_RECORDER_SF_d
0x140001cbf  jmp     loc_140001B23
0x140001cc4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001ccb  jz      short loc_140001CEE
0x140001ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x140001cd4  mov     r9d, 1Dh
0x140001cda  mov     r8d, 2
0x140001ce0  mov     [rsp+68h+var_48], rbp
0x140001ce5  mov     rcx, [rcx+40h]
0x140001ce9  call    WPP_RECORDER_SF_
0x140001cee  mov     rax, [rbx+368h]
0x140001cf5  mov     [rbx+370h], rax
0x140001cfc  jmp     loc_140001B37
0x140001d01  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d08  mov     r9d, 1Eh
0x140001d0e  mov     r8d, 3
0x140001d14  mov     [rsp+68h+var_48], rbp
0x140001d19  mov     rcx, [rcx+40h]
0x140001d1d  call    WPP_RECORDER_SF_
0x140001d22  jmp     loc_140001B44
```
