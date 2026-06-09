# MSCryptQueryValue

- ea: `0x180008120`
- end: `0x180008353`
- name: `MSCryptQueryValue`
- size: `563`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008d5c`

## callees

- `0x180008120`
- `0x18000b250`
- `0x1800398b0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000822b`
- `ntdll!RtlNtStatusToDosError` at `0x18000822b`
- `ntdll!RtlFreeHeap` at `0x18000821d`
- `ntdll!RtlFreeHeap` at `0x18000821d`
- `ntdll!NtQueryValueKey` at `0x1800081d5`
- `ntdll!NtQueryValueKey` at `0x1800081d5`
- `ntdll!RtlInitUnicodeString` at `0x180008160`
- `ntdll!RtlInitUnicodeString` at `0x180008160`
- `ntdll!RtlAllocateHeap` at `0x180008194`
- `ntdll!RtlAllocateHeap` at `0x180008194`

## string_xrefs

- `0x180008267`: `onecore\ds\security\cryptoapi\ncrypt\common\registry.c`
- `0x1800082d1`: `onecore\ds\security\cryptoapi\ncrypt\common\registry.c`
- `0x18000833a`: `onecore\ds\security\cryptoapi\ncrypt\common\registry.c`

## pseudocode

```c
ULONG __fastcall MSCryptQueryValue(HANDLE KeyHandle, int a2, __int64 a3, void *a4, int *a5)
{
  int *v5; // rdi
  int v8; // eax
  unsigned int *Heap; // rax
  int v10; // edx
  int v11; // r8d
  unsigned int *v12; // rbp
  int v13; // edx
  int v14; // ebx
  int v15; // r8d
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  ULONG Length; // [rsp+90h] [rbp+18h] BYREF
  int v19; // [rsp+94h] [rbp+1Ch]

  v19 = HIDWORD(a3);
  v5 = a5;
  Length = 0;
  DestinationString = 0;
  if ( !a4 || a5 )
  {
    RtlInitUnicodeString(&DestinationString, L"MachineGuid");
    v8 = 0;
    if ( v5 )
      v8 = *v5;
    Length = v8 + 12;
    Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)(v8 + 12));
    v12 = Heap;
    if ( Heap )
    {
      v14 = NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Heap, Length, &Length);
      if ( v14 >= 0 || v14 == -2147483643 || v14 == -1073741789 )
      {
        if ( v5 )
          *v5 = Length - 12;
        if ( v14 >= 0 )
        {
          if ( a4 )
          {
            memcpy_0(a4, v12 + 3, v12[2]);
            goto LABEL_11;
          }
        }
        else if ( a4 )
        {
          goto LABEL_11;
        }
        v14 = 0;
        goto LABEL_11;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          v15,
          (unsigned int)"Status",
          v14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\registry.c",
          45);
    }
    else
    {
      v14 = -1073741801;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          v11,
          (unsigned int)"Status",
          23,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\registry.c",
          2);
    }
  }
  else
  {
    v12 = 0;
    v14 = -1073741811;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\registry.c",
        232);
  }
LABEL_11:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  return RtlNtStatusToDosError(v14);
}

```

## disassembly

```asm
0x180008120  mov     rax, rsp
0x180008123  mov     [rax+18h], r8
0x180008127  push    rbx
0x180008128  push    rbp
0x180008129  push    rsi
0x18000812a  push    rdi
0x18000812b  sub     rsp, 58h
0x18000812f  mov     rdi, [rsp+78h+arg_20]
0x180008137  xorps   xmm0, xmm0
0x18000813a  mov     dword ptr [rax+18h], 0
0x180008141  mov     rsi, r9
0x180008144  mov     rbx, rcx
0x180008147  movups  xmmword ptr [rax-38h], xmm0
0x18000814b  test    r9, r9
0x18000814e  jnz     loc_180008301
0x180008154  lea     rdx, SourceString; "MachineGuid"
0x18000815b  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180008160  call    cs:__imp_RtlInitUnicodeString
0x180008167  nop     dword ptr [rax+rax+00h]
0x18000816c  xor     eax, eax
0x18000816e  test    rdi, rdi
0x180008171  jz      short loc_180008175
0x180008173  mov     eax, [rdi]
0x180008175  add     eax, 0Ch
0x180008178  mov     edx, 8; Flags
0x18000817d  mov     [rsp+78h+arg_10], eax
0x180008184  mov     rcx, gs:60h
0x18000818d  mov     r8d, eax; Size
0x180008190  mov     rcx, [rcx+30h]; HeapHandle
0x180008194  call    cs:__imp_RtlAllocateHeap
0x18000819b  nop     dword ptr [rax+rax+00h]
0x1800081a0  mov     rbp, rax
0x1800081a3  test    rax, rax
0x1800081a6  jz      loc_180008241
0x1800081ac  lea     rax, [rsp+78h+arg_10]
0x1800081b4  mov     r9, rbp; KeyValueInformation
0x1800081b7  mov     [rsp+78h+ResultLength], rax; ResultLength
0x1800081bc  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x1800081c1  mov     eax, [rsp+78h+arg_10]
0x1800081c8  mov     r8d, 2; KeyValueInformationClass
0x1800081ce  mov     rcx, rbx; KeyHandle
0x1800081d1  mov     [rsp+78h+Length], eax; Length
0x1800081d5  call    cs:__imp_NtQueryValueKey
0x1800081dc  nop     dword ptr [rax+rax+00h]
0x1800081e1  mov     ebx, eax
0x1800081e3  test    eax, eax
0x1800081e5  js      loc_180008290
0x1800081eb  test    rdi, rdi
0x1800081ee  jz      short loc_1800081FC
0x1800081f0  mov     eax, [rsp+78h+arg_10]
0x1800081f7  add     eax, 0FFFFFFF4h
0x1800081fa  mov     [rdi], eax
0x1800081fc  test    ebx, ebx
0x1800081fe  jns     loc_1800082E3
0x180008204  test    rsi, rsi
0x180008207  jnz     short loc_18000820B
0x180008209  xor     ebx, ebx
0x18000820b  mov     rcx, gs:60h
0x180008214  mov     r8, rbp; P
0x180008217  xor     edx, edx; Flags
0x180008219  mov     rcx, [rcx+30h]; HeapHandle
0x18000821d  call    cs:__imp_RtlFreeHeap
0x180008224  nop     dword ptr [rax+rax+00h]
0x180008229  mov     ecx, ebx; Status
0x18000822b  call    cs:__imp_RtlNtStatusToDosError
0x180008232  nop     dword ptr [rax+rax+00h]
0x180008237  add     rsp, 58h
0x18000823b  pop     rdi
0x18000823c  pop     rsi
0x18000823d  pop     rbp
0x18000823e  pop     rbx
0x18000823f  retn
0x180008241  mov     ebx, 0C0000017h
0x180008246  mov     rcx, cs:WPP_GLOBAL_Control
0x18000824d  lea     rax, WPP_GLOBAL_Control
0x180008254  cmp     rcx, rax
0x180008257  jz      short loc_18000820B
0x180008259  test    byte ptr [rcx+1Ch], 1
0x18000825d  jz      short loc_18000820B
0x18000825f  mov     [rsp+78h+var_48], 102h
0x180008267  lea     rax, aOnecoreDsSecur_40; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000826e  mov     [rsp+78h+ResultLength], rax
0x180008273  mov     [rsp+78h+Length], 0C0000017h
0x18000827b  mov     rcx, [rcx+10h]
0x18000827f  lea     r9, aStatus; "Status"
0x180008286  call    WPP_SF_sDsd
0x18000828b  jmp     loc_18000820B
0x180008290  cmp     ebx, 80000005h
0x180008296  jz      loc_1800081EB
0x18000829c  cmp     ebx, 0C0000023h
0x1800082a2  jz      loc_1800081EB
0x1800082a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082af  lea     rax, WPP_GLOBAL_Control
0x1800082b6  cmp     rcx, rax
0x1800082b9  jz      loc_18000820B
0x1800082bf  test    byte ptr [rcx+1Ch], 1
0x1800082c3  jz      loc_18000820B
0x1800082c9  mov     [rsp+78h+var_48], 12Dh
0x1800082d1  lea     rax, aOnecoreDsSecur_40; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800082d8  mov     [rsp+78h+ResultLength], rax
0x1800082dd  mov     [rsp+78h+Length], ebx
0x1800082e1  jmp     short loc_18000827B
0x1800082e3  test    rsi, rsi
0x1800082e6  jz      loc_180008209
0x1800082ec  mov     r8d, [rbp+8]; Size
0x1800082f0  lea     rdx, [rbp+0Ch]; Src
0x1800082f4  mov     rcx, rsi; void *
0x1800082f7  call    memcpy_0
0x1800082fc  jmp     loc_18000820B
0x180008301  test    rdi, rdi
0x180008304  jnz     loc_180008154
0x18000830a  xor     ebp, ebp
0x18000830c  mov     ebx, 0C000000Dh
0x180008311  mov     rcx, cs:WPP_GLOBAL_Control
0x180008318  lea     rax, WPP_GLOBAL_Control
0x18000831f  cmp     rcx, rax
0x180008322  jz      loc_18000820B
0x180008328  test    byte ptr [rcx+1Ch], 1
0x18000832c  jz      loc_18000820B
0x180008332  mov     [rsp+78h+var_48], 0E8h
0x18000833a  lea     rax, aOnecoreDsSecur_40; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008341  mov     [rsp+78h+ResultLength], rax
0x180008346  mov     [rsp+78h+Length], 0C000000Dh
0x18000834e  jmp     loc_18000827B
```
