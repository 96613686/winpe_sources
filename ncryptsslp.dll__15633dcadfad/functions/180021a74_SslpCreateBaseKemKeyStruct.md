# SslpCreateBaseKemKeyStruct

- ea: `0x180021a74`
- end: `0x180021b57`
- name: `SslpCreateBaseKemKeyStruct`
- size: `227`
- prototype: `__int64 __fastcall(__int64, __int16, int, __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180021b60`
- `0x1800222f0`
- `0x180022420`

## callees

- `0x180007940`
- `0x18000b654`
- `0x180010f60`
- `0x180011110`
- `0x180021a74`
- `0x180022164`

## string_xrefs

- `0x180021b33`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`

## pseudocode

```c
__int64 __fastcall SslpCreateBaseKemKeyStruct(__int64 a1, __int16 a2, int a3, __int64 *a4)
{
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // r9
  __int64 v11; // rcx
  int NCryptProviderHandle; // eax

  if ( a3 && a4 )
  {
    v7 = SafeAllocaAllocateFromHeap(56);
    v8 = v7;
    if ( v7 )
    {
      *(_OWORD *)v7 = 0;
      *(_OWORD *)(v7 + 16) = 0;
      *(_OWORD *)(v7 + 32) = 0;
      *(_QWORD *)(v7 + 48) = 0;
      *(_DWORD *)v7 = 56;
      *(_DWORD *)(v7 + 4) = 1936944188;
      *(_WORD *)(v7 + 44) = a2;
      *(_DWORD *)(v7 + 8) = a3;
      *(_DWORD *)(v7 + 48) = 1;
      NCryptProviderHandle = SslGetNCryptProviderHandle(L"Microsoft Software Key Storage Provider", v7 + 16);
      v9 = NCryptProviderHandle;
      if ( NCryptProviderHandle >= 0 )
      {
        *a4 = v8;
        return v9;
      }
      v9 = NormalizeNteStatus((unsigned int)NCryptProviderHandle, 2148073504LL);
      v11 = v9;
      v10 = 115;
    }
    else
    {
      v9 = -2146893810;
      v10 = 97;
      v11 = 2148073486LL;
    }
  }
  else
  {
    v8 = 0;
    v9 = -2146893785;
    v11 = 2148073511LL;
    v10 = 80;
  }
  DebugTraceError(v11, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", v10);
  if ( v8 )
    SslpFreeKemKey(v8);
  return v9;
}

```

## disassembly

```asm
0x180021a74  push    rbx
0x180021a76  push    rbp
0x180021a77  push    rsi
0x180021a78  push    rdi
0x180021a79  sub     rsp, 28h
0x180021a7d  mov     rsi, r9
0x180021a80  mov     edi, r8d
0x180021a83  movzx   ebp, dx
0x180021a86  test    r8d, r8d
0x180021a89  jz      loc_180021B1C
0x180021a8f  test    r9, r9
0x180021a92  jz      loc_180021B1C
0x180021a98  mov     ecx, 38h ; '8'
0x180021a9d  call    SafeAllocaAllocateFromHeap
0x180021aa2  mov     rbx, rax
0x180021aa5  test    rax, rax
0x180021aa8  jnz     short loc_180021ABA
0x180021aaa  mov     edi, 8009000Eh
0x180021aaf  lea     r9d, [rax+61h]
0x180021ab3  mov     ecx, 8009000Eh
0x180021ab8  jmp     short loc_180021B2C
0x180021aba  xorps   xmm0, xmm0
0x180021abd  lea     rdx, [rbx+10h]
0x180021ac1  movups  xmmword ptr [rbx], xmm0
0x180021ac4  xor     eax, eax
0x180021ac6  lea     rcx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x180021acd  movups  xmmword ptr [rbx+10h], xmm0
0x180021ad1  movups  xmmword ptr [rbx+20h], xmm0
0x180021ad5  mov     [rbx+30h], rax
0x180021ad9  mov     dword ptr [rbx], 38h ; '8'
0x180021adf  mov     dword ptr [rbx+4], 73736C3Ch
0x180021ae6  mov     [rbx+2Ch], bp
0x180021aea  mov     [rbx+8], edi
0x180021aed  mov     dword ptr [rbx+30h], 1
0x180021af4  call    SslGetNCryptProviderHandle
0x180021af9  mov     edi, eax
0x180021afb  test    eax, eax
0x180021afd  jns     short loc_180021B17
0x180021aff  mov     edx, 80090020h
0x180021b04  mov     ecx, eax
0x180021b06  call    NormalizeNteStatus
0x180021b0b  mov     edi, eax
0x180021b0d  mov     ecx, eax
0x180021b0f  mov     r9d, 73h ; 's'
0x180021b15  jmp     short loc_180021B2C
0x180021b17  mov     [rsi], rbx
0x180021b1a  jmp     short loc_180021B4C
0x180021b1c  xor     ebx, ebx
0x180021b1e  mov     edi, 80090027h
0x180021b23  mov     ecx, 80090027h
0x180021b28  lea     r9d, [rbx+50h]
0x180021b2c  lea     rdx, aStatus_0; "status"
0x180021b33  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021b3a  call    DebugTraceError
0x180021b3f  test    rbx, rbx
0x180021b42  jz      short loc_180021B4C
0x180021b44  mov     rcx, rbx
0x180021b47  call    SslpFreeKemKey
0x180021b4c  mov     eax, edi
0x180021b4e  add     rsp, 28h
0x180021b52  pop     rdi
0x180021b53  pop     rsi
0x180021b54  pop     rbp
0x180021b55  pop     rbx
0x180021b56  retn
```
