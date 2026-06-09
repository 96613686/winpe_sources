# SslExtractEarlyKey

- ea: `0x18000adc0`
- end: `0x18000b03e`
- name: `SslExtractEarlyKey`
- size: `638`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000adc0`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000ae4e`
- `ntdll!RtlAllocateHeap` at `0x18000ae4e`

## string_xrefs

- `0x18000af24`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000af76`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000afd5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000aff4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b01c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslExtractEarlyKey(
        _DWORD *a1,
        __int64 a2,
        NCryptKeyName **a3,
        PVOID *a4,
        DWORD a5,
        __int64 a6,
        int a7)
{
  unsigned int v7; // ebp
  _DWORD *v9; // rbx
  __int64 v10; // rsi
  _OWORD *Heap; // rax
  _OWORD *v12; // rdi
  __int64 v13; // rdx
  int v14; // esi

  v7 = (unsigned int)a4;
  v9 = a1;
  if ( !a1 || *a1 < 0x1B0u || a1[1] != 1145324609 || a1[3] )
    v9 = 0;
  if ( a2 && *(_DWORD *)a2 >= 0x20u && *(_DWORD *)(a2 + 4) == 1145324610 )
    v10 = a2;
  else
    v10 = 0;
  if ( v9 && (!a2 || v10) )
  {
    if ( a3 )
    {
      if ( *((_WORD *)v9 + 16) < 4u )
      {
        v14 = -2146893783;
        DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 3607);
      }
      else
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
        v12 = Heap;
        if ( Heap )
        {
          *Heap = 0;
          Heap[1] = 0;
          if ( v10 )
            v13 = *(_QWORD *)(v10 + 16);
          else
            v13 = 0;
          v14 = (*((__int64 (__fastcall **)(_QWORD, __int64, _OWORD *, _QWORD, DWORD, __int64, int))v9 + 35))(
                  *((_QWORD *)v9 + 53),
                  v13,
                  Heap + 1,
                  v7,
                  a5,
                  a6,
                  a7);
          if ( v14 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                a2,
                (_DWORD)a3,
                (unsigned int)"Status",
                v14,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
                54);
            MSCryptFree(v12);
          }
          else
          {
            *(_DWORD *)v12 = 32;
            *(_QWORD *)((char *)v12 + 4) = 1145324610;
            *((_DWORD *)v12 + 3) = 1;
            *((_QWORD *)v12 + 3) = v9;
            _InterlockedIncrement(v9 + 4);
            *a3 = (NCryptKeyName *)v12;
            v14 = 0;
          }
        }
        else
        {
          v14 = -2146893810;
          DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 3619);
        }
      }
    }
    else
    {
      v14 = -2146893785;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          0,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          12);
    }
  }
  else
  {
    v14 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        5);
  }
  return NormalizeNteStatus((unsigned int)v14, (NCRYPT_KEY_HANDLE *)a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000adc0  push    rbx
0x18000adc2  push    rbp
0x18000adc3  push    rsi
0x18000adc4  push    r14
0x18000adc6  sub     rsp, 48h
0x18000adca  mov     ebp, r9d
0x18000adcd  mov     r14, r8
0x18000add0  mov     rbx, rcx
0x18000add3  test    rcx, rcx
0x18000add6  jz      short loc_18000ADEF
0x18000add8  cmp     dword ptr [rcx], 1B0h
0x18000adde  jb      short loc_18000ADEF
0x18000ade0  cmp     dword ptr [rcx+4], 44444441h
0x18000ade7  jnz     short loc_18000ADEF
0x18000ade9  cmp     dword ptr [rcx+0Ch], 0
0x18000aded  jz      short loc_18000ADF1
0x18000adef  xor     ebx, ebx
0x18000adf1  test    rdx, rdx
0x18000adf4  jz      short loc_18000AE08
0x18000adf6  cmp     dword ptr [rdx], 20h ; ' '
0x18000adf9  jb      short loc_18000AE08
0x18000adfb  cmp     dword ptr [rdx+4], 44444442h
0x18000ae02  jz      loc_18000AF51
0x18000ae08  xor     esi, esi
0x18000ae0a  mov     [rsp+68h+arg_0], rdi
0x18000ae0f  test    rbx, rbx
0x18000ae12  jz      loc_18000AEFE
0x18000ae18  test    rdx, rdx
0x18000ae1b  jnz     loc_18000AEF5
0x18000ae21  test    r14, r14
0x18000ae24  jz      loc_18000AFA7
0x18000ae2a  mov     eax, 4
0x18000ae2f  cmp     ax, [rbx+20h]
0x18000ae33  ja      loc_18000AFEE
0x18000ae39  mov     rcx, gs:60h
0x18000ae42  xor     edx, edx; Flags
0x18000ae44  mov     r8d, 20h ; ' '; Size
0x18000ae4a  mov     rcx, [rcx+30h]; HeapHandle
0x18000ae4e  call    cs:__imp_RtlAllocateHeap
0x18000ae54  mov     rdi, rax
0x18000ae57  test    rax, rax
0x18000ae5a  jz      loc_18000B016
0x18000ae60  xorps   xmm0, xmm0
0x18000ae63  movups  xmmword ptr [rax], xmm0
0x18000ae66  movups  xmmword ptr [rax+10h], xmm0
0x18000ae6a  test    rsi, rsi
0x18000ae6d  jz      loc_18000AF4A
0x18000ae73  mov     rdx, [rsi+10h]
0x18000ae77  mov     ecx, [rsp+68h+arg_30]
0x18000ae7e  lea     r8, [rax+10h]
0x18000ae82  mov     rax, [rbx+118h]
0x18000ae89  mov     r9d, ebp
0x18000ae8c  mov     [rsp+68h+var_38], ecx
0x18000ae90  mov     rcx, [rsp+68h+arg_28]
0x18000ae98  mov     [rsp+68h+var_40], rcx
0x18000ae9d  mov     ecx, [rsp+68h+arg_20]
0x18000aea4  mov     [rsp+68h+var_48], ecx
0x18000aea8  mov     rcx, [rbx+1A8h]
0x18000aeaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeb4  mov     esi, eax
0x18000aeb6  test    eax, eax
0x18000aeb8  js      loc_18000AF59
0x18000aebe  mov     dword ptr [rdi], 20h ; ' '
0x18000aec4  mov     qword ptr [rdi+4], 44444442h
0x18000aecc  mov     dword ptr [rdi+0Ch], 1
0x18000aed3  mov     [rdi+18h], rbx
0x18000aed7  lock inc dword ptr [rbx+10h]
0x18000aedb  mov     [r14], rdi
0x18000aede  xor     esi, esi
0x18000aee0  mov     ecx, esi
0x18000aee2  mov     rdi, [rsp+68h+arg_0]
0x18000aee7  add     rsp, 48h
0x18000aeeb  pop     r14
0x18000aeed  pop     rsi
0x18000aeee  pop     rbp
0x18000aeef  pop     rbx
0x18000aef0  jmp     NormalizeNteStatus
0x18000aef5  test    rsi, rsi
0x18000aef8  jnz     loc_18000AE21
0x18000aefe  mov     esi, 80090026h
0x18000af03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af0a  lea     rax, WPP_GLOBAL_Control
0x18000af11  cmp     rcx, rax
0x18000af14  jz      short loc_18000AEE0
0x18000af16  test    byte ptr [rcx+1Ch], 1
0x18000af1a  jz      short loc_18000AEE0
0x18000af1c  mov     [rsp+68h+var_38], 0E05h
0x18000af24  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000af2b  mov     [rsp+68h+var_40], rax
0x18000af30  mov     [rsp+68h+var_48], 80090026h
0x18000af38  mov     rcx, [rcx+10h]
0x18000af3c  lea     r9, aStatus; "Status"
0x18000af43  call    WPP_SF_sDsd
0x18000af48  jmp     short loc_18000AEE0
0x18000af4a  xor     edx, edx
0x18000af4c  jmp     loc_18000AE77
0x18000af51  mov     rsi, rdx
0x18000af54  jmp     loc_18000AE0A
0x18000af59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af60  lea     rax, WPP_GLOBAL_Control
0x18000af67  cmp     rcx, rax
0x18000af6a  jz      short loc_18000AF9A
0x18000af6c  test    byte ptr [rcx+1Ch], 1
0x18000af70  jz      short loc_18000AF9A
0x18000af72  mov     rcx, [rcx+10h]
0x18000af76  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000af7d  mov     [rsp+68h+var_38], 0E36h
0x18000af85  lea     r9, aStatus; "Status"
0x18000af8c  mov     [rsp+68h+var_40], rax
0x18000af91  mov     [rsp+68h+var_48], esi
0x18000af95  call    WPP_SF_sDsd
0x18000af9a  mov     rcx, rdi
0x18000af9d  call    MSCryptFree
0x18000afa2  jmp     loc_18000AEE0
0x18000afa7  mov     esi, 80090027h
0x18000afac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afb3  lea     rax, WPP_GLOBAL_Control
0x18000afba  cmp     rcx, rax
0x18000afbd  jz      loc_18000AEE0
0x18000afc3  test    byte ptr [rcx+1Ch], 1
0x18000afc7  jz      loc_18000AEE0
0x18000afcd  mov     [rsp+68h+var_38], 0E0Ch
0x18000afd5  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000afdc  mov     [rsp+68h+var_40], rax
0x18000afe1  mov     [rsp+68h+var_48], 80090027h
0x18000afe9  jmp     loc_18000AF38
0x18000afee  mov     r9d, 0E17h
0x18000aff4  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000affb  lea     rdx, aStatus; "Status"
0x18000b002  mov     ecx, 80090029h
0x18000b007  mov     esi, 80090029h
0x18000b00c  call    DebugTraceError
0x18000b011  jmp     loc_18000AEE0
0x18000b016  mov     r9d, 0E23h
0x18000b01c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b023  lea     rdx, aStatus; "Status"
0x18000b02a  mov     ecx, 8009000Eh
0x18000b02f  mov     esi, 8009000Eh
0x18000b034  call    DebugTraceError
0x18000b039  jmp     loc_18000AEE0
```
