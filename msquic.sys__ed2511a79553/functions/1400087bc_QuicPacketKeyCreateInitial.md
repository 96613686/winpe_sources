# QuicPacketKeyCreateInitial

- ea: `0x1400087bc`
- end: `0x14000893e`
- name: `QuicPacketKeyCreateInitial`
- size: `386`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140008568`
- `0x14002f204`
- `0x140042e10`

## callees

- `0x1400087bc`
- `0x140008bb0`
- `0x140008ef0`
- `0x140038e38`
- `0x14003c8e0`
- `0x14003ce00`

## pseudocode

```c
__int64 __fastcall QuicPacketKeyCreateInitial(char a1, __int64 a2, int a3, char a4, __int64 a5, _QWORD *a6, _QWORD *a7)
{
  void *v9; // r14
  void *v10; // r15
  int v11; // r8d
  int v12; // ebx
  int v13; // r9d
  int v14; // esi
  _BYTE *v15; // r8
  int v16; // eax
  _BYTE *v17; // r8
  int v18; // eax
  void *v21; // [rsp+38h] [rbp-B9h] BYREF
  void *v22; // [rsp+40h] [rbp-B1h] BYREF
  __int64 v23; // [rsp+48h] [rbp-A9h]
  _BYTE v24[80]; // [rsp+50h] [rbp-A1h] BYREF
  _BYTE v25[80]; // [rsp+A0h] [rbp-51h] BYREF

  v23 = a2;
  memset(v24, 0, 0x48u);
  memset(v25, 0, 0x48u);
  v9 = 0;
  v10 = 0;
  v22 = 0;
  LOBYTE(v11) = a4;
  v21 = 0;
  v12 = CxPlatTlsDeriveInitialSecrets(a3, a5, v11, (unsigned int)v24, (__int64)v25);
  if ( v12 >= 0 )
  {
    v14 = v23;
    if ( !a7 )
      goto LABEL_17;
    v15 = v24;
    if ( a1 )
      v15 = v25;
    v16 = QuicPacketKeyDerive(0, v23, (_DWORD)v15, v13, 1, (__int64)&v21);
    v10 = v21;
    v12 = v16;
    if ( v16 >= 0 )
    {
LABEL_17:
      if ( !a6 )
        goto LABEL_10;
      v17 = v25;
      if ( a1 )
        v17 = v24;
      v18 = QuicPacketKeyDerive(0, v14, (_DWORD)v17, v13, 1, (__int64)&v22);
      v9 = v22;
      v12 = v18;
      if ( v18 >= 0 )
      {
LABEL_10:
        if ( a7 )
        {
          *a7 = v10;
          v10 = 0;
        }
        if ( a6 )
        {
          *a6 = v9;
          v9 = 0;
        }
      }
    }
  }
  QuicPacketKeyFree(v9);
  QuicPacketKeyFree(v10);
  memset(&v24[8], 0, 0x40u);
  memset(&v25[8], 0, 0x40u);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400087bc  mov     [rsp-8+arg_0], rbx
0x1400087c1  push    rbp
0x1400087c2  push    rsi
0x1400087c3  push    rdi
0x1400087c4  push    r12
0x1400087c6  push    r13
0x1400087c8  push    r14
0x1400087ca  push    r15
0x1400087cc  lea     rbp, [rsp-0Fh]
0x1400087d1  sub     rsp, 100h
0x1400087d8  mov     rax, cs:__security_cookie
0x1400087df  xor     rax, rsp
0x1400087e2  mov     [rbp+3Fh+var_40], rax
0x1400087e6  mov     rdi, [rbp+3Fh+arg_20]
0x1400087ea  mov     rsi, r8
0x1400087ed  mov     r12, [rbp+3Fh+arg_28]
0x1400087f1  mov     r14d, 48h ; 'H'
0x1400087f7  mov     r13, [rbp+3Fh+arg_30]
0x1400087fb  mov     r8d, r14d; Size
0x1400087fe  mov     [rsp+130h+var_E8], rdx
0x140008803  mov     bl, r9b
0x140008806  mov     [rsp+130h+var_100], cl
0x14000880a  xor     edx, edx; Val
0x14000880c  lea     rcx, [rsp+130h+var_E0]; void *
0x140008811  call    memset
0x140008816  mov     r8d, r14d; Size
0x140008819  lea     rcx, [rbp+3Fh+var_90]; void *
0x14000881d  xor     edx, edx; Val
0x14000881f  call    memset
0x140008824  lea     rax, [rbp+3Fh+var_90]
0x140008828  xor     r14d, r14d
0x14000882b  xor     r15d, r15d
0x14000882e  mov     [rsp+130h+var_110], rax
0x140008833  lea     r9, [rsp+130h+var_E0]
0x140008838  mov     [rsp+130h+var_F0], r14
0x14000883d  mov     r8b, bl
0x140008840  mov     [rsp+130h+var_F8], r15
0x140008845  mov     rdx, rdi
0x140008848  mov     rcx, rsi
0x14000884b  call    CxPlatTlsDeriveInitialSecrets
0x140008850  mov     ebx, eax
0x140008852  test    eax, eax
0x140008854  js      loc_1400088EE
0x14000885a  mov     dil, [rsp+130h+var_100]
0x14000885f  mov     rsi, [rsp+130h+var_E8]
0x140008864  test    r13, r13
0x140008867  jz      short loc_14000889D
0x140008869  lea     rax, [rbp+3Fh+var_90]
0x14000886d  test    dil, dil
0x140008870  lea     r8, [rsp+130h+var_E0]
0x140008875  mov     rdx, rsi
0x140008878  cmovnz  r8, rax
0x14000887c  lea     rax, [rsp+130h+var_F8]
0x140008881  mov     [rsp+130h+var_108], rax
0x140008886  xor     ecx, ecx
0x140008888  mov     byte ptr [rsp+130h+var_110], 1
0x14000888d  call    QuicPacketKeyDerive
0x140008892  mov     r15, [rsp+130h+var_F8]
0x140008897  mov     ebx, eax
0x140008899  test    eax, eax
0x14000889b  js      short loc_1400088EE
0x14000889d  test    r12, r12
0x1400088a0  jz      short loc_1400088D6
0x1400088a2  lea     rax, [rsp+130h+var_E0]
0x1400088a7  test    dil, dil
0x1400088aa  lea     r8, [rbp+3Fh+var_90]
0x1400088ae  mov     rdx, rsi
0x1400088b1  cmovnz  r8, rax
0x1400088b5  lea     rax, [rsp+130h+var_F0]
0x1400088ba  mov     [rsp+130h+var_108], rax
0x1400088bf  xor     ecx, ecx
0x1400088c1  mov     byte ptr [rsp+130h+var_110], 1
0x1400088c6  call    QuicPacketKeyDerive
0x1400088cb  mov     r14, [rsp+130h+var_F0]
0x1400088d0  mov     ebx, eax
0x1400088d2  test    eax, eax
0x1400088d4  js      short loc_1400088EE
0x1400088d6  test    r13, r13
0x1400088d9  jz      short loc_1400088E2
0x1400088db  mov     [r13+0], r15
0x1400088df  xor     r15d, r15d
0x1400088e2  test    r12, r12
0x1400088e5  jz      short loc_1400088EE
0x1400088e7  mov     [r12], r14
0x1400088eb  xor     r14d, r14d
0x1400088ee  mov     rcx, r14; P
0x1400088f1  call    QuicPacketKeyFree
0x1400088f6  mov     rcx, r15; P
0x1400088f9  call    QuicPacketKeyFree
0x1400088fe  xor     eax, eax
0x140008900  lea     rdi, [rsp+130h+var_D8]
0x140008905  lea     edx, [rax+40h]
0x140008908  mov     ecx, edx
0x14000890a  rep stosb
0x14000890c  lea     rdi, [rbp+3Fh+var_88]
0x140008910  mov     ecx, edx
0x140008912  rep stosb
0x140008914  mov     eax, ebx
0x140008916  mov     rcx, [rbp+3Fh+var_40]
0x14000891a  xor     rcx, rsp; StackCookie
0x14000891d  call    __security_check_cookie
0x140008922  mov     rbx, [rsp+130h+arg_0]
0x14000892a  add     rsp, 100h
0x140008931  pop     r15
0x140008933  pop     r14
0x140008935  pop     r13
0x140008937  pop     r12
0x140008939  pop     rdi
0x14000893a  pop     rsi
0x14000893b  pop     rbp
0x14000893c  retn
```
