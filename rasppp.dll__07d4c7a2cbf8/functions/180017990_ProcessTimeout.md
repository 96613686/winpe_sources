# ProcessTimeout

- ea: `0x180017990`
- end: `0x180017bb0`
- name: `ProcessTimeout`
- size: `544`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003110`
- `0x18000c4ac`
- `0x18000c854`
- `0x18000e364`
- `0x18000f334`
- `0x18000fe04`
- `0x180010cfc`
- `0x180011038`
- `0x180011064`
- `0x180012794`
- `0x180013490`
- `0x180017990`
- `0x18001a4bc`

## string_xrefs

- `0x180017b14`: `Closing down since completion routine not called`

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
        if ( (byte_18004CF34 & 1) != 0 )
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
0x180017990  mov     [rsp+arg_8], rbx
0x180017995  push    rdi
0x180017996  sub     rsp, 40h
0x18001799a  mov     rdi, rcx
0x18001799d  mov     rcx, [rcx+10h]
0x1800179a1  call    GetPCBPointerFromhPort
0x1800179a6  mov     rbx, rax
0x1800179a9  test    rax, rax
0x1800179ac  jz      loc_180017BA5
0x1800179b2  mov     edx, [rax+40h]
0x1800179b5  cmp     [rdi+34h], edx
0x1800179b8  jnz     loc_180017BA5
0x1800179be  mov     eax, [rdi+44h]
0x1800179c1  test    eax, eax
0x1800179c3  jz      loc_180017B8B
0x1800179c9  sub     eax, 1
0x1800179cc  jz      loc_180017B7C
0x1800179d2  sub     eax, 1
0x1800179d5  jz      loc_180017B6D
0x1800179db  sub     eax, 1
0x1800179de  jz      loc_180017AC1
0x1800179e4  sub     eax, 1
0x1800179e7  jz      loc_180017A9B
0x1800179ed  sub     eax, 2
0x1800179f0  jz      short loc_180017A29
0x1800179f2  sub     eax, 1
0x1800179f5  jz      short loc_180017A1F
0x1800179f7  cmp     eax, 1
0x1800179fa  jnz     loc_180017BA5
0x180017a00  mov     ecx, [rdi+3Ch]
0x180017a03  call    GetCpIndexFromProtocol
0x180017a08  mov     r9d, [rdi+40h]
0x180017a0c  mov     edx, eax
0x180017a0e  mov     r8d, [rdi+38h]
0x180017a12  mov     rcx, rbx
0x180017a15  call    FsmTimeoutConfRecv
0x180017a1a  jmp     loc_180017BA5
0x180017a1f  mov     edx, 7
0x180017a24  jmp     loc_180017B81
0x180017a29  mov     edx, 1
0x180017a2e  mov     rcx, rbx
0x180017a31  call    MakeStopOrInterimAccountingCall
0x180017a36  mov     rdx, [rbx+0A8h]
0x180017a3d  test    rdx, rdx
0x180017a40  jnz     short loc_180017A50
0x180017a42  mov     rax, [rbx+0A0h]
0x180017a49  test    rax, rax
0x180017a4c  cmovnz  rdx, rax
0x180017a50  mov     ecx, 55h ; 'U'
0x180017a55  call    RasAuthAttributeGet
0x180017a5a  test    rax, rax
0x180017a5d  jz      loc_180017BA5
0x180017a63  mov     eax, [rax+8]
0x180017a66  mov     ecx, 3Ch ; '<'
0x180017a6b  mov     rdx, [rbx+10h]
0x180017a6f  cmp     eax, ecx
0x180017a71  cmovb   eax, ecx
0x180017a74  mov     ecx, [rbx+40h]
0x180017a77  mov     [rsp+48h+var_18], eax
0x180017a7b  xor     r9d, r9d
0x180017a7e  mov     [rsp+48h+var_20], 6
0x180017a86  xor     r8d, r8d
0x180017a89  mov     [rsp+48h+var_28], 0
0x180017a91  call    InsertInTimerQ
0x180017a96  jmp     loc_180017BA5
0x180017a9b  mov     rax, [rbx+8]
0x180017a9f  mov     edx, 3A4h
0x180017aa4  mov     [rbx+5D8h], edx
0x180017aaa  test    dword ptr [rax+34h], 4000h
0x180017ab1  jz      loc_180017B63
0x180017ab7  bts     dword ptr [rbx+38h], 12h
0x180017abc  jmp     loc_180017B63
0x180017ac1  test    byte ptr [rbx+38h], 4
0x180017ac5  jz      short loc_180017B42
0x180017ac7  cmp     dword ptr [rbx+30h], 3
0x180017acb  jnz     loc_180017B58
0x180017ad1  mov     edi, 1
0x180017ad6  mov     edx, edi
0x180017ad8  mov     rcx, rbx
0x180017adb  call    GetPointerToCPCB
0x180017ae0  cmp     edi, dword ptr cs:PppConfigInfo
0x180017ae6  jnb     short loc_180017AF8
0x180017ae8  cmp     dword ptr [rax+2Ch], 0
0x180017aec  jz      short loc_180017AF4
0x180017aee  cmp     dword ptr [rax+38h], 1
0x180017af2  jz      short loc_180017B58
0x180017af4  inc     edi
0x180017af6  jmp     short loc_180017AD6
0x180017af8  cmp     dword ptr [rax], 9
0x180017afb  jnz     loc_180017BA5
0x180017b01  cmp     dword ptr [rax+38h], 1
0x180017b05  jnz     loc_180017BA5
0x180017b0b  test    cs:byte_18004CF34, 1
0x180017b12  jz      short loc_180017B2E
0x180017b14  lea     r8, aClosingDownSin; "Closing down since completion routine n"...
0x180017b1b  lea     rdx, RasPppTraceInfo
0x180017b22  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017b29  call    McTemplateU0z_EventWriteTransfer
0x180017b2e  mov     edx, edi
0x180017b30  mov     rcx, rbx
0x180017b33  call    GetPointerToCPCB
0x180017b38  mov     edx, 2DCh
0x180017b3d  mov     [rax+28h], edx
0x180017b40  jmp     short loc_180017B63
0x180017b42  mov     rax, [rbx+8]
0x180017b46  cmp     dword ptr [rax+528h], 2
0x180017b4d  jz      short loc_180017B58
0x180017b4f  test    dword ptr [rbx+38h], 800h
0x180017b56  jz      short loc_180017BA5
0x180017b58  mov     edx, 2CEh
0x180017b5d  mov     [rbx+5D8h], edx
0x180017b63  mov     rcx, rbx
0x180017b66  call    NotifyCallerOfFailure
0x180017b6b  jmp     short loc_180017BA5
0x180017b6d  xor     r8d, r8d
0x180017b70  xor     edx, edx
0x180017b72  mov     rcx, rbx
0x180017b75  call    FsmThisLayerFinished
0x180017b7a  jmp     short loc_180017BA5
0x180017b7c  mov     edx, 1
0x180017b81  mov     rcx, rbx
0x180017b84  call    CheckCpsForInactivity
0x180017b89  jmp     short loc_180017BA5
0x180017b8b  mov     ecx, [rdi+3Ch]
0x180017b8e  call    GetCpIndexFromProtocol
0x180017b93  mov     r9d, [rdi+40h]
0x180017b97  mov     edx, eax
0x180017b99  mov     r8d, [rdi+38h]
0x180017b9d  mov     rcx, rbx
0x180017ba0  call    FsmTimeout
0x180017ba5  mov     rbx, [rsp+48h+arg_8]
0x180017baa  add     rsp, 40h
0x180017bae  pop     rdi
0x180017baf  retn
```
