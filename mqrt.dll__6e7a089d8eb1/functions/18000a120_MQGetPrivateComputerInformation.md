# MQGetPrivateComputerInformation

- ea: `0x18000a120`
- end: `0x18000a335`
- name: `MQGetPrivateComputerInformation`
- size: `533`
- prototype: `HRESULT __stdcall(LPCWSTR lpwcsComputerName, MQPRIVATEPROPS *pPrivateProps)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180005488`
- `0x18000a120`
- `0x18000c4ec`
- `0x180010a58`
- `0x180013c74`
- `0x180014458`
- `0x180017ce0`
- `0x180021010`
- `0x180021060`
- `0x180023c36`

## pseudocode

```c
HRESULT __stdcall MQGetPrivateComputerInformation(LPCWSTR lpwcsComputerName, MQPRIVATEPROPS *pPrivateProps)
{
  int v4; // ebx
  unsigned __int16 v5; // r8
  int *v7; // r12
  int *aStatus; // r13
  int v9; // ebx
  int v10; // eax
  int v11; // esi
  __int64 i; // r14
  MQPROPVARIANT *v13; // rbx
  __int64 v14; // rcx
  MQPROPVARIANT *aPropVar; // rax
  __int64 v16; // [rsp+0h] [rbp-88h] BYREF
  HRESULT v17; // [rsp+20h] [rbp-68h]
  HRESULT v18; // [rsp+24h] [rbp-64h]
  int v19; // [rsp+28h] [rbp-60h]
  int *v20; // [rsp+30h] [rbp-58h]
  __int64 *v21; // [rsp+38h] [rbp-50h]
  int v22; // [rsp+40h] [rbp-48h]
  int v23; // [rsp+44h] [rbp-44h]
  unsigned int v24; // [rsp+48h] [rbp-40h]

  v21 = &v16;
  v4 = RtpOneTimeThreadInit();
  if ( v4 < 0 )
  {
    v5 = 1109;
LABEL_3:
    LogMsgHR(v4, (wchar_t *)L"rt/machine", v5);
    return v4;
  }
  v24 = 2;
  if ( lpwcsComputerName )
  {
    v5 = 110;
    v4 = -1072824314;
    goto LABEL_3;
  }
  v7 = 0;
  v20 = 0;
  aStatus = pPrivateProps->aStatus;
  if ( !aStatus )
  {
    v7 = (int *)MmAllocate(saturated_mul(pPrivateProps->cProp, 4u));
    v20 = v7;
    aStatus = v7;
  }
  v9 = RTpCheckComputerProps(pPrivateProps, aStatus);
  v10 = RTpConvertToMQCode(v9, 2u);
  v11 = v10;
  v22 = v10;
  v23 = v9;
  if ( v10 >= 0 )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v19 = i;
      if ( (unsigned int)i >= pPrivateProps->cProp )
        break;
      if ( !aStatus[i] )
      {
        if ( pPrivateProps->aPropID[i] == 5801 )
        {
          v14 = i;
          aPropVar = pPrivateProps->aPropVar;
          aPropVar[v14].lVal = 67184411;
          aPropVar[v14].vt = 19;
        }
        else
        {
          if ( pPrivateProps->aPropID[i] != 5802 )
          {
            v18 = LogHR(-1072824318, (wchar_t *)L"rt/machine", 0x82u);
            local_unwind_0(v21, &loc_18000A27A);
            return v18;
          }
          v13 = pPrivateProps->aPropVar;
          v13[i].iVal = IsWorkGroupMode() - 1;
          v13[i].vt = 11;
        }
      }
    }
    MmDeallocate(v7);
    if ( v11 < 0 )
      LogMsgHR(v11, (wchar_t *)L"rt/machine", 0x96u);
    return v11;
  }
  else
  {
    v17 = LogHR(v10, (wchar_t *)L"rt/machine", 0x78u);
    local_unwind_0(v21, &loc_18000A20B);
    return v17;
  }
}

```

## disassembly

```asm
0x18000a120  push    rbx
0x18000a122  push    rsi
0x18000a123  push    rdi
0x18000a124  push    r12
0x18000a126  push    r13
0x18000a128  push    r14
0x18000a12a  push    r15
0x18000a12c  sub     rsp, 50h
0x18000a130  mov     [rsp+88h+var_50], rsp
0x18000a135  mov     r15, rdx
0x18000a138  mov     rdi, rcx
0x18000a13b  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x18000a140  mov     ebx, eax
0x18000a142  test    eax, eax
0x18000a144  jns     short loc_18000A16C
0x18000a146  mov     r8d, 455h; unsigned __int16
0x18000a14c  lea     rdx, aRtMachine; "rt/machine"
0x18000a153  mov     ecx, ebx; int
0x18000a155  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000a15a  mov     eax, ebx
0x18000a15c  add     rsp, 50h
0x18000a160  pop     r15
0x18000a162  pop     r14
0x18000a164  pop     r13
0x18000a166  pop     r12
0x18000a168  pop     rdi
0x18000a169  pop     rsi
0x18000a16a  pop     rbx
0x18000a16b  retn
0x18000a16c  mov     esi, 2
0x18000a171  mov     [rsp+88h+var_40], esi
0x18000a175  test    rdi, rdi
0x18000a178  jz      short loc_18000A185
0x18000a17a  lea     r8d, [rsi+6Ch]
0x18000a17e  mov     ebx, 0C00E0006h
0x18000a183  jmp     short loc_18000A14C
0x18000a185  xor     r12d, r12d
0x18000a188  mov     [rsp+88h+var_58], r12
0x18000a18d  mov     r13, [r15+18h]
0x18000a191  test    r13, r13
0x18000a194  jnz     short loc_18000A1BD
0x18000a196  mov     ecx, [r15]
0x18000a199  lea     eax, [r12+4]
0x18000a19e  mul     rcx
0x18000a1a1  lea     rcx, [r12-1]
0x18000a1a6  cmovb   rax, rcx
0x18000a1aa  mov     rcx, rax; unsigned __int64
0x18000a1ad  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000a1b2  mov     r12, rax
0x18000a1b5  mov     [rsp+88h+var_58], rax
0x18000a1ba  mov     r13, rax
0x18000a1bd  mov     rdx, r13; int *
0x18000a1c0  mov     rcx, r15; struct tagMQPRIVATEPROPS *
0x18000a1c3  call    ?RTpCheckComputerProps@@YAJPEAUtagMQPRIVATEPROPS@@PEAJ@Z; RTpCheckComputerProps(tagMQPRIVATEPROPS *,long *)
0x18000a1c8  mov     ebx, eax
0x18000a1ca  mov     edx, esi; unsigned int
0x18000a1cc  mov     ecx, eax; int
0x18000a1ce  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000a1d3  mov     esi, eax
0x18000a1d5  mov     [rsp+88h+var_48], eax
0x18000a1d9  mov     [rsp+88h+var_44], ebx
0x18000a1dd  test    eax, eax
0x18000a1df  jns     short loc_18000A214
0x18000a1e1  mov     r8d, 78h ; 'x'; unsigned __int16
0x18000a1e7  lea     rdx, aRtMachine; "rt/machine"
0x18000a1ee  mov     ecx, eax; int
0x18000a1f0  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000a1f5  mov     [rsp+88h+var_68], eax
0x18000a1f9  lea     rdx, loc_18000A20B
0x18000a200  mov     rcx, [rsp+88h+var_50]
0x18000a205  call    _local_unwind_0
0x18000a20a  nop
0x18000a20b  mov     eax, [rsp+88h+var_68]
0x18000a20f  jmp     loc_18000A15C
0x18000a214  xor     r14d, r14d
0x18000a217  lea     r9d, [r14+1]
0x18000a21b  mov     [rsp+88h+var_60], r14d
0x18000a220  cmp     r14d, [r15]
0x18000a223  jnb     loc_18000A2CD
0x18000a229  cmp     dword ptr [r13+r14*4+0], 0
0x18000a22f  jz      short loc_18000A236
0x18000a231  jmp     loc_18000A2C5
0x18000a236  mov     rcx, [r15+8]
0x18000a23a  mov     r8d, [rcx+r14*4]
0x18000a23e  sub     r8d, 16A9h
0x18000a245  jz      short loc_18000A2AC
0x18000a247  cmp     r8d, 1
0x18000a24b  jz      short loc_18000A283
0x18000a24d  mov     r8d, 82h; unsigned __int16
0x18000a253  lea     rdx, aRtMachine; "rt/machine"
0x18000a25a  mov     ecx, 0C00E0002h; int
0x18000a25f  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000a264  mov     [rsp+88h+var_64], eax
0x18000a268  lea     rdx, loc_18000A27A
0x18000a26f  mov     rcx, [rsp+88h+var_50]
0x18000a274  call    _local_unwind_0
0x18000a279  nop
0x18000a27a  mov     eax, [rsp+88h+var_64]
0x18000a27e  jmp     loc_18000A15C
0x18000a283  lea     rdi, [r14+r14*2]
0x18000a287  mov     rbx, [r15+10h]
0x18000a28b  call    ?IsWorkGroupMode@@YA_NXZ; IsWorkGroupMode(void)
0x18000a290  movzx   eax, al
0x18000a293  mov     r9d, 1
0x18000a299  sub     ax, r9w
0x18000a29d  mov     [rbx+rdi*8+8], ax
0x18000a2a2  lea     eax, [r9+0Ah]
0x18000a2a6  mov     [rbx+rdi*8], ax
0x18000a2aa  jmp     short loc_18000A2C5
0x18000a2ac  lea     rcx, [r14+r14*2]
0x18000a2b0  mov     rax, [r15+10h]
0x18000a2b4  mov     dword ptr [rax+rcx*8+8], 401271Bh
0x18000a2bc  mov     edx, 13h
0x18000a2c1  mov     [rax+rcx*8], dx
0x18000a2c5  add     r14d, r9d
0x18000a2c8  jmp     loc_18000A21B
0x18000a2cd  jmp     short loc_18000A30E
0x18000a2cf  mov     ebx, eax
0x18000a2d1  mov     edx, [rsp+88h+var_40]; unsigned int
0x18000a2d5  mov     ecx, eax; int
0x18000a2d7  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000a2dc  mov     esi, eax
0x18000a2de  mov     [rsp+88h+var_48], eax
0x18000a2e2  mov     [rsp+88h+var_44], ebx
0x18000a2e6  test    eax, eax
0x18000a2e8  jg      short loc_18000A2EE
0x18000a2ea  mov     ecx, eax
0x18000a2ec  jmp     short loc_18000A2F7
0x18000a2ee  movzx   ecx, ax
0x18000a2f1  or      ecx, 80070000h; int
0x18000a2f7  mov     r8d, 8Ch; unsigned __int16
0x18000a2fd  lea     rdx, aRtMachine; "rt/machine"
0x18000a304  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000a309  mov     r12, [rsp+88h+var_58]
0x18000a30e  mov     rcx, r12; void *
0x18000a311  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x18000a316  test    esi, esi
0x18000a318  jns     short loc_18000A32E
0x18000a31a  mov     r8d, 96h; unsigned __int16
0x18000a320  lea     rdx, aRtMachine; "rt/machine"
0x18000a327  mov     ecx, esi; int
0x18000a329  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000a32e  mov     eax, esi
0x18000a330  jmp     loc_18000A15C
0x18002432c  push    rbp
0x18002432e  sub     rsp, 20h
0x180024332  mov     rbp, rdx
0x180024335  mov     rcx, [rbp+30h]; void *
0x180024339  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x18002433e  nop
0x18002433f  add     rsp, 20h
0x180024343  pop     rbp
0x180024344  retn
```
