# threadFuncDirectColorConv1(__int64)

- ea: `0x1800064d0`
- end: `0x180006607`
- name: `?threadFuncDirectColorConv1@@YAX_J@Z`
- size: `311`
- prototype: `void __fastcall(struct DIRECTCOLORCONVFRM *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800064d0`
- `0x180006760`
- `0x180006870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006513`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006513`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800064fc`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800065ef`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800064fc`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800065ef`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180006585`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800065c5`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180006585`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800065c5`

## pseudocode

```c
void __fastcall threadFuncDirectColorConv1(struct DIRECTCOLORCONVFRM *a1)
{
  void *v2; // rcx
  BOOL v3; // edi
  __int64 v4; // rsi
  int v5; // eax
  void *v6; // rcx
  HANDLE v7; // rax
  HANDLE v8; // rax

  v2 = (void *)*((_QWORD *)a1 + 1905);
  if ( v2 )
  {
    v3 = 0;
    if ( !*((_DWORD *)a1 + 3678) )
    {
      AvRevertMmThreadCharacteristics(v2);
      *((_QWORD *)a1 + 1905) = 0;
    }
  }
  else if ( *((_DWORD *)a1 + 3678) )
  {
    v8 = AvSetMmThreadCharacteristicsW((LPCWSTR)a1 + 7358, (LPDWORD)a1 + 3807);
    *((_QWORD *)a1 + 1905) = v8;
    v3 = v8 != 0;
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
    v6 = (void *)*((_QWORD *)a1 + 1905);
    if ( v3 )
    {
      if ( v6 )
      {
        if ( !v5 )
        {
          AvRevertMmThreadCharacteristics(v6);
          v3 = 0;
          *((_QWORD *)a1 + 1905) = 0;
        }
      }
    }
    else if ( !v6 && v5 )
    {
      v7 = AvSetMmThreadCharacteristicsW((LPCWSTR)a1 + 7358, (LPDWORD)a1 + 3807);
      *((_QWORD *)a1 + 1905) = v7;
      v3 = v7 != 0;
    }
    if ( *((_DWORD *)a1 + 3659) )
      break;
    process1(a1);
    v4 = 1 - (int)v4;
    syncCC((int *)a1 + 3661, *((void **)a1 + 1838), *((void **)a1 + v4 + 1836));
  }
}

```

## disassembly

```asm
0x1800064d0  mov     [rsp+arg_0], rbx
0x1800064d5  mov     [rsp+arg_8], rsi
0x1800064da  push    rdi
0x1800064db  sub     rsp, 20h
0x1800064df  mov     rbx, rcx
0x1800064e2  mov     rcx, [rcx+3B88h]; AvrtHandle
0x1800064e9  test    rcx, rcx
0x1800064ec  jz      loc_1800065AE
0x1800064f2  xor     edi, edi
0x1800064f4  cmp     [rbx+3978h], edi
0x1800064fa  jnz     short loc_180006509
0x1800064fc  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180006502  mov     [rbx+3B88h], rdi
0x180006509  mov     rcx, [rbx+3960h]; hHandle
0x180006510  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006513  call    cs:__imp_WaitForSingleObject
0x180006519  xor     esi, esi
0x18000651b  mov     eax, [rbx+3978h]
0x180006521  mov     rcx, [rbx+3B88h]; AvrtHandle
0x180006528  test    edi, edi
0x18000652a  jz      short loc_18000656E
0x18000652c  test    rcx, rcx
0x18000652f  jnz     loc_1800065E7
0x180006535  mov     eax, [rbx+392Ch]
0x18000653b  test    eax, eax
0x18000653d  jnz     short loc_18000659E
0x18000653f  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x180006542  call    ?process1@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; process1(DIRECTCOLORCONVFRM *)
0x180006547  mov     rdx, [rbx+3970h]; void *
0x18000654e  lea     rcx, [rbx+3934h]; int *
0x180006555  mov     eax, 1
0x18000655a  sub     eax, esi
0x18000655c  movsxd  rsi, eax
0x18000655f  mov     r8, [rbx+rsi*8+3960h]; void *
0x180006567  call    ?syncCC@@YAXPEAJPEAX1@Z; syncCC(long *,void *,void *)
0x18000656c  jmp     short loc_18000651B
0x18000656e  test    rcx, rcx
0x180006571  jnz     short loc_180006535
0x180006573  test    eax, eax
0x180006575  jz      short loc_180006535
0x180006577  lea     rdx, [rbx+3B7Ch]; TaskIndex
0x18000657e  lea     rcx, [rbx+397Ch]; TaskName
0x180006585  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x18000658b  mov     [rbx+3B88h], rax
0x180006592  test    rax, rax
0x180006595  jz      short loc_180006535
0x180006597  mov     edi, 1
0x18000659c  jmp     short loc_180006535
0x18000659e  mov     rbx, [rsp+28h+arg_0]
0x1800065a3  mov     rsi, [rsp+28h+arg_8]
0x1800065a8  add     rsp, 20h
0x1800065ac  pop     rdi
0x1800065ad  retn
0x1800065ae  cmp     dword ptr [rbx+3978h], 0
0x1800065b5  jz      short loc_1800065E0
0x1800065b7  lea     rdx, [rbx+3B7Ch]; TaskIndex
0x1800065be  lea     rcx, [rbx+397Ch]; TaskName
0x1800065c5  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x1800065cb  xor     edi, edi
0x1800065cd  mov     [rbx+3B88h], rax
0x1800065d4  test    rax, rax
0x1800065d7  setnz   dil
0x1800065db  jmp     loc_180006509
0x1800065e0  xor     edi, edi
0x1800065e2  jmp     loc_180006509
0x1800065e7  test    eax, eax
0x1800065e9  jnz     loc_180006535
0x1800065ef  call    cs:__imp_AvRevertMmThreadCharacteristics
0x1800065f5  xor     edi, edi
0x1800065f7  mov     qword ptr [rbx+3B88h], 0
0x180006602  jmp     loc_180006535
```
