# ProcessWitnessNotification

- ea: `0x14007f8e4`
- end: `0x14007fd35`
- name: `ProcessWitnessNotification`
- size: `1105`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14001f0e0`

## callees

- `0x140014400`
- `0x14003838c`
- `0x1400383d0`
- `0x140038e90`
- `0x140039090`
- `0x140039fa8`
- `0x140039fd8`
- `0x1400448ec`
- `0x140044dd8`
- `0x14007f8e4`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14007fbf6`
- `ntoskrnl!RtlCompareMemory` at `0x14007fbf6`
- `ntoskrnl!IoGetSiloParameters` at `0x14007f9e5`
- `ntoskrnl!IoGetSiloParameters` at `0x14007fb7a`
- `ntoskrnl!IoGetSiloParameters` at `0x14007f9e5`
- `ntoskrnl!IoGetSiloParameters` at `0x14007fb7a`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14007f9fa`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14007fb8f`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14007f9fa`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14007fb8f`
- `ntoskrnl!PsIsHostSilo` at `0x14007fa0c`
- `ntoskrnl!PsIsHostSilo` at `0x14007fba1`
- `ntoskrnl!PsIsHostSilo` at `0x14007fa0c`
- `ntoskrnl!PsIsHostSilo` at `0x14007fba1`

## pseudocode

```c
__int64 __fastcall ProcessWitnessNotification(_QWORD *a1, _DWORD *a2, unsigned int a3)
{
  unsigned int v5; // ebx
  __int64 v6; // r9
  int v7; // r10d
  __int64 v8; // r10
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // r8
  ULONG_PTR v14; // rsi
  char v15; // al
  unsigned int v16; // eax
  __int64 SiloParameters; // rax
  __int64 EffectiveServerSilo; // rbx
  ULONG_PTR v19; // rbx
  __int64 v20; // r8
  int v21; // eax
  _OWORD v23[3]; // [rsp+30h] [rbp-38h] BYREF

  if ( a3 < 8 )
    return (unsigned int)-1073741808;
  if ( a2[1] == 1 )
  {
    v23[0] = 0;
    if ( a3 < 0x34 || (v16 = a2[12], a3 < v16) || v16 >= 0xFFFE || a3 < v16 + 52 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids);
      }
      return (unsigned int)-1073741808;
    }
    *((_QWORD *)&v23[0] + 1) = a2 + 13;
    WORD1(v23[0]) = *((_WORD *)a2 + 24);
    LOWORD(v23[0]) = WORD1(v23[0]);
    SiloParameters = IoGetSiloParameters(*(_QWORD *)(*(_QWORD *)(a1[5] + 184LL) + 48LL));
    if ( !SiloParameters
      || (EffectiveServerSilo = PsGetEffectiveServerSilo(*(_QWORD *)(SiloParameters + 8)),
          (unsigned __int8)PsIsHostSilo(EffectiveServerSilo)) )
    {
      EffectiveServerSilo = 0;
    }
    v19 = LookupServerEntryByName(*(_QWORD *)(a1[10] + 504LL), v23, EffectiveServerSilo);
    if ( !v19 )
    {
LABEL_61:
      v5 = 0;
      a1[23] = 0;
      return v5;
    }
    v21 = a2[11];
    if ( v21 == 255 )
    {
      if ( RtlCompareMemory((const void *)(v19 + 656), a2 + 7, 0x10u) != 16 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids);
        }
        goto LABEL_60;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids, v19);
      }
      SmbCeSuspendServerConnections(v19, 0, 0xFFFFFFFFLL);
      if ( (*(_BYTE *)(v19 + 737) & 0xC) != 0xC )
      {
LABEL_60:
        SmbCeDereferenceServerEntryEx(v19, 0, v20);
        goto LABEL_61;
      }
    }
    else
    {
      if ( v21 != 1 )
        goto LABEL_60;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids, v19);
      }
    }
    SmbCeUnSuspendServerConnections(v19, 0);
    goto LABEL_60;
  }
  if ( (unsigned int)(a2[1] - 2) > 1 )
    return (unsigned int)-1073741808;
  v23[0] = 0;
  if ( a3 >= 0x18 )
  {
    v6 = (unsigned int)a2[2];
    v7 = a2[3];
    if ( (int)v6 + v7 < (unsigned int)v6 || a3 < (int)v6 + v7 )
    {
      v5 = -1073741808;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids, v6, v7);
      }
    }
    else
    {
      v8 = (unsigned int)a2[5];
      v9 = 24 * v8;
      if ( (unsigned __int64)(24 * v8) > 0xFFFFFFFF || v9 + 24 < v9 || a3 < v9 + 24 )
      {
        v5 = -1073741808;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            44,
            WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids,
            (unsigned int)v8,
            a3);
        }
      }
      else
      {
        *((_QWORD *)&v23[0] + 1) = (char *)a2 + v6;
        WORD1(v23[0]) = *((_WORD *)a2 + 6);
        LOWORD(v23[0]) = WORD1(v23[0]);
        v10 = IoGetSiloParameters(*(_QWORD *)(*(_QWORD *)(a1[5] + 184LL) + 48LL));
        if ( !v10 || (v11 = PsGetEffectiveServerSilo(*(_QWORD *)(v10 + 8)), (unsigned __int8)PsIsHostSilo(v11)) )
          v11 = 0;
        v12 = LookupServerEntryByName(*(_QWORD *)(a1[10] + 504LL), v23, v11);
        v14 = v12;
        if ( v12 )
        {
          v15 = *(_BYTE *)(v12 + 737);
          if ( (v15 & 0x20) == 0 || ((v5 = 0, !byte_14007D27A) || v15 >= 0) && a2[1] != 2 )
            v5 = MRxSmbProcessClientMoveNotification(a2, v14, v23);
          SmbCeDereferenceServerEntryEx(v14, 0, v13);
        }
        else
        {
          v5 = -1073741275;
        }
        a1[23] = 0;
      }
    }
  }
  else
  {
    v5 = -1073741808;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids, a3);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14007f8e4  push    rbx
0x14007f8e6  push    rbp
0x14007f8e7  push    rsi
0x14007f8e8  push    rdi
0x14007f8e9  sub     rsp, 48h
0x14007f8ed  mov     rdi, rdx
0x14007f8f0  mov     rbp, rcx
0x14007f8f3  cmp     r8d, 8
0x14007f8f7  jb      loc_14007FD24
0x14007f8fd  mov     ecx, [rdx+4]
0x14007f900  sub     ecx, 1
0x14007f903  jz      loc_14007FB1F
0x14007f909  sub     ecx, 1
0x14007f90c  jz      short loc_14007F917
0x14007f90e  cmp     ecx, 1
0x14007f911  jnz     loc_14007FD24
0x14007f917  xorps   xmm0, xmm0
0x14007f91a  movups  [rsp+68h+var_38], xmm0
0x14007f91f  cmp     r8d, 18h
0x14007f923  jnb     short loc_14007F973
0x14007f925  mov     ebx, 0C0000010h
0x14007f92a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007f931  lea     rax, WPP_GLOBAL_Control
0x14007f938  cmp     rcx, rax
0x14007f93b  jz      loc_14007FD29
0x14007f941  mov     eax, [rcx+2Ch]
0x14007f944  test    al, 1
0x14007f946  jz      loc_14007FD29
0x14007f94c  cmp     byte ptr [rcx+29h], 1
0x14007f950  jb      loc_14007FD29
0x14007f956  mov     rcx, [rcx+18h]
0x14007f95a  mov     r9d, r8d
0x14007f95d  lea     r8, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids
0x14007f964  mov     edx, 2Ah ; '*'
0x14007f969  call    WPP_SF_d
0x14007f96e  jmp     loc_14007FD29
0x14007f973  mov     r9d, [rdx+8]
0x14007f977  mov     r10d, [rdx+0Ch]
0x14007f97b  lea     eax, [r9+r10]
0x14007f97f  cmp     eax, r9d
0x14007f982  jb      loc_14007FACF
0x14007f988  cmp     r8d, eax
0x14007f98b  jb      loc_14007FACF
0x14007f991  mov     r10d, [rdx+14h]
0x14007f995  mov     ecx, 0FFFFFFFFh
0x14007f99a  lea     rax, [r10+r10*2]
0x14007f99e  shl     rax, 3
0x14007f9a2  cmp     rax, rcx
0x14007f9a5  ja      loc_14007FA8F
0x14007f9ab  lea     ecx, [rax+18h]
0x14007f9ae  cmp     ecx, eax
0x14007f9b0  jb      loc_14007FA8F
0x14007f9b6  cmp     r8d, ecx
0x14007f9b9  jb      loc_14007FA8F
0x14007f9bf  lea     rax, [rdx+r9]
0x14007f9c3  mov     qword ptr [rsp+68h+var_38+8], rax
0x14007f9c8  movzx   eax, word ptr [rdx+0Ch]
0x14007f9cc  mov     word ptr [rsp+68h+var_38+2], ax
0x14007f9d1  mov     word ptr [rsp+68h+var_38], ax
0x14007f9d6  mov     rax, [rbp+28h]
0x14007f9da  mov     rcx, [rax+0B8h]
0x14007f9e1  mov     rcx, [rcx+30h]
0x14007f9e5  call    cs:__imp_IoGetSiloParameters
0x14007f9ec  nop     dword ptr [rax+rax+00h]
0x14007f9f1  test    rax, rax
0x14007f9f4  jz      short loc_14007FA1C
0x14007f9f6  mov     rcx, [rax+8]
0x14007f9fa  call    cs:__imp_PsGetEffectiveServerSilo
0x14007fa01  nop     dword ptr [rax+rax+00h]
0x14007fa06  mov     rcx, rax
0x14007fa09  mov     rbx, rax
0x14007fa0c  call    cs:__imp_PsIsHostSilo
0x14007fa13  nop     dword ptr [rax+rax+00h]
0x14007fa18  test    al, al
0x14007fa1a  jz      short loc_14007FA1E
0x14007fa1c  xor     ebx, ebx
0x14007fa1e  mov     rcx, [rbp+50h]
0x14007fa22  lea     rdx, [rsp+68h+var_38]
0x14007fa27  mov     r8, rbx
0x14007fa2a  mov     rcx, [rcx+1F8h]
0x14007fa31  call    LookupServerEntryByName
0x14007fa36  mov     rsi, rax
0x14007fa39  test    rax, rax
0x14007fa3c  jz      short loc_14007FA7A
0x14007fa3e  mov     al, [rax+2E1h]
0x14007fa44  test    al, 20h
0x14007fa46  jz      short loc_14007FA5C
0x14007fa48  xor     ebx, ebx
0x14007fa4a  cmp     cs:byte_14007D27A, bl
0x14007fa50  jz      short loc_14007FA56
0x14007fa52  test    al, al
0x14007fa54  js      short loc_14007FA6E
0x14007fa56  cmp     dword ptr [rdi+4], 2
0x14007fa5a  jz      short loc_14007FA6E
0x14007fa5c  lea     r8, [rsp+68h+var_38]
0x14007fa61  mov     rdx, rsi
0x14007fa64  mov     rcx, rdi
0x14007fa67  call    MRxSmbProcessClientMoveNotification
0x14007fa6c  mov     ebx, eax
0x14007fa6e  xor     edx, edx
0x14007fa70  mov     rcx, rsi; BugCheckParameter2
0x14007fa73  call    SmbCeDereferenceServerEntryEx
0x14007fa78  jmp     short loc_14007FA7F
0x14007fa7a  mov     ebx, 0C0000225h
0x14007fa7f  mov     qword ptr [rbp+0B8h], 0
0x14007fa8a  jmp     loc_14007FD29
0x14007fa8f  mov     ebx, 0C0000010h
0x14007fa94  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007fa9b  lea     rax, WPP_GLOBAL_Control
0x14007faa2  cmp     rcx, rax
0x14007faa5  jz      loc_14007FD29
0x14007faab  mov     eax, [rcx+2Ch]
0x14007faae  test    al, 1
0x14007fab0  jz      loc_14007FD29
0x14007fab6  cmp     byte ptr [rcx+29h], 1
0x14007faba  jb      loc_14007FD29
0x14007fac0  mov     edx, 2Ch ; ','
0x14007fac5  mov     [rsp+68h+var_48], r8d
0x14007faca  mov     r9d, r10d
0x14007facd  jmp     short loc_14007FB0A
0x14007facf  mov     ebx, 0C0000010h
0x14007fad4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007fadb  lea     rax, WPP_GLOBAL_Control
0x14007fae2  cmp     rcx, rax
0x14007fae5  jz      loc_14007FD29
0x14007faeb  mov     eax, [rcx+2Ch]
0x14007faee  test    al, 1
0x14007faf0  jz      loc_14007FD29
0x14007faf6  cmp     byte ptr [rcx+29h], 1
0x14007fafa  jb      loc_14007FD29
0x14007fb00  mov     edx, 2Bh ; '+'
0x14007fb05  mov     [rsp+68h+var_48], r10d
0x14007fb0a  mov     rcx, [rcx+18h]
0x14007fb0e  lea     r8, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids
0x14007fb15  call    WPP_SF_Dd
0x14007fb1a  jmp     loc_14007FD29
0x14007fb1f  xorps   xmm0, xmm0
0x14007fb22  movups  [rsp+68h+var_38], xmm0
0x14007fb27  cmp     r8d, 34h ; '4'
0x14007fb2b  jb      loc_14007FCEF
0x14007fb31  mov     eax, [rdx+30h]
0x14007fb34  cmp     r8d, eax
0x14007fb37  jb      loc_14007FCEF
0x14007fb3d  cmp     eax, 0FFFEh
0x14007fb42  jnb     loc_14007FCEF
0x14007fb48  add     eax, 34h ; '4'
0x14007fb4b  cmp     r8d, eax
0x14007fb4e  jb      loc_14007FCEF
0x14007fb54  lea     rax, [rdx+34h]
0x14007fb58  mov     qword ptr [rsp+68h+var_38+8], rax
0x14007fb5d  movzx   eax, word ptr [rdx+30h]
0x14007fb61  mov     word ptr [rsp+68h+var_38+2], ax
0x14007fb66  mov     word ptr [rsp+68h+var_38], ax
0x14007fb6b  mov     rax, [rbp+28h]
0x14007fb6f  mov     rcx, [rax+0B8h]
0x14007fb76  mov     rcx, [rcx+30h]
0x14007fb7a  call    cs:__imp_IoGetSiloParameters
0x14007fb81  nop     dword ptr [rax+rax+00h]
0x14007fb86  test    rax, rax
0x14007fb89  jz      short loc_14007FBB1
0x14007fb8b  mov     rcx, [rax+8]
0x14007fb8f  call    cs:__imp_PsGetEffectiveServerSilo
0x14007fb96  nop     dword ptr [rax+rax+00h]
0x14007fb9b  mov     rcx, rax
0x14007fb9e  mov     rbx, rax
0x14007fba1  call    cs:__imp_PsIsHostSilo
0x14007fba8  nop     dword ptr [rax+rax+00h]
0x14007fbad  test    al, al
0x14007fbaf  jz      short loc_14007FBB3
0x14007fbb1  xor     ebx, ebx
0x14007fbb3  mov     rcx, [rbp+50h]
0x14007fbb7  lea     rdx, [rsp+68h+var_38]
0x14007fbbc  mov     r8, rbx
0x14007fbbf  mov     rcx, [rcx+1F8h]
0x14007fbc6  call    LookupServerEntryByName
0x14007fbcb  mov     rbx, rax
0x14007fbce  test    rax, rax
0x14007fbd1  jz      loc_14007FCE4
0x14007fbd7  mov     eax, [rdi+2Ch]
0x14007fbda  cmp     eax, 0FFh
0x14007fbdf  jnz     loc_14007FC93
0x14007fbe5  lea     rdx, [rdi+1Ch]; Source2
0x14007fbe9  mov     r8d, 10h; Length
0x14007fbef  lea     rcx, [rbx+290h]; Source1
0x14007fbf6  call    cs:__imp_RtlCompareMemory
0x14007fbfd  nop     dword ptr [rax+rax+00h]
0x14007fc02  cmp     rax, 10h
0x14007fc06  jnz     short loc_14007FC5C
0x14007fc08  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007fc0f  lea     rax, WPP_GLOBAL_Control
0x14007fc16  cmp     rcx, rax
0x14007fc19  jz      short loc_14007FC40
0x14007fc1b  mov     eax, [rcx+2Ch]
0x14007fc1e  test    al, 40h
0x14007fc20  jz      short loc_14007FC40
0x14007fc22  cmp     byte ptr [rcx+29h], 2
0x14007fc26  jb      short loc_14007FC40
0x14007fc28  mov     rcx, [rcx+18h]
0x14007fc2c  lea     r8, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids
0x14007fc33  mov     edx, 27h ; '''
0x14007fc38  mov     r9, rbx
0x14007fc3b  call    WPP_SF_q
0x14007fc40  or      r8d, 0FFFFFFFFh
0x14007fc44  xor     edx, edx
0x14007fc46  mov     rcx, rbx
0x14007fc49  call    SmbCeSuspendServerConnections
0x14007fc4e  mov     al, [rbx+2E1h]
0x14007fc54  and     al, 0Ch
0x14007fc56  cmp     al, 0Ch
0x14007fc58  jz      short loc_14007FCD0
0x14007fc5a  jmp     short loc_14007FCDA
0x14007fc5c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007fc63  lea     rax, WPP_GLOBAL_Control
0x14007fc6a  cmp     rcx, rax
0x14007fc6d  jz      short loc_14007FCDA
0x14007fc6f  mov     eax, [rcx+2Ch]
0x14007fc72  test    al, 1
0x14007fc74  jz      short loc_14007FCDA
0x14007fc76  cmp     byte ptr [rcx+29h], 1
0x14007fc7a  jb      short loc_14007FCDA
0x14007fc7c  mov     rcx, [rcx+18h]
0x14007fc80  lea     r8, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids
0x14007fc87  mov     edx, 28h ; '('
0x14007fc8c  call    WPP_SF_
0x14007fc91  jmp     short loc_14007FCDA
0x14007fc93  cmp     eax, 1
0x14007fc96  jnz     short loc_14007FCDA
0x14007fc98  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007fc9f  lea     rax, WPP_GLOBAL_Control
0x14007fca6  cmp     rcx, rax
0x14007fca9  jz      short loc_14007FCD0
0x14007fcab  mov     eax, [rcx+2Ch]
0x14007fcae  test    al, 40h
0x14007fcb0  jz      short loc_14007FCD0
0x14007fcb2  cmp     byte ptr [rcx+29h], 2
0x14007fcb6  jb      short loc_14007FCD0
0x14007fcb8  mov     rcx, [rcx+18h]
0x14007fcbc  lea     r8, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids
0x14007fcc3  mov     edx, 29h ; ')'
0x14007fcc8  mov     r9, rbx
0x14007fccb  call    WPP_SF_q
0x14007fcd0  xor     edx, edx
0x14007fcd2  mov     rcx, rbx
0x14007fcd5  call    SmbCeUnSuspendServerConnections
0x14007fcda  xor     edx, edx
0x14007fcdc  mov     rcx, rbx; BugCheckParameter2
0x14007fcdf  call    SmbCeDereferenceServerEntryEx
0x14007fce4  xor     ebx, ebx
0x14007fce6  mov     [rbp+0B8h], rbx
0x14007fced  jmp     short loc_14007FD29
0x14007fcef  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007fcf6  lea     rax, WPP_GLOBAL_Control
0x14007fcfd  cmp     rcx, rax
0x14007fd00  jz      short loc_14007FD24
0x14007fd02  mov     eax, [rcx+2Ch]
0x14007fd05  test    al, 1
0x14007fd07  jz      short loc_14007FD24
0x14007fd09  cmp     byte ptr [rcx+29h], 1
0x14007fd0d  jb      short loc_14007FD24
0x14007fd0f  mov     rcx, [rcx+18h]
0x14007fd13  lea     r8, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids
0x14007fd1a  mov     edx, 26h ; '&'
0x14007fd1f  call    WPP_SF_
0x14007fd24  mov     ebx, 0C0000010h
0x14007fd29  mov     eax, ebx
0x14007fd2b  add     rsp, 48h
0x14007fd2f  pop     rdi
0x14007fd30  pop     rsi
0x14007fd31  pop     rbp
0x14007fd32  pop     rbx
0x14007fd33  retn
```
