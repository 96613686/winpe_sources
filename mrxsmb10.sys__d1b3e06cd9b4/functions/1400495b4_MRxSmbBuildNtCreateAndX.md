# MRxSmbBuildNtCreateAndX

- ea: `0x1400495b4`
- end: `0x14004985d`
- name: `MRxSmbBuildNtCreateAndX`
- size: `681`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140047fb0`

## callees

- `0x14000b9c0`
- `0x14000dfa8`
- `0x140046380`
- `0x1400495b4`
- `0x14004a590`

## import_xrefs

- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x140049795`
- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x140049795`

## pseudocode

```c
__int64 __fastcall MRxSmbBuildNtCreateAndX(_QWORD *a1, int *a2)
{
  __int64 v2; // rbx
  int v4; // esi
  char v5; // bp
  unsigned int v6; // r12d
  const UNICODE_STRING *v7; // rdi
  __int64 v8; // r13
  __int64 ExchangeNetRoot; // rax
  int v10; // r11d
  char v11; // cl
  char v12; // r10
  char v13; // r8
  unsigned __int16 v14; // dx
  char v15; // cl
  __int16 v16; // ax
  __int64 *v17; // rax
  unsigned int started; // r14d
  unsigned int v19; // esi
  __int64 v20; // r8
  int v21; // edx
  __int64 Length; // r8
  __int64 v23; // r9
  const char *v24; // rdx
  __int64 v26; // [rsp+20h] [rbp-A8h]
  int v27; // [rsp+28h] [rbp-A0h]

  v2 = a1[6];
  v4 = 0;
  v5 = 1;
  v6 = *(_DWORD *)(v2 + 512);
  v7 = (const UNICODE_STRING *)(*(_QWORD *)(v2 + 56) + 360LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  }
  v8 = *(_QWORD *)(a1[7] + 80LL);
  ExchangeNetRoot = SmbCeGetExchangeNetRoot();
  if ( (*(_DWORD *)(v2 + 512) & 0x23) == 0 || (*(_BYTE *)(v2 + 540) & 1) != 0 )
  {
    v5 = v10;
    *(_DWORD *)(*(_QWORD *)(v2 + 72) + 72LL) |= 0x200u;
  }
  v11 = v10;
  v12 = v10;
  v13 = v10;
  if ( *(_BYTE *)(ExchangeNetRoot + 1) == (_BYTE)v10 )
    v11 = v5;
  v14 = v10;
  if ( !*(_BYTE *)(v8 + 505) )
    v12 = v11;
  while ( v14 < (unsigned __int16)(v7->Length >> 1) )
  {
    if ( v7->Buffer[v14] == 58 )
    {
      v13 = 1;
      break;
    }
    ++v14;
  }
  v15 = v10;
  if ( !v13 )
    v15 = v12;
  if ( MRxSmbOplocksDisabled == (_BYTE)v10 && v15 )
  {
    v16 = *(_WORD *)(v2 + 746);
    v6 = *(_DWORD *)(v2 + 512) & 0xFFEFFFFF;
    if ( (v16 & 0x800) != 0 )
    {
      v4 = v10;
    }
    else if ( (v16 & 0x400) != 0 )
    {
      v4 = 2;
      *(_DWORD *)(v2 + 732) = 9;
    }
    else
    {
      v4 = 6;
      *(_DWORD *)(v2 + 732) = 31;
    }
  }
  if ( v7->Length == (_WORD)v10 )
  {
    v17 = &UnicodeBackslash;
    if ( (*(_BYTE *)(v2 + 746) & 2) == 0 )
      v17 = (__int64 *)v7;
    v7 = (const UNICODE_STRING *)v17;
  }
  started = MRxSmbStartSMBCommand((_DWORD)a1, 2, -94, 51);
  if ( !started )
  {
    v19 = v4 | 0x10;
    v20 = a1[4];
    v21 = *a2;
    *(_DWORD *)(a1[7] + 72LL) |= 0x4000u;
    *(_WORD *)(v20 + 26) = v21;
    *(_WORD *)(v20 + 12) = HIWORD(v21);
    if ( (*(_DWORD *)(v8 + 420) & 0x8000) != 0 )
      Length = v7->Length;
    else
      Length = RtlxUnicodeStringToOemSize(v7);
    MRxSmbStuffSMB(a1, "XmwdddDdddDddyB", Length, v19, 0, v6);
    v24 = "u!";
    if ( (*(_DWORD *)(v8 + 420) & 0x8000) == 0 )
      v24 = "z!";
    MRxSmbStuffSMB(a1, v24, v7, v23, v26, v27);
  }
  return started;
}

```

## disassembly

```asm
0x1400495b4  mov     [rsp+arg_8], rdx
0x1400495b9  push    rbx
0x1400495ba  push    rbp
0x1400495bb  push    rsi
0x1400495bc  push    rdi
0x1400495bd  push    r12
0x1400495bf  push    r13
0x1400495c1  push    r14
0x1400495c3  push    r15
0x1400495c5  sub     rsp, 88h
0x1400495cc  mov     rbx, [rcx+30h]
0x1400495d0  xor     r11d, r11d
0x1400495d3  mov     r15, rcx
0x1400495d6  mov     esi, r11d
0x1400495d9  mov     bpl, 1
0x1400495dc  mov     rdi, [rbx+38h]
0x1400495e0  mov     r12d, [rbx+200h]
0x1400495e7  add     rdi, 168h
0x1400495ee  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400495f5  lea     rax, WPP_GLOBAL_Control
0x1400495fc  cmp     rcx, rax
0x1400495ff  jz      short loc_14004961F
0x140049601  bt      dword ptr [rcx+2Ch], 0Ah
0x140049606  jnb     short loc_14004961F
0x140049608  mov     rcx, [rcx+18h]
0x14004960c  lea     edx, [r11+21h]
0x140049610  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140049617  call    WPP_SF_
0x14004961c  xor     r11d, r11d
0x14004961f  mov     rcx, [r15+38h]
0x140049623  mov     r13, [rcx+50h]
0x140049627  call    SmbCeGetExchangeNetRoot
0x14004962c  mov     ecx, [rbx+200h]
0x140049632  mov     r8, rax
0x140049635  test    cl, 23h
0x140049638  setnz   dl
0x14004963b  test    [rbx+21Ch], bpl
0x140049642  setz    cl
0x140049645  test    cl, dl
0x140049647  jnz     short loc_140049655
0x140049649  mov     rcx, [rbx+48h]
0x14004964d  mov     bpl, r11b
0x140049650  bts     dword ptr [rcx+48h], 9
0x140049655  cmp     [r8+1], r11b
0x140049659  mov     ecx, r11d
0x14004965c  movzx   r9d, word ptr [rdi]
0x140049660  mov     r10d, r11d
0x140049663  movzx   eax, bpl
0x140049667  mov     r8b, r11b
0x14004966a  cmovz   ecx, eax
0x14004966d  mov     edx, r11d
0x140049670  cmp     [r13+1F9h], sil
0x140049677  movzx   eax, cl
0x14004967a  cmovz   r10d, eax
0x14004967e  shr     r9w, 1
0x140049682  cmp     dx, r9w
0x140049686  jnb     short loc_14004969E
0x140049688  mov     rax, [rdi+8]
0x14004968c  movzx   ecx, dx
0x14004968f  cmp     word ptr [rax+rcx*2], 3Ah ; ':'
0x140049694  jz      short loc_14004969B
0x140049696  inc     dx
0x140049699  jmp     short loc_140049682
0x14004969b  mov     r8b, 1
0x14004969e  test    r8b, r8b
0x1400496a1  movzx   eax, r10b
0x1400496a5  mov     ecx, r11d
0x1400496a8  mov     edx, 2
0x1400496ad  cmovz   ecx, eax
0x1400496b0  cmp     cs:MRxSmbOplocksDisabled, r11b
0x1400496b7  jnz     short loc_140049700
0x1400496b9  test    cl, cl
0x1400496bb  jz      short loc_140049700
0x1400496bd  mov     r12d, [rbx+200h]
0x1400496c4  movzx   eax, word ptr [rbx+2EAh]
0x1400496cb  btr     r12d, 14h
0x1400496d0  bt      ax, 0Bh
0x1400496d5  jnb     short loc_1400496DC
0x1400496d7  mov     esi, r11d
0x1400496da  jmp     short loc_140049700
0x1400496dc  bt      ax, 0Ah
0x1400496e1  jnb     short loc_1400496F1
0x1400496e3  mov     esi, edx
0x1400496e5  mov     dword ptr [rbx+2DCh], 9
0x1400496ef  jmp     short loc_140049700
0x1400496f1  mov     esi, 6
0x1400496f6  mov     dword ptr [rbx+2DCh], 1Fh
0x140049700  mov     ebp, [rbx+21Ch]
0x140049706  mov     eax, ebp
0x140049708  btr     eax, 0Ch
0x14004970c  test    dword ptr [r13+1A4h], 100000h
0x140049717  cmovz   ebp, eax
0x14004971a  cmp     [rdi], r11w
0x14004971e  jnz     short loc_140049734
0x140049720  test    [rbx+2EAh], dl
0x140049726  lea     rax, UnicodeBackslash
0x14004972d  cmovz   rax, rdi
0x140049731  mov     rdi, rax
0x140049734  mov     r9d, 33h ; '3'
0x14004973a  mov     [rsp+0C8h+var_A0], 40000h
0x140049742  mov     r8b, 0A2h
0x140049745  mov     rcx, r15
0x140049748  call    MRxSmbStartSMBCommand
0x14004974d  mov     r14d, eax
0x140049750  test    eax, eax
0x140049752  jnz     loc_140049845
0x140049758  mov     rcx, [r15+38h]
0x14004975c  or      esi, 10h
0x14004975f  mov     r8, [r15+20h]
0x140049763  mov     rdx, [rsp+0C8h+arg_8]
0x14004976b  mov     edx, [rdx]
0x14004976d  bts     dword ptr [rcx+48h], 0Eh
0x140049772  mov     [r8+1Ah], dx
0x140049777  shr     edx, 10h
0x14004977a  mov     [r8+0Ch], dx
0x14004977f  test    dword ptr [r13+1A4h], 8000h
0x14004978a  jz      short loc_140049792
0x14004978c  movzx   r8d, word ptr [rdi]
0x140049790  jmp     short loc_1400497A4
0x140049792  mov     rcx, rdi; UnicodeString
0x140049795  call    cs:__imp_RtlxUnicodeStringToOemSize
0x14004979c  nop     dword ptr [rax+rax+00h]
0x1400497a1  mov     r8d, eax
0x1400497a4  mov     rax, [rsp+0C8h+arg_8]
0x1400497ac  lea     rdx, aXmwddddddddddy; "XmwdddDdddDddyB"
0x1400497b3  mov     [rsp+0C8h+var_58], 0
0x1400497bc  mov     r9d, esi
0x1400497bf  movzx   ecx, byte ptr [rax+4]
0x1400497c3  mov     eax, [rbx+20Ch]
0x1400497c9  mov     [rsp+0C8h+var_60], ecx
0x1400497cd  mov     ecx, [rbx+228h]
0x1400497d3  mov     [rsp+0C8h+var_68], ecx
0x1400497d7  mov     ecx, [rbx+218h]
0x1400497dd  mov     [rsp+0C8h+var_70], ebp
0x1400497e1  mov     [rsp+0C8h+var_78], ecx
0x1400497e5  mov     ecx, [rbx+214h]
0x1400497eb  mov     [rsp+0C8h+var_80], ecx
0x1400497ef  mov     ecx, [rbx+210h]
0x1400497f5  mov     [rsp+0C8h+var_88], ecx
0x1400497f9  mov     rcx, r15
0x1400497fc  mov     [rsp+0C8h+var_90], eax
0x140049800  mov     eax, [rbx+208h]
0x140049806  mov     [rsp+0C8h+var_98], eax
0x14004980a  mov     [rsp+0C8h+var_A0], r12d
0x14004980f  mov     [rsp+0C8h+var_A8], 0
0x140049818  call    MRxSmbStuffSMB
0x14004981d  test    dword ptr [r13+1A4h], 8000h
0x140049828  lea     rax, aZ; "z!"
0x14004982f  lea     rdx, aU; "u!"
0x140049836  mov     r8, rdi
0x140049839  cmovz   rdx, rax
0x14004983d  mov     rcx, r15
0x140049840  call    MRxSmbStuffSMB
0x140049845  mov     eax, r14d
0x140049848  add     rsp, 88h
0x14004984f  pop     r15
0x140049851  pop     r14
0x140049853  pop     r13
0x140049855  pop     r12
0x140049857  pop     rdi
0x140049858  pop     rsi
0x140049859  pop     rbp
0x14004985a  pop     rbx
0x14004985b  retn
```
