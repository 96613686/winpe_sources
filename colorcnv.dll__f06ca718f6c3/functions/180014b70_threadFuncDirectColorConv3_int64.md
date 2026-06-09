# threadFuncDirectColorConv3(__int64)

- ea: `0x180014b70`
- end: `0x180014ca8`
- name: `?threadFuncDirectColorConv3@@YAX_J@Z`
- size: `312`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180006760`
- `0x1800148b4`
- `0x180014b70`
- `0x180029f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014bf2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014bf2`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180014bdb`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180014c44`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180014bdb`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180014c44`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180014bb5`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180014c22`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180014bb5`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180014c22`

## pseudocode

```c
void __fastcall threadFuncDirectColorConv3(__int64 a1)
{
  void *v2; // rcx
  HANDLE v3; // rax
  BOOL v4; // edi
  __int64 v5; // rsi
  int v6; // eax
  void *v7; // rcx
  HANDLE v8; // rax

  v2 = *(void **)(a1 + 15256);
  if ( v2 )
  {
    v4 = 0;
    if ( !*(_DWORD *)(a1 + 14712) )
    {
      AvRevertMmThreadCharacteristics(v2);
      *(_QWORD *)(a1 + 15256) = 0;
    }
  }
  else if ( *(_DWORD *)(a1 + 14712) )
  {
    v3 = AvSetMmThreadCharacteristicsW((LPCWSTR)(a1 + 14716), (LPDWORD)(a1 + 15228));
    *(_QWORD *)(a1 + 15256) = v3;
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
    v7 = *(void **)(a1 + 15256);
    if ( v4 )
    {
      if ( v7 && !v6 )
      {
        AvRevertMmThreadCharacteristics(v7);
        v4 = 0;
        *(_QWORD *)(a1 + 15256) = 0;
      }
    }
    else if ( !v7 )
    {
      if ( v6 )
      {
        v8 = AvSetMmThreadCharacteristicsW((LPCWSTR)(a1 + 14716), (LPDWORD)(a1 + 15228));
        *(_QWORD *)(a1 + 15256) = v8;
        v4 = v8 != 0;
      }
    }
    if ( *(_DWORD *)(a1 + 14636) )
      break;
    process3((struct DIRECTCOLORCONVFRM *)a1);
    v5 = 1 - (int)v5;
    syncCC((int *)(a1 + 14644), *(void **)(a1 + 14704), *(void **)(a1 + 8 * v5 + 14688));
  }
}

```

## disassembly

```asm
0x180014b70  mov     [rsp+arg_0], rbx
0x180014b75  mov     [rsp+arg_8], rsi
0x180014b7a  push    rdi
0x180014b7b  mov     eax, 3020h
0x180014b80  call    _alloca_probe
0x180014b85  sub     rsp, rax
0x180014b88  mov     rbx, rcx
0x180014b8b  mov     [rsp+3028h+var_3008], 3E7h
0x180014b93  mov     rcx, [rcx+3B98h]; AvrtHandle
0x180014b9a  test    rcx, rcx
0x180014b9d  jnz     short loc_180014BD1
0x180014b9f  cmp     [rbx+3978h], ecx
0x180014ba5  jz      short loc_180014BCD
0x180014ba7  lea     rdx, [rbx+3B7Ch]; TaskIndex
0x180014bae  lea     rcx, [rbx+397Ch]; TaskName
0x180014bb5  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x180014bbb  xor     edi, edi
0x180014bbd  mov     [rbx+3B98h], rax
0x180014bc4  test    rax, rax
0x180014bc7  setnz   dil
0x180014bcb  jmp     short loc_180014BE8
0x180014bcd  xor     edi, edi
0x180014bcf  jmp     short loc_180014BE8
0x180014bd1  xor     edi, edi
0x180014bd3  cmp     [rbx+3978h], edi
0x180014bd9  jnz     short loc_180014BE8
0x180014bdb  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180014be1  mov     [rbx+3B98h], rdi
0x180014be8  mov     rcx, [rbx+3960h]; hHandle
0x180014bef  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014bf2  call    cs:__imp_WaitForSingleObject
0x180014bf8  xor     esi, esi
0x180014bfa  mov     eax, [rbx+3978h]
0x180014c00  mov     rcx, [rbx+3B98h]; AvrtHandle
0x180014c07  test    edi, edi
0x180014c09  jnz     short loc_180014C3B
0x180014c0b  test    rcx, rcx
0x180014c0e  jnz     short loc_180014C57
0x180014c10  test    eax, eax
0x180014c12  jz      short loc_180014C57
0x180014c14  lea     rdx, [rbx+3B7Ch]; TaskIndex
0x180014c1b  lea     rcx, [rbx+397Ch]; TaskName
0x180014c22  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x180014c28  mov     [rbx+3B98h], rax
0x180014c2f  test    rax, rax
0x180014c32  jz      short loc_180014C57
0x180014c34  mov     edi, 1
0x180014c39  jmp     short loc_180014C57
0x180014c3b  test    rcx, rcx
0x180014c3e  jz      short loc_180014C57
0x180014c40  test    eax, eax
0x180014c42  jnz     short loc_180014C57
0x180014c44  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180014c4a  xor     edi, edi
0x180014c4c  mov     qword ptr [rbx+3B98h], 0
0x180014c57  mov     eax, [rbx+392Ch]
0x180014c5d  test    eax, eax
0x180014c5f  jnz     short loc_180014C93
0x180014c61  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x180014c64  call    ?process3@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; process3(DIRECTCOLORCONVFRM *)
0x180014c69  mov     rdx, [rbx+3970h]; void *
0x180014c70  lea     rcx, [rbx+3934h]; int *
0x180014c77  mov     eax, 1
0x180014c7c  sub     eax, esi
0x180014c7e  movsxd  rsi, eax
0x180014c81  mov     r8, [rbx+rsi*8+3960h]; void *
0x180014c89  call    ?syncCC@@YAXPEAJPEAX1@Z; syncCC(long *,void *,void *)
0x180014c8e  jmp     loc_180014BFA
0x180014c93  lea     r11, [rsp+3028h+var_8]
0x180014c9b  mov     rbx, [r11+10h]
0x180014c9f  mov     rsi, [r11+18h]
0x180014ca3  mov     rsp, r11
0x180014ca6  pop     rdi
0x180014ca7  retn
```
