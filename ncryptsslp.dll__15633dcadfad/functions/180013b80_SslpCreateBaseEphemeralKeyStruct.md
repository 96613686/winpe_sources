# SslpCreateBaseEphemeralKeyStruct

- ea: `0x180013b80`
- end: `0x180013c65`
- name: `SslpCreateBaseEphemeralKeyStruct`
- size: `229`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, int, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180013950`
- `0x180021778`

## callees

- `0x180007940`
- `0x18000b654`
- `0x180010f60`
- `0x180011110`
- `0x180013b80`
- `0x180013e6c`

## string_xrefs

- `0x180013c41`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`

## pseudocode

```c
__int64 __fastcall SslpCreateBaseEphemeralKeyStruct(__int64 a1, unsigned __int16 a2, int a3, __int64 *a4)
{
  int v4; // ebp
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // r9
  __int64 v11; // rcx
  int NCryptProviderHandle; // eax

  v4 = a2;
  if ( a3 && a4 )
  {
    v7 = SafeAllocaAllocateFromHeap(40);
    v8 = v7;
    if ( v7 )
    {
      *(_QWORD *)(v7 + 12) = 0;
      *(_QWORD *)(v7 + 20) = 0;
      *(_DWORD *)(v7 + 28) = 0;
      *(_DWORD *)v7 = 40;
      *(_DWORD *)(v7 + 4) = 1936944182;
      *(_DWORD *)(v7 + 32) = v4;
      *(_DWORD *)(v7 + 8) = a3;
      *(_DWORD *)(v7 + 36) = 1;
      NCryptProviderHandle = SslGetNCryptProviderHandle(L"Microsoft Software Key Storage Provider", v7 + 16);
      v9 = NCryptProviderHandle;
      if ( NCryptProviderHandle >= 0 )
      {
        *a4 = v8;
        return v9;
      }
      v9 = NormalizeNteStatus((unsigned int)NCryptProviderHandle, 2148073504LL);
      v11 = v9;
      v10 = 111;
    }
    else
    {
      v9 = -2146893810;
      v10 = 93;
      v11 = 2148073486LL;
    }
  }
  else
  {
    v8 = 0;
    v9 = -2146893785;
    v11 = 2148073511LL;
    v10 = 76;
  }
  DebugTraceError(v11, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c", v10);
  if ( v8 )
    SslpFreeEphemeralKey(v8);
  return v9;
}

```

## disassembly

```asm
0x180013b80  push    rbx
0x180013b82  push    rbp
0x180013b83  push    rsi
0x180013b84  push    rdi
0x180013b85  sub     rsp, 28h
0x180013b89  movzx   ebp, dx
0x180013b8c  mov     rsi, r9
0x180013b8f  mov     edi, r8d
0x180013b92  test    r8d, r8d
0x180013b95  jz      loc_180013C2A
0x180013b9b  test    r9, r9
0x180013b9e  jz      loc_180013C2A
0x180013ba4  mov     ecx, 28h ; '('
0x180013ba9  call    SafeAllocaAllocateFromHeap
0x180013bae  mov     rbx, rax
0x180013bb1  test    rax, rax
0x180013bb4  jnz     short loc_180013BC6
0x180013bb6  mov     edi, 8009000Eh
0x180013bbb  lea     r9d, [rax+5Dh]
0x180013bbf  mov     ecx, 8009000Eh
0x180013bc4  jmp     short loc_180013C3A
0x180013bc6  mov     qword ptr [rax+0Ch], 0
0x180013bce  lea     rdx, [rax+10h]
0x180013bd2  mov     qword ptr [rax+14h], 0
0x180013bda  lea     rcx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x180013be1  mov     dword ptr [rax+1Ch], 0
0x180013be8  mov     dword ptr [rax], 28h ; '('
0x180013bee  mov     dword ptr [rax+4], 73736C36h
0x180013bf5  mov     [rax+20h], ebp
0x180013bf8  mov     [rax+8], edi
0x180013bfb  mov     dword ptr [rax+24h], 1
0x180013c02  call    SslGetNCryptProviderHandle
0x180013c07  mov     edi, eax
0x180013c09  test    eax, eax
0x180013c0b  jns     short loc_180013C25
0x180013c0d  mov     edx, 80090020h
0x180013c12  mov     ecx, eax
0x180013c14  call    NormalizeNteStatus
0x180013c19  mov     edi, eax
0x180013c1b  mov     ecx, eax
0x180013c1d  mov     r9d, 6Fh ; 'o'
0x180013c23  jmp     short loc_180013C3A
0x180013c25  mov     [rsi], rbx
0x180013c28  jmp     short loc_180013C5A
0x180013c2a  xor     ebx, ebx
0x180013c2c  mov     edi, 80090027h
0x180013c31  mov     ecx, 80090027h
0x180013c36  lea     r9d, [rbx+4Ch]
0x180013c3a  lea     rdx, aStatus_0; "status"
0x180013c41  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013c48  call    DebugTraceError
0x180013c4d  test    rbx, rbx
0x180013c50  jz      short loc_180013C5A
0x180013c52  mov     rcx, rbx
0x180013c55  call    SslpFreeEphemeralKey
0x180013c5a  mov     eax, edi
0x180013c5c  add     rsp, 28h
0x180013c60  pop     rdi
0x180013c61  pop     rsi
0x180013c62  pop     rbp
0x180013c63  pop     rbx
0x180013c64  retn
```
