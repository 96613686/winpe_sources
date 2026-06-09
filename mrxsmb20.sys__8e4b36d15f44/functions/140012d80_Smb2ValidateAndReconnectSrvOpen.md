# Smb2ValidateAndReconnectSrvOpen

- ea: `0x140012d80`
- end: `0x140012eec`
- name: `Smb2ValidateAndReconnectSrvOpen`
- size: `364`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012d00`
- `0x14001cc00`
- `0x140023510`
- `0x1400236b0`
- `0x140029d70`

## callees

- `0x140012d80`
- `0x140029840`

## import_xrefs

- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140012e46`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140012e93`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140012e46`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140012e93`
- `mrxsmb!SmbCeInitiateExchange` at `0x140012e24`
- `mrxsmb!SmbCeInitiateExchange` at `0x140012eae`
- `mrxsmb!SmbCeInitiateExchange` at `0x140012e24`
- `mrxsmb!SmbCeInitiateExchange` at `0x140012eae`
- `mrxsmb!SmbCeInitializeExchange` at `0x140012df9`
- `mrxsmb!SmbCeInitializeExchange` at `0x140012df9`

## pseudocode

```c
__int64 __fastcall Smb2ValidateAndReconnectSrvOpen(__int64 a1)
{
  __int64 v1; // rbp
  unsigned int v3; // edi
  __int64 v4; // rcx
  int v5; // edx
  char v6; // si
  __int64 result; // rax
  unsigned int v8; // esi
  __int64 v9; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 72);
  v3 = *(unsigned __int8 *)(a1 + 32);
  v4 = *(_QWORD *)(*(_QWORD *)(v1 + 40) + 40LL);
  if ( ((unsigned __int8)v3 <= 0x11u && (v5 = 155672, _bittest(&v5, v3)) || (_BYTE)v3 == 12 && *(_BYTE *)(a1 + 33) == 2)
    && (*(_DWORD *)(a1 + 120) & 0x1000) != 0 )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    if ( (v3 & 0xED) == 0 && (_BYTE)v3 != 16 )
      *(_BYTE *)(a1 + 32) = 27;
  }
  v9 = 0;
  result = SmbCeInitializeExchange(&v9, a1, 0, 0, 0, v4, 1024, 0);
  if ( (int)result >= 0 )
  {
    if ( v6 )
    {
      _InterlockedOr((volatile signed __int32 *)(v9 + 68), 0x1000u);
      return SmbCeInitiateExchange(v9);
    }
    else
    {
      _InterlockedOr((volatile signed __int32 *)(v9 + 68), 0x1001u);
      v8 = SmbCeInitiateExchange(v9);
      if ( v8 == 259 )
        v8 = SmbCeWaitForCompletionAndFinalizeExchangeEx(v9, 0, 0, 0);
      else
        SmbCeWaitForCompletionAndFinalizeExchangeEx(v9, 0, 0, 0);
      *(_BYTE *)(a1 + 32) = v3;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids, v1, v8);
      }
      return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012d80  push    rbx
0x140012d82  push    rbp
0x140012d83  push    rsi
0x140012d84  push    rdi
0x140012d85  sub     rsp, 48h
0x140012d89  mov     rbp, [rcx+48h]
0x140012d8d  mov     rbx, rcx
0x140012d90  mov     rax, [rbp+28h]
0x140012d94  movzx   edi, byte ptr [rbx+20h]
0x140012d98  mov     rcx, [rax+28h]
0x140012d9c  cmp     dil, 11h
0x140012da0  ja      short loc_140012DB0
0x140012da2  mov     edx, 26018h
0x140012da7  bt      edx, edi
0x140012daa  jb      loc_140012E7E
0x140012db0  cmp     dil, 0Ch
0x140012db4  jz      loc_140012EBC
0x140012dba  xor     sil, sil
0x140012dbd  test    dil, 0EDh
0x140012dc1  jnz     short loc_140012DCD
0x140012dc3  cmp     dil, 10h
0x140012dc7  jz      short loc_140012DCD
0x140012dc9  mov     byte ptr [rbx+20h], 1Bh
0x140012dcd  xor     eax, eax
0x140012dcf  xor     r9d, r9d
0x140012dd2  mov     [rsp+68h+var_30], rax
0x140012dd7  xor     r8d, r8d
0x140012dda  mov     [rsp+68h+var_38], 400h
0x140012de2  mov     rdx, rbx
0x140012de5  mov     [rsp+68h+var_40], rcx
0x140012dea  lea     rcx, [rsp+68h+arg_0]
0x140012def  mov     [rsp+68h+arg_0], rax
0x140012df4  mov     [rsp+68h+var_48], rax
0x140012df9  call    cs:__imp_SmbCeInitializeExchange
0x140012e00  nop     dword ptr [rax+rax+00h]
0x140012e05  test    eax, eax
0x140012e07  js      short loc_140012E74
0x140012e09  mov     rax, [rsp+68h+arg_0]
0x140012e0e  test    sil, sil
0x140012e11  jnz     loc_140012EA1
0x140012e17  lock or dword ptr [rax+44h], 1001h
0x140012e1f  mov     rcx, [rsp+68h+arg_0]
0x140012e24  call    cs:__imp_SmbCeInitiateExchange
0x140012e2b  nop     dword ptr [rax+rax+00h]
0x140012e30  mov     rcx, [rsp+68h+arg_0]
0x140012e35  xor     r9d, r9d
0x140012e38  xor     r8d, r8d
0x140012e3b  xor     edx, edx
0x140012e3d  mov     esi, eax
0x140012e3f  cmp     eax, 103h
0x140012e44  jnz     short loc_140012E93
0x140012e46  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140012e4d  nop     dword ptr [rax+rax+00h]
0x140012e52  mov     esi, eax
0x140012e54  mov     [rbx+20h], dil
0x140012e58  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140012e5f  lea     rax, WPP_GLOBAL_Control
0x140012e66  cmp     rcx, rax
0x140012e69  jz      short loc_140012E72
0x140012e6b  mov     eax, [rcx+2Ch]
0x140012e6e  test    al, 20h
0x140012e70  jnz     short loc_140012EC8
0x140012e72  mov     eax, esi
0x140012e74  add     rsp, 48h
0x140012e78  pop     rdi
0x140012e79  pop     rsi
0x140012e7a  pop     rbp
0x140012e7b  pop     rbx
0x140012e7c  retn
0x140012e7e  test    dword ptr [rbx+78h], 1000h
0x140012e85  jz      loc_140012DBA
0x140012e8b  mov     sil, 1
0x140012e8e  jmp     loc_140012DCD
0x140012e93  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140012e9a  nop     dword ptr [rax+rax+00h]
0x140012e9f  jmp     short loc_140012E54
0x140012ea1  lock or dword ptr [rax+44h], 1000h
0x140012ea9  mov     rcx, [rsp+68h+arg_0]
0x140012eae  call    cs:__imp_SmbCeInitiateExchange
0x140012eb5  nop     dword ptr [rax+rax+00h]
0x140012eba  jmp     short loc_140012E74
0x140012ebc  cmp     byte ptr [rbx+21h], 2
0x140012ec0  jnz     loc_140012DBA
0x140012ec6  jmp     short loc_140012E7E
0x140012ec8  cmp     byte ptr [rcx+29h], 2
0x140012ecc  jb      short loc_140012E72
0x140012ece  mov     rcx, [rcx+18h]
0x140012ed2  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x140012ed9  mov     edx, 2Ah ; '*'
0x140012ede  mov     dword ptr [rsp+68h+var_48], esi
0x140012ee2  mov     r9, rbp
0x140012ee5  call    WPP_SF_qD
0x140012eea  jmp     short loc_140012E72
```
