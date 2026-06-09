# MRxSmbFsCtl

- ea: `0x14001afb0`
- end: `0x14001b0dd`
- name: `MRxSmbFsCtl`
- size: `301`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x14001afb0`
- `0x140027dc0`
- `0x14003acec`
- `0x140059ea0`
- `0x140059f00`
- `0x14007f65c`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14005e2b4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14005e2b4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14005e259`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14005e259`
- `ntoskrnl!SeExports` at `0x14005e2e6`
- `ntoskrnl!SeExports` at `0x14005e306`
- `ntoskrnl!SeExports` at `0x14005e34d`
- `ntoskrnl!SeExports` at `0x14005e36d`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14005e2f6`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14005e316`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14005e35d`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14005e382`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14005e2f6`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14005e316`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14005e35d`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14005e382`

## pseudocode

```c
__int64 __fastcall MRxSmbFsCtl(__int64 a1)
{
  __int64 v2; // r8
  __int64 v3; // rcx
  unsigned int v4; // edi
  _WORD *v5; // rax
  _WORD *v6; // rdx
  __int64 v7; // rdx
  ULONG_PTR v8; // rsi
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // eax
  ULONG_PTR v17; // rbp
  const void **v18; // rsi
  unsigned int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax

  v2 = 0;
  v3 = 0;
  v4 = -1073741808;
  v5 = *(_WORD **)(a1 + 64);
  if ( v5 && *v5 == 0xEC30 )
    v3 = *(_QWORD *)(a1 + 64);
  v6 = *(_WORD **)(a1 + 56);
  if ( v6 && (unsigned __int16)(*v6 + 5087) <= 1u )
    v2 = *(_QWORD *)(a1 + 56);
  if ( v3 )
  {
    v7 = *(_QWORD *)(a1 + 72);
    v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 40) + 32LL) + 32LL) + 32LL);
  }
  else
  {
    v7 = 0;
    if ( v2 )
      v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 120) + 32LL) + 32LL);
    else
      v8 = 0;
  }
  if ( *(_DWORD *)(a1 + 540) != 590255 )
  {
    switch ( *(_DWORD *)(a1 + 540) )
    {
      case 0x1401A8:
        if ( v8 )
        {
          v11 = *(_QWORD *)(a1 + 40);
          if ( v11 )
          {
            if ( *(_BYTE *)(v11 + 64) )
            {
              if ( SeSinglePrivilegeCheck(SeExports->SeTcbPrivilege, 1) )
                return (unsigned int)ProcessUserDisconnectRequest(
                                       a1,
                                       v8,
                                       *(_QWORD *)(a1 + 552),
                                       *(unsigned int *)(a1 + 568));
              v4 = -1073741790;
              if ( SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1) )
                return (unsigned int)ProcessUserDisconnectRequest(
                                       a1,
                                       v8,
                                       *(_QWORD *)(a1 + 552),
                                       *(unsigned int *)(a1 + 568));
            }
            else if ( !*(_DWORD *)(a1 + 568) && !*(_DWORD *)(a1 + 572) )
            {
              return (unsigned int)Smb2ForceServerDisconnected(a1, v8, v2);
            }
          }
        }
        break;
      case 0x1401E8:
        if ( v8 )
        {
          v21 = *(_QWORD *)(a1 + 40);
          if ( v21 )
          {
            if ( (!*(_BYTE *)(v21 + 64)
               || SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1)
               || SeSinglePrivilegeCheck(SeExports->SeTcbPrivilege, 1))
              && *(_DWORD *)(a1 + 568) == 36 )
            {
              MRxSmb2SetConnectionProps(v8);
              return 0;
            }
          }
        }
        break;
      case 0x140208:
        if ( v8 )
        {
          v17 = v8 + 144;
          ExAcquirePushLockSharedEx(v8 + 144, 0, v2);
          v18 = *(const void ***)(v8 + 152);
          if ( v18 && (v19 = *(unsigned __int16 *)v18, (_WORD)v19) )
          {
            v20 = *(unsigned __int16 *)v18;
            if ( *(_DWORD *)(a1 + 572) < v19 )
            {
              v4 = -1073741789;
            }
            else
            {
              memmove(*(void **)(a1 + 560), v18[1], *(unsigned __int16 *)v18);
              v20 = *(unsigned __int16 *)v18;
              v4 = 0;
            }
          }
          else
          {
            v4 = 0;
            v20 = 0;
          }
          *(_QWORD *)(a1 + 184) = v20;
          ExReleasePushLockSharedEx(v17, 0);
        }
        break;
      case 0x14020C:
        if ( v7 )
        {
          if ( *(_DWORD *)(a1 + 572) >= 4u )
          {
            v12 = *(_QWORD *)(v7 + 40);
            v13 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 32) + 32LL) + 32LL);
            if ( !v13 || *(_DWORD *)(v13 + 12) )
            {
              v16 = 0;
            }
            else
            {
              v14 = *(_QWORD *)(v12 + 40);
              if ( !v14 || *(_DWORD *)(v14 + 12) )
              {
                v16 = 16;
              }
              else
              {
                v15 = *(_QWORD *)(v7 + 48);
                if ( v15 && !*(_DWORD *)(v15 + 4) && *(_DWORD *)(v15 + 44) == *(_DWORD *)(v14 + 264) )
                  v16 = 48;
                else
                  v16 = 32;
              }
            }
            v4 = 0;
            **(_DWORD **)(a1 + 560) = v16;
          }
          else
          {
            v4 = -1073741789;
          }
          *(_QWORD *)(a1 + 184) = 4;
        }
        break;
      default:
        if ( v8 )
          return (unsigned int)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(v8 + 56) + 352LL))(
                                 a1,
                                 v7,
                                 v2);
        break;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14001afb0  mov     [rsp+arg_10], rbx
0x14001afb5  push    rdi
0x14001afb6  sub     rsp, 20h
0x14001afba  mov     rbx, rcx
0x14001afbd  xor     r8d, r8d
0x14001afc0  xor     ecx, ecx
0x14001afc2  mov     edi, 0C0000010h
0x14001afc7  mov     rax, [rbx+40h]
0x14001afcb  test    rax, rax
0x14001afce  jz      short loc_14001AFDC
0x14001afd0  mov     edx, 0EC30h
0x14001afd5  cmp     [rax], dx
0x14001afd8  cmovz   rcx, rax
0x14001afdc  mov     rdx, [rbx+38h]
0x14001afe0  test    rdx, rdx
0x14001afe3  jz      short loc_14001AFF3
0x14001afe5  mov     eax, 13DFh
0x14001afea  add     ax, [rdx]
0x14001afed  cmp     ax, 1
0x14001aff1  jbe     short loc_14001B069
0x14001aff3  mov     [rsp+28h+arg_8], rsi
0x14001aff8  test    rcx, rcx
0x14001affb  jz      short loc_14001B06E
0x14001affd  mov     rdx, [rbx+48h]
0x14001b001  mov     rax, [rdx+28h]
0x14001b005  mov     rcx, [rax+20h]
0x14001b009  mov     rax, [rcx+20h]
0x14001b00d  mov     rsi, [rax+20h]
0x14001b011  mov     eax, [rbx+21Ch]
0x14001b017  sub     eax, 901AFh
0x14001b01c  jz      short loc_14001B056
0x14001b01e  sub     eax, 0AFFF9h
0x14001b023  jz      short loc_14001B0A3
0x14001b025  sub     eax, 40h ; '@'
0x14001b028  jz      loc_14005E2CA
0x14001b02e  sub     eax, 20h ; ' '
0x14001b031  jz      loc_14005E23F
0x14001b037  cmp     eax, 4
0x14001b03a  jz      short loc_14001B087
0x14001b03c  test    rsi, rsi
0x14001b03f  jz      short loc_14001B056
0x14001b041  mov     rax, [rsi+38h]
0x14001b045  mov     rcx, rbx
0x14001b048  mov     rax, [rax+160h]
0x14001b04f  call    _guard_dispatch_icall
0x14001b054  mov     edi, eax
0x14001b056  mov     rsi, [rsp+28h+arg_8]
0x14001b05b  mov     eax, edi
0x14001b05d  mov     rbx, [rsp+28h+arg_10]
0x14001b062  add     rsp, 20h
0x14001b066  pop     rdi
0x14001b067  retn
0x14001b069  mov     r8, rdx
0x14001b06c  jmp     short loc_14001AFF3
0x14001b06e  xor     edx, edx
0x14001b070  test    r8, r8
0x14001b073  jz      loc_14005E1C2
0x14001b079  mov     rax, [r8+78h]
0x14001b07d  mov     rcx, [rax+20h]
0x14001b081  mov     rsi, [rcx+20h]
0x14001b085  jmp     short loc_14001B011
0x14001b087  test    rdx, rdx
0x14001b08a  jz      short loc_14001B056
0x14001b08c  cmp     dword ptr [rbx+23Ch], 4
0x14001b093  jnb     loc_14005E1C9
0x14001b099  mov     edi, 0C0000023h
0x14001b09e  jmp     loc_14005E22F
0x14001b0a3  test    rsi, rsi
0x14001b0a6  jz      short loc_14001B056
0x14001b0a8  mov     rax, [rbx+28h]
0x14001b0ac  test    rax, rax
0x14001b0af  jz      short loc_14001B056
0x14001b0b1  cmp     byte ptr [rax+40h], 0
0x14001b0b5  jnz     loc_14005E34D
0x14001b0bb  cmp     dword ptr [rbx+238h], 0
0x14001b0c2  jnz     short loc_14001B056
0x14001b0c4  cmp     dword ptr [rbx+23Ch], 0
0x14001b0cb  jnz     short loc_14001B056
0x14001b0cd  mov     rdx, rsi
0x14001b0d0  mov     rcx, rbx
0x14001b0d3  call    Smb2ForceServerDisconnected
0x14001b0d8  jmp     loc_14001B054
0x14005e1c2  xor     esi, esi
0x14005e1c4  jmp     loc_14001B011
0x14005e1c9  mov     r8, [rdx+28h]
0x14005e1cd  mov     rax, [r8+20h]
0x14005e1d1  mov     rcx, [rax+20h]
0x14005e1d5  mov     rax, [rcx+20h]
0x14005e1d9  test    rax, rax
0x14005e1dc  jz      short loc_14005E222
0x14005e1de  cmp     dword ptr [rax+0Ch], 0
0x14005e1e2  jnz     short loc_14005E222
0x14005e1e4  mov     rax, [r8+28h]
0x14005e1e8  test    rax, rax
0x14005e1eb  jz      short loc_14005E21B
0x14005e1ed  cmp     dword ptr [rax+0Ch], 0
0x14005e1f1  jnz     short loc_14005E21B
0x14005e1f3  mov     rcx, [rdx+30h]
0x14005e1f7  test    rcx, rcx
0x14005e1fa  jz      short loc_14005E214
0x14005e1fc  cmp     dword ptr [rcx+4], 0
0x14005e200  jnz     short loc_14005E214
0x14005e202  mov     eax, [rax+108h]
0x14005e208  cmp     [rcx+2Ch], eax
0x14005e20b  jnz     short loc_14005E214
0x14005e20d  mov     eax, 30h ; '0'
0x14005e212  jmp     short loc_14005E224
0x14005e214  mov     eax, 20h ; ' '
0x14005e219  jmp     short loc_14005E224
0x14005e21b  mov     eax, 10h
0x14005e220  jmp     short loc_14005E224
0x14005e222  xor     eax, eax
0x14005e224  mov     rcx, [rbx+230h]
0x14005e22b  xor     edi, edi
0x14005e22d  mov     [rcx], eax
0x14005e22f  mov     qword ptr [rbx+0B8h], 4
0x14005e23a  jmp     loc_14001B056
0x14005e23f  test    rsi, rsi
0x14005e242  jz      loc_14001B056
0x14005e248  mov     [rsp+28h+arg_0], rbp
0x14005e24d  xor     edx, edx
0x14005e24f  lea     rbp, [rsi+90h]
0x14005e256  mov     rcx, rbp
0x14005e259  call    cs:__imp_ExAcquirePushLockSharedEx
0x14005e260  nop     dword ptr [rax+rax+00h]
0x14005e265  mov     rsi, [rsi+98h]
0x14005e26c  test    rsi, rsi
0x14005e26f  jz      short loc_14005E2A4
0x14005e271  movzx   eax, word ptr [rsi]
0x14005e274  test    ax, ax
0x14005e277  jz      short loc_14005E2A4
0x14005e279  mov     ecx, eax
0x14005e27b  cmp     [rbx+23Ch], eax
0x14005e281  jb      short loc_14005E29D
0x14005e283  mov     rdx, [rsi+8]; Src
0x14005e287  mov     r8d, eax; Size
0x14005e28a  mov     rcx, [rbx+230h]; void *
0x14005e291  call    memmove
0x14005e296  movzx   ecx, word ptr [rsi]
0x14005e299  xor     edi, edi
0x14005e29b  jmp     short loc_14005E2A8
0x14005e29d  mov     edi, 0C0000023h
0x14005e2a2  jmp     short loc_14005E2A8
0x14005e2a4  xor     edi, edi
0x14005e2a6  xor     ecx, ecx
0x14005e2a8  mov     [rbx+0B8h], rcx
0x14005e2af  xor     edx, edx
0x14005e2b1  mov     rcx, rbp
0x14005e2b4  call    cs:__imp_ExReleasePushLockSharedEx
0x14005e2bb  nop     dword ptr [rax+rax+00h]
0x14005e2c0  mov     rbp, [rsp+28h+arg_0]
0x14005e2c5  jmp     loc_14001B056
0x14005e2ca  test    rsi, rsi
0x14005e2cd  jz      loc_14001B056
0x14005e2d3  mov     rax, [rbx+28h]
0x14005e2d7  test    rax, rax
0x14005e2da  jz      loc_14001B056
0x14005e2e0  cmp     byte ptr [rax+40h], 0
0x14005e2e4  jz      short loc_14005E32A
0x14005e2e6  mov     rax, cs:__imp_SeExports
0x14005e2ed  mov     dl, 1; PreviousMode
0x14005e2ef  mov     rcx, [rax]
0x14005e2f2  mov     rcx, [rcx+40h]; PrivilegeValue
0x14005e2f6  call    cs:__imp_SeSinglePrivilegeCheck
0x14005e2fd  nop     dword ptr [rax+rax+00h]
0x14005e302  test    al, al
0x14005e304  jnz     short loc_14005E32A
0x14005e306  mov     rax, cs:__imp_SeExports
0x14005e30d  mov     dl, 1; PreviousMode
0x14005e30f  mov     rcx, [rax]
0x14005e312  mov     rcx, [rcx+28h]; PrivilegeValue
0x14005e316  call    cs:__imp_SeSinglePrivilegeCheck
0x14005e31d  nop     dword ptr [rax+rax+00h]
0x14005e322  test    al, al
0x14005e324  jz      loc_14001B056
0x14005e32a  cmp     dword ptr [rbx+238h], 24h ; '$'
0x14005e331  jnz     loc_14001B056
0x14005e337  mov     rdx, [rbx+228h]
0x14005e33e  mov     rcx, rsi
0x14005e341  call    MRxSmb2SetConnectionProps
0x14005e346  xor     edi, edi
0x14005e348  jmp     loc_14001B056
0x14005e34d  mov     rax, cs:__imp_SeExports
0x14005e354  mov     dl, 1; PreviousMode
0x14005e356  mov     rcx, [rax]
0x14005e359  mov     rcx, [rcx+28h]; PrivilegeValue
0x14005e35d  call    cs:__imp_SeSinglePrivilegeCheck
0x14005e364  nop     dword ptr [rax+rax+00h]
0x14005e369  test    al, al
0x14005e36b  jnz     short loc_14005E396
0x14005e36d  mov     rax, cs:__imp_SeExports
0x14005e374  mov     dl, 1; PreviousMode
0x14005e376  mov     edi, 0C0000022h
0x14005e37b  mov     rcx, [rax]
0x14005e37e  mov     rcx, [rcx+40h]; PrivilegeValue
0x14005e382  call    cs:__imp_SeSinglePrivilegeCheck
0x14005e389  nop     dword ptr [rax+rax+00h]
0x14005e38e  test    al, al
0x14005e390  jz      loc_14001B056
0x14005e396  mov     r9d, [rbx+238h]
0x14005e39d  mov     rdx, rsi
0x14005e3a0  mov     r8, [rbx+228h]
0x14005e3a7  mov     rcx, rbx
0x14005e3aa  call    ProcessUserDisconnectRequest
0x14005e3af  nop
0x14005e3b0  jmp     loc_14001B054
```
