# Smb2GenericExchange_Restart

- ea: `0x14002f9e0`
- end: `0x14002fb6f`
- name: `Smb2GenericExchange_Restart`
- size: `399`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140008ec0`
- `0x14002b1c0`
- `0x14002b210`
- `0x14002b670`

## callees

- `0x14000e700`
- `0x14002a6a8`
- `0x14002f9e0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002fa52`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002fa52`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14002fadc`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14002fadc`

## pseudocode

```c
__int64 __fastcall Smb2GenericExchange_Restart(__int64 a1)
{
  __int64 v1; // r14
  __int64 v2; // rdx
  int v3; // ebx
  char v4; // bp
  __int64 v6; // rdi
  __int64 v7; // rcx
  PVOID v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // r11
  unsigned int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx

  v1 = a1 + 160;
  v2 = *(_QWORD *)(a1 + 160);
  v3 = 0;
  v4 = 0;
  v6 = v2 - 8;
  if ( v2 == a1 + 160 )
    v6 = 0;
  while ( v6 )
  {
    if ( (*(_DWORD *)(v6 + 4) & 0x400) != 0 )
      goto LABEL_22;
    v7 = *(_QWORD *)(v6 + 96);
    if ( !v7 )
      goto LABEL_22;
    if ( (*(_BYTE *)(v7 + 10) & 5) != 0 )
      v8 = *(PVOID *)(v7 + 24);
    else
      v8 = MmMapLockedPagesSpecifyCache((PMDL)v7, 0, MmCached, 0, 0, 0x40000010u);
    if ( !v8 )
    {
      v3 = -1073741670;
      break;
    }
    SmbCeBuildSmb2Header(a1, v8, *(unsigned int *)(*(_QWORD *)(v6 + 96) + 40LL));
    *(_WORD *)(v9 + 12) = v10;
    if ( (unsigned int)v10 >= 0x14 )
    {
      v3 = -1073741811;
      break;
    }
    if ( (_DWORD)v10 == 18 )
    {
      if ( *(_WORD *)(v9 + 64) == 24 )
      {
        v11 = 8;
LABEL_16:
        v12 = *(_QWORD *)(a1 + 48);
        if ( v12 )
        {
          v13 = *(_QWORD *)(v12 + 72);
          if ( v13 )
          {
            v14 = *(_QWORD *)(v13 + 48);
            if ( v14 )
              *(_OWORD *)(v11 + v9 + 64) = *(_OWORD *)(v14 + 28);
          }
        }
      }
    }
    else
    {
      v11 = *((_DWORD *)Smb2FidOffset + v10);
      if ( v11 )
        goto LABEL_16;
    }
    v3 = SmbCseSubmitBufferContext(v6);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids, v6, a1, v3);
      }
      break;
    }
    v4 = 1;
LABEL_22:
    v15 = *(_QWORD *)(v6 + 8);
    v6 = 0;
    if ( v15 != v1 )
      v6 = v15 - 8;
  }
  if ( v4 )
    return 259;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002f9e0  push    rbx
0x14002f9e2  push    rbp
0x14002f9e3  push    rsi
0x14002f9e4  push    rdi
0x14002f9e5  push    r14
0x14002f9e7  sub     rsp, 30h
0x14002f9eb  lea     r14, [rcx+0A0h]
0x14002f9f2  xor     eax, eax
0x14002f9f4  mov     rdx, [r14]
0x14002f9f7  xor     ebx, ebx
0x14002f9f9  xor     bpl, bpl
0x14002f9fc  mov     rsi, rcx
0x14002f9ff  cmp     rdx, r14
0x14002fa02  lea     rdi, [rdx-8]
0x14002fa06  cmovz   rdi, rax
0x14002fa0a  test    rdi, rdi
0x14002fa0d  jz      loc_14002FB56
0x14002fa13  test    dword ptr [rdi+4], 400h
0x14002fa1a  jnz     loc_14002FAF1
0x14002fa20  mov     rcx, [rdi+60h]; MemoryDescriptorList
0x14002fa24  test    rcx, rcx
0x14002fa27  jz      loc_14002FAF1
0x14002fa2d  test    byte ptr [rcx+0Ah], 5
0x14002fa31  jz      short loc_14002FA39
0x14002fa33  mov     rdx, [rcx+18h]
0x14002fa37  jmp     short loc_14002FA61
0x14002fa39  xor     r9d, r9d; RequestedAddress
0x14002fa3c  mov     [rsp+58h+Priority], 40000010h; Priority
0x14002fa44  xor     edx, edx; AccessMode
0x14002fa46  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002fa4e  lea     r8d, [r9+1]; CacheType
0x14002fa52  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002fa59  nop     dword ptr [rax+rax+00h]
0x14002fa5e  mov     rdx, rax
0x14002fa61  test    rdx, rdx
0x14002fa64  jz      loc_14002FB51
0x14002fa6a  mov     r8, [rdi+60h]
0x14002fa6e  mov     rcx, rsi
0x14002fa71  movzx   r11d, word ptr [rdx+0Ch]
0x14002fa76  mov     r8d, [r8+28h]
0x14002fa7a  call    SmbCeBuildSmb2Header
0x14002fa7f  mov     [rdx+0Ch], r11w
0x14002fa84  cmp     r11d, 14h
0x14002fa88  jnb     loc_14002FB4A
0x14002fa8e  cmp     r11d, 12h
0x14002fa92  jz      short loc_14002FAA5
0x14002fa94  lea     rcx, Smb2FidOffset
0x14002fa9b  mov     ecx, [rcx+r11*4]
0x14002fa9f  test    ecx, ecx
0x14002faa1  jz      short loc_14002FAD9
0x14002faa3  jmp     short loc_14002FAB1
0x14002faa5  cmp     word ptr [rdx+40h], 18h
0x14002faaa  jnz     short loc_14002FAD9
0x14002faac  mov     ecx, 8
0x14002fab1  mov     rax, [rsi+30h]
0x14002fab5  test    rax, rax
0x14002fab8  jz      short loc_14002FAD9
0x14002faba  mov     r8, [rax+48h]
0x14002fabe  test    r8, r8
0x14002fac1  jz      short loc_14002FAD9
0x14002fac3  mov     r9, [r8+30h]
0x14002fac7  test    r9, r9
0x14002faca  jz      short loc_14002FAD9
0x14002facc  movups  xmm0, xmmword ptr [r9+1Ch]
0x14002fad1  mov     eax, ecx
0x14002fad3  movdqu  xmmword ptr [rax+rdx+40h], xmm0
0x14002fad9  mov     rcx, rdi
0x14002fadc  call    cs:__imp_SmbCseSubmitBufferContext
0x14002fae3  nop     dword ptr [rax+rax+00h]
0x14002fae8  mov     ebx, eax
0x14002faea  test    eax, eax
0x14002faec  js      short loc_14002FB07
0x14002faee  mov     bpl, 1
0x14002faf1  mov     rcx, [rdi+8]
0x14002faf5  xor     edi, edi
0x14002faf7  cmp     rcx, r14
0x14002fafa  lea     rax, [rcx-8]
0x14002fafe  cmovnz  rdi, rax
0x14002fb02  jmp     loc_14002FA0A
0x14002fb07  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fb0e  lea     rax, WPP_GLOBAL_Control
0x14002fb15  cmp     rcx, rax
0x14002fb18  jz      short loc_14002FB56
0x14002fb1a  mov     eax, [rcx+2Ch]
0x14002fb1d  test    al, 1
0x14002fb1f  jz      short loc_14002FB56
0x14002fb21  cmp     byte ptr [rcx+29h], 1
0x14002fb25  jb      short loc_14002FB56
0x14002fb27  mov     rcx, [rcx+18h]
0x14002fb2b  lea     r8, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids
0x14002fb32  mov     edx, 29h ; ')'
0x14002fb37  mov     [rsp+58h+Priority], ebx
0x14002fb3b  mov     r9, rdi
0x14002fb3e  mov     qword ptr [rsp+58h+BugCheckOnFailure], rsi
0x14002fb43  call    WPP_SF_qqD
0x14002fb48  jmp     short loc_14002FB56
0x14002fb4a  mov     ebx, 0C000000Dh
0x14002fb4f  jmp     short loc_14002FB56
0x14002fb51  mov     ebx, 0C000009Ah
0x14002fb56  mov     eax, 103h
0x14002fb5b  test    bpl, bpl
0x14002fb5e  cmovnz  ebx, eax
0x14002fb61  mov     eax, ebx
0x14002fb63  add     rsp, 30h
0x14002fb67  pop     r14
0x14002fb69  pop     rdi
0x14002fb6a  pop     rsi
0x14002fb6b  pop     rbp
0x14002fb6c  pop     rbx
0x14002fb6d  retn
```
