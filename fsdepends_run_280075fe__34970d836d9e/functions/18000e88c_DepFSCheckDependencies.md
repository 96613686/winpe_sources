# DepFSCheckDependencies

- ea: `0x18000e88c`
- end: `0x18000eab9`
- name: `DepFSCheckDependencies`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d1c0`

## callees

- `0x180001020`
- `0x1800010b8`
- `0x18000b964`
- `0x18000d9d0`
- `0x18000e88c`
- `0x18000f4bc`
- `0x18000f5f8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000e8ee`
- `ntoskrnl!ExAllocatePool2` at `0x18000e8ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000e8c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ea99`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000e8c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ea99`

## pseudocode

```c
__int64 __fastcall DepFSCheckDependencies(__int64 a1)
{
  __int64 Pool2; // rdi
  unsigned int v3; // esi
  __int64 v4; // rbx
  __int64 v5; // rdx
  int v6; // eax
  int v7; // ebx
  unsigned int v8; // ebp
  __int64 v9; // rsi
  unsigned int v10; // eax
  unsigned int v11; // esi
  _WORD *v12; // rbp
  __int64 v14; // [rsp+20h] [rbp-48h]
  __int64 v15; // [rsp+28h] [rbp-40h]
  unsigned int *v16; // [rsp+30h] [rbp-38h]
  unsigned int v17; // [rsp+78h] [rbp+10h] BYREF
  int v18; // [rsp+80h] [rbp+18h] BYREF

  Pool2 = 0;
  v18 = 3;
  v17 = 0;
  v3 = 72;
  do
  {
    if ( Pool2 )
    {
      v4 = *(_QWORD *)(Pool2 + 8);
      ExFreePoolWithTag((PVOID)Pool2, 0x72517044u);
      Pool2 = 0;
      v3 = v4;
      if ( v4 != (unsigned int)v4 )
      {
        v7 = -1073741670;
LABEL_33:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_D(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x19u,
            (__int64)WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids,
            v7);
        }
        goto LABEL_37;
      }
    }
    Pool2 = ExAllocatePool2(256, v3, 1917939780);
    if ( !Pool2 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_37;
      v7 = -1073741670;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_D(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x17u,
          (__int64)WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids,
          v3);
      goto LABEL_33;
    }
    v16 = &v17;
    LODWORD(v15) = v3;
    v14 = Pool2;
    v6 = DepFSSendIoctl(a1, v5, &v18);
    v7 = v6;
  }
  while ( v6 == -2147483643 );
  if ( v6 >= 0 )
  {
    if ( v17 >= 0x38 )
    {
      v8 = 0;
      if ( *(_DWORD *)(Pool2 + 4) )
      {
        do
        {
          v9 = *(_QWORD *)(Pool2 + 48 * (v8 + 1LL));
          if ( v9 )
          {
            if ( *(_WORD *)v9 == 12336 )
            {
              DepFSIncrementActiveMountCount(*(_QWORD *)(Pool2 + 48 * (v8 + 1LL)));
              if ( *(int *)(v9 + 96) > 0 || (*(_DWORD *)(v9 + 92) & 0x31) != 0 )
              {
                v7 = -1069940708;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_q(
                    (__int64)WPP_GLOBAL_Control->AttachedDevice,
                    0x18u,
                    (__int64)WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids,
                    v9,
                    v14,
                    v15,
                    v16);
                }
              }
            }
          }
          v10 = *(_DWORD *)(Pool2 + 4);
          ++v8;
        }
        while ( v8 < v10 );
        v11 = 0;
        if ( v10 )
        {
          do
          {
            v12 = *(_WORD **)(Pool2 + 48 * (v11 + 1LL));
            if ( v12 && *v12 == 12336 )
            {
              if ( v7 < 0 )
                DepFSDecrementActiveMountCount(*(_QWORD *)(Pool2 + 48 * (v11 + 1LL)));
              DependentFSDereferenceDependency(v12);
            }
            ++v11;
          }
          while ( v11 < *(_DWORD *)(Pool2 + 4) );
        }
      }
    }
    goto LABEL_38;
  }
  if ( v6 != -1073741808 )
    goto LABEL_33;
LABEL_37:
  v7 = 0;
  if ( !Pool2 )
    return (unsigned int)v7;
LABEL_38:
  ExFreePoolWithTag((PVOID)Pool2, 0x72517044u);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000e88c  mov     rax, rsp
0x18000e88f  mov     [rax+8], rbx
0x18000e893  push    rbp
0x18000e894  push    rsi
0x18000e895  push    rdi
0x18000e896  push    r12
0x18000e898  push    r14
0x18000e89a  sub     rsp, 40h
0x18000e89e  xor     edi, edi
0x18000e8a0  mov     dword ptr [rax+18h], 3
0x18000e8a7  mov     rbp, rcx
0x18000e8aa  mov     [rax+10h], edi
0x18000e8ad  lea     esi, [rdi+48h]
0x18000e8b0  lea     r14, WPP_GLOBAL_Control
0x18000e8b7  test    rdi, rdi
0x18000e8ba  jz      short loc_18000E8E1
0x18000e8bc  mov     rbx, [rdi+8]
0x18000e8c0  mov     edx, 72517044h; Tag
0x18000e8c5  mov     rcx, rdi; P
0x18000e8c8  call    cs:__imp_ExFreePoolWithTag
0x18000e8cf  nop     dword ptr [rax+rax+00h]
0x18000e8d4  xor     edi, edi
0x18000e8d6  mov     esi, ebx
0x18000e8d8  cmp     rbx, rsi
0x18000e8db  jnz     loc_18000EA13
0x18000e8e1  mov     edx, esi
0x18000e8e3  mov     ecx, 100h
0x18000e8e8  mov     r8d, 72517044h
0x18000e8ee  call    cs:__imp_ExAllocatePool2
0x18000e8f5  nop     dword ptr [rax+rax+00h]
0x18000e8fa  mov     rdi, rax
0x18000e8fd  test    rax, rax
0x18000e900  jz      loc_18000EA23
0x18000e906  lea     rax, [rsp+68h+arg_8]
0x18000e90b  mov     rcx, rbp
0x18000e90e  mov     [rsp+68h+var_38], rax
0x18000e913  lea     r8, [rsp+68h+arg_10]
0x18000e91b  mov     dword ptr [rsp+68h+var_40], esi
0x18000e91f  mov     [rsp+68h+var_48], rdi
0x18000e924  call    DepFSSendIoctl
0x18000e929  mov     ebx, eax
0x18000e92b  cmp     eax, 80000005h
0x18000e930  jz      loc_18000E8B0
0x18000e936  test    eax, eax
0x18000e938  js      loc_18000EA1A
0x18000e93e  cmp     [rsp+68h+arg_8], 38h ; '8'
0x18000e943  jb      loc_18000EA91
0x18000e949  xor     ebp, ebp
0x18000e94b  cmp     [rdi+4], ebp
0x18000e94e  jbe     loc_18000EA91
0x18000e954  mov     r12d, 3030h
0x18000e95a  lea     r14, WPP_GLOBAL_Control
0x18000e961  mov     eax, ebp
0x18000e963  inc     rax
0x18000e966  lea     rax, [rax+rax*2]
0x18000e96a  add     rax, rax
0x18000e96d  mov     rsi, [rdi+rax*8]
0x18000e971  test    rsi, rsi
0x18000e974  jz      short loc_18000E9C7
0x18000e976  cmp     [rsi], r12w
0x18000e97a  jnz     short loc_18000E9C7
0x18000e97c  mov     rcx, rsi
0x18000e97f  call    DepFSIncrementActiveMountCount
0x18000e984  cmp     dword ptr [rsi+60h], 0
0x18000e988  jg      short loc_18000E991
0x18000e98a  mov     eax, [rsi+5Ch]
0x18000e98d  test    al, 31h
0x18000e98f  jz      short loc_18000E9C7
0x18000e991  mov     ebx, 0C03A001Ch
0x18000e996  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e99d  cmp     rcx, r14
0x18000e9a0  jz      short loc_18000E9C7
0x18000e9a2  mov     eax, [rcx+2Ch]
0x18000e9a5  test    al, 4
0x18000e9a7  jz      short loc_18000E9C7
0x18000e9a9  cmp     byte ptr [rcx+29h], 4
0x18000e9ad  jb      short loc_18000E9C7
0x18000e9af  mov     rcx, [rcx+18h]
0x18000e9b3  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000e9ba  mov     edx, 18h
0x18000e9bf  mov     r9, rsi
0x18000e9c2  call    WPP_SF_q
0x18000e9c7  mov     eax, [rdi+4]
0x18000e9ca  inc     ebp
0x18000e9cc  cmp     ebp, eax
0x18000e9ce  jb      short loc_18000E961
0x18000e9d0  xor     esi, esi
0x18000e9d2  test    eax, eax
0x18000e9d4  jz      loc_18000EA91
0x18000e9da  mov     eax, esi
0x18000e9dc  inc     rax
0x18000e9df  lea     rax, [rax+rax*2]
0x18000e9e3  add     rax, rax
0x18000e9e6  mov     rbp, [rdi+rax*8]
0x18000e9ea  test    rbp, rbp
0x18000e9ed  jz      short loc_18000EA0A
0x18000e9ef  cmp     [rbp+0], r12w
0x18000e9f4  jnz     short loc_18000EA0A
0x18000e9f6  test    ebx, ebx
0x18000e9f8  jns     short loc_18000EA02
0x18000e9fa  mov     rcx, rbp
0x18000e9fd  call    DepFSDecrementActiveMountCount
0x18000ea02  mov     rcx, rbp; P
0x18000ea05  call    DependentFSDereferenceDependency
0x18000ea0a  inc     esi
0x18000ea0c  cmp     esi, [rdi+4]
0x18000ea0f  jb      short loc_18000E9DA
0x18000ea11  jmp     short loc_18000EA91
0x18000ea13  mov     ebx, 0C000009Ah
0x18000ea18  jmp     short loc_18000EA59
0x18000ea1a  cmp     eax, 0C0000010h
0x18000ea1f  jz      short loc_18000EA8A
0x18000ea21  jmp     short loc_18000EA59
0x18000ea23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea2a  cmp     rcx, r14
0x18000ea2d  jz      short loc_18000EA8A
0x18000ea2f  mov     eax, [rcx+2Ch]
0x18000ea32  mov     ebx, 0C000009Ah
0x18000ea37  test    al, 1
0x18000ea39  jz      short loc_18000EA59
0x18000ea3b  cmp     byte ptr [rcx+29h], 2
0x18000ea3f  jb      short loc_18000EA59
0x18000ea41  mov     rcx, [rcx+18h]
0x18000ea45  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000ea4c  mov     edx, 17h
0x18000ea51  mov     r9d, esi
0x18000ea54  call    WPP_SF_D
0x18000ea59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea60  cmp     rcx, r14
0x18000ea63  jz      short loc_18000EA8A
0x18000ea65  mov     eax, [rcx+2Ch]
0x18000ea68  test    al, 1
0x18000ea6a  jz      short loc_18000EA8A
0x18000ea6c  cmp     byte ptr [rcx+29h], 2
0x18000ea70  jb      short loc_18000EA8A
0x18000ea72  mov     rcx, [rcx+18h]
0x18000ea76  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000ea7d  mov     edx, 19h
0x18000ea82  mov     r9d, ebx
0x18000ea85  call    WPP_SF_D
0x18000ea8a  xor     ebx, ebx
0x18000ea8c  test    rdi, rdi
0x18000ea8f  jz      short loc_18000EAA5
0x18000ea91  mov     edx, 72517044h; Tag
0x18000ea96  mov     rcx, rdi; P
0x18000ea99  call    cs:__imp_ExFreePoolWithTag
0x18000eaa0  nop     dword ptr [rax+rax+00h]
0x18000eaa5  mov     eax, ebx
0x18000eaa7  mov     rbx, [rsp+68h+arg_0]
0x18000eaac  add     rsp, 40h
0x18000eab0  pop     r14
0x18000eab2  pop     r12
0x18000eab4  pop     rdi
0x18000eab5  pop     rsi
0x18000eab6  pop     rbp
0x18000eab7  retn
```
