# threadFuncDirectColorConv0(__int64)

- ea: `0x180006610`
- end: `0x18000675a`
- name: `?threadFuncDirectColorConv0@@YAX_J@Z`
- size: `330`
- prototype: `void __fastcall(struct DIRECTCOLORCONVFRM *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006610`
- `0x180006760`
- `0x180006798`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006653`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006653`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000663c`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180006742`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000663c`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180006742`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800066d9`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18000671a`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800066d9`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18000671a`

## pseudocode

```c
void __fastcall threadFuncDirectColorConv0(struct DIRECTCOLORCONVFRM *a1)
{
  void *v2; // rcx
  BOOL v3; // edi
  __int64 v4; // rsi
  int v5; // eax
  void *v6; // rcx
  HANDLE v7; // rax
  HANDLE v8; // rax

  v2 = (void *)*((_QWORD *)a1 + 1904);
  if ( v2 )
  {
    v3 = 0;
    if ( !*((_DWORD *)a1 + 3678) )
    {
      AvRevertMmThreadCharacteristics(v2);
      *((_QWORD *)a1 + 1904) = 0;
    }
  }
  else if ( *((_DWORD *)a1 + 3678) )
  {
    v7 = AvSetMmThreadCharacteristicsW((LPCWSTR)a1 + 7358, (LPDWORD)a1 + 3807);
    *((_QWORD *)a1 + 1904) = v7;
    v3 = v7 != 0;
  }
  else
  {
    v3 = 0;
  }
  WaitForSingleObject(*((HANDLE *)a1 + 1836), 0xFFFFFFFF);
  LODWORD(v4) = 0;
  while ( 1 )
  {
    v5 = *((_DWORD *)a1 + 3678);
    v6 = (void *)*((_QWORD *)a1 + 1904);
    if ( v3 )
    {
      if ( v6 )
      {
        if ( !v5 )
        {
          AvRevertMmThreadCharacteristics(v6);
          v3 = 0;
          *((_QWORD *)a1 + 1904) = 0;
        }
      }
    }
    else if ( !v6 && v5 )
    {
      v8 = AvSetMmThreadCharacteristicsW((LPCWSTR)a1 + 7358, (LPDWORD)a1 + 3807);
      *((_QWORD *)a1 + 1904) = v8;
      v3 = v8 != 0;
    }
    if ( *((_DWORD *)a1 + 3659) )
      break;
    process0(a1);
    v4 = 1 - (int)v4;
    syncCC((int *)a1 + 3661, *((void **)a1 + 1838), *((void **)a1 + v4 + 1836));
  }
}

```

## disassembly

```asm
0x180006610  mov     [rsp+arg_0], rbx
0x180006615  mov     [rsp+arg_8], rsi
0x18000661a  push    rdi
0x18000661b  sub     rsp, 20h
0x18000661f  mov     rbx, rcx
0x180006622  mov     rcx, [rcx+3B80h]; AvrtHandle
0x180006629  test    rcx, rcx
0x18000662c  jz      loc_1800066C2
0x180006632  xor     edi, edi
0x180006634  cmp     [rbx+3978h], edi
0x18000663a  jnz     short loc_180006649
0x18000663c  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180006642  mov     [rbx+3B80h], rdi
0x180006649  mov     rcx, [rbx+3960h]; hHandle
0x180006650  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006653  call    cs:__imp_WaitForSingleObject
0x180006659  xor     esi, esi
0x18000665b  mov     eax, [rbx+3978h]
0x180006661  mov     rcx, [rbx+3B80h]; AvrtHandle
0x180006668  test    edi, edi
0x18000666a  jz      loc_1800066FB
0x180006670  test    rcx, rcx
0x180006673  jnz     loc_18000673A
0x180006679  mov     eax, [rbx+392Ch]
0x18000667f  test    eax, eax
0x180006681  jnz     short loc_1800066B2
0x180006683  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x180006686  call    ?process0@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; process0(DIRECTCOLORCONVFRM *)
0x18000668b  mov     rdx, [rbx+3970h]; void *
0x180006692  lea     rcx, [rbx+3934h]; int *
0x180006699  mov     eax, 1
0x18000669e  sub     eax, esi
0x1800066a0  movsxd  rsi, eax
0x1800066a3  mov     r8, [rbx+rsi*8+3960h]; void *
0x1800066ab  call    ?syncCC@@YAXPEAJPEAX1@Z; syncCC(long *,void *,void *)
0x1800066b0  jmp     short loc_18000665B
0x1800066b2  mov     rbx, [rsp+28h+arg_0]
0x1800066b7  mov     rsi, [rsp+28h+arg_8]
0x1800066bc  add     rsp, 20h
0x1800066c0  pop     rdi
0x1800066c1  retn
0x1800066c2  cmp     dword ptr [rbx+3978h], 0
0x1800066c9  jz      short loc_1800066F4
0x1800066cb  lea     rdx, [rbx+3B7Ch]; TaskIndex
0x1800066d2  lea     rcx, [rbx+397Ch]; TaskName
0x1800066d9  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x1800066df  xor     edi, edi
0x1800066e1  mov     [rbx+3B80h], rax
0x1800066e8  test    rax, rax
0x1800066eb  setnz   dil
0x1800066ef  jmp     loc_180006649
0x1800066f4  xor     edi, edi
0x1800066f6  jmp     loc_180006649
0x1800066fb  test    rcx, rcx
0x1800066fe  jnz     loc_180006679
0x180006704  test    eax, eax
0x180006706  jz      loc_180006679
0x18000670c  lea     rdx, [rbx+3B7Ch]; TaskIndex
0x180006713  lea     rcx, [rbx+397Ch]; TaskName
0x18000671a  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x180006720  mov     [rbx+3B80h], rax
0x180006727  test    rax, rax
0x18000672a  jz      loc_180006679
0x180006730  mov     edi, 1
0x180006735  jmp     loc_180006679
0x18000673a  test    eax, eax
0x18000673c  jnz     loc_180006679
0x180006742  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180006748  xor     edi, edi
0x18000674a  mov     qword ptr [rbx+3B80h], 0
0x180006755  jmp     loc_180006679
```
