# MsQuicConnectionSetConfiguration

- ea: `0x140022710`
- end: `0x1400228b0`
- name: `MsQuicConnectionSetConfiguration`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000c440`
- `0x14000c4b8`
- `0x140022710`
- `0x14002974c`
- `0x140029ef0`
- `0x1400337e4`
- `0x14003eca4`
- `0x14003ed00`
- `0x140040c2c`

## string_xrefs

- `0x14002284d`: `CONN_SET_CONFIGURATION operation`

## pseudocode

```c
__int64 __fastcall MsQuicConnectionSetConfiguration(unsigned int *a1, __int64 a2)
{
  unsigned int *v3; // rbx
  unsigned int v4; // ebx
  __int64 v5; // rdx

  v3 = a1;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 16, a1);
  if ( !a2 || *(_DWORD *)a2 != 1 || !v3 )
    goto LABEL_27;
  a1 = (unsigned int *)*v3;
  if ( (unsigned int)((_DWORD)a1 - 3) > 1 )
  {
    if ( (_DWORD)a1 == 5 )
    {
      if ( (v3[23] & 8) != 0 )
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 464, "!Stream->Flags.HandleClosed");
      if ( (v3[23] & 0x40) != 0 )
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 465, "!Stream->Flags.Freed");
      v3 = (unsigned int *)*((_QWORD *)v3 + 9);
      goto LABEL_13;
    }
LABEL_27:
    v4 = -1073741811;
    goto LABEL_28;
  }
LABEL_13:
  if ( (v3[63] & 0x40) != 0 && (*((_BYTE *)v3 + 249) & 4) != 0 )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 472, "!Connection->State.Freed");
    __int2c();
  }
  if ( (unsigned __int8)QuicConnIsClient(v3) )
    goto LABEL_27;
  if ( *((_QWORD *)v3 + 11) )
  {
    v4 = -1073741436;
    goto LABEL_28;
  }
  if ( !*(_QWORD *)(a2 + 48) )
    goto LABEL_27;
  if ( (v3[63] & 0x40) != 0 && (*((_BYTE *)v3 + 249) & 2) != 0 )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 491, "!Connection->State.HandleClosed");
    __int2c();
  }
  if ( QuicOperationAlloc(*((_QWORD *)v3 + 9), 0) )
  {
    CxPlatRefIncrement(a2 + 40);
    **(_DWORD **)(v5 + 24) = 3;
    *(_QWORD *)(*(_QWORD *)(v5 + 24) + 24LL) = a2;
    QuicConnQueueOper(v3, v5);
    v4 = 259;
  }
  else
  {
    v4 = -1073741801;
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(a1, 0, "CONN_SET_CONFIGURATION operation", 0);
  }
LABEL_28:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(a1, QuicApiExitStatus, v4);
  return v4;
}

```

## disassembly

```asm
0x140022710  mov     [rsp+arg_0], rbx
0x140022715  push    rdi
0x140022716  sub     rsp, 20h
0x14002271a  test    cs:Microsoft_QuicEnableBits, 8
0x140022721  mov     rdi, rdx
0x140022724  mov     rbx, rcx
0x140022727  jz      short loc_140022737
0x140022729  mov     r9, rcx
0x14002272c  mov     r8d, 10h
0x140022732  call    McTemplateU0qp_EtwWriteTransfer
0x140022737  test    rdi, rdi
0x14002273a  jz      loc_140022885
0x140022740  cmp     dword ptr [rdi], 1
0x140022743  jnz     loc_140022885
0x140022749  test    rbx, rbx
0x14002274c  jz      loc_140022885
0x140022752  mov     ecx, [rbx]
0x140022754  lea     eax, [rcx-3]
0x140022757  cmp     eax, 1
0x14002275a  jbe     short loc_1400227A5
0x14002275c  cmp     ecx, 5
0x14002275f  jnz     loc_140022885
0x140022765  test    byte ptr [rbx+5Ch], 8
0x140022769  jz      short loc_140022783
0x14002276b  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x140022772  mov     edx, 1D0h
0x140022777  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14002277e  call    CxPlatLogAssert
0x140022783  test    byte ptr [rbx+5Ch], 40h
0x140022787  jz      short loc_1400227A1
0x140022789  lea     r8, aStreamFlagsFre; "!Stream->Flags.Freed"
0x140022790  mov     edx, 1D1h
0x140022795  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14002279c  call    CxPlatLogAssert
0x1400227a1  mov     rbx, [rbx+48h]
0x1400227a5  test    byte ptr [rbx+0FCh], 40h
0x1400227ac  jz      short loc_1400227D1
0x1400227ae  test    byte ptr [rbx+0F9h], 4
0x1400227b5  jz      short loc_1400227D1
0x1400227b7  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x1400227be  mov     edx, 1D8h
0x1400227c3  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x1400227ca  call    CxPlatLogAssert
0x1400227cf  int     2Ch; Windows NT - assertion failure
0x1400227d1  mov     rcx, rbx
0x1400227d4  call    QuicConnIsClient
0x1400227d9  test    al, al
0x1400227db  jnz     loc_140022885
0x1400227e1  cmp     qword ptr [rbx+58h], 0
0x1400227e6  jz      short loc_1400227F2
0x1400227e8  mov     ebx, 0C0000184h
0x1400227ed  jmp     loc_14002288A
0x1400227f2  cmp     qword ptr [rdi+30h], 0
0x1400227f7  jz      loc_140022885
0x1400227fd  test    byte ptr [rbx+0FCh], 40h
0x140022804  jz      short loc_140022829
0x140022806  test    byte ptr [rbx+0F9h], 2
0x14002280d  jz      short loc_140022829
0x14002280f  lea     r8, aConnectionStat_0; "!Connection->State.HandleClosed"
0x140022816  mov     edx, 1EBh
0x14002281b  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x140022822  call    CxPlatLogAssert
0x140022827  int     2Ch; Windows NT - assertion failure
0x140022829  mov     rcx, [rbx+48h]
0x14002282d  xor     edx, edx
0x14002282f  call    QuicOperationAlloc
0x140022834  mov     rdx, rax
0x140022837  test    rax, rax
0x14002283a  jnz     short loc_14002285B
0x14002283c  test    cs:Microsoft_QuicEnableBits, 2
0x140022843  mov     ebx, 0C0000017h
0x140022848  jz      short loc_14002288A
0x14002284a  xor     r9d, r9d
0x14002284d  lea     r8, aConnSetConfigu; "CONN_SET_CONFIGURATION operation"
0x140022854  call    McTemplateU0sx_EtwWriteTransfer
0x140022859  jmp     short loc_14002288A
0x14002285b  lea     rcx, [rdi+28h]
0x14002285f  call    CxPlatRefIncrement
0x140022864  mov     rax, [rdx+18h]
0x140022868  mov     rcx, rbx
0x14002286b  mov     dword ptr [rax], 3
0x140022871  mov     rax, [rdx+18h]
0x140022875  mov     [rax+18h], rdi
0x140022879  call    QuicConnQueueOper
0x14002287e  mov     ebx, 103h
0x140022883  jmp     short loc_14002288A
0x140022885  mov     ebx, 0C000000Dh
0x14002288a  test    cs:Microsoft_QuicEnableBits, 8
0x140022891  jz      short loc_1400228A2
0x140022893  mov     r8d, ebx
0x140022896  lea     rdx, QuicApiExitStatus
0x14002289d  call    McTemplateU0q_EtwWriteTransfer
0x1400228a2  mov     eax, ebx
0x1400228a4  mov     rbx, [rsp+28h+arg_0]
0x1400228a9  add     rsp, 20h
0x1400228ad  pop     rdi
0x1400228ae  retn
```
