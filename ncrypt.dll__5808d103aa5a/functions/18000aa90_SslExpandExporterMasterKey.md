# SslExpandExporterMasterKey

- ea: `0x18000aa90`
- end: `0x18000acbd`
- name: `SslExpandExporterMasterKey`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000aa90`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000ab3d`
- `ntdll!RtlAllocateHeap` at `0x18000ab3d`

## string_xrefs

- `0x18000abf3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000ac23`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000ac4b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000ac6d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000ac95`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslExpandExporterMasterKey(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        PVOID *a4,
        __int64 a5,
        int a6)
{
  __int64 v7; // rbp
  __int64 v8; // rsi
  _DWORD *v9; // rbx
  _OWORD *Heap; // rax
  _OWORD *v11; // rdi
  int v12; // eax
  unsigned int v13; // esi

  v7 = a3;
  v8 = a2;
  v9 = a1;
  if ( !a1 || *a1 < 0x1B0u || a1[1] != 1145324609 || a1[3] )
    v9 = 0;
  if ( !a2 || *(_DWORD *)a2 < 0x20u || *(_DWORD *)(a2 + 4) != 1145324610 )
    v8 = 0;
  if ( !a3 || *(_DWORD *)a3 < 0x20u || *(_DWORD *)(a3 + 4) != 1145324611 )
    v7 = 0;
  if ( v9 && v8 && v7 )
  {
    if ( a4 )
    {
      if ( *((_WORD *)v9 + 16) < 4u )
      {
        v13 = -2146893783;
        DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 4229);
      }
      else
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
        v11 = Heap;
        if ( Heap )
        {
          *Heap = 0;
          Heap[1] = 0;
          v12 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _OWORD *, __int64, int))v9 + 40))(
                  *((_QWORD *)v9 + 53),
                  *(_QWORD *)(v8 + 16),
                  *(_QWORD *)(v7 + 16),
                  Heap + 1,
                  a5,
                  a6);
          v13 = v12;
          if ( v12 < 0 )
          {
            DebugTraceError(
              (unsigned int)v12,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              4259);
            MSCryptFree(v11);
          }
          else
          {
            *(_DWORD *)v11 = 32;
            *(_QWORD *)((char *)v11 + 4) = 1145324610;
            *((_DWORD *)v11 + 3) = 1;
            *((_QWORD *)v11 + 3) = v9;
            *a4 = v11;
            _InterlockedIncrement(v9 + 4);
            v13 = 0;
          }
        }
        else
        {
          v13 = -2146893810;
          DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 4241);
        }
      }
    }
    else
    {
      v13 = -2146893785;
      DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 4218);
    }
  }
  else
  {
    v13 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        115);
  }
  return NormalizeNteStatus(v13, (NCRYPT_KEY_HANDLE *)a2, (NCryptKeyName **)a3, a4, a5);
}

```

## disassembly

```asm
0x18000aa90  push    rbx
0x18000aa92  push    rbp
0x18000aa93  push    rsi
0x18000aa94  push    r14
0x18000aa96  sub     rsp, 48h
0x18000aa9a  mov     r14, r9
0x18000aa9d  mov     rbp, r8
0x18000aaa0  mov     rsi, rdx
0x18000aaa3  mov     rbx, rcx
0x18000aaa6  test    rcx, rcx
0x18000aaa9  jz      short loc_18000AAC2
0x18000aaab  cmp     dword ptr [rcx], 1B0h
0x18000aab1  jb      short loc_18000AAC2
0x18000aab3  cmp     dword ptr [rcx+4], 44444441h
0x18000aaba  jnz     short loc_18000AAC2
0x18000aabc  cmp     dword ptr [rcx+0Ch], 0
0x18000aac0  jz      short loc_18000AAC4
0x18000aac2  xor     ebx, ebx
0x18000aac4  test    rdx, rdx
0x18000aac7  jz      short loc_18000AAD7
0x18000aac9  cmp     dword ptr [rdx], 20h ; ' '
0x18000aacc  jb      short loc_18000AAD7
0x18000aace  cmp     dword ptr [rdx+4], 44444442h
0x18000aad5  jz      short loc_18000AAD9
0x18000aad7  xor     esi, esi
0x18000aad9  test    r8, r8
0x18000aadc  jz      short loc_18000AAEE
0x18000aade  cmp     dword ptr [r8], 20h ; ' '
0x18000aae2  jb      short loc_18000AAEE
0x18000aae4  cmp     dword ptr [r8+4], 44444443h
0x18000aaec  jz      short loc_18000AAF0
0x18000aaee  xor     ebp, ebp
0x18000aaf0  mov     [rsp+68h+arg_0], rdi
0x18000aaf5  test    rbx, rbx
0x18000aaf8  jz      loc_18000ABD1
0x18000aafe  test    rsi, rsi
0x18000ab01  jz      loc_18000ABD1
0x18000ab07  test    rbp, rbp
0x18000ab0a  jz      loc_18000ABD1
0x18000ab10  test    r14, r14
0x18000ab13  jz      loc_18000AC1D
0x18000ab19  mov     eax, 4
0x18000ab1e  cmp     ax, [rbx+20h]
0x18000ab22  ja      loc_18000AC45
0x18000ab28  mov     rcx, gs:60h
0x18000ab31  xor     edx, edx; Flags
0x18000ab33  mov     r8d, 20h ; ' '; Size
0x18000ab39  mov     rcx, [rcx+30h]; HeapHandle
0x18000ab3d  call    cs:__imp_RtlAllocateHeap
0x18000ab43  mov     rdi, rax
0x18000ab46  test    rax, rax
0x18000ab49  jz      loc_18000AC6D
0x18000ab4f  mov     ecx, [rsp+68h+arg_28]
0x18000ab56  lea     r9, [rax+10h]
0x18000ab5a  mov     dword ptr [rsp+68h+var_40], ecx
0x18000ab5e  xorps   xmm0, xmm0
0x18000ab61  mov     rcx, [rsp+68h+arg_20]
0x18000ab69  movups  xmmword ptr [rax], xmm0
0x18000ab6c  mov     [rsp+68h+var_48], rcx
0x18000ab71  movups  xmmword ptr [rax+10h], xmm0
0x18000ab75  mov     rcx, [rbx+1A8h]
0x18000ab7c  mov     r8, [rbp+10h]
0x18000ab80  mov     rdx, [rsi+10h]
0x18000ab84  mov     rax, [rbx+140h]
0x18000ab8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab90  mov     esi, eax
0x18000ab92  test    eax, eax
0x18000ab94  js      loc_18000AC95
0x18000ab9a  mov     dword ptr [rdi], 20h ; ' '
0x18000aba0  mov     qword ptr [rdi+4], 44444442h
0x18000aba8  mov     dword ptr [rdi+0Ch], 1
0x18000abaf  mov     [rdi+18h], rbx
0x18000abb3  mov     [r14], rdi
0x18000abb6  lock inc dword ptr [rbx+10h]
0x18000abba  xor     esi, esi
0x18000abbc  mov     ecx, esi
0x18000abbe  mov     rdi, [rsp+68h+arg_0]
0x18000abc3  add     rsp, 48h
0x18000abc7  pop     r14
0x18000abc9  pop     rsi
0x18000abca  pop     rbp
0x18000abcb  pop     rbx
0x18000abcc  jmp     NormalizeNteStatus
0x18000abd1  mov     esi, 80090026h
0x18000abd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abdd  lea     rax, WPP_GLOBAL_Control
0x18000abe4  cmp     rcx, rax
0x18000abe7  jz      short loc_18000ABBC
0x18000abe9  test    byte ptr [rcx+1Ch], 1
0x18000abed  jz      short loc_18000ABBC
0x18000abef  mov     rcx, [rcx+10h]
0x18000abf3  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000abfa  mov     [rsp+68h+var_38], 1073h
0x18000ac02  lea     r9, aStatus; "Status"
0x18000ac09  mov     [rsp+68h+var_40], rax
0x18000ac0e  mov     dword ptr [rsp+68h+var_48], 80090026h
0x18000ac16  call    WPP_SF_sDsd
0x18000ac1b  jmp     short loc_18000ABBC
0x18000ac1d  mov     r9d, 107Ah
0x18000ac23  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ac2a  lea     rdx, aStatus; "Status"
0x18000ac31  mov     ecx, 80090027h
0x18000ac36  mov     esi, 80090027h
0x18000ac3b  call    DebugTraceError
0x18000ac40  jmp     loc_18000ABBC
0x18000ac45  mov     r9d, 1085h
0x18000ac4b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ac52  lea     rdx, aStatus; "Status"
0x18000ac59  mov     ecx, 80090029h
0x18000ac5e  mov     esi, 80090029h
0x18000ac63  call    DebugTraceError
0x18000ac68  jmp     loc_18000ABBC
0x18000ac6d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ac74  mov     r9d, 1091h
0x18000ac7a  lea     rdx, aStatus; "Status"
0x18000ac81  mov     ecx, 8009000Eh
0x18000ac86  mov     esi, 8009000Eh
0x18000ac8b  call    DebugTraceError
0x18000ac90  jmp     loc_18000ABBC
0x18000ac95  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ac9c  mov     r9d, 10A3h
0x18000aca2  lea     rdx, aStatus; "Status"
0x18000aca9  mov     ecx, eax
0x18000acab  call    DebugTraceError
0x18000acb0  mov     rcx, rdi
0x18000acb3  call    MSCryptFree
0x18000acb8  jmp     loc_18000ABBC
```
