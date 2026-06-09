# threadFuncDirectColorConv2(__int64)

- ea: `0x180014a30`
- end: `0x180014b68`
- name: `?threadFuncDirectColorConv2@@YAX_J@Z`
- size: `312`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180006760`
- `0x1800147d0`
- `0x180014a30`
- `0x180029f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014ab2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014ab2`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180014a9b`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180014b04`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180014a9b`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180014b04`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180014a75`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180014ae2`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180014a75`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180014ae2`

## pseudocode

```c
void __fastcall threadFuncDirectColorConv2(__int64 a1)
{
  void *v2; // rcx
  HANDLE v3; // rax
  BOOL v4; // edi
  __int64 v5; // rsi
  int v6; // eax
  void *v7; // rcx
  HANDLE v8; // rax

  v2 = *(void **)(a1 + 15248);
  if ( v2 )
  {
    v4 = 0;
    if ( !*(_DWORD *)(a1 + 14712) )
    {
      AvRevertMmThreadCharacteristics(v2);
      *(_QWORD *)(a1 + 15248) = 0;
    }
  }
  else if ( *(_DWORD *)(a1 + 14712) )
  {
    v3 = AvSetMmThreadCharacteristicsW((LPCWSTR)(a1 + 14716), (LPDWORD)(a1 + 15228));
    *(_QWORD *)(a1 + 15248) = v3;
    v4 = v3 != 0;
  }
  else
  {
    v4 = 0;
  }
  WaitForSingleObject(*(HANDLE *)(a1 + 14688), 0xFFFFFFFF);
  LODWORD(v5) = 0;
  while ( 1 )
  {
    v6 = *(_DWORD *)(a1 + 14712);
    v7 = *(void **)(a1 + 15248);
    if ( v4 )
    {
      if ( v7 && !v6 )
      {
        AvRevertMmThreadCharacteristics(v7);
        v4 = 0;
        *(_QWORD *)(a1 + 15248) = 0;
      }
    }
    else if ( !v7 )
    {
      if ( v6 )
      {
        v8 = AvSetMmThreadCharacteristicsW((LPCWSTR)(a1 + 14716), (LPDWORD)(a1 + 15228));
        *(_QWORD *)(a1 + 15248) = v8;
        v4 = v8 != 0;
      }
    }
    if ( *(_DWORD *)(a1 + 14636) )
      break;
    process2((struct DIRECTCOLORCONVFRM *)a1);
    v5 = 1 - (int)v5;
    syncCC((int *)(a1 + 14644), *(void **)(a1 + 14704), *(void **)(a1 + 8 * v5 + 14688));
  }
}

```

## disassembly

```asm
0x180014a30  mov     [rsp+arg_0], rbx
0x180014a35  mov     [rsp+arg_8], rsi
0x180014a3a  push    rdi
0x180014a3b  mov     eax, 2020h
0x180014a40  call    _alloca_probe
0x180014a45  sub     rsp, rax
0x180014a48  mov     rbx, rcx
0x180014a4b  mov     [rsp+2028h+var_2008], 3E7h
0x180014a53  mov     rcx, [rcx+3B90h]; AvrtHandle
0x180014a5a  test    rcx, rcx
0x180014a5d  jnz     short loc_180014A91
0x180014a5f  cmp     [rbx+3978h], ecx
0x180014a65  jz      short loc_180014A8D
0x180014a67  lea     rdx, [rbx+3B7Ch]; TaskIndex
0x180014a6e  lea     rcx, [rbx+397Ch]; TaskName
0x180014a75  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x180014a7b  xor     edi, edi
0x180014a7d  mov     [rbx+3B90h], rax
0x180014a84  test    rax, rax
0x180014a87  setnz   dil
0x180014a8b  jmp     short loc_180014AA8
0x180014a8d  xor     edi, edi
0x180014a8f  jmp     short loc_180014AA8
0x180014a91  xor     edi, edi
0x180014a93  cmp     [rbx+3978h], edi
0x180014a99  jnz     short loc_180014AA8
0x180014a9b  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180014aa1  mov     [rbx+3B90h], rdi
0x180014aa8  mov     rcx, [rbx+3960h]; hHandle
0x180014aaf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014ab2  call    cs:__imp_WaitForSingleObject
0x180014ab8  xor     esi, esi
0x180014aba  mov     eax, [rbx+3978h]
0x180014ac0  mov     rcx, [rbx+3B90h]; AvrtHandle
0x180014ac7  test    edi, edi
0x180014ac9  jnz     short loc_180014AFB
0x180014acb  test    rcx, rcx
0x180014ace  jnz     short loc_180014B17
0x180014ad0  test    eax, eax
0x180014ad2  jz      short loc_180014B17
0x180014ad4  lea     rdx, [rbx+3B7Ch]; TaskIndex
0x180014adb  lea     rcx, [rbx+397Ch]; TaskName
0x180014ae2  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x180014ae8  mov     [rbx+3B90h], rax
0x180014aef  test    rax, rax
0x180014af2  jz      short loc_180014B17
0x180014af4  mov     edi, 1
0x180014af9  jmp     short loc_180014B17
0x180014afb  test    rcx, rcx
0x180014afe  jz      short loc_180014B17
0x180014b00  test    eax, eax
0x180014b02  jnz     short loc_180014B17
0x180014b04  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180014b0a  xor     edi, edi
0x180014b0c  mov     qword ptr [rbx+3B90h], 0
0x180014b17  mov     eax, [rbx+392Ch]
0x180014b1d  test    eax, eax
0x180014b1f  jnz     short loc_180014B53
0x180014b21  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x180014b24  call    ?process2@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; process2(DIRECTCOLORCONVFRM *)
0x180014b29  mov     rdx, [rbx+3970h]; void *
0x180014b30  lea     rcx, [rbx+3934h]; int *
0x180014b37  mov     eax, 1
0x180014b3c  sub     eax, esi
0x180014b3e  movsxd  rsi, eax
0x180014b41  mov     r8, [rbx+rsi*8+3960h]; void *
0x180014b49  call    ?syncCC@@YAXPEAJPEAX1@Z; syncCC(long *,void *,void *)
0x180014b4e  jmp     loc_180014ABA
0x180014b53  lea     r11, [rsp+2028h+var_8]
0x180014b5b  mov     rbx, [r11+10h]
0x180014b5f  mov     rsi, [r11+18h]
0x180014b63  mov     rsp, r11
0x180014b66  pop     rdi
0x180014b67  retn
```
