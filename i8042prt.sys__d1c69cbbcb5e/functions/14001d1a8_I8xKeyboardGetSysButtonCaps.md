# I8xKeyboardGetSysButtonCaps

- ea: `0x14001d1a8`
- end: `0x14001d2f3`
- name: `I8xKeyboardGetSysButtonCaps`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140020210`

## callees

- `0x140004530`
- `0x14001d1a8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001d2d7`
- `ntoskrnl!IofCompleteRequest` at `0x14001d2d7`

## pseudocode

```c
__int64 __fastcall I8xKeyboardGetSysButtonCaps(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rbp
  char v6; // al
  int v7; // ebx

  if ( *(_DWORD *)(*(_QWORD *)(a2 + 184) + 8LL) >= 4u )
  {
    v6 = *(_BYTE *)(a1 + 584);
    v7 = 1;
    if ( (v6 & 1) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          10,
          12,
          (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
        v6 = *(_BYTE *)(a1 + 584);
      }
    }
    else
    {
      v7 = 0;
    }
    if ( (v6 & 2) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          10,
          13,
          (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
        v6 = *(_BYTE *)(a1 + 584);
      }
      v7 |= 2u;
    }
    if ( (v6 & 4) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          10,
          14,
          (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
      v7 |= 0x80000000;
    }
    **(_DWORD **)(a2 + 24) = v7;
    v4 = 0;
    v5 = 4;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        25,
        11,
        (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
    v4 = -1073741306;
    v5 = 0;
  }
  *(_QWORD *)(a2 + 56) = v5;
  *(_DWORD *)(a2 + 48) = v4;
  IofCompleteRequest((PIRP)a2, 0);
  return v4;
}

```

## disassembly

```asm
0x14001d1a8  push    rbx
0x14001d1aa  push    rbp
0x14001d1ab  push    rsi
0x14001d1ac  push    rdi
0x14001d1ad  push    r14
0x14001d1af  push    r15
0x14001d1b1  sub     rsp, 38h
0x14001d1b5  mov     rax, [rdx+0B8h]
0x14001d1bc  mov     rdi, rdx
0x14001d1bf  mov     r15, rcx
0x14001d1c2  cmp     dword ptr [rax+8], 4
0x14001d1c6  jnb     short loc_14001D20A
0x14001d1c8  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001d1cf  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001d1d6  jz      short loc_14001D1FE
0x14001d1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d1df  lea     r14, WPP_9a74d45702a83a61696de9b252942f2f_Traceguids
0x14001d1e6  mov     r9d, 0Bh
0x14001d1ec  mov     [rsp+68h+var_48], r14
0x14001d1f1  mov     rcx, [rcx+40h]
0x14001d1f5  lea     r8d, [r9+0Eh]
0x14001d1f9  call    WPP_RECORDER_SF_
0x14001d1fe  mov     ebx, 0C0000206h
0x14001d203  xor     ebp, ebp
0x14001d205  jmp     loc_14001D2CB
0x14001d20a  mov     al, [rcx+248h]
0x14001d210  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001d217  xor     ebp, ebp
0x14001d219  lea     r14, WPP_9a74d45702a83a61696de9b252942f2f_Traceguids
0x14001d220  lea     ebx, [rbp+1]
0x14001d223  test    bl, al
0x14001d225  jz      short loc_14001D256
0x14001d227  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001d22e  jz      short loc_14001D258
0x14001d230  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d237  lea     r9d, [rbp+0Ch]
0x14001d23b  lea     r8d, [rbp+0Ah]
0x14001d23f  mov     [rsp+68h+var_48], r14
0x14001d244  mov     rcx, [rcx+40h]
0x14001d248  call    WPP_RECORDER_SF_
0x14001d24d  mov     al, [r15+248h]
0x14001d254  jmp     short loc_14001D258
0x14001d256  mov     ebx, ebp
0x14001d258  test    al, 2
0x14001d25a  jz      short loc_14001D28E
0x14001d25c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001d263  jz      short loc_14001D28B
0x14001d265  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d26c  mov     r9d, 0Dh
0x14001d272  mov     [rsp+68h+var_48], r14
0x14001d277  mov     rcx, [rcx+40h]
0x14001d27b  lea     r8d, [r9-3]
0x14001d27f  call    WPP_RECORDER_SF_
0x14001d284  mov     al, [r15+248h]
0x14001d28b  or      ebx, 2
0x14001d28e  test    al, 4
0x14001d290  jz      short loc_14001D2BE
0x14001d292  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001d299  jz      short loc_14001D2BA
0x14001d29b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d2a2  mov     r9d, 0Eh
0x14001d2a8  mov     [rsp+68h+var_48], r14
0x14001d2ad  mov     rcx, [rcx+40h]
0x14001d2b1  lea     r8d, [r9-4]
0x14001d2b5  call    WPP_RECORDER_SF_
0x14001d2ba  bts     ebx, 1Fh
0x14001d2be  mov     rax, [rdi+18h]
0x14001d2c2  mov     [rax], ebx
0x14001d2c4  mov     ebx, ebp
0x14001d2c6  mov     ebp, 4
0x14001d2cb  xor     edx, edx; PriorityBoost
0x14001d2cd  mov     [rdi+38h], rbp
0x14001d2d1  mov     rcx, rdi; Irp
0x14001d2d4  mov     [rdi+30h], ebx
0x14001d2d7  call    cs:__imp_IofCompleteRequest
0x14001d2de  nop     dword ptr [rax+rax+00h]
0x14001d2e3  mov     eax, ebx
0x14001d2e5  add     rsp, 38h
0x14001d2e9  pop     r15
0x14001d2eb  pop     r14
0x14001d2ed  pop     rdi
0x14001d2ee  pop     rsi
0x14001d2ef  pop     rbp
0x14001d2f0  pop     rbx
0x14001d2f1  retn
```
