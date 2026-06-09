# MRxSmbFinishNTCreateAndX

- ea: `0x140038ad0`
- end: `0x140038d4c`
- name: `MRxSmbFinishNTCreateAndX`
- size: `636`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x1400106d4`
- `0x140038ad0`
- `0x1400499e0`
- `0x140052f50`

## import_xrefs

- `rdbss!RxInferFileType` at `0x140038b8b`
- `rdbss!RxInferFileType` at `0x140038b8b`

## pseudocode

```c
__int64 __fastcall MRxSmbFinishNTCreateAndX(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  __int64 v6; // rsi
  __int64 v7; // r15
  __int64 v8; // r13
  __int64 v9; // rbx
  unsigned int FileSuccessTail; // ebx
  unsigned __int16 v11; // ax
  __int64 v12; // rax
  unsigned __int16 v13; // r10
  struct _RX_CONTEXT *v14; // rcx
  int v15; // r11d
  int v16; // eax
  unsigned __int16 v18; // [rsp+A0h] [rbp+8h]

  v3 = *(_QWORD *)(a1 + 24);
  v6 = *(_QWORD *)(v3 + 72);
  v7 = *(_QWORD *)(v3 + 56);
  if ( v6 )
    v8 = *(_QWORD *)(v6 + 48);
  else
    v8 = 0;
  v9 = *(_QWORD *)(a1 + 80);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  if ( *(_BYTE *)a2 == 42 && *(_DWORD *)(a1 + 1456) < 0x87u )
  {
    FileSuccessTail = -1073741629;
    v11 = 0;
    *(_DWORD *)(a1 + 48) = -1073741629;
  }
  else
  {
    if ( (*(_DWORD *)(v9 + 420) & 0x100000) != 0 && (*(_DWORD *)(v3 + 540) & 0x1000) != 0 )
    {
      if ( v7 )
        v12 = *(_QWORD *)(v7 + 136);
      else
        v12 = 0;
      *(_DWORD *)(v12 + 4) |= 1u;
    }
    if ( RxInferFileType((PRX_CONTEXT)v3) == FileTypeNotYetKnown
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        51,
        WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
        2 - (unsigned int)(*(_BYTE *)(a2 + 68) != 0));
    }
    v13 = *(_WORD *)(a2 + 6);
    *(_DWORD *)(v8 + 72) = *(_DWORD *)(a2 + 44);
    *(_DWORD *)(v8 + 96) = 1;
    *(_DWORD *)(v8 + 40) = *(_DWORD *)(a2 + 12);
    *(_DWORD *)(v8 + 44) = *(_DWORD *)(a2 + 16);
    *(_DWORD *)(v8 + 48) = *(_DWORD *)(a2 + 20);
    *(_DWORD *)(v8 + 52) = *(_DWORD *)(a2 + 24);
    *(_DWORD *)(v8 + 56) = *(_DWORD *)(a2 + 28);
    *(_DWORD *)(v8 + 60) = *(_DWORD *)(a2 + 32);
    *(_DWORD *)(v8 + 64) = *(_DWORD *)(a2 + 36);
    *(_DWORD *)(v8 + 68) = *(_DWORD *)(a2 + 40);
    *(_DWORD *)(v8 + 80) = *(_DWORD *)(a2 + 48);
    *(_DWORD *)(v8 + 84) = *(_DWORD *)(a2 + 52);
    *(_DWORD *)(v8 + 88) = *(_DWORD *)(a2 + 56);
    *(_DWORD *)(v8 + 92) = *(_DWORD *)(a2 + 60);
    *(_BYTE *)(v8 + 101) = *(_BYTE *)(a2 + 68);
    v18 = v13;
    MRxSmbCopyAndTranslatePipeState(v3, *(unsigned __int16 *)(a2 + 66));
    if ( *(_BYTE *)a2 == 42 )
    {
      *(_DWORD *)(v6 + 152) = *(_DWORD *)(a2 + 93);
      v16 = *(_DWORD *)(a2 + 97);
    }
    else
    {
      *(_DWORD *)(v6 + 152) = 2032127;
      v16 = 0;
    }
    *(_DWORD *)(v6 + 156) = v16;
    if ( *(_BYTE *)(a2 + 5) )
    {
      *(_WORD *)(v8 + 152) = *(_WORD *)(a2 + 66);
      *(_BYTE *)(v8 + 154) = 1;
    }
    *(_DWORD *)(v6 + 72) &= ~0x100000u;
    FileSuccessTail = MRxSmbCreateFileSuccessTail(v14, *(_DWORD *)(a1 + 52), *(_BYTE *)(a2 + 5), v15, v8 + 40);
    v11 = v18;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_LDDDqD(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      a3,
      FileSuccessTail,
      *(_DWORD *)(v7 + 156),
      *(_DWORD *)(v7 + 164),
      *(_DWORD *)(v7 + 160),
      v6,
      v11);
  return FileSuccessTail;
}

```

## disassembly

```asm
0x140038ad0  push    rbx
0x140038ad2  push    rbp
0x140038ad3  push    rsi
0x140038ad4  push    rdi
0x140038ad5  push    r12
0x140038ad7  push    r13
0x140038ad9  push    r14
0x140038adb  push    r15
0x140038add  sub     rsp, 58h
0x140038ae1  mov     rbp, [rcx+18h]
0x140038ae5  mov     rdi, rdx
0x140038ae8  mov     r14, rcx
0x140038aeb  mov     rsi, [rbp+48h]
0x140038aef  mov     r15, [rbp+38h]
0x140038af3  test    rsi, rsi
0x140038af6  jnz     short loc_140038AFD
0x140038af8  xor     r13d, r13d
0x140038afb  jmp     short loc_140038B01
0x140038afd  mov     r13, [rsi+30h]
0x140038b01  mov     rbx, [rcx+50h]
0x140038b05  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140038b0c  lea     rax, WPP_GLOBAL_Control
0x140038b13  cmp     rcx, rax
0x140038b16  jz      short loc_140038B36
0x140038b18  test    dword ptr [rcx+2Ch], 400h
0x140038b1f  jz      short loc_140038B36
0x140038b21  mov     rcx, [rcx+18h]
0x140038b25  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140038b2c  mov     edx, 32h ; '2'
0x140038b31  call    WPP_SF_
0x140038b36  cmp     byte ptr [rdi], 2Ah ; '*'
0x140038b39  jnz     short loc_140038B58
0x140038b3b  cmp     dword ptr [r14+5B0h], 87h
0x140038b46  jnb     short loc_140038B58
0x140038b48  mov     ebx, 0C00000C3h
0x140038b4d  xor     eax, eax
0x140038b4f  mov     [r14+30h], ebx
0x140038b53  jmp     loc_140038CE3
0x140038b58  test    dword ptr [rbx+1A4h], 100000h
0x140038b62  lea     r12, [r13+28h]
0x140038b66  jz      short loc_140038B88
0x140038b68  test    dword ptr [rbp+21Ch], 1000h
0x140038b72  jz      short loc_140038B88
0x140038b74  test    r15, r15
0x140038b77  jnz     short loc_140038B7D
0x140038b79  xor     eax, eax
0x140038b7b  jmp     short loc_140038B84
0x140038b7d  mov     rax, [r15+88h]
0x140038b84  or      dword ptr [rax+4], 1
0x140038b88  mov     rcx, rbp; RxContext
0x140038b8b  call    cs:__imp_RxInferFileType
0x140038b92  nop     dword ptr [rax+rax+00h]
0x140038b97  mov     ebx, eax
0x140038b99  test    eax, eax
0x140038b9b  jnz     short loc_140038BDB
0x140038b9d  mov     al, [rdi+44h]
0x140038ba0  neg     al
0x140038ba2  sbb     ebx, ebx
0x140038ba4  add     ebx, 2
0x140038ba7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140038bae  lea     rax, WPP_GLOBAL_Control
0x140038bb5  cmp     rcx, rax
0x140038bb8  jz      short loc_140038BDB
0x140038bba  test    dword ptr [rcx+2Ch], 400h
0x140038bc1  jz      short loc_140038BDB
0x140038bc3  mov     rcx, [rcx+18h]
0x140038bc7  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140038bce  mov     edx, 33h ; '3'
0x140038bd3  mov     r9d, ebx
0x140038bd6  call    WPP_SF_d
0x140038bdb  movzx   r10d, word ptr [rdi+6]
0x140038be0  mov     rcx, rbp
0x140038be3  mov     eax, [rdi+2Ch]
0x140038be6  mov     r11d, [rdi+8]
0x140038bea  mov     [r12+20h], eax
0x140038bef  mov     dword ptr [r12+38h], 1
0x140038bf8  mov     eax, [rdi+0Ch]
0x140038bfb  mov     [r12], eax
0x140038bff  mov     eax, [rdi+10h]
0x140038c02  mov     [r12+4], eax
0x140038c07  mov     eax, [rdi+14h]
0x140038c0a  mov     [r12+8], eax
0x140038c0f  mov     eax, [rdi+18h]
0x140038c12  mov     [r12+0Ch], eax
0x140038c17  mov     eax, [rdi+1Ch]
0x140038c1a  mov     [r12+10h], eax
0x140038c1f  mov     eax, [rdi+20h]
0x140038c22  mov     [r12+14h], eax
0x140038c27  mov     eax, [rdi+24h]
0x140038c2a  mov     [r12+18h], eax
0x140038c2f  mov     eax, [rdi+28h]
0x140038c32  mov     [r12+1Ch], eax
0x140038c37  mov     eax, [rdi+30h]
0x140038c3a  mov     [r12+28h], eax
0x140038c3f  mov     eax, [rdi+34h]
0x140038c42  mov     [r12+2Ch], eax
0x140038c47  mov     eax, [rdi+38h]
0x140038c4a  mov     [r12+30h], eax
0x140038c4f  mov     eax, [rdi+3Ch]
0x140038c52  mov     [r12+34h], eax
0x140038c57  mov     al, [rdi+44h]
0x140038c5a  mov     [r12+3Dh], al
0x140038c5f  movzx   edx, word ptr [rdi+42h]
0x140038c63  mov     word ptr [rsp+98h+arg_0], r10w
0x140038c6c  call    MRxSmbCopyAndTranslatePipeState
0x140038c71  cmp     byte ptr [rdi], 2Ah ; '*'
0x140038c74  jnz     short loc_140038C84
0x140038c76  mov     eax, [rdi+5Dh]
0x140038c79  mov     [rsi+98h], eax
0x140038c7f  mov     eax, [rdi+61h]
0x140038c82  jmp     short loc_140038C90
0x140038c84  mov     dword ptr [rsi+98h], 1F01FFh
0x140038c8e  xor     eax, eax
0x140038c90  mov     [rsi+9Ch], eax
0x140038c96  cmp     byte ptr [rdi+5], 0
0x140038c9a  jbe     short loc_140038CB0
0x140038c9c  movzx   eax, word ptr [rdi+42h]
0x140038ca0  mov     [r13+98h], ax
0x140038ca8  mov     byte ptr [r13+9Ah], 1
0x140038cb0  btr     dword ptr [rsi+48h], 14h
0x140038cb5  movzx   r9d, r10w
0x140038cb9  mov     al, [rdi+5]
0x140038cbc  mov     r8d, ebx
0x140038cbf  mov     [rsp+98h+var_60], r12; __int64
0x140038cc4  mov     [rsp+98h+var_68], r11d; int
0x140038cc9  mov     [rsp+98h+var_70], al; char
0x140038ccd  mov     eax, [r14+34h]
0x140038cd1  mov     [rsp+98h+var_78], eax; int
0x140038cd5  call    MRxSmbCreateFileSuccessTail
0x140038cda  mov     ebx, eax
0x140038cdc  mov     eax, [rsp+98h+arg_0]
0x140038ce3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140038cea  lea     rdx, WPP_GLOBAL_Control
0x140038cf1  cmp     rcx, rdx
0x140038cf4  jz      short loc_140038D38
0x140038cf6  test    dword ptr [rcx+2Ch], 400h
0x140038cfd  jz      short loc_140038D38
0x140038cff  mov     rcx, [rcx+18h]
0x140038d03  mov     r9d, ebx
0x140038d06  movzx   edx, ax
0x140038d09  mov     eax, [r15+0A0h]
0x140038d10  mov     [rsp+98h+var_58], edx
0x140038d14  mov     [rsp+98h+var_60], rsi
0x140038d19  mov     [rsp+98h+var_68], eax
0x140038d1d  mov     eax, [r15+0A4h]
0x140038d24  mov     dword ptr [rsp+98h+var_70], eax
0x140038d28  mov     eax, [r15+9Ch]
0x140038d2f  mov     [rsp+98h+var_78], eax
0x140038d33  call    WPP_SF_LDDDqD
0x140038d38  mov     eax, ebx
0x140038d3a  add     rsp, 58h
0x140038d3e  pop     r15
0x140038d40  pop     r14
0x140038d42  pop     r13
0x140038d44  pop     r12
0x140038d46  pop     rdi
0x140038d47  pop     rsi
0x140038d48  pop     rbp
0x140038d49  pop     rbx
0x140038d4a  retn
```
