# DafCreateDeviceChallengeContext

- ea: `0x180009aa0`
- end: `0x180009e0c`
- name: `DafCreateDeviceChallengeContext`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009e20`

## callees

- `0x18000178c`
- `0x1800017fc`
- `0x180002f10`
- `0x180009a00`
- `0x180009aa0`
- `0x18000bbc2`
- `0x18000bbf0`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180009cbc`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180009d2b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180009cbc`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180009d2b`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180009bd0`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180009c0f`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180009c3f`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180009bd0`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180009c0f`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180009c3f`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180009d02`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180009d02`

## pseudocode

```c
__int64 __fastcall DafCreateDeviceChallengeContext(_WORD *a1, struct _DAC_CLIENT_CONTEXT **a2)
{
  _WORD *v4; // r8
  unsigned int ChallengeContext; // ebx
  __int64 v6; // rax
  __int64 v7; // rdx
  _WORD *v8; // rcx
  int i; // edi
  __int64 Property; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  _WORD *v14; // rax
  __int64 v15; // rdx
  _WORD *v16; // rcx
  int ObjectProperties; // eax
  __int64 v19; // [rsp+48h] [rbp-B8h]
  _BYTE v20[400]; // [rsp+50h] [rbp-B0h] BYREF

  if ( dword_180015A58 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180015A58);
    if ( dword_180015A58 == -1 )
    {
      *(DEVPROPKEY *)byte_1800159A0 = DEVPKEY_Device_InLocalMachineContainer;
      *(DEVPROPKEY *)byte_1800159C0 = DEVPKEY_Device_Parent;
      dword_1800159B4 = 0;
      qword_1800159B8 = 0;
      xmmword_1800159E0 = DEVPKEY_Aep_AepId;
      dword_1800159D4 = 0;
      qword_1800159D8 = 0;
      dword_1800159F0 = 8;
      dword_1800159F4 = 0;
      qword_1800159F8 = 0;
      Init_thread_footer(&dword_180015A58);
    }
  }
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_303e45e916c7361cf38ffe655d6c194e_Traceguids);
  if ( a1 )
  {
    v6 = 2147483646;
    v4 = v20;
    v7 = 200;
    do
    {
      if ( !v6 )
        break;
      if ( !*a1 )
        break;
      *v4++ = *a1++;
      --v6;
      --v7;
    }
    while ( v7 );
    v8 = v4 - 1;
    ChallengeContext = v7 == 0 ? 0x8007007A : 0;
    if ( v7 )
      v8 = v4;
    *v8 = 0;
    if ( v7 )
    {
      for ( i = 0; ; i = 1 )
      {
        ObjectProperties = DevGetObjectProperties(3, v20, 0);
        ChallengeContext = ObjectProperties;
        if ( ObjectProperties < 0 )
          break;
        Property = DevFindProperty(&DEVPKEY_Device_InLocalMachineContainer, 0, 0, 0, v19);
        if ( Property
          && *(_DWORD *)(Property + 32) == 17
          && *(_DWORD *)(Property + 36)
          && **(_BYTE **)(Property + 40) == 0xFF )
        {
          goto LABEL_34;
        }
        v11 = DevFindProperty(&DEVPKEY_Aep_AepId, 0, 0, 0, v19);
        if ( v11 && *(_DWORD *)(v11 + 32) == 18 )
        {
          ChallengeContext = DafCreateChallengeContext(*(_QWORD *)(v11 + 40), a2);
          goto LABEL_35;
        }
        v12 = DevFindProperty(&DEVPKEY_Device_Parent, 0, 0, 0, v19);
        if ( !v12 || *(_DWORD *)(v12 + 32) != 18 )
          goto LABEL_34;
        v4 = *(_WORD **)(v12 + 40);
        v13 = 2147483646;
        v14 = v20;
        v15 = 200;
        do
        {
          if ( !v13 )
            break;
          if ( !*v4 )
            break;
          *v14++ = *v4++;
          --v13;
          --v15;
        }
        while ( v15 );
        v16 = v14 - 1;
        if ( v15 )
          v16 = v14;
        *v16 = 0;
        ChallengeContext = v15 == 0 ? 0x8007007A : 0;
        if ( !v15 )
          goto LABEL_35;
        DevFreeObjectProperties(0, v19, v4);
        v19 = 0;
      }
      if ( ObjectProperties == -2147024894 && i )
LABEL_34:
        ChallengeContext = -2140930037;
    }
  }
  else
  {
    ChallengeContext = -2147024809;
  }
LABEL_35:
  DevFreeObjectProperties(0, v19, v4);
  return ChallengeContext;
}

```

## disassembly

```asm
0x180009aa0  mov     [rsp-8+arg_0], rbx
0x180009aa5  mov     [rsp-8+arg_10], rsi
0x180009aaa  push    rbp
0x180009aab  push    rdi
0x180009aac  push    r14
0x180009aae  lea     rbp, [rsp-0F0h]
0x180009ab6  sub     rsp, 1F0h
0x180009abd  mov     rax, cs:__security_cookie
0x180009ac4  xor     rax, rsp
0x180009ac7  mov     [rbp+100h+var_20], rax
0x180009ace  mov     rax, gs:58h
0x180009ad7  mov     rbx, rcx
0x180009ada  mov     ecx, cs:_tls_index
0x180009ae0  mov     rsi, rdx
0x180009ae3  mov     edx, 4
0x180009ae8  xor     r14d, r14d
0x180009aeb  mov     rax, [rax+rcx*8]
0x180009aef  mov     eax, [rdx+rax]
0x180009af2  cmp     cs:dword_180015A58, eax
0x180009af8  jg      loc_180009D6A
0x180009afe  xor     edx, edx; Val
0x180009b00  mov     [rsp+200h+var_1C0], r14d
0x180009b05  mov     r8d, 190h; Size
0x180009b0b  mov     [rsp+200h+var_1B8], r14
0x180009b10  lea     rcx, [rsp+200h+var_1B0]; void *
0x180009b15  call    memset_0
0x180009b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b21  lea     rax, WPP_GLOBAL_Control
0x180009b28  cmp     rcx, rax
0x180009b2b  jz      short loc_180009B48
0x180009b2d  cmp     byte ptr [rcx+19h], 4
0x180009b31  jb      short loc_180009B48
0x180009b33  mov     rcx, [rcx+10h]
0x180009b37  lea     r8, WPP_303e45e916c7361cf38ffe655d6c194e_Traceguids
0x180009b3e  mov     edx, 0Ch
0x180009b43  call    WPP_SF_s
0x180009b48  test    rbx, rbx
0x180009b4b  jnz     short loc_180009B57
0x180009b4d  mov     ebx, 80070057h
0x180009b52  jmp     loc_180009D22
0x180009b57  mov     eax, 7FFFFFFEh
0x180009b5c  lea     r8, [rsp+200h+var_1B0]
0x180009b61  mov     edx, 0C8h
0x180009b66  test    rax, rax
0x180009b69  jz      short loc_180009B88
0x180009b6b  movzx   ecx, word ptr [rbx]
0x180009b6e  test    cx, cx
0x180009b71  jz      short loc_180009B88
0x180009b73  mov     [r8], cx
0x180009b77  add     rbx, 2
0x180009b7b  add     r8, 2
0x180009b7f  dec     rax
0x180009b82  sub     rdx, 1
0x180009b86  jnz     short loc_180009B66
0x180009b88  mov     rax, rdx
0x180009b8b  lea     rcx, [r8-2]
0x180009b8f  neg     rax
0x180009b92  sbb     ebx, ebx
0x180009b94  not     ebx
0x180009b96  and     ebx, 8007007Ah
0x180009b9c  test    rdx, rdx
0x180009b9f  cmovnz  rcx, r8
0x180009ba3  mov     [rcx], r14w
0x180009ba7  jz      loc_180009D22
0x180009bad  mov     edi, r14d
0x180009bb0  jmp     loc_180009CD1
0x180009bb5  mov     rax, [rsp+200h+var_1B8]
0x180009bba  lea     rcx, DEVPKEY_Device_InLocalMachineContainer
0x180009bc1  mov     r9d, [rsp+200h+var_1C0]
0x180009bc6  xor     r8d, r8d
0x180009bc9  xor     edx, edx
0x180009bcb  mov     [rsp+200h+var_1E0], rax
0x180009bd0  call    cs:__imp_DevFindProperty
0x180009bd6  test    rax, rax
0x180009bd9  jz      short loc_180009BF4
0x180009bdb  cmp     dword ptr [rax+20h], 11h
0x180009bdf  jnz     short loc_180009BF4
0x180009be1  cmp     dword ptr [rax+24h], 1
0x180009be5  jb      short loc_180009BF4
0x180009be7  mov     rax, [rax+28h]
0x180009beb  cmp     byte ptr [rax], 0FFh
0x180009bee  jz      loc_180009D1D
0x180009bf4  mov     rax, [rsp+200h+var_1B8]
0x180009bf9  lea     rcx, DEVPKEY_Aep_AepId
0x180009c00  mov     r9d, [rsp+200h+var_1C0]
0x180009c05  xor     r8d, r8d
0x180009c08  xor     edx, edx
0x180009c0a  mov     [rsp+200h+var_1E0], rax
0x180009c0f  call    cs:__imp_DevFindProperty
0x180009c15  test    rax, rax
0x180009c18  jz      short loc_180009C24
0x180009c1a  cmp     dword ptr [rax+20h], 12h
0x180009c1e  jz      loc_180009D5A
0x180009c24  mov     rax, [rsp+200h+var_1B8]
0x180009c29  lea     rcx, DEVPKEY_Device_Parent
0x180009c30  mov     r9d, [rsp+200h+var_1C0]
0x180009c35  xor     r8d, r8d
0x180009c38  xor     edx, edx
0x180009c3a  mov     [rsp+200h+var_1E0], rax
0x180009c3f  call    cs:__imp_DevFindProperty
0x180009c45  test    rax, rax
0x180009c48  jz      loc_180009D1D
0x180009c4e  cmp     dword ptr [rax+20h], 12h
0x180009c52  jnz     loc_180009D1D
0x180009c58  mov     r8, [rax+28h]
0x180009c5c  mov     ecx, 7FFFFFFEh
0x180009c61  lea     rax, [rsp+200h+var_1B0]
0x180009c66  mov     edx, 0C8h
0x180009c6b  test    rcx, rcx
0x180009c6e  jz      short loc_180009C8F
0x180009c70  movzx   r9d, word ptr [r8]
0x180009c74  test    r9w, r9w
0x180009c78  jz      short loc_180009C8F
0x180009c7a  mov     [rax], r9w
0x180009c7e  add     r8, 2
0x180009c82  add     rax, 2
0x180009c86  dec     rcx
0x180009c89  sub     rdx, 1
0x180009c8d  jnz     short loc_180009C6B
0x180009c8f  test    rdx, rdx
0x180009c92  lea     rcx, [rax-2]
0x180009c96  cmovnz  rcx, rax
0x180009c9a  mov     rax, rdx
0x180009c9d  neg     rax
0x180009ca0  sbb     ebx, ebx
0x180009ca2  not     ebx
0x180009ca4  mov     [rcx], r14w
0x180009ca8  and     ebx, 8007007Ah
0x180009cae  test    rdx, rdx
0x180009cb1  jz      short loc_180009D22
0x180009cb3  mov     rdx, [rsp+200h+var_1B8]
0x180009cb8  mov     ecx, [rsp+200h+var_1C0]
0x180009cbc  call    cs:__imp_DevFreeObjectProperties
0x180009cc2  mov     [rsp+200h+var_1C0], r14d
0x180009cc7  mov     edi, 1
0x180009ccc  mov     [rsp+200h+var_1B8], r14
0x180009cd1  lea     rax, [rsp+200h+var_1B8]
0x180009cd6  mov     r9d, 3
0x180009cdc  mov     [rsp+200h+var_1D0], rax
0x180009ce1  lea     rdx, [rsp+200h+var_1B0]
0x180009ce6  lea     rax, [rsp+200h+var_1C0]
0x180009ceb  xor     r8d, r8d
0x180009cee  mov     [rsp+200h+var_1D8], rax
0x180009cf3  mov     ecx, r9d
0x180009cf6  lea     rax, byte_1800159A0
0x180009cfd  mov     [rsp+200h+var_1E0], rax
0x180009d02  call    cs:__imp_DevGetObjectProperties
0x180009d08  mov     ebx, eax
0x180009d0a  test    eax, eax
0x180009d0c  jns     loc_180009BB5
0x180009d12  cmp     eax, 80070002h
0x180009d17  jnz     short loc_180009D22
0x180009d19  test    edi, edi
0x180009d1b  jz      short loc_180009D22
0x180009d1d  mov     ebx, 8064000Bh
0x180009d22  mov     rdx, [rsp+200h+var_1B8]
0x180009d27  mov     ecx, [rsp+200h+var_1C0]
0x180009d2b  call    cs:__imp_DevFreeObjectProperties
0x180009d31  mov     eax, ebx
0x180009d33  mov     rcx, [rbp+100h+var_20]
0x180009d3a  xor     rcx, rsp; StackCookie
0x180009d3d  call    __security_check_cookie
0x180009d42  lea     r11, [rsp+200h+var_10]
0x180009d4a  mov     rbx, [r11+20h]
0x180009d4e  mov     rsi, [r11+30h]
0x180009d52  mov     rsp, r11
0x180009d55  pop     r14
0x180009d57  pop     rdi
0x180009d58  pop     rbp
0x180009d59  retn
0x180009d5a  mov     rcx, [rax+28h]
0x180009d5e  mov     rdx, rsi
0x180009d61  call    DafCreateChallengeContext
0x180009d66  mov     ebx, eax
0x180009d68  jmp     short loc_180009D22
0x180009d6a  lea     rcx, dword_180015A58
0x180009d71  call    _Init_thread_header
0x180009d76  cmp     cs:dword_180015A58, 0FFFFFFFFh
0x180009d7d  jnz     loc_180009AFE
0x180009d83  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InLocalMachineContainer.fmtid.Data1
0x180009d8a  mov     eax, cs:DEVPKEY_Device_InLocalMachineContainer.pid
0x180009d90  lea     rcx, dword_180015A58
0x180009d97  mov     dword ptr cs:byte_1800159A0+10h, eax
0x180009d9d  mov     eax, cs:DEVPKEY_Device_Parent.pid
0x180009da3  movaps  xmmword ptr cs:byte_1800159A0, xmm0
0x180009daa  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_Parent.fmtid.Data1
0x180009db1  mov     dword ptr cs:byte_1800159C0+10h, eax
0x180009db7  mov     eax, cs:dword_180010550
0x180009dbd  movaps  xmmword ptr cs:byte_1800159C0, xmm0
0x180009dc4  movups  xmm0, cs:DEVPKEY_Aep_AepId
0x180009dcb  mov     cs:dword_1800159B4, r14d
0x180009dd2  mov     cs:qword_1800159B8, r14
0x180009dd9  movaps  cs:xmmword_1800159E0, xmm0
0x180009de0  mov     cs:dword_1800159D4, r14d
0x180009de7  mov     cs:qword_1800159D8, r14
0x180009dee  mov     cs:dword_1800159F0, eax
0x180009df4  mov     cs:dword_1800159F4, r14d
0x180009dfb  mov     cs:qword_1800159F8, r14
0x180009e02  call    _Init_thread_footer
0x180009e07  jmp     loc_180009AFE
```
