# I8xPutBytePolled

- ea: `0x1400059c0`
- end: `0x140005dcb`
- name: `I8xPutBytePolled`
- size: `1035`
- prototype: ``
- caller_count: `11`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140005830`
- `0x1400059c0`
- `0x140005de0`
- `0x14000b72c`
- `0x14000bb00`
- `0x14000d8c0`
- `0x14001a19c`
- `0x14001b574`
- `0x14001b750`
- `0x14001d8b0`
- `0x14001eea0`

## callees

- `0x140004530`
- `0x140005440`
- `0x1400059c0`
- `0x140006170`
- `0x1400066d0`
- `0x140007b10`
- `0x14000daa0`

## import_xrefs

- `HAL!KeStallExecutionProcessor` at `0x140005a62`
- `HAL!KeStallExecutionProcessor` at `0x140005a62`

## pseudocode

```c
__int64 __fastcall I8xPutBytePolled(char a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // r12d
  unsigned __int8 v5; // bp
  char v6; // r14
  unsigned int BytePolled; // ebx
  __int64 *v9; // rcx
  unsigned int v10; // esi
  __int64 v11; // r13
  __int64 v12; // rdi
  unsigned int v13; // ebx
  int v14; // edx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // [rsp+28h] [rbp-60h]
  char v23; // [rsp+A0h] [rbp+18h] BYREF

  v4 = (unsigned __int8)a4;
  v5 = a3;
  v6 = a2;
  v23 = 0;
  BytePolled = 0;
  v9 = WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      a2,
      0x13u,
      0x3Du,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  if ( v5 == 2 )
  {
    LOBYTE(a4) = -44;
    LOBYTE(a3) = 3;
    LOBYTE(v9) = 1;
    I8xPutBytePolled(v9, 0, a3, a4);
  }
  v10 = 0;
  v11 = *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 208LL);
  v12 = *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 216LL);
LABEL_6:
  if ( v10 < *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 70LL) )
  {
    v13 = 0;
    if ( !*(_WORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL) )
      goto LABEL_14;
    do
    {
      if ( ((*(__int64 (__fastcall **)(__int64))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(v12) & 2) == 0 )
        break;
      KeStallExecutionProcessor(*(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 78LL));
      ++v13;
    }
    while ( v13 < *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL) );
    if ( !v13 )
      goto LABEL_14;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dd(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        18,
        62,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
        *(_WORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 78LL),
        v13);
    if ( v13 >= *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          (__int64)&WPP_RECORDER_INITIALIZED,
          0x14u,
          0x3Fu,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
      BytePolled = -1073741643;
    }
    else
    {
LABEL_14:
      I8xDrainOutputBuffer(v11, v12);
      if ( a1 == 1 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v22) = v4;
          WPP_RECORDER_SF_D(
            (__int64)WPP_GLOBAL_Control->DeviceExtension,
            v14,
            0x14u,
            0x40u,
            (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
            v22);
        }
        v15 = v12;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v22) = v4;
          WPP_RECORDER_SF_D(
            (__int64)WPP_GLOBAL_Control->DeviceExtension,
            v14,
            0x14u,
            0x41u,
            (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
            v22);
        }
        v15 = v11;
      }
      ((void (__fastcall *)(__int64, _QWORD))WPP_MAIN_CB.Queue.Wcb.DeviceObject)(v15, (unsigned __int8)v4);
      if ( v6 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            (__int64)WPP_GLOBAL_Control->DeviceExtension,
            v16,
            0x12u,
            0x42u,
            (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
        while ( 1 )
        {
          BytePolled = I8xGetBytePolled(v5, &v23);
          if ( BytePolled )
            break;
          if ( v23 == -6 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_(
                (__int64)WPP_GLOBAL_Control->DeviceExtension,
                (__int64)&WPP_RECORDER_INITIALIZED,
                0x12u,
                0x43u,
                (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
            break;
          }
          if ( v23 == -2 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_(
                (__int64)WPP_GLOBAL_Control->DeviceExtension,
                v18,
                0x12u,
                0x44u,
                (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
            if ( v5 == 2 )
            {
              LOBYTE(v21) = -44;
              LOBYTE(v20) = 3;
              LOBYTE(v19) = 1;
              I8xPutBytePolled(v19, 0, v20, v21);
            }
            ++v10;
            goto LABEL_6;
          }
        }
      }
      else
      {
        BytePolled = 0;
      }
    }
  }
  if ( v10 >= *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 70LL) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        (__int64)&WPP_RECORDER_INITIALIZED,
        0x15u,
        0x45u,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
    BytePolled = -1073741643;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      (__int64)&WPP_RECORDER_INITIALIZED,
      0x13u,
      0x46u,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  return BytePolled;
}

```

## disassembly

```asm
0x1400059c0  push    rbx
0x1400059c2  push    rbp
0x1400059c3  push    rsi
0x1400059c4  push    rdi
0x1400059c5  push    r12
0x1400059c7  push    r13
0x1400059c9  push    r14
0x1400059cb  push    r15
0x1400059cd  sub     rsp, 48h
0x1400059d1  movzx   r12d, r9b
0x1400059d5  movzx   ebp, r8b
0x1400059d9  movzx   r14d, dl
0x1400059dd  mov     [rsp+88h+arg_10], 0
0x1400059e5  movzx   r15d, cl
0x1400059e9  xor     ebx, ebx
0x1400059eb  lea     rax, WPP_RECORDER_INITIALIZED
0x1400059f2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400059f9  lea     rcx, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140005a00  jnz     loc_140005BB4
0x140005a06  cmp     bpl, 2
0x140005a0a  jz      loc_140005C1F
0x140005a10  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140005a17  xor     esi, esi
0x140005a19  mov     r13, [rax+0D0h]
0x140005a20  mov     rdi, [rax+0D8h]
0x140005a27  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140005a2e  movzx   eax, word ptr [rcx+46h]
0x140005a32  cmp     esi, eax
0x140005a34  jnb     loc_140005AED
0x140005a3a  xor     ebx, ebx
0x140005a3c  xor     eax, eax
0x140005a3e  cmp     ax, [rcx+48h]
0x140005a42  jnb     short loc_140005AAA
0x140005a44  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140005a4b  mov     rcx, rdi
0x140005a4e  call    _guard_dispatch_icall
0x140005a53  test    al, 2
0x140005a55  jz      short loc_140005A7F
0x140005a57  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140005a5e  movzx   ecx, word ptr [rax+4Eh]; MicroSeconds
0x140005a62  call    cs:__imp_KeStallExecutionProcessor
0x140005a69  nop     dword ptr [rax+rax+00h]
0x140005a6e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140005a75  inc     ebx
0x140005a77  movzx   ecx, word ptr [rax+48h]
0x140005a7b  cmp     ebx, ecx
0x140005a7d  jb      short loc_140005A44
0x140005a7f  test    ebx, ebx
0x140005a81  jz      short loc_140005AAA
0x140005a83  lea     rdx, WPP_RECORDER_INITIALIZED
0x140005a8a  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140005a91  jnz     loc_140005C33
0x140005a97  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140005a9e  movzx   ecx, word ptr [rax+48h]
0x140005aa2  cmp     ebx, ecx
0x140005aa4  jnb     loc_140005CD9
0x140005aaa  mov     rdx, rdi
0x140005aad  mov     rcx, r13
0x140005ab0  call    I8xDrainOutputBuffer
0x140005ab5  cmp     r15b, 1
0x140005ab9  jnz     loc_140005BDA
0x140005abf  lea     rbx, WPP_RECORDER_INITIALIZED
0x140005ac6  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140005acd  jnz     loc_140005C7A
0x140005ad3  mov     rcx, rdi
0x140005ad6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140005add  movzx   edx, r12b
0x140005ae1  call    _guard_dispatch_icall
0x140005ae6  test    r14b, r14b
0x140005ae9  jnz     short loc_140005B28
0x140005aeb  xor     ebx, ebx
0x140005aed  lea     rdx, WPP_RECORDER_INITIALIZED
0x140005af4  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140005afb  movzx   ecx, word ptr [rax+46h]
0x140005aff  cmp     esi, ecx
0x140005b01  jnb     loc_140005D5C
0x140005b07  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140005b0e  jnz     loc_140005D9E
0x140005b14  mov     eax, ebx
0x140005b16  add     rsp, 48h
0x140005b1a  pop     r15
0x140005b1c  pop     r14
0x140005b1e  pop     r13
0x140005b20  pop     r12
0x140005b22  pop     rdi
0x140005b23  pop     rsi
0x140005b24  pop     rbp
0x140005b25  pop     rbx
0x140005b26  retn
0x140005b28  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140005b2f  jnz     loc_140005CAC
0x140005b35  lea     rdx, [rsp+88h+arg_10]
0x140005b3d  movzx   ecx, bpl
0x140005b41  call    I8xGetBytePolled
0x140005b46  mov     ebx, eax
0x140005b48  test    eax, eax
0x140005b4a  jnz     short loc_140005AED
0x140005b4c  movzx   eax, [rsp+88h+arg_10]
0x140005b54  cmp     al, 0FAh
0x140005b56  jz      loc_140005D1B
0x140005b5c  cmp     al, 0FEh
0x140005b5e  jnz     short loc_140005B35
0x140005b60  lea     rax, WPP_RECORDER_INITIALIZED
0x140005b67  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140005b6e  jz      short loc_140005B98
0x140005b70  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b77  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140005b7e  mov     r9d, 44h ; 'D'
0x140005b84  mov     [rsp+88h+var_68], rax
0x140005b89  mov     r8d, 12h
0x140005b8f  mov     rcx, [rcx+40h]
0x140005b93  call    WPP_RECORDER_SF_
0x140005b98  cmp     bpl, 2
0x140005b9c  jnz     short loc_140005BAD
0x140005b9e  mov     r9b, 0D4h
0x140005ba1  mov     r8b, 3
0x140005ba4  xor     edx, edx
0x140005ba6  mov     cl, 1
0x140005ba8  call    I8xPutBytePolled
0x140005bad  inc     esi
0x140005baf  jmp     loc_140005A27
0x140005bb4  mov     [rsp+88h+var_68], rcx
0x140005bb9  mov     r9d, 3Dh ; '='
0x140005bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140005bc6  mov     r8d, 13h
0x140005bcc  mov     rcx, [rcx+40h]
0x140005bd0  call    WPP_RECORDER_SF_
0x140005bd5  jmp     loc_140005A06
0x140005bda  lea     rbx, WPP_RECORDER_INITIALIZED
0x140005be1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140005be8  jz      short loc_140005C17
0x140005bea  mov     rcx, cs:WPP_GLOBAL_Control
0x140005bf1  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140005bf8  mov     r9d, 41h ; 'A'
0x140005bfe  mov     dword ptr [rsp+88h+var_60], r12d
0x140005c03  mov     r8d, 14h
0x140005c09  mov     [rsp+88h+var_68], rax
0x140005c0e  mov     rcx, [rcx+40h]
0x140005c12  call    WPP_RECORDER_SF_D
0x140005c17  mov     rcx, r13
0x140005c1a  jmp     loc_140005AD6
0x140005c1f  mov     r9b, 0D4h
0x140005c22  mov     r8b, 3
0x140005c25  xor     edx, edx
0x140005c27  mov     cl, 1
0x140005c29  call    I8xPutBytePolled
0x140005c2e  jmp     loc_140005A10
0x140005c33  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140005c3a  mov     r9d, 3Eh ; '>'
0x140005c40  mov     [rsp+88h+var_58], ebx
0x140005c44  mov     r8d, 12h
0x140005c4a  movzx   ecx, word ptr [rax+4Eh]
0x140005c4e  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140005c55  mov     dword ptr [rsp+88h+var_60], ecx
0x140005c59  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c60  mov     [rsp+88h+var_68], rax
0x140005c65  mov     rcx, [rcx+40h]
0x140005c69  call    WPP_RECORDER_SF_dd
0x140005c6e  lea     rdx, WPP_RECORDER_INITIALIZED
0x140005c75  jmp     loc_140005A97
0x140005c7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c81  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140005c88  mov     r9d, 40h ; '@'
0x140005c8e  mov     dword ptr [rsp+88h+var_60], r12d
0x140005c93  mov     r8d, 14h
0x140005c99  mov     [rsp+88h+var_68], rax
0x140005c9e  mov     rcx, [rcx+40h]
0x140005ca2  call    WPP_RECORDER_SF_D
0x140005ca7  jmp     loc_140005AD3
0x140005cac  mov     rcx, cs:WPP_GLOBAL_Control
0x140005cb3  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140005cba  mov     r9d, 42h ; 'B'
0x140005cc0  mov     [rsp+88h+var_68], rax
0x140005cc5  mov     r8d, 12h
0x140005ccb  mov     rcx, [rcx+40h]
0x140005ccf  call    WPP_RECORDER_SF_
0x140005cd4  jmp     loc_140005B35
0x140005cd9  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140005ce0  jz      short loc_140005D11
0x140005ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ce9  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140005cf0  mov     r9d, 3Fh ; '?'
0x140005cf6  mov     [rsp+88h+var_68], rax
0x140005cfb  mov     r8d, 14h
0x140005d01  mov     rcx, [rcx+40h]
0x140005d05  call    WPP_RECORDER_SF_
0x140005d0a  lea     rdx, WPP_RECORDER_INITIALIZED
0x140005d11  mov     ebx, 0C00000B5h
0x140005d16  jmp     loc_140005AF4
0x140005d1b  lea     rdx, WPP_RECORDER_INITIALIZED
0x140005d22  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140005d29  jz      loc_140005AF4
0x140005d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d36  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140005d3d  mov     r9d, 43h ; 'C'
0x140005d43  mov     [rsp+88h+var_68], rax
0x140005d48  mov     r8d, 12h
0x140005d4e  mov     rcx, [rcx+40h]
0x140005d52  call    WPP_RECORDER_SF_
0x140005d57  jmp     loc_140005AED
0x140005d5c  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140005d63  jz      short loc_140005D94
0x140005d65  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d6c  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140005d73  mov     r9d, 45h ; 'E'
0x140005d79  mov     [rsp+88h+var_68], rax
0x140005d7e  mov     r8d, 15h
0x140005d84  mov     rcx, [rcx+40h]
0x140005d88  call    WPP_RECORDER_SF_
0x140005d8d  lea     rdx, WPP_RECORDER_INITIALIZED
0x140005d94  mov     ebx, 0C00000B5h
0x140005d99  jmp     loc_140005B07
0x140005d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005da5  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140005dac  mov     r9d, 46h ; 'F'
0x140005db2  mov     [rsp+88h+var_68], rax
0x140005db7  mov     r8d, 13h
0x140005dbd  mov     rcx, [rcx+40h]
0x140005dc1  call    WPP_RECORDER_SF_
0x140005dc6  jmp     loc_140005B14
```
