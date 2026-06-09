# CxPlatTlsSecConfigSetTicketKeys

- ea: `0x14003695c`
- end: `0x140036a87`
- name: `CxPlatTlsSecConfigSetTicketKeys`
- size: `299`
- prototype: `__int64 __fastcall(PCredHandle phCredential)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140041588`

## callees

- `0x14003695c`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003e928`

## import_xrefs

- `ksecdd!SetCredentialsAttributesW` at `0x140036a28`
- `ksecdd!SetCredentialsAttributesW` at `0x140036a28`

## pseudocode

```c
__int64 __fastcall CxPlatTlsSecConfigSetTicketKeys(PCredHandle phCredential, __int64 a2, unsigned __int8 a3)
{
  int v3; // edi
  unsigned __int8 v7; // si
  __int64 v8; // r14
  unsigned __int8 v9; // al
  __int64 v10; // rbx
  size_t v11; // r8
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // ebx
  _DWORD pBuffer[2]; // [rsp+20h] [rbp-5C8h] BYREF
  _DWORD *v17; // [rsp+28h] [rbp-5C0h]
  _DWORD v18[352]; // [rsp+30h] [rbp-5B8h] BYREF

  v3 = a3;
  if ( a3 > 0x10u )
    return 3221225485LL;
  if ( (phCredential[1].dwLower & 1) != 0 )
    return 3221225659LL;
  v7 = 0;
  if ( a3 )
  {
    do
    {
      v8 = 81LL * v7;
      v9 = *(_BYTE *)(v8 + a2 + 80);
      if ( v9 > 0x40u )
        return 3221225485LL;
      v10 = 22LL * v7;
      v11 = *(unsigned __int8 *)(v8 + a2 + 80);
      v18[v10] = 0;
      LOBYTE(v18[v10 + 21]) = v9;
      memmove(&v18[v10 + 5], (const void *)(v8 + a2 + 16), v11);
      ++v7;
      *(_OWORD *)&v18[v10 + 1] = *(_OWORD *)(v8 + a2);
    }
    while ( v7 < (unsigned __int8)v3 );
  }
  pBuffer[0] = v3;
  pBuffer[1] = 0;
  v17 = v18;
  v12 = SetCredentialsAttributesW(phCredential, 0x73u, pBuffer, 0x10u);
  v15 = v12;
  if ( !v12 )
    return 0;
  if ( (Microsoft_QuicEnableBits & 4) != 0 )
    McTemplateU0qs_EtwWriteTransfer(v14, v13, v12, "SetCredentialsAttributesW(SESSION_TICKET_KEYS)");
  return v15;
}

```

## disassembly

```asm
0x14003695c  mov     [rsp+arg_18], rbx
0x140036961  push    rbp
0x140036962  push    rsi
0x140036963  push    rdi
0x140036964  push    r14
0x140036966  push    r15
0x140036968  sub     rsp, 5C0h
0x14003696f  mov     rax, cs:__security_cookie
0x140036976  xor     rax, rsp
0x140036979  mov     [rsp+5E8h+var_38], rax
0x140036981  movzx   edi, r8b
0x140036985  mov     r15, rdx
0x140036988  mov     rbp, rcx
0x14003698b  cmp     dil, 10h
0x14003698f  ja      loc_140036A5A
0x140036995  mov     eax, [rcx+10h]
0x140036998  test    al, 1
0x14003699a  jz      short loc_1400369A6
0x14003699c  mov     eax, 0C00000BBh
0x1400369a1  jmp     loc_140036A5F
0x1400369a6  xor     sil, sil
0x1400369a9  test    r8b, r8b
0x1400369ac  jz      short loc_1400369FE
0x1400369ae  movzx   ecx, sil
0x1400369b2  imul    r14, rcx, 51h ; 'Q'
0x1400369b6  movzx   eax, byte ptr [r14+r15+50h]
0x1400369bc  cmp     al, 40h ; '@'
0x1400369be  ja      loc_140036A5A
0x1400369c4  imul    rbx, rcx, 58h ; 'X'
0x1400369c8  lea     rdx, [r15+10h]
0x1400369cc  mov     r8d, eax; Size
0x1400369cf  lea     rcx, [rsp+5E8h+var_5A4]
0x1400369d4  add     rdx, r14; Src
0x1400369d7  add     rcx, rbx; void *
0x1400369da  and     [rsp+rbx+5E8h+var_5B8], 0
0x1400369df  mov     [rsp+rbx+5E8h+var_564], al
0x1400369e6  call    memmove
0x1400369eb  movups  xmm0, xmmword ptr [r14+r15]
0x1400369f0  inc     sil
0x1400369f3  movdqu  [rsp+rbx+5E8h+var_5B4], xmm0
0x1400369f9  cmp     sil, dil
0x1400369fc  jb      short loc_1400369AE
0x1400369fe  xor     eax, eax
0x140036a00  mov     [rsp+5E8h+pBuffer], edi
0x140036a04  mov     [rsp+5E8h+var_5C4], eax
0x140036a08  lea     r8, [rsp+5E8h+pBuffer]; pBuffer
0x140036a0d  and     [rsp+5E8h+var_5C4], eax
0x140036a11  mov     r9d, 10h; cbBuffer
0x140036a17  lea     rax, [rsp+5E8h+var_5B8]
0x140036a1c  mov     rcx, rbp; phCredential
0x140036a1f  mov     [rsp+5E8h+var_5C0], rax
0x140036a24  lea     edx, [r9+63h]; ulAttribute
0x140036a28  call    cs:__imp_SetCredentialsAttributesW
0x140036a2f  nop     dword ptr [rax+rax+00h]
0x140036a34  mov     ebx, eax
0x140036a36  test    eax, eax
0x140036a38  jz      short loc_140036A56
0x140036a3a  test    cs:Microsoft_QuicEnableBits, 4
0x140036a41  jz      short loc_140036A52
0x140036a43  lea     r9, aSetcredentials; "SetCredentialsAttributesW(SESSION_TICKE"...
0x140036a4a  mov     r8d, eax
0x140036a4d  call    McTemplateU0qs_EtwWriteTransfer
0x140036a52  mov     eax, ebx
0x140036a54  jmp     short loc_140036A5F
0x140036a56  xor     eax, eax
0x140036a58  jmp     short loc_140036A5F
0x140036a5a  mov     eax, 0C000000Dh
0x140036a5f  mov     rcx, [rsp+5E8h+var_38]
0x140036a67  xor     rcx, rsp; StackCookie
0x140036a6a  call    __security_check_cookie
0x140036a6f  mov     rbx, [rsp+5E8h+arg_18]
0x140036a77  add     rsp, 5C0h
0x140036a7e  pop     r15
0x140036a80  pop     r14
0x140036a82  pop     rdi
0x140036a83  pop     rsi
0x140036a84  pop     rbp
0x140036a85  retn
```
