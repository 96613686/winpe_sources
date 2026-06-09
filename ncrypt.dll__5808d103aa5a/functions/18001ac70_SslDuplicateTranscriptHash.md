# SslDuplicateTranscriptHash

- ea: `0x18001ac70`
- end: `0x18001adc0`
- name: `SslDuplicateTranscriptHash`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009cd0`
- `0x180009ea0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000e120`
- `0x180012b80`
- `0x18001ac70`
- `0x180020010`

## string_xrefs

- `0x18001acd5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001ad97`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslDuplicateTranscriptHash(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7)
{
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // r9d
  __int64 v13; // rdi
  unsigned int v14; // edi
  __int64 v15; // r9
  __int64 v16; // rcx
  NCRYPT_KEY_HANDLE *v17; // rdx
  NCryptKeyName **v18; // r8
  NCryptAlgorithmName **v19; // r9
  _OWORD *v20; // rax
  _OWORD *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // r9
  int v24; // eax

  v8 = ValidateSslProvHandle(a1);
  v10 = ValidateSslHashHandle(v9, v9);
  v13 = v10;
  if ( v8 && v10 )
  {
    if ( !v11 || v12 )
    {
      v14 = -2146893785;
      v15 = 4438;
      v16 = 2148073511LL;
      goto LABEL_7;
    }
    if ( *(_WORD *)(v8 + 32) < 5u )
    {
      v14 = -2146893783;
      v15 = 4449;
      v16 = 2148073513LL;
LABEL_7:
      DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v15);
      return NormalizeNteStatus(v14, v17, v18, v19, a5, a6, a7);
    }
    v20 = (_OWORD *)SafeAllocaAllocateFromHeap(32);
    v21 = v20;
    if ( v20 )
    {
      *v20 = 0;
      v20[1] = 0;
      v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _OWORD *, _QWORD))(v8 + 344))(
              *(_QWORD *)(v8 + 424),
              *(_QWORD *)(v13 + 16),
              v20 + 1,
              0);
      v14 = v24;
      if ( v24 >= 0 )
      {
        *(_DWORD *)v21 = 32;
        *(_QWORD *)((char *)v21 + 4) = 1145324611;
        *((_DWORD *)v21 + 3) = 1;
        *((_QWORD *)v21 + 3) = v8;
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 16));
        *a3 = v21;
        v14 = 0;
        return NormalizeNteStatus(v14, v17, v18, v19, a5, a6, a7);
      }
      v22 = (unsigned int)v24;
      v23 = 4481;
    }
    else
    {
      v14 = -2146893810;
      v22 = 2148073486LL;
      v23 = 4465;
    }
  }
  else
  {
    v21 = 0;
    v14 = -2146893786;
    v22 = 2148073510LL;
    v23 = 4431;
  }
  DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v23);
  if ( v21 )
    MSCryptFree(v21);
  return NormalizeNteStatus(v14, v17, v18, v19, a5, a6, a7);
}

```

## disassembly

```asm
0x18001ac70  push    rbx
0x18001ac72  push    rsi
0x18001ac73  push    rdi
0x18001ac74  push    r14
0x18001ac76  sub     rsp, 38h
0x18001ac7a  mov     r14, r8
0x18001ac7d  call    ValidateSslProvHandle
0x18001ac82  mov     rcx, rdx
0x18001ac85  mov     rsi, rax
0x18001ac88  call    ValidateSslHashHandle
0x18001ac8d  mov     rdi, rax
0x18001ac90  test    rsi, rsi
0x18001ac93  jz      loc_18001AD7E
0x18001ac99  test    rax, rax
0x18001ac9c  jz      loc_18001AD7E
0x18001aca2  test    r8, r8
0x18001aca5  jz      loc_18001AD69
0x18001acab  test    r9d, r9d
0x18001acae  jnz     loc_18001AD69
0x18001acb4  lea     eax, [r9+5]
0x18001acb8  cmp     ax, [rsi+20h]
0x18001acbc  jbe     short loc_18001ACE6
0x18001acbe  mov     edi, 80090029h
0x18001acc3  mov     r9d, 1161h
0x18001acc9  mov     ecx, 80090029h
0x18001acce  lea     rdx, aStatus; "Status"
0x18001acd5  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001acdc  call    DebugTraceError
0x18001ace1  jmp     loc_18001ADB0
0x18001ace6  mov     ecx, 20h ; ' '
0x18001aceb  call    SafeAllocaAllocateFromHeap
0x18001acf0  mov     rbx, rax
0x18001acf3  test    rax, rax
0x18001acf6  jnz     short loc_18001AD0D
0x18001acf8  mov     edi, 8009000Eh
0x18001acfd  mov     ecx, 8009000Eh
0x18001ad02  mov     r9d, 1171h
0x18001ad08  jmp     loc_18001AD90
0x18001ad0d  xorps   xmm0, xmm0
0x18001ad10  lea     r8, [rax+10h]
0x18001ad14  movups  xmmword ptr [rax], xmm0
0x18001ad17  xor     r9d, r9d
0x18001ad1a  movups  xmmword ptr [rax+10h], xmm0
0x18001ad1e  mov     rdx, [rdi+10h]
0x18001ad22  mov     rcx, [rsi+1A8h]
0x18001ad29  mov     rax, [rsi+158h]
0x18001ad30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad35  mov     edi, eax
0x18001ad37  test    eax, eax
0x18001ad39  jns     short loc_18001AD45
0x18001ad3b  mov     ecx, eax
0x18001ad3d  mov     r9d, 1181h
0x18001ad43  jmp     short loc_18001AD90
0x18001ad45  mov     dword ptr [rbx], 20h ; ' '
0x18001ad4b  mov     qword ptr [rbx+4], 44444443h
0x18001ad53  mov     dword ptr [rbx+0Ch], 1
0x18001ad5a  mov     [rbx+18h], rsi
0x18001ad5e  lock inc dword ptr [rsi+10h]
0x18001ad62  mov     [r14], rbx
0x18001ad65  xor     edi, edi
0x18001ad67  jmp     short loc_18001ADB0
0x18001ad69  mov     edi, 80090027h
0x18001ad6e  mov     r9d, 1156h
0x18001ad74  mov     ecx, 80090027h
0x18001ad79  jmp     loc_18001ACCE
0x18001ad7e  xor     ebx, ebx
0x18001ad80  mov     edi, 80090026h
0x18001ad85  mov     ecx, 80090026h
0x18001ad8a  mov     r9d, 114Fh
0x18001ad90  lea     rdx, aStatus; "Status"
0x18001ad97  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ad9e  call    DebugTraceError
0x18001ada3  test    rbx, rbx
0x18001ada6  jz      short loc_18001ADB0
0x18001ada8  mov     rcx, rbx
0x18001adab  call    MSCryptFree
0x18001adb0  mov     ecx, edi
0x18001adb2  add     rsp, 38h
0x18001adb6  pop     r14
0x18001adb8  pop     rdi
0x18001adb9  pop     rsi
0x18001adba  pop     rbx
0x18001adbb  jmp     NormalizeNteStatus
```
