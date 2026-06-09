# MRxSmb2QueryDirectory

- ea: `0x1400028d0`
- end: `0x140002b71`
- name: `MRxSmb2QueryDirectory`
- size: `673`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400028d0`
- `0x140002b80`
- `0x14002b42c`
- `0x140055650`
- `0x1400575a0`

## import_xrefs

- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140002a5b`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140002b20`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140002a5b`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140002b20`
- `mrxsmb!SmbCeInitiateExchange` at `0x140002a35`
- `mrxsmb!SmbCeInitiateExchange` at `0x140002a35`
- `mrxsmb!SmbCeInitializeExchange` at `0x1400029fc`
- `mrxsmb!SmbCeInitializeExchange` at `0x1400029fc`

## pseudocode

```c
__int64 __fastcall MRxSmb2QueryDirectory(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rcx
  __int64 v4; // rsi
  __int64 v5; // r14
  __int64 v6; // rbp
  int v7; // ecx
  unsigned int v8; // edi
  int v10; // r14d
  int v11; // ecx
  int v12; // [rsp+30h] [rbp-38h]
  int v13; // [rsp+70h] [rbp+8h] BYREF
  __int64 v14; // [rsp+78h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 72);
  v13 = 0;
  v3 = *(_QWORD *)(v1 + 40);
  v4 = *(_QWORD *)(v3 + 40);
  v14 = 0;
  if ( !*(_BYTE *)(a1 + 518) || (*(_BYTE *)(*(_QWORD *)(a1 + 80) + 1314LL) & 4) != 0 )
  {
    v5 = *(_QWORD *)(a1 + 64);
    v6 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 136LL);
    if ( (*(_DWORD *)(v6 + 8) & 2) != 0
      && (int)Smb2FetchVolumeFeatureSupportFromCache(v3, *(_QWORD *)(v4 + 424) + 928LL, *(_QWORD *)(v6 + 32), &v13) >= 0 )
    {
      v7 = *(_DWORD *)(a1 + 448);
      if ( (v7 == 60 || v7 == 63) && (v13 & 2) != 0 )
      {
        v8 = -1073741637;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_dDD(WPP_GLOBAL_Control->AttachedDevice, 19);
        }
        return v8;
      }
      if ( (unsigned int)(v7 - 80) <= 1 && (v13 & 4) != 0 )
      {
        v8 = -1073741637;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_dDD(WPP_GLOBAL_Control->AttachedDevice, 20);
        }
        return v8;
      }
    }
    if ( *(_BYTE *)(a1 + 518) || (v8 = MRxSmb2EnumerateDirectoryFromCache(a1), v8 == -1073741802) )
    {
      v12 = *(unsigned __int16 *)(v5 + 80) + 2552;
      v14 = 0;
      v8 = SmbCeInitializeExchange(&v14, a1, 0, 0, 0, v4, v12, &QueryDirDispatch);
      if ( !v8 )
      {
        v10 = 0;
        *(_DWORD *)(v14 + 2408) = *(_DWORD *)(a1 + 448);
        _InterlockedOr((volatile signed __int32 *)(v14 + 68), 1u);
        v8 = SmbCeInitiateExchange(v14);
        if ( v8 == 259 )
          v8 = SmbCeWaitForCompletionAndFinalizeExchangeEx(v14, 0, 0, 0);
        else
          SmbCeWaitForCompletionAndFinalizeExchangeEx(v14, 0, 0, 0);
        v11 = *(_DWORD *)(a1 + 448);
        if ( (v11 == 60 || v11 == 63) && (v8 + 1073741822 <= 1 || v8 == -1073741637) )
          v10 = 2;
        if ( (unsigned int)(v11 - 80) <= 1 && (v8 + 1073741822 <= 1 || v8 == -1073741637) )
          v10 |= 4u;
        if ( (*(_DWORD *)(v6 + 8) & 2) != 0 )
        {
          if ( v10 )
            Smb2UpdateVolumeFeatureSupportCacheEntry(
              a1,
              (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v4 + 424) + 928LL),
              *(_QWORD *)(v6 + 32),
              v10,
              v8);
        }
      }
    }
    return v8;
  }
  return 3221225474LL;
}

```

## disassembly

```asm
0x1400028d0  push    rbx
0x1400028d2  push    rsi
0x1400028d3  push    rdi
0x1400028d4  push    r15
0x1400028d6  sub     rsp, 48h
0x1400028da  mov     rax, [rcx+48h]
0x1400028de  xor     r15d, r15d
0x1400028e1  mov     rbx, rcx
0x1400028e4  mov     [rsp+68h+arg_0], r15d
0x1400028e9  mov     rcx, [rax+28h]
0x1400028ed  mov     rsi, [rcx+28h]
0x1400028f1  mov     [rsp+68h+arg_8], r15
0x1400028f6  cmp     [rbx+206h], r15b
0x1400028fd  jnz     loc_1400029A2
0x140002903  mov     rax, [rbx+38h]
0x140002907  mov     [rsp+68h+arg_10], rbp
0x14000290f  mov     [rsp+68h+var_28], r14
0x140002914  mov     r14, [rbx+40h]
0x140002918  mov     rbp, [rax+88h]
0x14000291f  mov     eax, [rbp+8]
0x140002922  test    al, 2
0x140002924  jz      short loc_14000296E
0x140002926  mov     rdx, [rsi+1A8h]
0x14000292d  lea     r9, [rsp+68h+arg_0]
0x140002932  mov     r8, [rbp+20h]
0x140002936  add     rdx, 3A0h
0x14000293d  call    Smb2FetchVolumeFeatureSupportFromCache
0x140002942  test    eax, eax
0x140002944  js      short loc_14000296E
0x140002946  mov     ecx, [rbx+1C0h]
0x14000294c  mov     eax, [rsp+68h+arg_0]
0x140002950  cmp     ecx, 3Ch ; '<'
0x140002953  jz      loc_140002AC7
0x140002959  cmp     ecx, 3Fh ; '?'
0x14000295c  jz      loc_140002AC7
0x140002962  add     ecx, 0FFFFFFB0h
0x140002965  cmp     ecx, 1
0x140002968  jbe     loc_140038076
0x14000296e  cmp     [rbx+206h], r15b
0x140002975  jnz     short loc_1400029C5
0x140002977  mov     rcx, rbx
0x14000297a  call    MRxSmb2EnumerateDirectoryFromCache
0x14000297f  mov     edi, eax
0x140002981  cmp     eax, 0C0000016h
0x140002986  jz      short loc_1400029C5
0x140002988  mov     rbp, [rsp+68h+arg_10]
0x140002990  mov     r14, [rsp+68h+var_28]
0x140002995  mov     eax, edi
0x140002997  add     rsp, 48h
0x14000299b  pop     r15
0x14000299d  pop     rdi
0x14000299e  pop     rsi
0x14000299f  pop     rbx
0x1400029a0  retn
0x1400029a2  mov     rax, [rbx+50h]
0x1400029a6  test    byte ptr [rax+522h], 4
0x1400029ad  jnz     loc_140002903
0x1400029b3  mov     edi, 0C0000002h
0x1400029b8  mov     eax, edi
0x1400029ba  add     rsp, 48h
0x1400029be  pop     r15
0x1400029c0  pop     rdi
0x1400029c1  pop     rsi
0x1400029c2  pop     rbx
0x1400029c3  retn
0x1400029c5  movzx   eax, word ptr [r14+50h]
0x1400029ca  lea     rcx, QueryDirDispatch
0x1400029d1  mov     [rsp+68h+var_30], rcx
0x1400029d6  add     eax, 9F8h
0x1400029db  mov     [rsp+68h+var_38], eax
0x1400029df  lea     rcx, [rsp+68h+arg_8]
0x1400029e4  mov     [rsp+68h+var_40], rsi
0x1400029e9  xor     r9d, r9d
0x1400029ec  xor     r8d, r8d
0x1400029ef  mov     [rsp+68h+var_48], r15
0x1400029f4  mov     rdx, rbx
0x1400029f7  mov     [rsp+68h+arg_8], r15
0x1400029fc  call    cs:__imp_SmbCeInitializeExchange
0x140002a03  nop     dword ptr [rax+rax+00h]
0x140002a08  mov     edi, eax
0x140002a0a  test    eax, eax
0x140002a0c  jnz     loc_140002988
0x140002a12  mov     rax, [rsp+68h+arg_8]
0x140002a17  mov     r14d, r15d
0x140002a1a  mov     ecx, [rbx+1C0h]
0x140002a20  mov     [rax+968h], ecx
0x140002a26  mov     rax, [rsp+68h+arg_8]
0x140002a2b  lock or dword ptr [rax+44h], 1
0x140002a30  mov     rcx, [rsp+68h+arg_8]
0x140002a35  call    cs:__imp_SmbCeInitiateExchange
0x140002a3c  nop     dword ptr [rax+rax+00h]
0x140002a41  mov     rcx, [rsp+68h+arg_8]
0x140002a46  xor     r9d, r9d
0x140002a49  xor     r8d, r8d
0x140002a4c  xor     edx, edx
0x140002a4e  mov     edi, eax
0x140002a50  cmp     eax, 103h
0x140002a55  jnz     loc_140002B20
0x140002a5b  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140002a62  nop     dword ptr [rax+rax+00h]
0x140002a67  mov     edi, eax
0x140002a69  mov     ecx, [rbx+1C0h]
0x140002a6f  cmp     ecx, 3Ch ; '<'
0x140002a72  jz      loc_140002B31
0x140002a78  cmp     ecx, 3Fh ; '?'
0x140002a7b  jz      loc_140002B31
0x140002a81  lea     eax, [rcx-50h]
0x140002a84  cmp     eax, 1
0x140002a87  jbe     loc_140002B51
0x140002a8d  mov     eax, [rbp+8]
0x140002a90  test    al, 2
0x140002a92  jz      loc_140002988
0x140002a98  test    r14d, r14d
0x140002a9b  jz      loc_140002988
0x140002aa1  mov     rdx, [rsi+1A8h]
0x140002aa8  mov     r9d, r14d
0x140002aab  mov     r8, [rbp+20h]
0x140002aaf  add     rdx, 3A0h
0x140002ab6  mov     rcx, rbx
0x140002ab9  mov     dword ptr [rsp+68h+var_48], edi
0x140002abd  call    Smb2UpdateVolumeFeatureSupportCacheEntry
0x140002ac2  jmp     loc_140002988
0x140002ac7  test    al, 2
0x140002ac9  jz      loc_140002962
0x140002acf  mov     edi, 0C00000BBh
0x140002ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x140002adb  lea     rdx, WPP_GLOBAL_Control
0x140002ae2  cmp     rcx, rdx
0x140002ae5  jz      loc_140002988
0x140002aeb  mov     edx, [rcx+2Ch]
0x140002aee  test    dl, 2
0x140002af1  jz      loc_140002988
0x140002af7  cmp     byte ptr [rcx+29h], 4
0x140002afb  jb      loc_140002988
0x140002b01  mov     rcx, [rcx+18h]
0x140002b05  mov     edx, 13h
0x140002b0a  mov     dword ptr [rsp+68h+var_40], 2
0x140002b12  mov     dword ptr [rsp+68h+var_48], eax
0x140002b16  call    WPP_SF_dDD
0x140002b1b  jmp     loc_140002988
0x140002b20  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140002b27  nop     dword ptr [rax+rax+00h]
0x140002b2c  jmp     loc_140002A69
0x140002b31  lea     eax, [rdi+3FFFFFFEh]
0x140002b37  cmp     eax, 1
0x140002b3a  jbe     loc_1400380D0
0x140002b40  cmp     edi, 0C00000BBh
0x140002b46  jnz     loc_140002A81
0x140002b4c  jmp     loc_1400380D0
0x140002b51  lea     eax, [rdi+3FFFFFFEh]
0x140002b57  cmp     eax, 1
0x140002b5a  jbe     loc_1400380DB
0x140002b60  cmp     edi, 0C00000BBh
0x140002b66  jnz     loc_140002A8D
0x140002b6c  jmp     loc_1400380DB
0x140038076  test    al, 4
0x140038078  jz      loc_14000296E
0x14003807e  mov     edi, 0C00000BBh
0x140038083  mov     rcx, cs:WPP_GLOBAL_Control
0x14003808a  lea     rdx, WPP_GLOBAL_Control
0x140038091  cmp     rcx, rdx
0x140038094  jz      loc_140002988
0x14003809a  mov     edx, [rcx+2Ch]
0x14003809d  test    dl, 2
0x1400380a0  jz      loc_140002988
0x1400380a6  cmp     byte ptr [rcx+29h], 4
0x1400380aa  jb      loc_140002988
0x1400380b0  mov     rcx, [rcx+18h]
0x1400380b4  mov     edx, 14h
0x1400380b9  mov     dword ptr [rsp+68h+var_40], 4
0x1400380c1  mov     dword ptr [rsp+68h+var_48], eax
0x1400380c5  call    WPP_SF_dDD
0x1400380ca  nop
0x1400380cb  jmp     loc_140002988
0x1400380d0  mov     r14d, 2
0x1400380d6  jmp     loc_140002A81
0x1400380db  or      r14d, 4
0x1400380df  jmp     loc_140002A8D
```
