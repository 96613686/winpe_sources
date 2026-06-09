# MRxSmb2QueryFsInformation

- ea: `0x140016510`
- end: `0x1400166de`
- name: `MRxSmb2QueryFsInformation`
- size: `462`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140016510`
- `0x1400166f0`

## import_xrefs

- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140016654`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400166ca`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140016654`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400166ca`
- `mrxsmb!SmbCeInitiateExchange` at `0x140016632`
- `mrxsmb!SmbCeInitiateExchange` at `0x140016632`
- `mrxsmb!SmbCeInitializeExchange` at `0x1400165d3`
- `mrxsmb!SmbCeInitializeExchange` at `0x1400165d3`

## pseudocode

```c
__int64 __fastcall MRxSmb2QueryFsInformation(__int64 a1)
{
  __int64 v1; // rax
  int v3; // edi
  __int64 v4; // rbp
  _DWORD *v5; // rdx
  unsigned int FsInformationFromVolumeCache; // esi
  __int64 v8; // rax
  _DWORD *v9; // rcx
  int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v3 = *(_DWORD *)(a1 + 448);
  v4 = *(_QWORD *)(v1 + 120);
  if ( v3 == 0xFFFF )
  {
    __debugbreak();
    goto LABEL_8;
  }
  if ( v3 != 4 )
  {
    if ( v3 == 1 || v3 == 5 )
    {
      FsInformationFromVolumeCache = MRxSmb2QueryFsInformationFromVolumeCache(a1);
      if ( FsInformationFromVolumeCache != -1073741802 )
      {
LABEL_11:
        if ( (FsInformationFromVolumeCache & 0x80000000) != 0 )
          return FsInformationFromVolumeCache;
        v9 = *(_DWORD **)(a1 + 456);
        if ( v3 == 3 )
        {
          v10 = v9[4] * v9[5];
        }
        else
        {
          if ( v3 != 7 )
            return FsInformationFromVolumeCache;
          v10 = v9[6] * v9[7];
        }
        v11 = v10 & 0xFFFE0;
        if ( v11 < 0x200 )
          v11 = 512;
        *(_DWORD *)(v4 + 104) = v11;
        return FsInformationFromVolumeCache;
      }
    }
LABEL_8:
    v8 = *(_QWORD *)(a1 + 72);
    v12 = 0;
    FsInformationFromVolumeCache = SmbCeInitializeExchange(
                                     &v12,
                                     a1,
                                     0,
                                     0,
                                     0,
                                     *(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL),
                                     2600,
                                     &QueryInfoDispatch);
    if ( !FsInformationFromVolumeCache )
    {
      *(_DWORD *)(v12 + 2424) = v3;
      *(_DWORD *)(v12 + 2420) = 2;
      *(_QWORD *)(v12 + 2408) = *(_QWORD *)(a1 + 456);
      *(_DWORD *)(v12 + 2416) = *(_DWORD *)(a1 + 472);
      _InterlockedOr((volatile signed __int32 *)(v12 + 68), 1u);
      FsInformationFromVolumeCache = SmbCeInitiateExchange(v12);
      if ( FsInformationFromVolumeCache == 259 )
        FsInformationFromVolumeCache = SmbCeWaitForCompletionAndFinalizeExchangeEx(v12, 0, 0, 0);
      else
        SmbCeWaitForCompletionAndFinalizeExchangeEx(v12, 0, 0, 0);
    }
    goto LABEL_11;
  }
  if ( *(_DWORD *)(a1 + 472) >= 8u )
  {
    v5 = *(_DWORD **)(a1 + 456);
    v5[1] = 16;
    *v5 = *(_DWORD *)(*(_QWORD *)(v1 + 120) + 80LL);
    *(_DWORD *)(a1 + 472) -= 8;
    return 0;
  }
  return 3221225507LL;
}

```

## disassembly

```asm
0x140016510  push    rbx
0x140016512  push    rbp
0x140016513  push    rsi
0x140016514  push    rdi
0x140016515  sub     rsp, 48h
0x140016519  mov     rax, [rcx+38h]
0x14001651d  mov     rbx, rcx
0x140016520  mov     edi, [rcx+1C0h]
0x140016526  mov     rbp, [rax+78h]
0x14001652a  cmp     edi, 0FFFFh
0x140016530  jz      loc_1400166D8
0x140016536  cmp     edi, 4
0x140016539  jnz     short loc_140016574
0x14001653b  cmp     dword ptr [rcx+1D8h], 8
0x140016542  jb      loc_1400166A4
0x140016548  mov     rdx, [rcx+1C8h]
0x14001654f  mov     dword ptr [rdx+4], 10h
0x140016556  mov     rax, [rax+78h]
0x14001655a  mov     ecx, [rax+50h]
0x14001655d  mov     [rdx], ecx
0x14001655f  add     dword ptr [rbx+1D8h], 0FFFFFFF8h
0x140016566  xor     esi, esi
0x140016568  mov     eax, esi
0x14001656a  add     rsp, 48h
0x14001656e  pop     rdi
0x14001656f  pop     rsi
0x140016570  pop     rbp
0x140016571  pop     rbx
0x140016572  retn
0x140016574  mov     ecx, edi
0x140016576  sub     ecx, 1
0x140016579  jnz     loc_1400166B3
0x14001657f  mov     rcx, rbx
0x140016582  call    MRxSmb2QueryFsInformationFromVolumeCache
0x140016587  mov     esi, eax
0x140016589  cmp     eax, 0C0000016h
0x14001658e  jnz     loc_140016662
0x140016594  mov     rax, [rbx+48h]
0x140016598  lea     rcx, QueryInfoDispatch
0x14001659f  mov     [rsp+68h+var_30], rcx
0x1400165a4  xor     esi, esi
0x1400165a6  mov     [rsp+68h+arg_0], rsi
0x1400165ab  lea     rcx, [rsp+68h+arg_0]
0x1400165b0  mov     [rsp+68h+var_38], 0A28h
0x1400165b8  xor     r9d, r9d
0x1400165bb  mov     rax, [rax+28h]
0x1400165bf  xor     r8d, r8d
0x1400165c2  mov     rdx, rbx
0x1400165c5  mov     rax, [rax+28h]
0x1400165c9  mov     [rsp+68h+var_40], rax
0x1400165ce  mov     [rsp+68h+var_48], rsi
0x1400165d3  call    cs:__imp_SmbCeInitializeExchange
0x1400165da  nop     dword ptr [rax+rax+00h]
0x1400165df  mov     esi, eax
0x1400165e1  test    eax, eax
0x1400165e3  jnz     short loc_140016662
0x1400165e5  mov     rax, [rsp+68h+arg_0]
0x1400165ea  mov     [rax+978h], edi
0x1400165f0  mov     rax, [rsp+68h+arg_0]
0x1400165f5  mov     dword ptr [rax+974h], 2
0x1400165ff  mov     rax, [rsp+68h+arg_0]
0x140016604  mov     rcx, [rbx+1C8h]
0x14001660b  mov     [rax+968h], rcx
0x140016612  mov     rax, [rsp+68h+arg_0]
0x140016617  mov     ecx, [rbx+1D8h]
0x14001661d  mov     [rax+970h], ecx
0x140016623  mov     rax, [rsp+68h+arg_0]
0x140016628  lock or dword ptr [rax+44h], 1
0x14001662d  mov     rcx, [rsp+68h+arg_0]
0x140016632  call    cs:__imp_SmbCeInitiateExchange
0x140016639  nop     dword ptr [rax+rax+00h]
0x14001663e  mov     rcx, [rsp+68h+arg_0]
0x140016643  xor     r9d, r9d
0x140016646  xor     r8d, r8d
0x140016649  xor     edx, edx
0x14001664b  mov     esi, eax
0x14001664d  cmp     eax, 103h
0x140016652  jnz     short loc_1400166CA
0x140016654  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x14001665b  nop     dword ptr [rax+rax+00h]
0x140016660  mov     esi, eax
0x140016662  test    esi, esi
0x140016664  js      loc_140016568
0x14001666a  mov     rcx, [rbx+1C8h]
0x140016671  cmp     edi, 3
0x140016674  jz      short loc_1400166C1
0x140016676  cmp     edi, 7
0x140016679  jnz     loc_140016568
0x14001667f  mov     eax, [rcx+1Ch]
0x140016682  imul    eax, [rcx+18h]
0x140016686  and     eax, 0FFFE0h
0x14001668b  mov     ecx, 200h
0x140016690  cmp     eax, ecx
0x140016692  cmovb   eax, ecx
0x140016695  mov     [rbp+68h], eax
0x140016698  mov     eax, esi
0x14001669a  add     rsp, 48h
0x14001669e  pop     rdi
0x14001669f  pop     rsi
0x1400166a0  pop     rbp
0x1400166a1  pop     rbx
0x1400166a2  retn
0x1400166a4  mov     eax, 0C0000023h
0x1400166a9  add     rsp, 48h
0x1400166ad  pop     rdi
0x1400166ae  pop     rsi
0x1400166af  pop     rbp
0x1400166b0  pop     rbx
0x1400166b1  retn
0x1400166b3  cmp     ecx, 4
0x1400166b6  jnz     loc_140016594
0x1400166bc  jmp     loc_14001657F
0x1400166c1  mov     eax, [rcx+14h]
0x1400166c4  imul    eax, [rcx+10h]
0x1400166c8  jmp     short loc_140016686
0x1400166ca  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x1400166d1  nop     dword ptr [rax+rax+00h]
0x1400166d6  jmp     short loc_140016662
0x1400166d8  int     3; Trap to Debugger
0x1400166d9  jmp     loc_140016594
```
