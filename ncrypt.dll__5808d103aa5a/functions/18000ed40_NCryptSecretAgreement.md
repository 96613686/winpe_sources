# NCryptSecretAgreement

- ea: `0x18000ed40`
- end: `0x18000f090`
- name: `NCryptSecretAgreement`
- size: `848`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_KEY_HANDLE hPrivKey, NCRYPT_KEY_HANDLE hPubKey, NCRYPT_SECRET_HANDLE *phAgreedSecret, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000ed40`
- `0x18000f098`
- `0x18000f148`
- `0x18000f634`
- `0x1800173c0`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000ee27`
- `ntdll!RtlAllocateHeap` at `0x18000ee27`

## string_xrefs

- `0x18000edbc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000eef8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000efd2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000f026`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
SECURITY_STATUS __stdcall NCryptSecretAgreement(
        NCRYPT_KEY_HANDLE hPrivKey,
        NCRYPT_KEY_HANDLE hPubKey,
        NCRYPT_SECRET_HANDLE *phAgreedSecret,
        DWORD dwFlags)
{
  NCRYPT_KEY_HANDLE v7; // rbx
  PVOID *v8; // rcx
  unsigned int v9; // ebp
  __int64 v10; // r14
  _QWORD *Heap; // rsi
  unsigned int v12; // eax
  __int64 v13; // rax
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 ProcessName; // rax
  int v18; // edx
  int v19; // ecx
  _BYTE *v20; // rax
  DWORD v21; // [rsp+28h] [rbp-60h]
  int v22; // [rsp+30h] [rbp-58h]
  char v23; // [rsp+30h] [rbp-58h]
  NCRYPT_KEY_HANDLE v24; // [rsp+90h] [rbp+8h] BYREF
  DWORD v25; // [rsp+B0h] [rbp+28h]

  v24 = hPrivKey;
  v7 = hPrivKey;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v21 = dwFlags;
    WPP_SF_PPD(*((_QWORD *)WPP_GLOBAL_Control + 2), hPubKey, phAgreedSecret, v7, hPubKey);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v7 = v24;
  }
  if ( v7 && *(_DWORD *)v7 == 1145307138 )
  {
    if ( hPubKey && *(_DWORD *)hPubKey == 1145307138 )
    {
      v10 = 24;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u);
      if ( Heap )
      {
        *(_OWORD *)Heap = 0;
        Heap[2] = 0;
        while ( 1 )
        {
          v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *, DWORD))(*(_QWORD *)(v7 + 8) + 208LL))(
                  *(_QWORD *)(*(_QWORD *)(v7 + 8) + 272LL),
                  *(_QWORD *)(v7 + 16),
                  *(_QWORD *)(hPubKey + 16),
                  Heap + 2,
                  dwFlags);
          v9 = v12;
          if ( v12 != -2146893778 )
            break;
          if ( (dwFlags & 0x40) != 0 )
          {
            v9 = -2146893790;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                hPubKey,
                (_DWORD)phAgreedSecret,
                (unsigned int)"Status",
                34,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
                179);
            goto LABEL_26;
          }
          v9 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_KEY_HANDLE, const wchar_t *, _QWORD))(*(_QWORD *)(v7 + 8)
                                                                                             + 192LL))(
                 *(_QWORD *)(*(_QWORD *)(v7 + 8) + 272LL),
                 v24,
                 L"NCryptSecretAgreement",
                 0);
          if ( v9 )
            goto LABEL_21;
        }
        if ( v12 )
        {
LABEL_21:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              hPubKey,
              (_DWORD)phAgreedSecret,
              (unsigned int)"Status",
              v9,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
              197);
          if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 1) != 0 )
          {
            v15 = *(_QWORD *)(v7 + 24);
            v16 = *(_QWORD *)(*(_QWORD *)(v7 + 8) + 280LL);
            ProcessName = I_GetProcessName();
            McTemplateU0qzzzzdz_EventWriteTransfer(v19, v18, 8, v16, v15, v21, v22, v9, ProcessName);
          }
LABEL_26:
          v20 = Heap;
          do
          {
            *v20++ = 0;
            --v10;
          }
          while ( v10 );
          MSCryptFree(Heap);
          return NormalizeNteStatus(
                   v9,
                   (NCRYPT_KEY_HANDLE *)hPubKey,
                   (NCryptKeyName **)phAgreedSecret,
                   *(PVOID **)&dwFlags,
                   v25);
        }
        if ( !*(_DWORD *)(v7 + 32) )
          CertInUseLog(2, v7 + 40, &v24);
        *(_DWORD *)Heap = 1145307139;
        Heap[1] = *(_QWORD *)(v7 + 8);
        v13 = *(_QWORD *)(v7 + 8);
        if ( v13 && *(_DWORD *)v13 == 1145307137 )
          _InterlockedIncrement((volatile signed __int32 *)(v13 + 4));
        *phAgreedSecret = (NCRYPT_SECRET_HANDLE)Heap;
      }
      else
      {
        v9 = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            hPubKey,
            (_DWORD)phAgreedSecret,
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            155);
      }
    }
    else
    {
      v9 = -2146893786;
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
      {
        v23 = -114;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v9 = -2146893786;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    {
      v23 = -123;
LABEL_9:
      WPP_SF_sDsd(
        (unsigned int)v8[2],
        hPubKey,
        (_DWORD)phAgreedSecret,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        v23);
    }
  }
  return NormalizeNteStatus(
           v9,
           (NCRYPT_KEY_HANDLE *)hPubKey,
           (NCryptKeyName **)phAgreedSecret,
           *(PVOID **)&dwFlags,
           v25);
}

```

## disassembly

```asm
0x18000ed40  mov     [rsp+arg_18], rbx
0x18000ed45  mov     [rsp+arg_0], rcx
0x18000ed4a  push    rbp
0x18000ed4b  push    rdi
0x18000ed4c  push    r12
0x18000ed4e  push    r13
0x18000ed50  push    r15
0x18000ed52  sub     rsp, 60h
0x18000ed56  mov     r15d, r9d
0x18000ed59  mov     r13, r8
0x18000ed5c  mov     rdi, rdx
0x18000ed5f  mov     rbx, rcx
0x18000ed62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed69  lea     r12, WPP_GLOBAL_Control
0x18000ed70  cmp     rcx, r12
0x18000ed73  jz      short loc_18000ED7B
0x18000ed75  test    byte ptr [rcx+1Ch], 4
0x18000ed79  jnz     short loc_18000EDE5
0x18000ed7b  mov     [rsp+88h+arg_8], rsi
0x18000ed83  mov     [rsp+88h+arg_10], r14
0x18000ed8b  test    rbx, rbx
0x18000ed8e  jz      short loc_18000ED9C
0x18000ed90  cmp     dword ptr [rbx], 44440002h
0x18000ed96  jz      loc_18000F03F
0x18000ed9c  mov     ebp, 80090026h
0x18000eda1  cmp     rcx, r12
0x18000eda4  jz      loc_18000EEAA
0x18000edaa  test    byte ptr [rcx+1Ch], 1
0x18000edae  jz      loc_18000EEAA
0x18000edb4  mov     [rsp+88h+var_58], 0E85h
0x18000edbc  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000edc3  mov     [rsp+88h+var_60], rax
0x18000edc8  mov     dword ptr [rsp+88h+var_68], 80090026h
0x18000edd0  mov     rcx, [rcx+10h]
0x18000edd4  lea     r9, aStatus; "Status"
0x18000eddb  call    WPP_SF_sDsd
0x18000ede0  jmp     loc_18000EEAA
0x18000ede5  mov     rcx, [rcx+10h]
0x18000ede9  mov     r9, rbx
0x18000edec  mov     dword ptr [rsp+88h+var_60], r15d
0x18000edf1  mov     [rsp+88h+var_68], rdi
0x18000edf6  call    WPP_SF_PPD
0x18000edfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee02  mov     rbx, [rsp+88h+arg_0]
0x18000ee0a  jmp     loc_18000ED7B
0x18000ee0f  mov     rcx, gs:60h
0x18000ee18  mov     r14d, 18h
0x18000ee1e  mov     r8d, r14d; Size
0x18000ee21  xor     edx, edx; Flags
0x18000ee23  mov     rcx, [rcx+30h]; HeapHandle
0x18000ee27  call    cs:__imp_RtlAllocateHeap
0x18000ee2d  mov     rsi, rax
0x18000ee30  test    rax, rax
0x18000ee33  jz      loc_18000EFFF
0x18000ee39  xorps   xmm0, xmm0
0x18000ee3c  xor     eax, eax
0x18000ee3e  movups  xmmword ptr [rsi], xmm0
0x18000ee41  mov     [rsi+10h], rax
0x18000ee45  mov     rcx, [rbx+8]
0x18000ee49  lea     r9, [rsi+10h]
0x18000ee4d  mov     r8, [rdi+10h]
0x18000ee51  mov     rdx, [rbx+10h]
0x18000ee55  mov     dword ptr [rsp+88h+var_68], r15d
0x18000ee5a  mov     rax, [rcx+0D0h]
0x18000ee61  mov     rcx, [rcx+110h]
0x18000ee68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee6d  mov     ebp, eax
0x18000ee6f  cmp     eax, 8009002Eh
0x18000ee74  jz      loc_18000EF72
0x18000ee7a  test    eax, eax
0x18000ee7c  jnz     short loc_18000EEDB
0x18000ee7e  cmp     [rbx+20h], eax
0x18000ee81  jz      loc_18000F075
0x18000ee87  mov     dword ptr [rsi], 44440003h
0x18000ee8d  mov     rax, [rbx+8]
0x18000ee91  mov     [rsi+8], rax
0x18000ee95  mov     rax, [rbx+8]
0x18000ee99  test    rax, rax
0x18000ee9c  jz      short loc_18000EEA6
0x18000ee9e  cmp     dword ptr [rax], 44440001h
0x18000eea4  jz      short loc_18000EED5
0x18000eea6  mov     [r13+0], rsi
0x18000eeaa  mov     ecx, ebp
0x18000eeac  mov     r14, [rsp+88h+arg_10]
0x18000eeb4  mov     rsi, [rsp+88h+arg_8]
0x18000eebc  mov     rbx, [rsp+88h+arg_18]
0x18000eec4  add     rsp, 60h
0x18000eec8  pop     r15
0x18000eeca  pop     r13
0x18000eecc  pop     r12
0x18000eece  pop     rdi
0x18000eecf  pop     rbp
0x18000eed0  jmp     NormalizeNteStatus
0x18000eed5  lock inc dword ptr [rax+4]
0x18000eed9  jmp     short loc_18000EEA6
0x18000eedb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eee2  lea     rax, WPP_GLOBAL_Control
0x18000eee9  cmp     rcx, rax
0x18000eeec  jz      short loc_18000EF1C
0x18000eeee  test    byte ptr [rcx+1Ch], 1
0x18000eef2  jz      short loc_18000EF1C
0x18000eef4  mov     rcx, [rcx+10h]
0x18000eef8  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eeff  mov     [rsp+88h+var_58], 0EC5h
0x18000ef07  lea     r9, aStatus; "Status"
0x18000ef0e  mov     [rsp+88h+var_60], rax
0x18000ef13  mov     dword ptr [rsp+88h+var_68], ebp
0x18000ef17  call    WPP_SF_sDsd
0x18000ef1c  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 1
0x18000ef23  jz      short loc_18000EF55
0x18000ef25  mov     rax, [rbx+8]
0x18000ef29  mov     rdi, [rbx+18h]
0x18000ef2d  mov     rbx, [rax+118h]
0x18000ef34  call    I_GetProcessName
0x18000ef39  mov     [rsp+88h+var_48], rax
0x18000ef3e  mov     r9, rbx
0x18000ef41  mov     [rsp+88h+var_50], ebp
0x18000ef45  mov     r8d, 8
0x18000ef4b  mov     [rsp+88h+var_68], rdi
0x18000ef50  call    McTemplateU0qzzzzdz_EventWriteTransfer
0x18000ef55  mov     rax, rsi
0x18000ef58  mov     byte ptr [rax], 0
0x18000ef5b  lea     rax, [rax+1]
0x18000ef5f  sub     r14, 1
0x18000ef63  jnz     short loc_18000EF58
0x18000ef65  mov     rcx, rsi
0x18000ef68  call    MSCryptFree
0x18000ef6d  jmp     loc_18000EEAA
0x18000ef72  test    r15b, 40h
0x18000ef76  jnz     short loc_18000EFB0
0x18000ef78  mov     rcx, [rbx+8]
0x18000ef7c  lea     r8, aNcryptsecretag_0; "NCryptSecretAgreement"
0x18000ef83  mov     rdx, [rsp+88h+arg_0]
0x18000ef8b  xor     r9d, r9d
0x18000ef8e  mov     rax, [rcx+0C0h]
0x18000ef95  mov     rcx, [rcx+110h]
0x18000ef9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efa1  mov     ebp, eax
0x18000efa3  test    eax, eax
0x18000efa5  jz      loc_18000EE45
0x18000efab  jmp     loc_18000EEDB
0x18000efb0  mov     ebp, 80090022h
0x18000efb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efbc  lea     rax, WPP_GLOBAL_Control
0x18000efc3  cmp     rcx, rax
0x18000efc6  jz      short loc_18000EF55
0x18000efc8  test    byte ptr [rcx+1Ch], 1
0x18000efcc  jz      short loc_18000EF55
0x18000efce  mov     rcx, [rcx+10h]
0x18000efd2  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000efd9  mov     [rsp+88h+var_58], 0EB3h
0x18000efe1  lea     r9, aStatus; "Status"
0x18000efe8  mov     [rsp+88h+var_60], rax
0x18000efed  mov     dword ptr [rsp+88h+var_68], 80090022h
0x18000eff5  call    WPP_SF_sDsd
0x18000effa  jmp     loc_18000EF55
0x18000efff  mov     ebp, 8009000Eh
0x18000f004  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f00b  cmp     rcx, r12
0x18000f00e  jz      loc_18000EEAA
0x18000f014  test    byte ptr [rcx+1Ch], 1
0x18000f018  jz      loc_18000EEAA
0x18000f01e  mov     [rsp+88h+var_58], 0E9Bh
0x18000f026  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f02d  mov     [rsp+88h+var_60], rax
0x18000f032  mov     dword ptr [rsp+88h+var_68], 8009000Eh
0x18000f03a  jmp     loc_18000EDD0
0x18000f03f  test    rdi, rdi
0x18000f042  jz      short loc_18000F050
0x18000f044  cmp     dword ptr [rdi], 44440002h
0x18000f04a  jz      loc_18000EE0F
0x18000f050  mov     ebp, 80090026h
0x18000f055  cmp     rcx, r12
0x18000f058  jz      loc_18000EEAA
0x18000f05e  test    byte ptr [rcx+1Ch], 1
0x18000f062  jz      loc_18000EEAA
0x18000f068  mov     [rsp+88h+var_58], 0E8Eh
0x18000f070  jmp     loc_18000EDBC
0x18000f075  lea     rdx, [rbx+28h]
0x18000f079  mov     ecx, 2
0x18000f07e  lea     r8, [rsp+88h+arg_0]
0x18000f086  call    CertInUseLog
0x18000f08b  jmp     loc_18000EE87
```
