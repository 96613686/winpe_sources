# SslDecrementProviderReferenceCount

- ea: `0x1800146e0`
- end: `0x180014795`
- name: `SslDecrementProviderReferenceCount`
- size: `181`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007ca0`
- `0x18000a770`
- `0x18000d02c`
- `0x1800146e0`
- `0x18001f175`
- `0x180020010`

## string_xrefs

- `0x180014713`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslDecrementProviderReferenceCount(unsigned int *a1, int a2, int a3)
{
  unsigned int v4; // ebx

  if ( *a1 >= 0x1B0 && a1[1] == 1145324609 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 4, 0xFFFFFFFF) <= 1 && a1[3] )
    {
      (*((void (__fastcall **)(_QWORD, _QWORD))a1 + 15))(*((_QWORD *)a1 + 53), 0);
      UnloadProvider(*((_QWORD *)a1 + 3));
      memset_0(a1, 0, *a1);
      MSCryptFree(a1);
    }
    return 0;
  }
  else
  {
    v4 = -1073741816;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        255);
  }
  return v4;
}

```

## disassembly

```asm
0x1800146e0  push    rbx
0x1800146e2  sub     rsp, 40h
0x1800146e6  cmp     dword ptr [rcx], 1B0h
0x1800146ec  mov     rbx, rcx
0x1800146ef  jnb     short loc_180014743
0x1800146f1  mov     ebx, 0C0000008h
0x1800146f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146fd  lea     rax, WPP_GLOBAL_Control
0x180014704  cmp     rcx, rax
0x180014707  jz      short loc_18001473B
0x180014709  test    byte ptr [rcx+1Ch], 1
0x18001470d  jz      short loc_18001473B
0x18001470f  mov     rcx, [rcx+10h]
0x180014713  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001471a  mov     [rsp+48h+var_18], 0CFFh
0x180014722  lea     r9, aStatus; "Status"
0x180014729  mov     [rsp+48h+var_20], rax
0x18001472e  mov     [rsp+48h+var_28], 0C0000008h
0x180014736  call    WPP_SF_sDsd
0x18001473b  mov     eax, ebx
0x18001473d  add     rsp, 40h
0x180014741  pop     rbx
0x180014742  retn
0x180014743  cmp     dword ptr [rcx+4], 44444441h
0x18001474a  jnz     short loc_1800146F1
0x18001474c  or      eax, 0FFFFFFFFh
0x18001474f  lock xadd [rcx+10h], eax
0x180014754  sub     eax, 1
0x180014757  jle     short loc_18001475D
0x180014759  xor     ebx, ebx
0x18001475b  jmp     short loc_18001473B
0x18001475d  cmp     dword ptr [rcx+0Ch], 0
0x180014761  jz      short loc_180014759
0x180014763  mov     rcx, [rcx+1A8h]
0x18001476a  xor     edx, edx
0x18001476c  mov     rax, [rbx+78h]
0x180014770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014775  mov     rcx, [rbx+18h]
0x180014779  call    UnloadProvider
0x18001477e  mov     r8d, [rbx]; Size
0x180014781  xor     edx, edx; Val
0x180014783  mov     rcx, rbx; void *
0x180014786  call    memset_0
0x18001478b  mov     rcx, rbx
0x18001478e  call    MSCryptFree
0x180014793  jmp     short loc_180014759
```
