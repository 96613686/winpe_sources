# ProcessTimeout

- ea: `0x1800181b0`
- end: `0x1800183d1`
- name: `ProcessTimeout`
- size: `545`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003170`
- `0x18000c8d4`
- `0x18000cc7c`
- `0x18000e7a4`
- `0x18000f780`
- `0x1800102bc`
- `0x180011230`
- `0x1800115a0`
- `0x1800115d0`
- `0x180012e38`
- `0x180013b54`
- `0x1800181b0`
- `0x18001ae70`

## string_xrefs

- `0x180018334`: `Closing down since completion routine not called`

## pseudocode

```c
int __fastcall ProcessTimeout(__int64 a1)
{
  _DWORD *PCBPointerFromhPort; // rax
  __int64 v3; // rbx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rdx
  unsigned int i; // edi
  __int64 PointerToCPCB; // rax
  unsigned int CpIndexFromProtocol; // eax

  PCBPointerFromhPort = (_DWORD *)GetPCBPointerFromhPort(*(_QWORD *)(a1 + 16));
  v3 = (__int64)PCBPointerFromhPort;
  if ( !PCBPointerFromhPort || *(_DWORD *)(a1 + 52) != PCBPointerFromhPort[16] )
    return (int)PCBPointerFromhPort;
  v4 = *(_DWORD *)(a1 + 68);
  if ( !v4 )
  {
    CpIndexFromProtocol = GetCpIndexFromProtocol(*(unsigned int *)(a1 + 60));
    LODWORD(PCBPointerFromhPort) = FsmTimeout(v3, CpIndexFromProtocol, *(_DWORD *)(a1 + 56), *(_DWORD *)(a1 + 64));
    return (int)PCBPointerFromhPort;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v11 = 1;
    goto LABEL_40;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    LODWORD(PCBPointerFromhPort) = FsmThisLayerFinished(v3, 0, 0);
    return (int)PCBPointerFromhPort;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    if ( (*(_BYTE *)(v3 + 56) & 4) != 0 )
    {
      if ( *(_DWORD *)(v3 + 48) == 3 )
      {
        for ( i = 1; ; ++i )
        {
          PCBPointerFromhPort = (_DWORD *)GetPointerToCPCB(v3, i);
          if ( i >= (unsigned int)PppConfigInfo )
            break;
          if ( PCBPointerFromhPort[11] && PCBPointerFromhPort[14] == 1 )
            goto LABEL_36;
        }
        if ( *PCBPointerFromhPort != 9 || PCBPointerFromhPort[14] != 1 )
          return (int)PCBPointerFromhPort;
        if ( (byte_18004DF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasPppTraceInfo,
            L"Closing down since completion routine not called");
        PointerToCPCB = GetPointerToCPCB(v3, i);
        v15 = 732;
        *(_DWORD *)(PointerToCPCB + 40) = 732;
LABEL_37:
        LODWORD(PCBPointerFromhPort) = NotifyCallerOfFailure(v3, v15);
        return (int)PCBPointerFromhPort;
      }
    }
    else
    {
      PCBPointerFromhPort = *(_DWORD **)(v3 + 8);
      if ( PCBPointerFromhPort[330] != 2 && (*(_DWORD *)(v3 + 56) & 0x800) == 0 )
        return (int)PCBPointerFromhPort;
    }
LABEL_36:
    v15 = 718;
    *(_DWORD *)(v3 + 1496) = 718;
    goto LABEL_37;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v14 = *(_QWORD *)(v3 + 8);
    v15 = 932;
    *(_DWORD *)(v3 + 1496) = 932;
    if ( (*(_DWORD *)(v14 + 52) & 0x4000) != 0 )
      *(_DWORD *)(v3 + 56) |= 0x40000u;
    goto LABEL_37;
  }
  v9 = v8 - 2;
  if ( v9 )
  {
    LODWORD(PCBPointerFromhPort) = v9 - 1;
    if ( (_DWORD)PCBPointerFromhPort )
    {
      if ( (_DWORD)PCBPointerFromhPort == 1 )
      {
        v10 = GetCpIndexFromProtocol(*(unsigned int *)(a1 + 60));
        LODWORD(PCBPointerFromhPort) = (unsigned int)FsmTimeoutConfRecv(
                                                       v3,
                                                       v10,
                                                       *(_DWORD *)(a1 + 56),
                                                       *(_DWORD *)(a1 + 64));
      }
      return (int)PCBPointerFromhPort;
    }
    v11 = 7;
LABEL_40:
    LODWORD(PCBPointerFromhPort) = CheckCpsForInactivity(v3, v11);
    return (int)PCBPointerFromhPort;
  }
  MakeStopOrInterimAccountingCall(v3, 1);
  v12 = *(_QWORD *)(v3 + 168);
  if ( !v12 && *(_QWORD *)(v3 + 160) )
    v12 = *(_QWORD *)(v3 + 160);
  PCBPointerFromhPort = (_DWORD *)RasAuthAttributeGet(85, v12);
  if ( PCBPointerFromhPort )
  {
    v13 = PCBPointerFromhPort[2];
    if ( v13 < 0x3C )
      v13 = 60;
    LODWORD(PCBPointerFromhPort) = InsertInTimerQ(*(_DWORD *)(v3 + 64), *(_QWORD *)(v3 + 16), 0, 0, 0, 6, v13);
  }
  return (int)PCBPointerFromhPort;
}

```

## disassembly

```asm
0x1800181b0  mov     [rsp+arg_8], rbx
0x1800181b5  push    rdi
0x1800181b6  sub     rsp, 40h
0x1800181ba  mov     rdi, rcx
0x1800181bd  mov     rcx, [rcx+10h]
0x1800181c1  call    GetPCBPointerFromhPort
0x1800181c6  mov     rbx, rax
0x1800181c9  test    rax, rax
0x1800181cc  jz      loc_1800183C5
0x1800181d2  mov     edx, [rax+40h]
0x1800181d5  cmp     [rdi+34h], edx
0x1800181d8  jnz     loc_1800183C5
0x1800181de  mov     eax, [rdi+44h]
0x1800181e1  test    eax, eax
0x1800181e3  jz      loc_1800183AB
0x1800181e9  sub     eax, 1
0x1800181ec  jz      loc_18001839C
0x1800181f2  sub     eax, 1
0x1800181f5  jz      loc_18001838D
0x1800181fb  sub     eax, 1
0x1800181fe  jz      loc_1800182E1
0x180018204  sub     eax, 1
0x180018207  jz      loc_1800182BB
0x18001820d  sub     eax, 2
0x180018210  jz      short loc_180018249
0x180018212  sub     eax, 1
0x180018215  jz      short loc_18001823F
0x180018217  cmp     eax, 1
0x18001821a  jnz     loc_1800183C5
0x180018220  mov     ecx, [rdi+3Ch]
0x180018223  call    GetCpIndexFromProtocol
0x180018228  mov     r9d, [rdi+40h]
0x18001822c  mov     edx, eax
0x18001822e  mov     r8d, [rdi+38h]
0x180018232  mov     rcx, rbx
0x180018235  call    FsmTimeoutConfRecv
0x18001823a  jmp     loc_1800183C5
0x18001823f  mov     edx, 7
0x180018244  jmp     loc_1800183A1
0x180018249  mov     edx, 1
0x18001824e  mov     rcx, rbx
0x180018251  call    MakeStopOrInterimAccountingCall
0x180018256  mov     rdx, [rbx+0A8h]
0x18001825d  test    rdx, rdx
0x180018260  jnz     short loc_180018270
0x180018262  mov     rax, [rbx+0A0h]
0x180018269  test    rax, rax
0x18001826c  cmovnz  rdx, rax
0x180018270  mov     ecx, 55h ; 'U'
0x180018275  call    RasAuthAttributeGet
0x18001827a  test    rax, rax
0x18001827d  jz      loc_1800183C5
0x180018283  mov     eax, [rax+8]
0x180018286  mov     ecx, 3Ch ; '<'
0x18001828b  mov     rdx, [rbx+10h]
0x18001828f  cmp     eax, ecx
0x180018291  cmovb   eax, ecx
0x180018294  mov     ecx, [rbx+40h]
0x180018297  mov     [rsp+48h+var_18], eax
0x18001829b  xor     r9d, r9d
0x18001829e  mov     [rsp+48h+var_20], 6
0x1800182a6  xor     r8d, r8d
0x1800182a9  mov     [rsp+48h+var_28], 0
0x1800182b1  call    InsertInTimerQ
0x1800182b6  jmp     loc_1800183C5
0x1800182bb  mov     rax, [rbx+8]
0x1800182bf  mov     edx, 3A4h
0x1800182c4  mov     [rbx+5D8h], edx
0x1800182ca  test    dword ptr [rax+34h], 4000h
0x1800182d1  jz      loc_180018383
0x1800182d7  bts     dword ptr [rbx+38h], 12h
0x1800182dc  jmp     loc_180018383
0x1800182e1  test    byte ptr [rbx+38h], 4
0x1800182e5  jz      short loc_180018362
0x1800182e7  cmp     dword ptr [rbx+30h], 3
0x1800182eb  jnz     loc_180018378
0x1800182f1  mov     edi, 1
0x1800182f6  mov     edx, edi
0x1800182f8  mov     rcx, rbx
0x1800182fb  call    GetPointerToCPCB
0x180018300  cmp     edi, dword ptr cs:PppConfigInfo
0x180018306  jnb     short loc_180018318
0x180018308  cmp     dword ptr [rax+2Ch], 0
0x18001830c  jz      short loc_180018314
0x18001830e  cmp     dword ptr [rax+38h], 1
0x180018312  jz      short loc_180018378
0x180018314  inc     edi
0x180018316  jmp     short loc_1800182F6
0x180018318  cmp     dword ptr [rax], 9
0x18001831b  jnz     loc_1800183C5
0x180018321  cmp     dword ptr [rax+38h], 1
0x180018325  jnz     loc_1800183C5
0x18001832b  test    cs:byte_18004DF34, 1
0x180018332  jz      short loc_18001834E
0x180018334  lea     r8, aClosingDownSin; "Closing down since completion routine n"...
0x18001833b  lea     rdx, RasPppTraceInfo
0x180018342  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180018349  call    McTemplateU0z_EventWriteTransfer
0x18001834e  mov     edx, edi
0x180018350  mov     rcx, rbx
0x180018353  call    GetPointerToCPCB
0x180018358  mov     edx, 2DCh
0x18001835d  mov     [rax+28h], edx
0x180018360  jmp     short loc_180018383
0x180018362  mov     rax, [rbx+8]
0x180018366  cmp     dword ptr [rax+528h], 2
0x18001836d  jz      short loc_180018378
0x18001836f  test    dword ptr [rbx+38h], 800h
0x180018376  jz      short loc_1800183C5
0x180018378  mov     edx, 2CEh
0x18001837d  mov     [rbx+5D8h], edx
0x180018383  mov     rcx, rbx
0x180018386  call    NotifyCallerOfFailure
0x18001838b  jmp     short loc_1800183C5
0x18001838d  xor     r8d, r8d
0x180018390  xor     edx, edx
0x180018392  mov     rcx, rbx
0x180018395  call    FsmThisLayerFinished
0x18001839a  jmp     short loc_1800183C5
0x18001839c  mov     edx, 1
0x1800183a1  mov     rcx, rbx
0x1800183a4  call    CheckCpsForInactivity
0x1800183a9  jmp     short loc_1800183C5
0x1800183ab  mov     ecx, [rdi+3Ch]
0x1800183ae  call    GetCpIndexFromProtocol
0x1800183b3  mov     r9d, [rdi+40h]
0x1800183b7  mov     edx, eax
0x1800183b9  mov     r8d, [rdi+38h]
0x1800183bd  mov     rcx, rbx
0x1800183c0  call    FsmTimeout
0x1800183c5  mov     rbx, [rsp+48h+arg_8]
0x1800183ca  add     rsp, 40h
0x1800183ce  pop     rdi
0x1800183cf  retn
```
