# MRxSmb2ParseSmb2Header

- ea: `0x14000d8f0`
- end: `0x14000da07`
- name: `MRxSmb2ParseSmb2Header`
- size: `279`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000d8f0`
- `0x1400297a8`

## import_xrefs

- `mrxsmb!Smb2CommandToString` at `0x14000d946`
- `mrxsmb!Smb2CommandToString` at `0x14000d946`

## pseudocode

```c
__int64 __fastcall MRxSmb2ParseSmb2Header(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  int v7; // esi
  unsigned int v8; // eax
  int v9; // eax

  if ( a2 < 0x40 )
    return 3221225667LL;
  if ( *(_DWORD *)a1 != 1112364030 )
    return 3221225667LL;
  v7 = *(_DWORD *)(a1 + 16);
  if ( (v7 & 1) == 0 )
    return 3221225667LL;
  *(_QWORD *)a4 = *(_QWORD *)(a1 + 24);
  *(_DWORD *)(a4 + 20) = *(_DWORD *)(a1 + 8);
  *(_DWORD *)(a4 + 24) = *(_DWORD *)(a1 + 20);
  *(_WORD *)(a4 + 28) = *(_WORD *)(a1 + 14);
  *(_QWORD *)(a4 + 32) = Smb2CommandToString(*(unsigned __int16 *)(a1 + 12));
  v8 = *(_DWORD *)(a4 + 24);
  if ( (v8 & 7) != 0 || v8 >= a3 )
    return 3221225667LL;
  *(_BYTE *)(a4 + 30) = 0;
  if ( (v7 & 2) != 0 )
  {
    *(_QWORD *)(a4 + 8) = *(_QWORD *)(a1 + 32);
    *(_BYTE *)(a4 + 30) = 1;
  }
  v9 = *(_DWORD *)(a4 + 20);
  if ( ((v9 >> 16) & 0xFFF) != 0 && (v9 & 0xFFF0000) != 0x400000 && (v9 & 0xFFF0000) != 0x5C0000 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids,
        (unsigned int)v9,
        (*(int *)(a4 + 20) >> 16) & 0xFFF);
    }
    if ( dbgBreakOnUnexpectedStatus )
      __debugbreak();
    goto LABEL_17;
  }
  if ( v9 == -1073741267 || v9 == -1073741802 || v9 == -1073741507 )
  {
LABEL_17:
    v9 = -1073741629;
    goto LABEL_13;
  }
  if ( v9 < 0 )
  {
LABEL_13:
    *(_DWORD *)(a4 + 16) = v9;
    return 0;
  }
  if ( v9 != 268 && v9 )
  {
    if ( v9 == 259 )
    {
      v9 = -1073741629;
    }
    else if ( v9 != 261 && v9 != 267 )
    {
      v9 = 0;
    }
  }
  *(_DWORD *)(a4 + 16) = v9;
  return 0;
}

```

## disassembly

```asm
0x14000d8f0  push    rbx
0x14000d8f2  push    rbp
0x14000d8f3  push    rsi
0x14000d8f4  push    rdi
0x14000d8f5  sub     rsp, 38h
0x14000d8f9  mov     rbx, r9
0x14000d8fc  mov     ebp, r8d
0x14000d8ff  mov     rdi, rcx
0x14000d902  cmp     edx, 40h ; '@'
0x14000d905  jb      loc_14000D9BE
0x14000d90b  cmp     dword ptr [rcx], 424D53FEh
0x14000d911  jnz     loc_14000D9BE
0x14000d917  mov     esi, [rcx+10h]
0x14000d91a  test    sil, 1
0x14000d91e  jz      loc_14000D9BE
0x14000d924  mov     rax, [rcx+18h]
0x14000d928  mov     [r9], rax
0x14000d92b  mov     eax, [rcx+8]
0x14000d92e  mov     [r9+14h], eax
0x14000d932  mov     eax, [rcx+14h]
0x14000d935  mov     [r9+18h], eax
0x14000d939  movzx   eax, word ptr [rcx+0Eh]
0x14000d93d  mov     [r9+1Ch], ax
0x14000d942  movzx   ecx, word ptr [rcx+0Ch]
0x14000d946  call    cs:__imp_Smb2CommandToString
0x14000d94d  nop     dword ptr [rax+rax+00h]
0x14000d952  mov     [rbx+20h], rax
0x14000d956  mov     eax, [rbx+18h]
0x14000d959  test    al, 7
0x14000d95b  jnz     short loc_14000D9BE
0x14000d95d  cmp     eax, ebp
0x14000d95f  jnb     short loc_14000D9BE
0x14000d961  mov     byte ptr [rbx+1Eh], 0
0x14000d965  test    sil, 2
0x14000d969  jz      short loc_14000D977
0x14000d96b  mov     rax, [rdi+20h]
0x14000d96f  mov     [rbx+8], rax
0x14000d973  mov     byte ptr [rbx+1Eh], 1
0x14000d977  mov     eax, [rbx+14h]
0x14000d97a  mov     r8d, eax
0x14000d97d  sar     r8d, 10h
0x14000d981  and     r8d, 0FFFh
0x14000d988  jnz     loc_140039B8C
0x14000d98e  cmp     eax, 0C000022Dh
0x14000d993  jz      short loc_14000D9E0
0x14000d995  cmp     eax, 0C0000016h
0x14000d99a  jz      short loc_14000D9E0
0x14000d99c  cmp     eax, 0C000013Dh
0x14000d9a1  jz      short loc_14000D9E0
0x14000d9a3  test    eax, eax
0x14000d9a5  jns     short loc_14000D9C5
0x14000d9a7  mov     ecx, 10h
0x14000d9ac  mov     rdx, rbx
0x14000d9af  mov     [rcx+rbx], eax
0x14000d9b2  xor     eax, eax
0x14000d9b4  add     rsp, 38h
0x14000d9b8  pop     rdi
0x14000d9b9  pop     rsi
0x14000d9ba  pop     rbp
0x14000d9bb  pop     rbx
0x14000d9bc  retn
0x14000d9be  mov     eax, 0C00000C3h
0x14000d9c3  jmp     short loc_14000D9B4
0x14000d9c5  cmp     eax, 10Ch
0x14000d9ca  jnz     short loc_14000D9E7
0x14000d9cc  mov     edx, 10h
0x14000d9d1  mov     [rbx+rdx], eax
0x14000d9d4  xor     eax, eax
0x14000d9d6  add     rsp, 38h
0x14000d9da  pop     rdi
0x14000d9db  pop     rsi
0x14000d9dc  pop     rbp
0x14000d9dd  pop     rbx
0x14000d9de  retn
0x14000d9e0  mov     eax, 0C00000C3h
0x14000d9e5  jmp     short loc_14000D9A7
0x14000d9e7  mov     edx, eax
0x14000d9e9  test    eax, eax
0x14000d9eb  jz      short loc_14000D9CC
0x14000d9ed  sub     edx, 103h
0x14000d9f3  jz      loc_140039BFF
0x14000d9f9  sub     edx, 2
0x14000d9fc  jz      short loc_14000D9CC
0x14000d9fe  cmp     edx, 6
0x14000da01  jz      short loc_14000D9CC
0x14000da03  xor     eax, eax
0x14000da05  jmp     short loc_14000D9CC
0x140039b8c  mov     ecx, eax
0x140039b8e  and     ecx, 0FFF0000h
0x140039b94  cmp     ecx, 400000h
0x140039b9a  jz      loc_14000D98E
0x140039ba0  cmp     ecx, 5C0000h
0x140039ba6  jz      loc_14000D98E
0x140039bac  mov     rcx, cs:WPP_GLOBAL_Control
0x140039bb3  lea     rdx, WPP_GLOBAL_Control
0x140039bba  cmp     rcx, rdx
0x140039bbd  jz      short loc_140039BEA
0x140039bbf  mov     edx, [rcx+2Ch]
0x140039bc2  test    dl, 1
0x140039bc5  jz      short loc_140039BEA
0x140039bc7  cmp     byte ptr [rcx+29h], 1
0x140039bcb  jb      short loc_140039BEA
0x140039bcd  mov     rcx, [rcx+18h]
0x140039bd1  mov     edx, 0Ah
0x140039bd6  mov     [rsp+58h+var_38], r8d
0x140039bdb  mov     r9d, eax
0x140039bde  lea     r8, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids
0x140039be5  call    WPP_SF_DD
0x140039bea  movzx   eax, cs:dbgBreakOnUnexpectedStatus
0x140039bf1  test    al, al
0x140039bf3  jz      loc_14000D9E0
0x140039bf9  int     3; Trap to Debugger
0x140039bfa  jmp     loc_14000D9E0
0x140039bff  mov     eax, 0C00000C3h
0x140039c04  jmp     loc_14000D9CC
```
