# PortMgrCreateNewPort

- ea: `0x18001fb58`
- end: `0x18001fe52`
- name: `PortMgrCreateNewPort`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180012cc0`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000c5a0`
- `0x180010ae0`
- `0x180013560`
- `0x18001c2f4`
- `0x18001c6c0`
- `0x18001d7f8`
- `0x18001fb58`
- `0x1800214f0`
- `0x1800235a4`
- `0x180023640`
- `0x1800238b8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001fd98`
- `MobileNetworking!ReleaseWriteLock` at `0x18001fd98`
- `MobileNetworking!AcquireWriteLock` at `0x18001fd48`
- `MobileNetworking!AcquireWriteLock` at `0x18001fd48`
- `MobileNetworking!AllocateMemory` at `0x18001fc1c`
- `MobileNetworking!AllocateMemory` at `0x18001fc1c`
- `MobileNetworking!FreeMemory` at `0x18001fd1a`
- `MobileNetworking!FreeMemory` at `0x18001fd1a`

## string_xrefs

- `0x18001fc0c`: `PortMgrCreateNewPort`
- `0x18001fd0f`: `PortMgrCreateNewPort`
- `0x18001fd33`: `PortMgrCreateNewPort`
- `0x18001fd6c`: `PortMgrCreateNewPort`

## pseudocode

```c
__int64 __fastcall PortMgrCreateNewPort(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  unsigned int Memory; // eax
  __int64 v11; // rdx
  __int64 v12; // rdi
  unsigned int inited; // eax
  unsigned int updated; // eax
  __int64 *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD v20[3]; // [rsp+30h] [rbp-18h] BYREF

  v20[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 39, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
  if ( !*a5 || (unsigned int)PortMgrFindInGlobalListAndRemove(*a5, 0) )
  {
    *a5 = 0;
    Memory = AllocateMemory(3000, v20, "PortMgrCreateNewPort", 378);
    v8 = Memory;
    if ( Memory )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v8;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_32;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, Memory);
      goto LABEL_31;
    }
    *(_DWORD *)(v20[0] + 20LL) = _InterlockedIncrement(&dword_18003DD88);
    v12 = *(unsigned int *)(v20[0] + 20LL);
    inited = PortMgrInitPort(v20[0], v11, a4);
    v8 = inited;
    if ( inited )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          42,
          WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids,
          (unsigned int)v12,
          inited);
    }
    else
    {
      updated = PortMgrUpdatePortCharacterstics(v20[0], a2, a3, a4);
      v8 = updated;
      if ( !updated )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v20[0] + 16LL));
        AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrCreateNewPort", 404);
        v15 = (__int64 *)qword_18003DD70;
        if ( *(__int64 **)qword_18003DD70 != &qword_18003DD68 )
          __fastfail(3u);
        v16 = v20[0];
        *(_QWORD *)v20[0] = &qword_18003DD68;
        *(_QWORD *)(v16 + 8) = v15;
        *v15 = v16;
        qword_18003DD70 = v16;
        ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrCreateNewPort", 406);
        _InterlockedIncrement((volatile signed __int32 *)&qword_18003DD8C);
        _InterlockedIncrement((_DWORD *)&qword_18003DD8C + 1);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            44,
            (unsigned int)WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids,
            v12,
            v20[0] + 220LL);
        NetTraceMarkContextActivityStart(v12, (unsigned int)v12);
        if ( (byte_18003DF41 & 0x10) != 0 )
          McTemplateU0qz_EtwEventWriteTransfer(v18, v17, (unsigned int)v12, v20[0] + 220LL);
        *a5 = v20[0];
        goto LABEL_31;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          43,
          WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids,
          (unsigned int)v12,
          updated);
      PortMgrDeInitPort(v20[0]);
    }
    FreeMemory(v20, "PortMgrCreateNewPort", 434);
LABEL_31:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_32;
  }
  v8 = 1247;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 40, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, *a5);
    goto LABEL_31;
  }
LABEL_32:
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D(v9[7], 45, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18001fb58  push    rbp
0x18001fb5a  push    rbx
0x18001fb5b  push    rsi
0x18001fb5c  push    rdi
0x18001fb5d  push    r12
0x18001fb5f  push    r13
0x18001fb61  push    r14
0x18001fb63  push    r15
0x18001fb65  mov     rbp, rsp
0x18001fb68  sub     rsp, 48h
0x18001fb6c  mov     r14, r9
0x18001fb6f  mov     [rbp+var_18], 0
0x18001fb77  mov     r15, r8
0x18001fb7a  mov     r12d, edx
0x18001fb7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb84  lea     r13, WPP_GLOBAL_Control
0x18001fb8b  cmp     rcx, r13
0x18001fb8e  jz      short loc_18001FBAE
0x18001fb90  test    dword ptr [rcx+44h], 800h
0x18001fb97  jz      short loc_18001FBAE
0x18001fb99  mov     rcx, [rcx+38h]
0x18001fb9d  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001fba4  mov     edx, 27h ; '''
0x18001fba9  call    WPP_SF_
0x18001fbae  mov     rsi, [rbp+arg_20]
0x18001fbb2  mov     rcx, [rsi]
0x18001fbb5  test    rcx, rcx
0x18001fbb8  jz      short loc_18001FBFF
0x18001fbba  xor     edx, edx
0x18001fbbc  call    PortMgrFindInGlobalListAndRemove
0x18001fbc1  test    eax, eax
0x18001fbc3  jnz     short loc_18001FBFF
0x18001fbc5  mov     ebx, 4DFh
0x18001fbca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbd1  cmp     rcx, r13
0x18001fbd4  jz      loc_18001FE3F
0x18001fbda  test    byte ptr [rcx+44h], 1
0x18001fbde  jz      loc_18001FE19
0x18001fbe4  mov     r9, [rsi]
0x18001fbe7  lea     edx, [rax+28h]
0x18001fbea  mov     rcx, [rcx+38h]
0x18001fbee  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001fbf5  call    WPP_SF_q
0x18001fbfa  jmp     loc_18001FE12
0x18001fbff  mov     r9d, 17Ah
0x18001fc05  mov     qword ptr [rsi], 0
0x18001fc0c  lea     r8, aPortmgrcreaten; "PortMgrCreateNewPort"
0x18001fc13  mov     ecx, 0BB8h
0x18001fc18  lea     rdx, [rbp+var_18]
0x18001fc1c  call    cs:__imp_AllocateMemory
0x18001fc22  mov     ebx, eax
0x18001fc24  test    eax, eax
0x18001fc26  jz      short loc_18001FC5F
0x18001fc28  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc2f  cmp     rcx, r13
0x18001fc32  jz      loc_18001FE3F
0x18001fc38  test    byte ptr [rcx+44h], 1
0x18001fc3c  jz      loc_18001FE19
0x18001fc42  mov     rcx, [rcx+38h]
0x18001fc46  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001fc4d  mov     edx, 29h ; ')'
0x18001fc52  mov     r9d, eax
0x18001fc55  call    WPP_SF_d
0x18001fc5a  jmp     loc_18001FE12
0x18001fc5f  mov     rcx, [rbp+var_18]
0x18001fc63  mov     eax, 1
0x18001fc68  lock xadd cs:dword_18003DD88, eax
0x18001fc70  inc     eax
0x18001fc72  mov     r8, r14
0x18001fc75  mov     [rcx+14h], eax
0x18001fc78  mov     rcx, [rbp+var_18]
0x18001fc7c  mov     edi, [rcx+14h]
0x18001fc7f  call    PortMgrInitPort
0x18001fc84  mov     ebx, eax
0x18001fc86  test    eax, eax
0x18001fc88  jz      short loc_18001FCBA
0x18001fc8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc91  cmp     rcx, r13
0x18001fc94  jz      short loc_18001FD09
0x18001fc96  test    byte ptr [rcx+44h], 1
0x18001fc9a  jz      short loc_18001FD09
0x18001fc9c  mov     rcx, [rcx+38h]
0x18001fca0  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001fca7  mov     edx, 2Ah ; '*'
0x18001fcac  mov     dword ptr [rsp+48h+var_28], eax
0x18001fcb0  mov     r9d, edi
0x18001fcb3  call    WPP_SF_dd
0x18001fcb8  jmp     short loc_18001FD09
0x18001fcba  mov     rcx, [rbp+var_18]
0x18001fcbe  mov     r9, r14
0x18001fcc1  mov     r8, r15
0x18001fcc4  mov     edx, r12d
0x18001fcc7  call    PortMgrUpdatePortCharacterstics
0x18001fccc  mov     ebx, eax
0x18001fcce  test    eax, eax
0x18001fcd0  jz      short loc_18001FD25
0x18001fcd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcd9  cmp     rcx, r13
0x18001fcdc  jz      short loc_18001FD00
0x18001fcde  test    byte ptr [rcx+44h], 1
0x18001fce2  jz      short loc_18001FD00
0x18001fce4  mov     rcx, [rcx+38h]
0x18001fce8  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001fcef  mov     edx, 2Bh ; '+'
0x18001fcf4  mov     dword ptr [rsp+48h+var_28], eax
0x18001fcf8  mov     r9d, edi
0x18001fcfb  call    WPP_SF_dd
0x18001fd00  mov     rcx, [rbp+var_18]
0x18001fd04  call    PortMgrDeInitPort
0x18001fd09  mov     r8d, 1B2h
0x18001fd0f  lea     rdx, aPortmgrcreaten; "PortMgrCreateNewPort"
0x18001fd16  lea     rcx, [rbp+var_18]
0x18001fd1a  call    cs:__imp_FreeMemory
0x18001fd20  jmp     loc_18001FE12
0x18001fd25  mov     rax, [rbp+var_18]
0x18001fd29  lock inc dword ptr [rax+10h]
0x18001fd2d  mov     r9d, 194h
0x18001fd33  lea     r8, aPortmgrcreaten; "PortMgrCreateNewPort"
0x18001fd3a  lea     rdx, qword_18003DD98
0x18001fd41  lea     rcx, g_OneXInfo
0x18001fd48  call    cs:__imp_AcquireWriteLock
0x18001fd4e  mov     rcx, cs:qword_18003DD70
0x18001fd55  lea     rdx, qword_18003DD68
0x18001fd5c  cmp     [rcx], rdx
0x18001fd5f  jz      short loc_18001FD68
0x18001fd61  mov     ecx, 3
0x18001fd66  int     29h; Win8: RtlFailFast(ecx)
0x18001fd68  mov     rax, [rbp+var_18]
0x18001fd6c  lea     r8, aPortmgrcreaten; "PortMgrCreateNewPort"
0x18001fd73  mov     r9d, 196h
0x18001fd79  mov     [rax], rdx
0x18001fd7c  lea     rdx, qword_18003DD98
0x18001fd83  mov     [rax+8], rcx
0x18001fd87  mov     [rcx], rax
0x18001fd8a  lea     rcx, g_OneXInfo
0x18001fd91  mov     cs:qword_18003DD70, rax
0x18001fd98  call    cs:__imp_ReleaseWriteLock
0x18001fd9e  lock inc dword ptr cs:qword_18003DD8C
0x18001fda5  lock inc dword ptr cs:qword_18003DD8C+4
0x18001fdac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdb3  cmp     rcx, r13
0x18001fdb6  jz      short loc_18001FDE5
0x18001fdb8  test    byte ptr [rcx+44h], 4
0x18001fdbc  jz      short loc_18001FDE5
0x18001fdbe  mov     rax, [rbp+var_18]
0x18001fdc2  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001fdc9  mov     rcx, [rcx+38h]
0x18001fdcd  add     rax, 0DCh
0x18001fdd3  mov     edx, 2Ch ; ','
0x18001fdd8  mov     [rsp+48h+var_28], rax
0x18001fddd  mov     r9d, edi
0x18001fde0  call    WPP_SF_dS
0x18001fde5  mov     rcx, rdi
0x18001fde8  mov     edx, edi
0x18001fdea  call    NetTraceMarkContextActivityStart
0x18001fdef  test    cs:byte_18003DF41, 10h
0x18001fdf6  jz      short loc_18001FE0B
0x18001fdf8  mov     r9, [rbp+var_18]
0x18001fdfc  mov     r8d, edi
0x18001fdff  add     r9, 0DCh
0x18001fe06  call    McTemplateU0qz_EtwEventWriteTransfer
0x18001fe0b  mov     rax, [rbp+var_18]
0x18001fe0f  mov     [rsi], rax
0x18001fe12  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe19  cmp     rcx, r13
0x18001fe1c  jz      short loc_18001FE3F
0x18001fe1e  test    dword ptr [rcx+44h], 800h
0x18001fe25  jz      short loc_18001FE3F
0x18001fe27  mov     rcx, [rcx+38h]
0x18001fe2b  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001fe32  mov     edx, 2Dh ; '-'
0x18001fe37  mov     r9d, ebx
0x18001fe3a  call    WPP_SF_D
0x18001fe3f  mov     eax, ebx
0x18001fe41  add     rsp, 48h
0x18001fe45  pop     r15
0x18001fe47  pop     r14
0x18001fe49  pop     r13
0x18001fe4b  pop     r12
0x18001fe4d  pop     rdi
0x18001fe4e  pop     rsi
0x18001fe4f  pop     rbx
0x18001fe50  pop     rbp
0x18001fe51  retn
```
