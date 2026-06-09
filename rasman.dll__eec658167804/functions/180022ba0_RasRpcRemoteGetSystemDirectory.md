# RasRpcRemoteGetSystemDirectory

- ea: `0x180022ba0`
- end: `0x180022c8f`
- name: `RasRpcRemoteGetSystemDirectory`
- size: `239`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180021000`
- `0x180021488`
- `0x180022ba0`
- `0x180023968`

## pseudocode

```c
__int64 __fastcall RasRpcRemoteGetSystemDirectory(__int64 a1)
{
  PVOID *v2; // rcx
  unsigned int SystemDirectory; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, a1);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 || *(_DWORD *)(a1 + 8) )
  {
    v4 = 87;
    if ( v2 == &WPP_GLOBAL_Control )
      return v4;
    if ( (*((_BYTE *)v2 + 28) & 0x40) == 0 || *((_BYTE *)v2 + 25) < 2u )
      goto LABEL_18;
    v5 = 36;
    v6 = 87;
    goto LABEL_16;
  }
  SystemDirectory = RemoteGetSystemDirectory(a1);
  v4 = SystemDirectory;
  if ( !SystemDirectory )
  {
LABEL_17:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = 37;
    v6 = SystemDirectory;
LABEL_16:
    WPP_SF_d(v2[2], v5, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, v6);
    goto LABEL_17;
  }
LABEL_18:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 38, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180022ba0  mov     [rsp+arg_0], rbx
0x180022ba5  push    rsi
0x180022ba6  sub     rsp, 20h
0x180022baa  mov     rbx, rcx
0x180022bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bb4  lea     rsi, WPP_GLOBAL_Control
0x180022bbb  cmp     rcx, rsi
0x180022bbe  jz      short loc_180022BEB
0x180022bc0  test    byte ptr [rcx+1Ch], 40h
0x180022bc4  jz      short loc_180022BEB
0x180022bc6  cmp     byte ptr [rcx+19h], 6
0x180022bca  jb      short loc_180022BEB
0x180022bcc  mov     rcx, [rcx+10h]
0x180022bd0  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180022bd7  mov     edx, 23h ; '#'
0x180022bdc  mov     r9, rbx
0x180022bdf  call    WPP_SF_q
0x180022be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180022beb  test    rbx, rbx
0x180022bee  jz      short loc_180022C26
0x180022bf0  cmp     dword ptr [rbx+8], 0
0x180022bf4  jnz     short loc_180022C26
0x180022bf6  mov     rcx, rbx
0x180022bf9  call    RemoteGetSystemDirectory
0x180022bfe  mov     ebx, eax
0x180022c00  test    eax, eax
0x180022c02  jz      short loc_180022C52
0x180022c04  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c0b  cmp     rcx, rsi
0x180022c0e  jz      short loc_180022C82
0x180022c10  test    byte ptr [rcx+1Ch], 40h
0x180022c14  jz      short loc_180022C59
0x180022c16  cmp     byte ptr [rcx+19h], 2
0x180022c1a  jb      short loc_180022C59
0x180022c1c  mov     edx, 25h ; '%'
0x180022c21  mov     r9d, eax
0x180022c24  jmp     short loc_180022C42
0x180022c26  mov     ebx, 57h ; 'W'
0x180022c2b  cmp     rcx, rsi
0x180022c2e  jz      short loc_180022C82
0x180022c30  test    byte ptr [rcx+1Ch], 40h
0x180022c34  jz      short loc_180022C59
0x180022c36  cmp     byte ptr [rcx+19h], 2
0x180022c3a  jb      short loc_180022C59
0x180022c3c  lea     edx, [rbx-33h]
0x180022c3f  mov     r9d, ebx
0x180022c42  mov     rcx, [rcx+10h]
0x180022c46  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180022c4d  call    WPP_SF_d
0x180022c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c59  cmp     rcx, rsi
0x180022c5c  jz      short loc_180022C82
0x180022c5e  test    byte ptr [rcx+1Ch], 40h
0x180022c62  jz      short loc_180022C82
0x180022c64  cmp     byte ptr [rcx+19h], 6
0x180022c68  jb      short loc_180022C82
0x180022c6a  mov     rcx, [rcx+10h]
0x180022c6e  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180022c75  mov     edx, 26h ; '&'
0x180022c7a  mov     r9d, ebx
0x180022c7d  call    WPP_SF_d
0x180022c82  mov     eax, ebx
0x180022c84  mov     rbx, [rsp+28h+arg_0]
0x180022c89  add     rsp, 20h
0x180022c8d  pop     rsi
0x180022c8e  retn
```
