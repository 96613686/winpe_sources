# MRxSmb2QueryEaInformation

- ea: `0x14001deb0`
- end: `0x14001e023`
- name: `MRxSmb2QueryEaInformation`
- size: `371`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400040a0`
- `0x14001deb0`

## import_xrefs

- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14001dfe0`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14001e005`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14001dfe0`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14001e005`
- `mrxsmb!SmbCeInitiateExchange` at `0x14001dfbe`
- `mrxsmb!SmbCeInitiateExchange` at `0x14001dfbe`
- `mrxsmb!SmbCeInitializeExchange` at `0x14001df17`
- `mrxsmb!SmbCeInitializeExchange` at `0x14001df17`

## pseudocode

```c
__int64 __fastcall MRxSmb2QueryEaInformation(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rsi
  unsigned int v4; // ebp
  __int64 v5; // rax
  int v6; // edi
  __int64 result; // rax
  __int64 v8; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 40);
  v2 = *(_QWORD *)(a1 + 64);
  v4 = 0;
  if ( v1 )
    v4 = *(unsigned __int8 *)(*(_QWORD *)(v1 + 184) + 2LL);
  if ( !*(_DWORD *)(v2 + 96) )
  {
    if ( !*(_DWORD *)(a1 + 520) && !*(_DWORD *)(a1 + 524) && v4 <= 1 )
    {
      LODWORD(v8) = *(_DWORD *)(a1 + 472);
      result = Smb2FetchFileInfoFromCache(
                 a1,
                 *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL) + 424LL) + 376LL,
                 1,
                 15,
                 0,
                 *(_QWORD *)(a1 + 456),
                 &v8);
      if ( (int)result >= 0 )
      {
        *(_DWORD *)(a1 + 472) -= v8;
        return result;
      }
    }
    if ( !*(_DWORD *)(v2 + 96) && (v4 & 4) == 0 )
      v4 |= 1u;
  }
  v5 = *(_QWORD *)(a1 + 72);
  v8 = 0;
  v6 = SmbCeInitializeExchange(&v8, a1, 0, 0, 0, *(_QWORD *)(*(_QWORD *)(v5 + 40) + 40LL), 2600, &QueryInfoDispatch);
  if ( !v6 )
  {
    *(_DWORD *)(v8 + 2424) = 15;
    *(_DWORD *)(v8 + 2420) = 1;
    *(_QWORD *)(v8 + 2408) = *(_QWORD *)(a1 + 456);
    *(_DWORD *)(v8 + 2416) = *(_DWORD *)(a1 + 472);
    *(_DWORD *)(v8 + 2428) = v4;
    *(_QWORD *)(v8 + 2440) = *(_QWORD *)(a1 + 512);
    *(_DWORD *)(v8 + 2448) = *(_DWORD *)(a1 + 520);
    *(_DWORD *)(v8 + 2432) = *(_DWORD *)(a1 + 524);
    _InterlockedOr((volatile signed __int32 *)(v8 + 68), 1u);
    v6 = SmbCeInitiateExchange(v8);
    if ( v6 == 259 )
      v6 = SmbCeWaitForCompletionAndFinalizeExchangeEx(v8, 0, 0, 0);
    else
      SmbCeWaitForCompletionAndFinalizeExchangeEx(v8, 0, 0, 0);
  }
  if ( v6 >= 0 )
    *(_DWORD *)(v2 + 96) = 1;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001deb0  push    rbx
0x14001deb2  push    rbp
0x14001deb3  push    rsi
0x14001deb4  push    rdi
0x14001deb5  sub     rsp, 48h
0x14001deb9  mov     rax, [rcx+28h]
0x14001debd  xor     edi, edi
0x14001debf  mov     rsi, [rcx+40h]
0x14001dec3  mov     rbx, rcx
0x14001dec6  mov     ebp, edi
0x14001dec8  test    rax, rax
0x14001decb  jnz     loc_14001E013
0x14001ded1  cmp     [rsi+60h], edi
0x14001ded4  jz      loc_14003C020
0x14001deda  mov     rax, [rbx+48h]
0x14001dede  lea     rcx, QueryInfoDispatch
0x14001dee5  mov     [rsp+68h+var_30], rcx
0x14001deea  xor     r9d, r9d
0x14001deed  mov     [rsp+68h+arg_0], rdi
0x14001def2  lea     rcx, [rsp+68h+arg_0]
0x14001def7  mov     dword ptr [rsp+68h+var_38], 0A28h
0x14001deff  xor     r8d, r8d
0x14001df02  mov     rax, [rax+28h]
0x14001df06  mov     rdx, rbx
0x14001df09  mov     rax, [rax+28h]
0x14001df0d  mov     [rsp+68h+var_40], rax
0x14001df12  mov     [rsp+68h+var_48], rdi
0x14001df17  call    cs:__imp_SmbCeInitializeExchange
0x14001df1e  nop     dword ptr [rax+rax+00h]
0x14001df23  mov     edi, eax
0x14001df25  test    eax, eax
0x14001df27  jnz     loc_14001DFEE
0x14001df2d  mov     rax, [rsp+68h+arg_0]
0x14001df32  mov     dword ptr [rax+978h], 0Fh
0x14001df3c  mov     rax, [rsp+68h+arg_0]
0x14001df41  mov     dword ptr [rax+974h], 1
0x14001df4b  mov     rcx, [rbx+1C8h]
0x14001df52  mov     rax, [rsp+68h+arg_0]
0x14001df57  mov     [rax+968h], rcx
0x14001df5e  mov     rax, [rsp+68h+arg_0]
0x14001df63  mov     ecx, [rbx+1D8h]
0x14001df69  mov     [rax+970h], ecx
0x14001df6f  mov     rax, [rsp+68h+arg_0]
0x14001df74  mov     [rax+97Ch], ebp
0x14001df7a  mov     rax, [rsp+68h+arg_0]
0x14001df7f  mov     rcx, [rbx+200h]
0x14001df86  mov     [rax+988h], rcx
0x14001df8d  mov     rax, [rsp+68h+arg_0]
0x14001df92  mov     ecx, [rbx+208h]
0x14001df98  mov     [rax+990h], ecx
0x14001df9e  mov     rax, [rsp+68h+arg_0]
0x14001dfa3  mov     ecx, [rbx+20Ch]
0x14001dfa9  mov     [rax+980h], ecx
0x14001dfaf  mov     rax, [rsp+68h+arg_0]
0x14001dfb4  lock or dword ptr [rax+44h], 1
0x14001dfb9  mov     rcx, [rsp+68h+arg_0]
0x14001dfbe  call    cs:__imp_SmbCeInitiateExchange
0x14001dfc5  nop     dword ptr [rax+rax+00h]
0x14001dfca  mov     rcx, [rsp+68h+arg_0]
0x14001dfcf  xor     r9d, r9d
0x14001dfd2  xor     r8d, r8d
0x14001dfd5  xor     edx, edx
0x14001dfd7  mov     edi, eax
0x14001dfd9  cmp     eax, 103h
0x14001dfde  jnz     short loc_14001E005
0x14001dfe0  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x14001dfe7  nop     dword ptr [rax+rax+00h]
0x14001dfec  mov     edi, eax
0x14001dfee  test    edi, edi
0x14001dff0  js      short loc_14001DFF9
0x14001dff2  mov     dword ptr [rsi+60h], 1
0x14001dff9  mov     eax, edi
0x14001dffb  add     rsp, 48h
0x14001dfff  pop     rdi
0x14001e000  pop     rsi
0x14001e001  pop     rbp
0x14001e002  pop     rbx
0x14001e003  retn
0x14001e005  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x14001e00c  nop     dword ptr [rax+rax+00h]
0x14001e011  jmp     short loc_14001DFEE
0x14001e013  mov     rax, [rax+0B8h]
0x14001e01a  movzx   ebp, byte ptr [rax+2]
0x14001e01e  jmp     loc_14001DED1
0x14003c020  cmp     [rcx+208h], edi
0x14003c026  jnz     short loc_14003C09A
0x14003c028  cmp     [rcx+20Ch], edi
0x14003c02e  jnz     short loc_14003C09A
0x14003c030  cmp     ebp, 1
0x14003c033  ja      short loc_14003C09A
0x14003c035  mov     eax, [rcx+1D8h]
0x14003c03b  mov     r9d, 0Fh
0x14003c041  mov     dword ptr [rsp+68h+arg_0], eax
0x14003c045  mov     r8d, 1
0x14003c04b  mov     rax, [rcx+48h]
0x14003c04f  mov     rcx, [rax+28h]
0x14003c053  mov     rax, [rcx+28h]
0x14003c057  mov     rcx, rbx
0x14003c05a  mov     rdx, [rax+1A8h]
0x14003c061  lea     rax, [rsp+68h+arg_0]
0x14003c066  mov     [rsp+68h+var_38], rax
0x14003c06b  add     rdx, 178h
0x14003c072  mov     rax, [rbx+1C8h]
0x14003c079  mov     [rsp+68h+var_40], rax
0x14003c07e  mov     dword ptr [rsp+68h+var_48], edi
0x14003c082  call    Smb2FetchFileInfoFromCache
0x14003c087  test    eax, eax
0x14003c089  js      short loc_14003C09A
0x14003c08b  mov     ecx, dword ptr [rsp+68h+arg_0]
0x14003c08f  sub     [rbx+1D8h], ecx
0x14003c095  jmp     loc_14001DFFB
0x14003c09a  cmp     [rsi+60h], edi
0x14003c09d  jnz     loc_14001DEDA
0x14003c0a3  test    bpl, 4
0x14003c0a7  jnz     loc_14001DEDA
0x14003c0ad  or      ebp, 1
0x14003c0b0  jmp     loc_14001DEDA
```
